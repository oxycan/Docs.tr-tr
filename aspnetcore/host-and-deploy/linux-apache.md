---
title: ASP.NET Core Apache ile Linux ana bilgisayar
description: "Apache CentOS üzerinde ters proxy sunucu olarak Kestrel üzerinde çalışan bir ASP.NET Core web uygulaması için HTTP trafiği yönlendirmek için nasıl ayarlanacağını öğrenin."
author: spboyer
manager: wpickett
ms.author: spboyer
ms.custom: mvc
ms.date: 10/19/2016
ms.prod: asp.net-core
ms.technology: aspnet
ms.topic: article
uid: host-and-deploy/linux-apache
ms.openlocfilehash: aa55ecd6dc8169e0e77b3899389ec924b1e1ae4a
ms.sourcegitcommit: a510f38930abc84c4b302029d019a34dfe76823b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="host-aspnet-core-on-linux-with-apache"></a>ASP.NET Core Apache ile Linux ana bilgisayar

Tarafından [Shayne Boyer](https://github.com/spboyer)

Bu kılavuz kullanılarak nasıl ayarlanacağını öğrenin [Apache](https://httpd.apache.org/) ters proxy sunucusu olarak [CentOS 7](https://www.centos.org/) üzerinde çalışan bir ASP.NET Core web uygulaması için HTTP trafiği yönlendirmek için [Kestrel](xref:fundamentals/servers/kestrel). [Mod_proxy uzantısı](http://httpd.apache.org/docs/2.4/mod/mod_proxy.html) ve ilgili modüller sunucunun ters proxy oluşturun.

## <a name="prerequisites"></a>Önkoşullar

1. Sudo ayrıcalığa sahip standart kullanıcı hesabı ile CentOS 7'yi çalıştıran sunucu
2. ASP.NET Core uygulama

## <a name="publish-the-app"></a>Uygulama yayımlama

Bir uygulama olarak yayımlama bir [müstakil dağıtım](/dotnet/core/deploying/#self-contained-deployments-scd) CentOS 7 çalışma zamanı için sürüm yapılandırmasında (`centos.7-x64`). İçeriğini kopyalayın *bin/Release/netcoreapp2.0/centos.7-x64/publish* SCP, FTP veya başka bir dosya aktarım yöntemi kullanarak sunucu klasörüne.

> [!NOTE]
> Bir üretim dağıtım senaryosunda sürekli tümleştirme iş akışı uygulama yayımlama ve varlıkları sunucuya kopyalama işlemlerini yapar. 

## <a name="configure-a-proxy-server"></a>Bir proxy sunucusunu yapılandırın

Ters proxy hizmet veren dinamik web uygulamaları için ortak bir kurulur. Ters proxy HTTP isteği sonlandırır ve ASP.NET uygulamasına iletir.

Bir proxy sunucusu, istemci isteklerini yerine bunları kendisi yerine getiren başka bir sunucuya iletir biridir. Ters proxy genellikle rastgele istemcileri adına sabit bir hedef iletir. Bu kılavuzda, Apache Kestrel ASP.NET Core uygulama hizmet ettiğini aynı sunucu üzerinde çalışan ters proxy yapılandırılmıştır.

### <a name="install-apache"></a>Apache yükleyin

CentOS paketleri en son kararlı sürümlerine güncelleştirin:

```bash
sudo yum update -y
```

Apache web sunucusu üzerinde CentOS tek bir yükleme `yum` komutu:

```bash
sudo yum -y install httpd mod_ssl
```

Komutu çalıştırdıktan sonra çıktı örneği:

```bash
Downloading packages:
httpd-2.4.6-40.el7.centos.4.x86_64.rpm               | 2.7 MB  00:00:01
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
Installing : httpd-2.4.6-40.el7.centos.4.x86_64      1/1 
Verifying  : httpd-2.4.6-40.el7.centos.4.x86_64      1/1 

Installed:
httpd.x86_64 0:2.4.6-40.el7.centos.4

Complete!
```

> [!NOTE]
> Bu örnekte, CentOS 7 sürümü 64-bit olduğundan çıktı httpd.86_64 yansıtır. Apache yüklendiği doğrulamak için çalıştırın `whereis httpd` bir komut isteminden. 

### <a name="configure-apache-for-reverse-proxy"></a>Apache için ters proxy ayarlarını yapılandır

İçinde Apache için yapılandırma dosyalarının bulunduğu `/etc/httpd/conf.d/` dizin. Herhangi dosya ile *.conf* uzantısı modül yapılandırma dosyalarında yanı sıra alfabetik sırada işlenir `/etc/httpd/conf.modules.d/`, herhangi bir yapılandırma içeren modüllerini yüklemek gerekli dosyaları.

Adlı uygulama için bir yapılandırma dosyası oluşturma `hellomvc.conf`:

```
<VirtualHost *:80>
    ProxyPreserveHost On
    ProxyPass / http://127.0.0.1:5000/
    ProxyPassReverse / http://127.0.0.1:5000/
    ErrorLog /var/log/httpd/hellomvc-error.log
    CustomLog /var/log/httpd/hellomvc-access.log common
</VirtualHost>
```

**VirtualHost** düğümü, bir sunucu üzerindeki bir veya daha fazla dosyalarda birden çok kez görüntülenebilir. **VirtualHost** 80 numaralı bağlantı noktasını kullanarak tüm IP adresini dinlemek üzere ayarlayın. Sonraki iki satır varsayılan olarak, bağlantı noktası 5000 127.0.0.1 sunucuda kök proxy istekleri için ayarlanır. Çift yönlü iletişimi için *ProxyPass* ve *ProxyPassReverse* gereklidir.

Günlüğe kaydetme, başına yapılandırılabilir **VirtualHost** kullanarak **hata günlüğüne** ve **CustomLog** yönergeleri. **Hata günlüğü** burada sunucusu günlüklerini hataları, konumu ve **CustomLog** filename ve günlük dosyası biçimini ayarlar. Bu durumda, istek bilgilerini günlüğe nerede budur. Her istek için bir satır vardır.

Dosyayı kaydedin ve yapılandırmayı test etme. Her şeyi geçerse, yanıt olmalıdır `Syntax [OK]`.

```bash
sudo service httpd configtest
```

Apache yeniden başlatın:

```bash
sudo systemctl restart httpd
sudo systemctl enable httpd
```

## <a name="monitoring-the-app"></a>Uygulama izleme

Apache olan şimdi yapılan isteklerini iletmek için kurulumu `http://localhost:80` Kestrel çalışan ASP.NET Core App `http://127.0.0.1:5000`.  Ancak, Apache Kestrel işlemini yönetmek için ayarlanmamış. Kullanım *systemd* ve Başlat ve temel web uygulaması izlemek için bir hizmet dosyası oluşturun. *systemd* , başlatma, durdurma ve işlemlerini yönetme için çok güçlü özellikler sağlayan bir init sistemidir. 


### <a name="create-the-service-file"></a>Hizmet dosyası oluşturma

Hizmet tanımı dosyası oluşturun:

```bash
sudo nano /etc/systemd/system/kestrel-hellomvc.service
```

Uygulama için bir örnek hizmet dosyası:

```
[Unit]
Description=Example .NET Web API App running on CentOS 7

[Service]
WorkingDirectory=/var/aspnetcore/hellomvc
ExecStart=/usr/local/bin/dotnet /var/aspnetcore/hellomvc/hellomvc.dll
Restart=always
# Restart service after 10 seconds if dotnet service crashes
RestartSec=10
SyslogIdentifier=dotnet-example
User=apache
Environment=ASPNETCORE_ENVIRONMENT=Production 

[Install]
WantedBy=multi-user.target
```

> [!NOTE]
> **Kullanıcı** &mdash; , kullanıcı *apache* kullanılmaz yapılandırmanın, kullanıcı ilk oluşturulmalı ve doğru sahipliği dosyaları için verilen.

Dosyayı kaydedin ve hizmeti etkinleştirin:

```bash
systemctl enable kestrel-hellomvc.service
```

Hizmeti başlatın ve çalıştığından emin olun:

```bash
systemctl start kestrel-hellomvc.service
systemctl status kestrel-hellomvc.service

● kestrel-hellomvc.service - Example .NET Web API App running on CentOS 7
    Loaded: loaded (/etc/systemd/system/kestrel-hellomvc.service; enabled)
    Active: active (running) since Thu 2016-10-18 04:09:35 NZDT; 35s ago
Main PID: 9021 (dotnet)
    CGroup: /system.slice/kestrel-hellomvc.service
            └─9021 /usr/local/bin/dotnet /var/aspnetcore/hellomvc/hellomvc.dll
```

Ters proxy yapılandırılmış ve üzerinden yönetilen Kestrel *systemd*, web uygulaması tam olarak yapılandırılmamış ve yerel makinede bir tarayıcıdan erişilebilir `http://localhost`. Yanıt Üstbilgileri incelemek **Server** üstbilgi gösterir ASP.NET Core uygulama tarafından Kestrel sunulur:

```
HTTP/1.1 200 OK
Date: Tue, 11 Oct 2016 16:22:23 GMT
Server: Kestrel
Keep-Alive: timeout=5, max=98
Connection: Keep-Alive
Transfer-Encoding: chunked
```

### <a name="viewing-logs"></a>Günlükleri görüntüleme

Web uygulaması bu yana Kestrel kullanarak kullanılarak yönetilir *systemd*, olaylar ve işlemleri merkezi bir günlüğe kaydedilir. Ancak, bu günlük tüm işlemler tarafından yönetilen ve Hizmetleri için girişleri içerir *systemd*. Görüntülemek için `kestrel-hellomvc.service`-belirli öğeleri, aşağıdaki komutu kullanın:

```bash
sudo journalctl -fu kestrel-hellomvc.service
```

Zaman filtresi uygulamak için komutuyla zaman seçeneklerini belirtin. Örneğin, `--since today` geçerli gün için filtre uygulamak için veya `--until 1 hour ago` önceki saatlik girişlerini görmek için. Daha fazla bilgi için bkz: [journalctl adam sayfa](https://www.unix.com/man-page/centos/1/journalctl/).

```bash
sudo journalctl -fu kestrel-hellomvc.service --since "2016-10-18" --until "2016-10-18 04:00"
```

## <a name="securing-the-app"></a>Uygulama güvenliğini sağlama

### <a name="configure-firewall"></a>Güvenlik duvarını yapılandırma

*Firewalld* ağ bölgeleri için destek ile Güvenlik Duvarı'nı yönetmek için bir dinamik arka plan programı kullanılır. Bağlantı noktaları ve paket filtreleme hala iptables tarafından yönetilebilir. *Firewalld* varsayılan olarak yüklü olması. `yum`paketi yüklemek ya da yüklü doğrulamak için kullanılabilir.

```bash
sudo yum install firewalld -y
```

Kullanım `firewalld` yalnızca uygulama için gerekli bağlantı noktalarını açın. Bu durumda, bağlantı noktası 80 ve 443 kullanılır. Aşağıdaki komutlar, 80 ve 443'ü açmak için bağlantı noktalarını kalıcı olarak ayarlayın:

```bash
sudo firewall-cmd --add-port=80/tcp --permanent
sudo firewall-cmd --add-port=443/tcp --permanent
```

Güvenlik Duvarı ayarlarını yeniden yükleyin. Kullanılabilir hizmetleri ve bağlantı noktalarını varsayılan bölgede denetleyin. Seçenekleri kullanılabilir inceleyerek `firewall-cmd -h`.

```bash 
sudo firewall-cmd --reload
sudo firewall-cmd --list-all
```

```bash
public (default, active)
interfaces: eth0
sources: 
services: dhcpv6-client
ports: 443/tcp 80/tcp
masquerade: no
forward-ports: 
icmp-blocks: 
rich rules: 
```

### <a name="ssl-configuration"></a>SSL yapılandırması

SSL, Apache yapılandırmak için *mod_ssl* modülü kullanılır. Zaman *httpd* modülü yüklendi, *mod_ssl* modülü de yüklendi. Yüklü değildi kullanırsanız `yum` yapılandırmasına eklemek için.

```bash
sudo yum install mod_ssl
```
SSL zorlamak için yükleme `mod_rewrite` modülü URL yeniden yazma işlemi etkinleştirmek için:

```bash
sudo yum install mod_rewrite
```

Değiştirme *hellomvc.conf* dosya URL yeniden yazma işlemi etkinleştirmek ve bağlantı noktası 443 üzerinden iletişimi güvenli hale getirmek için:

```
<VirtualHost *:80>
    RewriteEngine On
    RewriteCond %{HTTPS} !=on
    RewriteRule ^/?(.*) https://%{SERVER_NAME}/ [R,L]
</VirtualHost>

<VirtualHost *:443>
    ProxyPreserveHost On
    ProxyPass / http://127.0.0.1:5000/
    ProxyPassReverse / http://127.0.0.1:5000/
    ErrorLog /var/log/httpd/hellomvc-error.log
    CustomLog /var/log/httpd/hellomvc-access.log common
    SSLEngine on
    SSLProtocol all -SSLv2
    SSLCipherSuite ALL:!ADH:!EXPORT:!SSLv2:!RC4+RSA:+HIGH:+MEDIUM:!LOW:!RC4
    SSLCertificateFile /etc/pki/tls/certs/localhost.crt
    SSLCertificateKeyFile /etc/pki/tls/private/localhost.key
</VirtualHost>
```

> [!NOTE]
> Bu örnek, yerel olarak oluşturulan bir sertifika kullanıyor. **SSLCertificateFile** birincil sertifika dosyası için etki alanı adı olmalıdır. **SSLCertificateKeyFile** CSR oluşturulduğunda anahtar dosyası oluşturulması gerekir. **SSLCertificateChainFile** ara sertifika dosyası (varsa) olmalıdır sertifika yetkilisi tarafından sağlandı.

Dosyayı kaydedin ve test yapılandırması:

```bash
sudo service httpd configtest
```

Apache yeniden başlatın:

```bash
sudo systemctl restart httpd
```

## <a name="additional-apache-suggestions"></a>Ek Apache öneriler

### <a name="additional-headers"></a>Ek üstbilgileri

Kötü amaçlı saldırılara karşı güvenli hale getirmek için ya da değiştirildiğinde veya eklendiğinde birkaç üstbilgileri vardır. Emin `mod_headers` modülü yüklenir:

```bash
sudo yum install mod_headers
```

#### <a name="secure-apache-from-clickjacking-attacks"></a>Clickjacking öğesini saldırılarına karşı güvenli Apache

[Clickjacking öğesini](https://blog.qualys.com/securitylabs/2015/10/20/clickjacking-a-common-implementation-mistake-that-can-put-your-websites-in-danger), olarak da bilinen bir *UI redress saldırı*, bir Web sitesine ziyaretçiyi yere sağladı şu anda ziyaret ettiğiniz daha bir bağlantı veya başka bir sayfaya düğmesine tıklamak amaçlı bir saldırı aracıdır. Kullanım `X-FRAME-OPTIONS` sitesi güvenliğini sağlamak için.

Düzen *httpd.conf* dosyası:

```bash
sudo nano /etc/httpd/conf/httpd.conf
```

Satırı ekleyin `Header append X-FRAME-OPTIONS "SAMEORIGIN"`. Dosyayı kaydedin. Apache yeniden başlatın.

#### <a name="mime-type-sniffing"></a>MIME türü algılaması

`X-Content-Type-Options` Üstbilgi engeller Internet Explorer'dan *MIME algılaması* (bir dosyanın belirleneceği `Content-Type` dosyanın içerikten). Sunucu ayarlarsa `Content-Type` başlığına `text/html` ile `nosniff` seçenek kümesi, Internet Explorer işler içeriği olarak `text/html` dosyanın içeriği ne olursa olsun.

Düzen *httpd.conf* dosyası:

```bash
sudo nano /etc/httpd/conf/httpd.conf
```

Satırı ekleyin `Header set X-Content-Type-Options "nosniff"`. Dosyayı kaydedin. Apache yeniden başlatın.

### <a name="load-balancing"></a>YükDengeleme 

Bu örnekte, Kurulum ve Apache CentOS 7 ve Kestrel aynı örneği makinede yapılandırmak gösterilmektedir. Tek bir hata noktası olmaması için; kullanarak *mod_proxy_balancer* ve değiştirme **VirtualHost** web uygulamaları Apache proxy sunucunun arkasında birden çok örneğini yönetmek için izin verir.

```bash
sudo yum install mod_proxy_balancer
```

Yapılandırma dosyasında ek bir örneği aşağıda gösterilen `hellomvc` 5001 bağlantı noktası üzerinde çalıştırmak için Kurulum uygulamadır. *Proxy* bölüm ayarlanmış iki üyeleriyle dengeleyici yapılandırmasına sahip Yük Dengelemesi *byrequests*.

```
<VirtualHost *:80>
    RewriteEngine On
    RewriteCond %{HTTPS} !=on
    RewriteRule ^/?(.*) https://%{SERVER_NAME}/ [R,L]
</VirtualHost>

<VirtualHost *:443>
    ProxyPass / balancer://mycluster/ 

    ProxyPassReverse / http://127.0.0.1:5000/
    ProxyPassReverse / http://127.0.0.1:5001/

    <Proxy balancer://mycluster>
        BalancerMember http://127.0.0.1:5000
        BalancerMember http://127.0.0.1:5001 
        ProxySet lbmethod=byrequests
    </Proxy>

    <Location />
        SetHandler balancer
    </Location>
    ErrorLog /var/log/httpd/hellomvc-error.log
    CustomLog /var/log/httpd/hellomvc-access.log common
    SSLEngine on
    SSLProtocol all -SSLv2
    SSLCipherSuite ALL:!ADH:!EXPORT:!SSLv2:!RC4+RSA:+HIGH:+MEDIUM:!LOW:!RC4
    SSLCertificateFile /etc/pki/tls/certs/localhost.crt
    SSLCertificateKeyFile /etc/pki/tls/private/localhost.key
</VirtualHost>
```

### <a name="rate-limits"></a>Oran sınırları
Kullanarak *mod_ratelimit*, içinde bulunan *httpd* modülü, bant genişliği istemcilerin olabilir sınırlı:

```bash
sudo nano /etc/httpd/conf.d/ratelimit.conf
```
Örnek dosyası kök konumu altında 600 KB/sn olarak bant genişliği sınırları:

```
<IfModule mod_ratelimit.c>
    <Location />
        SetOutputFilter RATE_LIMIT
        SetEnv rate-limit 600
    </Location>
</IfModule>
```
