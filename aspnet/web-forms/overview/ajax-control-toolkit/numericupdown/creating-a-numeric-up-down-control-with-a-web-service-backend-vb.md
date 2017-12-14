---
uid: web-forms/overview/ajax-control-toolkit/numericupdown/creating-a-numeric-up-down-control-with-a-web-service-backend-vb
title: "Bir Web hizmeti arka (VB) ile bir sayısal yukarı/aşağı denetim oluşturma | Microsoft Docs"
author: wenz
description: "Bir onay kutusuna bir değer yazın kullanıcının yapmasına izin vermek yerine bir sayısal yukarı/aşağı (Windows ve diğer işletim sistemleri mevcut) denetimi olarak daha fazla c kanıtlamak..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/02/2008
ms.topic: article
ms.assetid: afa59dfa-fef1-43d3-8fdd-aea3be36ed3c
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/numericupdown/creating-a-numeric-up-down-control-with-a-web-service-backend-vb
msc.type: authoredcontent
ms.openlocfilehash: 5ceefd6c18761c2abe3f3a4298d340642a0951d6
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="creating-a-numeric-updown-control-with-a-web-service-backend-vb"></a><span data-ttu-id="2cbce-103">Bir Web hizmeti arka (VB) ile bir sayısal yukarı/aşağı denetimi oluşturma</span><span class="sxs-lookup"><span data-stu-id="2cbce-103">Creating a Numeric Up/Down Control with a Web Service Backend (VB)</span></span>
====================
<span data-ttu-id="2cbce-104">tarafından [Christian Wenz](https://github.com/wenz)</span><span class="sxs-lookup"><span data-stu-id="2cbce-104">by [Christian Wenz](https://github.com/wenz)</span></span>

<span data-ttu-id="2cbce-105">[Kodu indirme](http://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/numericupdown1.vb.zip) veya [PDF indirin](http://download.microsoft.com/download/2/d/c/2dc10e34-6983-41d4-9c08-f78f5387d32b/numericupdown1VB.pdf)</span><span class="sxs-lookup"><span data-stu-id="2cbce-105">[Download Code](http://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/numericupdown1.vb.zip) or [Download PDF](http://download.microsoft.com/download/2/d/c/2dc10e34-6983-41d4-9c08-f78f5387d32b/numericupdown1VB.pdf)</span></span>

> <span data-ttu-id="2cbce-106">Bir onay kutusuna bir değer yazın kullanıcının yapmasına izin vermek yerine bir sayısal yukarı/aşağı (Windows ve diğer işletim sistemleri mevcut) denetimi olarak daha fazla kanıtlamak rahat.</span><span class="sxs-lookup"><span data-stu-id="2cbce-106">Instead of letting a user type a value into a check box, a numeric up/down control (that exists on Windows and other operating systems) could prove as more comfortable.</span></span> <span data-ttu-id="2cbce-107">Varsayılan olarak, NumericUpDown denetimi her zaman artırır veya bir değer 1 ile azaltır, ancak daha fazla esneklik bir web hizmeti kanıtlar.</span><span class="sxs-lookup"><span data-stu-id="2cbce-107">By default, the NumericUpDown control always increases or decreases a value by 1, but a web service proves more flexibility.</span></span>


## <a name="overview"></a><span data-ttu-id="2cbce-108">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="2cbce-108">Overview</span></span>

<span data-ttu-id="2cbce-109">Bir onay kutusuna bir değer yazın kullanıcının yapmasına izin vermek yerine bir sayısal yukarı/aşağı (Windows ve diğer işletim sistemleri mevcut) denetimi olarak daha fazla kanıtlamak rahat.</span><span class="sxs-lookup"><span data-stu-id="2cbce-109">Instead of letting a user type a value into a check box, a numeric up/down control (that exists on Windows and other operating systems) could prove as more comfortable.</span></span> <span data-ttu-id="2cbce-110">Varsayılan olarak, `NumericUpDown` denetimi her zaman artırır veya bir değer 1 ile azaltır, ancak daha fazla esneklik bir web hizmeti kanıtlar.</span><span class="sxs-lookup"><span data-stu-id="2cbce-110">By default, the `NumericUpDown` control always increases or decreases a value by 1, but a web service proves more flexibility.</span></span>

## <a name="steps"></a><span data-ttu-id="2cbce-111">Adımlar</span><span class="sxs-lookup"><span data-stu-id="2cbce-111">Steps</span></span>

<span data-ttu-id="2cbce-112">ASP.NET AJAX Denetim Araç Seti içeren `NumericUpDown` otomatik olarak bir metin kutusu iki düğme ekleyen genişletici: kendi değeri, bunu azaltmak için bir tane artırmak için bir tane.</span><span class="sxs-lookup"><span data-stu-id="2cbce-112">The ASP.NET AJAX Control Toolkit contains the `NumericUpDown` extender which automatically adds two buttons to a text box: One for increasing its value, one for decreasing it.</span></span> <span data-ttu-id="2cbce-113">Ancak denetim bir web hizmeti çağrısı (veya sayfa yöntem çağrısı) destekler.</span><span class="sxs-lookup"><span data-stu-id="2cbce-113">However the control also supports a web service call (or page method call).</span></span> <span data-ttu-id="2cbce-114">Her yukarı veya aşağı düğmesine tıklandığında, JavaScript kodu web sunucusuna bağlanır ve bir yöntemi yürütür.</span><span class="sxs-lookup"><span data-stu-id="2cbce-114">Whenever the up or down button is clicked, the JavaScript code connects to the web server and executes a method there.</span></span> <span data-ttu-id="2cbce-115">Yöntem imzası şu olur:</span><span class="sxs-lookup"><span data-stu-id="2cbce-115">The method signature is the following one:</span></span>

[!code-vb[Main](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/samples/sample1.vb)]

<span data-ttu-id="2cbce-116">`current` Bağımsız değişkeni metin kutusundaki; geçerli değeridir `tag` özniteliktir özelliği olarak ayarlanabilir ek bağlam verileri `NumericUpDown` genişletici (ancak gerekli değildir).</span><span class="sxs-lookup"><span data-stu-id="2cbce-116">The `current` argument is the current value in the text box; the `tag` attribute is additional context data that can be set as a property of the `NumericUpDown` extender (but is not required).</span></span>

<span data-ttu-id="2cbce-117">Bu örnek için yukarı/aşağı Denetim sayısal yalnızca iki tabanların olan değerleri izin: 1, 2, 4, 8, 16, 32, 64 ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="2cbce-117">For this sample, the numeric up/down control shall only allow values that are powers of two: 1, 2, 4, 8, 16, 32, 64, and so on.</span></span> <span data-ttu-id="2cbce-118">Bu nedenle, kullanıcı değeri artırmak istediğinde yürütülen yöntemi çift eski değer gerekir; başka bir yöntem değer iki tarafından bölmek gerekir.</span><span class="sxs-lookup"><span data-stu-id="2cbce-118">Therefore, the method executed when the user wants to increase the value must double the old value; the other method must divide value by two.</span></span> <span data-ttu-id="2cbce-119">Bu nedenle tam web hizmeti şöyledir:</span><span class="sxs-lookup"><span data-stu-id="2cbce-119">So here is the complete web service:</span></span>

[!code-aspx[Main](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/samples/sample2.aspx)]

<span data-ttu-id="2cbce-120">Son olarak, yeni bir ASP.NET sayfası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="2cbce-120">Finally, create a new ASP.NET page.</span></span> <span data-ttu-id="2cbce-121">Her zamanki gibi ihtiyacınız bir `ScriptManager` denetimi, bir `TextBox` denetim ve `NumericUpDownExtender` denetim.</span><span class="sxs-lookup"><span data-stu-id="2cbce-121">As usual, you need a `ScriptManager` control, a `TextBox` control and a `NumericUpDownExtender` control.</span></span> <span data-ttu-id="2cbce-122">İkincisi, web hizmeti bilgileri sağlamak için gerekenler:</span><span class="sxs-lookup"><span data-stu-id="2cbce-122">For the latter, you have to provide the web service information:</span></span>

- <span data-ttu-id="2cbce-123">`ServiceDownMethod`Aşağı adını web yöntemi veya sayfa yöntemi</span><span class="sxs-lookup"><span data-stu-id="2cbce-123">`ServiceDownMethod` name of the down web method or page method</span></span>
- <span data-ttu-id="2cbce-124">`ServiceDownPath`Aşağı hizmet yöntemi web hizmetiyle yolu; bir sayfa yöntemini kullanıyorsanız atlayın</span><span class="sxs-lookup"><span data-stu-id="2cbce-124">`ServiceDownPath` path to the web service with the down service method; omit if you are using a page method</span></span>
- <span data-ttu-id="2cbce-125">`ServiceUpMethod`Yukarı adını web yöntemi veya sayfa yöntemi</span><span class="sxs-lookup"><span data-stu-id="2cbce-125">`ServiceUpMethod` name of the up web method or page method</span></span>
- <span data-ttu-id="2cbce-126">`ServiceUpPath`Yukarı hizmet yöntemi web hizmetiyle yolu; bir sayfa yöntemini kullanıyorsanız atlayın</span><span class="sxs-lookup"><span data-stu-id="2cbce-126">`ServiceUpPath` path to the web service with the up service method; omit if you are using a page method</span></span>

<span data-ttu-id="2cbce-127">Sayfa için tam biçimlendirme şöyledir:</span><span class="sxs-lookup"><span data-stu-id="2cbce-127">Here is the complete markup for the page:</span></span>

[!code-aspx[Main](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/samples/sample3.aspx)]

<span data-ttu-id="2cbce-128">Sayfa çalıştırırsanız, üst düğmeyi tıklatın ve daha düşük düğmeyi tıkladığınızda yarıya nasıl metin kutusundaki değeri her zaman iki katına çıkar dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="2cbce-128">If you run the page, notice how the value in the text box always doubles when you click on the upper button, and is halved when you click on the lower button.</span></span>


<span data-ttu-id="2cbce-129">[![2'in olan sayılar görünür](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/_static/image2.png)](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/_static/image1.png)</span><span class="sxs-lookup"><span data-stu-id="2cbce-129">[![Only numbers that are a power of 2 appear](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/_static/image2.png)](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/_static/image1.png)</span></span>

<span data-ttu-id="2cbce-130">Yalnızca 2'in sayılar görüntülenir ([tam boyutlu görüntüyü görüntülemek için tıklatın](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/_static/image3.png))</span><span class="sxs-lookup"><span data-stu-id="2cbce-130">Only numbers that are a power of 2 appear ([Click to view full-size image](creating-a-numeric-up-down-control-with-a-web-service-backend-vb/_static/image3.png))</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="2cbce-131">Önceki</span><span class="sxs-lookup"><span data-stu-id="2cbce-131">Previous</span></span>](creating-a-numeric-up-down-control-with-a-web-service-backend-cs.md)