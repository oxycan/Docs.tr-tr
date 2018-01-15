---
uid: whitepapers/ms03-32-issue
title: "IE güvenlik güncelleştirmesi uyguladıktan sonra 'Sunucu uygulaması kullanılamıyor' hata düzeltme | Microsoft Docs"
author: rick-anderson
description: "Bu yazı Wi üzerinde çalışan ASP.NET 1.0 uygulamaları etkiler Internet Explorer için MS03-32 güvenlik güncelleştirmesiyle bir sorunu giderir düzeltme eki açıklar..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 02/10/2010
ms.topic: article
ms.assetid: 1365eebb-bdf7-4a05-8d18-7f200531be55
ms.technology: 
ms.prod: .net-framework
msc.legacyurl: /whitepapers/ms03-32-issue
msc.type: content
ms.openlocfilehash: 8658e387aeb4ea0340080666906b2b89db49a31a
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="fix-for-server-application-unavailable-error-after-applying-security-update-for-ie"></a><span data-ttu-id="68122-103">IE güvenlik güncelleştirmesi uygulandıktan sonra 'Sunucu uygulaması kullanılamıyor' hata düzeltme</span><span class="sxs-lookup"><span data-stu-id="68122-103">Fix for 'Server Application Unavailable' Error after Applying Security Update for IE</span></span>
====================
> <span data-ttu-id="68122-104">Bu yazı, Windows XP Professional üzerinde çalışan ASP.NET 1.0 uygulamaları etkiler Internet Explorer için MS03-32 güvenlik güncelleştirmesiyle bir sorunu giderir düzeltme eki açıklar.</span><span class="sxs-lookup"><span data-stu-id="68122-104">This paper describes the patch that fixes an issue with the MS03-32 Security Update for Internet Explorer that affects ASP.NET 1.0 applications running on Windows XP Professional.</span></span>
> 
> <span data-ttu-id="68122-105">ASP.NET 1.0 ve Windows XP Professional için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="68122-105">Applies to ASP.NET 1.0 and Windows XP Professional.</span></span>


<span data-ttu-id="68122-106">Microsoft Internet Explorer Güvenlik Düzeltme Eki MS03-32 güvenlik güncelleştirmesi ve Windows XP'de çalışan ASP.NET 1.0 ile ilgili bir sorun tanımlamıştır.</span><span class="sxs-lookup"><span data-stu-id="68122-106">Microsoft identified an issue with the MS03-32 Security Update for Internet Explorer security patch and ASP.NET 1.0 running on Windows XP.</span></span> <span data-ttu-id="68122-107">Bu düzeltme eki el ile veya son kritik güncelleştirmeler Windows Update sitesinden alma yüklenebilir.</span><span class="sxs-lookup"><span data-stu-id="68122-107">This patch can be installed manually or by obtaining recent critical updates from the Windows Update site.</span></span>

<span data-ttu-id="68122-108">Bu sorunu düzeltme eki Windows XP makineye yükledikten sonra yerel IIS 5.1 web sunucusunda çalışan ASP.NET uygulamaları için tüm istekleri "Sunucu uygulaması kullanılamıyor" bildiren bir hata iletisi neden belirtisidir.</span><span class="sxs-lookup"><span data-stu-id="68122-108">The symptom of this issue is that after installing the patch on a Windows XP machine, all requests to ASP.NET applications running on the local IIS 5.1 web server result in an error message saying "Server Application Unavailable".</span></span> <span data-ttu-id="68122-109">Uzak web sunucularının isteklerine etkilenmez.</span><span class="sxs-lookup"><span data-stu-id="68122-109">Requests to remote web servers are unaffected.</span></span>

<span data-ttu-id="68122-110">Bu sorun yalnızca ASP.NET 1.0 Windows XP çalıştıran yüklemeleri etkiler.</span><span class="sxs-lookup"><span data-stu-id="68122-110">This issue only impacts installations running ASP.NET 1.0 on Windows XP.</span></span> <span data-ttu-id="68122-111">Windows 2000 veya Windows Server 2003 çalıştıran makineleri etkilemez.</span><span class="sxs-lookup"><span data-stu-id="68122-111">It does not impact machines running Windows 2000 or Windows Server 2003.</span></span> <span data-ttu-id="68122-112">Ayrıca ASP.NET 1.1 yüklenen Windows XP çalıştıran makineleri etkilemez.</span><span class="sxs-lookup"><span data-stu-id="68122-112">It also does not impact machines running Windows XP with ASP.NET 1.1 installed.</span></span>

<span data-ttu-id="68122-113">Lütfen unutmayın bu sorunu **değil** güvenlik hata ASP.NET ile.</span><span class="sxs-lookup"><span data-stu-id="68122-113">Please note that this issue **is not** a security bug with ASP.NET.</span></span> <span data-ttu-id="68122-114">Bu **yok** açık veya herhangi bir ASP.NET uygulaması veya sunucu kötü amaçlı saldırıları izin verin.</span><span class="sxs-lookup"><span data-stu-id="68122-114">It **does not** open up or allow any malicious attacks against an ASP.NET application or server.</span></span> <span data-ttu-id="68122-115">Bunun yerine, bu düzeltme ekiyle neden zamanıyla ilgili bir işlev hatasıdır.</span><span class="sxs-lookup"><span data-stu-id="68122-115">Instead, it is purely a functional bug caused by the patch itself.</span></span>

<span data-ttu-id="68122-116">Sabit Bu sorun için kalıcı bir çözüm üzerinde çalışıyoruz.</span><span class="sxs-lookup"><span data-stu-id="68122-116">We are working hard on a permanent solution for this issue.</span></span> <span data-ttu-id="68122-117">Bu arada, sorun için geçici çözüm olarak aşağıdaki toplu iş dosyasını çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="68122-117">In the meantime, you can execute the following batch file as a workaround for the issue.</span></span> <span data-ttu-id="68122-118">Toplu iş dosyası şunları yapar:</span><span class="sxs-lookup"><span data-stu-id="68122-118">The batch file does the following:</span></span>

1. <span data-ttu-id="68122-119">IIS ve ASP.NET durum hizmetleri durdurur</span><span class="sxs-lookup"><span data-stu-id="68122-119">Stops the IIS and ASP.NET state services</span></span>
2. <span data-ttu-id="68122-120">Siler ve bilinen bir geçici parola ASPNET hesabıyla yeniden oluşturur</span><span class="sxs-lookup"><span data-stu-id="68122-120">Deletes and recreates the ASPNET account with a known temporary password</span></span>
3. <span data-ttu-id="68122-121">Windows kullanan `runas` bir ASP.NET kullanıcı profili oluşturan bir yürütülebilir dosya başlatmak için komut</span><span class="sxs-lookup"><span data-stu-id="68122-121">Uses the Windows `runas` command to launch an executable that creates an ASPNET user profile</span></span>
4. <span data-ttu-id="68122-122">ASP.NET yeniden kaydeder.</span><span class="sxs-lookup"><span data-stu-id="68122-122">Re-registers ASP.NET.</span></span> <span data-ttu-id="68122-123">Bu hesap için yeni rastgele bir parola oluşturur ve bunu için varsayılan ASP.NET erişim denetimi ayarlarını uygular</span><span class="sxs-lookup"><span data-stu-id="68122-123">This creates a new random password for the account and applies default ASP.NET access control settings for it</span></span>
5. <span data-ttu-id="68122-124">IIS hizmetini yeniden başlatır</span><span class="sxs-lookup"><span data-stu-id="68122-124">Restarts the IIS service</span></span>

<span data-ttu-id="68122-125">Toplu iş dosyası, sabit kodlanmış geçici bir parola içeren "**1pass@word**", olacağı toplu iş dosyasını çalıştırdığınızda runas komutunu için girmesi istenir.</span><span class="sxs-lookup"><span data-stu-id="68122-125">The batch file contains a hardcoded temporary password of "**1pass@word**" which you will be prompted to enter for the runas command when the batch file is run.</span></span> <span data-ttu-id="68122-126">Runas komutunu tamamlandıktan sonra ASPNET hesabı parolası güçlü rastgele bir değeri ile yeniden oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="68122-126">After the runas command completes, the ASPNET account password is recreated with a strong random value.</span></span> <span data-ttu-id="68122-127">Sabit kodlanmış parola ortamınızdaki parola karmaşıklık gereksinimlerini karşılamıyorsa toplu iş dosyasını başlatılamayabilir unutmayın.</span><span class="sxs-lookup"><span data-stu-id="68122-127">Note that the batch file may fail if the hardcoded password does not meet the password complexity requirements in your environment.</span></span> <span data-ttu-id="68122-128">Bu durumda, ortamınız için uygun olan başka bir değer değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="68122-128">If that's the case, you can change it to another value that is appropriate for your environment.</span></span>

<span data-ttu-id="68122-129">*> [!IMPORTANT]*Özel erişim denetimi ayarlarını veya ASP.NET hesabından veritabanı hesap izinlerini eklediyseniz, bu toplu iş dosyası tamamlandıktan sonra yeniden oluşturulması gerekir.</span><span class="sxs-lookup"><span data-stu-id="68122-129">*> [!IMPORTANT]* If you have added custom access control settings or database account permissions for the ASPNET account, they will need to be recreated after this batch file completes.</span></span> <span data-ttu-id="68122-130">Hesabı yeniden oluşturulduğunda, yeni bir güvenlik tanımlayıcısı (SID) alırsınız olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="68122-130">This is because when the account is recreated, it will get a new security identifier (SID).</span></span>

<span data-ttu-id="68122-131">*> [!IMPORTANT]*Ardından ASP.NET hesabından farklı özel bir hesap ile ASP.NET çalışan işlemi çalıştırıyorsanız, bu toplu iş dosyası çalışmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="68122-131">*> [!IMPORTANT]* If you are running the ASP.NET worker process with a custom account other than the ASPNET account, then you should not run this batch file.</span></span> <span data-ttu-id="68122-132">Bunun yerine, etkileşimli olarak oturum açın veya bu hesap için bir kullanıcı profili oluşturacak olan bu hesapla runas komutunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="68122-132">Instead, you should log in interactively or use the runas command with that account which will create a user profile for that account.</span></span>

<span data-ttu-id="68122-133">Toplu iş dosyasını aşağıdaki kendiliğinden açılan arşive eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="68122-133">The batch file is included in the self-extracting archive below.</span></span> <span data-ttu-id="68122-134">Kullanmak için:</span><span class="sxs-lookup"><span data-stu-id="68122-134">To use it:</span></span>

1. <span data-ttu-id="68122-135">Yönetici ayrıcalıklarına sahip bir hesap gibi çalıştırmalıdır</span><span class="sxs-lookup"><span data-stu-id="68122-135">You must be running as an account with Administrator privileges</span></span>
2. [<span data-ttu-id="68122-136">İndirin ve kendiliğinden açılan yürütülebilir dosyasını açın</span><span class="sxs-lookup"><span data-stu-id="68122-136">Download and open the self-extracting executable file</span></span>](ms03-32-issue/_static/fixup1.exe)
3. <span data-ttu-id="68122-137">C:\ içeriği Ayıkla</span><span class="sxs-lookup"><span data-stu-id="68122-137">Extract the contents to c:\\</span></span>
4. <span data-ttu-id="68122-138">Select... Başlat menüsünden çalıştırın ve girin`cmd.exe`</span><span class="sxs-lookup"><span data-stu-id="68122-138">Select Run... from the start menu, and enter `cmd.exe`</span></span>
5. <span data-ttu-id="68122-139">Aç komutu Windows'da yazın `c:\fixup.cmd`.</span><span class="sxs-lookup"><span data-stu-id="68122-139">In the open command windows, type `c:\fixup.cmd`.</span></span>
6. <span data-ttu-id="68122-140">İstendiğinde, girin  **1pass@word**  ve parola olarak.</span><span class="sxs-lookup"><span data-stu-id="68122-140">When prompted, enter **1pass@word** as the password.</span></span>
7. <span data-ttu-id="68122-141">Daha önce özel erişim denetimi ayarlarını veya veritabanı hesap izinlerini ASPNET hesabı varsa, bu ayarları şimdi yeniden uygulanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="68122-141">If you have previously custom access control settings or database account permissions for the ASPNET account, you'll need to re-apply these settings now.</span></span>

<span data-ttu-id="68122-142">Birçok bu neden bu sorundan dolayı özür.</span><span class="sxs-lookup"><span data-stu-id="68122-142">Many apologies for the inconvenience that this has caused.</span></span> <span data-ttu-id="68122-143">Kullanılabilir olduğunda size ek bilgi gönderin.</span><span class="sxs-lookup"><span data-stu-id="68122-143">We'll post additional information as it becomes available.</span></span>

<span data-ttu-id="68122-144">Matris platformları ve bu sorundan etkilenen sürümleri ayrıntıları.</span><span class="sxs-lookup"><span data-stu-id="68122-144">The matrix below details platforms and versions impacted by this issue.</span></span>

| <span data-ttu-id="68122-145">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="68122-145">.NET Framework</span></span> | <span data-ttu-id="68122-146">Platform</span><span class="sxs-lookup"><span data-stu-id="68122-146">Platform</span></span> | <span data-ttu-id="68122-147">Etkilenen</span><span class="sxs-lookup"><span data-stu-id="68122-147">Affected</span></span> |
| --- | --- | --- |
| <span data-ttu-id="68122-148">Sürüm 1.0</span><span class="sxs-lookup"><span data-stu-id="68122-148">Version 1.0</span></span> | <span data-ttu-id="68122-149">Windows 2000 Professional</span><span class="sxs-lookup"><span data-stu-id="68122-149">Windows 2000 Professional</span></span> | <span data-ttu-id="68122-150">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-150">No</span></span> |
| <span data-ttu-id="68122-151">Sürüm 1.0</span><span class="sxs-lookup"><span data-stu-id="68122-151">Version 1.0</span></span> | <span data-ttu-id="68122-152">Windows 2000 Server</span><span class="sxs-lookup"><span data-stu-id="68122-152">Windows 2000 Server</span></span> | <span data-ttu-id="68122-153">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-153">No</span></span> |
| <span data-ttu-id="68122-154">Sürüm 1.0</span><span class="sxs-lookup"><span data-stu-id="68122-154">Version 1.0</span></span> | <span data-ttu-id="68122-155">Windows XP Professional</span><span class="sxs-lookup"><span data-stu-id="68122-155">Windows XP Professional</span></span> | <span data-ttu-id="68122-156">Evet</span><span class="sxs-lookup"><span data-stu-id="68122-156">Yes</span></span> |
| <span data-ttu-id="68122-157">Sürüm 1.0</span><span class="sxs-lookup"><span data-stu-id="68122-157">Version 1.0</span></span> | <span data-ttu-id="68122-158">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="68122-158">Windows Server 2003</span></span> | <span data-ttu-id="68122-159">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-159">No</span></span> |
| <span data-ttu-id="68122-160">Sürüm 1.0</span><span class="sxs-lookup"><span data-stu-id="68122-160">Version 1.0</span></span> | <span data-ttu-id="68122-161">Windows XP Home Cassini ile</span><span class="sxs-lookup"><span data-stu-id="68122-161">Windows XP Home with Cassini</span></span> | <span data-ttu-id="68122-162">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-162">No</span></span> |
| <span data-ttu-id="68122-163">Sürüm 1.1</span><span class="sxs-lookup"><span data-stu-id="68122-163">Version 1.1</span></span> | <span data-ttu-id="68122-164">Windows 2000 Professional</span><span class="sxs-lookup"><span data-stu-id="68122-164">Windows 2000 Professional</span></span> | <span data-ttu-id="68122-165">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-165">No</span></span> |
| <span data-ttu-id="68122-166">Sürüm 1.1</span><span class="sxs-lookup"><span data-stu-id="68122-166">Version 1.1</span></span> | <span data-ttu-id="68122-167">Windows 2000 Server</span><span class="sxs-lookup"><span data-stu-id="68122-167">Windows 2000 Server</span></span> | <span data-ttu-id="68122-168">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-168">No</span></span> |
| <span data-ttu-id="68122-169">Sürüm 1.1</span><span class="sxs-lookup"><span data-stu-id="68122-169">Version 1.1</span></span> | <span data-ttu-id="68122-170">Windows XP Professional</span><span class="sxs-lookup"><span data-stu-id="68122-170">Windows XP Professional</span></span> | <span data-ttu-id="68122-171">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-171">No</span></span> |
| <span data-ttu-id="68122-172">Sürüm 1.1</span><span class="sxs-lookup"><span data-stu-id="68122-172">Version 1.1</span></span> | <span data-ttu-id="68122-173">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="68122-173">Windows Server 2003</span></span> | <span data-ttu-id="68122-174">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-174">No</span></span> |
| <span data-ttu-id="68122-175">Sürüm 1.1</span><span class="sxs-lookup"><span data-stu-id="68122-175">Version 1.1</span></span> | <span data-ttu-id="68122-176">Windows XP Home Cassini ile</span><span class="sxs-lookup"><span data-stu-id="68122-176">Windows XP Home with Cassini</span></span> | <span data-ttu-id="68122-177">Hayır</span><span class="sxs-lookup"><span data-stu-id="68122-177">No</span></span> |

<span data-ttu-id="68122-178">teşekkürler</span><span class="sxs-lookup"><span data-stu-id="68122-178">Thanks,</span></span>   
 <span data-ttu-id="68122-179">ASP.NET ekibi</span><span class="sxs-lookup"><span data-stu-id="68122-179">The ASP.NET Team</span></span>