---
uid: ajax/cdn/overview
title: "Microsoft Ajax içerik teslim ağı | Microsoft Docs"
author: rick-anderson
description: 
ms.author: aspnetcontent
manager: wpickett
ms.date: 10/14/2017
ms.topic: article
ms.assetid: 8935bf14-ca6d-4a4e-9dbe-b96ce74cef49
ms.technology: 
ms.prod: .net-framework
msc.legacyurl: /ajax/cdn
msc.type: content
ms.openlocfilehash: f69f707ba64d13fc372b7bc44718c9dcf8cec6e2
ms.sourcegitcommit: 3f491f887074310fc0f145cd01a670aa63b969e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
<a name="microsoft-ajax-content-delivery-network"></a>Microsoft Ajax içerik teslim ağı
====================
Not: Bir Azure CDN kullanarak özellik hiçbir SLA Microsoft Ajax CDN sahiptir.

## <a name="table-of-contents"></a>İçindekiler tablosu

**[ajax.microsoft.com AJAX.aspnetcdn.com için yeniden adlandırıldı](#ajaxmicrosoftcom_renamed_to_ajaxaspnetcdncom_18)**  
**[Visual Studio .vsdoc desteği](#Visual_Studio_vsdoc_Support_19)**  
**[ASP.NET Ajax CDN kullanma](#Using_ASPNET_Ajax_from_the_CDN_20)**  
**[CDN jQuery kullanma](#Using_jQuery_from_the_CDN_21)**  
**[JQuery UI CDN kullanma](#Using_jQuery_UI_from_the_CDN_22)**  
**[CDN üçüncü taraf dosyaları](#Third-Party_Files_on_the_CDN_23)**  
  
 [CDN üzerinde jQuery sürümleri](#jQuery_Releases_on_the_CDN_0)  
 [CDN üzerinde jQuery geçirmek sürümleri](#jQuery_Migrate_Releases_on_the_CDN_1)  
 [jQuery UI sürümleri CDN üzerinde](#jQuery_UI_Releases_on_the_CDN_2)  
 [jQuery CDN üzerinde doğrulama sürümleri](#jQuery_Validation_Releases_on_the_CDN_3)  
 [jQuery Mobile sürümleri CDN üzerinde](#jQuery_Mobile_Releases_on_the_CDN_4)  
 [jQuery CDN üzerinde şablonları sürümleri](#jQuery_Templates_Releases_on_the_CDN_5)  
 [jQuery CDN üzerinde döngüsü sürümleri](#jQuery_Cycle_Releases_on_the_CDN_6)  
 [jQuery CDN üzerinde DataTables sürümleri](#jQuery_DataTables_Releases_on_the_CDN_7)  
 [CDN üzerinde Modernizr sürümleri](#Modernizr_Releases_on_the_CDN_8)  
 [CDN üzerinde JSHint sürümleri](#JSHint_Releases_on_the_CDN_10)  
 [CDN üzerinde Boşaltılan sürümleri](#Knockout_Releases_on_the_CDN_11)  
 [CDN üzerinde sürümleri globalize](#Globalize_Releases_on_the_CDN_12)  
 [CDN üzerinde sürümleri yanıt](#Respond_Releases_on_the_CDN_13)  
 [CDN üzerinde önyükleme sürümleri](#Bootstrap_Releases_on_the_CDN_14)  
 [CDN üzerinde önyükleme TouchCarousel sürümleri](#BootstrapTouchCarousel_Releases_on_the_CDN_18)  
 [CDN üzerinde Hammer.js sürümleri](#Hammerjs_Releases_on_the_CDN_19)  
 [ASP.NET Web formları ve CDN üzerinde Ajax sürümleri](#ASPNET_Web_Forms_and_Ajax_Releases_on_the_CDN_15)  
 [ASP.NET MVC üzerinde CDN serbest bırakır](#ASPNET_MVC_Releases_on_the_CDN_16)  
 [ASP.NET SignalR üzerinde CDN serbest bırakır](#ASPNET_SignalR_Releases_on_the_CDN_17)

Microsoft Ajax içerik teslim ağı (CDN) jQuery gibi popüler üçüncü taraf JavaScript kitaplıklarını barındırır ve bunları Web uygulamalarınızın kolayca eklemenize olanak tanır. Örneğin, basitçe ekleyerek bu CDN üzerinde barındırılan jQuery kullanmaya başlayabilmeniz için bir &lt;betik&gt; etiketi sayfanıza ajax.aspnetcdn.com için işaret eder.

CDN yararlanarak, Ajax uygulamalarınızın performansını önemli ölçüde artırabilir. CDN içeriğini tüm dünyada bulunan sunucuları önbelleğe alınır. Ayrıca, CDN farklı etki alanlarında bulunan web siteleri için önbelleğe alınan üçüncü taraf JavaScript dosyaları yeniden tarayıcılar sağlar.

Güvenli Yuva Katmanı'ni kullanarak bir web sayfası hizmet gerekebileceği CDN SSL (HTTPS) destekler.

CDN yüklenmiş ve size bu kitaplıkları sahibi tarafından lisanslanır aşağıdaki üçüncü taraf betik kitaplıkları barındırır:

- jQuery (www.jquery.com)
- jQuery UI (www.jqueryui.com)
- jQuery Mobile (www.jquerymobile.com)
- jQuery doğrulama (www.jquery.com)
- jQuery döngüsü (www.malsup.com/jquery/cycle/)
- jQuery DataTables (http://datatables.net/)

Microsoft Ajax CDN Ayrıca, Microsoft tarafından yüklenen aşağıdaki kitaplıkları içerir:

- ASP.NET Ajax'ı
- ASP.NET MVC JavaScript dosyaları
- ASP.NET SignalR JavaScript dosyaları

Microsoft, bu CDN üzerinde barındırılan herhangi bir üçüncü taraf kitaplıklar sahipliğini talep değil. Telif hakkı sahipleri kitaplıkları, size bu kitaplıklar lisans. Karşıdan yükleme ve bu tür kitaplıklarını kullanma gerekebilir herhangi bir hakka yalnızca ilgili telif hakkı sahipleri tarafından verilir. Bunlar Microsoft kitaplıkları olduğundan, Microsoft bu CDN üzerinde barındırılan üçüncü taraf kitaplıklar için hiçbir garanti vermez veya fikri mülkiyet hakları lisansları (zımni hiçbir patent hakları dahil) sağlar.

JavaScript kitaplığı göndermek istiyor ve kitaplığınızın üst (http://trends.builtwith.com üzerinde listelendiği gibi) JavaScript kitaplıklarını veya bu kitaplıkları uzantıları/eklentilerinde biri (a) popüler; veya (b) için faydalı üzerindeki ASP.NET kullanın sonra temasa AjaxCDNSubmission@Microsoft.com.

<a id="ajaxmicrosoftcom_renamed_to_ajaxaspnetcdncom_18"></a>

## <a name="ajaxmicrosoftcom-renamed-to-ajaxaspnetcdncom"></a>ajax.microsoft.com AJAX.aspnetcdn.com için yeniden adlandırıldı

CDN microsoft.com etki alanı adını kullanmak için kullanılan ve aspnetcdn.com etki alanı adını kullanmak üzere değiştirildi. Bu değişiklik, bir tarayıcı microsoft.com etki alanı başvurulduğunda tüm tanımlama bilgilerini bu etki alanından her istek ile kablo üzerinden göndermeden çünkü performansı artırmak için yapılmıştır. Microsoft.com dışında bir etki alanı adı için adlandırarak performans çok % 25 olarak artırılabilir. Not ajax.microsoft.com çalışmaya devam eder ancak ajax.aspnetcdn.com önerilir.

- Eski biçimi: http://ajax.microsoft.com/ajax/jQuery/jquery-1.8.0.js
- Yeni biçim: http://ajax.aspnetcdn.com/ajax/jQuery/jquery-1.8.0.js

<a id="Visual_Studio_vsdoc_Support_19"></a>

## <a name="visual-studio-vsdoc-support"></a>Visual Studio .vsdoc desteği

.Vsdoc dosyaları düzgün VS 2008 SP1'e sahip olduğunuzdan emin olmanız gerekir Visual Studio 2008 ile kullanmak için yüklenir ve vsdoc dosyaları düzeltmesinin yüklü. Bunlar buradan edinebilirsiniz:

- [Visual Studio 2008 SP1'i karşıdan](https://www.microsoft.com/downloads/en/details.aspx?FamilyId=FBEE1648-7106-44A7-9649-6D9F6D58056E&amp;displaylang=en "Visual Studio 2008 SP1'i Yükle")
- [Visual Studio 2008 SP1 için .vsdoc Düzeltme karşıdan](https://code.msdn.microsoft.com/KB958502/Release/ProjectReleases.aspx?ReleaseId=1736 ".vsdoc düzeltme için Visual Studio 2008 SP1 yükle")

Visual Studio 2010 ek düzeltme eklerinin olmadan .vsdoc dosyalarını destekler.

<a id="Using_ASPNET_Ajax_from_the_CDN_20"></a>

## <a name="using-aspnet-ajax-from-the-cdn"></a>ASP.NET Ajax CDN kullanma

ASP.NET 4 kullanırken, ASP.NET framework komut dosyaları için tüm istekleri için CDN yönlendirebilirsiniz. Yerel web sunucunuzun yerine CDN komut dosyaları alma önemli ölçüde ortak ASP.NET Web siteleri performansını artırabilir.

Microsoft Ajax CDN ile tüm ASP.NET framework betik isteklerini yeniden yönlendirmek için ScriptManager EnableCDN özelliğini kullanın:

[!code-aspx[Main](overview/samples/sample1.aspx)]

<a id="Using_jQuery_from_the_CDN_21"></a>

## <a name="using-jquery-from-the-cdn"></a>CDN jQuery kullanma

Aşağıdaki betik öğesi bir sayfaya ekleyerek Web uygulamanızda CDN üzerinde barındırılan jQuery betikleri kullanabilirsiniz:

[!code-html[Main](overview/samples/sample2.html)]

CDN alabileceğiniz jQuery komut dosyasının küçültülmüş sürümünü de içerir. aşağıdaki öğeyi kullanarak:

[!code-html[Main](overview/samples/sample3.html)]

CDN kullanılamaz durumda, kendi Web sitesinde bir yerel yol veritabanından jQuery yükleme için geri dönüş sayfanıza izin vermek için hemen CDN başvuran öğesinden sonra aşağıdaki öğeyi ekleyin:

[!code-html[Main](overview/samples/sample4.html)]

Aşağıdaki örnek sayfasına bir düğme tıklatıldığında div öğesinin içeriğini görüntülemek için jQuery kitaplığı (ile yerel bir kopya için geri dönüş) CDN sürümünü kullanır.

[!code-html[Main](overview/samples/sample5.html)]

JQuery hakkında daha fazla bilgi ve ziyaret ederek jQuery yerel bir kopyasını indirin [jQuery](http://jquery.com/) Web sitesi.

<a id="Using_jQuery_UI_from_the_CDN_22"></a>

## <a name="using-jquery-ui-from-the-cdn"></a>JQuery UI CDN kullanma

CDN jQuery kullanıcı Arabirimi kitaplığı da barındırır. JQuery kullanıcı Arabirimi kitaplığı zengin bir pencere öğeleri ve ASP.NET uygulamalarınızın kullanabilirsiniz efektler içerir. Örneğin, aşağıdaki sayfayı açılır takvimi görüntülemek için bir ASP.NET Web Forms uygulama bağlamında jQuery UI Datepicker nasıl kullanabileceğiniz gösterilmektedir:

[!code-aspx[Main](overview/samples/sample6.aspx)]

Klavyenizi kullanarak metin kutusuna odağı taşıdığınızda, bir takvim görüntülenir:

![Oluşturulan DatePicker popup Takvim](overview/_static/image1.png)

Yukarıdaki kod CDN üç dosyaları içermelidir dikkat edin:

- JQuery Kitaplığı &mdash; jQuery kullanıcı Arabirimi kitaplığı jQuery kitaplıkta bağlıdır. JQuery kullanıcı Arabirimi kitaplığı eklemeden önce jQuery kitaplığı sayfanıza eklemeniz gerekir.
- JQuery kullanıcı Arabirimi Kitaplığı &mdash; jQuery kullanıcı Arabirimi kitaplığı tüm jQuery UI etkiler ve yukarıdaki sayfa kullanılan Datepicker pencere gibi pencere öğeleri içerir.
- JQuery UI tema &mdash; farklı temaları jQuery UI destekler. Yukarıdaki sayfa Redmond temayı içeri aktarmak için bir CSS dosyası için bir bağlantı içerir.

Tüm standart jQuery UI temaları CDN üzerinde barındırılır. [Bu sayfayı ziyaret](jquery-ui/cdnjqueryui1910.md "jQuery UI 1.8.10 Microsoft Ajax CDN üzerinde") her tema için küçük resimler görüntülemek için.

JQuery kullanıcı Arabirimi Kitaplığı hakkında daha fazla bilgi edinmek için resmi ziyaret [jQuery UI Web sitesi](http://jQueryUI.com "jQuery UI Web sitesi").

<a id="Third-Party_Files_on_the_CDN_23"></a>

## <a name="third-party-files-on-the-cdn"></a>CDN üçüncü taraf dosyaları

CDN en popüler üçüncü taraf JavaScript kitaplıklarını bazıları barındırır. Microsoft, bu CDN üzerinde barındırılan herhangi bir üçüncü taraf kitaplıklar sahipliğini talep değil. Telif hakkı sahipleri kitaplıkları, size bu kitaplıklar lisans. Karşıdan yükleme ve bu tür kitaplıklarını kullanma gerekebilir herhangi bir hakka yalnızca ilgili telif hakkı sahipleri tarafından verilir. Bunlar Microsoft kitaplıkları olduğundan, Microsoft bu CDN üzerinde barındırılan üçüncü taraf kitaplıklar için hiçbir garanti vermez veya fikri mülkiyet hakları lisansları (zımni hiçbir patent hakları dahil) sağlar.

<a id="jQuery_Releases_on_the_CDN_0"></a>

### <a name="jquery-releases-on-the-cdn"></a>CDN üzerinde jQuery sürümleri

JQuery aşağıdaki sürümleri CDN üzerinde barındırılan:

#### <a name="jquery-version-331"></a>jQuery sürüm 3.3.1
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.3.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.3.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.3.1.Min.map
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.3.1.Slim.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.3.1.Slim.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.3.1.Slim.Min.map

#### <a name="jquery-version-321"></a>jQuery sürüm 3.2.1
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.1.Min.map
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.1.Slim.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.1.Slim.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.1.Slim.Min.map

#### <a name="jquery-version-320"></a>jQuery sürüm 3.2.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.0.Min.map
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.0.Slim.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.0.Slim.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.2.0.Slim.Min.map

#### <a name="jquery-version-311"></a>jQuery sürüm 3.1.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.1.Min.map
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.1.Slim.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.1.Slim.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.1.Slim.Min.map

#### <a name="jquery-version-310"></a>jQuery sürüm 3.1.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.0.Min.map
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.0.Slim.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.0.Slim.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.1.0.Slim.Min.map

#### <a name="jquery-version-300"></a>jQuery sürüm 3.0.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.0.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.0.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.0.0.Min.map
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.0.0.Slim.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.0.0.Slim.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-3.0.0.Slim.Min.map

#### <a name="jquery-version-224"></a>jQuery sürüm 2.2.4

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.4.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.4.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.4.Min.map

#### <a name="jquery-version-223"></a>jQuery sürüm 2.2.3

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.3.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.3.Min.map

#### <a name="jquery-version-222"></a>jQuery sürüm 2.2.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.2.Min.map

#### <a name="jquery-version-221"></a>jQuery sürüm 2.2.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.1.Min.map

#### <a name="jquery-version-220"></a>jQuery sürüm 2.2.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.2.0.Min.map

#### <a name="jquery-version-214"></a>jQuery sürüm 2.1.4

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.4.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.4.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.4.Min.map

#### <a name="jquery-version-213"></a>jQuery sürüm 2.1.3

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.3.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.3.Min.map

#### <a name="jquery-version-212"></a>jQuery sürüm 2.1.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.2.Min.js

#### <a name="jquery-version-211"></a>jQuery sürüm 2.1.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.1.Min.map

#### <a name="jquery-version-210"></a>jQuery sürüm 2.1.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.0-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.1.0.Min.map

#### <a name="jquery-version-203"></a>jQuery sürüm 2.0.3

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.3.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.3-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.3.Min.map

#### <a name="jquery-version-202"></a>jQuery sürüm 2.0.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.2-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.2.Min.map

#### <a name="jquery-version-201"></a>jQuery sürüm 2.0.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.1-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.1.Min.map

#### <a name="jquery-version-200"></a>jQuery sürüm 2.0.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.0-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-2.0.0.Min.map

#### <a name="jquery-version-1124"></a>jQuery sürüm 1.12.4

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.4.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.4.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.4.Min.map

#### <a name="jquery-version-1123"></a>jQuery sürüm 1.12.3

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.3.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.3.Min.map

#### <a name="jquery-version-1122"></a>jQuery sürüm 1.12.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.2.Min.map

#### <a name="jquery-version-1121"></a>jQuery sürüm 1.12.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.1.Min.map

#### <a name="jquery-version-1120"></a>jQuery sürüm 1.12.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.12.0.Min.map

#### <a name="jquery-version-1113"></a>jQuery sürüm 1.11.3

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.3.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.3.Min.map

#### <a name="jquery-version-1112"></a>jQuery sürüm 1.11.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.2.Min.map

#### <a name="jquery-version-1111"></a>jQuery sürüm 1.11.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.1.Min.map

#### <a name="jquery-version-1110"></a>jQuery sürüm 1.11.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.0-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.11.0.Min.map

#### <a name="jquery-version-1102"></a>jQuery sürüm 1.10.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.2-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.2.Min.map

#### <a name="jquery-version-1101"></a>jQuery sürüm 1.10.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.1-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.1.Min.map

#### <a name="jquery-version-1100"></a>jQuery sürüm 1.10.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.0-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.10.0.Min.map

#### <a name="jquery-version-191"></a>jQuery sürüm 1.9.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.9.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.9.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.9.1-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.9.1.Min.map

#### <a name="jquery-version-190"></a>jQuery sürüm 1.9.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.9.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.9.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.9.0-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.9.0.Min.map

#### <a name="jquery-version-183"></a>jQuery sürüm 1.8.3

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.3.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.3-vsdoc.js

#### <a name="jquery-version-182"></a>jQuery sürüm 1.8.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.2-vsdoc.js

#### <a name="jquery-version-181"></a>jQuery sürüm 1.8.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.1-vsdoc.js

#### <a name="jquery-version-180"></a>jQuery sürüm 1.8.0

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.8.0-vsdoc.js

#### <a name="jquery-version-172"></a>jQuery sürüm 1.7.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.7.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.7.2.Min.js

#### <a name="jquery-version-171"></a>jQuery sürüm 1.7.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.7.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.7.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.7.1-vsdoc.js

#### <a name="jquery-version-17"></a>jQuery sürüm 1.7

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.7.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.7.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.7-vsdoc.js

#### <a name="jquery-version-164"></a>jQuery sürüm 1.6.4

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.4.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.4.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.4-vsdoc.js

#### <a name="jquery-version-163"></a>jQuery sürüm 1.6.3

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.3.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.3-vsdoc.js

#### <a name="jquery-version-162"></a>jQuery sürüm 1.6.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.2-vsdoc.js

#### <a name="jquery-version-161"></a>jQuery sürüm 1.6.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.1-vsdoc.js

#### <a name="jquery-version-16"></a>jQuery sürüm 1.6

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.6-vsdoc.js

#### <a name="jquery-version-152"></a>jQuery sürüm 1.5.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5.2-vsdoc.js

#### <a name="jquery-version-151"></a>jQuery sürüm 1.5.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5.1-vsdoc.js

#### <a name="jquery-version-15"></a>jQuery sürüm 1.5

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.5-vsdoc.js

#### <a name="jquery-version-144"></a>jQuery sürüm 1.4.4

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.4.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.4.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.4-vsdoc.js

#### <a name="jquery-version-143"></a>jQuery sürüm 1.4.3

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.3.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.3-vsdoc.js

#### <a name="jquery-version-142"></a>jQuery sürüm 1.4.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.2-vsdoc.js

#### <a name="jquery-version-141"></a>jQuery sürüm 1.4.1

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.1-vsdoc.js

#### <a name="jquery-version-14"></a>jQuery sürüm 1.4

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.4.Min.js

#### <a name="jquery-version-132"></a>jQuery sürüm 1.3.2

- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.3.2.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.3.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.3.2-vsdoc.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery/JQuery-1.3.2.Min-vsdoc.js

<a id="jQuery_Migrate_Releases_on_the_CDN_1"></a>

### <a name="jquery-migrate-releases-on-the-cdn"></a>CDN üzerinde jQuery geçirmek sürümleri

JQuery geçirme aşağıdaki sürümleri CDN üzerinde barındırılan:

#### <a name="jquery-migrate-version-300"></a>jQuery sürüm 3.0.0 geçirme

- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-3.0.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-3.0.0.Min.js

#### <a name="jquery-migrate-version-121"></a>jQuery geçirme 1.2.1 sürümü

- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.2.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.2.1.Min.js

jQuery sürüm 1.2.0 geçirme

- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.2.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.2.0.Min.js

#### <a name="jquery-migrate-version-111"></a>jQuery sürüm 1.1.1 geçirme

- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.1.1.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.1.1.Min.js

#### <a name="jquery-migrate-version-110"></a>jQuery sürüm 1.1.0 geçirme

- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.1.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.1.0.Min.js

#### <a name="jquery-migrate-version-100"></a>jQuery sürümü 1.0.0 geçirme

- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.0.0.js
- http://AJAX.aspnetcdn.com/AJAX/JQuery.Migrate/JQuery-Migrate-1.0.0.Min.js

<a id="jQuery_UI_Releases_on_the_CDN_2"></a>

### <a name="jquery-ui-releases-on-the-cdn"></a>jQuery UI sürümleri CDN üzerinde

JQuery kullanıcı Arabirimi kitaplığı aşağıdaki sürümleri, bu CDN üzerinde barındırılır. Dosyaların gerçek listesini görmek için her bağlantıyı tıklatın.

- [jQuery UI 1.12.1](jquery-ui/cdnjqueryui1121.md "jQuery UI 1.12.1 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.12.0](jquery-ui/cdnjqueryui1120.md "jQuery UI 1.12.0 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.11.4](jquery-ui/cdnjqueryui1114.md "jQuery UI 1.11.4 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.11.3](jquery-ui/cdnjqueryui1113.md "jQuery UI 1.11.3 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.11.2](jquery-ui/cdnjqueryui1112.md "jQuery UI 1.11.2 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.11.1](jquery-ui/cdnjqueryui1111.md "jQuery UI 1.11.1 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.11.0](jquery-ui/cdnjqueryui1110.md "jQuery UI 1.11.0 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.10.4](jquery-ui/cdnjqueryui1104.md "jQuery UI 1.10.4 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.10.3](jquery-ui/cdnjqueryui1103.md "jQuery UI 1.10.3 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.10.2](jquery-ui/cdnjqueryui1102.md "jQuery 1.10.2 UI Microsoft Ajax CDN")
- [jQuery UI 1.10.1](jquery-ui/cdnjqueryui1101.md "jQuery UI 1.10.1 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.10.0](jquery-ui/cdnjqueryui1100.md "jQuery UI 1.10.0 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.9.2](jquery-ui/cdnjqueryui192.md "jQuery UI 1.9.2 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.9.1](jquery-ui/cdnjqueryui191.md "jQuery UI 1.9.1 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.9.0](jquery-ui/cdnjqueryui190.md "jQuery UI 1.9.0 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.24](jquery-ui/cdnjqueryui1824.md "jQuery UI 1.8.24 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.23](jquery-ui/cdnjqueryui1823.md "jQuery UI 1.8.23 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.22](jquery-ui/cdnjqueryui1822.md "jQuery UI 1.8.22 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.21](jquery-ui/cdnjqueryui1821.md "jQuery UI 1.8.21 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.20](jquery-ui/cdnjqueryui1820.md "jQuery UI 1.8.20 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.19](jquery-ui/cdnjqueryui1819.md "jQuery UI 1.8.19 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.18](jquery-ui/cdnjqueryui1818.md "jQuery UI 1.8.18 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.17](jquery-ui/cdnjqueryui1817.md "jQuery UI 1.8.17 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.16](jquery-ui/cdnjqueryui1816.md "jQuery UI 1.8.16 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.15](jquery-ui/cdnjqueryui1815.md "jQuery UI 1.8.15 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.14](jquery-ui/cdnjqueryui1814.md "jQuery UI 1.8.14 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.13](jquery-ui/cdnjqueryui1813.md "jQuery UI 1.8.13 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.12](jquery-ui/cdnjqueryui1812.md "jQuery UI 1.8.12 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.11](jquery-ui/cdnjqueryui1811.md "jQuery UI 1.8.11 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.10](jquery-ui/cdnjqueryui1910.md "jQuery UI 1.8.10 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.9](jquery-ui/cdnjqueryui189.md "jQuery UI 1.8.9 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.8](jquery-ui/cdnjqueryui188.md "jQuery UI 1.8.8 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.7](jquery-ui/cdnjqueryui187.md "jQuery UI 1.8.7 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.6](jquery-ui/cdnjqueryui186.md "jQuery UI 1.8.6 Microsoft Ajax CDN üzerinde")
- [jQuery UI 1.8.5](jquery-ui/cdnjqueryui185.md "jQuery UI 1.8.5")

<a id="jQuery_Validation_Releases_on_the_CDN_3"></a>

### <a name="jquery-validation-releases-on-the-cdn"></a>jQuery CDN üzerinde doğrulama sürümleri

JQuery doğrulama kitaplığı aşağıdaki sürümleri, bu CDN üzerinde barındırılır. Dosyaların gerçek listesini görmek için her bağlantıyı tıklatın.

- [jQuery doğrulama 1.17.0](jquery-validate/cdnjqueryvalidate1170.md "jQuery doğrulama 1.17.0")
- [jQuery doğrulama 1.16.0](jquery-validate/cdnjqueryvalidate1160.md "jQuery doğrulama 1.16.0")
- [jQuery doğrulama 1.15.1](jquery-validate/cdnjqueryvalidate1151.md "jQuery doğrulama 1.15.1")
- [jQuery doğrulama 1.15.0](jquery-validate/cdnjqueryvalidate1150.md "jQuery doğrulama 1.15.0")
- [jQuery doğrulama 1.14.0](jquery-validate/cdnjqueryvalidate1140.md "jQuery doğrulama 1.14.0")
- [jQuery doğrulama 1.13.1](jquery-validate/cdnjqueryvalidate1131.md "jQuery doğrulama 1.13.1")
- [jQuery doğrulama 1.13.0](jquery-validate/cdnjqueryvalidate1130.md "jQuery doğrulama 1.13.0")
- [jQuery doğrulama 1.12.0](jquery-validate/cdnjqueryvalidate1120.md "jQuery doğrulama 1.12.0")
- [jQuery doğrulama 1.11.1](jquery-validate/cdnjqueryvalidate1111.md "jQuery doğrulama 1.11.1")
- [jQuery doğrulama 1.11.0](jquery-validate/cdnjqueryvalidate111.md "jQuery doğrulama 1.11.0")
- [jQuery doğrulama 1.10.0](jquery-validate/cdnjqueryvalidate110.md "jQuery doğrulama 1.10.0")
- [jQuery doğrulama 1.9](jquery-validate/cdnjqueryvalidate19.md "jquery.validate sürüm 1.9")
- [jQuery doğrulama 1.8.1](jquery-validate/cdnjqueryvalidate181.md "jquery.validate sürüm 1.8.1")
- [jQuery doğrulama 1.8](jquery-validate/cdnjqueryvalidate18.md "jquery.validate sürüm 1,8")
- [jQuery doğrulama 1.7](jquery-validate/cdnjqueryvalidate17.md "jquery.validate sürüm 1.7")
- [jQuery doğrulama 1.6](jquery-validate/cdnjqueryvalidate16.md "jQuery doğrulama 1.6")
- [jQuery doğrulama 1.5.5](jquery-validate/cdnjqueryvalidate155.md "jQuery doğrulama 1.5.5")

<a id="jQuery_Mobile_Releases_on_the_CDN_4"></a>

### <a name="jquery-mobile-releases-on-the-cdn"></a>jQuery Mobile sürümleri CDN üzerinde

JQuery Mobile kitaplığı aşağıdaki sürümleri, bu CDN üzerinde barındırılır. Dosyaların gerçek listesini görmek için her bağlantıyı tıklatın.

- [jQuery Mobile 1.4.5](jquery-mobile/cdnjquerymobile145.md "jQuery Mobile 1.4.5 Microsoft Ajax CDN")
- [jQuery Mobile 1.4.2](jquery-mobile/cdnjquerymobile142.md "jQuery Mobile 1.4.2 Microsoft Ajax CDN")
- [jQuery Mobile 1.4.1](jquery-mobile/cdnjquerymobile141.md "jQuery Mobile 1.4.1 Microsoft Ajax CDN")
- [jQuery Mobile 1.4.0](jquery-mobile/cdnjquerymobile140.md "jQuery Mobile 1.4.0 Microsoft Ajax CDN")
- [jQuery Mobile 1.3.2](jquery-mobile/cdnjquerymobile132.md "jQuery Mobile 1.3.2 Microsoft Ajax CDN")
- [jQuery Mobile 1.3.1](jquery-mobile/cdnjquerymobile131.md "jQuery Mobile 1.3.1 Microsoft Ajax CDN")
- [jQuery Mobile 1.3.0](jquery-mobile/cdnjquerymobile130.md "jQuery Mobile 1.3.0 Microsoft Ajax CDN")
- [jQuery Mobile 1.2.0](jquery-mobile/cdnjquerymobile120.md "jQuery Mobile 1.2.0 Microsoft Ajax CDN")
- [jQuery Mobile 1.1.2](jquery-mobile/cdnjquerymobile112.md "jQuery Mobile 1.1.2 Microsoft Ajax CDN")
- [jQuery Mobile 1.1.1](jquery-mobile/cdnjquerymobile111.md "jQuery Mobile 1.1.1 Microsoft Ajax CDN")
- [jQuery Mobile 1.1.0](jquery-mobile/cdnjquerymobile110.md "jQuery Mobile 1.1.0 Microsoft Ajax CDN")
- [jQuery Mobile 1.1.0 RC 2](jquery-mobile/cdnjquerymobile110rc2.md "jQuery Mobile 1.1.0 RC2 için Microsoft Ajax CDN")
- [jQuery Mobile 1.0.1](jquery-mobile/cdnjquerymobile101.md "jQuery Mobile 1.0.1 Microsoft Ajax CDN")
- [jQuery Mobile 1.0](jquery-mobile/cdnjquerymobile10.md "jQuery Mobile 1.0 Microsoft Ajax CDN")
- [jQuery Mobile 1.0 RC 2](jquery-mobile/cdnjquerymobile10rc2.md "jQuery Mobile 1.0 RC2 için Microsoft Ajax CDN üzerinde")
- [jQuery Mobile 1.0 RC 1](jquery-mobile/cdnjquerymobile10rc1.md "jQuery Mobile 1.0 RC1 için Microsoft Ajax CDN üzerinde")
- [jQuery Mobile 1.0 beta 3](jquery-mobile/cdnjquerymobile10b3.md "Microsoft Ajax CDN üzerinde jQuery Mobile 1.0 Beta 3")

<a id="jQuery_Templates_Releases_on_the_CDN_5"></a>

### <a name="jquery-templates-releases-on-the-cdn"></a>jQuery CDN üzerinde şablonları sürümleri

JQuery şablonları eklentisi aşağıdaki sürümleri, bu CDN üzerinde barındırılır. Dosyaların gerçek listesini görmek için her bağlantıyı tıklatın.

- [jQuery şablonları Beta 1](jquery-templates/cdnjquerytemplatesbeta1.md "jQuery şablonları Beta 1")

<a id="jQuery_Cycle_Releases_on_the_CDN_6"></a>

### <a name="jquery-cycle-releases-on-the-cdn"></a>jQuery CDN üzerinde döngüsü sürümleri

JQuery döngüsü eklentisi aşağıdaki sürümleri, bu CDN üzerinde barındırılır. Dosyaların gerçek listesini görmek için her bağlantıyı tıklatın.

- [jQuery döngüsü 2.99](jquery-cycle/cdnjquerycycle299.md "jQuery döngüsü 2.99")
- [jQuery döngüsü 2.94](jquery-cycle/cdnjquerycycle294.md "jQuery döngüsü 2.94")
- [jQuery döngüsü 2.88](jquery-cycle/cdnjquerycycle288.md "jQuery döngüsü 2.88")

<a id="jQuery_DataTables_Releases_on_the_CDN_7"></a>

### <a name="jquery-datatables-releases-on-the-cdn"></a>jQuery CDN üzerinde DataTables sürümleri

JQuery DataTables eklentisi aşağıdaki sürümleri, bu CDN üzerinde barındırılır. Dosyaların gerçek listesini görmek için her bağlantıyı tıklatın.

- [jQuery DataTables 1.10.5](jquery-datatables/cdnjquerydatatables105.md "jQuery DataTables 1.10.5")
- [jQuery DataTables 1.10.4](jquery-datatables/cdnjquerydatatables104.md "jQuery DataTables 1.10.4")
- [jQuery DataTables 1.9.4](jquery-datatables/cdnjquerydatatables194.md "jQuery DataTables 1.9.4")
- [jQuery DataTables 1.9.3](jquery-datatables/cdnjquerydatatables193.md "jQuery DataTables 1.9.3")
- [jQuery DataTables 1.9.2](jquery-datatables/cdnjquerydatatables192.md "jQuery DataTables 1.9.2")
- [jQuery DataTables 1.9.1](jquery-datatables/cdnjquerydatatables191.md "jQuery DataTables 1.9.1")
- [jQuery DataTables 1.9.0](jquery-datatables/cdnjquerydatatables190.md "jQuery DataTables 1.9.0")
- [jQuery DataTables 1.8.2](jquery-datatables/cdnjquerydatatables182.md "jQuery DataTables 1.8.2")

<a id="Modernizr_Releases_on_the_CDN_8"></a>

### <a name="modernizr-releases-on-the-cdn"></a>CDN üzerinde Modernizr sürümleri

Aşağıdaki sürümleri [Modernizr](http://www.modernizr.com "Modernizr") CDN üzerinde barındırılan:

- http://AJAX.aspnetcdn.com/AJAX/Modernizr/Modernizr-2.8.3.js
- http://AJAX.aspnetcdn.com/AJAX/Modernizr/Modernizr-2.7.2.js
- http://AJAX.aspnetcdn.com/AJAX/Modernizr/Modernizr-2.7.1.js
- http://AJAX.aspnetcdn.com/AJAX/Modernizr/Modernizr-2.6.2.js
- http://AJAX.aspnetcdn.com/AJAX/Modernizr/Modernizr-1.7-Development-only.js
- http://AJAX.aspnetcdn.com/AJAX/Modernizr/Modernizr-2.0.6-Development-only.js

<a id="JSHint_Releases_on_the_CDN_10"></a>

### <a name="jshint-releases-on-the-cdn"></a>CDN üzerinde JSHint sürümleri

Aşağıdaki sürümleri [JSHint](http://www.jshint.com "JSHint") CDN üzerinde barındırılan:

- http://AJAX.aspnetcdn.com/AJAX/jshint/r07/jshint.js

<a id="Knockout_Releases_on_the_CDN_11"></a>

### <a name="knockout-releases-on-the-cdn"></a>CDN üzerinde Boşaltılan sürümleri

Aşağıdaki sürümleri [Boşaltılan](http://www.knockoutjs.com "Boşaltılan") CDN üzerinde barındırılan:

- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-2.2.1.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-2.2.1.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-2.2.0.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-2.2.0.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-2.1.0.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-2.1.0.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.0.0.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.0.0.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.1.0.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.1.0.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.2.0.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.2.0.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.3.0.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.3.0.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.4.0.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.4.0.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.4.1.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.4.1.Debug.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.4.2.js
- http://AJAX.aspnetcdn.com/AJAX/knockout/knockout-3.4.2.Debug.js

<a id="Globalize_Releases_on_the_CDN_12"></a>

### <a name="globalize-releases-on-the-cdn"></a>CDN üzerinde sürümleri globalize

Aşağıdaki sürümleri [Globalize](https://github.com/jquery/globalize "Globalize") CDN üzerinde barındırılan:

#### <a name="globalize-version-100"></a>Sürümü 1.0.0 globalize

- http://AJAX.aspnetcdn.com/AJAX/globalize/1.0.0/globalize.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/1.0.0/node-Main.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/1.0.0/globalize/Currency.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/1.0.0/globalize/Date.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/1.0.0/globalize/Message.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/1.0.0/globalize/Number.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/1.0.0/globalize/plural.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/1.0.0/globalize/Relative-Time.js

#### <a name="globalize-version-011"></a>Sürüm 0.1.1 globalize

- http://AJAX.aspnetcdn.com/AJAX/globalize/0.1.1/globalize.Min.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/0.1.1/globalize.js
- http://AJAX.aspnetcdn.com/AJAX/globalize/0.1.1/cultures/globalize.cultures.js

    - tüm kültürler
- http://AJAX.aspnetcdn.com/AJAX/globalize/0.1.1/cultures/globalize.culture. {kültür kodu} .js

    - "{Kodu kültür}" istenen kültürü kod ile değiştirin, örneğin globalize.culture.en GB.js== Microsoft CDN üzerinde dosyaları bu == kitaplıkları, Microsoft tarafından karşıya.

<a id="Respond_Releases_on_the_CDN_13"></a>

### <a name="respond-releases-on-the-cdn"></a>CDN üzerinde sürümleri yanıt

Aşağıdaki sürümleri [https://github.com/scottjehl/Respond](https://github.com/scottjehl/Respond "https://github.com/scottjehl/Respond") yanıt CDN üzerinde barındırılan:

#### <a name="respond-version-142"></a>Sürüm 1.4.2 yanıt

- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.2/Respond.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.2/Respond.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.2/Respond.matchmedia.addListener.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.2/Respond.matchmedia.addListener.Min.js

#### <a name="respond-version-141"></a>Sürüm 1.4.1 yanıt

- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.1/Respond.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.1/Respond.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.1/Respond.matchmedia.addListener.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.1/Respond.matchmedia.addListener.Min.js

#### <a name="respond-version-140"></a>Sürüm 1.4.0 yanıt

- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.0/Respond.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.0/Respond.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.0/Respond.matchmedia.addListener.js
- http://AJAX.aspnetcdn.com/AJAX/Respond/1.4.0/Respond.matchmedia.addListener.Min.js

#### <a name="respond-version-130"></a>Sürüm 1.3.0 yanıt

- http://AJAX.aspnetcdn.com/AJAX/Respond/1.3.0/Respond.js

#### <a name="respond-version-120"></a>Sürüm 1.2.0 yanıt

- http://AJAX.aspnetcdn.com/AJAX/Respond/1.2.0/Respond.js

<a id="Bootstrap_Releases_on_the_CDN_14"></a>

### <a name="bootstrap-releases-on-the-cdn"></a>CDN üzerinde önyükleme sürümleri

Aşağıdaki sürümleri [getbootstrap.com](http://getbootstrap.com "getbootstrap.com") önyükleme CDN üzerinde barındırılan:

#### <a name="bootstrap-version-337"></a>Önyükleme sürüm 3.3.7

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/Fonts/glyphicons-halflings-Regular.woff
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.7/Fonts/glyphicons-halflings-Regular.woff2

#### <a name="bootstrap-version-336"></a>Önyükleme sürüm 3.3.6

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/Fonts/glyphicons-halflings-Regular.woff
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.6/Fonts/glyphicons-halflings-Regular.woff2

#### <a name="bootstrap-version-335"></a>Önyükleme sürüm 3.3.5

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/Fonts/glyphicons-halflings-Regular.woff
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.5/Fonts/glyphicons-halflings-Regular.woff2

#### <a name="bootstrap-version-334"></a>Önyükleme sürüm 3.3.4

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/Fonts/glyphicons-halflings-Regular.woff
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.4/Fonts/glyphicons-halflings-Regular.woff2

#### <a name="bootstrap-version-332"></a>Önyükleme sürüm 3.3.2

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/Fonts/glyphicons-halflings-Regular.woff
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.2/Fonts/glyphicons-halflings-Regular.woff2

#### <a name="bootstrap-version-331"></a>Önyükleme sürüm 3.3.1

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.1/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-330"></a>Önyükleme sürüm 3.3.0

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.3.0/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-320"></a>Önyükleme sürüm 3.2.0

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.2.0/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-311"></a>Önyükleme sürüm 3.1.1

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.1/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-310"></a>Önyükleme sürüm 3.1.0

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/CSS/Bootstrap.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/CSS/Bootstrap-theme.css.map
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.1.0/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-303"></a>Önyükleme sürüm 3.0.3

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.3/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-302"></a>Önyükleme sürüm 3.0.2

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.2/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-301"></a>Önyükleme sürüm 3.0.1

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.1/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-300"></a>Önyükleme sürüm 3.0.0

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/CSS/Bootstrap-theme.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/CSS/Bootstrap-theme.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/Fonts/glyphicons-halflings-Regular.EOT
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/Fonts/glyphicons-halflings-Regular.SVG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/Fonts/glyphicons-halflings-Regular.ttf
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/3.0.0/Fonts/glyphicons-halflings-Regular.woff

#### <a name="bootstrap-version-232"></a>Önyükleme sürüm 2.3.2

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.2/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.2/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.2/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.2/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.2/CSS/Bootstrap-responsive.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.2/CSS/Bootstrap-responsive.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.2/img/glyphicons-halflings.PNG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.2/img/glyphicons-halflings-White.PNG

#### <a name="bootstrap-version-231"></a>Önyükleme sürüm 2.3.1

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.1/Bootstrap.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.1/Bootstrap.Min.js
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.1/CSS/Bootstrap.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.1/CSS/Bootstrap.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.1/CSS/Bootstrap-responsive.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.1/CSS/Bootstrap-responsive.Min.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.1/img/glyphicons-halflings.PNG
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap/2.3.1/img/glyphicons-halflings-White.PNG

<a id="BootstrapTouchCarousel_Releases_on_the_CDN_18"></a>

### <a name="bootstrap-touchcarousel-releases-on-the-cdn"></a>CDN üzerinde önyükleme TouchCarousel sürümleri

Aşağıdaki sürümleri [https://github.com/ixisio/bootstrap-touch-carousel](https://github.com/ixisio/bootstrap-touch-carousel "https://github.com/ixisio/bootstrap-touch-carousel") önyükleme TouchCarousel sürümleri CDN üzerinde barındırılan :

#### <a name="bootstrap-touchcarousel-version-080"></a>Önyükleme TouchCarousel sürüm 0.8.0

- http://AJAX.aspnetcdn.com/AJAX/Bootstrap-Touch-carousel/0.8.0/CSS/Bootstrap-Touch-carousel.css
- http://AJAX.aspnetcdn.com/AJAX/Bootstrap-Touch-carousel/0.8.0/js/Bootstrap-Touch-carousel.js

<a id="Hammerjs_Releases_on_the_CDN_19"></a>

### <a name="hammerjs-releases-on-the-cdn"></a>CDN üzerinde Hammer.js sürümleri

Aşağıdaki sürümleri [http://hammerjs.github.io/](http://hammerjs.github.io/ "http://hammerjs.github.io/") Hammer.js sürümleri CDN üzerinde barındırılan:

#### <a name="hammerjs-version-204"></a>Hammer.js sürüm 2.0.4

- http://AJAX.aspnetcdn.com/AJAX/hammer.js/2.0.4/hammer.js
- http://AJAX.aspnetcdn.com/AJAX/hammer.js/2.0.4/hammer.Min.js
- http://AJAX.aspnetcdn.com/AJAX/hammer.js/2.0.4/hammer.Min.map

<a id="ASPNET_Web_Forms_and_Ajax_Releases_on_the_CDN_15"></a>

### <a name="aspnet-web-forms-and-ajax-releases-on-the-cdn"></a>ASP.NET Web formları ve CDN üzerinde Ajax sürümleri

ASP.NET Ajax kitaplığı aşağıdaki sürümleri üzerinde CDN barındırılır. Dosyaların gerçek listesini görmek için her bağlantıyı tıklatın.

- [ASP.NET Web Forms ve Ajax sürüm 4.5.2](cdnajax452.md "ASP.NET Web Forms ve Ajax 4.5.2")
- [ASP.NET Web Forms ve Ajax sürüm 4](cdnajax4.md "ASP.NET Web Forms ve Ajax 4")
- [ASP.NET Ajax sürüm 3.5](cdnajax35.md "ASP.NET Ajax 3.5")

<a id="ASPNET_MVC_Releases_on_the_CDN_16"></a>

### <a name="aspnet-mvc-releases-on-the-cdn"></a>ASP.NET MVC üzerinde CDN serbest bırakır

Aşağıdaki ASP.NET MVC JavaScript dosyaları bu CDN üzerinde barındırılan:

#### <a name="aspnet-mvc-523"></a>ASP.NET MVC 5.2.3

- http://AJAX.aspnetcdn.com/AJAX/MVC/5.2.3/JQuery.Validate.unobtrusive.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/5.2.3/JQuery.Validate.unobtrusive.Min.js

#### <a name="aspnet-mvc-51"></a>ASP.NET MVC 5.1

- http://AJAX.aspnetcdn.com/AJAX/MVC/5.1/JQuery.Validate.unobtrusive.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/5.1/JQuery.Validate.unobtrusive.Min.js

#### <a name="aspnet-mvc-50"></a>ASP.NET MVC 5.0

- http://AJAX.aspnetcdn.com/AJAX/MVC/5.0/JQuery.Validate.unobtrusive.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/5.0/JQuery.Validate.unobtrusive.Min.js

#### <a name="aspnet-mvc-40"></a>ASP.NET MVC 4.0

- http://AJAX.aspnetcdn.com/AJAX/MVC/4.0/JQuery.Validate.unobtrusive.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/4.0/JQuery.Validate.unobtrusive.Min.js

#### <a name="aspnet-mvc-30"></a>ASP.NET MVC 3.0

- http://AJAX.aspnetcdn.com/AJAX/MVC/3.0/JQuery.unobtrusive-AJAX.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/3.0/JQuery.unobtrusive-AJAX.Min.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/3.0/JQuery.Validate.unobtrusive.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/3.0/JQuery.Validate.unobtrusive.Min.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/3.0/MicrosoftMvcAjax.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/3.0/MicrosoftMvcAjax.Debug.js

#### <a name="aspnet-mvc-20"></a>ASP.NET MVC 2.0

- http://AJAX.aspnetcdn.com/AJAX/MVC/2.0/MicrosoftMvcAjax.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/2.0/MicrosoftMvcAjax.Debug.js

#### <a name="aspnet-mvc-10"></a>ASP.NET MVC 1,0

- http://AJAX.aspnetcdn.com/AJAX/MVC/1.0/MicrosoftMvcAjax.js
- http://AJAX.aspnetcdn.com/AJAX/MVC/1.0/MicrosoftMvcAjax.Debug.js

<a id="ASPNET_SignalR_Releases_on_the_CDN_17"></a>

### <a name="aspnet-signalr-releases-on-the-cdn"></a>ASP.NET SignalR üzerinde CDN serbest bırakır

Aşağıdaki ASP.NET SignalR JavaScript dosyaları bu CDN üzerinde barındırılan:

#### <a name="aspnet-signalr-222"></a>ASP.NET SignalR 2.2.2

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.2.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.2.2.js

#### <a name="aspnet-signalr-221"></a>ASP.NET SignalR 2.2.1

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.2.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.2.1.js

#### <a name="aspnet-signalr-220"></a>ASP.NET SignalR 2.2.0

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.2.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.2.0.js

#### <a name="aspnet-signalr-210"></a>ASP.NET SignalR 2.1.0

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.1.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.1.0.js

#### <a name="aspnet-signalr-203"></a>ASP.NET SignalR 2.0.3

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.0.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.0.3.js

#### <a name="aspnet-signalr-202"></a>ASP.NET SignalR 2.0.2

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.0.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.0.2.js

#### <a name="aspnet-signalr-201"></a>ASP.NET SignalR 2.0.1

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.0.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.0.1.js

#### <a name="aspnet-signalr-200"></a>ASP.NET SignalR 2.0.0

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.0.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-2.0.0.js

#### <a name="aspnet-signalr-113"></a>ASP.NET SignalR 1.1.3

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.1.3.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.1.3.js

#### <a name="aspnet-signalr-112"></a>ASP.NET SignalR 1.1.2

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.1.2.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.1.2.js

#### <a name="aspnet-signalr-111"></a>ASP.NET SignalR 1.1.1

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.1.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.1.1.js

#### <a name="aspnet-signalr-110"></a>ASP.NET SignalR 1.1.0

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.1.0.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.1.0.js

#### <a name="aspnet-signalr-101"></a>ASP.NET SignalR 1.0.1

- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.0.1.Min.js
- http://AJAX.aspnetcdn.com/AJAX/signalr/JQuery.signalr-1.0.1.js

CDN kullanım koşulları hakkında daha fazla bilgi için bkz: [Microsoft Ajax CDN Kullanım Koşulları'nı](https://www.asp.net/terms-of-use "Microsoft Ajax CDN Kullanım Koşulları'nı").
