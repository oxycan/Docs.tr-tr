---
uid: web-pages/readme/beta3
title: "Web Matrix ve ASP.NET Web sayfaları (Razor) Beta 3 Sürüm Benioku | Microsoft Docs"
author: rick-anderson
description: "Web Matrix ve ASP.NET Web sayfaları (Razor) Beta 3 Sürüm Benioku dosyası"
ms.author: aspnetcontent
manager: wpickett
ms.date: 01/10/2011
ms.topic: article
ms.assetid: ffa3d5c9-91e5-4da3-b409-560b0c7fbbf0
ms.technology: dotnet-webpages
ms.prod: .net-framework
msc.legacyurl: /web-pages/readme/beta3
msc.type: content
ms.openlocfilehash: 5fad4b659dafe5470aeb84d320ff711b8840d1e0
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="web-matrix-and-aspnet-web-pages-razor-beta-3-release-readme"></a><span data-ttu-id="3f000-103">Web Matrix ve ASP.NET Web sayfaları (Razor) Beta 3 Sürüm Benioku dosyası</span><span class="sxs-lookup"><span data-stu-id="3f000-103">Web Matrix and ASP.NET Web Pages (Razor) Beta 3 Release Readme</span></span>
====================
> <span data-ttu-id="3f000-104">Web Matrix ve ASP.NET Web sayfaları (Razor) Beta 3 Sürüm Benioku dosyası</span><span class="sxs-lookup"><span data-stu-id="3f000-104">Web Matrix and ASP.NET Web Pages (Razor) Beta 3 Release Readme</span></span>

<span data-ttu-id="3f000-105">9 Kasım 2010</span><span class="sxs-lookup"><span data-stu-id="3f000-105">9 November 2010</span></span>

## <a name="contents"></a><span data-ttu-id="3f000-106">İçindekiler</span><span class="sxs-lookup"><span data-stu-id="3f000-106">Contents</span></span>

- [<span data-ttu-id="3f000-107">Genel bakış</span><span class="sxs-lookup"><span data-stu-id="3f000-107">Overview</span></span>](#Overview)
- [<span data-ttu-id="3f000-108">Yükleme</span><span class="sxs-lookup"><span data-stu-id="3f000-108">Installation</span></span>](#Installation_Notes)
- [<span data-ttu-id="3f000-109">Yeni özellikler, değişiklikler ve Beta 3 sürümündeki bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="3f000-109">New Features, Changes, and Known Issues in the Beta 3 release</span></span>](#Known_Issues)

    - [<span data-ttu-id="3f000-110">WebMatrix yükleme sorunları</span><span class="sxs-lookup"><span data-stu-id="3f000-110">WebMatrix Installation Issues</span></span>](#Known_Issues_Installation)
    - [<span data-ttu-id="3f000-111">ASP.NET Web sayfaları</span><span class="sxs-lookup"><span data-stu-id="3f000-111">ASP.NET Web Pages</span></span>](#Known_Issues_ASPNET)
    - [<span data-ttu-id="3f000-112">SQL Server Compact</span><span class="sxs-lookup"><span data-stu-id="3f000-112">SQL Server Compact</span></span>](#Known_Issues_SQL_Server_Compact)
    - [<span data-ttu-id="3f000-113">Uygulamaları yükleme</span><span class="sxs-lookup"><span data-stu-id="3f000-113">Installing Applications</span></span>](#Known_Issues_Installing_Applications)
    - [<span data-ttu-id="3f000-114">Uygulama yayımlama</span><span class="sxs-lookup"><span data-stu-id="3f000-114">Publishing Applications</span></span>](#Known_Issues_Publishing_Applications)
    - [<span data-ttu-id="3f000-115">Diğer Sorunlar</span><span class="sxs-lookup"><span data-stu-id="3f000-115">Other Issues</span></span>](#Known_Issues_Other_Issues)
- [<span data-ttu-id="3f000-116">Daha fazla bilgi için</span><span class="sxs-lookup"><span data-stu-id="3f000-116">For More Information</span></span>](#More_Info)

<a id="Overview"></a>

## <a name="overview"></a><span data-ttu-id="3f000-117">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="3f000-117">Overview</span></span>

> <span data-ttu-id="3f000-118">Microsoft WebMatrix Beta dakikalar içinde yüklenen bir ücretsiz web geliştirme yığını ' dir.</span><span class="sxs-lookup"><span data-stu-id="3f000-118">Microsoft WebMatrix Beta is a free web development stack that installs in minutes.</span></span> <span data-ttu-id="3f000-119">Veritabanını ve programlama çerçevelerini tek, tümleşik bir deneyim sağlamak amacıyla bir web sunucusu tümleştirir.</span><span class="sxs-lookup"><span data-stu-id="3f000-119">It integrates a web server with database and programming frameworks to create a single, integrated experience.</span></span> <span data-ttu-id="3f000-120">Kod, test ve kendi ASP.NET veya PHP Web sitesi yayımlama yolu kolaylaştırmak için WebMatrix Beta kullanabilirsiniz veya DotNetNuke, Umbraco, WordPress veya Joomla gibi popüler açık kaynak uygulamaları kullanarak yeni bir Web sitesini başlatmak için WebMatrix Beta kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f000-120">You can use WebMatrix Beta to streamline the way you code, test, and publish your own ASP.NET or PHP website, or you can use WebMatrix Beta to start a new website using popular open-source apps like DotNetNuke, Umbraco, WordPress, or Joomla.</span></span> <span data-ttu-id="3f000-121">WebMatrix Beta aynı güçlü web sunucusu, veritabanı motoru ve Web sitenizi Internet'e bağlı olmasını sağlayan geliştirmeden üretime geçişinizin sorunsuz ve düzgün çalışır çerçeveler ortamının kullanır.</span><span class="sxs-lookup"><span data-stu-id="3f000-121">WebMatrix Beta uses the same powerful web server, database engine, and frameworks environment that will run your website on the internet, which makes the transition from development to production smooth and seamless.</span></span>


<a id="Installation_Notes"></a>

## <a name="installation"></a><span data-ttu-id="3f000-122">Yükleme</span><span class="sxs-lookup"><span data-stu-id="3f000-122">Installation</span></span>

> <span data-ttu-id="3f000-123">WebMatrix Beta 3'ü yüklemek için kullandığınız [Microsoft Web Platformu yükleyicisi 3.0](https://go.microsoft.com/fwlink/?LinkID=194638).</span><span class="sxs-lookup"><span data-stu-id="3f000-123">To install WebMatrix Beta 3, you use [Microsoft Web Platform Installer 3.0](https://go.microsoft.com/fwlink/?LinkID=194638).</span></span> <span data-ttu-id="3f000-124">Web Platformu yükleyicisi yükledikten sonra WebMatrix Beta 3'ü yüklemek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f000-124">After you've installed the Web Platform Installer, you can use it to install WebMatrix Beta 3.</span></span>
> 
> <span data-ttu-id="3f000-125">Yükleme sırasında sorunlarla karşılaşırsanız, başvurmak [Microsoft Web Platformu Yükleyicisi ile sorunlarını giderme](https://go.microsoft.com/fwlink/?LinkId=196212).</span><span class="sxs-lookup"><span data-stu-id="3f000-125">If you have problems during installation, refer to [Troubleshooting Problems with Microsoft Web Platform Installer](https://go.microsoft.com/fwlink/?LinkId=196212).</span></span>


<a id="Installation_Notes0"></a>

## <a name="instructions-for-publishing-applications"></a><span data-ttu-id="3f000-126">Uygulamaları yayımlama için yönergeler</span><span class="sxs-lookup"><span data-stu-id="3f000-126">Instructions for Publishing Applications</span></span>

> <span data-ttu-id="3f000-127">Bkz: [uygulamaları yayımlama için adım adım yönergeler](https://go.microsoft.com/fwlink/?LinkID=196149)</span><span class="sxs-lookup"><span data-stu-id="3f000-127">See [Step-by-Step Instructions for Publishing Applications](https://go.microsoft.com/fwlink/?LinkID=196149)</span></span>


<a id="Known_Issues"></a>

## <a name="new-features-changes-andknown-issues"></a><span data-ttu-id="3f000-128">Yeni özellikler, değişiklikleri andKnown sorunlar</span><span class="sxs-lookup"><span data-stu-id="3f000-128">New Features, Changes, andKnown Issues</span></span>

<a id="Known_Issues_Installation"></a>

### <a name="webmatrix-beta-3-installation"></a><span data-ttu-id="3f000-129">WebMatrix Beta 3 yükleme</span><span class="sxs-lookup"><span data-stu-id="3f000-129">WebMatrix Beta 3 Installation</span></span>

#### <a name="issue-webmatrix-beta-3-is-only-available-on-platforms-that-support-microsoft-net-framework-4"></a><span data-ttu-id="3f000-130">Sorun: WebMatrix Beta 3 yalnızca Microsoft .NET Framework 4 desteği platformlarda kullanılabilir</span><span class="sxs-lookup"><span data-stu-id="3f000-130">Issue: WebMatrix Beta 3 is only available on platforms that support Microsoft .NET Framework 4</span></span>

> <span data-ttu-id="3f000-131">.NET Framework sürüm 4 WebMatrix Beta için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="3f000-131">The .NET Framework version 4 is required for WebMatrix Beta.</span></span> <span data-ttu-id="3f000-132">Bazı durumlarda, WebMatrix Beta yükleyici, desteklenen bir yapılandırma kümesinin parçası olmayan bir platformda yüklemeye olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="3f000-132">In certain cases, the WebMatrix Beta installer will let you try to install on a platform that is not part of the supported configuration set.</span></span> <span data-ttu-id="3f000-133">Özellikle, Windows Vista SP1 Güncelleştirmesi olmadan, WebMatrix Beta yüklemesini başlatmak olanak tanır ancak .NET Framework 4 bileşen başarısız olacak ve yüklemenizi engelleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-133">In particular, Windows Vista without the SP1 update will let you begin the installation of WebMatrix Beta, but the .NET Framework 4 component will fail and block your installation.</span></span>
> 
> <span data-ttu-id="3f000-134">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-134">**Workaround**</span></span>  
> <span data-ttu-id="3f000-135">İçeren desteklenen bir platform üzerinde yükleyin:</span><span class="sxs-lookup"><span data-stu-id="3f000-135">Install on a supported platform, which includes:</span></span>
> 
> - <span data-ttu-id="3f000-136">Windows 7</span><span class="sxs-lookup"><span data-stu-id="3f000-136">Windows 7</span></span>
> - <span data-ttu-id="3f000-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="3f000-137">Windows Server 2008</span></span>
> - <span data-ttu-id="3f000-138">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3f000-138">Windows Server 2008 R2</span></span>
> - <span data-ttu-id="3f000-139">Windows Vista SP1 veya sonraki sürümü</span><span class="sxs-lookup"><span data-stu-id="3f000-139">Windows Vista SP1 or later</span></span>
> - <span data-ttu-id="3f000-140">Windows XP SP3</span><span class="sxs-lookup"><span data-stu-id="3f000-140">Windows XP SP3</span></span>
> - <span data-ttu-id="3f000-141">Windows Server 2003 SP2</span><span class="sxs-lookup"><span data-stu-id="3f000-141">Windows Server 2003 SP2</span></span>


#### <a name="issue-cannot-install-webmatrix-beta-3-if-microsoft-visual-studio-2008-is-installed-without-microsoft-visual-studio-2008-sp1"></a><span data-ttu-id="3f000-142">Sorun: Microsoft Visual Studio 2008 Microsoft Visual Studio 2008 SP1 yüklediyseniz WebMatrix Beta 3 yükleyemezsiniz</span><span class="sxs-lookup"><span data-stu-id="3f000-142">Issue: Cannot install WebMatrix Beta 3 if Microsoft Visual Studio 2008 is installed without Microsoft Visual Studio 2008 SP1</span></span>

> <span data-ttu-id="3f000-143">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-143">**Workaround**</span></span>  
> <span data-ttu-id="3f000-144">Yükleme [Microsoft Visual Studio 2008 SP1'in](https://www.microsoft.com/downloads/details.aspx?FamilyId=FBEE1648-7106-44A7-9649-6D9F6D58056E&amp;displaylang=en) Microsoft İndirme Merkezi'nden.</span><span class="sxs-lookup"><span data-stu-id="3f000-144">Install [Microsoft Visual Studio 2008 SP1](https://www.microsoft.com/downloads/details.aspx?FamilyId=FBEE1648-7106-44A7-9649-6D9F6D58056E&amp;displaylang=en) from the Microsoft Download Center.</span></span>


#### <a name="issue-some-assemblies-for-sql-server-compact-40-are-not-installed-in-the-gac"></a><span data-ttu-id="3f000-145">Sorun: SQL Server Compact 4.0 için bazı derlemeleri GAC'de yüklü değil</span><span class="sxs-lookup"><span data-stu-id="3f000-145">Issue: Some assemblies for SQL Server Compact 4.0 are not installed in the GAC</span></span>

> <span data-ttu-id="3f000-146">Yönetilen derlemeler SQL Server Compact 4.0 için 64-bit bir bilgisayarda SQL Server Compact 4.0 yükledikten ve bilgisayarın yalnızca .NET Framework 3.5 SP1 istemci yüklü profili olduğunda Genel Derleme Önbelleği (GAC) yerleştirilmez.</span><span class="sxs-lookup"><span data-stu-id="3f000-146">The managed assemblies for SQL Server Compact 4.0 are not placed in the global assembly cache (GAC) when you install SQL Server Compact 4.0 on a 64-bit computer and the computer has only the .NET Framework 3.5 SP1 Client Profile installed.</span></span> <span data-ttu-id="3f000-147">GAC içinde yüklenmemiş Yönetilen derlemeler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="3f000-147">The managed assemblies that are not installed in the GAC are:</span></span>
> 
> - <span data-ttu-id="3f000-148">*System.Data.SqlServerCe.dll* (ADO.NET sağlayıcısı)</span><span class="sxs-lookup"><span data-stu-id="3f000-148">*System.Data.SqlServerCe.dll* (ADO.NET provider)</span></span>
> - <span data-ttu-id="3f000-149">*System.Data.SqlServerCe.Entity.dll* (ADO.NET Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="3f000-149">*System.Data.SqlServerCe.Entity.dll* (ADO.NET Entity Framework )</span></span>
> 
> <span data-ttu-id="3f000-150">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-150">**Workaround**</span></span>  
> <span data-ttu-id="3f000-151">SQL Server'ı kaldırın Compact 4.0.</span><span class="sxs-lookup"><span data-stu-id="3f000-151">Uninstall SQL Server Compact 4.0.</span></span> <span data-ttu-id="3f000-152">Karşıdan yükle ve .NET Framework 3.5 SP1'ın tam sürümünü şu konumdan yükleyin:</span><span class="sxs-lookup"><span data-stu-id="3f000-152">Download and install the full version of .NET Framework 3.5 SP1 from the following location:</span></span>  
>   
> [<span data-ttu-id="3f000-153">Microsoft .NET Framework 3.5 Service pack 1 (tam paketi)</span><span class="sxs-lookup"><span data-stu-id="3f000-153">Microsoft .NET Framework 3.5 Service pack 1 (Full Package)</span></span>](https://go.microsoft.com/fwlink/?LinkId=194828)  
>   
> <span data-ttu-id="3f000-154">SQL Server Compact 4.0 yeniden yükleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-154">Then reinstall SQL Server Compact 4.0.</span></span>


#### <a name="issue-cannot-uninstall-sql-server-compact-using-the-command-line"></a><span data-ttu-id="3f000-155">Sorun: SQL Server komut satırını kullanarak Compact kaldıramadı.</span><span class="sxs-lookup"><span data-stu-id="3f000-155">Issue: Cannot uninstall SQL Server Compact using the command line</span></span>

> <span data-ttu-id="3f000-156">SQL Server komut satırı seçeneklerini kullanarak Compact kaldırılması, bu sürümde çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="3f000-156">Uninstallation of SQL Server Compact using command-line options does not work in this release.</span></span>
> 
> <span data-ttu-id="3f000-157">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-157">**Workaround**</span></span>  
> <span data-ttu-id="3f000-158">Kullanım *programlar ve Özellikler* Microsoft SQL Server Compact 4.0 kaldırmak için Windows Denetim Masası'nda.</span><span class="sxs-lookup"><span data-stu-id="3f000-158">Use *Programs and Features* in the Windows Control Panel to uninstall Microsoft SQL Server Compact 4.0.</span></span>


<a id="Known_Issues_ASPNET"></a>

### <a name="aspnet-web-pages"></a><span data-ttu-id="3f000-159">ASP.NET Web sayfaları</span><span class="sxs-lookup"><span data-stu-id="3f000-159">ASP.NET Web Pages</span></span>

<span data-ttu-id="3f000-160">Bu bölümde belgenin yeni özellikler, değişiklikler ve Razor sözdizimi olan Beta 3 sürümü, ASP.NET Web sayfaları ile ilgili bilinen sorunlar açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="3f000-160">This section of the document describes new features, changes, and known issues with the Beta 3 release of ASP.NET Web Pages with Razor syntax.</span></span>

- [<span data-ttu-id="3f000-161">Yeni Özellikler</span><span class="sxs-lookup"><span data-stu-id="3f000-161">New features</span></span>](#NewFeatures)
- [<span data-ttu-id="3f000-162">Değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="3f000-162">Changes</span></span>](#Changes)
- [<span data-ttu-id="3f000-163">Sorunları</span><span class="sxs-lookup"><span data-stu-id="3f000-163">Issues</span></span>](#Issues)

<a id="NewFeatures"></a>

#### <a name="new-features-in-beta-3-for-aspnet-web-pages-with-razor-syntax"></a><span data-ttu-id="3f000-164">Beta 3 ASP.NET Web sayfaları için Razor sözdizimi olan yeni özellikler</span><span class="sxs-lookup"><span data-stu-id="3f000-164">New Features in Beta 3 for ASP.NET Web Pages with Razor Syntax</span></span>

#### <a name="new-htmlraw-method-renders-unencoded-markup"></a><span data-ttu-id="3f000-165">Yeni: "Html.Raw" yöntemi kodlanmamış biçimlendirme oluşturur</span><span class="sxs-lookup"><span data-stu-id="3f000-165">New: "Html.Raw" method renders unencoded markup</span></span>

> <span data-ttu-id="3f000-166">Yeni `Html.Raw` yöntemi kodlanmış çıkış işleme yerine biçimlendirmesi olarak HTML biçimlendirmesi oluşturmak olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="3f000-166">The new `Html.Raw` method lets you render HTML markup as markup instead of rendering encoded output.</span></span> <span data-ttu-id="3f000-167">(Varsayılan olarak, ASP.NET Razor dizeleri işlemeden önce kodlar.) Sözdizimi şöyledir:</span><span class="sxs-lookup"><span data-stu-id="3f000-167">(By default, ASP.NET Razor encodes strings before rendering them.) The syntax is:</span></span>
> 
> `Html.Raw(value)`
> 
> <span data-ttu-id="3f000-168">Aşağıdaki örnekte nasıl kullanılacağını gösterir `Html.Raw`:</span><span class="sxs-lookup"><span data-stu-id="3f000-168">The following example shows how to use `Html.Raw`:</span></span>
> 
> [!code-cshtml[Main](beta3/samples/sample1.cshtml)]


<a id="Changes"></a>

#### <a name="changes-in-beta-3-for-aspnet-web-pages-with-razor-syntax"></a><span data-ttu-id="3f000-169">Beta 3 ASP.NET Web sayfaları için Razor sözdizimi olan değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="3f000-169">Changes in Beta 3 for ASP.NET Web Pages with Razor Syntax</span></span>

#### <a name="change-hrefattribute-method-removed"></a><span data-ttu-id="3f000-170">Değiştir: kaldırıldı "HrefAttribute" yöntem</span><span class="sxs-lookup"><span data-stu-id="3f000-170">Change: "HrefAttribute" method removed</span></span>

> <span data-ttu-id="3f000-171">`HrefAttribute` Yöntemi `WebPage` sınıfı kaldırıldı.</span><span class="sxs-lookup"><span data-stu-id="3f000-171">The `HrefAttribute` method of the `WebPage` class has been removed.</span></span> <span data-ttu-id="3f000-172">Bu yardımcı URL'lerde güvenli olmayan karakterleri kodlamak için kullanıldı.</span><span class="sxs-lookup"><span data-stu-id="3f000-172">This helper was used to encode unsafe characters in URLs.</span></span> <span data-ttu-id="3f000-173">ASP.NET Razor dizeleri otomatik olarak kodlar çünkü artık gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="3f000-173">It is no longer required because ASP.NET Razor automatically encodes strings.</span></span> <span data-ttu-id="3f000-174">(Yeni `Html.Raw` kodlanmamış dizeleri işlemek için yöntem.)</span><span class="sxs-lookup"><span data-stu-id="3f000-174">(Use the new `Html.Raw` method to render unencoded strings.)</span></span>


#### <a name="change-syntax-for-declarative-helper-helpers-changed"></a><span data-ttu-id="3f000-175">Değişikliği: Sözdizimi bildirim temelli "@helper" değiştirilen Yardımcıları</span><span class="sxs-lookup"><span data-stu-id="3f000-175">Change: Syntax for declarative "@helper" helpers changed</span></span>

> <span data-ttu-id="3f000-176">Nasıl kullanılarak oluşturulan Yardımcıları ayrıştırır ASP.NET Beta 3 sürümü, değişiklikleri `@helper` sözdizimi.</span><span class="sxs-lookup"><span data-stu-id="3f000-176">In the Beta 3 release, ASP.NET changes how it parses helpers that are created using the `@helper` syntax.</span></span> <span data-ttu-id="3f000-177">Esas olarak, `@helper` sözdizimi bir kod bloğu bir blok kod içerebilir biçimlendirme olarak şimdi ayrıştırılır.</span><span class="sxs-lookup"><span data-stu-id="3f000-177">In essence, the `@helper` syntax is now parsed as a code block instead of as a block of markup that can include code.</span></span> <span data-ttu-id="3f000-178">Bu nedenle, yardımcı içinde kod içine gerekmez `@{ }` engeller.</span><span class="sxs-lookup"><span data-stu-id="3f000-178">Therefore, code inside the helper does not need to be enclosed in `@{ }` blocks.</span></span> <span data-ttu-id="3f000-179">Buna karşılık, HTML öğeleri veya ASP.NET Razor açıkça dahil edilecek biçimlendirmesi içinde yardımcı olan `<text></text>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="3f000-179">Conversely, markup inside the helper has to be explicitly included in HTML elements or in ASP.NET Razor `<text></text>` tags.</span></span>
> 
> <span data-ttu-id="3f000-180">Örneğin, aşağıdaki `@helper` sözdizimi Beta 3 sürümde çalışır:</span><span class="sxs-lookup"><span data-stu-id="3f000-180">For example, the following `@helper` syntax works in the Beta 3 release:</span></span>
> 
> [!code-cshtml[Main](beta3/samples/sample2.cshtml)]
> 
> <span data-ttu-id="3f000-181">Beta 3 sürümü, aşağıdaki gibi aramak için bu yardımcı değiştirilmelidir:</span><span class="sxs-lookup"><span data-stu-id="3f000-181">In the Beta 3 release, this helper must be changed to look like the following example:</span></span>
> 
> [!code-cshtml[Main](beta3/samples/sample3.cshtml)]
> 
> <span data-ttu-id="3f000-182">Dikkat `@{ }` yardımcı ilk kodda etrafındaki karakterleri artık kullanılmamaktadır.</span><span class="sxs-lookup"><span data-stu-id="3f000-182">Notice that the `@{ }` characters around the initial code in the helper is no longer used.</span></span> <span data-ttu-id="3f000-183">Bu durum, Yardımcıları içeriğini kod bloğu olarak varsayılan olarak kabul edilir çünkü.</span><span class="sxs-lookup"><span data-stu-id="3f000-183">This is because the contents of the helpers are treated as a code block by default.</span></span> <span data-ttu-id="3f000-184">Yardımcı açılırken başlatır biçimlendirmesini işler `<a>` etiketi.</span><span class="sxs-lookup"><span data-stu-id="3f000-184">The helper renders markup, which starts with the opening `<a>` tag.</span></span> <span data-ttu-id="3f000-185">Yardımcı düz metin veya kapanış etiketi içermez etiketleri oluşturmak gerekir, (örneğin, `<meta>` etiketleri), işlenecek içeriği olmalıdır `<text></text>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="3f000-185">If the helper must render plain text or tags that do not include a closing tag (for example, `<meta>` tags), the content to be rendered must be in `<text></text>` tags.</span></span>


#### <a name="change-webpagecontexthttpcontext-removed"></a><span data-ttu-id="3f000-186">Değişikliği: "WebPageContext.HttpContext" kaldırıldı</span><span class="sxs-lookup"><span data-stu-id="3f000-186">Change: "WebPageContext.HttpContext" removed</span></span>

> <span data-ttu-id="3f000-187">`WebPageContext.HttpContext` Özelliği kaldırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="3f000-187">The `WebPageContext.HttpContext` property has been removed.</span></span> <span data-ttu-id="3f000-188">Bunun yerine `HttpContext.Current` kullanın.</span><span class="sxs-lookup"><span data-stu-id="3f000-188">Use `HttpContext.Current` instead.</span></span> <span data-ttu-id="3f000-189">( `WebPageContext.HttpContext` Özelliği yalnızca Sarmalanan bu.)</span><span class="sxs-lookup"><span data-stu-id="3f000-189">(The `WebPageContext.HttpContext` property simply wrapped this.)</span></span>


#### <a name="change-facebook-helper-moved-to-new-package"></a><span data-ttu-id="3f000-190">Değişikliği: "Facebook" Yardımcısı yeni pakete taşındı.</span><span class="sxs-lookup"><span data-stu-id="3f000-190">Change: "Facebook" helper moved to new package</span></span>

> <span data-ttu-id="3f000-191">`Facebook` Yardımcısı için taşındı *Facebook.Helper* içeren kitaplık `Facebook` Yardımcısı ve ek işlevsellik.</span><span class="sxs-lookup"><span data-stu-id="3f000-191">The `Facebook` helper has been moved to the *Facebook.Helper* library, which includes the `Facebook` helper and additional functionality.</span></span> <span data-ttu-id="3f000-192">Bu kitaplık ayrı bir paket "Yükleme Yardımcıları ile Paket Yöneticisi'nde" açıklandığı gibi öğreticide yüklemelisiniz [ASP.NET sayfaları ile çalışmaya başlama](https://go.microsoft.com/fwlink/?LinkId=202889).</span><span class="sxs-lookup"><span data-stu-id="3f000-192">You must install this library as a separate package, as described in "Installing Helpers with Package Manager" in the tutorial [Getting Started with ASP.NET Pages](https://go.microsoft.com/fwlink/?LinkId=202889).</span></span>


#### <a name="change-membership-role-and-security-types-moves-to-new-assembly"></a><span data-ttu-id="3f000-193">Değişikliği: Yeni bir derleme üyelik ve rol güvenlik türleri taşır</span><span class="sxs-lookup"><span data-stu-id="3f000-193">Change: Membership, Role, and Security types moves to new assembly</span></span>

> <span data-ttu-id="3f000-194">Şu türler için taşındı `WebMatrix.WebData` derleme:</span><span class="sxs-lookup"><span data-stu-id="3f000-194">The following types were moved to the `WebMatrix.WebData` assembly:</span></span>
> 
> - `ExtendedMembershipProvider`
> - `SimpleMembershipProvider`
> - `SimpleRoleProvider`
> - `WebSecurity`


#### <a name="change-tagbuilder-class-moved-to-systemwebwebpagesdll-assembly"></a><span data-ttu-id="3f000-195">Değişikliği: System.Web.WebPages.dll derlemeye taşınmış "TagBuilder" sınıfı</span><span class="sxs-lookup"><span data-stu-id="3f000-195">Change: "TagBuilder" class moved to System.Web.WebPages.dll assembly</span></span>

> <span data-ttu-id="3f000-196">`TagBuilde` r sınıfı System.Web.WebPages.dll derlemeye taşındı.</span><span class="sxs-lookup"><span data-stu-id="3f000-196">The `TagBuilde` r class has been moved to the System.Web.WebPages.dll assembly.</span></span> <span data-ttu-id="3f000-197">Daha önce ASP.NET MVC parçası olan bir derlemede, bu.</span><span class="sxs-lookup"><span data-stu-id="3f000-197">Previously, this was in an assembly that was part of ASP.NET MVC.</span></span> <span data-ttu-id="3f000-198">Bu değişiklik kullanmak için ASP.NET MVC yüklemek gerekmez anlamına gelir `TagBuilder` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="3f000-198">This change means that you do not have to install ASP.NET MVC in order to use the `TagBuilder` class.</span></span>
> 
> <span data-ttu-id="3f000-199">Ancak, yine de sınıftır `System.Web.Mvc` ad alanı.</span><span class="sxs-lookup"><span data-stu-id="3f000-199">However, the class is still in the `System.Web.Mvc` namespace.</span></span> <span data-ttu-id="3f000-200">Kullanmak için `TagBuilder` sınıfta (örneğin, bir özel ASP.NET Razor Yardımcısı), ad alanına başvurmalıdır (ekleyerek Örneğin, `@using System.Web.Mvc` kodunuza).</span><span class="sxs-lookup"><span data-stu-id="3f000-200">In order to use the `TagBuilder` class (for example, in a custom ASP.NET Razor helper), you must reference the namespace (for example, by adding `@using System.Web.Mvc` to your code).</span></span>


#### <a name="change-request-validation-syntax-changed-validation-class-removed"></a><span data-ttu-id="3f000-201">Değişiklik: değiştirilen doğrulama sözdizimi isteği; "Doğrulama" sınıfı kaldırıldı</span><span class="sxs-lookup"><span data-stu-id="3f000-201">Change: Request validation syntax changed; "Validation" class removed</span></span>

> <span data-ttu-id="3f000-202">Beta 3 sürümü, bir tek alan veya alanlar, kümesi için doğrulama devre dışı bırakmak için çağırabilirsiniz `Validation.Exclude` yöntemi, sunucunun adını veya doğrulamanın dışında tutulacak alanların adlarını geçirme.</span><span class="sxs-lookup"><span data-stu-id="3f000-202">In the Beta 3 release, to disable validation for an individual field or set of fields, you can call the `Validation.Exclude` method, passing in the name or names of the fields to exclude from validation.</span></span> <span data-ttu-id="3f000-203">Yeni bir sözdizimi doğrulama atlayarak için Beta 3 sürümünde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-203">A new syntax is available in the Beta 3 release for bypassing validation.</span></span> <span data-ttu-id="3f000-204">`Validation` Beta 3'te kullanılan yöntem kaldırıldı.</span><span class="sxs-lookup"><span data-stu-id="3f000-204">The `Validation` method used in Beta 3 has been removed.</span></span>
> 
> > [!NOTE]
> > <span data-ttu-id="3f000-205">Kullanıcılar (örneğin, bir zengin metin düzenleyici bir sayfada kullanarak) HTML biçimlendirmesi yüklemeye çalışırsanız, istek doğrulamayı devre dışı bırakmayın, Web sitesi gibi bir hata bildirir *potansiyel olarak tehlikeli olabilecek bir Request.Form değeristemcidenalgılandı*ve kullanıcı girişini kabul edilmez.</span><span class="sxs-lookup"><span data-stu-id="3f000-205">If you do not disable request validation, if users try to upload HTML markup (for example, by using a rich text editor on a page), the website will report an error like *A potentially dangerous Request.Form value was detected from the client* and the user input is not accepted.</span></span> <span data-ttu-id="3f000-206">İstek doğrulamayı devre dışı bırakırsanız, kullanıcı girişi bırakmaz potansiyel olarak tehlikeli olabilecek biçimlendirme içeren veya benzeri kullanarak komut dosyası olduğundan emin olmak için el ile denetlemelisiniz [Microsoft virüsten arası Site komut dosyası çalıştırma kitaplığı V4.0](https://www.microsoft.com/downloads/en/details.aspx?FamilyID=f4cd231b-7e06-445b-bec7-343e5884e651).</span><span class="sxs-lookup"><span data-stu-id="3f000-206">If you disable request validation, you must manually check user input to make sure that it does not contain potentially dangerous markup or script using something like the [Microsoft Anti-Cross Site Scripting Library V4.0](https://www.microsoft.com/downloads/en/details.aspx?FamilyID=f4cd231b-7e06-445b-bec7-343e5884e651).</span></span>
> 
> 
> <span data-ttu-id="3f000-207">Otomatik istek doğrulamayı devre dışı bırakmak için çağrı `Request.Unvalidated` yöntemi, alan veya istek doğrulamasını atlamak istediğiniz diğer post nesnesinin adını geçirme.</span><span class="sxs-lookup"><span data-stu-id="3f000-207">To disable automatic request validation, call the `Request.Unvalidated` method, passing it the name of the field or other post object that you want to bypass request validation for.</span></span> <span data-ttu-id="3f000-208">Tüm öğeler için doğrulama atlamak için bu yöntemi kullanabilirsiniz `Form`, `QueryString`, `Cookies`, ve `ServerVariables` koleksiyonları.</span><span class="sxs-lookup"><span data-stu-id="3f000-208">You can use this method to bypass validation for any items in the `Form`, `QueryString`, `Cookies`, and `ServerVariables` collections.</span></span> <span data-ttu-id="3f000-209">Aşağıdaki örnekler nasıl kullanılacağını `Unvalidated` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="3f000-209">The following examples show how to use the `Unvalidated` method:</span></span>
> 
> [!code-csharp[Main](beta3/samples/sample4.cs)]


<a id="Issues"></a>

#### <a name="known-issues-for-aspnet-web-pages-with-razor-syntax"></a><span data-ttu-id="3f000-210">Razor sözdizimi ile ASP.NET Web sayfaları için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="3f000-210">Known Issues for ASP.NET Web Pages with Razor Syntax</span></span>

#### <a name="issue-unexpected-behavior-when-using-a-custom-user-table-for-membership"></a><span data-ttu-id="3f000-211">Sorun: bir özel kullanıcı tablosu için üyeliği kullanırken beklenmeyen davranışları</span><span class="sxs-lookup"><span data-stu-id="3f000-211">Issue: Unexpected behavior when using a custom user table for membership</span></span>

> <span data-ttu-id="3f000-212">Bir ASP.NET Razor Web sitesi için üyelik sağlayıcısını başlatmak için arama `WebSecurity.InitializeDatabaseConnection` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3f000-212">To initialize the membership provider for an ASP.NET Razor website, you call the `WebSecurity.InitializeDatabaseConnection` method.</span></span> <span data-ttu-id="3f000-213">(Webmatrix'te, başlangıç sitesi şablonunda bu yöntem çağrısı içeriyor  *\_AppStart.cshtml* dosyası.) Varsa `autoCreateTables` bu yöntemin parametresi ayarlanmış true (varsayılan olarak ayarlanır başlangıç sitesi şablonunda true), ve bir tanınmayan tablo adı (ikinci parametre) yönteme aktarılırsa, yöntemi bir hata oluşturmadığını.</span><span class="sxs-lookup"><span data-stu-id="3f000-213">(In WebMatrix, the Starter Site template includes a call to this method in the *\_AppStart.cshtml* file.) If the `autoCreateTables` parameter of this method is set to true (by default, it is set to true in the Starter Site template), and if an unrecognized table name is passed to the method (the second parameter), the method does not throw an error.</span></span> <span data-ttu-id="3f000-214">Bunun yerine, tablonun otomatik olarak oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3f000-214">Instead, it automatically creates the table.</span></span>
> 
> <span data-ttu-id="3f000-215">Üyelik için özel bir kullanıcı tablosu kullanır ancak yanlış tablo adını geçirmek istiyorsanız, bu bir sorun olabilir `WebSecurity.InitializeDatabaseConnection` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3f000-215">This can be a problem if you intend to use a custom user table for membership but pass the wrong table name to the `WebSecurity.InitializeDatabaseConnection` method.</span></span> <span data-ttu-id="3f000-216">Belirttiğiniz tablo yoksa, yöntem varsayılan olarak bir hata oluşturmaz olduğundan ve bunun yerine yeni bir tablo oluşturduğundan, uygulama çalışıyor gibi görünebilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-216">Because the method does not by default raise an error if the table you specify does not exist, and because it instead creates a new table, the application can appear to be working.</span></span> <span data-ttu-id="3f000-217">Ancak, özel kullanıcı tablosunda (ve bu alanlara) dayanır uygulama kodu sonunda beklenmeyen hatalarla başarısız olabilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-217">However, application code that relies on your custom user table (and on fields in it) can eventually fail with unexpected errors.</span></span>
> 
> <span data-ttu-id="3f000-218">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-218">**Workaround**</span></span>  
> <span data-ttu-id="3f000-219">Adı geçirilen olduğundan emin olun `InitializeDatabaseConnection` kullanıcı profili tablosu üyelik veritabanında veya olduğundan emin olun yöntemi eşleşme `autoCreateTables` parametresini false olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="3f000-219">Make sure that the name passed in the `InitializeDatabaseConnection` method matches the user profile table in the membership database, or make sure that the `autoCreateTables` parameter is set to false.</span></span>


#### <a name="issue-failed-to-generate-a-user-instance-of-sql-server-error"></a><span data-ttu-id="3f000-220">Sorun: "SQL Server'ın bir kullanıcı örneği oluşturulamadı" hatası</span><span class="sxs-lookup"><span data-stu-id="3f000-220">Issue: "Failed to generate a user instance of SQL Server" error</span></span>

> <span data-ttu-id="3f000-221">Bir WebMatrix Web uygulaması SQL Server Express kullanıyorsa ve Windows 7 veya Windows Server 2008 R2 çalıştıran IIS 7.5, SQL Server çalışma zamanında kullanıcının yerel uygulama yolu alamıyor belirten bir hata görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f000-221">If a WebMatrix Web application uses SQL Server Express and is running IIS 7.5 on Windows 7 or Windows Server 2008 R2, you might see an error that indicates that SQL Server cannot retrieve the user's local application path at run time.</span></span>
> 
> <span data-ttu-id="3f000-222">**Geçici çözüm** uygulama (genellikle altında ağ hizmeti) çalıştıran Windows hesabı alt klasörler ve uygulamanın kök klasör için okuma/yazma izinleri gibi olduğundan emin olun *uygulama\_veri*.</span><span class="sxs-lookup"><span data-stu-id="3f000-222">**Workaround** Make sure that the Windows account that the application runs under (typically NETWORK SERVICE) has read/write permissions for root folders of the application and for subfolders such as *App\_Data*.</span></span> <span data-ttu-id="3f000-223">Bilgi Bankası makalesinde daha ayrıntılı bilgi sağlanmıştır [sorunları kullanıcı SQL Server Express depolamasına ve ASP.net Web uygulaması projelerine](https://support.microsoft.com/kb/2002980).</span><span class="sxs-lookup"><span data-stu-id="3f000-223">More detailed information is available in the KnowledgeBase article [Problems with SQL Server Express user instancing and ASP.net Web Application Projects](https://support.microsoft.com/kb/2002980).</span></span>


#### <a name="issue-in-visual-studio-namespaces-for-custom-assemblies-dlls-are-not-imported-automatically"></a><span data-ttu-id="3f000-224">Sorun: Visual Studio'da özel derleme (dll) için ad alanları otomatik olarak içeri aktarılmaz</span><span class="sxs-lookup"><span data-stu-id="3f000-224">Issue: In Visual Studio, namespaces for custom assemblies (DLLs) are not imported automatically</span></span>

> <span data-ttu-id="3f000-225">Visual Studio'da bir projede özel derlemeler kullanırsanız, bu derlemelerde bildirilen ad alanlarını otomatik olarak tasarım zamanında içeri aktarılmadı.</span><span class="sxs-lookup"><span data-stu-id="3f000-225">If you use custom assemblies in a project in Visual Studio, the namespaces declared in those assemblies are not automatically imported at design time.</span></span> <span data-ttu-id="3f000-226">Sonuç olarak, özel türler için başvuru tasarım zamanında tanınmayabilir ve ("dalgalı" kullanarak) olarak tanınmıyor Visual Studio işaretlenir.</span><span class="sxs-lookup"><span data-stu-id="3f000-226">As a result, references to custom types might not be recognized at design time and are marked as not recognized in Visual Studio (using a "squiggle").</span></span> <span data-ttu-id="3f000-227">Bu sorun, Visual Studio tasarım zamanında yalnızca oluşur; uygulamanın düzgün çalışır.</span><span class="sxs-lookup"><span data-stu-id="3f000-227">This problem occurs only at design time in Visual Studio; the application itself runs properly.</span></span>
> 
> <span data-ttu-id="3f000-228">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-228">**Workaround**</span></span>  
> <span data-ttu-id="3f000-229">Dahil bir `using` deyimi (`imports` Visual Basic'te) tasarım zamanında tanımaz varlıkları başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="3f000-229">Include a `using` statement (`imports` in Visual Basic) that references the entities that are not recognized at design time.</span></span>


#### <a name="issue-visual-studio-intellisense-and-project-templates-available-only-in-aspnet-mvc-version-3"></a><span data-ttu-id="3f000-230">Sorun: Visual Studio IntelliSense ve proje şablonları yalnızca ASP.NET MVC sürüm 3 kullanılabilir</span><span class="sxs-lookup"><span data-stu-id="3f000-230">Issue: Visual Studio IntelliSense and project templates available only in ASP.NET MVC version 3</span></span>

> <span data-ttu-id="3f000-231">ASP.NET Web sayfaları yüklenmesi de araçları Visual Studio için ASP.NET Web Pages uygulamaları için IntelliSense ve proje şablonları gibi yüklemez.</span><span class="sxs-lookup"><span data-stu-id="3f000-231">Installing ASP.NET Web Pages does not also install tools for Visual Studio such as IntelliSense and project templates for ASP.NET Web Pages applications.</span></span>
> 
> <span data-ttu-id="3f000-232">**Geçici çözüm** Visual Studio'da ASP.NET Web Pages uygulamaları için IntelliSense ve proje şablonları kullanmak için ASP.NET MVC 3 RC Web Platformu yükleyicisi yoluyla yüklemek veya [tek başına yükleyici](https://go.microsoft.com/fwlink/?LinkID=191797).</span><span class="sxs-lookup"><span data-stu-id="3f000-232">**Workaround** To use IntelliSense and project templates for ASP.NET Web Pages applications in Visual Studio, install ASP.NET MVC 3 RC either through the Web Platform Installer or the [stand-alone installer](https://go.microsoft.com/fwlink/?LinkID=191797).</span></span>


#### <a name="issue-lthelpergt-class-cannot-be-found-error"></a><span data-ttu-id="3f000-233">Sorun: "&lt;yardımcı&gt; sınıfı bulunamadı" hatası</span><span class="sxs-lookup"><span data-stu-id="3f000-233">Issue: "&lt;helper&gt; class cannot be found" error</span></span>

> <span data-ttu-id="3f000-234">Beta 3'e yükselttikten sonra bir hata görebilirsiniz, bir yardımcı sınıfı (örneğin, `Facebook` sınıfı) bulunamıyor.</span><span class="sxs-lookup"><span data-stu-id="3f000-234">After you upgrade to Beta 3, you might see an error that a helper class (for example, the `Facebook` class) cannot not be found.</span></span> <span data-ttu-id="3f000-235">Beta 2'de başlangıç ve Beta 3'te etmeden, Yardımcıları açıkça yüklemelisiniz paketleri taşınmıştır.</span><span class="sxs-lookup"><span data-stu-id="3f000-235">Starting in Beta 2 and continuing in Beta 3, helpers have been moved to packages that you must explicitly install.</span></span> <span data-ttu-id="3f000-236">Bu paketleri dahil etmek için var olan siteler yükseltilmeden değil; Bu sitede içerir *\My Documents\IISExpress* veya *\My Documents\My Web siteleri* klasörler.</span><span class="sxs-lookup"><span data-stu-id="3f000-236">Existing sites are not upgraded to include these packages; this includes sites in the *\My Documents\IISExpress* or *\My Documents\My Web Sites* folders.</span></span> <span data-ttu-id="3f000-237">Özellikle, varsayılan sitenin kullanırsanız, bu hata iletisiyle karşılaşırsınız *Sitelerim* (Websitesi1), bir başvuru içeren `Twitter` Yardımcısı.</span><span class="sxs-lookup"><span data-stu-id="3f000-237">In particular, you will see this error if you use the default site in *My Sites* (WebSite1), which includes a reference to the `Twitter` helper.</span></span>
> 
> <span data-ttu-id="3f000-238">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-238">**Workaround**</span></span>  
> <span data-ttu-id="3f000-239">Açıklama çalıştırmak sitedeki tüm yardımcıları çağrıları çıkışı  *\_yönetici* sayfasında ve paket veya kullanmak istediğiniz Yardımcıları dahil paketlerini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-239">Comment out calls to any helpers in the site, run the *\_Admin* page, and install the package or packages that include the helpers that you want to use.</span></span> <span data-ttu-id="3f000-240">Paketi yükledikten sonra Yardımcıları başvuru satırları açıklamadan çıkarın.</span><span class="sxs-lookup"><span data-stu-id="3f000-240">After you've installed the package, you can uncomment the lines that reference helpers.</span></span>


#### <a name="issue-deploying-beta-3-aspnet-razor-assemblies-to-the-bin-folder-might-not-work-on-hosting-sites"></a><span data-ttu-id="3f000-241">Sorun: Bin klasörüne Beta 3 ASP.NET Razor derlemeleri dağıtma siteleri barındırma çalışmayabilir</span><span class="sxs-lookup"><span data-stu-id="3f000-241">Issue: Deploying Beta 3 ASP.NET Razor assemblies to the Bin folder might not work on hosting sites</span></span>

> <span data-ttu-id="3f000-242">Bir ASP.NET Web Pages Web sitesi barındırma bir siteye dağıtırsanız ve sitenin ASP.NET Razor Beta 3 derlemeleri dağıtırsanız *Bin* klasörü, hatalar, aşağıdakiler dahil deneyimi:</span><span class="sxs-lookup"><span data-stu-id="3f000-242">If you deploy an ASP.NET Web Pages website to a hosting site, and if you deploy the ASP.NET Razor Beta 3 assemblies to the site's *Bin* folder, you might experience errors, including the following:</span></span>
> 
> `Could not load type 'Microsoft.Web.Infrastructure.DynamicModuleHelper.DynamicModuleUtility' from assembly 'Microsoft.Web.Infrastructure, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.`
> 
> <span data-ttu-id="3f000-243">Barındırma sağlayıcısı ASP.NET Web sayfaları Beta 1 derlemeleri sunucunun genel uygulama önbelleğine (GAC) yüklü olmadığını bu durum oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-243">This can happen if the hosting provider has installed the ASP.NET Web Pages Beta 1 assemblies into the server's global application cache (GAC).</span></span> <span data-ttu-id="3f000-244">Derleme GAC içinde yerel olarak yüklenmiş derlemeleri Öncelik Alma *Bin* klasör.</span><span class="sxs-lookup"><span data-stu-id="3f000-244">Assemblies in the GAC get precedence over assemblies installed locally in the *Bin* folder.</span></span>
> 
> <span data-ttu-id="3f000-245">**Geçici çözüm** gördüğünüz hataları sağlayıcının sürümleri arasında bir çakışma nedeniyle olduğunu doğrulamak için barındırma sağlayıcınızla bağlantı kurun ve derlemeler size ait.</span><span class="sxs-lookup"><span data-stu-id="3f000-245">**Workaround** Contact your hosting provider to confirm that the errors you are seeing are due to a conflict between the provider's versions of the assemblies and yours.</span></span> <span data-ttu-id="3f000-246">Bu durumda, barındırma sağlayıcısı sunucunun GAC derlemelerde güncelleştirme isteği.</span><span class="sxs-lookup"><span data-stu-id="3f000-246">If so, request that the hosting provider update the assemblies in the server's GAC.</span></span>


#### <a name="issue-reading-feeds-or-other-external-data-via-a-proxy-server"></a><span data-ttu-id="3f000-247">Sorun: akışları ya da bir proxy sunucu üzerinden diğer dış veri okuma</span><span class="sxs-lookup"><span data-stu-id="3f000-247">Issue: Reading feeds or other external data via a proxy server</span></span>

> <span data-ttu-id="3f000-248">Site sunucusunu bir proxy sunucunun arkasında ise, proxy bilgileri yapılandırmanız gerekebilir *Web.config* sitenizi dışında geldiği bilgileri okumak için dosya.</span><span class="sxs-lookup"><span data-stu-id="3f000-248">If the server running the site is behind a proxy server, you might need to configure proxy information in the *Web.config* file in order to be able to read information that comes from outside your site.</span></span> <span data-ttu-id="3f000-249">Örneğin, kullanırsanız `ReCaptcha` Yardımcısı, yardımcı reCAPTCHA hizmetiyle iletişim kurar, ancak proxy sunucunuz tarafından engellenmiş olabilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-249">For example, if you use the `ReCaptcha` helper, the helper communicates with the reCAPTCHA service, but might be blocked by your proxy server.</span></span> <span data-ttu-id="3f000-250">Benzer şekilde, Paket Yöneticisi tarafından kullanılan akış gibi ASP.NET Web Pages'da kullanılan akışları proxy yapılandırma gerektirebilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-250">Similarly, feeds that are used in ASP.NET Web Pages, such as the feed used by the package manager, might require proxy configuration.</span></span>
> 
> <span data-ttu-id="3f000-251">Bir dış hizmeti ile çalışma veya akış paketiyle çalışma sorunlarla karşılaşırsanız, aşağıdaki öğeleri, uygulamanızın kök koyabilirsiniz *Web.config* dosyası:</span><span class="sxs-lookup"><span data-stu-id="3f000-251">If you experience problems in working with an external service or working with the package feed, put the following elements into your application's root *Web.config* file:</span></span>
> 
> [!code-xml[Main](beta3/samples/sample5.xml)]
> 
> <span data-ttu-id="3f000-252">Bir proxy sunucusu yapılandırma hakkında daha fazla bilgi için bkz: [ &lt;proxy&gt; öğesi (ağ ayarları)](https://msdn.microsoft.com/en-us/library/sa91de1e.aspx) MSDN Web sitesinde.</span><span class="sxs-lookup"><span data-stu-id="3f000-252">For more information about configuring a proxy server, see [&lt;proxy&gt; Element (Network Settings)](https://msdn.microsoft.com/en-us/library/sa91de1e.aspx) on the MSDN Web site.</span></span>


#### <a name="issue-microsoftwebinfrastructuredll-cannot-be-loaded-error"></a><span data-ttu-id="3f000-253">Sorun: "Microsoft.Web.Infrastructure.dll yüklenemiyor" hatası</span><span class="sxs-lookup"><span data-stu-id="3f000-253">Issue: "Microsoft.Web.Infrastructure.dll cannot be loaded" error</span></span>

> <span data-ttu-id="3f000-254">Razor sözdizimi ile ASP.NET Web sayfaları, Beta 1 sürümünü önceden yüklenmiş Beta 3 sürümünü yüklerseniz, tüm uygun derlemeleri dışında GAC'de yüklü *Microsoft.Web.Infrastructure.dll*.</span><span class="sxs-lookup"><span data-stu-id="3f000-254">If you previously installed the Beta 1 version of ASP.NET Web Pages with Razor syntax and then install the Beta 3 version, all appropriate assemblies are installed in the GAC except *Microsoft.Web.Infrastructure.dll*.</span></span> <span data-ttu-id="3f000-255">Sonuç olarak, ASP.NET Razor sayfalarının çalıştırdığınızda belirten bir hata bkz *Microsoft.Web.Infrastructure.dll* yüklenemedi.</span><span class="sxs-lookup"><span data-stu-id="3f000-255">As a consequence, when you run ASP.NET Razor pages, you see an error that indicates that *Microsoft.Web.Infrastructure.dll* could not be loaded.</span></span>
> 
> <span data-ttu-id="3f000-256">Beta 3 sürümünün temiz bir bilgisayarda yüklü değilse bu sorun gerçekleşmez.</span><span class="sxs-lookup"><span data-stu-id="3f000-256">This issue does not occur if you loaded the Beta 3 release on a clean computer.</span></span>
> 
> <span data-ttu-id="3f000-257">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-257">**Workaround**</span></span>  
> <span data-ttu-id="3f000-258">Denetim Masası'nda, ASP.NET Web sayfaları kaldırın.</span><span class="sxs-lookup"><span data-stu-id="3f000-258">In Control Panel, uninstall ASP.NET Web Pages.</span></span> <span data-ttu-id="3f000-259">Yeniden Beta 3 sürümü yükleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-259">Then reinstall the Beta 3 release.</span></span>


#### <a name="issue-uninstalling-the-net-framework-version-4-disables-aspnet-web-pages-with-razor-syntax"></a><span data-ttu-id="3f000-260">Sorun: .NET Framework sürüm 4 kaldırma Razor sözdizimi ile ASP.NET Web sayfaları devre dışı bırakır</span><span class="sxs-lookup"><span data-stu-id="3f000-260">Issue: Uninstalling the .NET Framework version 4 disables ASP.NET Web Pages with Razor Syntax</span></span>

> <span data-ttu-id="3f000-261">.NET Framework sürüm 4 kaldırın ve yeniden yükleyin, Razor sözdizimi ile ASP.NET Web sayfaları devre dışı bırakılır.</span><span class="sxs-lookup"><span data-stu-id="3f000-261">If you uninstall the .NET Framework version 4 and then reinstall it, ASP.NET Web Pages with Razor syntax is disabled.</span></span> <span data-ttu-id="3f000-262">İle sayfaları *.cshtml* uzantısı düzgün çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="3f000-262">Pages with the *.cshtml* extension do not run correctly.</span></span> <span data-ttu-id="3f000-263">ASP.NET Web sayfaları kaydeder bütünleştirilmiş makine kök dizininde *Web.config* dosyasını ve .NET Framework kaldırma bu dosyayı kaldırır.</span><span class="sxs-lookup"><span data-stu-id="3f000-263">ASP.NET Web Pages registers an assembly in the machine root *Web.config* file, and removing the .NET Framework removes that file.</span></span> <span data-ttu-id="3f000-264">.NET Framework yeniden yapılandırma dosyasını yeni bir sürümünü yükler, ancak başvuru için ASP.NET Web sayfaları derlemesi eklemez.</span><span class="sxs-lookup"><span data-stu-id="3f000-264">Reinstalling the .NET Framework installs a new version of the configuration file, but does not add the reference for the ASP.NET Web Pages assembly.</span></span>
> 
> <span data-ttu-id="3f000-265">**Geçici çözüm** .NET Framework yeniden yükledikten sonra Razor sözdizimi ile ASP.NET Web sayfaları yeniden yükleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-265">**Workaround** After reinstalling the .NET Framework, reinstall ASP.NET Web Pages with Razor syntax.</span></span> <span data-ttu-id="3f000-266">Bu şu öğeye ekler *Web.config* genellikle şu konumdadır makine kök dosyasında:</span><span class="sxs-lookup"><span data-stu-id="3f000-266">This adds the following element to the *Web.config* file in the machine root, which is typically in the following location:</span></span>  
>   
> `C:\Windows\Microsoft.NET\Framework\v4.0.30319\Config (32-bit)`  
>   
> `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config (64-bit)`
> 
> [!code-xml[Main](beta3/samples/sample6.xml)]


#### <a name="issue-applications-previously-deployed-with-aspnet-assemblies-in-the-bin-folder-experience-errors"></a><span data-ttu-id="3f000-267">Sorun: Bin klasöründeki ASP.NET derlemeler ile daha önce dağıtılan uygulamalar hataları deneyimi</span><span class="sxs-lookup"><span data-stu-id="3f000-267">Issue: Applications previously deployed with ASP.NET assemblies in the Bin folder experience errors</span></span>

> <span data-ttu-id="3f000-268">Dağıtımı sırasında ASP.NET Web sayfaları derlemeleri kopyalarını (örneğin, *Microsoft.WebPages.dll*) için *Bin* Web sitesinin sunucudaki klasör.</span><span class="sxs-lookup"><span data-stu-id="3f000-268">During deployment, copies of the ASP.NET Web Pages assemblies (for example, *Microsoft.WebPages.dll*) to the *Bin* folder of the website on the server.</span></span> <span data-ttu-id="3f000-269">(Bu otomatik olarak dağıtım sırasında oluşmuş veya Geliştirici açıkça derlemeler kopyalanmadığından.) Ancak, Beta 3 sürümü yüklendiğinde, hatalar meydana gelir, belirli türleri bulunamıyor hataları gibi.</span><span class="sxs-lookup"><span data-stu-id="3f000-269">(This might have happened automatically during deployment or because the developer explicitly copied the assemblies.) However, when the Beta 3 release is installed, errors occurs, such as errors that certain types cannot be found.</span></span> <span data-ttu-id="3f000-270">Bu durum, ASP.NET Web sayfaları türlerinin sayısı Beta 3 sürüm için farklı ad alanında taşındı kaynaklanır.</span><span class="sxs-lookup"><span data-stu-id="3f000-270">This occurs because a number of ASP.NET Web Pages types were moved into different namespaces for the Beta 3 release.</span></span>
> 
> <span data-ttu-id="3f000-271">**Geçici çözüm** </span><span class="sxs-lookup"><span data-stu-id="3f000-271">**Workaround** </span></span>  
> <span data-ttu-id="3f000-272">Clear *Bin* dağıtılan bir uygulama klasörünü yeni derlemeleri klasörüne kopyalayın (veya uygulamayı yeniden Dağıt) ve uygulamayı yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="3f000-272">Clear the *Bin* folder of the deployed application, copy the new assemblies to the folder (or redeploy the application), and then restart the application.</span></span>


#### <a name="issue-extensionless-urls-do-not-find-cshtmlvbhtml-files-on-iis-7-or-iis-75"></a><span data-ttu-id="3f000-273">Sorun: IIS 7 veya IIS 7.5.cshtml/.vbhtml dosyaları uzantısız URL'leri bulamazsanız</span><span class="sxs-lookup"><span data-stu-id="3f000-273">Issue: Extensionless URLs do not find .cshtml/.vbhtml files on IIS 7 or IIS 7.5</span></span>

> <span data-ttu-id="3f000-274">IIS 7 veya IIS 7.5, aşağıdaki gibi bir URL ile istekleri sahip sayfalar bulamıyor olmayan *.cshtml* veya *.vbhtml* uzantısı:</span><span class="sxs-lookup"><span data-stu-id="3f000-274">On IIS 7 or IIS 7.5, requests with a URL like the following are not able to find pages that have the *.cshtml* or *.vbhtml* extension:</span></span>  
>   
> `http://www.example.com/ExampleSite/ExampleFile`  
>   
> <span data-ttu-id="3f000-275">URL yeniden yazma işlemi varsayılan olarak IIS 7 veya IIS 7.5 için etkinleştirilmediğinden sorun ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="3f000-275">The issue arises because URL rewriting is not enabled by default for IIS 7 or IIS 7.5.</span></span> <span data-ttu-id="3f000-276">Denetçilerinde IIS Express kullanarak yerel olarak test ederken sorun görmezsiniz, ancak Web sitenizi barındıran bir Web sitesine dağıttığınızda deneyimi senaryodur.</span><span class="sxs-lookup"><span data-stu-id="3f000-276">The likeliest scenario is that you do not see the problem when testing locally using IIS Express, but you experience it when you deploy your website to a hosting website.</span></span>
> 
> <span data-ttu-id="3f000-277">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-277">**Workaround**</span></span>
> 
> - <span data-ttu-id="3f000-278">Sunucu bilgisayarı üzerinde denetim varsa, sunucu bilgisayarda açıklanan güncelleştirmeyi [bir güncelleştirme etkinleştirir işlemek için IIS 7.0 veya IIS 7.5 işleyicilerinin URL'leri isteklerini belirli bir nokta ile bitmeyen kullanılabilir](https://support.microsoft.com/kb/980368).</span><span class="sxs-lookup"><span data-stu-id="3f000-278">If you have control over the server computer, on the server computer install the update that is described in [A update is available that enables certain IIS 7.0 or IIS 7.5 handlers to handle requests whose URLs do not end with a period](https://support.microsoft.com/kb/980368).</span></span>
> - <span data-ttu-id="3f000-279">Sunucu bilgisayarı üzerinde denetim yoksa (örneğin, bir barındırma Web sitesine dağıtıyorsanız), Web sitenizin aşağıdakileri ekleyin *Web.config* dosyası:</span><span class="sxs-lookup"><span data-stu-id="3f000-279">If you do not have control over the server computer (for example, you are deploying to a hosting website), add the following to the website's *Web.config* file:</span></span>
> 
> 
> [!code-xml[Main](beta3/samples/sample7.xml)]


#### <a name="issue-using-web-application-project-or-aspnet-mvc-and-aspnet-web-pages-in-the-same-application"></a><span data-ttu-id="3f000-280">Sorun: Web uygulama projesi veya ASP.NET MVC ve ASP.NET Web sayfaları aynı uygulamasında kullanma</span><span class="sxs-lookup"><span data-stu-id="3f000-280">Issue: Using Web Application Project or ASP.NET MVC and ASP.NET Web pages in the same application</span></span>

> <span data-ttu-id="3f000-281">ASP.NET Web sayfaları, bir Web uygulaması projesi ya da ASP.NET MVC uygulaması kullanıyorsanız, bir hata görebilirsiniz, *WebPageHttpApplication* bulunamıyor.</span><span class="sxs-lookup"><span data-stu-id="3f000-281">If you were using ASP.NET Web Pages in a Web Application project or ASP.NET MVC application, you might see an error that *WebPageHttpApplication* cannot be found.</span></span>
> 
> <span data-ttu-id="3f000-282">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-282">**Workaround**</span></span>  
> <span data-ttu-id="3f000-283">Bu hata alırsanız, uygulama türetilen temel sınıf değiştirin.</span><span class="sxs-lookup"><span data-stu-id="3f000-283">If you get this error, change the base class from which the application derives.</span></span> <span data-ttu-id="3f000-284">İçinde *Global.asax* dosya, aşağıdaki satırı değiştirin:</span><span class="sxs-lookup"><span data-stu-id="3f000-284">In the *Global.asax* file, change the following line:</span></span>
> 
> [!code-csharp[Main](beta3/samples/sample8.cs)]
> 
> <span data-ttu-id="3f000-285">Bunun için:</span><span class="sxs-lookup"><span data-stu-id="3f000-285">To this:</span></span>
> 
> [!code-csharp[Main](beta3/samples/sample9.cs)]
> 
> <span data-ttu-id="3f000-286">Bu uygulamada tanıtılan bir değişiklik tersine çevirir Razor sözdizimi ile ASP.NET Web sayfaları, Beta 1 sürümü.</span><span class="sxs-lookup"><span data-stu-id="3f000-286">This in effect reverses a change that was introduced for the Beta 1 release of ASP.NET Web Pages with Razor syntax.</span></span>


#### <a name="issue-deploying-an-application-to-a-computer-that-does-not-have-sql-server-compact-installed"></a><span data-ttu-id="3f000-287">Sorun: SQL Server yüklü Compact sahip olmayan bir bilgisayara uygulama dağıtma</span><span class="sxs-lookup"><span data-stu-id="3f000-287">Issue: Deploying an application to a computer that does not have SQL Server Compact installed</span></span>

> <span data-ttu-id="3f000-288">SQL Server Compact veritabanları içeren uygulamaları, SQL Server Compact değil yüklü olduğu bir bilgisayarda çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f000-288">Applications that include SQL Server Compact databases can run on a computer where SQL Server Compact is not installed.</span></span> <span data-ttu-id="3f000-289">Microsoft WebMatrix Beta 3 otomatik olarak sizin için bu ikili dosyaları kopyalar ve uygun gerçekleştirir *Web.config* dosya dönüşümler.</span><span class="sxs-lookup"><span data-stu-id="3f000-289">Microsoft WebMatrix Beta 3 automatically copies these binaries for you and performs the appropriate *Web.config* file transforms.</span></span>
> 
> <span data-ttu-id="3f000-290">**Geçici çözüm** bu dosyaları kopyalayın ve yapmak gereksinim duyarsanız *Web.config* dosya değişiklikleri el ile aşağıdakileri yapın:</span><span class="sxs-lookup"><span data-stu-id="3f000-290">**Workaround** If you need to copy these files and make the *Web.config* file changes manually, do the following :</span></span>
> 
> 1. <span data-ttu-id="3f000-291">Veritabanı altyapısı derlemeler için kopyalama *Bin* uygulamanın hedef bilgisayardaki klasör (ve alt klasörler):</span><span class="sxs-lookup"><span data-stu-id="3f000-291">Copy the database engine assemblies to the *Bin* folder (and subfolders) of the application on the target computer:</span></span> 
> 
>     - <span data-ttu-id="3f000-292">Kopya *C:\Program Files\Microsoft SQL Server Compact Edition\v4.0\Desktop\System.Data.SqlServerCe.dll* **için** *\Bin*</span><span class="sxs-lookup"><span data-stu-id="3f000-292">Copy *C:\Program Files\Microsoft SQL Server Compact Edition\v4.0\Desktop\System.Data.SqlServerCe.dll* **to** *\Bin*</span></span>
>     - <span data-ttu-id="3f000-293">Kopya *C:\Program Files\Microsoft SQL Server Compact Edition\v4.0\Private\x86\\** **için** *\Bin\x86*</span><span class="sxs-lookup"><span data-stu-id="3f000-293">Copy *C:\Program Files\Microsoft SQL Server Compact Edition\v4.0\Private\x86\\** **to** *\Bin\x86*</span></span>
>     - <span data-ttu-id="3f000-294">Kopya *C:\Program Files\Microsoft SQL Server Compact Edition\v4.0\Private\amd64\\** **için** *\Bin\amd64*</span><span class="sxs-lookup"><span data-stu-id="3f000-294">Copy *C:\Program Files\Microsoft SQL Server Compact Edition\v4.0\Private\amd64\\** **to** *\Bin\amd64*</span></span>
> 2. <span data-ttu-id="3f000-295">Web sitesinin kök klasöründe oluşturun veya açın bir *Web.config* dosya.</span><span class="sxs-lookup"><span data-stu-id="3f000-295">In the root folder of the website, create or open a *Web.config* file.</span></span> <span data-ttu-id="3f000-296">(WebMatrix Beta 3'te, bu dosya türü tıklatırsanız kullanılabilir **tüm** içinde **bir dosya türünü seçin** iletişim kutusu.)</span><span class="sxs-lookup"><span data-stu-id="3f000-296">(In WebMatrix Beta 3, this file type is available if you click **All** in the **Choose a File Type** dialog box.)</span></span>
> 3. <span data-ttu-id="3f000-297">Bir alt öğesi olarak aşağıdaki öğeyi ekleyin  **&lt;yapılandırma&gt;**  öğesi (içinde değil  **&lt;system.web&gt;**  öğesi):</span><span class="sxs-lookup"><span data-stu-id="3f000-297">Add the following element as a child of the **&lt;configuration&gt;** element (not inside the **&lt;system.web&gt;** element):</span></span>
> 
> 
> [!code-xml[Main](beta3/samples/sample10.xml)]


#### <a name="issue-database-and-webgrid-helpers-do-not-work-in-medium-trust-in-visual-basic"></a><span data-ttu-id="3f000-298">Sorun: Orta güveni Visual Basic'te veritabanı ve WebGrid Yardımcıları çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="3f000-298">Issue: Database and WebGrid helpers do not work in Medium Trust in Visual Basic</span></span>

> <span data-ttu-id="3f000-299">Visual Basic kullanıyorsanız (oluşturma *.vbhtml* dosyaları), `Database` ve `WebGrid` Yardımcıları uygulama Medium Trust kullanmak üzere ayarlanmışsa çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="3f000-299">If you are using Visual Basic (creating *.vbhtml* files), the `Database` and `WebGrid` helpers will not work if the application is set to use Medium Trust.</span></span>
> 
> <span data-ttu-id="3f000-300">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-300">**Workaround**</span></span>  
> <span data-ttu-id="3f000-301">Tam güven kullanmak için uygulamayı geçici olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="3f000-301">Temporarily set the application to use Full Trust.</span></span>

<a id="Known_Issues_SQL_Server_Compact"></a>
### <a name="sql-server-compact"></a><span data-ttu-id="3f000-302">SQL Server Compact</span><span class="sxs-lookup"><span data-stu-id="3f000-302">SQL Server Compact</span></span>

#### <a name="issue-encrypt-property-is-not-recognized"></a><span data-ttu-id="3f000-303">Sorun: "Şifrele" özelliği tanınmıyor</span><span class="sxs-lookup"><span data-stu-id="3f000-303">Issue: "Encrypt" property is not recognized</span></span>

> <span data-ttu-id="3f000-304">SQL Server Compact 4.0 tanımıyor `Encrypt` özelliği `SqlCeConnection` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="3f000-304">SQL Server Compact 4.0 does not recognize the `Encrypt` property of the `SqlCeConnection` class.</span></span> <span data-ttu-id="3f000-305">Bu özellik, veritabanı dosyaları şifrelemek için kullanmamalısınız.</span><span class="sxs-lookup"><span data-stu-id="3f000-305">You should not use this property to encrypt database files.</span></span> <span data-ttu-id="3f000-306">`Encrypt` Özelliği SQL Server Compact 3.5 sürümünde kullanımdan kaldırılmıştır ve yalnızca geriye dönük uyumluluk için korunur.</span><span class="sxs-lookup"><span data-stu-id="3f000-306">The `Encrypt` property was deprecated in SQL Server Compact 3.5 release and was retained only for backward compatibility.</span></span> 
> 
> <span data-ttu-id="3f000-307">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-307">**Workaround**</span></span>  
> <span data-ttu-id="3f000-308">Kullanım `Encryption Mode` özelliği `SqlCeConnection` SQL Server Compact 4.0 veritabanı dosyaları şifrelemek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="3f000-308">Use the `Encryption Mode` property of the `SqlCeConnection` class to encrypt SQL Server Compact 4.0 database files.</span></span> <span data-ttu-id="3f000-309">Aşağıdaki örnek şifrelenmiş bir SQL Server Compact 4.0 veritabanı kullanarak oluşturulacağını gösterir `Encryption Mode` özelliği:</span><span class="sxs-lookup"><span data-stu-id="3f000-309">The following example shows how to create an encrypted SQL Server Compact 4.0 database using the `Encryption Mode` property:</span></span>
>  
> [!code-csharp[Main](beta3/samples/sample11.cs)]
>  
> [!code-vb[Main](beta3/samples/sample12.vb)]
> 
> <span data-ttu-id="3f000-310">Var olan bir SQL Server Compact 4.0 veritabanı şifreleme modunu değiştirmek için aşağıdakileri yapın:</span><span class="sxs-lookup"><span data-stu-id="3f000-310">To change the encryption mode of an existing SQL Server Compact 4.0 database, do the following:</span></span>
>  
> [!code-csharp[Main](beta3/samples/sample13.cs)]
>  
> [!code-vb[Main](beta3/samples/sample14.vb)]
> 
> <span data-ttu-id="3f000-311">Şifrelenmemiş bir SQL Server Compact 4.0 veritabanı şifrelemek için aşağıdakileri yapın:</span><span class="sxs-lookup"><span data-stu-id="3f000-311">To encrypt an unencrypted SQL Server Compact 4.0 database, do the following:</span></span>
>  
> [!code-csharp[Main](beta3/samples/sample15.cs)]
>  
> [!code-vb[Main](beta3/samples/sample16.vb)]


#### <a name="issue-microsoft-visual-c-2008-runtime-libraries-are-required"></a><span data-ttu-id="3f000-312">Sorun: Microsoft Visual C++ 2008 çalışma zamanı kitaplıkları gereklidir</span><span class="sxs-lookup"><span data-stu-id="3f000-312">Issue: Microsoft Visual C++ 2008 runtime libraries are required</span></span>

> <span data-ttu-id="3f000-313">Yerel DLL'leri, SQL Server Compact 4.0 Microsoft Visual C++ 2008 çalışma zamanı kitaplıkları (x 86, IA64 ve x 64), Service Pack 1 gerekir.</span><span class="sxs-lookup"><span data-stu-id="3f000-313">The native DLLs of SQL Server Compact 4.0 need the Microsoft Visual C++ 2008 Runtime Libraries (x86, IA64, and x64), Service Pack 1.</span></span>
> 
> <span data-ttu-id="3f000-314">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-314">**Workaround**</span></span>  
> <span data-ttu-id="3f000-315">.NET Framework 3.5 SP1'i yükleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-315">Install the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="3f000-316">Bu, Visual C++ 2008 çalışma zamanı kitaplıkları SP1'i de yükler.</span><span class="sxs-lookup"><span data-stu-id="3f000-316">This also installs the Visual C++ 2008 Runtime Libraries SP1.</span></span> <span data-ttu-id="3f000-317">Kitaplıkları aşağıdaki konumdan yükleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="3f000-317">You can download the libraries from the following location:</span></span>   
>   
> [<span data-ttu-id="3f000-318">Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package ATL güvenlik güncelleştirmesi</span><span class="sxs-lookup"><span data-stu-id="3f000-318">Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update</span></span>](https://go.microsoft.com/fwlink/?LinkId=194827)
> 
> [!NOTE]
> <span data-ttu-id="3f000-319">Bu .NET Framework 2.0, 3.0, yüklemeden dikkat edin veya 4 mu *değil* Visual C++ 2008 çalışma zamanı kitaplıkları SP1'i yükleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-319">Note that installing the .NET Framework 2.0, 3.0, or 4 does *not* install the Visual C++ 2008 Runtime Libraries SP1.</span></span>


#### <a name="issue-if-sql-server-compact-is-installed-prior-to-installing-net-framework-on-the-computer-its-provider-invariant-name-is-not-registered-in-the-net-framework-machineconfig-file"></a><span data-ttu-id="3f000-320">Sorun: SQL Server Compact bilgisayarda .NET Framework yüklenmeden önce yüklü ise, sağlayıcı sabit adı .NET Framework machine.config dosyasında kayıtlı değil</span><span class="sxs-lookup"><span data-stu-id="3f000-320">Issue: If SQL Server Compact is installed prior to installing .NET Framework on the computer, its provider invariant name is not registered in the .NET Framework machine.config file</span></span>

> <span data-ttu-id="3f000-321">SQL Server Compact SQL Server Compact .NET framework gerektirdiği için .NET Framework yüklü olmayan bir makineye yüklenebilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-321">SQL Server Compact can be installed on a machine that does not have .NET Framework installed because SQL Server Compact does require the .NET framework.</span></span> <span data-ttu-id="3f000-322">SQL Server Compact kurulumu, SQL Server Compact yüklemeden önce ne .NET Framework sürüm 3.5 ne de 4 yüklü değilse, sağlayıcı sabit adı kaydetmez *machine.config* dosya.</span><span class="sxs-lookup"><span data-stu-id="3f000-322">If neither .NET Framework version 3.5 nor 4 is installed before you install SQL Server Compact, the SQL Server Compact Setup does not register its provider invariant name in the *machine.config* file.</span></span> <span data-ttu-id="3f000-323">SQL Server Compact girdisinde güvenen herhangi bir uygulama *machine.config* dosyası başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="3f000-323">Any application that relies on the SQL Server Compact entry in the *machine.config* file will fail.</span></span> <span data-ttu-id="3f000-324">Değişmez adı kayıt girişi *machine.config* aşağıdaki örnek gibi görünüyor:</span><span class="sxs-lookup"><span data-stu-id="3f000-324">The invariant name registration entry in *machine.config* looks like the following example:</span></span>
> 
> [!code-xml[Main](beta3/samples/sample17.xml)]
> 
> <span data-ttu-id="3f000-325">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-325">**Workaround**</span></span>  
> <span data-ttu-id="3f000-326">SQL Server Compact 4.0 CTP1 kaldırın.</span><span class="sxs-lookup"><span data-stu-id="3f000-326">Uninstall SQL Server Compact 4.0 CTP1.</span></span> <span data-ttu-id="3f000-327">İndirin ve .NET Framework'ün tam sürümü için şu konumdan yükleyin:</span><span class="sxs-lookup"><span data-stu-id="3f000-327">Download and install the full versions of the .NET Framework from the following location:</span></span>
> 
> [<span data-ttu-id="3f000-328">Microsoft .NET Framework 3.5 Service pack 1 (tam paketi)</span><span class="sxs-lookup"><span data-stu-id="3f000-328">Microsoft .NET Framework 3.5 Service pack 1 (Full Package)</span></span>](https://go.microsoft.com/fwlink/?LinkId=194828)  
> [<span data-ttu-id="3f000-329">Microsoft .NET Framework 4.0 sürümü (tam paketi)</span><span class="sxs-lookup"><span data-stu-id="3f000-329">Microsoft .NET Framework 4.0 Release (Full Package)</span></span>](https://www.microsoft.com/downloads/details.aspx?FamilyID=9cfb2d51-5ff4-4491-b0e5-b386f32c0992&amp;displaylang=en)
> 
> <span data-ttu-id="3f000-330">Yeniden [SQL Server Compact 4.0 CTP1](https://www.microsoft.com/downloads/details.aspx?FamilyID=0d2357ea-324f-46fd-88fc-7364c80e4fdb&amp;displaylang=en).</span><span class="sxs-lookup"><span data-stu-id="3f000-330">Then reinstall [SQL Server Compact 4.0 CTP1](https://www.microsoft.com/downloads/details.aspx?FamilyID=0d2357ea-324f-46fd-88fc-7364c80e4fdb&amp;displaylang=en).</span></span>


<a id="Known_Issues_Installing_Applications"></a>

### <a name="installing-applications"></a><span data-ttu-id="3f000-331">Uygulamaları yükleme</span><span class="sxs-lookup"><span data-stu-id="3f000-331">Installing Applications</span></span>

#### <a name="issue-installing-an-application-can-take-a-long-time-if-the-users-my-documents-folder-is-redirected-to-a-network-share"></a><span data-ttu-id="3f000-332">Sorun: kullanıcının Belgeler klasörünü bir ağ paylaşımına yönlendirilir, bir uygulamanın yüklenmesi bir uzun zaman alabilir</span><span class="sxs-lookup"><span data-stu-id="3f000-332">Issue: Installing an application can take a long time if the user's My Documents folder is redirected to a network share</span></span>

> <span data-ttu-id="3f000-333">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-333">**Workaround**</span></span>  
> <span data-ttu-id="3f000-334">Yok.</span><span class="sxs-lookup"><span data-stu-id="3f000-334">None.</span></span> <span data-ttu-id="3f000-335">Uygulama yüklemek için biraz zaman alabilir ancak düzgün yüklenecektir.</span><span class="sxs-lookup"><span data-stu-id="3f000-335">The application might take a while to install, but will install correctly.</span></span>


<a id="Known_Issues_Publishing_Applications"></a>

### <a name="publishing-applications"></a><span data-ttu-id="3f000-336">Uygulama yayımlama</span><span class="sxs-lookup"><span data-stu-id="3f000-336">Publishing Applications</span></span>

#### <a name="issue-site-might-not-work-after-publishing-if-the-destination-url-field-is-not-prefixed-with-http-or-https"></a><span data-ttu-id="3f000-337">Sorun: "Hedef URL" alanını http:// veya https:// ile eklenmedi, yayımladıktan sonra Site çalışmayabilir</span><span class="sxs-lookup"><span data-stu-id="3f000-337">Issue: Site might not work after publishing if the "Destination URL" field is not prefixed with http:// or https://</span></span>

> <span data-ttu-id="3f000-338">İçinde **yayımlama ayarlarını** iletişim kutusunda, hedef URL ile başlamıyorsa `http://` veya `https://`, site dağıtımdan sonra çalışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-338">In the **Publishing Settings** dialog box, if the destination URL does not begin with `http://` or `https://`, the site might not work after deployment.</span></span>
> 
> <span data-ttu-id="3f000-339">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-339">**Workaround**</span></span>  
> <span data-ttu-id="3f000-340">Bir site, hedef URL yayımlamadan önce olduğundan emin olun **yayımlama ayarları** iletişim kutusu ile başlayan `http://` veya `https://`.</span><span class="sxs-lookup"><span data-stu-id="3f000-340">Make sure that before you publish a site, the destination URL in the **Publish Settings** dialog box starts with `http://` or `https://`.</span></span>


#### <a name="issue-publishing-a-mysql-database-fails-with-the-error-failed-to-publish-the-database-this-can-happen-if-the-remote-database-cannot-run-the-script"></a><span data-ttu-id="3f000-341">Sorun: bir MySQL veritabanı yayımlama hatasıyla "veritabanı yayımlanamadı. başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="3f000-341">Issue: Publishing a MySQL database fails with the error "Failed to publish the database.</span></span> <span data-ttu-id="3f000-342">Uzak veritabanı komut dosyası çalıştırılamadığında oluşabilir."</span><span class="sxs-lookup"><span data-stu-id="3f000-342">This can happen if the remote database cannot run the script."</span></span>

> <span data-ttu-id="3f000-343">Hata, birçok nedenden dolayı ortaya çıkabilir.</span><span class="sxs-lookup"><span data-stu-id="3f000-343">The error can occur for a number of reasons.</span></span> <span data-ttu-id="3f000-344">Bu hatayı görebilirsiniz bir veritabanı betiği tek tırnak karakteri (') içerir ve hedef MySQL veritabanının varsayılan karakter kümesini UTF-8'e değil nedenidir.</span><span class="sxs-lookup"><span data-stu-id="3f000-344">One reason you can see this error is if the database script contains a single quotation character (') and the destination MySQL database's default character set is not to UTF-8.</span></span>
> 
> <span data-ttu-id="3f000-345">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-345">**Workaround**</span></span>  
> <span data-ttu-id="3f000-346">Uzak MySQL veritabanı için UTF-8'e ayarlanmış varsayılan karakter kümesi.</span><span class="sxs-lookup"><span data-stu-id="3f000-346">Set the default character set for the remote MySQL database to UTF-8.</span></span>


<a id="Known_Issues_Other_Issues"></a>

### <a name="other-issues"></a><span data-ttu-id="3f000-347">Diğer Sorunlar</span><span class="sxs-lookup"><span data-stu-id="3f000-347">Other Issues</span></span>

#### <a name="issue-searchfilter-does-not-work-in-reports-for-group-by-issue-type"></a><span data-ttu-id="3f000-348">Sorun: Arama/filtresi raporlarda için Group By seçeneği çalışmıyor: sorun türü</span><span class="sxs-lookup"><span data-stu-id="3f000-348">Issue: Search/Filter does not work in Reports for Group By: Issue Type</span></span>

> <span data-ttu-id="3f000-349">Bir rapor çalıştırdığınızda bir site için metin girerseniz, *URL'ye göre filtre* kutusuna ve tıklatın *arama*, hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="3f000-349">When you run a report for a site, if you enter text in the *Filter by URL* box and click *Search*, nothing happens.</span></span> <span data-ttu-id="3f000-350">Bu denetim sırasında işlevsel değil. Bunun nedeni *Group By* raporun durumu ayarlanmış *sorun türü*, varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="3f000-350">This is because this control is not functional while the *Group By* state of the report is set to *Issue Type*, which is the default.</span></span>
> 
> <span data-ttu-id="3f000-351">**Geçici çözüm** içinde *Group By* sekmesini Şeritinde tıklatın *URL* girdileri kendi kaynak URL göre gruplandırmak için.</span><span class="sxs-lookup"><span data-stu-id="3f000-351">**Workaround** In the *Group By* tab of ribbon, click *URL* to group the entries by their source URL.</span></span> <span data-ttu-id="3f000-352">Bu durumda, girişlere filtre düğmesi ve metin kutusu işlevseldir.</span><span class="sxs-lookup"><span data-stu-id="3f000-352">The text box and button to filter the entries are functional while in this state.</span></span>


#### <a name="issue-wcf-applications-fail-to-run-with-iis-express"></a><span data-ttu-id="3f000-353">Sorun: IIS Express ile çalıştırmak WCF uygulamaları başarısız</span><span class="sxs-lookup"><span data-stu-id="3f000-353">Issue: WCF applications fail to run with IIS Express</span></span>

> <span data-ttu-id="3f000-354">WCF bir uygulama için gözatma aşağıdakine benzer bir hata sonuçlanır:</span><span class="sxs-lookup"><span data-stu-id="3f000-354">Browsing to a WCF application results in an error like the following one:</span></span>
> 
> <span data-ttu-id="3f000-355">*Dosya veya derleme yüklenemedi ' Microsoft.Web.Administration, sürüm 7.0.0.0'dan, Culture = neutral, PublicKeyToken = 31bf3856ad364e35 ' ya da bağımlılıklarından biri. Sistem belirtilen dosyayı bulamıyor.*</span><span class="sxs-lookup"><span data-stu-id="3f000-355">*Could not load file or assembly 'Microsoft.Web.Administration, Version=7.0.0.0, Culture=neutral,PublicKeyToken=31bf3856ad364e35' or one of its dependencies. The system cannot find the file specified.*</span></span>
> 
> <span data-ttu-id="3f000-356">Bu durum, IIS Express Beta sürümü varsayılan olarak WCF desteklemiyor kaynaklanır.</span><span class="sxs-lookup"><span data-stu-id="3f000-356">This occurs because IIS Express Beta release doesn't support WCF by default.</span></span>
> 
> <span data-ttu-id="3f000-357">**Geçici çözüm** aşağıdaki geçici çözümlerden birini kullanın (geçici çözüm #2 gerektiren Microsoft Windows Vista veya daha üstü):</span><span class="sxs-lookup"><span data-stu-id="3f000-357">**Workaround** Use any one of the following workarounds (workaround #2 requires Microsoft Windows Vista or higher):</span></span>
> 
> 
> 1. <span data-ttu-id="3f000-358">Kopya *Microsoft.Web.dll* ve *Microsoft.Web.Administration.dll* WebMatrix yükleme konumuna derlemelerden *bin* WCF dizin uygulama.</span><span class="sxs-lookup"><span data-stu-id="3f000-358">Copy the *Microsoft.Web.dll* and *Microsoft.Web.Administration.dll* assemblies from the WebMatrix installation location to the *bin* directory of the WCF application.</span></span> <span data-ttu-id="3f000-359">Varsayılan olarak, WebMatrix yüklü *Microsoft WebMatrix* sistemin altında alt *Program Files* klasör.</span><span class="sxs-lookup"><span data-stu-id="3f000-359">By default, WebMatrix is installed in the *Microsoft WebMatrix* subfolder under the system's *Program Files* folder.</span></span>
> 2. <span data-ttu-id="3f000-360">Microsoft Windows Vista veya sonraki bir simgesel derlemelere oluşturmak *bin* aşağıdaki komutları kullanarak dizin.</span><span class="sxs-lookup"><span data-stu-id="3f000-360">On Microsoft Windows Vista or higher, create a symlink to the assemblies in the *bin* directory using the following commands.</span></span> <span data-ttu-id="3f000-361">(Bu yaklaşım derlemeler kopyasını oluşturmaz avantajı vardır.)</span><span class="sxs-lookup"><span data-stu-id="3f000-361">(This approach has the advantage that it does not create a copy of the assemblies.)</span></span>
> 
>     [!code-console[Main](beta3/samples/sample18.cmd)]
> 3. <span data-ttu-id="3f000-362">İki derlemeyi GAC'ye yükleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-362">Install the two assemblies in the GAC.</span></span> <span data-ttu-id="3f000-363">Yükseltilmiş bir isteminden aşağıdaki komutları çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="3f000-363">From an elevated prompt, run the following commands:</span></span>
> 
>     [!code-console[Main](beta3/samples/sample19.cmd)]


#### <a name="issue-webmatrix-beta-3-is-unable-to-perform-certain-tasks-that-require-elevation"></a><span data-ttu-id="3f000-364">Sorun: Ayrıcalık gerektiren bazı görevleri gerçekleştirmek WebMatrix Beta 3 alamıyor</span><span class="sxs-lookup"><span data-stu-id="3f000-364">Issue: WebMatrix Beta 3 is unable to perform certain tasks that require elevation</span></span>

> <span data-ttu-id="3f000-365">Aşağıdaki durumlarda ek bileşeni yükleme gibi ayrıcalık gerektiren bazı görevleri gerçekleştirmek WebMatrix Beta 3 alamıyor:</span><span class="sxs-lookup"><span data-stu-id="3f000-365">WebMatrix Beta 3 is unable to perform certain tasks that require elevation, such as installing additional components in the following situations:</span></span>
> 
> - <span data-ttu-id="3f000-366">Windows Vista veya Windows 7 üzerinde yönetimsel ayrıcalıklara sahip bir hesapla oturum günlüğe kaydedilir ve kullanıcı hesabı denetimi (UAC) devre dışı bırakılır.</span><span class="sxs-lookup"><span data-stu-id="3f000-366">On Windows Vista or Windows 7, you are logged in with an account that does not have administrative privileges and User Account Control (UAC) is disabled.</span></span>
> - <span data-ttu-id="3f000-367">Microsoft Windows XP veya Microsoft Windows Server 2003 kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="3f000-367">You are using Microsoft Windows XP or Microsoft Windows Server 2003.</span></span>
> 
> <span data-ttu-id="3f000-368">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-368">**Workaround**</span></span>  
> <span data-ttu-id="3f000-369">WebMatrix Beta 3'te görevlerin çoğu yönetici izni gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="3f000-369">Most tasks in WebMatrix Beta 3 do not require administrative permission.</span></span> <span data-ttu-id="3f000-370">Olmayanlar için yönetici olarak işlemi gerçekleştirebilir, veya şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="3f000-370">For those that do, you can perform the operation as an administrator, or follow these steps:</span></span>
> 
> - <span data-ttu-id="3f000-371">Windows Vista veya Windows 7, UAC etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="3f000-371">On Windows Vista or Windows 7, enable UAC.</span></span>
> - <span data-ttu-id="3f000-372">Windows XP'de, kullanıcı yöneticileri güvenlik grubuna ekleyin.</span><span class="sxs-lookup"><span data-stu-id="3f000-372">On Windows XP, add the user to the Administrators security group.</span></span>


#### <a name="issue-site-from-web-gallery-is-disabled"></a><span data-ttu-id="3f000-373">Sorun: "Web Galeri'den Site" devre dışı bırakıldı</span><span class="sxs-lookup"><span data-stu-id="3f000-373">Issue: "Site from Web Gallery" is disabled</span></span>

> <span data-ttu-id="3f000-374">**Web Galerisi sitesinden** Web Platformu yükleyicisi 3.0 yüklü değilse seçeneği devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="3f000-374">The **Site from Web Gallery** option is disabled if the Web Platform Installer 3.0 is not installed.</span></span>
> 
> <span data-ttu-id="3f000-375">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-375">**Workaround**</span></span>  
> <span data-ttu-id="3f000-376">Yükleme [Microsoft Web Platformu yükleyicisi 3.0](https://go.microsoft.com/fwlink/?LinkID=194638).</span><span class="sxs-lookup"><span data-stu-id="3f000-376">Install the [Microsoft Web Platform Installer 3.0](https://go.microsoft.com/fwlink/?LinkID=194638).</span></span>


#### <a name="issue-on-windows-server-2003-iis-express-does-not-start-for-a-non-administrative-user"></a><span data-ttu-id="3f000-377">Sorun: Windows Server 2003'te, IIS Express için yönetici olmayan bir kullanıcı başlamıyor</span><span class="sxs-lookup"><span data-stu-id="3f000-377">Issue: On Windows Server 2003, IIS Express does not start for a non-administrative user</span></span>

> <span data-ttu-id="3f000-378">Bir sayfa başlatın veya IIS Express, başlattığınızda Windows Server 2003'te, IIS Express başlatılmaz.</span><span class="sxs-lookup"><span data-stu-id="3f000-378">On Windows Server 2003, when you launch a page or start IIS Express, IIS Express does not start.</span></span> <span data-ttu-id="3f000-379">Web sayfaları için uygulama yönetici olmayan bir kullanıcı tarafından başlatılmış olduğunu belirten bir hata görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="3f000-379">For Web pages, an error is displayed that indicates that the application has been started by a non-administrative user.</span></span>
> 
> <span data-ttu-id="3f000-380">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-380">**Workaround**</span></span>  
> <span data-ttu-id="3f000-381">WebMatrix Beta 3 bir yönetici kullanıcı olarak başlatın.</span><span class="sxs-lookup"><span data-stu-id="3f000-381">Start WebMatrix Beta 3 as an administrative user.</span></span> <span data-ttu-id="3f000-382">Daha fazla ayrıntı için aşağıdaki Bilgi Bankası makalesine bakın:</span><span class="sxs-lookup"><span data-stu-id="3f000-382">For more details, see the following KnowledgeBase article:</span></span>  
>   
> [<span data-ttu-id="3f000-383">Yönetici olmayan bir kullanıcı tarafından başlatılan bir uygulama üzerinde uygulama Windows Vista, Windows Server 2003 veya Windows XP çalıştıran bilgisayarın HTTP trafiği için dinleyemiyor.</span><span class="sxs-lookup"><span data-stu-id="3f000-383">An application that is started by a non-administrative user cannot listen to the HTTP traffic of the computer on which the application is running in Windows Vista, Windows Server 2003, or Windows XP.</span></span>](https://support.microsoft.com/kb/939786)


#### <a name="issue-google-chrome-is-not-available-as-a-run-option"></a><span data-ttu-id="3f000-384">Sorun: Google Chrome Çalıştır seçeneği olarak kullanılabilir değil</span><span class="sxs-lookup"><span data-stu-id="3f000-384">Issue: Google Chrome is not available as a Run option</span></span>

> <span data-ttu-id="3f000-385">Google Chrome tarayıcılar altında listesinde görüntülenmez **çalıştırmak** üzerinde **giriş** sekmesi.</span><span class="sxs-lookup"><span data-stu-id="3f000-385">Google Chrome is not displayed in the list of browsers under **Run** on the **Home** tab.</span></span>
> 
> <span data-ttu-id="3f000-386">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-386">**Workaround**</span></span>  
> <span data-ttu-id="3f000-387">Google Chrome bazı sürümleri kendilerini doğru Windows varsayılan programlar özelliğiyle kaydetmez.</span><span class="sxs-lookup"><span data-stu-id="3f000-387">Some versions of Google Chrome do not register themselves correctly with the Default Programs feature in Windows.</span></span> <span data-ttu-id="3f000-388">Google Chrome geçici bir çözüm olarak başlatmak için tıklatın *özelleştirme ve denetim Google Chrome* menüsünde tıklatın *seçenekleri*ve ardından *yapma Google Chrome my varsayılan tarayıcı*.</span><span class="sxs-lookup"><span data-stu-id="3f000-388">As a workaround, start Google Chrome, click the *Customize and control Google Chrome* menu, click *Options*, and then click *Make Google Chrome my default browser*.</span></span>


#### <a name="issue-the-foreign-key-dialog-box-doesnt-allow-entering-a-primary-key"></a><span data-ttu-id="3f000-389">Sorun: "Yabancı anahtarı" birincil anahtarı girme izin ver iletişim kutusu değil</span><span class="sxs-lookup"><span data-stu-id="3f000-389">Issue: The "Foreign Key" dialog box doesn't allow entering a primary key</span></span>

> <span data-ttu-id="3f000-390">**Yabancı anahtar** iletişim kutusu izin vermez birincil anahtar tablosunda birincil anahtar adı girin.</span><span class="sxs-lookup"><span data-stu-id="3f000-390">The **Foreign Key** dialog box does not allow you to enter the primary key name from the primary key table.</span></span>
> 
> <span data-ttu-id="3f000-391">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-391">**Workaround**</span></span>  
> <span data-ttu-id="3f000-392">Bu bilinen bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="3f000-392">This is intentional.</span></span> <span data-ttu-id="3f000-393">Birincil anahtar tablosundan birincil anahtarın adını girmeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="3f000-393">You do not need to enter the name of the primary key from the primary key table.</span></span>


#### <a name="issue-the-relationships-button-is-disabled"></a><span data-ttu-id="3f000-394">Sorun: "İlişkiler" düğmesini devre dışı bırakıldı</span><span class="sxs-lookup"><span data-stu-id="3f000-394">Issue: The "Relationships" button is disabled</span></span>

> <span data-ttu-id="3f000-395">**İlişkileri** altında düğmesini **tablo** sekmesinde **veritabanları** çalışma SQL Server Compact veritabanları için devre dışı.</span><span class="sxs-lookup"><span data-stu-id="3f000-395">The **Relationships** button under the **Table** tab in the **Databases** workspace is disabled for SQL Server Compact databases.</span></span>
> 
> <span data-ttu-id="3f000-396">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-396">**Workaround**</span></span>  
> <span data-ttu-id="3f000-397">Yok.</span><span class="sxs-lookup"><span data-stu-id="3f000-397">None.</span></span> <span data-ttu-id="3f000-398">SQL Server Compact tablolar arasında ilişkiler desteklemez.</span><span class="sxs-lookup"><span data-stu-id="3f000-398">SQL Server Compact does not support relationships between tables.</span></span>


#### <a name="issue-parameterized-sql-queries-throw-exceptions"></a><span data-ttu-id="3f000-399">Sorun: Parametreleştirilmiş SQL sorguları özel durumlar oluşturma</span><span class="sxs-lookup"><span data-stu-id="3f000-399">Issue: Parameterized SQL queries throw exceptions</span></span>

> <span data-ttu-id="3f000-400">SQL Server Compact bir veri türü gibi belirtmezseniz 4.0, `SqlDbType` veya `DbType` sorgu çalıştırıldığında parametreli sorgular parametreleri için bir özel durum oluşur.</span><span class="sxs-lookup"><span data-stu-id="3f000-400">In SQL Server Compact 4.0, if you do not specify a data type such as `SqlDbType` or `DbType` for parameters in parameterized queries, an exception is thrown when the query runs.</span></span>
> 
> <span data-ttu-id="3f000-401">**Geçici çözüm**</span><span class="sxs-lookup"><span data-stu-id="3f000-401">**Workaround**</span></span>  
> <span data-ttu-id="3f000-402">Parametre veri türü gibi açık olarak ayarlanıp `SqlDbType` veya `DbType`.</span><span class="sxs-lookup"><span data-stu-id="3f000-402">Explicitly set the data type for parameters such as `SqlDbType` or `DbType`.</span></span> <span data-ttu-id="3f000-403">Bu BLOB veri türleri söz konusu olduğunda önemlidir (`image` ve `ntext`).</span><span class="sxs-lookup"><span data-stu-id="3f000-403">This is critical in the case of BLOB data types (`image` and `ntext`).</span></span> <span data-ttu-id="3f000-404">Aşağıdaki gibi bir kod kullanın:</span><span class="sxs-lookup"><span data-stu-id="3f000-404">Use code like the following:</span></span>
> 
> [!code-sql[Main](beta3/samples/sample20.sql)]
>  
> [!code-vb[Main](beta3/samples/sample21.vb)]


<a id="More_Info"></a>

## <a name="for-more-information"></a><span data-ttu-id="3f000-405">Daha Fazla Bilgi İçin</span><span class="sxs-lookup"><span data-stu-id="3f000-405">For More Information</span></span>

<span data-ttu-id="3f000-406">WebMatrix Beta 3 hakkında daha fazla bilgi için aşağıdaki Web sitelerine bakın:</span><span class="sxs-lookup"><span data-stu-id="3f000-406">For more information about WebMatrix Beta 3, see the following websites:</span></span>

- [<span data-ttu-id="3f000-407">IIS.NET</span><span class="sxs-lookup"><span data-stu-id="3f000-407">IIS.net</span></span>](http://iis.net/)
- [<span data-ttu-id="3f000-408">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3f000-408">ASP.NET</span></span>](https://asp.net/webmatrix)
- [<span data-ttu-id="3f000-409">Microsoft.com/Web</span><span class="sxs-lookup"><span data-stu-id="3f000-409">Microsoft.com/web</span></span>](https://www.microsoft.com/web)

* * *

<span data-ttu-id="3f000-410">© 2010 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="3f000-410">© 2010 Microsoft Corporation.</span></span> <span data-ttu-id="3f000-411">Tüm hakları saklıdır.</span><span class="sxs-lookup"><span data-stu-id="3f000-411">All Rights Reserved.</span></span> <span data-ttu-id="3f000-412">[Kullanım koşulları](https://msdn.microsoft.com/en-us/cc300389.aspx).</span><span class="sxs-lookup"><span data-stu-id="3f000-412">[Terms of Use](https://msdn.microsoft.com/en-us/cc300389.aspx).</span></span>