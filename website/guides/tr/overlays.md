---
title: "Sürüş ekranını seçin ve katman paketleri ekleyin"
description: "Live View'un yolu nasıl çizeceğini seçin: comma four'un ekranı, comma 3X'inki veya CommaView'un kendisi. Ardından fork'unuzun kendi ekranında çizdikleri için bir katman paketi ekleyin."
topic: screens
order: 6
kind: walkthrough
lede: "Live View, yol kamerasının üzerine bir sürüş ekranı çizer: **comma four**'unki, **comma 3X**'inki veya **CommaView**'un kendisi. comma ekranları fork'unuzun görünümünde çizilir. **Katman paketleri**, fork'unuzun kendi ekranının çizip CommaView'un çizmediği şeyleri ekler; örneğin BluePilot'un hibrit göstergeleri veya dragonpilot'un gökkuşağı yolu."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View çalışıyor"
    text: "Bir Android telefonda, comma'nızla eşleştirilmiş CommaView. Henüz değil mi? [CommaView'u kurun](/tr/guides/setup)."
  - title: "Mağaza için giriş yapılmış"
    text: "Üyeler CommaView'un paketlerine göz atar. Giriş yapmadan da bir dosyadan veya bağlantıdan paket ekleyebilirsiniz."
steps:
  - id: switch
    title: "Live View'da ekran değiştirin"
    body: |
      Live View'da sürüş ekranı anahtarına dokunun. Gösterdiği ekranın adını taşır ve her dokunuş bir sonrakine geçer: **comma 4**, **comma 3X**, **CommaView**, sonra yeniden başa. Bıraktığınız ekran bir dahaki sefere de kullanılır.
    screen: phone-live-view
    clip: onroad-screen
    pins:
      - target: onroad-screen-button
        text: "Gösterdiği ekranın adını taşıyan sürüş ekranı anahtarı."
    note: "Diğer kontrollerin yanına sığmadığı yerde **Daha fazla** içinde, **Sürüş ekranı** olarak bulunur. Bir kayıt sürerken soluktur: bir kayıt başladığı ekranla devam eder."
  - id: display
    title: "Ya da Ayarlar › Ekran'da seçin"
    body: |
      Seçmeden önce her ekranı görmek için **Ayarlar › Ekran**'ı açın. **Sürüş ekranı** kartı, seçilen ekranın bir yol fotoğrafı üzerindeki önizlemesini, comma'nızın kameralarına göre kadrajlanmış ve fork'unuzun görünümünde çizilmiş olarak gösterir. Altındaki **Devrede**, **Müdahale** ve **Devre dışı** gösterilen anı değiştirir; hiçbir şey kaydetmez.
    screen: settings-display
    pins:
      - target: onroad-screen-card
        text: "Seçilen ekranın önizlemesi."
      - target: onroad-screen
        text: "**Sürüş ekranı**: listeyi görmek için dokunun."
  - id: pick
    title: "Bir ekran seçin"
    body: |
      Listedeki her ekranın küçük bir resmi ve bir notu vardır:

      - **comma four**: değiştikçe yolun üstünde MAKS, yanında direksiyon ve güven.
      - **comma 3X**: bir durum çerçevesi, MAKS kutusu, büyük bir hız ve altta uyarılar.
      - **CommaView**: akan bir yol, öndeki araç için kilitlenme ve CommaView'un kendi hızı, durumu ve uyarıları.

      Birini seçmek onu kaydeder ve önizlemeyi, seçeneklerini ve Live View'u değiştirir. Her ekran iki comma'da da çalışır.
    screen: settings-display-onroad-screens
    clip: display-pick
    pins:
      - target: comma-four-option
        text: "**comma four**."
      - target: comma-3x-option
        text: "**comma 3X**."
      - target: commaview-option
        text: "**CommaView**."
    note: "Uyarılar, ikazlar ve sürücü izleme durumu, hangi ekranı seçerseniz seçin her zaman comma'nızın kendi renklerini kullanır."
  - id: store
    title: "Katman paketleri mağazasını açın"
    body: |
      **Ayarlar › Katman paketleri**'ni açın veya Ana sayfa'daki **Katman paketleri** kartına dokunun.
    tabs:
      - label: "Giriş yapılmış"
        body: |
          Mağaza önce CommaView'un **Resmî** paketlerini, ardından **Topluluk** paketlerini listeler; hepsini CommaView inceler. **comma'nız için**, comma'nızın çalıştırdığı fork için resmî paketi önerir. Arayın veya listeyi **Tümü**, **Resmî**, **Topluluk** ve **comma'larım için** ile daraltın.
        screen: overlay-packs-store
        pins:
          - target: search
            text: "**Paket ara**."
          - text: "**comma'nız için**: comma'nızın fork'u için resmî paket."
          - target: bluepilot-row
            text: "BluePilot HUD gibi **Resmî** paketler."
          - target: yours
            text: "**Paketleriniz**: bu telefonda olanlar."
      - label: "Dosyadan veya bağlantıdan"
        body: |
          Birisi bir `.cvpack` dosyası veya bağlantı (GitHub, bir gist, bir Discord eki) mi paylaştı? **Paketleriniz**'i açın ve **Kendiniz paket ekleyin** altında **Dosyadan yükle** veya **Bağlantı yapıştır**'a dokunun. CommaView bu şekilde eklenen bir paketi incelemedi ve yükleme iletişim kutusu bunu söyler.
  - id: install
    title: "Bir paket yükleyin"
    body: |
      Önizlemesini, **üzerinde çalıştığı** fork'ları ve Live View'a ne eklediğini görmek için bir pakete dokunun. **Yükle**'ye, ardından iletişim kutusunda yeniden **Yükle**'ye dokunun. Paket bu telefona ve eşleştirilmiş comma'larınıza gider.
    screen: overlay-pack-detail
    pins:
      - text: "Önizleme: paketle Live View. Büyütmek için dokunun."
      - target: install
        text: "**Yükle**."
    note: "Resmî bir paket yalnızca yapıldığı fork'larda çalışır. Eşleştirilmiş comma'larınızın hiçbiri onlardan birini çalıştırmıyorsa iletişim kutusu bunu söyler; yine de yüklenir ama biri çalıştırana kadar Live View'da görünmez."
  - id: drive
    title: "Bir sonraki sürüşünüzde görün"
    body: |
      Yüklendikten sonra mağaza, paketin bu telefon comma'nıza ulaştıkça ona gittiğini ve araç kapalıyken orada başladığını söyler. Bir sonraki sürüşünüzde Live View'u açın: paket, sürüş ekranının kendi uyarılarının altında, comma four, comma 3X ve CommaView ekranlarında çizilir.

      Bir paketi kapatmak için **Paketleriniz**'i açın: her paketin bu telefon ve eşleştirilmiş tüm comma'lar için birlikte tek bir anahtarı vardır.
check: "Live View'un **Ayrıntılar** bölümünde **Katman paketleri** satırı paketi adlandırır ve **çalışıyor** der."
fixes:
  - q: "Sürüş ekranı anahtarı soluk"
    a: "Bir kayıt sürüyor. Durdurun veya bitmesini bekleyin, ardından değiştirin."
  - q: "Ayrıntılar paket için “bu fork için değil” diyor"
    a: "Paket başka bir fork'un ekranı için yapılmış ve sizinkinde hiçbir şey çizmiyor. Resmî paketler hangi fork'lar için olduklarını **üzerinde çalışır** altında söyler."
  - q: "Paket henüz Live View'da yok"
    a: "Telefonunuz comma'nıza bağlandıkça ona ulaşır ve araç kapalıyken orada başlar. Telefonunuz comma'nın ağındayken aracı kapatıp yeniden açın, ardından Live View'u açın."
  - q: "“CommaView'un paketlerini görmek için giriş yapın”"
    a: "Mağaza CommaView'un paketlerini giriş yapmış üyelere listeler. **Giriş yap**'a dokunun. Telefonda zaten olan paketler çıkış yapmışken de çalışmaya devam eder."
  - q: "“my.commaview.com'a ulaşılamıyor”"
    a: "Bu telefonun internet bağlantısını kontrol edin, ardından **Yeniden dene**'ye dokunun. **Paketleriniz** yine de telefondaki her şeyi listeler."
related: [live-view, record, forks]
blogPost: commaview-0-0-166-languages-browser-view
---

## Her ekranın seçenekleri

Önizlemenin altında **Ayarlar › Ekran**, seçilen ekranın kendi seçeneklerini gösterir:

- **comma four seçenekleri**: **Önizleme kadrajı** (comma four'un kadrajıyla birebir eşleştirin, kameranın daha fazlasını gösterin veya bu ekranı dolduracak şekilde kırpın) ve **Kompakt güven paneli** (daha fazla video için daha küçük bir panel ve top).
- **CommaView seçenekleri**: **Kamera kadrajı** (**Ekranı doldur**, kamerayı yatay bir ekranı dolduracak şekilde kırpar; **Tam kamera**, gerektiğinde siyah şeritlerle tamamını gösterir) ve CommaView'un yolunu, hızını ve kilitlenmesini sabit tutan **Hareketi azalt**.
- **comma 3X**: yok. comma'nın çizdiği gibi çizilir.

Ardından **Her ekranda**: kontrolleri aynalayan **Sürücü konumu**, **Tema**, güneş ve parlama için **Gün ışığı kontrastı** ve görüntünün kenarlarını kesen bir araç ekranı için **Ekran kenarları** ([araç ekranları](/tr/guides/car-screens)).

Kayıtlar'da oluşturduğunuz bir tekrar oynatma, daha sonra ne seçerseniz seçin, kayıt sırasında Live View'un çizdiğini çizer.

## Bir katman nereden gelir

CommaView neyi çizeceğini tahmin etmez. comma'nızdaki çalışma ortamı, openpilot'un kendi ekranının okuduğu sürüş verilerinin aynısını (yol, şeritler, öndeki araç, hızlar, uyarılar, sürücü izleme) videonun yanında gönderir ve uygulama bunları telefonunuzda, gösterdiği kamerayla hizalayarak çizer. Bu veriler geciktiğinde, eksik olduğunda veya başka bir kamera için olduğunda CommaView yanlış olabilecek bir şey çizmek yerine o kısmı dışarıda bırakır.

## Güvenlik

Ekranı seçmeyi ve paket yüklemeyi park hâlinde yapın. Sürerken CommaView'u kullanmayın: openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun. Bir katman bakılacak bir şeydir, sürüş yardımı değildir: comma'nızın kendi uyarıları ve aracınızın göstergeleri önce gelir. Sürücü izleme simgesi dikkatin kanıtı değildir ve bir tekrar oynatmanın katmanı bir sürüşe geri bakmak içindir, tam olarak ne olduğunun kanıtı değildir.
