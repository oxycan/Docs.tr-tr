---
title: "Rol tabanlı yetkilendirme"
author: rick-anderson
description: "Bu belge Authorize özniteliğine rolleri geçirerek ASP.NET Core denetleyici ve eylem erişimi kısıtlamak nasıl gösterir."
manager: wpickett
ms.author: riande
ms.date: 10/14/2016
ms.prod: asp.net-core
ms.technology: aspnet
ms.topic: article
uid: security/authorization/roles
ms.openlocfilehash: 764d1fcc384fc8370d1a536f9609333de6bd4357
ms.sourcegitcommit: a510f38930abc84c4b302029d019a34dfe76823b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="role-based-authorization"></a>Rol tabanlı yetkilendirme

<a name="security-authorization-role-based"></a>

Kimlikteki oluşturduğunuzda bir veya daha fazla role ait. Örneğin, Scott yalnızca kullanıcı rolüne ait olabilir adımında Tracy yönetici ve kullanıcı role ait. Bu roller nasıl oluşturulduğunu ve yönetilen Yetkilendirme işlemi yedekleme deposunda bağlıdır. Rolleri geliştiriciye açığa [IsInRole](https://docs.microsoft.com/dotnet/api/system.security.principal.genericprincipal.isinrole) yöntemi [ClaimsPrincipal](https://docs.microsoft.com/dotnet/api/system.security.claims.claimsprincipal) sınıfı.

## <a name="adding-role-checks"></a>Rol denetimleri ekleme

Rol tabanlı yetkilendirme denetimleri bildirim temelli&mdash;Geliştirici bunları kendi kodundaki bir denetleyici veya eylemin bir denetleyici içinde karşı istenen kaynağa erişmek için geçerli kullanıcının bir üyesi olması gereken roller belirtme katıştırır.

Örneğin, aşağıdaki kod üzerinde herhangi bir eylem erişimi sınırlar `AdministrationController` kullanıcılara bir üyesi olan `Administrator` rol:

```csharp
[Authorize(Roles = "Administrator")]
public class AdministrationController : Controller
{
}
```

Birden çok rol bir virgülle ayrılmış liste olarak belirtebilirsiniz:

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{
}
```

Bu denetleyici yalnızca üyeleri olan kullanıcılar tarafından erişilebilir olan, `HRManager` rol veya `Finance` rol.

Birden çok öznitelik uygularsanız erişen bir kullanıcı belirtilen tüm rollerinin bir üyesi olması gerekir; Aşağıdaki örnek bir kullanıcı hem de bir üyesi olmasını gerektirir `PowerUser` ve `ControlPanelUser` rol.

```csharp
[Authorize(Roles = "PowerUser")]
[Authorize(Roles = "ControlPanelUser")]
public class ControlPanelController : Controller
{
}
```

Eylem düzeyinde ek rol yetkilendirme öznitelikleri uygulayarak erişimi daha da sınırlandırabilirsiniz:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

Önceki kod parçacığını üyelerinde `Administrator` rol veya `PowerUser` rol denetleyicisi erişebilir ve `SetTime` eylem, ancak yalnızca üyeleri `Administrator` rol erişebilir `ShutDown` eylem.

Ayrıca, denetleyicisi kilit ancak ayrı Eylemler anonim ve kimliği doğrulanmamış erişim izin.

```csharp
[Authorize]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [AllowAnonymous]
    public ActionResult Login()
    {
    }
}
```

<a name="security-authorization-role-policy"></a>

## <a name="policy-based-role-checks"></a>İlke tabanlı rol denetimleri

Rol gereksinimlerini de burada bir geliştirici başlangıçta bir ilke yetkilendirme hizmet yapılandırmasının bir parçası kaydeder yeni ilke sözdizimi kullanılarak belirtilebilir. Bu normalde oluşuyor `ConfigureServices()` içinde *haline* dosya.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    services.AddAuthorization(options =>
    {
        options.AddPolicy("RequireAdministratorRole", policy => policy.RequireRole("Administrator"));
    });
}
```

İlkeleri kullanarak uygulanır `Policy` özellikte `AuthorizeAttribute` özniteliği:

```csharp
[Authorize(Policy = "RequireAdministratorRole")]
public IActionResult Shutdown()
{
    return View();
}
```

Birden çok izin verilen rol bir gereksinim olarak belirtmek istediğiniz sonra için parametre olarak belirtebilirsiniz `RequireRole` yöntemi:

```csharp
options.AddPolicy("ElevatedRights", policy =>
                  policy.RequireRole("Administrator", "PowerUser", "BackupAdministrator"));
```

Bu örnek ait kullanıcılar yetkilendirir `Administrator`, `PowerUser` veya `BackupAdministrator` rolleri.
