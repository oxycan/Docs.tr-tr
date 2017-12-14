---
uid: mvc/overview/older-versions/getting-started-with-aspnet-mvc3/cs/adding-a-controller
title: Bir denetleyici (C#) ekleme | Microsoft Docs
author: Rick-Anderson
description: "Bu öğretici Microsoft Visual Web Developer 2010 Express Serivice Pack 1, hangi i kullanarak bir ASP.NET MVC Web uygulaması oluşturmanın temellerini öğretmek..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 01/12/2011
ms.topic: article
ms.assetid: 0b8c56b5-fdf3-42dd-a866-98fbe0ab78a0
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/older-versions/getting-started-with-aspnet-mvc3/cs/adding-a-controller
msc.type: authoredcontent
ms.openlocfilehash: 77bfc8f3778dcf75453c216579e50a016b1ac971
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="adding-a-controller-c"></a><span data-ttu-id="527e2-103">Bir denetleyici (C#) ekleme</span><span class="sxs-lookup"><span data-stu-id="527e2-103">Adding a Controller (C#)</span></span>
====================
<span data-ttu-id="527e2-104">Tarafından [Rick Anderson](https://github.com/Rick-Anderson)</span><span class="sxs-lookup"><span data-stu-id="527e2-104">by [Rick Anderson](https://github.com/Rick-Anderson)</span></span>

> > [!NOTE]
> > <span data-ttu-id="527e2-105">Bu öğretici güncelleştirilmiş bir sürümü kullanılabilir [burada](../../../getting-started/introduction/getting-started.md) ASP.NET MVC 5 ve Visual Studio 2013'ü kullanır.</span><span class="sxs-lookup"><span data-stu-id="527e2-105">An updated version of this tutorial is available [here](../../../getting-started/introduction/getting-started.md) that uses ASP.NET MVC 5 and Visual Studio 2013.</span></span> <span data-ttu-id="527e2-106">Daha güvenli, izlemek çok daha kolaydır ve daha fazla özelliklerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="527e2-106">It's more secure, much simpler to follow and demonstrates more features.</span></span>
> 
> 
> <span data-ttu-id="527e2-107">Bu öğretici Microsoft Visual Web Developer 2010 Express Service Pack ücretsiz Microsoft Visual Studio sürümünü olan 1, kullanarak bir ASP.NET MVC Web uygulaması oluşturmanın temellerini öğretmek.</span><span class="sxs-lookup"><span data-stu-id="527e2-107">This tutorial will teach you the basics of building an ASP.NET MVC Web application using Microsoft Visual Web Developer 2010 Express Service Pack 1, which is a free version of Microsoft Visual Studio.</span></span> <span data-ttu-id="527e2-108">Başlamadan önce aşağıda listelenen önkoşulları kurduğunuzdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="527e2-108">Before you start, make sure you've installed the prerequisites listed below.</span></span> <span data-ttu-id="527e2-109">Bunların tümünün aşağıdaki bağlantıyı tıklatarak yükleyin: [Web Platformu yükleyicisi](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack).</span><span class="sxs-lookup"><span data-stu-id="527e2-109">You can install all of them by clicking the following link: [Web Platform Installer](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack).</span></span> <span data-ttu-id="527e2-110">Alternatif olarak, aşağıdaki bağlantıları kullanarak önkoşulları ayrı ayrı yükleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="527e2-110">Alternatively, you can individually install the prerequisites using the following links:</span></span>
> 
> - [<span data-ttu-id="527e2-111">Visual Studio Web Developer Express SP1 önkoşulları</span><span class="sxs-lookup"><span data-stu-id="527e2-111">Visual Studio Web Developer Express SP1 prerequisites</span></span>](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack)
> - [<span data-ttu-id="527e2-112">ASP.NET MVC 3 araçları güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="527e2-112">ASP.NET MVC 3 Tools Update</span></span>](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=MVC3)
> - <span data-ttu-id="527e2-113">[SQL Server Compact 4.0](https://www.microsoft.com/web/gallery/install.aspx?appid=SQLCE;SQLCEVSTools_4_0)(çalışma zamanı + araçları destekler)</span><span class="sxs-lookup"><span data-stu-id="527e2-113">[SQL Server Compact 4.0](https://www.microsoft.com/web/gallery/install.aspx?appid=SQLCE;SQLCEVSTools_4_0)(runtime + tools support)</span></span>
> 
> <span data-ttu-id="527e2-114">Visual Web Developer 2010 yerine Visual Studio 2010 kullanıyorsanız, aşağıdaki bağlantıyı tıklatarak önkoşulları yükleyin: [Visual Studio 2010 önkoşulları](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=VS2010SP1Pack).</span><span class="sxs-lookup"><span data-stu-id="527e2-114">If you're using Visual Studio 2010 instead of Visual Web Developer 2010, install the prerequisites by clicking the following link: [Visual Studio 2010 prerequisites](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=VS2010SP1Pack).</span></span>
> 
> <span data-ttu-id="527e2-115">C# kaynak kodu ile Visual Web Developer projesi bu konuya eşlik etmek kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="527e2-115">A Visual Web Developer project with C# source code is available to accompany this topic.</span></span> <span data-ttu-id="527e2-116">[C# sürümü](https://code.msdn.microsoft.com/Introduction-to-MVC-3-10d1b098).</span><span class="sxs-lookup"><span data-stu-id="527e2-116">[Download the C# version](https://code.msdn.microsoft.com/Introduction-to-MVC-3-10d1b098).</span></span> <span data-ttu-id="527e2-117">Visual Basic tercih ederseniz, geçiş [Visual Basic sürüm](../vb/intro-to-aspnet-mvc-3.md) Bu öğreticinin.</span><span class="sxs-lookup"><span data-stu-id="527e2-117">If you prefer Visual Basic, switch to the [Visual Basic version](../vb/intro-to-aspnet-mvc-3.md) of this tutorial.</span></span>


<span data-ttu-id="527e2-118">MVC anlamına gelir *model-view-controller*.</span><span class="sxs-lookup"><span data-stu-id="527e2-118">MVC stands for *model-view-controller*.</span></span> <span data-ttu-id="527e2-119">MVC, iyi tasarlanmış ve bakımını kolay uygulamaları geliştirmek için bir desen olur.</span><span class="sxs-lookup"><span data-stu-id="527e2-119">MVC is a pattern for developing applications that are well architected and easy to maintain.</span></span> <span data-ttu-id="527e2-120">MVC tabanlı uygulamalar içerir:</span><span class="sxs-lookup"><span data-stu-id="527e2-120">MVC-based applications contain:</span></span>

- <span data-ttu-id="527e2-121">Denetleyicileri: uygulamaya gelen istekleri işleyen sınıflar model verileri alabilir ve istemciye bir yanıt döndürür görünüm şablonları belirtin.</span><span class="sxs-lookup"><span data-stu-id="527e2-121">Controllers: Classes that handle incoming requests to the application, retrieve model data, and then specify view templates that return a response to the client.</span></span>
- <span data-ttu-id="527e2-122">Modelleri: uygulama verilerini temsil eden ve bu verilere iş kurallarını zorunlu tutmak için doğrulama mantığını kullanan sınıflar.</span><span class="sxs-lookup"><span data-stu-id="527e2-122">Models: Classes that represent the data of the application and that use validation logic to enforce business rules for that data.</span></span>
- <span data-ttu-id="527e2-123">Görünümleri: dinamik olarak HTML yanıtları oluşturmak için uygulamanızın kullandığı şablon dosyalarını.</span><span class="sxs-lookup"><span data-stu-id="527e2-123">Views: Template files that your application uses to dynamically generate HTML responses.</span></span>

<span data-ttu-id="527e2-124">Biz, Bu öğretici serisinde, tüm bu kavramları kapsayan olması ve bunları bir uygulama oluşturmak için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="527e2-124">We'll be covering all these concepts in this tutorial series and show you how to use them to build an application.</span></span>

<span data-ttu-id="527e2-125">Denetleyici sınıfı oluşturarak başlayalım.</span><span class="sxs-lookup"><span data-stu-id="527e2-125">Let's begin by creating a controller class.</span></span> <span data-ttu-id="527e2-126">İçinde **Çözüm Gezgini**, sağ *denetleyicileri* klasörünü ve ardından **denetleyici Ekle**.</span><span class="sxs-lookup"><span data-stu-id="527e2-126">In **Solution Explorer**, right-click the *Controllers* folder and then select **Add Controller**.</span></span>

[![](adding-a-controller/_static/image2.png)](adding-a-controller/_static/image1.png)

<span data-ttu-id="527e2-127">Yeni denetleyicinize "HelloWorldController" olarak adlandırın.</span><span class="sxs-lookup"><span data-stu-id="527e2-127">Name your new controller "HelloWorldController".</span></span> <span data-ttu-id="527e2-128">Varsayılan şablon olarak bırakın **boş denetleyicisi** tıklatıp **Ekle**.</span><span class="sxs-lookup"><span data-stu-id="527e2-128">Leave the default template as **Empty controller** and click **Add**.</span></span>

<span data-ttu-id="527e2-129">[![AddHelloWorldController](adding-a-controller/_static/image4.png)](adding-a-controller/_static/image3.png)</span><span class="sxs-lookup"><span data-stu-id="527e2-129">[![AddHelloWorldController](adding-a-controller/_static/image4.png)](adding-a-controller/_static/image3.png)</span></span>

<span data-ttu-id="527e2-130">Fark **Çözüm Gezgini** yeni bir dosya adlandırılmış oluşturulduğunu *HelloWorldController.cs*.</span><span class="sxs-lookup"><span data-stu-id="527e2-130">Notice in **Solution Explorer** that a new file has been created named *HelloWorldController.cs*.</span></span> <span data-ttu-id="527e2-131">Dosya IDE içinde açılmış durumda.</span><span class="sxs-lookup"><span data-stu-id="527e2-131">The file is open in the IDE.</span></span>

![](adding-a-controller/_static/image5.png)

<span data-ttu-id="527e2-132">İçinde `public class HelloWorldController` engellemek, aşağıdaki kod gibi görünen iki yöntem oluşturun.</span><span class="sxs-lookup"><span data-stu-id="527e2-132">Inside the `public class HelloWorldController` block, create two methods that look like the following code.</span></span> <span data-ttu-id="527e2-133">Denetleyici örneği olarak HTML dizesi döndürür.</span><span class="sxs-lookup"><span data-stu-id="527e2-133">The controller will return a string of HTML as an example.</span></span>

[!code-csharp[Main](adding-a-controller/samples/sample1.cs)]

<span data-ttu-id="527e2-134">Denetleyicinizi adlı `HelloWorldController` ve yukarıdaki ilk yöntem adlı `Index`.</span><span class="sxs-lookup"><span data-stu-id="527e2-134">Your controller is named `HelloWorldController` and the first method above is named `Index`.</span></span> <span data-ttu-id="527e2-135">Şimdi bir tarayıcıdan çağırır.</span><span class="sxs-lookup"><span data-stu-id="527e2-135">Let's invoke it from a browser.</span></span> <span data-ttu-id="527e2-136">Uygulama (F5 veya Ctrl + F5'e basın) çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="527e2-136">Run the application (press F5 or Ctrl+F5).</span></span> <span data-ttu-id="527e2-137">Tarayıcıda, yolun adres çubuğundaki "HelloWorld" ekleyin.</span><span class="sxs-lookup"><span data-stu-id="527e2-137">In the browser, append "HelloWorld" to the path in the address bar.</span></span> <span data-ttu-id="527e2-138">(Örneğin, aşağıdaki, çizimdeki `http://localhost:43246/HelloWorld.`) sayfasını tarayıcıda aşağıdaki ekran görüntüsüne benzeyen arar.</span><span class="sxs-lookup"><span data-stu-id="527e2-138">(For example, in the illustration below, it's `http://localhost:43246/HelloWorld.`) The page in the browser will look like the following screenshot.</span></span> <span data-ttu-id="527e2-139">Yukarıdaki yöntemi kodu doğrudan bir dize döndürdü.</span><span class="sxs-lookup"><span data-stu-id="527e2-139">In the method above, the code returned a string directly.</span></span> <span data-ttu-id="527e2-140">Yalnızca bazı HTML döndürmek için sistem söylediyse ve olduğu!</span><span class="sxs-lookup"><span data-stu-id="527e2-140">You told the system to just return some HTML, and it did!</span></span>

![](adding-a-controller/_static/image6.png)

<span data-ttu-id="527e2-141">ASP.NET MVC, gelen URL bağlı olarak farklı bir denetleyici sınıfları (ve bunların içindeki farklı eylem yöntemleri) çağırır.</span><span class="sxs-lookup"><span data-stu-id="527e2-141">ASP.NET MVC invokes different controller classes (and different action methods within them) depending on the incoming URL.</span></span> <span data-ttu-id="527e2-142">ASP.NET MVC tarafından kullanılan varsayılan eşleme mantığını çağırmak için kodu nedir belirlemek için bu gibi bir biçim kullanır:</span><span class="sxs-lookup"><span data-stu-id="527e2-142">The default mapping logic used by ASP.NET MVC uses a format like this to determine what code to invoke:</span></span>

`/[Controller]/[ActionName]/[Parameters]`

<span data-ttu-id="527e2-143">URL ilk bölümü yürütmek için denetleyici sınıfını belirler.</span><span class="sxs-lookup"><span data-stu-id="527e2-143">The first part of the URL determines the controller class to execute.</span></span> <span data-ttu-id="527e2-144">Bu nedenle */HelloWorld* eşlendiği `HelloWorldController` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="527e2-144">So */HelloWorld* maps to the `HelloWorldController` class.</span></span> <span data-ttu-id="527e2-145">URL ikinci bölümü eylem yöntemine yürütmek için sınıf belirler.</span><span class="sxs-lookup"><span data-stu-id="527e2-145">The second part of the URL determines the action method on the class to execute.</span></span> <span data-ttu-id="527e2-146">Bu nedenle */HelloWorld/dizin* neden olacağından `Index` yöntemi `HelloWorldController` yürütmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="527e2-146">So */HelloWorld/Index* would cause the `Index` method of the `HelloWorldController` class to execute.</span></span> <span data-ttu-id="527e2-147">Biz yalnızca Gözat gerekiyordu bildirimi */HelloWorld* ve `Index` yöntemi, varsayılan olarak kullanıldı.</span><span class="sxs-lookup"><span data-stu-id="527e2-147">Notice that we only had to browse to */HelloWorld* and the `Index` method was used by default.</span></span> <span data-ttu-id="527e2-148">Bir yöntem adlı olmasıdır `Index` bir açıkça belirtilmezse, bir denetleyicisinde çağrılacak varsayılan yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="527e2-148">This is because a method named `Index` is the default method that will be called on a controller if one is not explicitly specified.</span></span>

<span data-ttu-id="527e2-149">Gözat `http://localhost:xxxx/HelloWorld/Welcome`.</span><span class="sxs-lookup"><span data-stu-id="527e2-149">Browse to `http://localhost:xxxx/HelloWorld/Welcome`.</span></span> <span data-ttu-id="527e2-150">`Welcome` Yöntemi çalışır ve "... Hoş Geldiniz eylem yöntemi olduğu" dizesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="527e2-150">The `Welcome` method runs and returns the string "This is the Welcome action method...".</span></span> <span data-ttu-id="527e2-151">Varsayılan MVC eşlemesi `/[Controller]/[ActionName]/[Parameters]`.</span><span class="sxs-lookup"><span data-stu-id="527e2-151">The default MVC mapping is `/[Controller]/[ActionName]/[Parameters]`.</span></span> <span data-ttu-id="527e2-152">Bu URL için denetleyicisidir `HelloWorld` ve `Welcome` eylem yöntemidir.</span><span class="sxs-lookup"><span data-stu-id="527e2-152">For this URL, the controller is `HelloWorld` and `Welcome` is the action method.</span></span> <span data-ttu-id="527e2-153">Kullandığınız parolalardan `[Parameters]` URL henüz parçası.</span><span class="sxs-lookup"><span data-stu-id="527e2-153">You haven't used the `[Parameters]` part of the URL yet.</span></span>

![](adding-a-controller/_static/image7.png)

<span data-ttu-id="527e2-154">Böylece denetleyiciye URL'den bazı parametre bilgilerini geçirebilirsiniz örnek biraz değiştirelim (örneğin, */HelloWorld/Hoş Geldiniz? adı Scott =&amp;numtimes = 4*).</span><span class="sxs-lookup"><span data-stu-id="527e2-154">Let's modify the example slightly so that you can pass some parameter information from the URL to the controller (for example, */HelloWorld/Welcome?name=Scott&amp;numtimes=4*).</span></span> <span data-ttu-id="527e2-155">Değişiklik, `Welcome` yöntemi iki parametre aşağıda gösterildiği gibi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="527e2-155">Change your `Welcome` method to include two parameters as shown below.</span></span> <span data-ttu-id="527e2-156">Kod belirtmek için C# isteğe bağlı parametre özelliği kullandığına dikkat edin `numTimes` Bu parametre için değer iletilmezse, parametresi 1 olarak varsayılan.</span><span class="sxs-lookup"><span data-stu-id="527e2-156">Note that the code uses the C# optional-parameter feature to indicate that the `numTimes` parameter should default to 1 if no value is passed for that parameter.</span></span>

[!code-csharp[Main](adding-a-controller/samples/sample2.cs)]

<span data-ttu-id="527e2-157">Uygulamanızı çalıştırın ve örnek URL'sine gidin (`http://localhost:xxxx/HelloWorld/Welcome?name=Scott&numtimes=4)`.</span><span class="sxs-lookup"><span data-stu-id="527e2-157">Run your application and browse to the example URL (`http://localhost:xxxx/HelloWorld/Welcome?name=Scott&numtimes=4)`.</span></span> <span data-ttu-id="527e2-158">İçin farklı değerler deneyin `name` ve `numtimes` URL.</span><span class="sxs-lookup"><span data-stu-id="527e2-158">You can try different values for `name` and `numtimes` in the URL.</span></span> <span data-ttu-id="527e2-159">Sistem otomatik olarak sorgu dizesi adres çubuğundaki yönteminizi parametrelerinde adlandırılmış parametreleri eşler.</span><span class="sxs-lookup"><span data-stu-id="527e2-159">The system automatically maps the named parameters from the query string in the address bar to parameters in your method.</span></span>

![](adding-a-controller/_static/image8.png)

<span data-ttu-id="527e2-160">MVC "VC" bölümünü yapılması edilmiş hem de bu örneklerde denetleyicisi — diğer bir deyişle, Görünüm ve denetleyici çalışma.</span><span class="sxs-lookup"><span data-stu-id="527e2-160">In both these examples the controller has been doing the "VC" portion of MVC — that is, the view and controller work.</span></span> <span data-ttu-id="527e2-161">Denetleyici HTML doğrudan döndürüyor.</span><span class="sxs-lookup"><span data-stu-id="527e2-161">The controller is returning HTML directly.</span></span> <span data-ttu-id="527e2-162">Normalde kodu çok kullanışsız hale beri HTML doğrudan döndürerek denetleyicileri istemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="527e2-162">Ordinarily you don't want controllers returning HTML directly, since that becomes very cumbersome to code.</span></span> <span data-ttu-id="527e2-163">Bunun yerine genellikle ayrı görünüm şablon dosyası HTML yanıtı oluşturmak yardımcı olmak için kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="527e2-163">Instead we'll typically use a separate view template file to help generate the HTML response.</span></span> <span data-ttu-id="527e2-164">Nasıl biz bunu yapmak için sonraki olarak bakalım.</span><span class="sxs-lookup"><span data-stu-id="527e2-164">Let's look next at how we can do this.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="527e2-165">[Önceki](intro-to-aspnet-mvc-3.md)
[sonraki](adding-a-view.md)</span><span class="sxs-lookup"><span data-stu-id="527e2-165">[Previous](intro-to-aspnet-mvc-3.md)
[Next](adding-a-view.md)</span></span>