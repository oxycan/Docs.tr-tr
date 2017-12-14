---
title: "ASP.NET Core geliştirme sırasında uygulama sırrı güvenli depolama"
author: rick-anderson
description: "Gizli geliştirme sırasında güvenli bir şekilde depolamak nasıl gösterir"
keywords: "ASP.NET Çekirdeği"
ms.author: riande
manager: wpickett
ms.date: 09/15/2017
ms.topic: article
ms.technology: aspnet
ms.prod: asp.net-core
uid: security/app-secrets
ms.openlocfilehash: 897d9b360ceeb5fbb0863ff1c1fcec039e1a8b8f
ms.sourcegitcommit: 8f42ab93402c1b8044815e1e48d0bb84c81f8b59
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
---
# <a name="safe-storage-of-app-secrets-during-development-in-aspnet-core"></a><span data-ttu-id="cb454-104">ASP.NET Core geliştirme sırasında uygulama sırrı güvenli depolama</span><span class="sxs-lookup"><span data-stu-id="cb454-104">Safe storage of app secrets during development in ASP.NET Core</span></span>

<span data-ttu-id="cb454-105">Tarafından [Rick Anderson](https://twitter.com/RickAndMSFT), [Daniel Roth](https://github.com/danroth27), ve [Scott Addie](https://scottaddie.com)</span><span class="sxs-lookup"><span data-stu-id="cb454-105">By [Rick Anderson](https://twitter.com/RickAndMSFT), [Daniel Roth](https://github.com/danroth27), and [Scott Addie](https://scottaddie.com)</span></span> 

<span data-ttu-id="cb454-106">Bu belge, gizli Yöneticisi aracını geliştirme gizli kodunuzu dışında tutmak için nasıl kullanabileceğinizi gösterir.</span><span class="sxs-lookup"><span data-stu-id="cb454-106">This document shows how you can use the Secret Manager tool in development to keep secrets out of your code.</span></span> <span data-ttu-id="cb454-107">En önemli kaynak kodunda parolalar ve diğer hassas verileri asla saklamalısınız ve geliştirme ve test modunda üretim gizli kullanmamanız noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="cb454-107">The most important point is you should never store passwords or other sensitive data in source code, and you shouldn't use production secrets in development and test mode.</span></span> <span data-ttu-id="cb454-108">Bunun yerine kullanabileceğiniz [yapılandırma](xref:fundamentals/configuration/index) ortam değişkenlerinin bu değerleri okumak veya gizli Yöneticisi'ni kullanarak depolanan değerlerden aracı sistem.</span><span class="sxs-lookup"><span data-stu-id="cb454-108">You can instead use the [configuration](xref:fundamentals/configuration/index) system to read these values from environment variables or from values stored using the Secret Manager tool.</span></span> <span data-ttu-id="cb454-109">Gizli Manager aracı kaynak denetimine iade hassas verileri önlemeye yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="cb454-109">The Secret Manager tool helps prevent sensitive data from being checked into source control.</span></span> <span data-ttu-id="cb454-110">[Yapılandırma](xref:fundamentals/configuration/index) sistem, bu makalede açıklanan gizli Yöneticisi aracıyla depolanan gizli okuyabilir.</span><span class="sxs-lookup"><span data-stu-id="cb454-110">The [configuration](xref:fundamentals/configuration/index) system can read secrets stored with the Secret Manager tool described in this article.</span></span>

<span data-ttu-id="cb454-111">Parola Yöneticisi aracını yalnızca geliştirme kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cb454-111">The Secret Manager tool is used only in development.</span></span> <span data-ttu-id="cb454-112">Azure test ve üretim parolaları ile koruma [Microsoft Azure anahtar kasası](https://azure.microsoft.com/services/key-vault/) yapılandırma sağlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="cb454-112">You can safeguard Azure test and production secrets with the [Microsoft Azure Key Vault](https://azure.microsoft.com/services/key-vault/) configuration provider.</span></span> <span data-ttu-id="cb454-113">Bkz: [Azure anahtar kasası yapılandırma sağlayıcısı](https://docs.microsoft.com/aspnet/core/security/key-vault-configuration) daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="cb454-113">See [Azure Key Vault configuration provider](https://docs.microsoft.com/aspnet/core/security/key-vault-configuration) for more information.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="cb454-114">Ortam değişkenleri</span><span class="sxs-lookup"><span data-stu-id="cb454-114">Environment variables</span></span>

<span data-ttu-id="cb454-115">Uygulama gizli kod veya yerel yapılandırma dosyalarını depolamak önlemek için ortam değişkenleri gizli depolar.</span><span class="sxs-lookup"><span data-stu-id="cb454-115">To avoid storing app secrets in code or in local configuration files, you store secrets in environment variables.</span></span> <span data-ttu-id="cb454-116">Kurulum [yapılandırma](xref:fundamentals/configuration/index) çağırarak ortam değişkenlerinin değerlerini okumasını framework `AddEnvironmentVariables`.</span><span class="sxs-lookup"><span data-stu-id="cb454-116">You can setup the [configuration](xref:fundamentals/configuration/index) framework to read values from environment variables by calling `AddEnvironmentVariables`.</span></span> <span data-ttu-id="cb454-117">Ardından, tüm daha önce belirtilen yapılandırma kaynakları için yapılandırma değerleri geçersiz kılmak için ortam değişkenlerini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cb454-117">You can then use environment variables to override configuration values for all previously specified configuration sources.</span></span>

<span data-ttu-id="cb454-118">Örneğin, tek tek kullanıcı hesaplarını yeni bir ASP.NET Core web uygulaması oluşturursanız, bu varsayılan bağlantı dizesi ekleyecek *appsettings.json* anahtarla proje dosyasında `DefaultConnection`.</span><span class="sxs-lookup"><span data-stu-id="cb454-118">For example, if you create a new ASP.NET Core web app with individual user accounts, it will add a default connection string to the *appsettings.json* file in the project with the key `DefaultConnection`.</span></span> <span data-ttu-id="cb454-119">Varsayılan bağlantı dizesini, kullanıcı modunda çalışır ve bir parola gerektirmez, LocalDB kullanmak üzere kurulur.</span><span class="sxs-lookup"><span data-stu-id="cb454-119">The default connection string is setup to use LocalDB, which runs in user mode and doesn't require a password.</span></span> <span data-ttu-id="cb454-120">Uygulamanızı test veya üretim sunucusunu dağıttığınızda, geçersiz kılabilirsiniz `DefaultConnection` anahtar değerini ayarıyla test veya üretim veritabanı için (potansiyel olarak harfe duyarlı kimlik bilgileri) bağlantı dizesini içeren bir ortam değişkeni Sunucu.</span><span class="sxs-lookup"><span data-stu-id="cb454-120">When you deploy your application to a test or production server, you can override the `DefaultConnection` key value with an environment variable setting that contains the connection string (potentially with sensitive credentials) for a test or production database server.</span></span>

>[!WARNING]
> <span data-ttu-id="cb454-121">Ortam değişkenleri genellikle düz metin olarak depolanır ve şifrelenmez.</span><span class="sxs-lookup"><span data-stu-id="cb454-121">Environment variables are generally stored in plain text and are not encrypted.</span></span> <span data-ttu-id="cb454-122">Makine ya da işlem aşılırsa, ortam değişkenleri Güvenilmeyen taraflar tarafından erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="cb454-122">If the machine or process is compromised, then environment variables can be accessed by untrusted parties.</span></span> <span data-ttu-id="cb454-123">Kullanıcı parolaları açığa çıkmasını önlemek için ek önlemler gerekli olabilir.</span><span class="sxs-lookup"><span data-stu-id="cb454-123">Additional measures to prevent disclosure of user secrets may still be required.</span></span>

## <a name="secret-manager"></a><span data-ttu-id="cb454-124">Parola Yöneticisi</span><span class="sxs-lookup"><span data-stu-id="cb454-124">Secret Manager</span></span>

<span data-ttu-id="cb454-125">Parola Yöneticisi aracını proje ağacı dışında geliştirme çalışması için hassas verileri depolar.</span><span class="sxs-lookup"><span data-stu-id="cb454-125">The Secret Manager tool stores sensitive data for development work outside of your project tree.</span></span> <span data-ttu-id="cb454-126">Parola Yöneticisi Aracı için parolaları depolamak için kullanılan bir proje araçtır bir [.NET Core](https://www.microsoft.com/net/core) proje geliştirme sırasında.</span><span class="sxs-lookup"><span data-stu-id="cb454-126">The Secret Manager tool is a project tool that can be used to store secrets for a [.NET Core](https://www.microsoft.com/net/core) project during development.</span></span> <span data-ttu-id="cb454-127">Gizli Yöneticisi aracıyla uygulama sırrı belirli bir proje ile ilişkilendirmek ve birden çok projeler arasında paylaşın.</span><span class="sxs-lookup"><span data-stu-id="cb454-127">With the Secret Manager tool, you can associate app secrets with a specific project and share them across multiple projects.</span></span>

>[!WARNING]
> <span data-ttu-id="cb454-128">Gizli Yöneticisi aracını depolanan gizli şifrelemez ve güvenilir bir deposu olarak değerlendirilmeyen.</span><span class="sxs-lookup"><span data-stu-id="cb454-128">The Secret Manager tool does not encrypt the stored secrets and should not be treated as a trusted store.</span></span> <span data-ttu-id="cb454-129">Yalnızca geliştirme amacıyla kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cb454-129">It is for development purposes only.</span></span> <span data-ttu-id="cb454-130">Anahtarları ve değerleri, kullanıcı profili dizini bir JSON yapılandırma dosyasında depolanır.</span><span class="sxs-lookup"><span data-stu-id="cb454-130">The keys and values are stored in a JSON configuration file in the user profile directory.</span></span>

## <a name="installing-the-secret-manager-tool"></a><span data-ttu-id="cb454-131">Parola Yöneticisi aracını yükleme</span><span class="sxs-lookup"><span data-stu-id="cb454-131">Installing the Secret Manager tool</span></span>

# <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="cb454-132">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cb454-132">Visual Studio</span></span>](#tab/visual-studio)

<span data-ttu-id="cb454-133">Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Düzenle \<project_name\>.csproj** ve bağlam menüsünden.</span><span class="sxs-lookup"><span data-stu-id="cb454-133">Right-click the project in Solution Explorer, and select **Edit \<project_name\>.csproj** from the context menu.</span></span> <span data-ttu-id="cb454-134">Vurgulanan satırı ekleyin *.csproj* dosya ve ilişkili NuGet paket geri yüklemek için kaydedin:</span><span class="sxs-lookup"><span data-stu-id="cb454-134">Add the highlighted line to the *.csproj* file, and save to restore the associated NuGet package:</span></span>

[!code-xml[Main](app-secrets/sample/UserSecrets/UserSecrets-before.csproj?highlight=10)]

<span data-ttu-id="cb454-135">Çözüm Gezgini'nde projeye tekrar sağ tıklayın ve seçin **kullanıcı parolaları yönetme** ve bağlam menüsünden.</span><span class="sxs-lookup"><span data-stu-id="cb454-135">Right-click the project in Solution Explorer again, and select **Manage User Secrets** from the context menu.</span></span> <span data-ttu-id="cb454-136">Bu hareketi yeni ekler `UserSecretsId` düğümde bir `PropertyGroup` , *.csproj* dosyası, aşağıdaki örnekte vurgulanmış olarak:</span><span class="sxs-lookup"><span data-stu-id="cb454-136">This gesture adds a new `UserSecretsId` node within a `PropertyGroup` of the *.csproj* file, as highlighted in the following sample:</span></span>

[!code-xml[Main](app-secrets/sample/UserSecrets/UserSecrets-after.csproj?highlight=4)]

<span data-ttu-id="cb454-137">Değiştirilen kaydetme *.csproj* dosya de açılır bir `secrets.json` dosyasını bir metin düzenleyicisinde.</span><span class="sxs-lookup"><span data-stu-id="cb454-137">Saving the modified *.csproj* file also opens a `secrets.json` file in the text editor.</span></span> <span data-ttu-id="cb454-138">Değiştir `secrets.json` aşağıdaki kod ile dosya:</span><span class="sxs-lookup"><span data-stu-id="cb454-138">Replace the contents of the `secrets.json` file with the following code:</span></span>

```json
{
    "MySecret": "ValueOfMySecret"
}
```

# <a name="visual-studio-codetabvisual-studio-code"></a>[<span data-ttu-id="cb454-139">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cb454-139">Visual Studio Code</span></span>](#tab/visual-studio-code)

<span data-ttu-id="cb454-140">Ekleme `Microsoft.Extensions.SecretManager.Tools` için *.csproj* dosya ve çalıştırma `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="cb454-140">Add `Microsoft.Extensions.SecretManager.Tools` to the *.csproj* file and run `dotnet restore`.</span></span> <span data-ttu-id="cb454-141">Parola Yöneticisi için komut satırını kullanarak aracı yüklemek için aynı adımları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cb454-141">You can use the same steps to install the Secret Manager Tool using for the command line.</span></span>

[!code-xml[Main](app-secrets/sample/UserSecrets/UserSecrets-before.csproj?highlight=10)]

<span data-ttu-id="cb454-142">Parola Yöneticisi aracını aşağıdaki komutu çalıştırarak test edin:</span><span class="sxs-lookup"><span data-stu-id="cb454-142">Test the Secret Manager tool by running the following command:</span></span>

```console
dotnet user-secrets -h
```

<span data-ttu-id="cb454-143">Parola Yöneticisi aracını kullanımı, seçenekleri ve komut Yardımı görüntüler.</span><span class="sxs-lookup"><span data-stu-id="cb454-143">The Secret Manager tool will display usage, options and command help.</span></span>

> [!NOTE]
> <span data-ttu-id="cb454-144">Aynı dizinde olmalıdır *.csproj* tanımlanan araçları çalıştırmak için dosya *.csproj* dosyanın `DotNetCliToolReference` düğümleri.</span><span class="sxs-lookup"><span data-stu-id="cb454-144">You must be in the same directory as the *.csproj* file to run tools defined in the *.csproj* file's `DotNetCliToolReference` nodes.</span></span>

<span data-ttu-id="cb454-145">Kullanıcı profilinizde depolanan projeye özgü yapılandırma ayarlarını gizli Yöneticisi aracını çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="cb454-145">The Secret Manager tool operates on project-specific configuration settings that are stored in your user profile.</span></span> <span data-ttu-id="cb454-146">Kullanıcı parolaları kullanmak için proje belirtmeniz gerekir bir `UserSecretsId` değeri kendi *.csproj* dosya.</span><span class="sxs-lookup"><span data-stu-id="cb454-146">To use user secrets, the project must specify a `UserSecretsId` value in its *.csproj* file.</span></span> <span data-ttu-id="cb454-147">Değeri `UserSecretsId` isteğe bağlıdır, ancak projeye genellikle benzersizdir.</span><span class="sxs-lookup"><span data-stu-id="cb454-147">The value of `UserSecretsId` is arbitrary, but is generally unique to the project.</span></span> <span data-ttu-id="cb454-148">Geliştiriciler genellikle oluşturmak için bir GUID `UserSecretsId`.</span><span class="sxs-lookup"><span data-stu-id="cb454-148">Developers typically generate a GUID for the `UserSecretsId`.</span></span>

<span data-ttu-id="cb454-149">Ekleme bir `UserSecretsId` projenizde için *.csproj* dosyası:</span><span class="sxs-lookup"><span data-stu-id="cb454-149">Add a `UserSecretsId` for your project in the *.csproj* file:</span></span>

[!code-xml[Main](app-secrets/sample/UserSecrets/UserSecrets-after.csproj?highlight=4)]

<span data-ttu-id="cb454-150">Bir parolayı ayarlamak için gizli Yöneticisi aracını kullanın.</span><span class="sxs-lookup"><span data-stu-id="cb454-150">Use the Secret Manager tool to set a secret.</span></span> <span data-ttu-id="cb454-151">Örneğin, proje dizinden bir komut penceresinde aşağıdakileri girin:</span><span class="sxs-lookup"><span data-stu-id="cb454-151">For example, in a command window from the project directory, enter the following:</span></span>

```console
dotnet user-secrets set MySecret ValueOfMySecret
```

<span data-ttu-id="cb454-152">Diğer dizinlerden gizli Yöneticisi aracını çalıştırabilirsiniz ancak kullanmalısınız `--project` yolunu geçirmek için seçeneği *.csproj* dosyası:</span><span class="sxs-lookup"><span data-stu-id="cb454-152">You can run the Secret Manager tool from other directories, but you must use the `--project` option to pass in the path to the *.csproj* file:</span></span>
 
```console
dotnet user-secrets set MySecret ValueOfMySecret --project c:\work\WebApp1\src\webapp1
```

<span data-ttu-id="cb454-153">Gizli Yöneticisi aracını, listesinde, kaldırmak ve uygulama temizlemek için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cb454-153">You can also use the Secret Manager tool to list, remove and clear app secrets.</span></span>

-----

## <a name="accessing-user-secrets-via-configuration"></a><span data-ttu-id="cb454-154">Kullanıcı parolaları yapılandırması aracılığıyla erişme</span><span class="sxs-lookup"><span data-stu-id="cb454-154">Accessing user secrets via configuration</span></span>

<span data-ttu-id="cb454-155">Gizli Yöneticisi gizli yapılandırma sistemi aracılığıyla erişebilir.</span><span class="sxs-lookup"><span data-stu-id="cb454-155">You access Secret Manager secrets through the configuration system.</span></span> <span data-ttu-id="cb454-156">Ekleme `Microsoft.Extensions.Configuration.UserSecrets` paketini ve çalıştırma `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="cb454-156">Add the `Microsoft.Extensions.Configuration.UserSecrets` package and run `dotnet restore`.</span></span>

<span data-ttu-id="cb454-157">Kullanıcı parolaları yapılandırma kaynağı'na ekleyin `Startup` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="cb454-157">Add the user secrets configuration source to the `Startup` method:</span></span>

[!code-csharp[Main](app-secrets/sample/UserSecrets/Startup.cs?highlight=16-19)]

<span data-ttu-id="cb454-158">Kullanıcı parolaları yapılandırma API'si aracılığıyla erişebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="cb454-158">You can access user secrets via the configuration API:</span></span>

[!code-csharp[Main](app-secrets/sample/UserSecrets/Startup.cs?highlight=26-29)]

## <a name="how-the-secret-manager-tool-works"></a><span data-ttu-id="cb454-159">Parola Yöneticisi aracını nasıl çalışır</span><span class="sxs-lookup"><span data-stu-id="cb454-159">How the Secret Manager tool works</span></span>

<span data-ttu-id="cb454-160">Parola Yöneticisi aracını hemen nerede ve nasıl değerleri saklanır gibi uygulama ayrıntılarını soyutlar.</span><span class="sxs-lookup"><span data-stu-id="cb454-160">The Secret Manager tool abstracts away the implementation details, such as where and how the values are stored.</span></span> <span data-ttu-id="cb454-161">Bu uygulama ayrıntılarını bilmeden aracını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cb454-161">You can use the tool without knowing these implementation details.</span></span> <span data-ttu-id="cb454-162">İçinde depolanan geçerli sürümde değerlerden bir [JSON](http://json.org/) kullanıcı profili dizini yapılandırma dosyasında:</span><span class="sxs-lookup"><span data-stu-id="cb454-162">In the current version, the values are stored in a [JSON](http://json.org/) configuration file in the user profile directory:</span></span>

* <span data-ttu-id="cb454-163">Windows:`%APPDATA%\microsoft\UserSecrets\<userSecretsId>\secrets.json`</span><span class="sxs-lookup"><span data-stu-id="cb454-163">Windows: `%APPDATA%\microsoft\UserSecrets\<userSecretsId>\secrets.json`</span></span>

* <span data-ttu-id="cb454-164">Linux:`~/.microsoft/usersecrets/<userSecretsId>/secrets.json`</span><span class="sxs-lookup"><span data-stu-id="cb454-164">Linux: `~/.microsoft/usersecrets/<userSecretsId>/secrets.json`</span></span>

* <span data-ttu-id="cb454-165">Mac:`~/.microsoft/usersecrets/<userSecretsId>/secrets.json`</span><span class="sxs-lookup"><span data-stu-id="cb454-165">Mac: `~/.microsoft/usersecrets/<userSecretsId>/secrets.json`</span></span>

<span data-ttu-id="cb454-166">Değeri `userSecretsId` içinde belirtilen değerle geldiği *.csproj* dosya.</span><span class="sxs-lookup"><span data-stu-id="cb454-166">The value of `userSecretsId` comes from the value specified in *.csproj* file.</span></span>

<span data-ttu-id="cb454-167">Bu uygulama ayrıntılarını değişebilir gibi konumu veya gizli anahtarı Yöneticisi aracıyla kaydedilen verilerin biçimi bağlıdır kodu yazamaz.</span><span class="sxs-lookup"><span data-stu-id="cb454-167">You should not write code that depends on the location or format of the data saved with the Secret Manager tool, as these implementation details might change.</span></span> <span data-ttu-id="cb454-168">Örneğin, gizli şu anda değerlerdir *değil* bugün şifrelenir, ancak gün olabilir.</span><span class="sxs-lookup"><span data-stu-id="cb454-168">For example, the secret values are currently *not* encrypted today, but could be someday.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb454-169">Ek Kaynaklar</span><span class="sxs-lookup"><span data-stu-id="cb454-169">Additional Resources</span></span>

* [<span data-ttu-id="cb454-170">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="cb454-170">Configuration</span></span>](xref:fundamentals/configuration/index)