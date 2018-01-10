---
uid: web-forms/overview/ajax-control-toolkit/animation/executing-several-animations-at-the-same-time-vb
title: "Birkaç animasyon (VB) aynı anda yürütülen | Microsoft Docs"
author: wenz
description: "ASP.NET AJAX Denetim Araç Seti animasyon denetiminde bir denetimi ancak animasyonları için bir denetim eklemek için tam bir çerçeve değil. Severa çalışmasına izin..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/02/2008
ms.topic: article
ms.assetid: 2469f7ea-1489-42fb-a8e1-414c90141ce9
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/animation/executing-several-animations-at-the-same-time-vb
msc.type: authoredcontent
ms.openlocfilehash: 8461f5ea303a9e1166f694d4039d4c1aedd1caa8
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="executing-several-animations-at-the-same-time-vb"></a>(VB) aynı anda birkaç animasyon yürütme
====================
tarafından [Christian Wenz](https://github.com/wenz)

[Kodu indirme](http://download.microsoft.com/download/f/9/a/f9a26acd-8df4-4484-8a18-199e4598f411/Animation2.vb.zip) veya [PDF indirin](http://download.microsoft.com/download/6/7/1/6718d452-ff89-4d3f-a90e-c74ec2d636a3/animation2VB.pdf)

> ASP.NET AJAX Denetim Araç Seti animasyon denetiminde bir denetimi ancak animasyonları için bir denetim eklemek için tam bir çerçeve değil. Bu, birkaç animasyon paralel bir şekilde çalışmasına olanak verir.


## <a name="overview"></a>Genel Bakış

ASP.NET AJAX Denetim Araç Seti animasyon denetiminde bir denetimi ancak animasyonları için bir denetim eklemek için tam bir çerçeve değil. Bu, birkaç animasyon paralel bir şekilde çalışmasına olanak verir.

## <a name="steps"></a>Adımlar

İlk olarak dahil `ScriptManager` sayfasında; daha sonra ASP.NET AJAX kitaplığı, Denetim Araç Seti kullanmayı mümkün hale getirme yüklenir:

[!code-aspx[Main](executing-several-animations-at-the-same-time-vb/samples/sample1.aspx)]

Animasyonun bir panel şöyle metin uygulanır:

[!code-aspx[Main](executing-several-animations-at-the-same-time-vb/samples/sample2.aspx)]

İlişkili CSS sınıfı bölmesinin iyi arka plan rengi tanımlayın ve ayrıca sabit genişlikli bölmesinin ayarlayın:

[!code-css[Main](executing-several-animations-at-the-same-time-vb/samples/sample3.css)]

Ardından, ekleyin `AnimationExtender` sayfasına sağlayan bir `ID`, `TargetControlID` özniteliği ve zorunlu `runat="server"`:

[!code-aspx[Main](executing-several-animations-at-the-same-time-vb/samples/sample4.aspx)]

İçinde `<Animations>` düğümü, kullanım `<OnLoad>` sayfa tam yüklenmeden silindikten sonra animasyonları çalıştırmak için. Genellikle, `<OnLoad>` yalnızca bir animasyon kabul eder. Animasyon çerçevesi bir kullanarak birkaç animasyon katılma sayesinde `<Parallel>` öğesi. İçindeki tüm animasyonları `<Parallel>` aynı anda çalıştırılır.

İşte için olası bir biçimlendirme `AnimationExtender` yavaş çıkış ve paneli aynı anda yeniden boyutlandırma denetimi:

[!code-aspx[Main](executing-several-animations-at-the-same-time-vb/samples/sample5.aspx)]

Ve gerçekten: Bu komut dosyasını çalıştırdığınızda paneli görüntülenir, sonra yeniden boyutlandırır (threefolding'den fazla genişlik ve halfing yüksekliğini) ve aynı anda silinerek çıkar.


[![Bölmenin yavaş çıkış ve (tarayıcının işleme altyapısı sayesinde içeriğine dahil) yeniden boyutlandırma](executing-several-animations-at-the-same-time-vb/_static/image2.png)](executing-several-animations-at-the-same-time-vb/_static/image1.png)

Bölmenin yavaş çıkış ve (tarayıcının işleme altyapısı sayesinde içeriğine dahil) yeniden boyutlandırma ([tam boyutlu görüntüyü görüntülemek için tıklatın](executing-several-animations-at-the-same-time-vb/_static/image3.png))

>[!div class="step-by-step"]
[Önceki](adding-animation-to-a-control-vb.md)
[sonraki](executing-several-animations-after-each-other-vb.md)