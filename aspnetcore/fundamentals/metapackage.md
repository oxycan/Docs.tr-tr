---
title: "ASP.NET Core Microsoft.AspNetCore.All metapackage 2.x ve sonraki sürümler"
author: Rick-Anderson
description: "Microsoft.AspNetCore.All metapackage bağımlılıklarını yanı sıra tüm desteklenen ASP.NET Core ve Entity Framework Çekirdek paketleri içerir."
manager: wpickett
ms.author: riande
ms.date: 09/20/2017
ms.prod: asp.net-core
ms.technology: aspnet
ms.topic: article
uid: fundamentals/metapackage
ms.openlocfilehash: 07220fdae299723088fa85e452cedff5e5685bd7
ms.sourcegitcommit: a510f38930abc84c4b302029d019a34dfe76823b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
#<a name="microsoftaspnetcoreall-metapackage-for-aspnet-core-2x"></a>ASP.NET Core Microsoft.AspNetCore.All metapackage 2.x

Bu özellik, ASP.NET Core 2.x hedefleme .NET gerektirir 2.x çekirdek.

[Microsoft.AspNetCore.All](https://www.nuget.org/packages/Microsoft.AspNetCore.All) ASP.NET Core metapackage içerir:

* Tüm paketler ASP.NET Core ekibi tarafından desteklenir.
* Tüm paketleri Entity Framework Çekirdek tarafından desteklenir. 
* ASP.NET Core ve Entity Framework Çekirdek tarafından kullanılan iç ve 3. taraf bağımlılıkları. 

ASP.NET Core tüm özelliklerini 2.x ve Entity Framework Çekirdek 2.x dahil edilmiştir `Microsoft.AspNetCore.All` paket. Bu paket varsayılan proje şablonları kullanın.

Sürüm numarasını `Microsoft.AspNetCore.All` metapackage ASP.NET Core sürüm ve Entity Framework Çekirdek sürüm (.NET Core sürümüyle hizalı) temsil eder.

Kullanan uygulamalar `Microsoft.AspNetCore.All` metapackage otomatik olarak avantajından [.NET çekirdeği çalışma zamanı deposu](https://docs.microsoft.com/dotnet/core/deploying/runtime-store). Çalışma zamanı deposu ASP.NET Core 2.x uygulamaları çalıştırmak için gereken tüm çalışma zamanı varlıklarını içerir. Kullandığınızda `Microsoft.AspNetCore.All` metapackage, **hiçbir** başvurulan ASP.NET Core NuGet paketlerini varlıklarından uygulama ile dağıtılan &mdash; .NET çekirdeği çalışma zamanı deposu bu varlıkları içerir. Çalışma zamanı deposundaki varlıklar uygulama başlangıç zamanını geliştirmek için önceden derlenmiş.

Paket kesme işlemi kullanmadığınız paketleri kaldırmak için kullanabilirsiniz. Yayımlanan uygulama çıktıda bölünen paketleri bırakılır.

Aşağıdaki *.csproj* dosya başvuruları `Microsoft.AspNetCore.All` metapackage ASP.NET Core için:

[!code-xml[Main](..\mvc\views\view-compilation\sample\MvcRazorCompileOnPublish2.csproj?highlight=9)]
