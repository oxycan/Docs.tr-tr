---
uid: webhooks/diagnostics/debugging
title: "ASP.NET hata ayıklama Kancalarını | Microsoft Docs"
author: rick-anderson
description: "ASP.NET Web Kancalarını hata ayıklamak nasıl."
ms.author: aspnetcontent
manager: wpickett
ms.date: 01/17/2012
ms.topic: article
ms.assetid: 467da78b-3c35-4c51-8b08-77a32379e4a8
ms.technology: 
ms.prod: .net-framework
ms.openlocfilehash: 566ee353f6a947e3ef0efdfd0af3a81dff2147c7
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
# <a name="aspnet-webhooks-debugging"></a><span data-ttu-id="fc520-103">ASP.NET Web Kancalarını hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="fc520-103">ASP.NET WebHooks debugging</span></span>  

## <a name="debugging-in-azure"></a><span data-ttu-id="fc520-104">Azure'da hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="fc520-104">Debugging in Azure</span></span>

<span data-ttu-id="fc520-105">Web uygulamanızı Azure'da çalıştırılırken hata ayıklamak için lütfen öğretici bakın [Visual Studio kullanarak Azure App Service web uygulamasında sorun giderme](https://azure.microsoft.com/en-us/documentation/articles/web-sites-dotnet-troubleshoot-visual-studio/#webserverlogs).</span><span class="sxs-lookup"><span data-stu-id="fc520-105">To debug your Web Application while running in Azure, please see the tutorial [Troubleshoot a web app in Azure App Service using Visual Studio](https://azure.microsoft.com/en-us/documentation/articles/web-sites-dotnet-troubleshoot-visual-studio/#webserverlogs).</span></span>

## <a name="debugging-with-source-and-symbols"></a><span data-ttu-id="fc520-106">Kaynak ve simgeler ile hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="fc520-106">Debugging with Source and Symbols</span></span>

<span data-ttu-id="fc520-107">Kendi kodunuzu hata ayıklama ek olarak, Microsoft ASP.NET WebHooks doğrudan ve hatta hata ayıklamak mümkündür tüm .NET.</span><span class="sxs-lookup"><span data-stu-id="fc520-107">In addition to debugging your own code, it is possible to debug directly into Microsoft ASP.NET WebHooks, and in fact all of .NET.</span></span> <span data-ttu-id="fc520-108">Bu, olup, yerel olarak veya uzaktan hata ayıklama bağımsız olarak çalışır.</span><span class="sxs-lookup"><span data-stu-id="fc520-108">This works regardless of whether you debug locally or remotely.</span></span> <span data-ttu-id="fc520-109">İlk olarak, kaynak ve simgeleri giderek bulmak için Visual Studio'yu yapılandırma **hata ayıklama** ve ardından **seçenekleri ve ayarları**.</span><span class="sxs-lookup"><span data-stu-id="fc520-109">First, configure Visual Studio to find the source and symbols by going to **Debug** and then **Options and Settings**.</span></span> <span data-ttu-id="fc520-110">Bu gibi seçenekleri ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="fc520-110">Set the options like this:</span></span>

![Seçenekler ve ayarlar](_static/SourceSymbols.png)

<span data-ttu-id="fc520-112">Bağlantı Ekle [symbolsource.org](http://symbolsource.org) kaynak ve simgeleri indirme.</span><span class="sxs-lookup"><span data-stu-id="fc520-112">Then add a link to [symbolsource.org](http://symbolsource.org) for downloading the source and symbols.</span></span> <span data-ttu-id="fc520-113">Git **simgeleri** yukarıdaki menüsünün sekmesini ve bir simgenin konumu olarak aşağıdakileri ekleyin:</span><span class="sxs-lookup"><span data-stu-id="fc520-113">Go to the **Symbols** tab of the menu above and add the following as a symbol location:</span></span>

```
http://srv.symbolsource.org/pdb/Public
```

<span data-ttu-id="fc520-114">Ayrıca, önbellek dizini kısa bir ad olduğundan emin olun; Aksi takdirde dosya adları yüklenmemesi simgeler neden olacak çok uzun elde edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc520-114">In addition, make sure that the cache directory has a short name; otherwise the file names can get too long which will cause the symbols to not load.</span></span> <span data-ttu-id="fc520-115">Bir örnek yolu şöyledir:</span><span class="sxs-lookup"><span data-stu-id="fc520-115">A sample path is:</span></span>

```
C:\SymCache
```

<span data-ttu-id="fc520-116">Ayarları şuna benzer görünmelidir:</span><span class="sxs-lookup"><span data-stu-id="fc520-116">The settings should look similar to this:</span></span>

![Seçenekler simgesi dosyası konumu örneği](_static/SymSource.png)