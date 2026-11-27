---
title: "Live View'u aracınızın tarayıcısında gösterin"
description: "Browser View, CommaView'un Live View'unu aracınızın kendi web tarayıcısında, Tesla dahil, telefonunuzun hotspot'u üzerinden gösterir. Araca yüklenecek bir şey yok."
topic: screens
order: 2
kind: walkthrough
lede: "**Browser View**, Live View'un gösterdiğini aracınızın kendi web tarayıcısında gösterir. Telefonunuz onu hotspot'u veya Wi‑Fi üzerinden araca sunar; bu yüzden araca yüklenecek bir şey yoktur. Tarayıcısı olup CarPlay veya Android Auto'su olmayan Tesla gibi araçlar için yapıldı ve telefonunuza ulaşabilen her tarayıcıda çalışır."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View çalışıyor"
    text: "Bir Android telefonda, comma'nızla eşleştirilmiş CommaView. Henüz değil mi? [CommaView'u kurun](/tr/guides/setup)."
  - title: "Araçta bir tarayıcı"
    text: "Bir Tesla, web tarayıcısı olan başka bir araç veya araçtaki bir tablet ya da dizüstü bilgisayar."
  - title: "Tek bir ağ"
    text: "Araç ve comma'nız telefonunuzun hotspot'unda veya üçünün paylaştığı herhangi bir ağda."
howItWorks:
  - title: "comma'nız"
    text: "Live View'u her zamanki gibi telefonunuza gönderir."
  - title: "Telefonunuz"
    text: "Görüntüyü sekiz haneli bir kodun arkasında bir web sayfası olarak sunar."
    edge: "hotspot"
  - title: "Aracın tarayıcısı"
    text: "Sayfayı açar: saniyede 20 kare, 720p veya 1080p, en fazla dört tarayıcı."
steps:
  - id: hotspot
    title: "Aracı telefonunuzun hotspot'una bağlayın"
    body: |
      Telefonunuzun hotspot'unu açın, ardından aracı aracın Wi‑Fi ayarlarından ona bağlayın. Aracın zaten bildiği bir Wi‑Fi'a değil, telefonunuza bağlandığını kontrol edin. Henüz bağlı değilse comma'nızı da hotspot'a bağlayın: telefonunuzun her zamanki gibi comma'nıza ihtiyacı var.
    note: "**Tesla'da**, hotspot mobil veriyi paylaşsın diye önce telefonunuzun Wi‑Fi'ını kapatın."
  - id: start
    title: "Browser View'u Live View'un Ayrıntılar'ından başlatın"
    body: |
      Telefonda **Live View**'u, ardından **Ayrıntılar**'ı açın. Sona yakın **Browser View** kartı ne yaptığını ve CommaView'a neyi bildirdiğini söyler. **Başlat**'a dokunun.
    screen: live-view-browser-view
    clip: browser-view-start
    pins:
      - target: browser-view-card
        text: "**Ayrıntılar**'ın sonuna yakın **Browser View** kartı."
      - target: start-button
        text: "**Başlat**. İlk seferde telefona sertifikasını alması için birkaç saniye verin."
      - target: privacy-policy
        text: "Browser View'un çalışırken CommaView'a bildirdikleri ve **Gizlilik politikası**."
  - id: vpn
    title: "Tesla'da VPN adresini açın"
    tabs:
      - label: "Tesla"
        body: |
          Bir Tesla'nın tarayıcısı, hotspot'un verdiği adresleri açmaz. Kartta **VPN adresini aç**'a dokunun ve Android CommaView'un bir VPN kurmasına izin vermenizi istediğinde izin verin. Telefonunuz Tesla'nın açacağı bir adres alır: `169.254.99.1`. Hiçbir trafik taşımaz ve açıkken başka bir VPN uygulaması kapalıdır.
        screen: live-view-browser-view-vpn
        pins:
          - target: short-link
            text: "Tesla için de kısa bağlantı: **Aracın tarayıcısında (Tesla dahil) açın**."
          - target: vpn-address
            text: "Telefonun VPN adresindeki adresleri, `169.254.99.1`."
        note: "Android'in VPN hakkındaki kendi sorusu gösterilmiyor: Android'e aittir ve her telefonda farklı görünür."
      - label: "Başka bir araç"
        body: |
          Burada yapılacak bir şey yok: diğer araçların tarayıcıları hotspot'un adresini açar. Sonraki adıma geçin.
  - id: open
    title: "Kısa bağlantıyı aracın tarayıcısına yazın"
    body: |
      Kart, sekiz haneli kodunuzla kısa bir bağlantı gösterir; örneğin `commaview.app/48291374`. Bunu aracın tarayıcısına yazın ve **Aç**'a dokunun. Araç çevrimiçiyken ve CommaView'a giriş yapılmışken sayfa telefonunuzu bulur ve Live View'u güvenli bir bağlantı üzerinden açar: asma kilit, uyarı yok ve en akıcı görüntü.
    screen: live-view-browser-view-on
    pins:
      - target: short-link
        text: "Araca yazılacak, kodunuzu içeren kısa bağlantı."
      - target: show-addresses
        text: "**Araçta internet yok mu? Adresleri göster**: telefonun kendi adresleri."
      - target: quality
        text: "**Browser View görüntüsü**: 720p veya 1080p."
      - target: stop-button
        text: "**Durdur**, Browser View'u sonlandırır."
    warn: "**Araçta internet yok mu?** Kısa bağlantının internete ihtiyacı var. Bunun yerine telefonun kendi adresini kullanın: [Araçta internet yok](#no-internet-in-the-car) bölümüne bakın."
  - id: bookmark
    title: "Sayfayı yer imlerine ekleyin"
    body: |
      Sayfanın adresi aynı kalır; bu yüzden bir dahaki sefere, araç çevrimiçiyken, kısa bağlantıyı yazmak yerine yer imini açın.
check: "Telefondaki kart kimin izlediğini ve aracın tarayıcısının ne çizdiğini söyler; örneğin **1 tarayıcı izliyor** ve `Tesla 2025.20.6 · H.264 over HTTPS via the VPN name · 20 fps`."
fixes:
  - q: "“Aracın tarayıcısı bekleniyor” ve hiçbir şey açılmıyor"
    a: "Aracın başka bir Wi‑Fi'a değil, telefonunuzun hotspot'una bağlandığını kontrol edin. Tesla'da VPN adresini açın ([3. adım](#step-vpn))."
  - q: "“Hotspot'u bu telefonda açıp aracı ona bağlayın”"
    a: "Telefon ne Wi‑Fi'da ne de aracın paylaşabileceği bir hotspot'ta. Biri açıldıktan sonra 5 saniye içinde adres görünür."
  - q: "Kısa bağlantı VPN adresinin kapalı olduğunu söylüyor"
    a: "Kartta açın, ardından sayfayı yeniden yükleyin."
  - q: "Geçemediğiniz bir uyarı"
    a: "Araç çevrimiçiyken kısa bağlantıyı veya temel görüntüyü kullanın ([Araçta internet yok](#no-internet-in-the-car))."
  - q: "Görüntü D konumunda duruyor"
    a: "Bir aracın tarayıcısının sürüş sırasında çizmeye devam edip etmeyeceği araç üreticisine bağlıdır. Kartın rapor satırı aracın ne çizdiğini söyler (“0 fps · hidden”, aracın durdurduğu bir görüntüdür). Aracınızı ve yazılım sürümünü bize bildirin: sürmeden önce **Tanılamayı sakla (bu telefon)**'u açın, ardından Ayarlar'dan **Sorun bildirin veya fikir gönderin** ile gönderin."
related: [car-screens, ai-box, go-live]
blogPost: commaview-0-0-166-languages-browser-view
---

## Araçta internet yok

Kısa bağlantının sayfası için aracın, hotspot'un mobil verisi veya aracın kendi bağlantısı üzerinden çevrimiçi olması gerekir. Değilse telefonun kendi adresini açın. Kartta **Araçta internet yok mu? Adresleri göster**'e dokunun:

- **En iyi görüntü**, `https://192.168.43.1:8443/48291374` gibi bir HTTPS adresi. Tarayıcı önce uyarır, çünkü bu adresi telefon kendisi imzalar: devam etmek için uyarıyı kabul edin. Tesla'nın tarayıcısı bunu geçmenize izin vermez.
- **Temel görüntü**, aynı adres HTTP üzerinden, örneğin `192.168.43.1:8090/48291374`. Hiçbir tarayıcıda, Tesla'nınkinde de uyarı yok, ama daha düşük kaliteli, daha az akıcı bir görüntü.

VPN adresi açıkken kart bunun yerine onun adreslerini gösterir: `https://169.254.99.1:8443/<code>` ve `169.254.99.1:8090/<code>`. İnterneti olmayan bir Tesla'da temel olanı kullanın.

Telefonunuzun hotspot adresi örnekten farklı olabilir; kart her zaman doğrusunu, her birinin yanında bir Kopyala düğmesiyle gösterir.

## Karttaki seçenekler

- **Browser View görüntüsü: 720p veya 1080p.** 1080p daha keskindir ve telefondan ve hotspot'tan daha fazlasını alır. Siz seçene kadar 720p.
- **Live View ile başlat.** Browser View, Live View her açıldığında, açıksa VPN adresiyle başlar. Durdurursanız Live View yeniden açılana kadar durur.
- **Yeni kod.** Yeni bir sekiz haneli kod oluşturur; böylece başkasının gördüğü bir adres çalışmaz. Yeni adresi araçta açın.
- **Araçtaki kontroller.** Kayıt, Anı kaydet ve Live View'un diğer kontrolleri görüntünün altında veya sürücü tarafında yanında durur, asla üzerinde değil. Karttaki **Araçtaki kontroller** onları kapatır.
- **Sürücü kamerası**, Live View'un **Sürücü kamerası** açıkken araçta da görünür.

## Çalışırken

- **Browser View, telefon kilitliyken** veya başka bir uygulamadayken devam eder. Bildirimi “Live View, Browser View'da gösteriliyor” der ve **Durdur**'u onu sonlandırır.
- **Live View'dan çıkmak onu sonlandırır**; canlı yayını ve canlı kopyaları sonlandırdığı gibi.
- **Browser View'un yanında Yayına başla** onun görüntüsünü paylaşır. Browser View tek başına çalışırken başlatılan bir yayının sesi olmaz: ses için önce Browser View'u durdurun.

## Gizlilik ve güvenlik

- Görüntü yalnızca telefonunuzun hotspot'unda veya Wi‑Fi'ında kodu olan tarayıcılara gider. Asla mobil veri üzerinden ve asla CommaView'un sunucuları üzerinden değil.
- Bir cihazdan bir dakikada on yanlış kod, onu bir dakikalığına dışarıda bırakır; zaten izleyen bir cihaz devam eder.
- Browser View çalışırken telefonunuz, kısa bağlantının telefonunuzu bulabilmesi için CommaView'un hesap hizmetine kodunu, portlarını, VPN adresinin açık olup olmadığını ve hotspot'un veya Wi‑Fi'ın özel adresini gönderir. Kodu olan herkes bunları ve telefonunuzun `commaview.app` adını, Browser View çalışırken ve beklenmedik şekilde durduktan sonra en fazla 2 saat boyunca görebilir; hiçbiri telefonunuzun hotspot'u veya Wi‑Fi'ı olmadan bir şey açmaz. Browser View'un son çalışmasından 30 gün sonra silinirler. Telefonunuzun `commaview.app` adı ve son sertifikasının tarihi hesabınız durdukça kalır. Sertifikalar herkese açıktır, bu yüzden o ad Certificate Transparency günlüklerinde kalır; sizin, aracınız veya comma'nız hakkında hiçbir şey söylemez. Ayrıntılar [gizlilik politikasında](/privacy).
- VPN adresi sizin seçiminizdir, asla kendiliğinden açılmaz ve hiçbir trafik taşımaz.

## Sorular

**Bir AI box'a veya yeni bir multimedya ünitesine ihtiyacım var mı?** Hayır. Browser View aracınızda zaten olan tarayıcıyı kullanır. Aracınızda bunun yerine CarPlay veya Android Auto varsa bir [Android AI box](/blog/android-ai-box-commaview), CommaView'u aracın kendi ekranında çalıştırabilir.

**Mobil verimi kullanır mı?** Görüntü kullanmaz: telefondan araca hotspot üzerinden gider. Kısa bağlantının sayfası ve aracın hotspot'u kendi kullanımı kullanır.

**Bunu telefonumunki yerine comma'mın hotspot'u yapabilir mi?** Çoğu tarayıcı için evet: telefonu ve aracı comma'nın hotspot'una bağlayın ve kartın gösterdiği adresi açın. Tesla'nın, yalnızca telefonun kendi hotspot'undaki bir araç için çalışan VPN adresine ihtiyacı vardır.

## Güvenlik

Browser View'u park hâlinde kurun, sonra kendi hâline bırakın. Sürerken CommaView'u kullanmayın: openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun. comma'nızın kendi uyarıları ve aracınızın göstergeleri önce gelir. CommaView yalnızca comma'nın gördüğünü gösterir.
