---
uid: web-forms/overview/deployment/configuring-server-environments-for-web-deployment/configuring-server-environments-for-web-deployment
title: "Web dağıtımı için sunucu ortamları yapılandırma | Microsoft Docs"
author: jrjlee
description: "Bu öğretici sunucu ortamları desteği tek tıklamayla veya otomatik, Web dağıtımı ve çeşitli farklı scen içine yayımlama için ayarlamak üzere nasıl yapacağınızı gösterir..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 05/04/2012
ms.topic: article
ms.assetid: 0bf0959b-4ca8-45de-bd13-b15347543b5a
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/deployment/configuring-server-environments-for-web-deployment/configuring-server-environments-for-web-deployment
msc.type: authoredcontent
ms.openlocfilehash: 8a07d283e3e4344e5513152cf760ac90481d9f4b
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="configuring-server-environments-for-web-deployment"></a>Web dağıtımı için sunucu ortamları yapılandırma
====================
tarafından [Jason Lee](https://github.com/jrjlee)

[PDF indirin](https://msdnshared.blob.core.windows.net/media/MSDNBlogsFS/prod.evol.blogs.msdn.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/63/56/8130.DeployingWebAppsInEnterpriseScenarios.pdf)

> Bu öğretici sunucu ortamları desteği tek tıklamayla veya otomatik, Web dağıtımı ve çeşitli farklı senaryolarda yayımlama için ayarlamak üzere nasıl yapacağınızı gösterir. Öğretici, dağıtım ve sağlayan senaryo tabanlı genel bakışlar birlikte bir Web grubu çerçevesi (WFF) sunucu grubuna ayarlama belirli yaklaşımlar desteklemek için bir web sunucusu yapılandırma gibi çeşitli görevleri tamamlama aracılığıyla yol için konuları içerir üst düzey uçtan uca yönergeler.
> 
> Öğretici açıklanan Fabrikam, Inc. dağıtım senaryosu kullanır [Kurumsal Web Dağıtımı: senaryoya genel bakış](../deploying-web-applications-in-enterprise-scenarios/enterprise-web-deployment-scenario-overview.md) örnekler ve ağ altyapısı için bir başvuru noktası olarak.
> 
> Bu öğreticileri için bir İtalyanca çeviri ziyaret [http://www.lucamorelli.it](http://www.lucamorelli.it).


Bu öğretici, bu konuları içerir:

- [Web dağıtımı için doğru yaklaşım seçme](choosing-the-right-approach-to-web-deployment.md)
- [Senaryo: bir Test ortamı için Web dağıtımı yapılandırma](scenario-configuring-a-test-environment-for-web-deployment.md)
- [Senaryo: Web dağıtımı için hazırlama ortamını yapılandırma](scenario-configuring-a-staging-environment-for-web-deployment.md)
- [Senaryo: bir üretim ortamı için Web dağıtımı yapılandırma](scenario-configuring-a-production-environment-for-web-deployment.md)
- [Web dağıtımı için yayımlama (Uzak Aracı) bir Web sunucusu yapılandırma](configuring-a-web-server-for-web-deploy-publishing-remote-agent.md)
- [Web için bir Web sunucusu yapılandırma dağıtımı yayımlamadan (Web dağıtımı işleyici)](configuring-a-web-server-for-web-deploy-publishing-web-deploy-handler.md)
- [Web dağıtımı için yayımlama (çevrimdışı dağıtımı) bir Web sunucusu yapılandırma](configuring-a-web-server-for-web-deploy-publishing-offline-deployment.md)
- [Web dağıtımı yayımlama için veritabanı sunucusunu yapılandırma](configuring-a-database-server-for-web-deploy-publishing.md)
- [Web Farm Framework ile bir sunucu grubu oluşturma](creating-a-server-farm-with-the-web-farm-framework.md)
- [Hedef ortam için dağıtım özellikleri yapılandırma](configuring-deployment-properties-for-a-target-environment.md)

İlk konu [Web dağıtımı sağ yaklaşımı seçme](choosing-the-right-approach-to-web-deployment.md), Internet Information Services (IIS) Web Dağıtım Aracı (Web dağıtımı) kullanarak web uygulamaları yayımlamak için kullanabileceğiniz ana yaklaşımları açıklar 2.0. Ayrıca, her bir yaklaşım eşleme senaryoları tanımlar. Buradan, her senaryo konu tamamlamak için gereken görevler üst düzey bir genel bakış sağlar ve bu görevleri tamamlamanıza yardımcı olmak için çalışmasını gerekir konuları tanımlar.

Açıklanan bölünmüş proje dosyası yaklaşım kullanıyorsanız [oluşturma işlemini anlama](../web-deployment-in-the-enterprise/understanding-the-build-process.md) oluşturmak ve son konu çözümünüzü dağıtmak için [hedef ortamiçindağıtımözellikleriyapılandırma](configuring-deployment-properties-for-a-target-environment.md), ortama özgü proje dosyalarını dağıtım farklı bir hedef ortamlar için yapılandırmayı açıklar.

## <a name="key-technologies"></a>Temel teknolojileri

Bu öğretici, bu ürün ve teknolojileri web dağıtımını desteklemek için nasıl kullanılacağı hakkında odaklanır:

- IIS 7.5
- Web dağıtımı 2.x
- WFF 2.x
- IIS Web Yönetim Hizmeti (WMSvc)

Öğreticinin ayrıca Windows Server 2008 R2, SQL Server 2008 R2, ASP.NET 4.0 ve ASP.NET MVC 3 kullanımını dokunur.

## <a name="other-tutorials-in-this-series"></a>Bu serideki diğer öğreticileri

Bu beş eğitim serileri parçası Kurumsal ölçekte web dağıtımı oluşturur. Bu serideki diğer öğreticileri şunlardır:

- [Kuruluş senaryolarında Web uygulamalarını dağıtma](../deploying-web-applications-in-enterprise-scenarios/deploying-web-applications-in-enterprise-scenarios.md). Bu giriş içeriği bağlamsal arka plan öğretici seri için sağlar. Öğretici senaryo açıklar ve görevleri ve izlenecek yollar seriyi açıklanan daha geniş bir uygulama yaşam döngüsü yönetimi (ALM) işlemine nasıl uyduğunu göstermektedir.
- [Web dağıtımı kuruluştaki](../web-deployment-in-the-enterprise/web-deployment-in-the-enterprise.md). Bu öğreticide, Microsoft Build Engine (MSBuild) proje dosyalarına kavramsal bir giriş, Web yayımlama ardışık düzen, Web dağıtımı ve diğer ilgili teknolojiler sağlar. Bunu nasıl bu araçları birlikte karmaşık dağıtım işlemlerini yönetmek için kullanabileceğiniz açıklanmaktadır.
- [Team Foundation Server için Web dağıtımı yapılandırma](../configuring-team-foundation-server-for-web-deployment/configuring-team-foundation-server-for-web-deployment.md). Bu öğretici, Team Foundation Server'ın (TFS) ve belirli derlemeleri dağıtımları el ile tetiklenen otomatik dağıtım sürekli tümleştirme (CI) işleminin bir parçası olarak dahil olmak üzere çeşitli dağıtım senaryosunu destekleyecek şekilde yapılandırmak açıklar.
- [Kurumsal Web dağıtımı Gelişmiş](../advanced-enterprise-web-deployment/advanced-enterprise-web-deployment.md). Bu öğretici, birden çok ortamlar için veritabanı dağıtımları özelleştirme, dağıtımdan dosya ve klasörleri dışarıda ve dağıtım işlemi sırasında çevrimdışı web uygulamaları alma gibi çeşitli daha gelişmiş dağıtım görevlerinin açıklar .

>[!div class="step-by-step"]
[Sonraki](choosing-the-right-approach-to-web-deployment.md)
