---
uid: aspnet/mvc/overview/older-versions-1/views/creating-custom-html-helpers-cs
title: "Özel HTML Yardımcıları (C#) oluşturma | Microsoft Docs"
author: microsoft
description: "Bu öğreticinin amacı, MVC görünümlerinizde içinde kullanabileceğiniz özel HTML Yardımcıları nasıl oluşturabileceğinizi göstermektir. HTML Yardımcısı yararlanarak..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 10/07/2008
ms.topic: article
ms.assetid: e454c67d-a86e-4119-a858-eb04bbec2dff
ms.technology: dotnet-mvc
ms.prod: .net-framework
msc.legacyurl: /mvc/overview/older-versions-1/views/creating-custom-html-helpers-cs
msc.type: authoredcontent
ms.openlocfilehash: a0b6d67eb7aab51ba2b422fab0788e34255f2c8c
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="creating-custom-html-helpers-c"></a><span data-ttu-id="f8b65-104">Oluşturma özel HTML Yardımcıları (C#)</span><span class="sxs-lookup"><span data-stu-id="f8b65-104">Creating Custom HTML Helpers (C#)</span></span>
====================
<span data-ttu-id="f8b65-105">tarafından [Microsoft](https://github.com/microsoft)</span><span class="sxs-lookup"><span data-stu-id="f8b65-105">by [Microsoft](https://github.com/microsoft)</span></span>

[<span data-ttu-id="f8b65-106">PDF indirin</span><span class="sxs-lookup"><span data-stu-id="f8b65-106">Download PDF</span></span>](http://download.microsoft.com/download/1/1/f/11f721aa-d749-4ed7-bb89-a681b68894e6/ASPNET_MVC_Tutorial_9_CS.pdf)

> <span data-ttu-id="f8b65-107">Bu öğreticinin amacı, MVC görünümlerinizde içinde kullanabileceğiniz özel HTML Yardımcıları nasıl oluşturabileceğinizi göstermektir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-107">The goal of this tutorial is to demonstrate how you can create custom HTML Helpers that you can use within your MVC views.</span></span> <span data-ttu-id="f8b65-108">HTML Yardımcıları yararlanarak, can sıkıcı bir standart HTML sayfası oluşturmak için gerçekleştirmeniz gereken HTML etiketleri yazarak miktarını azaltabilir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-108">By taking advantage of HTML Helpers, you can reduce the amount of tedious typing of HTML tags that you must perform to create a standard HTML page.</span></span>


<span data-ttu-id="f8b65-109">Bu öğreticinin amacı, MVC görünümlerinizde içinde kullanabileceğiniz özel HTML Yardımcıları nasıl oluşturabileceğinizi göstermektir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-109">The goal of this tutorial is to demonstrate how you can create custom HTML Helpers that you can use within your MVC views.</span></span> <span data-ttu-id="f8b65-110">HTML Yardımcıları yararlanarak, can sıkıcı bir standart HTML sayfası oluşturmak için gerçekleştirmeniz gereken HTML etiketleri yazarak miktarını azaltabilir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-110">By taking advantage of HTML Helpers, you can reduce the amount of tedious typing of HTML tags that you must perform to create a standard HTML page.</span></span>

<span data-ttu-id="f8b65-111">Bu öğreticinin ilk bölümü ı ASP.NET MVC çerçevesiyle dahil olan HTML Yardımcıları bazıları açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="f8b65-111">In the first part of this tutorial, I describe some of the existing HTML Helpers included with the ASP.NET MVC framework.</span></span> <span data-ttu-id="f8b65-112">Ardından, t özel HTML Yardımcıları oluşturmak için iki yöntem açıklanmaktadır: özel HTML Yardımcıları bir statik yöntem oluşturarak ve bir genişletme yöntemi oluşturarak nasıl oluşturulacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="f8b65-112">Next, I describe two methods of creating custom HTML Helpers: I explain how to create custom HTML Helpers by creating a static method and by creating an extension method.</span></span>

## <a name="understanding-html-helpers"></a><span data-ttu-id="f8b65-113">HTML Yardımcıları anlama</span><span class="sxs-lookup"><span data-stu-id="f8b65-113">Understanding HTML Helpers</span></span>

<span data-ttu-id="f8b65-114">Bir HTML Yardımcısı dizesi döndüren yalnızca bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-114">An HTML Helper is just a method that returns a string.</span></span> <span data-ttu-id="f8b65-115">Dize istediğiniz içerik herhangi bir türde temsil edebilir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-115">The string can represent any type of content that you want.</span></span> <span data-ttu-id="f8b65-116">Örneğin, HTML gibi standart HTML etiketlerini işlemek için bir HTML Yardımcıları kullanabilirsiniz `<input>` ve `<img>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="f8b65-116">For example, you can use HTML Helpers to render standard HTML tags like HTML `<input>` and `<img>` tags.</span></span> <span data-ttu-id="f8b65-117">HTML Yardımcıları sekmesini Şerit veya veritabanı verilerinin bir HTML tablosu gibi daha karmaşık içerik işlemek için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f8b65-117">You also can use HTML Helpers to render more complex content such as a tab strip or an HTML table of database data.</span></span>

<span data-ttu-id="f8b65-118">ASP.NET MVC çerçevesi aşağıdaki standart HTML Yardımcıları (Bu tam bir listesi değildir) kümesini içerir:</span><span class="sxs-lookup"><span data-stu-id="f8b65-118">The ASP.NET MVC framework includes the following set of standard HTML Helpers (this is not a complete list):</span></span>

- <span data-ttu-id="f8b65-119">Html.ActionLink()</span><span class="sxs-lookup"><span data-stu-id="f8b65-119">Html.ActionLink()</span></span>
- <span data-ttu-id="f8b65-120">Html.BeginForm()</span><span class="sxs-lookup"><span data-stu-id="f8b65-120">Html.BeginForm()</span></span>
- <span data-ttu-id="f8b65-121">Html.CheckBox()</span><span class="sxs-lookup"><span data-stu-id="f8b65-121">Html.CheckBox()</span></span>
- <span data-ttu-id="f8b65-122">Html.DropDownList()</span><span class="sxs-lookup"><span data-stu-id="f8b65-122">Html.DropDownList()</span></span>
- <span data-ttu-id="f8b65-123">Html.EndForm()</span><span class="sxs-lookup"><span data-stu-id="f8b65-123">Html.EndForm()</span></span>
- <span data-ttu-id="f8b65-124">Html.Hidden()</span><span class="sxs-lookup"><span data-stu-id="f8b65-124">Html.Hidden()</span></span>
- <span data-ttu-id="f8b65-125">Html.ListBox()</span><span class="sxs-lookup"><span data-stu-id="f8b65-125">Html.ListBox()</span></span>
- <span data-ttu-id="f8b65-126">Html.Password()</span><span class="sxs-lookup"><span data-stu-id="f8b65-126">Html.Password()</span></span>
- <span data-ttu-id="f8b65-127">Html.RadioButton()</span><span class="sxs-lookup"><span data-stu-id="f8b65-127">Html.RadioButton()</span></span>
- <span data-ttu-id="f8b65-128">Html.TextArea()</span><span class="sxs-lookup"><span data-stu-id="f8b65-128">Html.TextArea()</span></span>
- <span data-ttu-id="f8b65-129">Html.TextBox()</span><span class="sxs-lookup"><span data-stu-id="f8b65-129">Html.TextBox()</span></span>

<span data-ttu-id="f8b65-130">Örneğin, 1 listeleme formunda göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="f8b65-130">For example, consider the form in Listing 1.</span></span> <span data-ttu-id="f8b65-131">Bu form Yardımı iki standart HTML Yardımcıları (bkz. Şekil 1 ') ile işlenir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-131">This form is rendered with the help of two of the standard HTML Helpers (see Figure 1).</span></span> <span data-ttu-id="f8b65-132">Bu form kullanır `Html.BeginForm()` ve `Html.TextBox()` basit bir HTML form işlemek için yardımcı yöntemler.</span><span class="sxs-lookup"><span data-stu-id="f8b65-132">This form uses the `Html.BeginForm()` and `Html.TextBox()` Helper methods to render a simple HTML form.</span></span>


<span data-ttu-id="f8b65-133">[![Sayfanın HTML Yardımcıları ile çizilir](creating-custom-html-helpers-cs/_static/image2.png)](creating-custom-html-helpers-cs/_static/image1.png)</span><span class="sxs-lookup"><span data-stu-id="f8b65-133">[![Page rendered with HTML Helpers](creating-custom-html-helpers-cs/_static/image2.png)](creating-custom-html-helpers-cs/_static/image1.png)</span></span>

<span data-ttu-id="f8b65-134">**Şekil 01**: sayfa işlenen HTML Yardımcıları ile ([tam boyutlu görüntüyü görüntülemek için tıklatın](creating-custom-html-helpers-cs/_static/image3.png))</span><span class="sxs-lookup"><span data-stu-id="f8b65-134">**Figure 01**: Page rendered with HTML Helpers ([Click to view full-size image](creating-custom-html-helpers-cs/_static/image3.png))</span></span>


<span data-ttu-id="f8b65-135">**Kod 1 –`Views\Home\Index.aspx`**</span><span class="sxs-lookup"><span data-stu-id="f8b65-135">**Listing 1 – `Views\Home\Index.aspx`**</span></span>

[!code-aspx[Main](creating-custom-html-helpers-cs/samples/sample1.aspx)]

<span data-ttu-id="f8b65-136">Açma ve kapatma HTML oluşturmak için kullanılan Html.BeginForm() yardımcı yöntem `<form>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="f8b65-136">The Html.BeginForm() Helper method is used to create the opening and closing HTML `<form>` tags.</span></span> <span data-ttu-id="f8b65-137">Dikkat `Html.BeginForm()` yöntemi kullanarak bir içinde çağrılır deyimi.</span><span class="sxs-lookup"><span data-stu-id="f8b65-137">Notice that the `Html.BeginForm()` method is called within a using statement.</span></span> <span data-ttu-id="f8b65-138">Sağlar deyimiyle `<form>` etiketi kullanarak sonunda kapalı bloğu.</span><span class="sxs-lookup"><span data-stu-id="f8b65-138">The using statement ensures that the `<form>` tag gets closed at the end of the using block.</span></span>

<span data-ttu-id="f8b65-139">Kullanarak bir oluşturmak yerine tercih ederseniz bloğu kapatmak için Html.EndForm() yardımcı yöntemini çağırabilir `<form>` etiketi.</span><span class="sxs-lookup"><span data-stu-id="f8b65-139">If you prefer, instead of creating a using block, you can call the Html.EndForm() Helper method to close the `<form>` tag.</span></span> <span data-ttu-id="f8b65-140">Bir açma oluşturma ve kapatma için yaklaşımı kullanmak `<form>` size en sezgisel görünen etiket.</span><span class="sxs-lookup"><span data-stu-id="f8b65-140">Use whichever approach to creating an opening and closing `<form>` tag that seems most intuitive to you.</span></span>

<span data-ttu-id="f8b65-141">`Html.TextBox()` Yardımcı yöntemler listeleme 1'de HTML oluşturmak için kullanılan `<input>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="f8b65-141">The `Html.TextBox()` Helper methods are used in Listing 1 to render HTML `<input>` tags.</span></span> <span data-ttu-id="f8b65-142">Tarayıcınızda kaynağı görüntüle seçeneğini belirlerseniz, listeleme 2 HTML kaynağında görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="f8b65-142">If you select view source in your browser then you see the HTML source in Listing 2.</span></span> <span data-ttu-id="f8b65-143">Kaynak standart HTML etiketleri içerdiğine dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="f8b65-143">Notice that the source contains standard HTML tags.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8b65-144">dikkat `Html.TextBox()`-HTML Yardımcısı ile işlenir `<%= %>` yerine etiketler `<% %>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="f8b65-144">notice that the `Html.TextBox()`-HTML Helper is rendered with `<%= %>` tags instead of `<% %>` tags.</span></span> <span data-ttu-id="f8b65-145">Sonra eşittir işareti eklemezseniz, hiçbir şey tarayıcıda görüntülenen.</span><span class="sxs-lookup"><span data-stu-id="f8b65-145">If you don't include the equal sign, then nothing gets rendered to the browser.</span></span>

<span data-ttu-id="f8b65-146">ASP.NET MVC çerçevesi Yardımcıları, küçük bir kümesini içerir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-146">The ASP.NET MVC framework contains a small set of helpers.</span></span> <span data-ttu-id="f8b65-147">Büyük olasılıkla, MVC çerçevesi özel HTML Yardımcıları ile genişletmek gerekir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-147">Most likely, you will need to extend the MVC framework with custom HTML Helpers.</span></span> <span data-ttu-id="f8b65-148">Bu öğreticinin geri kalanında içinde özel HTML Yardımcıları oluşturma iki yöntemleri öğrenin.</span><span class="sxs-lookup"><span data-stu-id="f8b65-148">In the remainder of this tutorial, you learn two methods of creating custom HTML Helpers.</span></span>

<span data-ttu-id="f8b65-149">**Kod 2 –`Index.aspx Source`**</span><span class="sxs-lookup"><span data-stu-id="f8b65-149">**Listing 2 – `Index.aspx Source`**</span></span>

[!code-aspx[Main](creating-custom-html-helpers-cs/samples/sample2.aspx)]

### <a name="creating-html-helpers-with-static-methods"></a><span data-ttu-id="f8b65-150">HTML Yardımcıları statik yöntemleriyle oluşturma</span><span class="sxs-lookup"><span data-stu-id="f8b65-150">Creating HTML Helpers with Static Methods</span></span>

<span data-ttu-id="f8b65-151">Yeni bir HTML Yardımcısı oluşturmanın en kolay yolu, bir dize döndürür bir statik yöntem oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="f8b65-151">The easiest way to create a new HTML Helper is to create a static method that returns a string.</span></span> <span data-ttu-id="f8b65-152">Örneğin, bir HTML işleyen yeni bir HTML Yardımcısı oluşturmaya karar düşünün `<label>` etiketi.</span><span class="sxs-lookup"><span data-stu-id="f8b65-152">Imagine, for example, that you decide to create a new HTML Helper that renders an HTML `<label>` tag.</span></span> <span data-ttu-id="f8b65-153">Sınıfı listeleme 2'de oluşturmak için kullanabileceğiniz bir `<label>` .</span><span class="sxs-lookup"><span data-stu-id="f8b65-153">You can use the class in Listing 2 to render a `<label>` .</span></span>

<span data-ttu-id="f8b65-154">**Kod 2 –`Helpers\LabelHelper.cs`**</span><span class="sxs-lookup"><span data-stu-id="f8b65-154">**Listing 2 – `Helpers\LabelHelper.cs`**</span></span>

[!code-csharp[Main](creating-custom-html-helpers-cs/samples/sample3.cs)]

<span data-ttu-id="f8b65-155">2. listeleme sınıfı hakkında özel bir şey yoktur.</span><span class="sxs-lookup"><span data-stu-id="f8b65-155">There is nothing special about the class in Listing 2.</span></span> <span data-ttu-id="f8b65-156">`Label()` Yöntemi yalnızca bir dize döndürür.</span><span class="sxs-lookup"><span data-stu-id="f8b65-156">The `Label()` method simply returns a string.</span></span>

<span data-ttu-id="f8b65-157">Listeleme 3 değiştirilmiş dizin görünümünde kullanan `LabelHelper` HTML oluşturmak için `<label>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="f8b65-157">The modified Index view in Listing 3 uses the `LabelHelper` to render HTML `<label>` tags.</span></span> <span data-ttu-id="f8b65-158">Görünüm içerir bildirimi bir `<%@ imports %>` alır yönergesi `Application1.Helpers` ad alanı.</span><span class="sxs-lookup"><span data-stu-id="f8b65-158">Notice that the view includes an `<%@ imports %>` directive that imports the `Application1.Helpers` namespace.</span></span>

<span data-ttu-id="f8b65-159">**Kod 2 –`Views\Home\Index2.aspx`**</span><span class="sxs-lookup"><span data-stu-id="f8b65-159">**Listing 2 – `Views\Home\Index2.aspx`**</span></span>

[!code-aspx[Main](creating-custom-html-helpers-cs/samples/sample4.aspx)]

### <a name="creating-html-helpers-with-extension-methods"></a><span data-ttu-id="f8b65-160">HTML Yardımcıları genişletme yöntemleri ile oluşturma</span><span class="sxs-lookup"><span data-stu-id="f8b65-160">Creating HTML Helpers with Extension Methods</span></span>

<span data-ttu-id="f8b65-161">Oluşturmak istiyorsanız çalışmaya HTML Yardımcıları genişletme yöntemleri oluşturmanıza gerek sonra ASP.NET MVC çerçevesi dahil standart HTML Yardımcıları ister.</span><span class="sxs-lookup"><span data-stu-id="f8b65-161">If you want to create HTML Helpers that work just like the standard HTML Helpers included in the ASP.NET MVC framework then you need to create extension methods.</span></span> <span data-ttu-id="f8b65-162">Genişletme yöntemleri, varolan bir sınıfa yeni yöntemler eklemenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="f8b65-162">Extension methods enable you to add new methods to an existing class.</span></span> <span data-ttu-id="f8b65-163">Bir HTML yardımcı yöntem oluştururken, bir görünümün Html özelliği tarafından temsil edilen HtmlHelper sınıfı için yeni yöntemler ekleyin.</span><span class="sxs-lookup"><span data-stu-id="f8b65-163">When creating an HTML Helper method, you add new methods to the HtmlHelper class represented by a view's Html property.</span></span>

<span data-ttu-id="f8b65-164">Bir genişletme yöntemi listeleme 3'te sınıfı ekler `HtmlHelper` adlı sınıf `Label()`.</span><span class="sxs-lookup"><span data-stu-id="f8b65-164">The class in Listing 3 adds an extension method to the `HtmlHelper` class named `Label()`.</span></span> <span data-ttu-id="f8b65-165">Bu sınıfı hakkında dikkat etmelidir şunları vardır.</span><span class="sxs-lookup"><span data-stu-id="f8b65-165">There are a couple of things that you should notice about this class.</span></span> <span data-ttu-id="f8b65-166">İlk olarak, sınıfın statik sınıf olduğuna dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="f8b65-166">First, notice that the class is a static class.</span></span> <span data-ttu-id="f8b65-167">Statik sınıf uzantısı yöntemiyle tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-167">You must define an extension method with a static class.</span></span>

<span data-ttu-id="f8b65-168">İkinci olarak, dikkat ilk parametresi `Label()` yöntemi anahtar sözcüğüyle öncesinde `this`.</span><span class="sxs-lookup"><span data-stu-id="f8b65-168">Second, notice that the first parameter of the `Label()` method is preceded by the keyword `this`.</span></span> <span data-ttu-id="f8b65-169">Bir genişletme yöntemi ilk parametresi uzantısı yöntemin genişlettiği sınıfı gösterir.</span><span class="sxs-lookup"><span data-stu-id="f8b65-169">The first parameter of an extension method indicates the class that the extension method extends.</span></span>

<span data-ttu-id="f8b65-170">**Kod 3 –`Helpers\LabelExtensions.cs`**</span><span class="sxs-lookup"><span data-stu-id="f8b65-170">**Listing 3 – `Helpers\LabelExtensions.cs`**</span></span>

[!code-csharp[Main](creating-custom-html-helpers-cs/samples/sample5.cs)]

<span data-ttu-id="f8b65-171">Bir genişletme yöntemi oluşturun ve başarılı bir şekilde uygulamanızı sonra genişletme yöntemi Visual Studio IntelliSense tüm bir sınıfın diğer yöntemleri gibi görünür. (bkz: Şekil 2).</span><span class="sxs-lookup"><span data-stu-id="f8b65-171">After you create an extension method, and build your application successfully, the extension method appears in Visual Studio Intellisense like all of the other methods of a class (see Figure 2).</span></span> <span data-ttu-id="f8b65-172">Tek fark, bunları (aşağı ok simgesi) yanındaki özel simgesiyle yöntemleri görünür bu uzantısıdır.</span><span class="sxs-lookup"><span data-stu-id="f8b65-172">The only difference is that extension methods appear with a special symbol next to them (an icon of a downward arrow).</span></span>


<span data-ttu-id="f8b65-173">[![Html.Label() genişletme yöntemi kullanma](creating-custom-html-helpers-cs/_static/image5.png)](creating-custom-html-helpers-cs/_static/image4.png)</span><span class="sxs-lookup"><span data-stu-id="f8b65-173">[![Using the Html.Label() extension method](creating-custom-html-helpers-cs/_static/image5.png)](creating-custom-html-helpers-cs/_static/image4.png)</span></span>

<span data-ttu-id="f8b65-174">**Şekil 02**: Html.Label() genişletme yöntemi kullanarak ([tam boyutlu görüntüyü görüntülemek için tıklatın](creating-custom-html-helpers-cs/_static/image6.png))</span><span class="sxs-lookup"><span data-stu-id="f8b65-174">**Figure 02**: Using the Html.Label() extension method  ([Click to view full-size image](creating-custom-html-helpers-cs/_static/image6.png))</span></span>


<span data-ttu-id="f8b65-175">Listeleme 4 değiştirilmiş dizin görünümünde tüm işlemek için Html.Label() genişletme yöntemi kullanan kendi `<label>` etiketler.</span><span class="sxs-lookup"><span data-stu-id="f8b65-175">The modified Index view in Listing 4 uses the Html.Label() extension method to render all of its `<label>` tags.</span></span>

<span data-ttu-id="f8b65-176">**4 listeleme –`Views\Home\Index3.aspx`**</span><span class="sxs-lookup"><span data-stu-id="f8b65-176">**Listing 4 – `Views\Home\Index3.aspx`**</span></span>

[!code-aspx[Main](creating-custom-html-helpers-cs/samples/sample6.aspx)]

## <a name="summary"></a><span data-ttu-id="f8b65-177">Özet</span><span class="sxs-lookup"><span data-stu-id="f8b65-177">Summary</span></span>

<span data-ttu-id="f8b65-178">Bu öğreticide, özel HTML Yardımcıları oluşturmak için iki yöntem öğrendiniz.</span><span class="sxs-lookup"><span data-stu-id="f8b65-178">In this tutorial, you learned two methods of creating custom HTML Helpers.</span></span> <span data-ttu-id="f8b65-179">Özel bir oluşturmak öğrendiniz ilk olarak, `Label()` bir statik yöntem oluşturarak HTML Yardımcısı bir dize döndürür.</span><span class="sxs-lookup"><span data-stu-id="f8b65-179">First, you learned how to create a custom `Label()` HTML Helper by creating a static method that returns a string.</span></span> <span data-ttu-id="f8b65-180">Ardından, özel bir oluşturma öğrenilen `Label()` üzerinde bir genişletme yöntemi oluşturarak HTML yardımcı yöntem `HtmlHelper` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="f8b65-180">Next, you learned how to create a custom `Label()` HTML Helper method by creating an extension method on the `HtmlHelper` class.</span></span>

<span data-ttu-id="f8b65-181">Bu öğreticide, oldukça basit bir HTML yardımcı yöntemi oluşturma üzerine odaklanır.</span><span class="sxs-lookup"><span data-stu-id="f8b65-181">In this tutorial, I focused on building an extremely simple HTML Helper method.</span></span> <span data-ttu-id="f8b65-182">Bir HTML Yardımcısı istediğiniz kadar karmaşık olabileceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f8b65-182">Realize that an HTML Helper can be as complicated as you want.</span></span> <span data-ttu-id="f8b65-183">Ağaç görünümleri, menüler veya veritabanı veri tabloları gibi zengin içerik işlemek HTML Yardımcıları oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f8b65-183">You can build HTML Helpers that render rich content such as tree views, menus, or tables of database data.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="f8b65-184">[Önceki](asp-net-mvc-views-overview-cs.md)
[sonraki](using-the-tagbuilder-class-to-build-html-helpers-cs.md)</span><span class="sxs-lookup"><span data-stu-id="f8b65-184">[Previous](asp-net-mvc-views-overview-cs.md)
[Next](using-the-tagbuilder-class-to-build-html-helpers-cs.md)</span></span>