---
title: "comma'nızın çalışma ortamını güncelleyin"
description: "comma'nızdaki CommaView çalışma ortamını Ana sayfa'dan veya Cihaz ayarları'ndan güncelleyin. Güvenli güncelleme P konumunu bekler, böylece bir güncelleme sürüşü asla kesmez."
topic: account
order: 1
kind: walkthrough
lede: "comma'nızdaki CommaView çalışma ortamı kendiliğinden değil, uygulamadan güncellenir. Önce CommaView'u, ardından uygulama sunduğunda çalışma ortamını güncelleyin. Araç sürülüyorsa **Güvenli güncelleme** güncellemeyi comma'da sıraya alır ve araç P konumunda ve openpilot devre dışı olduğunda yükler."
updated: 2026-11-27
needs:
  - title: "Telefon ve comma bir arada"
    text: "comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda."
  - title: "Araç açık"
    text: "Aracı çalışır durumda, P konumunda tutun. Güç kablo demeti yoksa aracı kapatmak comma'yı da kapatır."
howItWorks:
  - title: "CommaView"
    text: "Her uygulama sürümü birlikte test edildiği çalışma ortamını adlandırır ve tam olarak onu sunar."
  - title: "comma'nız"
    text: "Araç P konumuna alındığında onu indirir, denetler ve yükler."
    edge: "yeniden başlatma"
  - title: "Live View"
    text: "comma yeniden başladığında yeniden başlar."
steps:
  - id: app-first
    title: "Önce CommaView'u güncelleyin"
    body: |
      Uygulama birlikte test edildiği çalışma ortamını yükler; bu yüzden uygulamayı çalışma ortamından önce güncelleyin. Bir güncelleme hazır olduğunda **Güncelle**, Ana sayfa'nın üstünde ve Ayarlar › **Hakkında**'da görünür. Dokunun: **CommaView'u güncelle** sürümü, kanalını ve boyutunu söyler. **İndir**'e dokunun; CommaView onu arka planda indirir ve denetler, ardından Android yüklemeyi onaylamanızı ister.
    screen: app-update-offer
    pins:
      - target: download
        text: "**İndir**."
      - target: channel
        text: "Sürümün kanalı: **Beta** veya test edenler için **Alfa**."
    note: "Çalışma ortamını güncellemeden önce bu comma'yı izleyen her telefonda, tablette ve araç ekranında CommaView'u güncelleyin."
  - id: open
    title: "Çalışma ortamı güncellemesini açın"
    tabs:
      - label: "Ana sayfa'dan"
        body: "Bu comma için yeni bir çalışma ortamı hazır olduğunda Ana sayfa **Çalışma ortamı güncellemesi hazır** gösterir. **Güncellemeyi gözden geçir**'e dokunun: **Çalışma ortamı güncellemesi** kartı **Yüklü** ve **Mevcut** sürümleri ve aracın hazır olup olmadığını gösterir. **Çalışma ortamını güncelle**'ye veya araç sürülürken **Güncellemeyi sıraya al**'a dokunun."
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**Çalışma ortamı güncellemesi**: Yüklü, Mevcut ve aracın hazır olup olmadığı."
          - target: update-runtime
            text: "**Çalışma ortamını güncelle** (araç sürülürken **Güncellemeyi sıraya al**)."
      - label: "Cihaz ayarları'ndan"
        body: "comma'nın **Cihaz ayarları**'nı, ardından **Çalışma ortamı**'nı açın (biri hazır olduğunda **Güncelle** gösterir). Sayfa yüklü ve mevcut çalışma ortamını gösterir. **Şimdi güncelle**'ye dokunun."
        screen: device-runtime
        pins:
          - target: update-now
            text: "**Şimdi güncelle**."
  - id: install
    title: "Yükleyin veya Güvenli güncellemenin sıraya almasına izin verin"
    body: |
      Cihaz ayarları'ndan açılan **Çalışma ortamı güncellemesi** iletişim kutusu aracın hazır olup olmadığını söyler.
    tabs:
      - label: "Araç P konumunda"
        body: "“Araç P konumunda ve openpilot devrede değil. Çalışma ortamı güncellemesini başlatmak güvenli.” der. **Güncellemeyi yükle**'ye dokunun."
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**Güncellemeyi yükle**."
          - target: close
            text: "**Kapat**, sonraya bırakır."
      - label: "Araç sürülüyor"
        body: "“Araç sürülüyor. Güvenli güncelleme, güncellemeyi comma'da sıraya alır ve araç P konumunda ve openpilot devre dışıyken yükler.” der. **Güvenli güncelleme…**'ye dokunun, notu okuyun ve kısa geri sayımı bitince **Güvenli güncellemeyi başlat**'a dokunun. CommaView aracın sürülüp sürülmediğini doğrulayamadığında da aynısı olur."
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**Güvenli güncelleme…**, ardından **Güvenli güncellemeyi başlat**."
    note: "CommaView openpilot'u veya fork'unuzu asla durdurmaz: sıraya alınan bir güncelleme P konumunu bekler ve bir sürüş asla kesilmez."
  - id: progress
    title: "Çalışmasına izin verin"
    body: |
      comma sürümü indirir, eksiksiz ve değiştirilmemiş olduğunu denetler, yükler ve CommaView'u yeniden başlatır; uygulama her adımı gösterir. Uygulama değiştirebilir veya telefonunuzu kilitleyebilirsiniz: güncelleme devam eder ve bildirimi ne kadar ilerlediğini gösterir.

      comma yüklemeye başlayana kadar **Güncellemeyi iptal et** onu durdurur ve comma'nızda hiçbir şey değişmez.
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "Adımlar: İndiriliyor, Doğrulanıyor, Yükleniyor, CommaView yeniden başlatılıyor, Yeniden bağlanılıyor."
  - id: queued
    title: "Sıraya alınan bir güncelleme P konumunu bekler"
    body: |
      Sıraya alınan bir güncelleme Ana sayfa'nın **Çalışma ortamı güncellemesi** kartında **Aracın P konumuna alınması bekleniyor** olarak görünür. Araç openpilot devre dışıyken birkaç saniye P konumunda kaldığında yüklenir. Yüklenirken aracı açık bırakın.
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "Adımıyla **Aracın P konumuna alınması bekleniyor**."
  - id: reboot
    title: "Bitirmek için comma'yı yeniden başlatın"
    body: |
      Bir çalışma ortamı güncellemesinden sonra, CommaView ondan yeniden yayın yapmadan önce comma'nın yeniden başlatılması gerekir: openpilot CommaView'un yeni ekran kodunu yalnızca comma yeniden başladığında yükler. Uygulama onu asla kendiliğinden yeniden başlatmaz.

      Araç kapalıyken veya P konumundayken Ana sayfa'nın kartındaki **comma'yı yeniden başlat**'a veya iletişim kutusundaki **comma'yı şimdi yeniden başlat**'a dokunun. openpilot yaklaşık bir dakika durur. comma'nın kendisinden de yeniden başlatabilirsiniz: **Ayarlar → Cihaz → Yeniden başlat**.
check: "Güncellemenin son adımı **Güncellendi** der ve Cihaz ayarları yeni çalışma ortamını **Güncel** gösterir. Yeniden başlatmadan sonra Live View katmanıyla oynar."
fixes:
  - q: "“Bu comma'nın çalışma ortamı bu uygulamanın yüklediğinden daha yeni”"
    a: "CommaView'u güncelleyin, ardından yeniden deneyin. comma'da hiçbir şey değiştirilmedi."
  - q: "“Güncelleme gerekiyor”"
    a: "Bu uygulama ve bu comma'nın çalışma ortamı birbiri için yeterince yeni değil. Önce CommaView'u, ardından çalışma ortamını güncelleyin."
  - q: "“comma … sürümünü yüklemedi: CommaView'un listelemediği … çalıştırıyor”"
    a: "comma hiçbir şeyi değiştirmedi ve mevcut çalışma ortamını korudu. CommaView'u o fork'a sınırlı destekle eklemek için bu comma'nın kurulumunu yeniden çalıştırın: fork'u denetler ve önce size sorar."
  - q: "“Her başladığında araç yeniden çalıştırıldı, bu yüzden comma denemeyi bıraktı”"
    a: "openpilot devre dışıyken vitesi P'ye alın, ardından yeniden deneyin."
  - q: "“Çalışma ortamı güncellemesi geri alındı”"
    a: "comma eski çalışma ortamını geri getirdi. Yeniden deneyin; yine başarısız olursa [bir destek paketi gönderin](/tr/guides/support-bundle)."
  - q: "“CommaView zaten bir çalışma ortamını güncelliyor veya kaldırıyor”"
    a: "Aynı anda tek bir çalışma ortamı işi çalışır. Bittiğinde yeniden deneyin."
  - q: "Güncellemeden sonra katman veya telemetri yok"
    a: "comma henüz yeniden başlamadı. Araç kapalıyken veya P konumundayken yeniden başlatın."
related: [releases, uninstall, another-phone]
---

## Güncellemeler neden P konumunu bekler

Çalışma ortamını yüklemek, dosyaları değiştirilirken comma'daki CommaView'u durdurur ve hizmetlerini yeniden başlatır; bu yüzden comma bunu yalnızca araç P konumunda ve openpilot devre dışıyken yapar. Güvenli güncelleme openpilot'tan sürüş dışına geçmesini istemez: işi comma'da sıraya alır, comma da araç P konumuna alındığında çalıştırır. Aracı kapatmanız gerekmez; P konumunda açık tutun.

comma'da bir şey değişmeden önce sürümü indirir ve eksiksiz ve değiştirilmemiş olduğunu denetler. Bundan sonra bir yükleme başarısız olursa comma eski çalışma ortamını geri getirir.
