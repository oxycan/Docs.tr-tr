---
uid: mvc/overview/older-versions-1/getting-started-with-mvc/getting-started-with-mvc-part2
title: Bir denetleyici ekleme | Microsoft Docs
author: shanselman
description: "Bu öğretici, burada Visual Studio 2013 kullanarak kullanılabiliyorsa, güncelleştirilmiş bir sürüm. Yeni öğretici t birçok iyileştirme sağlayan ASP.NET MVC 5 kullanır..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 08/14/2010
ms.topic: article
ms.assetid: ff03dcc0-da97-458d-838f-0823e7482642
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/older-versions-1/getting-started-with-mvc/getting-started-with-mvc-part2
msc.type: authoredcontent
ms.openlocfilehash: 93a362cf83d39b29fcba3f2dee0c28257805a89e
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="adding-a-controller"></a><span data-ttu-id="720fe-104">Bir denetleyici ekleme</span><span class="sxs-lookup"><span data-stu-id="720fe-104">Adding a Controller</span></span>
====================
<span data-ttu-id="720fe-105">tarafından [Scott Hanselman](https://github.com/shanselman)</span><span class="sxs-lookup"><span data-stu-id="720fe-105">by [Scott Hanselman](https://github.com/shanselman)</span></span>

> > [!NOTE]
> > <span data-ttu-id="720fe-106">Bu öğretici kullanılabiliyorsa, güncelleştirilmiş bir sürümünü [burada](../../getting-started/introduction/getting-started.md) kullanarak [Visual Studio 2013](https://www.microsoft.com/visualstudio/eng/2013-downloads).</span><span class="sxs-lookup"><span data-stu-id="720fe-106">An updated version if this tutorial is available [here](../../getting-started/introduction/getting-started.md) using [Visual Studio 2013](https://www.microsoft.com/visualstudio/eng/2013-downloads).</span></span> <span data-ttu-id="720fe-107">Yeni öğretici Bu öğretici birçok iyileştirme sağlayan ASP.NET MVC 5 kullanır.</span><span class="sxs-lookup"><span data-stu-id="720fe-107">The new tutorial uses ASP.NET MVC 5, which provides many improvements over this tutorial.</span></span>
> 
> 
> <span data-ttu-id="720fe-108">ASP.NET MVC temelleri tanıtır bir başlangıç Öğreticisi budur.</span><span class="sxs-lookup"><span data-stu-id="720fe-108">This is a beginner tutorial that introduces the basics of ASP.NET MVC.</span></span> <span data-ttu-id="720fe-109">Okuyan ve yazan bir veritabanından basit bir web uygulaması oluşturacaksınız.</span><span class="sxs-lookup"><span data-stu-id="720fe-109">You'll create a simple web application that reads and writes from a database.</span></span> <span data-ttu-id="720fe-110">Ziyaret [ASP.NET MVC öğrenme Merkezi](../../../index.md) diğer ASP.NET MVC öğreticiler ve örnekleri bulunamadı.</span><span class="sxs-lookup"><span data-stu-id="720fe-110">Visit the [ASP.NET MVC learning center](../../../index.md) to find other ASP.NET MVC tutorials and samples.</span></span>


<span data-ttu-id="720fe-111">MVC Model, görünüm, denetleyici anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="720fe-111">MVC stands for Model, View, Controller.</span></span> <span data-ttu-id="720fe-112">MVC birbirinden farklı bir sorumluluk her bölümü sahip olacağı şekilde uygulamaları geliştirmek için bir desen ' dir.</span><span class="sxs-lookup"><span data-stu-id="720fe-112">MVC is a pattern for developing applications such that each part has a responsibility that is different from another.</span></span>

- <span data-ttu-id="720fe-113">Modeli: Uygulamanızın veri</span><span class="sxs-lookup"><span data-stu-id="720fe-113">Model: The data of your application</span></span>
- <span data-ttu-id="720fe-114">Görünümleri: Dinamik olarak HTML yanıtları oluşturmak için uygulamanızın şablon dosyalarını kullanır.</span><span class="sxs-lookup"><span data-stu-id="720fe-114">Views: The template files your application will use to dynamically generate HTML responses.</span></span>
- <span data-ttu-id="720fe-115">Denetleyicileri: uygulama gelen URL isteklerini işleyen sınıflar model verileri almak ve istemcisine geri yanıt işleme görünüm şablonları belirtin</span><span class="sxs-lookup"><span data-stu-id="720fe-115">Controllers: Classes that handle incoming URL requests to the application, retrieve model data, and then specify view templates that render a response back to the client</span></span>

<span data-ttu-id="720fe-116">Biz, bu öğreticide, tüm bu kavramları kapsayan olması ve bunları bir uygulama oluşturmak için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="720fe-116">We'll be covering all these concepts in this tutorial and show you how to use them to build an application.</span></span>

<span data-ttu-id="720fe-117">Yeni bir denetleyicisi solution Explorer denetleyicileri klasörüne sağ tıklayıp denetleyici Ekle seçerek oluşturalım.</span><span class="sxs-lookup"><span data-stu-id="720fe-117">Let's create a new controller by right-clicking the controllers folder in the solution Explorer and selecting Add Controller.</span></span>

<span data-ttu-id="720fe-118">[![AddControllerRightClick](getting-started-with-mvc-part2/_static/image2.png)](getting-started-with-mvc-part2/_static/image1.png)</span><span class="sxs-lookup"><span data-stu-id="720fe-118">[![AddControllerRightClick](getting-started-with-mvc-part2/_static/image2.png)](getting-started-with-mvc-part2/_static/image1.png)</span></span>

<span data-ttu-id="720fe-119">Yeni denetleyicinize "HelloWorldController" olarak adlandırın ve Ekle'yi tıklatın.</span><span class="sxs-lookup"><span data-stu-id="720fe-119">Name your new controller "HelloWorldController" and click Add.</span></span>

<span data-ttu-id="720fe-120">[![Denetleyici Ekle iletişim kutusu](getting-started-with-mvc-part2/_static/image4.png)](getting-started-with-mvc-part2/_static/image3.png)</span><span class="sxs-lookup"><span data-stu-id="720fe-120">[![Add Controller Dialog](getting-started-with-mvc-part2/_static/image4.png)](getting-started-with-mvc-part2/_static/image3.png)</span></span>

<span data-ttu-id="720fe-121">Bildirim HelloWorldController.cs adlı sizin için yeni bir dosya oluşturuldu ve bu dosyayı şimdi açılır sağdaki Çözüm Gezgini'nde **IDE**.</span><span class="sxs-lookup"><span data-stu-id="720fe-121">Notice in the Solution Explorer on the right that a new file has been created for you called HelloWorldController.cs and that file is now opened in the **IDE**.</span></span>

<span data-ttu-id="720fe-122">[![HelloWorldControllerCode](getting-started-with-mvc-part2/_static/image6.png)](getting-started-with-mvc-part2/_static/image5.png)</span><span class="sxs-lookup"><span data-stu-id="720fe-122">[![HelloWorldControllerCode](getting-started-with-mvc-part2/_static/image6.png)](getting-started-with-mvc-part2/_static/image5.png)</span></span>

<span data-ttu-id="720fe-123">Yeni ortak sınıfının HelloWorldController içinde şuna iki yeni yöntemi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="720fe-123">Create two new methods that look like this inside of your new public class HelloWorldController.</span></span> <span data-ttu-id="720fe-124">Örnek olarak HTML dizesi doğrudan sunduğumuz denetleyicisinden getireceğiz.</span><span class="sxs-lookup"><span data-stu-id="720fe-124">We'll return a string of HTML directly from our controller as an example.</span></span>

[!code-csharp[Main](getting-started-with-mvc-part2/samples/sample1.cs)]

<span data-ttu-id="720fe-125">Denetleyicinizi HelloWorldController adlandırılır ve yeni yönteminizi dizin adı verilir.</span><span class="sxs-lookup"><span data-stu-id="720fe-125">Your Controller is named HelloWorldController and your new Method is called Index.</span></span> <span data-ttu-id="720fe-126">Uygulamanızı yeniden çalıştırma yalnızca eskisi (Oynat düğmesini tıklatın veya bunu yapmak için F5 tuşuna basın).</span><span class="sxs-lookup"><span data-stu-id="720fe-126">Run your application again, just as before (click the play button or press F5 to do this).</span></span> <span data-ttu-id="720fe-127">Tarayıcınız başladıktan sonra Adres çubuğuna yolu değiştirmek `http://localhost:xx/HelloWorld` burada xx ne olursa olsun, bilgisayarınızın sayı seçilidir.</span><span class="sxs-lookup"><span data-stu-id="720fe-127">Once your browser has started up, change the path in the address bar to `http://localhost:xx/HelloWorld` where xx is whatever number your computer has chosen.</span></span> <span data-ttu-id="720fe-128">Tarayıcınız aşağıdaki ekran görüntüsüne görünmelidir.</span><span class="sxs-lookup"><span data-stu-id="720fe-128">Now your browser should look like the screenshot below.</span></span> <span data-ttu-id="720fe-129">Bizim yukarıdaki yönteminde size bir dize "İçerik" adlı bir yönteme geçirilen döndürdü.</span><span class="sxs-lookup"><span data-stu-id="720fe-129">In our method above we returned a string passed into a method called "Content."</span></span> <span data-ttu-id="720fe-130">Biz, sistem yalnızca bazı HTML döndürür ve olduğu söylediyse!</span><span class="sxs-lookup"><span data-stu-id="720fe-130">We told the system just returns some HTML, and it did!</span></span>

<span data-ttu-id="720fe-131">ASP.NET MVC, gelen URL bağlı olarak farklı denetleyicisi sınıfları (ve bunların içindeki farklı eylem yöntemleri) çağırır.</span><span class="sxs-lookup"><span data-stu-id="720fe-131">ASP.NET MVC invokes different Controller classes (and different Action methods within them) depending on the incoming URL.</span></span> <span data-ttu-id="720fe-132">ASP.NET MVC tarafından kullanılan varsayılan eşleme mantığı hangi kod çalıştığını denetlemek için bu gibi bir biçim kullanır:</span><span class="sxs-lookup"><span data-stu-id="720fe-132">The default mapping logic used by ASP.NET MVC uses a format like this to control what code is run:</span></span>

<span data-ttu-id="720fe-133">/ [Denetleyicisi] / [EylemAdı] / [parametreler]</span><span class="sxs-lookup"><span data-stu-id="720fe-133">/[Controller]/[ActionName]/[Parameters]</span></span>

<span data-ttu-id="720fe-134">URL ilk bölümü yürütmek için denetleyici sınıfını belirler.</span><span class="sxs-lookup"><span data-stu-id="720fe-134">The first part of the URL determines the Controller class to execute.</span></span> <span data-ttu-id="720fe-135">Bu nedenle /HelloWorld HelloWorldController sınıfına eşler.</span><span class="sxs-lookup"><span data-stu-id="720fe-135">So /HelloWorld maps to the HelloWorldController class.</span></span> <span data-ttu-id="720fe-136">URL ikinci bölümü eylem yöntemine yürütmek için sınıf belirler.</span><span class="sxs-lookup"><span data-stu-id="720fe-136">The second part of the URL determines the Action method on the class to execute.</span></span> <span data-ttu-id="720fe-137">Bu nedenle /HelloWorld/Index yürütmek için HelloWorldcontroller sınıfının İNDİS() yöntemi neden olur.</span><span class="sxs-lookup"><span data-stu-id="720fe-137">So /HelloWorld/Index would cause the Index() method of the HelloWorldcontroller class to execute.</span></span> <span data-ttu-id="720fe-138">Biz yalnızca yukarıdaki /HelloWorld ve dizin kapsanan yöntemi ziyaret etmek olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="720fe-138">Notice that we only had to visit /HelloWorld above and the method Index was implied.</span></span> <span data-ttu-id="720fe-139">"Dizin" adlı bir yöntem bir açıkça belirtilmezse, bir denetleyicisinde çağrılacak varsayılan yöntemdir olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="720fe-139">This is because a method named "Index" is the default method that will be called on a controller if one is not explicitly specified.</span></span>

<span data-ttu-id="720fe-140">[![Bu my varsayılan değerdir](getting-started-with-mvc-part2/_static/image8.png)](getting-started-with-mvc-part2/_static/image7.png)</span><span class="sxs-lookup"><span data-stu-id="720fe-140">[![This is my default action](getting-started-with-mvc-part2/_static/image8.png)](getting-started-with-mvc-part2/_static/image7.png)</span></span>

<span data-ttu-id="720fe-141">Şimdi, şimdi ziyaret `http://localhost:xx/HelloWorld/Welcome.` artık bizim Hoş Geldiniz yöntemi yürütülen ve HTML dizesi döndürdü.</span><span class="sxs-lookup"><span data-stu-id="720fe-141">Now, let's visit `http://localhost:xx/HelloWorld/Welcome.` Now our Welcome Method has executed and returned its HTML string.</span></span>

<span data-ttu-id="720fe-142">Yeniden / [denetleyicisi] / [EylemAdı] / [denetleyicisidir HelloWorld Hoş Geldiniz yöntemi bu durumda böylelikle parametreler].</span><span class="sxs-lookup"><span data-stu-id="720fe-142">Again, /[Controller]/[ActionName]/[Parameters] so Controller is HelloWorld and Welcome is the Method in this case.</span></span> <span data-ttu-id="720fe-143">Biz parametreleri henüz yapmadınız.</span><span class="sxs-lookup"><span data-stu-id="720fe-143">We haven't done Parameters yet.</span></span>

<span data-ttu-id="720fe-144">[![Hoş Geldiniz eylem yöntem budur](getting-started-with-mvc-part2/_static/image10.png)](getting-started-with-mvc-part2/_static/image9.png)</span><span class="sxs-lookup"><span data-stu-id="720fe-144">[![This is the Welcome action method](getting-started-with-mvc-part2/_static/image10.png)](getting-started-with-mvc-part2/_static/image9.png)</span></span>

<span data-ttu-id="720fe-145">Böylece biz bazı bilgileri URL'den örneğin gibi bizim denetleyicisine geçirebilirsiniz bizim örnek biraz değiştirelim: / HelloWorld/Hoş Geldiniz? adı Scott =&amp;numtimes = 4.</span><span class="sxs-lookup"><span data-stu-id="720fe-145">Let's modify our sample slightly so that we can pass some information in from the URL to our controller, for example like this: /HelloWorld/Welcome?name=Scott&amp;numtimes=4.</span></span> <span data-ttu-id="720fe-146">Hoş Geldiniz yönteminizi iki parametre ve güncelleştirme gibi aşağıda içerecek şekilde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="720fe-146">Change your Welcome method to include two parameters and update it like below.</span></span> <span data-ttu-id="720fe-147">C# isteğe bağlı parametre özelliği geçirilen değil, parametre numTimes 1 varsayılan belirtmek için kullandığımız olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="720fe-147">Note that we've used the C# optional parameter feature to indicate that the parameter numTimes should default to 1 if it's not passed in.</span></span>

[!code-csharp[Main](getting-started-with-mvc-part2/samples/sample2.cs)]

<span data-ttu-id="720fe-148">Uygulamanızı çalıştırın ve ziyaret `http://localhost:xx/HelloWorld/Welcome?name=Scott&numtimes=4` dilediğiniz şekilde adı ve numtimes değerini değiştirme.</span><span class="sxs-lookup"><span data-stu-id="720fe-148">Run your application and visit `http://localhost:xx/HelloWorld/Welcome?name=Scott&numtimes=4` changing the value of name and numtimes as you like.</span></span> <span data-ttu-id="720fe-149">Sistem, sorgu dizesi adres çubuğundaki yönteminizi parametrelerinde adlandırılmış parametreleri otomatik olarak eşlenir.</span><span class="sxs-lookup"><span data-stu-id="720fe-149">The system automatically mapped the named parameters from your query string in the address bar to parameters in your method.</span></span>

<span data-ttu-id="720fe-150">Bu örneklerin her ikisi de denetleyicisi tüm çalışarak olmuştur ve HTML doğrudan döndürüyor.</span><span class="sxs-lookup"><span data-stu-id="720fe-150">In both these examples the controller has been doing all the work, and has been returning HTML directly.</span></span> <span data-ttu-id="720fe-151">Normalde biz bizim denetleyicileri istemediğiniz kodu oldukça zahmetli olan bitip beri HTML doğrudan - döndürüyor.</span><span class="sxs-lookup"><span data-stu-id="720fe-151">Ordinarily we don't want our Controllers returning HTML directly - since that ends up being very cumbersome to code.</span></span> <span data-ttu-id="720fe-152">Bunun yerine genellikle ayrı bir görünüm şablon dosyası HTML yanıtı oluşturmak yardımcı olmak için kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="720fe-152">Instead we'll typically use a separate View template file to help generate the HTML response.</span></span> <span data-ttu-id="720fe-153">Nasıl bunu yapabiliriz konumundaki bakalım.</span><span class="sxs-lookup"><span data-stu-id="720fe-153">Let's look at how we can do this.</span></span> <span data-ttu-id="720fe-154">Tarayıcınızı kapatın ve IDE döndürür.</span><span class="sxs-lookup"><span data-stu-id="720fe-154">Close your browser and return to the IDE.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="720fe-155">[Önceki](getting-started-with-mvc-part1.md)
[sonraki](getting-started-with-mvc-part3.md)</span><span class="sxs-lookup"><span data-stu-id="720fe-155">[Previous](getting-started-with-mvc-part1.md)
[Next](getting-started-with-mvc-part3.md)</span></span>