---
title: "ASP.NET Core üzerinde kimliğini giriş"
author: rick-anderson
description: "Bir ASP.NET Core uygulamayla kimliğini kullan"
keywords: "ASP.NET Core, kimlik, yetkilendirme, güvenlik"
ms.author: riande
manager: wpickett
ms.date: 01/02/2018
ms.topic: article
ms.assetid: cf119f21-1a2b-49a2-b052-547ccb66ee83
ms.technology: aspnet
ms.prod: asp.net-core
uid: security/authentication/identity
ms.openlocfilehash: fc8e076af92bd8f9a95e73abb66ce32cae8ab9cf
ms.sourcegitcommit: 2d23ea501e0213bbacf65298acf1c8bd17209540
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="introduction-to-identity-on-aspnet-core"></a><span data-ttu-id="94e35-104">ASP.NET Core üzerinde kimliğini giriş</span><span class="sxs-lookup"><span data-stu-id="94e35-104">Introduction to Identity on ASP.NET Core</span></span>

<span data-ttu-id="94e35-105">Tarafından [Pranav Rastogi](https://github.com/rustd), [Rick Anderson](https://twitter.com/RickAndMSFT), [zel Dykstra](https://github.com/tdykstra), Jon Galloway [Erik Reitan](https://github.com/Erikre), ve [Steve Smith](https://ardalis.com/)</span><span class="sxs-lookup"><span data-stu-id="94e35-105">By [Pranav Rastogi](https://github.com/rustd), [Rick Anderson](https://twitter.com/RickAndMSFT), [Tom Dykstra](https://github.com/tdykstra), Jon Galloway, [Erik Reitan](https://github.com/Erikre), and [Steve Smith](https://ardalis.com/)</span></span>

<span data-ttu-id="94e35-106">ASP.NET Core, uygulamanıza oturum açma işlevsellik eklemesine olanak tanıyan bir üyelik sistemi kimliğidir.</span><span class="sxs-lookup"><span data-stu-id="94e35-106">ASP.NET Core Identity is a membership system which allows you to add login functionality to your application.</span></span> <span data-ttu-id="94e35-107">Kullanıcılar bir kullanıcı adıyla bir hesap ve oturum açma oluşturabilir ve parola veya bir dış oturum açma sağlayıcısı Facebook, Google, Microsoft Account, Twitter veya diğerleri gibi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="94e35-107">Users can create an account and login with a user name and password or they can use an external login provider such as Facebook, Google, Microsoft Account, Twitter or others.</span></span>

<span data-ttu-id="94e35-108">ASP.NET Core kimliği kullanıcı adları, parolalar ve profil verileri depolamak için bir SQL Server veritabanını kullanmak üzere yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="94e35-108">You can configure ASP.NET Core Identity to use a SQL Server database to store user names, passwords, and profile data.</span></span> <span data-ttu-id="94e35-109">Alternatif olarak, örneğin, bir Azure Table Storage kendi kalıcı depoya kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="94e35-109">Alternatively, you can use your own persistent store, for example, an Azure Table Storage.</span></span> <span data-ttu-id="94e35-110">Bu belge, CLI kullanarak için ve Visual Studio için yönergeler içerir.</span><span class="sxs-lookup"><span data-stu-id="94e35-110">This document contains instructions for Visual Studio and for using the CLI.</span></span>

[<span data-ttu-id="94e35-111">Görüntülemek veya örnek kodu indirin.</span><span class="sxs-lookup"><span data-stu-id="94e35-111">View or download the sample code.</span></span>](https://github.com/aspnet/Docs/tree/master/aspnetcore/security/authentication/identity/sample/src/ASPNETCore-IdentityDemoComplete/) [<span data-ttu-id="94e35-112">(Karşıdan yükleme)</span><span class="sxs-lookup"><span data-stu-id="94e35-112">(How to download)</span></span>](https://docs.microsoft.com/en-us/aspnet/core/tutorials/index#how-to-download-a-sample)

## <a name="overview-of-identity"></a><span data-ttu-id="94e35-113">Kimliği'ne genel bakış</span><span class="sxs-lookup"><span data-stu-id="94e35-113">Overview of Identity</span></span>

<span data-ttu-id="94e35-114">Bu konuda, oturum açma kaydetmeyi işlevselliği eklemek için ASP.NET Core kimliği kullanmayı öğrenin ve bir kullanıcı oturum.</span><span class="sxs-lookup"><span data-stu-id="94e35-114">In this topic, you'll learn how to use ASP.NET Core Identity to add functionality to register, log in, and log out a user.</span></span> <span data-ttu-id="94e35-115">ASP.NET Core kimliği kullanarak uygulamaları oluşturma hakkında daha ayrıntılı yönergeler için bu makalenin sonunda sonraki adımlar bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="94e35-115">For more detailed instructions about creating apps using ASP.NET Core Identity, see the Next Steps section at the end of this article.</span></span>

1.  <span data-ttu-id="94e35-116">Bir ASP.NET çekirdek Web uygulaması projesi ile bireysel kullanıcı hesapları oluşturun.</span><span class="sxs-lookup"><span data-stu-id="94e35-116">Create an ASP.NET Core Web Application project with Individual User Accounts.</span></span>

    # <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="94e35-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94e35-117">Visual Studio</span></span>](#tab/visual-studio)

    <span data-ttu-id="94e35-118">Visual Studio'da seçin **dosya** > **yeni** > **proje**.</span><span class="sxs-lookup"><span data-stu-id="94e35-118">In Visual Studio, select **File** > **New** > **Project**.</span></span> <span data-ttu-id="94e35-119">Seçin **ASP.NET çekirdek Web uygulaması** tıklatıp **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="94e35-119">Select **ASP.NET Core Web Application** and click **OK**.</span></span>

    ![Yeni Proje iletişim kutusu](identity/_static/01-new-project.png)

    <span data-ttu-id="94e35-121">Bir ASP.NET Core seçin **Web uygulaması (Model-View-Controller)** ASP.NET 2.x çekirdek ve ardından **kimlik doğrulamayı Değiştir**.</span><span class="sxs-lookup"><span data-stu-id="94e35-121">Select an ASP.NET Core **Web Application (Model-View-Controller)** for ASP.NET Core 2.x, then select **Change Authentication**.</span></span>

    ![Yeni Proje iletişim kutusu](identity/_static/02-new-project.png)

    <span data-ttu-id="94e35-123">Bir iletişim kutusu önerme görünür kimlik doğrulama seçenekleri.</span><span class="sxs-lookup"><span data-stu-id="94e35-123">A dialog appears offering authentication choices.</span></span> <span data-ttu-id="94e35-124">Seçin **tek tek kullanıcı hesaplarını** tıklatıp **Tamam** önceki iletişim kutusuna dönmek için.</span><span class="sxs-lookup"><span data-stu-id="94e35-124">Select **Individual User Accounts** and click **OK** to return to the previous dialog.</span></span>

    ![Yeni Proje iletişim kutusu](identity/_static/03-new-project-auth.png)

    <span data-ttu-id="94e35-126">Seçme **tek tek kullanıcı hesaplarını** modelleri, ViewModels, görünümler, denetleyicileri ve proje şablonu bir parçası olarak kimlik doğrulaması için gerekli diğer varlıklar oluşturmak için Visual Studio yönlendirir.</span><span class="sxs-lookup"><span data-stu-id="94e35-126">Selecting **Individual User Accounts** directs Visual Studio to create Models, ViewModels, Views, Controllers, and other assets required for authentication as part of the project template.</span></span>

    # <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="94e35-127">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="94e35-127">.NET Core CLI</span></span>](#tab/netcore-cli)

    <span data-ttu-id="94e35-128">.NET Core CLI kullanıyorsanız, yeni projesi oluşturun ``dotnet new mvc --auth Individual``.</span><span class="sxs-lookup"><span data-stu-id="94e35-128">If using the .NET Core CLI, create the new project using ``dotnet new mvc --auth Individual``.</span></span> <span data-ttu-id="94e35-129">Bu komut, Visual Studio oluşturur aynı kimlik şablonu kodu ile yeni bir proje oluşturur.</span><span class="sxs-lookup"><span data-stu-id="94e35-129">This command creates a new project with the same Identity template code Visual Studio creates.</span></span>

    <span data-ttu-id="94e35-130">Oluşturulan projeyi içeren `Microsoft.AspNetCore.Identity.EntityFrameworkCore` kimlik veri ve şema SQL Server kullanmaya devam ederse paket [Entity Framework Çekirdek](https://docs.microsoft.com/ef/).</span><span class="sxs-lookup"><span data-stu-id="94e35-130">The created project contains the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package, which persists the Identity data and schema to SQL Server using [Entity Framework Core](https://docs.microsoft.com/ef/).</span></span>

    ---

2.  <span data-ttu-id="94e35-131">Kimlik hizmetlerini yapılandırmak ve Ara yazılımında eklemek `Startup`.</span><span class="sxs-lookup"><span data-stu-id="94e35-131">Configure Identity services and add middleware in `Startup`.</span></span>

    <span data-ttu-id="94e35-132">Kimlik Hizmetleri Uygulaması'na eklenen `ConfigureServices` yönteminde `Startup` sınıfı:</span><span class="sxs-lookup"><span data-stu-id="94e35-132">The Identity services are added to the application in the `ConfigureServices` method in the `Startup` class:</span></span>

    # <a name="aspnet-core-2xtabaspnetcore2x"></a>[<span data-ttu-id="94e35-133">ASP.NET 2.x çekirdek</span><span class="sxs-lookup"><span data-stu-id="94e35-133">ASP.NET Core 2.x</span></span>](#tab/aspnetcore2x)
    
    [!code-csharp[Main](identity/sample/src/ASPNETv2-IdentityDemo/Startup.cs?name=snippet_configureservices&highlight=7-9,11-28,30-39)]
    
    <span data-ttu-id="94e35-134">Bu Hizmetleri üzerinden uygulama için kullanılabilir hale getirilir [bağımlılık ekleme](xref:fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="94e35-134">These services are made available to the application through [dependency injection](xref:fundamentals/dependency-injection).</span></span>
    
    <span data-ttu-id="94e35-135">Kimlik etkin uygulama için çağırarak `UseAuthentication` içinde `Configure` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="94e35-135">Identity is enabled for the application by calling `UseAuthentication` in the `Configure` method.</span></span> <span data-ttu-id="94e35-136">`UseAuthentication`kimlik doğrulama ekler [ara yazılım](xref:fundamentals/middleware) istek ardışık düzenine.</span><span class="sxs-lookup"><span data-stu-id="94e35-136">`UseAuthentication` adds authentication [middleware](xref:fundamentals/middleware) to the request pipeline.</span></span>
    
    [!code-csharp[Main](identity/sample/src/ASPNETv2-IdentityDemo/Startup.cs?name=snippet_configure&highlight=17)]
    
    # <a name="aspnet-core-1xtabaspnetcore1x"></a>[<span data-ttu-id="94e35-137">ASP.NET 1.x çekirdek</span><span class="sxs-lookup"><span data-stu-id="94e35-137">ASP.NET Core 1.x</span></span>](#tab/aspnetcore1x)
    
    [!code-csharp[Main](identity/sample/src/ASPNET-IdentityDemo/Startup.cs?name=snippet_configureservices&highlight=7-9,13-34)]
    
    <span data-ttu-id="94e35-138">Bu Hizmetleri üzerinden uygulama için kullanılabilir hale getirilir [bağımlılık ekleme](xref:fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="94e35-138">These services are made available to the application through [dependency injection](xref:fundamentals/dependency-injection).</span></span>
    
    <span data-ttu-id="94e35-139">Kimlik etkin uygulama için çağırarak `UseIdentity` içinde `Configure` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="94e35-139">Identity is enabled for the application by calling `UseIdentity` in the `Configure` method.</span></span> <span data-ttu-id="94e35-140">`UseIdentity`tanımlama bilgisi tabanlı kimlik doğrulaması ekler [ara yazılım](xref:fundamentals/middleware) istek ardışık düzenine.</span><span class="sxs-lookup"><span data-stu-id="94e35-140">`UseIdentity` adds cookie-based authentication [middleware](xref:fundamentals/middleware) to the request pipeline.</span></span>
        
    [!code-csharp[Main](identity/sample/src/ASPNET-IdentityDemo/Startup.cs?name=snippet_configure&highlight=21)]
    
    ---
     
    <span data-ttu-id="94e35-141">Uygulama başlatma işlemi hakkında daha fazla bilgi için bkz: [uygulama başlangıç](xref:fundamentals/startup).</span><span class="sxs-lookup"><span data-stu-id="94e35-141">For more information about the application start up process, see [Application Startup](xref:fundamentals/startup).</span></span>

3.  <span data-ttu-id="94e35-142">Bir kullanıcı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="94e35-142">Create a user.</span></span>

    <span data-ttu-id="94e35-143">Uygulamayı başlatın ve sonra tıklatın **kaydetmek** bağlantı.</span><span class="sxs-lookup"><span data-stu-id="94e35-143">Launch the application and then click on the **Register** link.</span></span>

    <span data-ttu-id="94e35-144">Bu eylem gerçekleştiriyorsunuz ilk kez kullanıyorsanız geçişler çalıştırmak için gerekli olabilir.</span><span class="sxs-lookup"><span data-stu-id="94e35-144">If this is the first time you're performing this action, you may be required to run migrations.</span></span> <span data-ttu-id="94e35-145">Uygulama ister **uygulamak geçişler**.</span><span class="sxs-lookup"><span data-stu-id="94e35-145">The application prompts you to **Apply Migrations**.</span></span> <span data-ttu-id="94e35-146">Gerekirse sayfayı yenileyin.</span><span class="sxs-lookup"><span data-stu-id="94e35-146">Refresh the page if needed.</span></span>
    
    ![Geçişler Web sayfasına Uygula](identity/_static/apply-migrations.png)
    
    <span data-ttu-id="94e35-148">Alternatif olarak, kullanarak, bir bellek içi veritabanına kalıcı bir veritabanı olmadan uygulamanızla ASP.NET Core kimliği test edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="94e35-148">Alternately, you can test using ASP.NET Core Identity with your app without a persistent database by using an in-memory database.</span></span> <span data-ttu-id="94e35-149">Bellek içi veritabanı kullanmak için add ``Microsoft.EntityFrameworkCore.InMemory`` paketini uygulamanıza ve uygulamanızın çağrısına değiştirme ``AddDbContext`` içinde ``ConfigureServices`` gibi:</span><span class="sxs-lookup"><span data-stu-id="94e35-149">To use an in-memory database, add the ``Microsoft.EntityFrameworkCore.InMemory`` package to your app and modify your app's call to ``AddDbContext`` in ``ConfigureServices`` as follows:</span></span>

    ```csharp
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseInMemoryDatabase(Guid.NewGuid().ToString()));
    ```
    
    <span data-ttu-id="94e35-150">Kullanıcı tıkladığında **kaydetmek** bağlantı ``Register`` eylem çağrılır ``AccountController``.</span><span class="sxs-lookup"><span data-stu-id="94e35-150">When the user clicks the **Register** link, the ``Register`` action is invoked on ``AccountController``.</span></span> <span data-ttu-id="94e35-151">``Register`` Eylem çağırarak kullanıcı oluşturur `CreateAsync` üzerinde `_userManager` nesne (için sağlanan ``AccountController`` bağımlılık ekleme göre):</span><span class="sxs-lookup"><span data-stu-id="94e35-151">The ``Register`` action creates the user by calling `CreateAsync` on the  `_userManager` object (provided to ``AccountController`` by dependency injection):</span></span>
 
    [!code-csharp[Main](identity/sample/src/ASPNET-IdentityDemo/Controllers/AccountController.cs?name=snippet_register&highlight=11)]

    <span data-ttu-id="94e35-152">Kullanıcı başarıyla oluşturulduysa, kullanıcı çağrısıyla oturum ``_signInManager.SignInAsync``.</span><span class="sxs-lookup"><span data-stu-id="94e35-152">If the user was created successfully, the user is logged in by the call to ``_signInManager.SignInAsync``.</span></span>

    <span data-ttu-id="94e35-153">**Not:** bkz [hesap onayı](xref:security/authentication/accconfirm#prevent-login-at-registration) adımların kayıt sırasında hemen oturum açma önlemek.</span><span class="sxs-lookup"><span data-stu-id="94e35-153">**Note:** See [account confirmation](xref:security/authentication/accconfirm#prevent-login-at-registration) for steps to prevent immediate login at registration.</span></span>
 
4.  <span data-ttu-id="94e35-154">Oturum aç.</span><span class="sxs-lookup"><span data-stu-id="94e35-154">Log in.</span></span>
 
    <span data-ttu-id="94e35-155">Kullanıcılar oturum açabilir tıklayarak **oturum** üst sitenin bağlantısını veya yetkilendirme gerektiren site parçası erişmeye çalışırsanız, oturum açma sayfasına gittiğinizde.</span><span class="sxs-lookup"><span data-stu-id="94e35-155">Users can sign in by clicking the **Log in** link at the top of the site, or they may be navigated to the Login page if they attempt to access a part of the site that requires authorization.</span></span> <span data-ttu-id="94e35-156">Kullanıcı oturum açma sayfasındaki formu gönderdiğinde ``AccountController`` ``Login`` eylem çağrılır.</span><span class="sxs-lookup"><span data-stu-id="94e35-156">When the user submits the form on the Login page, the ``AccountController`` ``Login`` action is called.</span></span>

    <span data-ttu-id="94e35-157">``Login`` Eylem çağrılarını ``PasswordSignInAsync`` üzerinde ``_signInManager`` nesne (için sağlanan ``AccountController`` bağımlılık ekleme tarafından).</span><span class="sxs-lookup"><span data-stu-id="94e35-157">The ``Login`` action calls ``PasswordSignInAsync`` on the ``_signInManager`` object (provided to ``AccountController`` by dependency injection).</span></span>

    [!code-csharp[Main](identity/sample/src/ASPNET-IdentityDemo/Controllers/AccountController.cs?name=snippet_login&highlight=13-14)]
 
    <span data-ttu-id="94e35-158">Temel ``Controller`` sınıf çıkarır bir ``User`` denetleyicisi yöntemleri erişebilirsiniz özelliği.</span><span class="sxs-lookup"><span data-stu-id="94e35-158">The base ``Controller`` class exposes a ``User`` property that you can access from controller methods.</span></span> <span data-ttu-id="94e35-159">Örneğin, listeleme `User.Claims` ve yetkilendirme kararları.</span><span class="sxs-lookup"><span data-stu-id="94e35-159">For instance, you can enumerate `User.Claims` and make authorization decisions.</span></span> <span data-ttu-id="94e35-160">Daha fazla bilgi için bkz: [yetkilendirme](xref:security/authorization/index).</span><span class="sxs-lookup"><span data-stu-id="94e35-160">For more information, see [Authorization](xref:security/authorization/index).</span></span>
 
5.  <span data-ttu-id="94e35-161">Oturumu kapatın.</span><span class="sxs-lookup"><span data-stu-id="94e35-161">Log out.</span></span>
 
    <span data-ttu-id="94e35-162">Tıklatarak **oturumunuzu** bağlama çağrıları `LogOut` eylem.</span><span class="sxs-lookup"><span data-stu-id="94e35-162">Clicking the **Log out** link calls the `LogOut` action.</span></span>
 
    [!code-csharp[Main](identity/sample/src/ASPNET-IdentityDemo/Controllers/AccountController.cs?name=snippet_logout&highlight=7)]
 
    <span data-ttu-id="94e35-163">Önceki kod çağrıları yukarıda `_signInManager.SignOutAsync` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="94e35-163">The preceding code above calls the `_signInManager.SignOutAsync` method.</span></span> <span data-ttu-id="94e35-164">`SignOutAsync` Yöntemi bir tanımlama bilgisinde depolanan kullanıcının talepleri temizler.</span><span class="sxs-lookup"><span data-stu-id="94e35-164">The `SignOutAsync` method clears the user's claims stored in a cookie.</span></span>
 
6.  <span data-ttu-id="94e35-165">Yapılandırma.</span><span class="sxs-lookup"><span data-stu-id="94e35-165">Configuration.</span></span>

    <span data-ttu-id="94e35-166">Kimlik, uygulamanızın başlangıç sınıfında geçersiz kılabilirsiniz bazı varsayılan davranışlar vardır.</span><span class="sxs-lookup"><span data-stu-id="94e35-166">Identity has some default behaviors that you can override in your application's startup class.</span></span> <span data-ttu-id="94e35-167">Yapılandırma gerekmez ``IdentityOptions`` varsayılan davranışları kullanıyorsanız.</span><span class="sxs-lookup"><span data-stu-id="94e35-167">You do not need to configure ``IdentityOptions`` if you are using the default behaviors.</span></span>

    # <a name="aspnet-core-2xtabaspnetcore2x"></a>[<span data-ttu-id="94e35-168">ASP.NET 2.x çekirdek</span><span class="sxs-lookup"><span data-stu-id="94e35-168">ASP.NET Core 2.x</span></span>](#tab/aspnetcore2x)
    
    [!code-csharp[Main](identity/sample/src/ASPNETv2-IdentityDemo/Startup.cs?name=snippet_configureservices&highlight=7-9,11-28,30-39)]
    
    # <a name="aspnet-core-1xtabaspnetcore1x"></a>[<span data-ttu-id="94e35-169">ASP.NET 1.x çekirdek</span><span class="sxs-lookup"><span data-stu-id="94e35-169">ASP.NET Core 1.x</span></span>](#tab/aspnetcore1x)
    
    [!code-csharp[Main](identity/sample/src/ASPNET-IdentityDemo/Startup.cs?name=snippet_configureservices&highlight=13-34)]

    ---
    
    <span data-ttu-id="94e35-170">Kimlik yapılandırma hakkında daha fazla bilgi için bkz: [yapılandırma kimlik](xref:security/authentication/identity-configuration).</span><span class="sxs-lookup"><span data-stu-id="94e35-170">For more information about how to configure Identity, see [Configure Identity](xref:security/authentication/identity-configuration).</span></span>
    
    <span data-ttu-id="94e35-171">Birincil anahtar, veri türünü de yapılandırabilirsiniz bkz [yapılandırma kimlik birincil anahtarlar veri türü](xref:security/authentication/identity-primary-key-configuration).</span><span class="sxs-lookup"><span data-stu-id="94e35-171">You also can configure the data type of the primary key, see [Configure Identity primary keys data type](xref:security/authentication/identity-primary-key-configuration).</span></span>
 
7.  <span data-ttu-id="94e35-172">Veritabanını görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="94e35-172">View the database.</span></span>

    <span data-ttu-id="94e35-173">Uygulamanızı bir SQL Server veritabanı (Windows ve Visual Studio kullanıcılar için varsayılan) kullanıyorsa, veritabanı oluşturulan uygulama görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="94e35-173">If your app is using a SQL Server database (the default on Windows and for Visual Studio users), you can view the database the app created.</span></span> <span data-ttu-id="94e35-174">Kullanabileceğiniz **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="94e35-174">You can use **SQL Server Management Studio**.</span></span> <span data-ttu-id="94e35-175">Alternatif olarak, Visual Studio'dan seçin **Görünüm** > **SQL Server Nesne Gezgini**.</span><span class="sxs-lookup"><span data-stu-id="94e35-175">Alternatively, from Visual Studio, select **View** > **SQL Server Object Explorer**.</span></span> <span data-ttu-id="94e35-176">Bağlanmak **(localdb) \MSSQLLocalDB**.</span><span class="sxs-lookup"><span data-stu-id="94e35-176">Connect to **(localdb)\MSSQLLocalDB**.</span></span> <span data-ttu-id="94e35-177">İle eşleşen ada sahip veritabanı  **aspnet - <*projenizin ad*>-<*tarih dizesi*> ** görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="94e35-177">The database with a name matching **aspnet-<*name of your project*>-<*date string*>** is displayed.</span></span>

    ![Bağlam menüsünde AspNetUsers veritabanı tablosu](identity/_static/04-db.png)
    
    <span data-ttu-id="94e35-179">Veritabanı'nı genişletin ve kendi **tabloları**, sonra sağ **dbo. AspNetUsers** tablo ve seçin **görünüm verilerini**.</span><span class="sxs-lookup"><span data-stu-id="94e35-179">Expand the database and its **Tables**, then right-click the **dbo.AspNetUsers** table and select **View Data**.</span></span>

8. <span data-ttu-id="94e35-180">Kimliği'nin çalıştığını doğrulama</span><span class="sxs-lookup"><span data-stu-id="94e35-180">Verify Identity works</span></span>

    <span data-ttu-id="94e35-181">Varsayılan *ASP.NET çekirdek Web uygulaması* proje şablonu sağlar gerek kalmadan uygulama içinde herhangi bir işlem erişmek kullanıcıların oturum açmak için.</span><span class="sxs-lookup"><span data-stu-id="94e35-181">The default *ASP.NET Core Web Application* project template allows users to access any action in the application without having to login.</span></span> <span data-ttu-id="94e35-182">ASP.NET Identity çalıştığını doğrulamak için ekleme bir`[Authorize]` özniteliğini `About` eylemi `Home` denetleyicisi.</span><span class="sxs-lookup"><span data-stu-id="94e35-182">To verify that ASP.NET Identity works, add an`[Authorize]` attribute to the `About` action of the `Home` Controller.</span></span>
 
    ```cs
    [Authorize]
    public IActionResult About()
    {
        ViewData["Message"] = "Your application description page.";
        return View();
    }
    ```
    
    # <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="94e35-183">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94e35-183">Visual Studio</span></span>](#tab/visual-studio)

    <span data-ttu-id="94e35-184">Kullanarak projeyi çalıştırmak **Ctrl** + **F5** gidin **hakkında** sayfası.</span><span class="sxs-lookup"><span data-stu-id="94e35-184">Run the project using **Ctrl** + **F5** and navigate to the **About** page.</span></span> <span data-ttu-id="94e35-185">Yalnızca kimliği doğrulanan kullanıcılar erişebilir **hakkında** ASP.NET oturum açmak veya kaydetmek için oturum açma sayfasına yönlendirir şekilde şimdi, sayfa.</span><span class="sxs-lookup"><span data-stu-id="94e35-185">Only authenticated users may access the **About** page now, so ASP.NET redirects you to the login page to login or register.</span></span>

    # <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="94e35-186">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="94e35-186">.NET Core CLI</span></span>](#tab/netcore-cli)

    <span data-ttu-id="94e35-187">Bir komut penceresi açın ve projenin kök dizinine gidin dizinini içeren `.csproj` dosya.</span><span class="sxs-lookup"><span data-stu-id="94e35-187">Open a command window and navigate to the project's root directory containing the `.csproj` file.</span></span> <span data-ttu-id="94e35-188">Çalıştırma `dotnet run` uygulamayı çalıştırmak için komutu:</span><span class="sxs-lookup"><span data-stu-id="94e35-188">Run the `dotnet run` command to run the app:</span></span>

    ```cs
    dotnet run 
    ```

    <span data-ttu-id="94e35-189">Cmdlet çıktısının belirtilen URL'ye Gözat `dotnet run` komutu.</span><span class="sxs-lookup"><span data-stu-id="94e35-189">Browse the URL specified in the output from the `dotnet run` command.</span></span> <span data-ttu-id="94e35-190">URL işaret etmelidir `localhost` ile oluşturulan bağlantı noktası numarası.</span><span class="sxs-lookup"><span data-stu-id="94e35-190">The URL should point to `localhost` with a generated port number.</span></span> <span data-ttu-id="94e35-191">Gidin **hakkında** sayfası.</span><span class="sxs-lookup"><span data-stu-id="94e35-191">Navigate to the **About** page.</span></span> <span data-ttu-id="94e35-192">Yalnızca kimliği doğrulanan kullanıcılar erişebilir **hakkında** ASP.NET oturum açmak veya kaydetmek için oturum açma sayfasına yönlendirir şekilde şimdi, sayfa.</span><span class="sxs-lookup"><span data-stu-id="94e35-192">Only authenticated users may access the **About** page now, so ASP.NET redirects you to the login page to login or register.</span></span>

    ---

## <a name="identity-components"></a><span data-ttu-id="94e35-193">Kimlik bileşenleri</span><span class="sxs-lookup"><span data-stu-id="94e35-193">Identity Components</span></span>

<span data-ttu-id="94e35-194">Kimlik sistemi için birincil başvuru derleme `Microsoft.AspNetCore.Identity`.</span><span class="sxs-lookup"><span data-stu-id="94e35-194">The primary reference assembly for the Identity system is `Microsoft.AspNetCore.Identity`.</span></span> <span data-ttu-id="94e35-195">Bu paket ASP.NET Core kimliği arabirimleri çekirdek kümesini içerir ve tarafından dahil `Microsoft.AspNetCore.Identity.EntityFrameworkCore`.</span><span class="sxs-lookup"><span data-stu-id="94e35-195">This package contains the core set of interfaces for ASP.NET Core Identity, and is included by `Microsoft.AspNetCore.Identity.EntityFrameworkCore`.</span></span>

<span data-ttu-id="94e35-196">Bu bağımlılıklar, ASP.NET Core uygulamalarında kimlik sistemi kullanmak için gereklidir:</span><span class="sxs-lookup"><span data-stu-id="94e35-196">These dependencies are needed to use the Identity system in ASP.NET Core applications:</span></span>

* <span data-ttu-id="94e35-197">`Microsoft.AspNetCore.Identity.EntityFrameworkCore`-Identity Entity Framework Çekirdek ile kullanmak için gereken türler içerir.</span><span class="sxs-lookup"><span data-stu-id="94e35-197">`Microsoft.AspNetCore.Identity.EntityFrameworkCore` - Contains the required types to use Identity with Entity Framework Core.</span></span>

* <span data-ttu-id="94e35-198">`Microsoft.EntityFrameworkCore.SqlServer`-Entity Framework Çekirdek Microsoft'un önerilen veri erişimi SQL Server gibi ilişkisel veritabanları için teknolojisidir.</span><span class="sxs-lookup"><span data-stu-id="94e35-198">`Microsoft.EntityFrameworkCore.SqlServer` - Entity Framework Core is Microsoft's recommended data access technology for relational databases like SQL Server.</span></span> <span data-ttu-id="94e35-199">Kullanabileceğiniz test etmek için `Microsoft.EntityFrameworkCore.InMemory`.</span><span class="sxs-lookup"><span data-stu-id="94e35-199">For testing, you can use `Microsoft.EntityFrameworkCore.InMemory`.</span></span>

* <span data-ttu-id="94e35-200">`Microsoft.AspNetCore.Authentication.Cookies`-Tanımlama bilgisi tabanlı kimlik doğrulaması kullanmak bir uygulama sağlar ara yazılımı.</span><span class="sxs-lookup"><span data-stu-id="94e35-200">`Microsoft.AspNetCore.Authentication.Cookies` - Middleware that enables an app to use cookie-based authentication.</span></span>

## <a name="migrating-to-aspnet-core-identity"></a><span data-ttu-id="94e35-201">ASP.NET Core kimliği geçirme</span><span class="sxs-lookup"><span data-stu-id="94e35-201">Migrating to ASP.NET Core Identity</span></span>

<span data-ttu-id="94e35-202">Ek bilgi ve mevcut kimliğinizi geçirme konusunda yönergeler bakın depolamak için [geçirme kimlik doğrulama ve kimlik](xref:migration/identity).</span><span class="sxs-lookup"><span data-stu-id="94e35-202">For additional information and guidance on migrating your existing Identity store see [Migrating Authentication and Identity](xref:migration/identity).</span></span>

## <a name="next-steps"></a><span data-ttu-id="94e35-203">Sonraki Adımlar</span><span class="sxs-lookup"><span data-stu-id="94e35-203">Next Steps</span></span>

* [<span data-ttu-id="94e35-204">Geçirme kimlik doğrulama ve kimlik</span><span class="sxs-lookup"><span data-stu-id="94e35-204">Migrating Authentication and Identity</span></span>](xref:migration/identity)
* [<span data-ttu-id="94e35-205">Hesap Onaylama ve Parola Kurtarma</span><span class="sxs-lookup"><span data-stu-id="94e35-205">Account Confirmation and Password Recovery</span></span>](xref:security/authentication/accconfirm)
* [<span data-ttu-id="94e35-206">SMS ile iki öğeli kimlik doğrulama</span><span class="sxs-lookup"><span data-stu-id="94e35-206">Two-factor authentication with SMS</span></span>](xref:security/authentication/2fa)
* [<span data-ttu-id="94e35-207">Facebook, Google ve diğer dış sağlayıcıları kullanarak kimlik doğrulamayı etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="94e35-207">Enabling authentication using Facebook, Google and other external providers</span></span>](xref:security/authentication/social/index)