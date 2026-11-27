---
title: "CommaView'u bir Android AI box'ta çalıştırın"
description: "Bir Android AI box ile Live View'u aracınızın kendi CarPlay veya Android Auto ekranına taşıyın: takın, CommaView'u yükleyin, comma'nın ağına alın, eşleştirin ve sığdırın."
topic: screens
order: 4
kind: walkthrough
lede: "Aracınızda fabrikadan **kablolu** CarPlay veya Android Auto varsa, bir **Android AI box** CommaView'un Live View'unu yeni bir teyp veya kablolama olmadan aracın kendi ekranına taşıyabilir. Kutu, telefonunuzu taktığınız USB bağlantı noktasına takılan küçük bir Android bilgisayardır. CommaView kutuda çalışır, böylece telefonunuz aramalar ve haritalar için boş kalır."
parked: true
updated: 2026-11-27
needs:
  - title: "Kablolu CarPlay veya Android Auto"
    text: "Veri taşıyan bir USB bağlantı noktası üzerinden fabrikadan kablolu CarPlay veya kablolu Android Auto. Kutunun aracınızdakini desteklediğini kontrol edin."
  - title: "Gerçek Android çalıştıran bir kutu"
    text: "Bir dosyadan uygulama yüklemenize izin veren Android 8 veya üstü. Kapalı “video” kutuları ve sıradan kablosuz adaptörler CommaView'u çalıştıramaz. [Hangi kutuyu almalı](/blog/android-ai-box-commaview)."
  - title: "Telefonunuzda CommaView"
    text: "Önce comma'nızı telefonunuzdan kurun, sonra kutuyu eşleştirin. [CommaView'u kurun](/tr/guides/setup)."
howItWorks:
  - title: "comma'nız"
    text: "Live View'u yerel bir ağ üzerinden kutuya gönderir."
    edge: "Wi‑Fi"
  - title: "AI box"
    text: "Herhangi bir Android cihaz gibi CommaView'u çalıştırır."
    edge: "USB"
  - title: "Araç ekranı"
    text: "CarPlay'i gösterdiği gibi kutunun ekranını gösterir."
steps:
  - id: plug-in
    title: "Kutuyu takın ve CommaView'u yükleyin"
    body: |
      Kutuyu aracın CarPlay veya Android Auto USB bağlantı noktasına takın ve başlamasını bekleyin. Şimdilik internetli bir Wi‑Fi'a bağlayın.

      Kutunun tarayıcısında, davetinizin geldiği e-postayla [my.commaview.com](https://my.commaview.com) adresinde giriş yapın ve **Get the app** altında **Download CommaView**'a dokunun. Bu tek yükleme için tarayıcıdan yüklemeye izin verin, sonra yeniden kapatın. CommaView'u açın ve giriş yapın.
    note: "CommaView'u, telefonunuzun CarPlay'i aktarılırken değil, kutunun Android modunda çalıştırın."
  - id: network
    title: "Kutuyu ve comma'yı aynı ağa alın"
    body: |
      Live View internet üzerinden değil, yerel bir ağ üzerinden doğrudan comma'dan kutuya gider ve ikisinin de bulunduğu herhangi bir ağ iş görür.
    tabs:
      - label: "Kutunun hotspot'u"
        body: "SIM kartlı kutular genellikle hotspot paylaşabilir. Açın ve comma'yı comma'nın **Ayarlar › Ağ** bölümünden ona bağlayın."
      - label: "Telefonunuzun hotspot'u"
        body: "Kutuyu ve comma'yı telefonunuzun hotspot'una bağlayın. İnterneti de buradan alırlar."
      - label: "comma'nın hotspot'u"
        body: "comma'nın hotspot'unu açın (openpilot buna tethering der) ve kutudan ona katılın."
    note: "Çoğu kutu, kablosuz CarPlay için telefonunuzu bağlamak üzere de Wi‑Fi kullanır ve bazıları bunu yaparken Wi‑Fi internetini keser. Kutudaki VPN'i kapatın."
  - id: pair
    title: "Kutuyu comma'nızla eşleştirin"
    body: |
      Telefonunuzda comma'nın **Cihaz ayarları**'nı açın, **Başka bir telefon eşleştir**'e dokunun ve **Başka bir telefon ekle** altında **Davet göster**'e dokunun. Kutuda **CommaView çalıştıran bir comma eşleştirin**'e dokunun, comma'nızı seçin ve kodu yazın ya da **QR kodunu tara**'ya dokunun. Her adım: [CommaView'u bir tablette veya araç ekranında kullanın](/tr/guides/car-screens#step-pair).
  - id: edges
    title: "Uygulamayı aracın kestiği kenarlardan içeri alın"
    body: |
      Bazı araçlar kutunun gönderdiğinin kenarlarını kırpar ve Android bunu anlayamaz. **Ayarlar › Ekran › Ekran kenarları**'nı açın. Bir çizgi uygulamanın nerede bittiğini gösterir: çizgiyi baştan sona görene kadar her kenarı **−** ve **+** ile içeri taşıyın, ardından **Bitti**'ye dokunun. **Sıfırla** kapatır.

      Ardından Ana sayfa'nın, Live View'un ve Ayarlar'ın içine sığdığını kontrol edin.
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−** ve **+** her kenarı içeri taşır; **Bitti** saklar."
      - text: "Yine **Ayarlar › Ekran**'daki **Tema**: **Bu cihazla aynı** kutuyu izler."
  - id: auto
    title: "Kendiliğinden açılmasına izin verin"
    body: |
      **Ayarlar › Ekran**'da, **Live View açılıyor** altında:

      - **Bu cihaz başladığında CommaView'u aç**, araçla birlikte yeniden başlayan bir kutu için.
      - **Bluetooth bağlandığında CommaView'u aç**, telefonunuzu seçerek, bunun yerine uyuyan bir kutu için.
      - **Bağlanınca Live View'u aç**, araç açıkken comma'nız bağlandığında doğrudan Live View'a geçmek için.

      CommaView'un kendiliğinden açılabilmesi için **Diğer uygulamaların üzerinde göster** izni verin. Olmadan, bir bildirim açmayı önerir.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Bağlanınca Live View'u aç**."
  - id: check
    title: "Live View'un oynadığını kontrol edin, sonra sürün"
    body: |
      Araç açıkken kutuda Live View'u açın. Kontrolleri sürücü tarafında bir şeritte durur; kısa bir ekranda kompakt olur. Sürmeden önce görüntünün oynadığını ve hiçbir şeyin kesilmediğini kontrol edin.
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "Şeridin üstünde **Kayıt**."
      - target: details
        text: "Şeridin aşağısında **Ayrıntılar**."
    note: "Kutunun ekranı araca video olarak ulaşır, bu yüzden Live View yolda bir kez daha kodlanır. Elinizdeki bir telefondakinden biraz daha yumuşak ve biraz daha geç olmasını bekleyin."
check: "Aracın ekranı CommaView'un Ana sayfa'sını, ardından akış etiketi **Canlı** diyen Live View'u gösterir ve **Ekran kenarları**'ndaki çizgi baştan sona görünür."
fixes:
  - q: "Kutu CommaView'u yükleyemiyor"
    a: "Bazı kutular tarayıcıdan yüklemeyi engeller. Uygulamayı bir bilgisayara indirin, USB belleğe kopyalayın ve kutunun dosya yöneticisinden açın. Kapalı sistemli ve sabit uygulama listeli bir kutu onu hiç yükleyemez."
  - q: "Kutu comma'yı bulamıyor"
    a: "İkisinin aynı ağda olduğunu ve kutunun kablosuz CarPlay için Wi‑Fi'ını kesmediğini kontrol edin. Gerekirse comma'nın IP adresini girin: comma'nın kendi hotspot'unda 192.168.43.1. Daha fazlası [Araçta bağlanın](/tr/guides/connect-in-the-car) sayfasında."
  - q: "Görüntü takılıyor veya oynamıyor"
    a: "comma yol kamerasını 1928 × 1208 HEVC (H.265) olarak gönderir ve en ucuz kutuların kod çözücüleri yetersiz kalabilir. Bir kod çözücü başarısız olursa CommaView kutunun diğerlerini kendiliğinden dener. Hiçbiri oynatamadığında Live View **Bu comma'nın videosu oynatılamıyor** der: kutudan bir destek raporu gönderin."
  - q: "“Live View başka bir cihazda açık”"
    a: "comma'nız aynı anda tek bir telefona veya multimedya ünitesine yayın yapar. Telefonunuzdaki CommaView'da Ana sayfa'ya dönün; Live View kutuda kendiliğinden başlar."
  - q: "Telefonumdan CarPlay'i hâlâ kullanabilir miyim?"
    a: "Evet. Çoğu kutu telefonunuzun CarPlay veya Android Auto'sunu kablosuz aktarır ve onunla kutunun Android'i arasında geçiş yaparsınız. CommaView kutunun Android modunda çalışır."
  - q: "Kutunun SIM karta ihtiyacı var mı?"
    a: "Live View için değil. Beta süresince CommaView erişim hakkını yenilemek için ara sıra internete ihtiyaç duyar; bunu evdeki Wi‑Fi, telefonunuzun hotspot'u veya kutudaki bir SIM sağlar."
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## Dört tür “CarPlay adaptörü”

Mağazalar aynı adla oldukça farklı dört şey satar. Yalnızca biri CommaView'u çalıştırır.

| Tür | Ne yapar | CommaView'u çalıştırır mı? |
| --- | --- | --- |
| **Android AI box** | Aracın ekranında tam Android, uygulamalar telefondaki gibi yüklenir | **Evet** |
| **Kapalı “video” kutusu** | Kilitli bir sistemde birkaç yerleşik yayın uygulaması | Hayır |
| **Kablosuz adaptör** | Kablolu CarPlay veya Android Auto'yu kablosuz yapar. Kendi Android'i yok | Hayır |
| **Taşınabilir CarPlay ekranı** | Telefonunuzun CarPlay'i için ayrı bir ekran, içi çoğu zaman Android değil | Hayır |

[CommaView için en iyi Android AI box'lar](/blog/android-ai-box-commaview), almaya değer kutuları karşılaştırır. Tesla'da CarPlay veya Android Auto yoktur: bunun yerine [Browser View](/tr/guides/browser-view) kullanın.

comma'nızın çalışma ortamını güncellediğinizde, comma'nızı izleyen her cihazda olduğu gibi önce kutudaki CommaView'u güncelleyin.

## Güvenlik

Kutuyu park hâlinde kurun, sonra kendi hâline bırakın. Sürerken CommaView'u kullanmayın: openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun. comma'nızın kendi uyarıları ve aracınızın göstergeleri önce gelir. CommaView yalnızca comma'nın gördüğünü gösterir.
