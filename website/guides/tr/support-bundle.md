---
title: "Destek paketi gönderin"
description: "Tanılamayı açık tutun, sorunu yeniden oluşturun, ardından Ayarlar › Destek ve tanılama'dan telefonunuzun ve comma'nızın günlükleriyle bir rapor gönderin."
topic: troubleshooting
order: 3
kind: walkthrough
lede: "Destek paketi, CommaView uygulamasının telefonunuzda ve çalışma ortamının comma'nızda gördüklerinin küçük bir zip'idir. Aracınızda olmadan bir sorunu bulmamızı sağlar. Yalnızca günlük içerir: video yok, konum yok."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Tanılama açık"
    text: "**Tanılamayı sakla (bu telefon)**, biri kapatmadıysa açıktır. Sorun yeniden olmadan önce kontrol edin."
  - title: "comma'nıza bağlı"
    text: "comma'nızın günlükleri için gönderdiğinizde Ana sayfa comma'nızı **Bağlı** göstermeli."
  - title: "Göndermek için giriş yapılmış"
    text: "Göndermek için beta hesabınız gerekir. Giriş yapmadan **Dosya olarak kaydet** yine çalışır."
howItWorks:
  - title: "Telefonunuz"
    text: "Son 10 sürüşünüzden günlüklerini ve sayaçlarını tutar."
  - title: "comma'nız"
    text: "Gönder'e dokunduğunuzda çalışma ortamının günlüklerini ekler; konum, VIN, kimlikler, Wi‑Fi adları ve belirteçler çıkarılmış olarak."
    edge: "Gönder'e dokunduğunuzda"
  - title: "CommaView ekibi"
    text: "Özel depolamada okur ve e-postayla yanıt verir."
steps:
  - id: open
    title: "Destek ve tanılama'yı açın"
    body: |
      CommaView'da alttaki çubukta **Ayarlar**'a dokunun. Tablette veya multimedya ünitesinde yandaki şerittedir. Sona yakın, Hakkında'dan önce **Destek ve tanılama**'ya dokunun.
    screen: support-settings
    pins:
      - text: "**Destek ve tanılama**."
  - id: keep-diagnostics
    title: "Tanılamayı bu telefonda saklayın"
    body: |
      **Tanılamayı sakla (bu telefon)**, biri kapatmadıysa açıktır: uygulama son 10 sürüşünüzden günlüklerini ve sayaçlarını tutar, böylece bir rapor ne olduğunu söyleyebilir. Kapalıysa açın, ardından sorunu yeniden oluşturun.
    screen: support-diagnostics
    pins:
      - target: keep-diagnostics
        text: "**Tanılamayı sakla (bu telefon)**."
    note: "Tanılama verileri siz bir rapor gönderene kadar bu telefonda kalır: asla otomatik olarak yüklenmez."
  - id: happen-again
    title: "Park hâlinde yeniden oluşturun"
    body: |
      comma'nıza her zamanki gibi bağlanın: telefonunuz comma'nın Wi‑Fi'ında veya hotspot'unda ve Ana sayfa comma'nızı **Bağlı** gösteriyor. Yanlış gideni yapın; örneğin Live View'u açın, sorunlu sürüş ekranına geçin ve orada 10 ila 20 saniye bırakın. Yaklaşık ne zaman olduğunu ve ne yaptığınızı not edin. Bir ekran kaydı da yardımcı olur.
    warn: "P konumunda yeniden oluşturun. Yalnızca yolda oluyorsa, olmasına izin verin ve park ettikten sonra raporu gönderin: kayıt sizi bekler. Sürerken asla uygulamada dokunarak gezinmeyin."
  - id: open-send
    title: "CommaView'a gönder'i açın"
    body: |
      **Destek ve tanılama**'da **Sorun bildirin veya fikir gönderin**'e dokunun.

      Ya da sorundan başlayın: uygulamanın bir hata gösterdiği yerde **Bildir**'e dokunun; bir kayıt için **Kayıt işlemleri**'nde **CommaView'a gönder…**'i seçin. Her biri, ilgili bilgiler doldurulmuş aynı sayfayı açar.
    screen: support-diagnostics
    pins:
      - target: report
        text: "**Sorun bildirin veya fikir gönderin**."
  - id: send
    title: "Neyin gideceğini seçin ve gönderin"
    body: |
      **Sorun**'u seçin ve ne olduğunu anlatın. **Ekler** altında **Bu telefondaki tanılama verileri**'ni ve comma'nızın günlüklerini açık bırakın. **Gör**, her birinin tam olarak ne içerdiğini gösterir. Satırların altında sayfa her raporla gidenleri listeler: uygulama sürümü, telefonunuzun modeli ve Android sürümü, comma'nızın sürüş yazılımı ve kurulumu.

      **Gönder**'e dokunun: “Gönderiliyor. Arka planda gider ve bağlantı bekler.”
    screen: support-send-feedback
    pins:
      - target: problem
        text: "**Sorun** veya **Fikir**."
      - text: "**Ekler**: her satırın bir anahtarı ve **Gör**'ü var."
      - target: send
        text: "**Gönder**."
    note: "Uygulama comma'nıza bağlıyken gönderin: Gönder'e dokunduğunuzda comma'dan günlüklerini ister. comma kapalıysa veya erişim dışındaysa paket nedenini söyler ve yine uygulamanın kendi günlüklerini içerir."
  - id: save-file
    title: "Ya da dosya olarak kaydedin"
    body: |
      Destek dosyanın kendisini mi istedi, yoksa giriş yapmadınız mı? Gönder yerine **Dosya olarak kaydet**'e dokunun. Uygulama aynı paketi, küçük bir `.zip` olarak oluşturur ve Android'in paylaşım sayfasını açar. Desteğin istediği yere gönderin: Discord'da doğrudan mesaj, e-posta veya bulut sürücü bağlantısı.
    screen: support-share-bug-report
    pins:
      - target: save-file
        text: "**Dosya olarak kaydet**."
  - id: afterwards
    title: "Yanıtımızı okuyun"
    body: |
      Yanıt verdiğimizde yanıt e-postayla gelir ve raporunuzla birlikte my.commaview.com'daki [Your feedback](https://my.commaview.com/feedback) sayfasında bulunur. Biz kapatana kadar bize oradan yanıt verin; sonrasında 30 gün boyunca yeniden açabilirsiniz. **Destek ve tanılama**'daki **Talepleriniz** de bunları listeler.
    screen: support-diagnostics
    pins:
      - target: your-requests
        text: "**Talepleriniz**: yanıtlar ve CommaView ile konuşmalarınız."
check: "Sayfa “Gönderiliyor. Arka planda gider ve bağlantı bekler.” ile kapanır ve rapor gönderildikten sonra **Talepleriniz** altında görünür."
fixes:
  - q: "Pakette comma günlükleri yok"
    a: "Gönder'e dokunduğunuzda uygulama comma'nıza ulaşamadı veya **Ekler** altındaki satırı kapalıydı. CommaView'a gönder'i açmadan önce Ana sayfa'nın comma'nızı **Bağlı** gösterdiğini kontrol edin ve comma'nızın satırını açık bırakın. Uygulama comma'nızı yeniden eşleştirmenizi isterse önce eşleştirin, sonra yeniden gönderin."
  - q: "Gönder düğmesi **Göndermek için giriş yapın** diyor"
    a: "Çıkış yapmışsınız. Beta hesabınızla giriş yapmak için dokunun veya **Dosya olarak kaydet**'i kullanın."
  - q: "“Ekler, bir raporun taşıyabileceği 25 MB'ı aşıyor. Birini kapatın veya Dosya olarak kaydet'i kullanın.”"
    a: "İhtiyacınız olmayan bir eki kapatın veya **Dosya olarak kaydet**'e dokunup dosyayı desteğin istediği yere gönderin."
  - q: "Dosya olarak kaydet'e dokunduğumda hiçbir şey olmuyor"
    a: "Bu cihazda bir dosyayı alabilecek bir uygulama yok. Bu, multimedya ünitelerinde yaygındır. Bunun yerine CommaView'a [gönderin](#step-send) veya CommaView çalıştıran bir telefondan kaydedin."
  - q: "“Rapor hazırlanamadı. Yerel depolamayı kontrol edip yeniden deneyin.”"
    a: "Uygulama paketi yazamadı; genellikle cihazın depolama alanı az olduğu için. Biraz yer açın ve yeniden deneyin."
related: [setup-troubleshooting, comma-not-found, releases]
---

## Bir destek paketinde neler var

- **Bu telefondaki tanılama verileri.** Bu telefondan CommaView'un tanılama günlükleri ve sayaçları: video akışı, çizim, bağlantı ve kayıt hataları; uygulama sürümü, telefonun modeli ve Android sürümüyle. Navigasyon ile ayrıca her türden kaç yer aramasının çalıştığı veya başarısız olduğu; asla ne aradığınız değil.
- **comma'nızın günlükleri.** comma'nızın satırı açıkken: CommaView çalışma ortamının günlükleri, sayaçları ve ayarları, hangi openpilot süreçlerinin neden durduğu ve comma'nın çekirdeğinden bellek yetersizliği satırları.
- **Bir pakette asla.** Video yok, GPS konumu yok, VIN yok ve ham sürüş telemetrisi yok: gönderdiğiniz bir kayıt paketin içinde değil, yanında gider. Güncel bir comma çalışma ortamı, günlüklerini göndermeden önce GPS koordinatlarını, VIN'leri, Wi‑Fi adlarını, genel IP adreslerini, belirteçleri ve tam dongle ID'yi çıkarır.
- **Yalnızca siz gönderdiğinizde.** Bir paket telefonunuzdan yalnızca Gönder'e veya Dosya olarak kaydet'e dokunduğunuzda çıkar. Kaydettiğiniz bir dosya yalnızca gönderdiğiniz yere gider. Yerel IP adresleri, oturum kimlikleri ve sürüm ayrıntıları kalabilir; bu yüzden bir paketi yalnızca güvendiğiniz kişilerle paylaşın.

## Nereye gider ve ne kadar süre

Gönderdiğiniz bir paket, yalnızca CommaView ekibinin açtığı CommaView'un özel depolamasına gider. Gönderdikten 180 gün sonra veya daha erken, bizden istediğinizde ya da hesabınızı sildiğinizde hemen silinir ([Gizlilik](/privacy)). İstemek için support@commaview.com adresine e-posta gönderin.

Uygulamanın bu telefonda tuttuklarını kaldırmak için **Destek ve tanılama**'da **Yerel tanılama verilerini temizle**'ye dokunun. Kayıtlarınızı asla silmez. Bundan sonra yalnızca kayıt hatalarının geçmişini tutmak için aynı sayfada **Tanılamayı sakla (bu telefon)**'u kapatın.

Nereye göndereceğinizden emin değil misiniz? [CommaView Discord](https://discord.gg/UuMhz9K8ft)'unda sorun.
