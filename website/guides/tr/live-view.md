---
title: "comma'nızı Live View'da izleyin"
description: "comma'nızın yol kamerasını ve sürüş ekranını telefonunuzda görmek için Live View'u açın; kontrollerini, Ayrıntılar'ı ve bir sorun olduğunda ne dediğini öğrenin."
topic: screens
order: 1
kind: walkthrough
lede: "**Live View**, comma'nızın yol kamerasını canlı olarak, üzerine çizilmiş sürüş ekranıyla gösterir: comma four'unki, comma 3X'inki veya CommaView'un kendisi. Görüntü internetten değil, kendi ağınız üzerinden doğrudan comma'dan gelir."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView kurulmuş"
    text: "Bir Android telefonda, comma'nızla eşleştirilmiş CommaView. Henüz değil mi? [CommaView'u kurun](/tr/guides/setup)."
  - title: "Araç açık"
    text: "openpilot yalnızca sürüşteyken video gönderir. Araç kapalıyken Live View bekler ve araç çalışınca kendiliğinden başlar."
  - title: "Tek bir ağ"
    text: "Telefonunuz ve comma'nız aynı Wi‑Fi'da veya hotspot'ta. Araçta [Araçta bağlanın](/tr/guides/connect-in-the-car) sayfasına bakın."
steps:
  - id: open
    title: "Live View'u Ana sayfa'dan açın"
    body: |
      **Ana sayfa**'da, comma'nız bağlı ve araç açıkken **Live View'u aç**'a dokunun. Yol birkaç saniye içinde görünür ve akış etiketi **Canlı** der.
    screen: phone-home
    pins:
      - target: open-live-view
        text: "Ana sayfa'nın ana düğmesi **Live View'u aç**."
    note: "Araç kapalıyken Live View **comma'nız çevrimiçi ama sürüşte değil** der. Araç çalışınca kendiliğinden ya da **Yenile** ile hemen başlar."
  - id: controls
    title: "Görüntünün altındaki kontrolleri öğrenin"
    body: |
      Dik tutulduğunda kontroller videonun altındadır:

      - **Kayıt**, sürüşün bu bölümünü kaydeder. [Bir sürüşü kaydedin](/tr/guides/record) sayfasına bakın.
      - **Kaydet**, sürüşün son 3 dakikasını ve sonraki dakikasını tutar.
      - Gösterdiği ekranın adını taşıyan sürüş ekranı anahtarı (**CommaView**, **comma 4**, **comma 3X**), her dokunuşta bir sonrakine geçer. [Sürüş ekranını seçin](/tr/guides/overlays) sayfasına bakın.
      - **Yayına başla**, ayarladıktan sonra Live View'un gösterdiğini yayınlar. [Yayına başlayın](/tr/guides/go-live) sayfasına bakın.
      - **Sürücü kamerası**, sürücü kamerasını görüntünün bir köşesinde gösterir.
      - **Ayrıntılar**, Live View'un bilgilerini ve kartlarını açar.

      Telefonunuzun genişliğine ve yazı boyutuna sığmayanlar **Daha fazla**'ya gider. Hiçbir şey küçültülmez veya kesilmez.
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**Kayıt**."
      - target: onroad-screen-button
        text: "Sürüş ekranı anahtarı."
      - target: driver-cam-button
        text: "**Sürücü kamerası**."
      - target: go-live-button
        text: "Canlı yayın ayarlandıktan sonra **Yayına başla**."
      - text: "**Daha fazla**, sığmayanları tutar."
    note: "Bir kayıt sürerken sürüş ekranı anahtarı ve **Sürücü kamerası** soluktur: **Kayıt**'a dokunmadan önce seçin."
  - id: details
    title: "Ayrıntılar'ı açın"
    body: |
      **Ayrıntılar**'a dokunun veya ekranın altındaki sayfayı yukarı kaldırın. Akışın durumunu, videoyu, çalışma ortamını, comma'nızın yazılımını ve adresini, kayıt veya yayın yapıp yapmadığınızı ve **Browser View** kartını gösterir. Bağlantıları **Kayıtlar**'ı ve comma'nızın **Cihaz ayarları**'nı açar.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**Ayrıntılar** sayfası."
      - text: "Özet: akışın durumu, video ve çalışma ortamı."
      - target: recordings-link
        text: "**Kayıtlar**."
      - target: device-settings-link
        text: "Bu comma'nın **Cihaz ayarları**."
  - id: turn
    title: "Telefonu çevirin veya daha büyük bir ekran kullanın"
    body: |
      Telefonu yan çevirdiğinizde video ekranı kaplar, kontroller sürücü tarafındaki bir şeritte yer alır. **Ayrıntılar** görüntünün yanında açılır ve **Çık** Live View'dan çıkar.
    tabs:
      - label: "Yan çevrilmiş telefon"
        body: "Şerit aynı kontrolleri tutar. Kısa bir ekranda kompakt hâle gelir."
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "Şeridin üstünde **Kayıt**."
          - target: more
            text: "**Daha fazla**, **Sürücü kamerası** ve **Ayrıntılar**'ı tutar."
          - target: exit
            text: "**Çık**, Live View'dan çıkar."
      - label: "Tablet veya araç ekranı"
        body: "Geniş bir ekranda şerit sürücü tarafında kalır. [CommaView'u bir araç ekranında kullanın](/tr/guides/car-screens) sayfasına bakın."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Kayıt**."
          - target: onroad-screen-button
            text: "Sürüş ekranı anahtarı."
          - target: driver-cam-button
            text: "**Sürücü kamerası**."
          - target: details
            text: "**Ayrıntılar**."
          - target: exit
            text: "**Çık**."
  - id: auto
    title: "Live View'un kendiliğinden açılmasına izin verin"
    body: |
      Yalnızca Live View'u göstermek için duran bir telefon veya multimedya ünitesi için **Ayarlar › Ekran**'ı açın ve **Live View açılıyor** altında **Bağlanınca Live View'u aç**'ı açın. Live View, araç açıkken comma'nız bağlandığında kendiliğinden açılır. Ondan çıkarsanız bir dahaki sefere kadar kapalı kalır.

      Hemen altındaki **Durum çubuğunu göster**, tüm ekranı kullanmak yerine Live View'un üstünde sistem saatini gösterir.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Bağlanınca Live View'u aç**."
  - id: leave
    title: "İşiniz bitince Live View'dan çıkın"
    body: |
      Park ettikten sonra **Çık**'a veya geri tuşuna dokunun. Live View'dan çıkmak canlı yayını, Browser View'u ve canlı kopyaları da sonlandırır. Live View aynı anda tek bir telefonda veya multimedya ünitesinde açıktır; başka birinde açmadan önce birinden çıkın.
check: "Akış etiketi **Canlı** der, yol hareket eder ve Ayrıntılar'daki akış durumu **İyi** der."
fixes:
  - q: "“comma'nız çevrimiçi ama sürüşte değil”"
    a: "Araç kapalı veya openpilot başlamadı. Live View araç çalıştıktan sonraki 30 saniye içinde kendiliğinden geri gelir ya da **Yenile**'ye dokunun."
  - q: "“Bu comma'ya ulaşılamıyor”"
    a: "Telefonunuz comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda olmalı. comma yanıt verdiğinde Live View yeniden bağlanır ya da **Yeniden dene**'ye dokunun. Hâlâ bir şey yok mu? [CommaView comma'nızı bulamıyor](/tr/guides/comma-not-found) sayfasına bakın."
  - q: "“Live View başka bir cihazda açık”"
    a: "comma'nız aynı anda tek bir telefona veya multimedya ünitesine yayın yapar. Diğerinde CommaView'da Ana sayfa'ya dönün; Live View burada kendiliğinden başlar."
  - q: "“Araç verileri gelmiyor”"
    a: "Video geliyor ama aracın hızı, sinyalleri ve uyarıları gelmiyor. Düzeltmek için comma'yı yeniden başlatın."
  - q: "“Video gecikmeli”"
    a: "Bir saniyedir yeni kare gelmedi. Live View bunu görüntünün yanında söyler ve video geri gelmezse kendiliğinden yeniden bağlanır."
  - q: "“Bu comma'nın videosu oynatılamıyor”"
    a: "Telefonun video kod çözücülerinden hiçbiri oynatamadı. CommaView denemeye devam eder. CommaView'un inceleyebilmesi için Ayarlar'dan bir destek raporu gönderin: [Destek raporu gönderin](/tr/guides/support-bundle) sayfasına bakın."
related: [overlays, record, browser-view, car-screens]
---

## Güvenlik

Live View'u park hâlinde açın, sonra kendi hâline bırakın. Sürerken CommaView'u kullanmayın: openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun. comma'nızın kendi uyarıları ve aracınızın göstergeleri önce gelir. CommaView yalnızca comma'nın gördüğünü gösterir.
