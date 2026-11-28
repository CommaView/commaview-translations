---
title: "YouTube'da veya başka bir sunucuda yayına başlayın"
description: "Live View'un gösterdiğini, yolu ve sürüş ekranını, YouTube kanalınıza veya herhangi bir RTMP sunucusuna 720p ya da 1080p yayınlayın. Bir kez kurun, sonra Live View'dan yayına başlayın."
topic: screens
order: 5
kind: walkthrough
lede: "**Yayına başla**, Live View'un gösterdiğini, yolu ve sürüş ekranını, telefonunuzdan YouTube kanalınıza veya herhangi bir RTMP sunucusuna 720p ya da 1080p olarak yayınlar. Ayarlar'da bir kez kurun, ardından Live View'dan başlatın."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View çalışıyor"
    text: "Bir Android telefonda, comma'nızla eşleştirilmiş CommaView. Henüz değil mi? [CommaView'u kurun](/tr/guides/setup)."
  - title: "Yayın yapılacak bir yer"
    text: "Giriş yapılacak bir YouTube kanalı veya YouTube Studio'dan ya da başka bir RTMP sunucusundan bir yayın anahtarı."
  - title: "Telefonda internet"
    text: "comma'nın Wi‑Fi'ında internet yoksa yayın telefonunuzun mobil verisini kullanır: 720p'de saatte yaklaşık 1,4 GB."
howItWorks:
  - title: "comma'nız"
    text: "Live View'u her zamanki gibi telefonunuza gönderir."
  - title: "Telefonunuz"
    text: "Live View'un çizdiğini yayınlar: saniyede 20 kare, 720p veya 1080p."
    edge: "internet"
  - title: "YouTube veya sunucunuz"
    text: "İzlemesine izin verdiğiniz kişilere gösterir."
steps:
  - id: settings
    title: "Ayarlar › Canlı yayın'ı açın"
    body: |
      **Ayarlar**'ı açın ve **Canlı yayın**'a dokunun. Kurana kadar satırı **Kur** der.
    screen: support-settings
    pins:
      - target: live-streaming-row
        text: "**Canlı yayın**."
  - id: destination
    title: "Nereye yayın yapacağınızı seçin"
    tabs:
      - label: "YouTube ile giriş yap"
        body: |
          **YouTube ile giriş yap**'a dokunun. Google'ın giriş sayfası tarayıcınızda açılır; orada hesabı ve kanalı seçersiniz. Giriş yaptıktan sonra Yayına başla her yayını kanalınızda oluşturur ve YouTube onu kendiliğinden başlatır: yayın anahtarı yok, YouTube Studio'da basılacak bir şey yok. Ardından **Yayın hedefi** kartı kanalınızı **Giriş yapıldı** olarak gösterir.
        screen: settings-live-streaming
        pins:
          - target: destination-row
            text: "**Yayın hedefi**: kanalınız, giriş yapılmış."
        note: "Google'ın kendi giriş sayfaları gösterilmiyor."
      - label: "Bir yayın anahtarı veya sunucu"
        body: |
          **Yayın anahtarı kullan**'a (veya **Yayın hedefini kur**'a) dokunun, **Platform** olarak **YouTube** ya da **Diğer sunucu**'yu seçin ve yayın anahtarını yapıştırın. YouTube için: YouTube Studio'da Oluştur › Canlı yayına geç › Yayın'a gidin, yayın anahtarını kopyalayın ve her yayının video geldiğinde başlaması için orada Otomatik başlat'ı açın. Başka bir sunucu için `rtmp://` veya `rtmps://` adresini de yapıştırın. **Yayın hedefini kaydet**'e dokunun.
        screen: settings-live-streaming-destination
        pins:
          - target: platform
            text: "**Platform**."
          - target: stream-key
            text: "Yayın anahtarı. Yalnızca bu telefonda tutulur ve yalnızca ait olduğu sunucuya gönderilir."
          - target: save
            text: "**Yayın hedefini kaydet**."
        note: "`rtmp://` yayın anahtarınızı şifrelemeden gönderir. Sunucunuz sunuyorsa `rtmps://` kullanın."
  - id: choices
    title: "Kimlerin izleyebileceğini, kaliteyi ve sesi kontrol edin"
    body: |
      - **Kimler izleyebilir** (YouTube'a giriş yapılmışsa): **Herkese açık**, **Liste dışı** veya **Gizli**. **Liste dışı** ile başlar. Yayın anahtarıyla bunu YouTube Studio'da seçin. İzleyen herkes nerede sürdüğünüzü görür.
      - **Başlık ve açıklama** (YouTube'a giriş yapılmışsa): her yayının adı; tarih, araç ve daha fazlası için etiketlerle.
      - **Kalite**: 720p veya 1080p; her birinin saatte yaklaşık ne kadar mobil veri kullandığıyla.
      - **Ses**: comma'nızın veya bu telefonun mikrofonunu seçmedikçe kapalı. Araçtaki herkes, yolcular da duyulur. Yalnızca yayınınıza ve canlı kopyalarınıza gider, asla CommaView'a değil.

      **Yayına başlamadan önce** hepsini özetler: veri kullanımı, sürücü kamerası ve yayının ne zaman durduğu.
    screen: settings-live-streaming
    pins:
      - text: "**Başlık ve açıklama**."
      - target: sound-row
        text: "**Ses**."
  - id: go
    title: "Live View'da Yayına başla'ya dokunun"
    body: |
      Live View'u açın ve **Yayına başla**'ya dokunun. **Başlıyor…** der, ardından ne kadar süredir yayında olduğunuzu gösterir. Yola çıkmadan önce başlatın, sonra kendi hâline bırakın.
    screen: phone-live-view
    pins:
      - target: go-live-button
        text: "**Yayına başla**. Sığmadığı yerde **Daha fazla** içindedir."
    warn: "**Sürücü kamerası** açık olduğunda yayın sürücü kamerasını gösterir ve **Sürücü kamerası** bu durumda **Canlı** der. Sürücü kamerasını yayının dışında tutmak için **Sürücü kamerası**'nı kapatın."
  - id: share
    title: "İzleme bağlantısını paylaşın"
    body: |
      **Ayrıntılar**'da yayının satırı **Yayında** ve ne kadar süredir olduğunu, gönderdiği hızı, kullanılan veriyi ve ağı gösterir. YouTube'a giriş yapılmışsa altındaki **İzleme bağlantısını paylaş**, yayınınızın `youtu.be` bağlantısını paylaşır.
    screen: phone-live-view-go-live
    pins:
      - target: stop-live
        text: "Yayındayken zamanlayıcısıyla **Yayına başla**."
      - target: streaming
        text: "**Yayında** ve ne kadar süredir."
      - target: share-watch-link
        text: "**İzleme bağlantısını paylaş**."
  - id: stop
    title: "Park ettikten sonra yayını durdurun"
    body: |
      Durdurmak için **Yayına başla**'ya yeniden dokunun. Yayın, Live View'dan çıktığınızda, bildiriminin **Durdur**'una dokunduğunuzda ve videosu durduktan bir dakika sonra kendiliğinden de durur. Uygulama değiştirdiğinizde veya telefonu kilitlediğinizde devam eder.
check: "Live View'daki **Yayına başla** canlı renklerde işleyen bir zamanlayıcı gösterir, Ayrıntılar **Yayında** der ve yayınınız YouTube'da veya sunucunuzda oynar."
fixes:
  - q: "Live View'da Yayına başla yok"
    a: "Canlı yayın henüz kurulmadı: Ayrıntılar **Buradan yayına başlamak için Ayarlar'da canlı yayını kurun** der. Ya da kontrollerin hepsinin sığmadığı yerde **Daha fazla** içindedir."
  - q: "“Ayarlar › Canlı yayın'dan yayın anahtarınızı ekleyin”"
    a: "Yayına başla'nın yayın yapacağı bir yer yok. **Ayarlar › Canlı yayın**'da YouTube ile giriş yapın veya bir yayın anahtarı ekleyin."
  - q: "YouTube yayını bir yayın anahtarıyla başlamıyor"
    a: "Yayın anahtarıyla her yayını YouTube Studio'da Canlı yayına geç ile başlatın veya orada Otomatik başlat'ı açın. YouTube ile giriş yapılmışsa kendiliğinden başlar."
  - q: "“Bu anahtarda boşluk var”"
    a: "Anahtarı yayın hizmetinizden yeniden kopyalayın ve yapıştırın."
  - q: "“Ses yok: Browser View sessiz çalışıyor”"
    a: "Yayına başla, sesi olmayan Browser View'un görüntüsünü paylaşır. Ses için yayına başlamadan önce Browser View'u durdurun. Aynısı sessiz başlayan bir kayıt için de geçerlidir."
  - q: "Yayın kendiliğinden duruyor"
    a: "Live View her seferinde nedenini bir mesajla söyler. Yayın ayrıca videosu durduktan bir dakika sonra ve Live View'dan çıktığınızda durur."
related: [live-view, browser-view, live-copy]
blogPost: commaview-0-0-165-go-live-send-to-commaview
---

## Her yayının bir kopyasını tutun

**Ayarlar › Kayıtlar › Her canlı yayını kaydet**, her canlı yayının gönderildiği hâliyle, yayının kalitesinde bir MP4'ünü Kayıtlar'a kaydeder. Telefonunuzda kalır. [Canlı kopya tutun](/tr/guides/live-copy) sayfasına bakın.

## Yayında ne var, ne yok

- **İçinde:** yol ve üzerine çizilen sürüş ekranı, **Sürücü kamerası** açıkken sürücü kamerası.
- **İçinde değil:** Live View'un kontrolleri, Ayrıntılar ve mesajlar. Navigasyonun haritası yalnızca Ayarlar'ın sunduğu yerde **Yayında harita** açıkken ve yalnızca CommaView'un köşesindeki harita.
- Kayıt ve Yayına başla bağımsızdır: bir sürüşü aynı anda kaydedip yayınlayabilirsiniz.

## Güvenlik

Yayına başla'yı park hâlinde kurun ve başlatın, sonra kendi hâline bırakın. Sürerken CommaView'u kullanmayın: openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun. İzleyen herkes nerede sürdüğünüzü görür.
