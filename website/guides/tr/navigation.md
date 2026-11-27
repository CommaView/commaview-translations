---
title: "Kendi Stadia Maps anahtarınızla yol tarifi alın"
description: "Stadia Maps anahtarınızı ekleyin, Ana sayfa'da bir yer arayın, bir rota seçin ve Live View'da dönüş kartını ve sesli komutları izleyin. Yeri comma'nıza da gönderin."
topic: navigation
order: 1
kind: walkthrough
lede: "**Navigasyon**, Live View'da sizi bir yere yönlendirir. Ana sayfa'da **Nereye?** ile arayın, bir rota seçin, **Başlat**'a dokunun, ardından dönüş kartını ve sesli komutları izleyin. Rotalar, telefonunuzda şifreli kalan kendi anahtarınızla Stadia Maps'ten gelir. Yönlendirme yalnızca gösterim içindir ve aracı asla kontrol etmez."
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "Giriş yapılmış"
    text: "CommaView 0.0.167 veya üstü, beta hesabınızla giriş yapılmış. Çıkış yapılmışken navigasyon sunulmaz."
  - title: "Bir Stadia Maps anahtarı"
    text: "Kendi Stadia Maps hesabınızdan bir API anahtarı. Rotalar hesabınız ve koşulları altında istenir."
  - title: "Araç konumu açık"
    text: "Yönlendirme comma'nızın GPS'ini izler. Ana sayfa'da comma'nız için **Araç konumu**'nu açın."
  - title: "Telefonunuzda internet"
    text: "Aramalar ve rotalar için. comma'nın Wi‑Fi'ında internet yoksa mobil veri üzerinden gider."
howItWorks:
  - title: "Nereye?"
    text: "OpenStreetMap verilerinden (Photon) comma'nızın yakınındaki yerleri bulur."
    edge: "anahtarınız"
  - title: "Stadia Maps"
    text: "Telefonunuzun anahtarınızla istediği rotaları planlar. Hiçbir şey CommaView üzerinden geçmez."
  - title: "Live View"
    text: "comma'nızın konumundan sizi yönlendirir: dönüş kartı, harita ve sesli komutlar."
steps:
  - id: open
    title: "Haritalar ve navigasyon'u açın"
    body: |
      **Ayarlar**'a, ardından **Haritalar ve navigasyon**'a dokunun. Giriş yapılmışken eskiden Çevrimdışı haritaların bulunduğu satırdır.
    screen: support-settings
    pins:
      - target: maps-row
        text: "**Haritalar ve navigasyon**."
  - id: get-key
    title: "Stadia Maps'ten bir anahtar alın"
    body: |
      **Stadia Maps anahtarınız** altında **API anahtarı** **Eklenmedi** der. **Stadia Maps'ten anahtar alın**'a dokunun: Stadia'nın kayıt sayfasını tarayıcınızda açar. Kaydolun, ardından API anahtarınızı Stadia Maps panelinizden kopyalayın.
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**Stadia Maps anahtarınız**: “Rotalar kendi Stadia Maps anahtarınızı gerektirir…”"
      - target: get-key
        text: "**Stadia Maps'ten anahtar alın**, Stadia'nın kayıt sayfasını açar."
      - target: add-key
        text: "Anahtarınızı kopyaladıktan sonra **Ekle**."
    note: "Stadia'nın sitesi gösterilmiyor: onlara ait. Paneli anahtarınızın kullanımını, planını ve sınırlarını gösterir."
  - id: add-key
    title: "Yapıştırın, ardından Denetle ve kaydet"
    body: |
      CommaView'a dönüp **Ekle**'ye dokunun. Anahtarınızı alana koymak için **Yapıştır**'a, ardından **Denetle ve kaydet**'e dokunun. CommaView, anahtarı denetlemek için Stadia Maps'ten sabit iki nokta arasında, size ait hiçbir şey içermeyen kısa bir rota ister: **Stadia Maps ile denetleniyor…**. Kabul edildiğinde **API anahtarı** onu maskeli gösterir, örneğin **•••• e1f0**.
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "Maskeli **Stadia Maps API anahtarınız**."
      - target: paste
        text: "Panodan **Yapıştır**."
      - target: check-and-save
        text: "**Denetle ve kaydet**."
    note: "“Yalnızca bu telefonda, şifreli olarak tutulur. Saklanmadan önce Stadia Maps'e kısa bir rotayla denetlenir.” Asla bir destek paketinde veya çökme raporunda yer almaz."
  - id: where-to
    title: "Ana sayfa'da Nereye?'ye dokunun"
    body: |
      Park hâlinde, Ana sayfa'da comma'nızın kartının altındaki **Nereye?**'ye dokunun. Bir yer veya adres yazın ya da söylemek için mikrofona dokunun. Kaydettikten sonra **Ev** ve **İş** kartta tek dokunuş uzaklıktadır.
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**Nereye?** aramayı açar."
      - target: voice
        text: "**Nereye? (sesle)**."
      - target: home-chip
        text: "Kaydettikten sonra **Ev**."
  - id: pick
    title: "Yeri seçin"
    body: |
      Sonuçlar comma'nızın yakınındadır, her biri adresi ve mesafesiyle; ardından kayıtlı ve son yerleriniz gelir. İstediğinize dokunun.
    screen: navigation-search
    pins:
      - target: search-field
        text: "**Yer veya adres arayın**."
      - target: first-result
        text: "comma'nızdan adresi ve mesafesiyle bir sonuç."
    note: "Araç hareket ederken yazma kapalıdır: “Araç hareket ederken yazma kapalıdır. Sesi veya kayıtlı bir yeri kullanın.”"
  - id: start
    title: "Bir rota seçin ve Başlat'a dokunun"
    body: |
      Rota önizlemesi rotayı bir haritada, süreyi, mesafeyi ve ne zaman varacağınızı gösterir. Her rotanın bir etiketi vardır: **En hızlı**, **Rota 2** ve benzeri. **Başlat**'a dokunun: yönlendirme başlar ve Live View açılır.

      **Ev olarak kaydet** ve **İş olarak kaydet**, yeri Ana sayfa'da tek dokunuşla kullanmak için saklar.
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "Rotalar: **En hızlı**, **Rota 2**…"
      - target: start
        text: "**Başlat**."
      - target: save-home
        text: "**Ev olarak kaydet** ve yanında **İş olarak kaydet**."
  - id: follow
    title: "Live View'da izleyin"
    body: |
      Dönüş kartı sonraki dönüşü gösterir: oku, mesafeyi, talimatı ve ondan sonraki adımı, ayrıca ne zaman varacağınızı. Her dönüşten yaklaşık 20 saniye önce bir sesli komut, hemen öncesinde bir tane daha ve vardığınızda bir tane gelir. CommaView'un kendi sürüş ekranında şeridinize ve dönüşün çıkışına şerit okları çizilir.

      Bir dönüşü kaçırırsanız birkaç saniye içinde yeni bir rota gelir. Yolculuk, vardıktan ve aracı kapattıktan sonra kendiliğinden biter.
    tabs:
      - label: "Telefon"
        body: |
          Dik tutulduğunda dönüş kartı ve harita videonun altındadır.
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "Dönüş kartı."
          - target: end
            text: "**Navigasyonu bitir**."
          - target: mute
            text: "**Yönlendirme sesini kapat**."
          - target: map-button
            text: "**Harita**, yolculuk için haritayı gizler ve geri getirir."
      - label: "Araç ekranı"
        body: |
          Bir multimedya ünitesinde, videonun yanında yer olduğunda harita ve dönüş kartı orada kendi panellerinde durur. Yer olmadığında CommaView'un ekranı haritayı videonun köşesine harmanlar. Panelin genişliğini değiştirmek için ayırıcıyı sürükleyin.
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "Dönüş kartı."
          - target: divider
            text: "Haritanın genişliğini değiştirmek için ayırıcı."
          - target: map-button
            text: "**Harita**."
    warn: "Yolculuğu park hâlinde ayarlayın. Sürerken CommaView'da dokunarak gezinmeyin: dönüş kartı ve ses bunu yapmanıza gerek kalmasın diye var; openpilot'un ve aracınızın kendi uyarıları önce gelir."
  - id: send
    title: "Fork'unuz kabul ediyorsa yeri comma'nıza gönderin"
    body: |
      **Başlat**'ın altında rota önizlemesinde, kendi navigasyonu bir varış noktası kabul eden fork'lar için **comma'ya gönder** bulunur: StarPilot, carrotpilot ve openpilot'un navigasyonu (alfa), ondan gelen sunnypilot'unki ile. Diğer fork'lar bunu göstermez.

      Dokunun. CommaView önce sorar ve fork'un şu anki ayarlarıyla sürüşe ne yaptığını söyler; örneğin dönüşler için yavaşlamak. **Gönder**'e dokunun: “comma'nıza gönderildi. StarPilot orada kendi rotasını planlar.” Fork kendi hizmetiyle rota oluşturur; bu yüzden rotası CommaView'unkinden farklı olabilir. **comma'dan sil** onu kaldırır, yolculuğu bitirmek de siler.
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**Gönder**."
    note: "comma'ya gönder'in altındaki **Her yolculuğu bu comma'ya gönder**, Başlat'a dokunduğunuzda her yolculuğu gönderir. Fork'un sürüş ayarları değişirse siz yeniden onaylayana kadar kendiliğinden duraklar."
check: "**Haritalar ve navigasyon**'da **API anahtarı** anahtarınızı maskeli gösterir ve rota önizlemesi **Rota: Stadia Maps · Yönlendirme yalnızca gösterim içindir ve aracı asla kontrol etmez.** der."
fixes:
  - q: "“Rota almak için kendi Stadia Maps anahtarınızı ekleyin: Ayarlar › Haritalar ve navigasyon.”"
    a: "Henüz bir anahtar saklanmadı. Rota önizlemesinde **Anahtarınızı ekleyin**'e dokunun veya [2. ve 3. adımları](#step-get-key) izleyin. Nereye?, arama ve yerler anahtarsız çalışır."
  - q: "“Stadia Maps bu anahtarı kabul etmedi (401). Panelinizden tam olarak kopyalandığını kontrol edin.”"
    a: "Anahtarı Stadia Maps panelinizden eksiksiz olarak yeniden kopyalayın ve bir kez daha yapıştırın."
  - q: "“Bu bir Stadia Maps anahtarı değil.”"
    a: "Yapıştırdığınız şey bir API anahtarı biçiminde değil, bu yüzden hiçbir şey gönderilmedi. API anahtarını Stadia Maps panelinizden kopyalayın: harfler, rakamlar ve tireler."
  - q: "“Stadia Maps bu anahtarı reddetti (403): planı rota hizmetini içermiyor olabilir.”"
    a: "Stadia Maps panelinizde planınızı kontrol edin."
  - q: "“Stadia Maps anahtarınız sınırını aştı (429)”"
    a: "Bu ayın kredileri bitti veya az önce çok sık istekte bulunuldu. Stadia Maps panelinizden kontrol edin. Uygulama beş dakika boyunca onunla yeniden istekte bulunmaz."
  - q: "“Anahtarı denetlemek için Stadia Maps'e ulaşılamadı. İnternet bağlantısını bu telefonda kontrol edip yeniden deneyin.”"
    a: "Telefonunuzda şu anda internet yok. Mobil veriyle veya internete çıkan bir Wi‑Fi ile yeniden deneyin."
  - q: "Ana sayfa'da **Nereye?** yok"
    a: "Navigasyon, CommaView 0.0.167'den itibaren giriş yapmış üyeler içindir. Çıkış yapılmışken veya geçerliliği doğrulanmayan bir erişim hakkıyla sunulmaz. Çin anakarasında kapalıdır."
  - q: "Dönüş kartı “Araç konumu kapalı” diyor"
    a: "Yönlendirmenin comma'nızın konumuna ihtiyacı var. Ana sayfa'da bu comma için **Araç konumu**'nu açın."
  - q: "Dönüş kartı “GPS bekleniyor” diyor"
    a: "Yönlendirme comma'nızın ilk konum tespitiyle başlar. Açık gökyüzü altında biraz zaman tanıyın."
  - q: "“Bu, tek bir yolculuk için çok uzak”"
    a: "Navigasyon en fazla 1.500 km (930 mil) uzaktaki yerlere rota planlar. Yol üzerinde bir durak seçin, sonra oradan devam edin."
  - q: "**comma'ya gönder** yok"
    a: "Yalnızca rota önizlemesinde ve yalnızca navigasyonu bir varış noktası kabul eden bir fork için görünür: StarPilot, carrotpilot ya da openpilot'un veya sunnypilot'un navigasyonu (alfa)."
  - q: "“Bu yolculuğu göndermek için comma'nıza ulaşılamıyor.”"
    a: "Bu telefonu comma'nızla aynı ağa bağlayın, ardından **Yeniden dene**'ye dokunun."
  - q: "“openpilot'un navigasyonu (alfa) comma'nızda kapalı.”"
    a: "Park hâlinde **Navigasyonu (alfa) aç**'a dokunun. Her başlangıçta onu kapatan sürüm yapılarında henüz açık tutulamaz."
related: [live-view, car-screens, overlays]
---

## Live View'da harita

**Ayarlar › Haritalar ve navigasyon › Live View haritası** nereye gideceğini seçer:

- **Yerleşim**: **Otomatik** (yer varsa videonun yanında, yoksa köşede), **Videonun yanında** veya **Köşede**. comma 3X, comma four, StarPilot ve Surround ekranları haritayı her zaman videonun yanında gösterir.
- **Videonun yanındaki genişlik**, Live View'da ayırıcıyı sürükleyerek ayarlanır. **Sıfırla** geri getirir.
- **Harita teması**: **Uygulamayla aynı** (varsayılan: CommaView açıkken açık, koyuyken koyu), **Otomatik** (comma'nızın bulunduğu yerde gün doğumundan gün batımına kadar açık), **Telefonla aynı**, **Açık** veya **Koyu**. Her haritaya uygulanır: Live View'unki, Ana sayfa'daki konum kartı, **Araç konumu** ve rota önizlemesi.

## Sesli yönlendirme ve yerleriniz

- **Sesli yönlendirme**, komutları kapatıp açar. Dönüş kartının hoparlörü **Yönlendirme sesini kapat** aynı ayardır.
- **Yerleriniz**: **Ev** ve **İş** ile **Son yerler**, bu telefonda tutulur. **Temizle** son yerleri kaldırır.

## Başka bir uygulamadan bir yer

Google Maps'te veya başka bir harita uygulamasında bir yeri paylaşın ve **CommaView ile yol tarifi**'ni seçin. Rota önizlemesi, kayıtlı bir yerinki gibi Ana sayfa'da açılır.

## Mapbox

Hesabınız sunuyorsa Ayarlar › Haritalar ve navigasyon, Stadia Maps yerine kendi Mapbox belirtecinizle rota oluşturabilir.

## Gizlilik

Stadia Maps anahtarınız yalnızca bu telefonda, şifreli olarak tutulur ve asla günlüğe yazılmaz veya bir destek paketine konmaz. Rotalar onunla telefonunuzdan Stadia Maps'e gider; hiçbir şey CommaView'un hesap hizmetine gitmez. Aramalar, comma'nızın konumunun yakınında Photon'a gider. Anahtarınızı temizlemek veya çıkış yapmak onu telefondan kaldırır.

## Güvenlik

Bir yolculuğu park hâlinde ayarlayın ve dönüş kartının ve sesin size yol göstermesine izin verin. Navigasyon yalnızca gösterim içindir: asla direksiyonu çevirmez, fren yapmaz veya openpilot'un yaptığını değiştirmez. Sürerken CommaView'u kullanmayın: openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun.
