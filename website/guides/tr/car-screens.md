---
title: "CommaView'u bir tablette veya araç ekranında kullanın"
description: "CommaView'un Live View'unu daha büyük bir ekranda çalıştırın: Android multimedya ünitesi, aracın ekranında Android AI box veya tutucudaki bir tablet. Yükleme, ağ, eşleştirme ve düzen."
topic: screens
order: 3
kind: walkthrough
lede: "comma 3X'in ve comma four'un ekranları küçüktür. CommaView, comma'nızın Live View'unu daha büyük bir ekranda gösterir: bir Android multimedya ünitesi, aracın kendi ekranındaki bir Android AI box veya tutucudaki bir telefon ya da tablet. Araç ekranı, comma'nızla eşleştirilmiş kendi CommaView kopyasını çalıştırır."
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 veya üstü"
    text: "Android 8 veya üstü çalıştıran ve uygulama yüklemenize izin veren bir multimedya ünitesi, AI box, telefon veya tablet."
  - title: "Davetiniz"
    text: "my.commaview.com'da ve uygulamada giriş yapmak için CommaView davetinizin geldiği e-posta adresi."
  - title: "Telefonunuzda CommaView"
    text: "En kolayı: önce comma'nızı telefonunuzdan kurun, sonra araç ekranını eşleştirin. [CommaView'u kurun](/tr/guides/setup)."
howItWorks:
  - title: "comma'nız"
    text: "Live View'u internet üzerinden değil, yerel bir ağ üzerinden gönderir."
    edge: "hotspot veya Wi‑Fi"
  - title: "Araç ekranı"
    text: "comma'nızla eşleştirilmiş kendi CommaView'unu çalıştırır."
steps:
  - id: install
    title: "CommaView'u araç ekranına yükleyin"
    body: |
      Multimedya ünitesinde, AI box'ta, telefonda veya tablette web tarayıcısını açın ve davetinizin geldiği e-postayla [my.commaview.com](https://my.commaview.com) adresinde giriş yapın. **Get the app** altında **Download CommaView**'a dokunun, indirileni açın ve bu seferlik tarayıcıdan yüklemeye izin verin, sonra [kurulum rehberindeki](/tr/guides/setup) gibi yeniden kapatın.

      CommaView'u açın ve giriş yapın. Beta süresince erişim hakkını yenilemek için ara sıra internete ihtiyaç duyar; bu yüzden ona arada bir internetli Wi‑Fi verin.
    note: "Bazı multimedya üniteleri ve kutular tarayıcıdan yüklemeyi engeller. Uygulamayı bir bilgisayara indirin, USB belleğe kopyalayın ve ünitenin dosya yöneticisinden açın."
  - id: network
    title: "comma ile aynı ağa alın"
    body: |
      Live View yerel bir ağ üzerinden doğrudan comma'dan araç ekranına gider. Yalnızca aynı ağda olmaları gerekir; araçta bu genellikle bir hotspot'tur. Araçla birlikte kendiliğinden açılanı seçin: genellikle en zahmetsizidir.
    tabs:
      - label: "Araç ekranının hotspot'u"
        body: "AI box veya multimedya ünitesi hotspot paylaşabiliyorsa (SIM kartlı pek çoğu yapabilir), açın ve comma'yı comma'nın **Ayarlar › Ağ** bölümünden ona bağlayın."
      - label: "Telefonunuzun hotspot'u"
        body: "comma'yı ve araç ekranını telefonunuzun hotspot'una bağlayın. İnterneti de buradan alırlar."
      - label: "comma'nın hotspot'u"
        body: "comma'nın hotspot'unu açın (openpilot buna tethering der: comma four'da **Ayarlar › Ağ › tethering'i etkinleştir**; comma 3X'te **Ayarlar › Ağ › Gelişmiş › Tethering'i etkinleştir**) ve araç ekranından ona katılın."
      - label: "Ev Wi‑Fi'ı"
        body: "Evde ikisi de Wi‑Fi'nızda. Kurulum için kullanışlı ama yola çıktığınızda biter."
    note: "Araç ekranındaki VPN'i kapatın. Bazı hotspot'lar bağlı cihazları birbirinden ayırır: araç ekranı birinde comma'yı bulamazsa başkasını deneyin. Daha fazlası [Araçta bağlanın](/tr/guides/connect-in-the-car) sayfasında."
  - id: pair
    title: "comma'nızla eşleştirin"
    body: |
      comma'nız telefonunuzdan zaten CommaView çalıştırıyorsa, araç ekranını yeniden kurmak yerine eşleştirin. Kendi anahtarını alır.
    tabs:
      - label: "Telefonunuzda"
        body: |
          comma'nın **Cihaz ayarları**'nı, ardından **Başka bir telefon eşleştir**'i açın. **Başka bir telefon ekle** altında **Davet göster**'e dokunun: yazılacak bir kod veya bir QR kodu, 10 dakika geçerli ve bir kez kullanılır.
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**Davet göster**."
          - target: this-phone
            text: "Anahtarı olan telefonlar, bu telefon **Bu telefon** olarak işaretli. Araç ekranı onlara katılır."
      - label: "Araç ekranında"
        body: |
          **comma'nızı bağlayın** ekranında **CommaView çalıştıran bir comma eşleştirin**'e dokunun (zaten bir comma eklenmişse bunun yerine **comma ekle**'yi açın). comma'nızı seçin ve **Eşleştirme kodunu girin**'e veya **QR kodunu tara**'ya dokunun. Listede yoksa **Adres ve kod girin**'e dokunun. Daveti **Eşleştirme kodu veya davet** alanına yazın ve **comma eşleştir**'e dokunun.
        screen: add-comma
        pins:
          - target: found-comma
            text: "Bu ağda bulunan comma'nız."
          - target: scan-qr
            text: "**QR kodunu tara**."
          - target: enter-address
            text: "Listede yoksa **Adres ve kod girin**."
    note: "Ardından telefonunuz **Yeni bir telefonun anahtarı var** der. **Benim**'e dokunun. Her adım: [Başka bir telefon veya tablet ekleyin](/tr/guides/another-phone)."
  - id: fit
    title: "Ekranınıza sığdırın"
    body: |
      Geniş bir ekranda CommaView, yanda bir gezinme şeridiyle gösterge paneli düzeninde yerleşir. Ünitenin yazı boyutunu bir bakışta okuyabileceğiniz bir boyutta tutun: CommaView o boyutta sahip olduğu alana göre yerleşir.

      Live View'un kontrolleri sürücü tarafındadır. **Otomatik**'te CommaView comma'nızın bildirdiği tarafı izler; kendiniz ayarlamak için **Ayarlar › Ekran › Sürücü konumu**'nu seçin: **Otomatik**, **Soldan direksiyonlu** veya **Sağdan direksiyonlu**. Kontrolleri her ekranda aynalar.
    tabs:
      - label: "Tablet"
        body: "Ana sayfa aracı, haftanızı, haritayı ve sürüşlerinizi yan yana, şerit yandayken gösterir."
        screen: tablet-home
        pins:
          - target: home-tab
            text: "Şerit: **Ana sayfa**, **Kayıtlar**, **Ayarlar**."
          - target: open-live-view
            text: "**Live View'u aç**."
      - label: "Multimedya ünitesi"
        body: "Aynı gösterge paneli, gösterge paneline gömülü bir ekran için boyutlandırılmış."
        screen: car-home
        pins:
          - target: home-tab
            text: "Şerit: **Ana sayfa**, **Kayıtlar**, **Ayarlar**."
          - target: open-live-view
            text: "**Live View'u aç**."
      - label: "Bir AI box üzerinden"
        body: |
          Bazı araçlar bir AI box'ın gönderdiği görüntünün kenarlarını keser ve Android bunu anlayamaz. **Ayarlar › Ekran › Ekran kenarları**'nı açın ve çizgiyi baştan sona görene kadar her kenarı içeri taşıyın. Ardından Ana sayfa'nın, Live View'un ve Ayarlar'ın içine sığdığını kontrol edin. Oradaki **Tema** araç ekranını izleyebilir: **Bu cihazla aynı**.
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−** ve **+** her kenarı içeri taşır; **Bitti** saklar."
  - id: live-view
    title: "Live View'u açın ve oynadığını kontrol edin"
    body: |
      Araç açıkken **Live View'u aç**'a dokunun. Kontrolleri yolun yanında, sürücü tarafında bir şeritte durur; kısa bir ekranda kompakt olur.
    tabs:
      - label: "Tablet"
        body: "**Ayrıntılar** videonun yanında bir panelde açılır."
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "Ayrıntılar, videonun yanında."
          - target: record-button
            text: "**Kayıt**."
          - target: go-live-button
            text: "**Yayına başla**."
      - label: "Multimedya ünitesi"
        body: "Şerit Kayıt'ı, sürüş ekranı anahtarını, Sürücü kamerası'nı, Ayrıntılar'ı ve Çık'ı tutar."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Kayıt**."
          - target: onroad-screen-button
            text: "Sürüş ekranı anahtarı."
          - target: driver-cam-button
            text: "**Sürücü kamerası**."
          - target: details
            text: "Sürücü kamerası'nın altında **Ayrıntılar**."
          - target: exit
            text: "**Çık**."
  - id: auto
    title: "Kendiliğinden açılmasına izin verin"
    body: |
      **Ayarlar › Ekran**'da, **Live View açılıyor** altında:

      - **Bağlanınca Live View'u aç**, araç açıkken comma'nız bağlandığında Live View'u kendiliğinden açar.
      - **Bu cihaz başladığında CommaView'u aç**, araçla birlikte yeniden başlayan bir multimedya ünitesi için. Bunun yerine uyuyan birinin başlatılacak uygulamalar için kendi listesi olabilir.
      - **Bluetooth bağlandığında CommaView'u aç**: seçtiğiniz cihaz bağlandığında; aracınız veya bir multimedya ünitesinde telefonunuz.

      **Diğer uygulamaların üzerinde göster** izni verildiğinde CommaView kendiliğinden açılır. Aksi hâlde bir bildirim açmayı önerir.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Bağlanınca Live View'u aç**."
check: "Araç açıkken araç ekranı Live View'u açar, akış etiketi **Canlı** der ve her kontrol ekranın kenarlarının içindedir."
fixes:
  - q: "CommaView'u CarPlay veya Android Auto üzerinden kullanabilir miyim?"
    a: "Telefonunuzdan değil. CommaView bir CarPlay veya Android Auto uygulaması değildir ve bu platformlar telefon uygulamalarının araç hareket ederken video göstermesine izin vermez. Bir Android AI box bunu aşar, çünkü kendisi bir Android cihazıdır: CommaView kutuda çalışır ve araç kutunun ekranını gösterir. [CommaView'u bir Android AI box'ta çalıştırın](/tr/guides/ai-box) sayfasına bakın."
  - q: "Aracımın yerleşik Android Automotive'inde (Google built-in) çalışır mı?"
    a: "Henüz değil. Google built-in olan araçlar uygulamaları yalnızca CommaView'un bulunmadığı kendi Play Store'larından yükler. Başka bir yolla denerseniz nasıl gittiğini bize anlatın."
  - q: "Aynı comma ile bir araç ekranı ve telefonumu kullanabilir miyim?"
    a: "Evet: her birini comma ile eşleştirin. Live View aynı anda birinde açıktır; bu yüzden önce diğerinde Live View'dan çıkın. Live View **Live View başka bir cihazda açık** der ve diğerinde Ana sayfa'ya döndüğünüzde kendiliğinden başlar."
  - q: "Aracım görüntünün kenarlarını kesiyor"
    a: "Bazı araçlar bir AI box'ın gönderdiği görüntüyü kırpar ve Android bunu anlayamaz. **Ayarlar › Ekran › Ekran kenarları**, uygulamayı ayarladığınız her kenardan uzak tutar."
  - q: "Araç ekranı comma'yı bulamıyor"
    a: "CommaView aynı ağda comma'yı kendiliğinden bulur, adresi değişse bile. Bulamazsa comma'nın IP adresini girin: comma'nın kendi hotspot'unda 192.168.43.1 (her comma'da aynıdır) veya başka herhangi bir ağda comma'nın **Ayarlar › Ağ** altında gösterdiği IP adresi: comma four'da Wi‑Fi düğmesindeki ağ adının altında, comma 3X'te **Gelişmiş** altında."
  - q: "Bir çalışma ortamı güncellemesinden sonra araç ekranına video gelmiyor"
    a: "comma'nızın çalışma ortamını güncellediğinizde önce onu izleyen her cihazda, araç ekranı dahil, CommaView'u güncelleyin. Eski bir CommaView kullanan bir araç ekranı, comma'nın ilk telefonu anahtarını aldıktan sonra 90 gün çalışmaya devam eder; bundan sonra CommaView 0.0.166 veya üstüne ve bir davete ihtiyaç duyar."
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## Sürerken neler çalışır

CommaView bir Android uygulamasıdır, bu yüzden önünüzde bir Android cihaz gerekir. Bunlardan herhangi biri sürerken onu çalıştırabilir:

- **Bir Android multimedya ünitesi.** Android 8 veya üstü çalıştıran sonradan takılan bir multimedya ünitesi: CommaView bir telefondaki gibi yüklenir ve sürerken aracın ekranında çalışır.
- **Bir Android “AI box”.** Aracın kablolu CarPlay veya Android Auto bağlantı noktasına takılan ve orada kendi Android ekranını çizen küçük bir Android bilgisayar. CommaView telefonunuzda değil, kutuda çalışır. [CommaView'u bir Android AI box'ta çalıştırın](/tr/guides/ai-box) sayfasına bakın.
- **Tutucudaki bir telefon veya tablet.** Görüşünüzü engellemeyen bir torpido veya havalandırma tutucusunda herhangi bir Android telefon veya tablet. En basit yol ve çoğu kişinin kullandığı.

Tesla gibi web tarayıcısı olan bir araç bunun yerine Live View'u tarayıcıda gösterebilir: [Live View'u aracınızın tarayıcısında gösterin](/tr/guides/browser-view) sayfasına bakın.

## Neler çalışmaz ve neden

- **Telefonunuzdan CarPlay ve Android Auto.** CommaView bir CarPlay veya Android Auto uygulaması değildir. Bu platformlar telefon uygulamalarının araç hareket ederken video göstermesine izin vermez.
- **CarPlay ve Android Auto'da park hâlinde video.** Apple ve Google bazı araçlar için video ekliyor, ama yalnızca park hâlindeyken; bu yüzden yolda Live View gösteremez.
- **Telefonunuzu araca yansıtma.** Bir telefonun ekranını CarPlay veya Android Auto üzerinden yansıtan adaptörler desteklenmez. Bunun yerine CommaView'u kendisi çalıştıran bir Android AI box veya multimedya ünitesi kullanın.
- **Google built-in (Android Automotive).** Bu araçlar uygulamaları yalnızca CommaView'un bulunmadığı kendi Play Store'larından yükler.

## Test edilen donanım

CommaView ekibinin sürüş yaptığı araç ekranları. CommaView Android 8 veya üstü olan her cihazda çalışmalı, ama kontrol ettiklerimiz bunlar:

| Cihaz | Tür | Ne kontrol ettik |
| --- | --- | --- |
| **Doro multimedya ünitesi** (Qualcomm QCM6125, Android 13, 1280 × 720) | Multimedya ünitesi | Şehir sürüşlerinde Live View (Ekim 2026). |
| **Dasaita 10.2″ multimedya ünitesi** (1280 × 720, bir Toyota RAV4'te) | Multimedya ünitesi | Sürerken Live View; park hâlinde kayıt yüklemeleri. |

**Test etmemize yardım edin.** Her araç ekranı farklıdır. CommaView'u bir multimedya ünitesinde veya kutuda çalıştırıyorsanız [nasıl gittiğini bize anlatın](#araç-ekranınızı-bize-anlatın), kontrol ettikten sonra buraya ekleyelim.

## Araç ekranınızı bize anlatın

Raporun modelini ve ekran boyutunu taşıması için araç ekranının kendisinden gönderin:

1. Multimedya ünitesindeki veya kutudaki CommaView'da **Ayarlar › Destek ve tanılama**'yı açın ve **Sorun bildirin veya fikir gönderin**'e dokunun.
2. **Fikir**'i seçin, ardından **Bu cihazdaki tanılama verileri**'ni açın (bir fikirde kapalıdır): markasını, modelini ve ekran boyutunu bize söyler.
3. Notta aracınızı, multimedya ünitesini veya kutuyu (marka ve model), nasıl bağlandığını (kimin hotspot'u veya Wi‑Fi) ve neyin çalışıp neyin çalışmadığını yazın. Ardından **Gönder**'e dokunun.

Gönderdiklerinizi ve yanıtlarımızı [my.commaview.com](https://my.commaview.com/feedback) adresinde Your feedback altında bulursunuz. Henüz beta'da değil misiniz veya uygulama başlamıyor mu? [CommaView Discord](https://discord.gg/UuMhz9K8ft)'unda bize söyleyin.

## Güvenlik

- Yüklemeyi, eşleştirmeyi ve düzeni park hâlinde yapın. Sürmeden önce Live View'un oynadığını kontrol edin.
- Sürerken CommaView'u kullanmayın. openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun.
- comma'nızın kendi uyarıları ve aracınızın göstergeleri önce gelir. CommaView yalnızca comma'nın gördüğünü gösterir.
- Bir telefonu veya tableti görüşünüzü ya da bir hava yastığını engellemeyecek bir yere takın ve araçlardaki ekranlarla ilgili yerel kurallara uyun.
