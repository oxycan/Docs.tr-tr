---
title: "Veri Koruma API'ları ile çalışmaya başlama"
author: rick-anderson
description: "Bu belge koruma ve uygulama veri koruması kaldırıldığında ASP.NET Core veri koruma API kullanımı açıklanmaktadır."
manager: wpickett
ms.author: riande
ms.date: 10/14/2016
ms.prod: asp.net-core
ms.technology: aspnet
ms.topic: article
uid: security/data-protection/using-data-protection
ms.openlocfilehash: e8c4183f5c47d8ffec8edf163eb1e4d6f2757d9d
ms.sourcegitcommit: a510f38930abc84c4b302029d019a34dfe76823b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="getting-started-with-the-data-protection-apis"></a>Veri Koruma API'ları ile çalışmaya başlama

<a name="security-data-protection-getting-started"></a>

Basit ve koruma verilerini aşağıdaki adımlardan oluşur:

1. Veri koruyucu bir veri koruma sağlayıcıdan oluşturun.

2. Çağrı `Protect` yöntemi ile korumak istediğiniz verileri.

3. Çağrı `Unprotect` yöntemi verilerle istediğiniz geri düz metne dönüştürecek.

Çoğu çerçeveler ve ASP.NET veya SignalR, gibi uygulama modelleri zaten veri koruma sisteminde yapılandırmak ve bağımlılık ekleme erişim bir hizmet kapsayıcısı ekleyin. Aşağıdaki örnek, bir hizmet kapsayıcısı bağımlılık ekleme için yapılandırma ve veri koruma yığını kaydetme, veri koruma sağlayıcısı dı aracılığıyla alma, koruyucusu ve koruma sonra kaldırmayı veri oluşturma gösterir

[!code-csharp[Main](../../security/data-protection/using-data-protection/samples/protectunprotect.cs?highlight=26,34,35,36,37,38,39,40)]

Bir koruyucu oluşturduğunuzda bir veya daha fazla sağlamalısınız [amacı dizeleri](consumer-apis/purpose-strings.md). Bir amaç dize tüketicileri arasında yalıtım sağlar. Örneğin, "Yeşil" amacı dizesi ile oluşturulan bir koruyucu "mor" bir amacı koruyucusu tarafından sağlanan verilerin korumasını yapamazlar.

>[!TIP]
> Örneklerini `IDataProtectionProvider` ve `IDataProtector` olan birden çok çağıranlar için iş parçacığı. Bir bileşen bir başvuru edinir sonra istemiş bir `IDataProtector` çağrısıyla `CreateProtector`, birden çok çağrılar için bu başvuru kullanacağı `Protect` ve `Unprotect`.
>
>Çağrı `Unprotect` korumalı yükü doğrulandı veya yararlanılarak CryptographicException özel durum oluşturacak. Bazı bileşenler hatalarını yok saymak isteyebilirsiniz sırasında işlemleri; korumayı Kaldır kimlik doğrulaması tanımlama bilgileri okuyan bir bileşeni bu hatayı işleyebilir ve isteği, tanımlama bilgisi hiç sahipmiş gibi ele alın yerine depolayabileceği isteği başarısız. Bu davranış istediğiniz bileşenleri tüm özel durumları swallowing yerine CryptographicException özellikle catch.
