---
title: "Mac için Visual Studio Razor sayfalarının uygulamayla bir modeli ekleme"
author: rick-anderson
description: "Mac için Visual Studio kullanarak ASP.NET Core Razor sayfalarının uygulamada bir modeli ekleme"
manager: wpickett
ms.author: riande
ms.date: 08/27/2017
ms.prod: aspnet-core
ms.technology: aspnet
ms.topic: get-started-article
uid: tutorials/razor-pages-vsc/model
ms.openlocfilehash: 9600392b47fb8b1dded06faefaff1bf87d67af4e
ms.sourcegitcommit: a510f38930abc84c4b302029d019a34dfe76823b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="adding-a-model-to-a-razor-pages-app-in-aspnet-core-with-visual-studio-code"></a>Visual Studio Code ile ASP.NET Core Razor sayfalarının uygulamada bir modeli ekleme

[!INCLUDE[model1](../../includes/RP/model1.md)]

## <a name="add-a-data-model"></a>Bir veri modeli ekleme

* Adlı bir klasör ekleme *modelleri*.
* Bir sınıfa eklemek *modelleri* adlı klasörü *Movie.cs*.
* Aşağıdaki kodu ekleyin *Models/Movie.cs* dosyası:

[!INCLUDE[model 2](../../includes/RP/model2.md)]
[!INCLUDE[model 2a](../../includes/RP/model2a.md)]

[!code-csharp[Main](../../tutorials/razor-pages/razor-pages-start/sample/RazorPagesMovie/Startup.cs?name=snippet_ConfigureServices2&highlight=3-6)]

Herhangi bir hata yoksa doğrulamak için projeyi oluşturun.

### <a name="entity-framework-core-nuget-packages-for-migrations"></a>Geçişler için Entity Framework Core NuGet paketleri

EF Araçları komut satırı arabirimi (CLI) için sağlanan [Microsoft.EntityFrameworkCore.Tools.DotNet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Tools.DotNet). Bu paketi yüklemek için ekleyin `DotNetCliToolReference` koleksiyonunda *.csproj* dosya. **Not:** düzenleyerek bu paketi yüklemek zorunda *.csproj* dosya; kullanamazsınız `install-package` komut veya GUI Paket Yöneticisi.

Düzen *RazorPagesMovie.csproj* dosyası:

* Seçin **dosya** > **açık dosya**ve ardından *RazorPagesMovie.csproj* dosya.
* Aracı başvurusunu ekleyin `Microsoft.EntityFrameworkCore.Tools.DotNet` ikinci  **\<ItemGroup >**:

[!code-xml[Main](../../tutorials/razor-pages/razor-pages-start/snapshot_cli_sample/RazorPagesMovie/RazorPagesMovie.cli.csproj)]

[!INCLUDE[model 3](../../includes/RP/model3.md)]

<a name="scaffold"></a>
### <a name="scaffold-the-movie-model"></a>İskele film modeli

* Proje dizininde bir komut penceresi açın (içeren dizine *Program.cs*, *haline*, ve *.csproj* dosyaları).
* Şu komutu çalıştırın:

**Not: Windows aşağıdaki komutu çalıştırın. MacOS ve Linux için bkz: sonraki komutu**

  ```console
  dotnet aspnet-codegenerator razorpage -m Movie -dc MovieContext -udl -outDir Pages\Movies --referenceScriptLibraries
  ```

* MacOS ve Linux üzerinde aşağıdaki komutu çalıştırın:

  ```console
  dotnet aspnet-codegenerator razorpage -m Movie -dc MovieContext -udl -outDir Pages/Movies --referenceScriptLibraries
  ```

Hatayı alırsanız:
  ```
  The process cannot access the file 
 'RazorPagesMovie/bin/Debug/netcoreapp2.0/RazorPagesMovie.dll' 
  because it is being used by another process.
  ```

Visual Studio çıkın ve komutu yeniden çalıştırın.

[!INCLUDE[model 4](../../includes/RP/model4.md)]Sonraki öğretici yapı iskelesi tarafından oluşturulan dosyalar açıklanmaktadır.

>[!div class="step-by-step"]
[Önceki: Başlarken](xref:tutorials/razor-pages-vsc/razor-pages-start)
[sonraki: iskele kurulmuş Razor sayfaları](xref:tutorials/razor-pages-vsc/page)
