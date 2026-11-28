---
title: "Live View'un gösterdiğinin canlı kopyasını kaydedin"
description: "Canlı kopya, Live View'un gösterdiğini siz sürerken telefonunuza kaydeder; durduğunuz anda Kayıtlar'da hazırdır, 10 dakika sınırı yoktur. Asla yüklenmez."
topic: recordings
order: 2
kind: walkthrough
lede: "**Canlı kopya**, Live View'un gösterdiğini, yolu ve sürüş ekranını, siz sürerken telefonunuza kaydeder. Durduğunuz anda Kayıtlar'da hazırdır: oluşturulacak tekrar oynatma ve 10 dakika sınırı yok. Canlı kopyalar telefonunuzda kalır ve asla yüklenmez."
appVersion: "0.0.164"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View çalışıyor"
    text: "Telefonunuzda, comma'nızla eşleştirilmiş CommaView. Henüz değil mi? [CommaView'u kurun](/tr/guides/setup)."
  - title: "Telefonunuzda yer"
    text: "720p'de saatte yaklaşık 1,4 GB, 1080p'de saatte 2,3 GB. Canlı kopya her zaman 500 MB boş bırakır."
howItWorks:
  - title: "Live View"
    text: "Her zamanki gibi yolu ve sürüş ekranını çizer."
    edge: "siz sürerken"
  - title: "Telefonunuz"
    text: "Live View'un çizdiğini saniyede 20 karede bir MP4'e kodlar."
  - title: "Kayıtlar"
    text: "Kopya durduğunuz anda hazırdır."
steps:
  - id: choose
    title: "Canlı kopya veya İkisi de seçin"
    body: |
      **Ayarlar**'a, ardından **Kayıtlar**'a dokunun. **Live View'da kayıt** altında Kayıt'ın ne oluşturacağını seçin. Seçtiğiniz anda saklanır.
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Live View'da kayıt**: **Tekrar oynatma**, **Canlı kopya** veya **İkisi de**."
    tabs:
      - label: "Canlı kopya"
        body: |
          “Live View'un gösterdiği, durdurduğunuz anda hazır. Oluşturulacak tekrar oynatma ve zaman sınırı yok.”
      - label: "İkisi de"
        body: |
          “Şimdi canlı kopya, sürüşten sonra tekrar oynatma. Tekrar oynatmanın 10 dakikalık sınırı geçerlidir.” Tekrar oynatma, [Bir sürüşü kaydedin](/tr/guides/record) sayfasında anlatıldığı gibi park ettiğinizde oluşturulur.
  - id: quality
    title: "Kalitesini ve sesini seçin"
    body: |
      Canlı kopya seçildiğinde sayfa ilgili satırları ekler. **Canlı kopya kalitesi**, siz **1080p** seçene kadar **720p**'dir. **Ses**, bir mikrofon seçmedikçe kapalıdır: comma'nınki veya bu telefonunki. Ayarlar › Canlı yayın'daki Ses ile aynıdır.
    screen: settings-recordings
    pins:
      - text: "**Canlı kopya kalitesi**: 720p (saatte yaklaşık 1,4 GB) veya 1080p (saatte yaklaşık 2,3 GB)."
      - text: "**Ses**: kapalı, comma'nın mikrofonu veya bu telefonunki."
    note: "Canlı kopya Live View'un gösterdiğini gösterir; **Sürücü kamerası** açıkken sürücü kamerası küçük penceresi de dahil. Sürücü kamerasını dışarıda tutmak için Live View'da Sürücü kamerasını kapatın."
  - id: record
    title: "Live View'da Kayıt'a dokunun"
    body: |
      Araç açık ve hâlâ P konumundayken **Live View**'u açın ve **Kayıt**'a dokunun. Zamanlayıcısı işler ve **Ayrıntılar**, her kayıtta olduğu gibi **Kaydediliyor ·** ile süreyi yazar. Durdurmak için Kayıt'a yeniden dokunun.

      Uygulama değiştirdiğinizde veya telefonu kilitlediğinizde de zamanlayıcısı ve **Durdur** olan **Canlı kopya kaydı yapılıyor** bildirimiyle kaydetmeye devam eder. Live View'u kapatmak onu sonlandırır.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Zamanlayıcısıyla Kayıt. Durdurmak için yeniden dokunun."
      - target: recording
        text: "**Ayrıntılar**'da **Kaydediliyor ·** süre."
    warn: "Kaydı yola çıkmadan önce başlatın veya bir yolcuya bırakın. Sürerken CommaView'da dokunarak gezinmeyin."
  - id: find
    title: "Kayıtlar'da bulun"
    body: |
      **Kayıtlar**'ı açın. Kopya, günün altında süresi ve boyutuyla **Canlı kopya** olarak işaretlidir. Durdurduktan sonra bir an ne kadar ilerlediğiyle **Canlı kopya kaydediliyor…** der; sonra oynar.

      **İkisi de** ile sürüşün iki satırı olur: canlı kopya ve park ettikten sonra sizin oluşturmanızı bekleyen tekrar oynatma.
    screen: phone-recordings
    pins:
      - target: live-copy-row
        text: "**Canlı kopya** olarak işaretli satır."
      - text: "**İkisi de** ile sürüşün tekrar oynatması, ayrı bir satır."
  - id: watch
    title: "İzleyin, paylaşın veya silin"
    body: |
      İzlemek için kopyaya dokunun. Bilgilerine **Sürüm** (**Canlı kopya** veya İkisi de ile **Canlı kopya · tekrar oynatması da var**), **Kalite** ve **Ses** eklenir. **Kayıt işlemleri**'nde **Paylaş**, **Başka bir uygulamada aç**, **Seç** ve **Sil** bulunur.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Kayıt işlemleri**: Paylaş, Başka bir uygulamada aç, Seç ve Sil."
      - text: "**Tam ekran**."
check: "Kopya kaydedilir kaydedilmez Kayıtlar'da oynar ve izleme ekranındaki **Sürüm** **Canlı kopya** der."
fixes:
  - q: "“Canlı kopya için yeterli alan yok: bu telefonda her zaman 500 MB boş bırakır. Artık ihtiyacınız olmayan sürüşleri Kayıtlar'dan silin.”"
    a: "Artık ihtiyacınız olmayan sürüşleri silin veya **Ayarlar › Kayıtlar › Depolama**'da başka bir depolama seçin. Depolama kartı yaklaşık kaç saatlik canlı kopyanın sığacağını söyler."
  - q: "“Canlı kopya durdu: bu telefon neredeyse dolu. Kayıtlar'a kaydedildi; her zaman 500 MB boş bırakır.”"
    a: "Kaydedilenler saklanır. Bir sonraki sürüşten önce biraz yer açın."
  - q: "“Canlı kopya durdu: bir dakikadır comma'dan video yok. Kaydedilenler Kayıtlar'da saklandı.”"
    a: "Telefon bir dakikalığına comma'yı kaybetti, bu yüzden kopya bitti. Telefonunuzun comma'nın Wi‑Fi'ında veya hotspot'unda kaldığını kontrol edin. [CommaView comma'nızı bulamıyor](/tr/guides/comma-not-found) sayfasına bakın."
  - q: "“Bu canlı kopya, bir dosyanın alabileceği en fazla boyut olan 3,5 GB'a ulaştı: Kayıtlar'da yeni bir kopyada devam ediyor.”"
    a: "Hiçbir şey kaybolmaz: sürüş, Kayıtlar'da kendi satırı olan ikinci bir canlı kopyada devam eder."
  - q: "“Tekrar oynatma 10 dakikalık sınırında durdu. Canlı kopya kaydetmeye devam ediyor.”"
    a: "**İkisi de** ile yalnızca tekrar oynatma 10 dakikada durur. Canlı kopya siz durdurana kadar devam eder."
  - q: "“Yalnızca canlı kopya kaydediliyor. Tekrar oynatma başlatılamadı: …”"
    a: "**İkisi de** ile tekrar oynatma kısmı başlayamazken kopya kaydeder; örneğin comma'nın yeniden başlatılması gerektiğinde veya bu telefon onunla eşleştirilmemişken. Mesaj nedenini söyler."
  - q: "Satır “Kaydetmek için 1,2 GB boş alan gerekiyor” diyor"
    a: "Kopyanın parçaları, tek bir videoda birleştirilecek yer olana kadar tutulur. Artık ihtiyacınız olmayan sürüşleri silin; kendiliğinden kaydedilir."
  - q: "**Kaydedildi** bilgisi “Uygulama kapandıktan sonra kurtarıldı: son dakikası eksik olabilir” diyor"
    a: "Uygulama kayıt sırasında kapandı, bu yüzden kopya yazılanlardan bir araya getirildi: son dakikaya kadarı hariç her şey."
  - q: "“CommaView yalnızca ekrandayken yayın ve kayıt yapmaya devam edebilir: Android arka planda çalışmasına izin vermedi.”"
    a: "Android, CommaView'un arka planda çalışmasını engelledi. Kayıt yaparken Live View'u ekranda tutun."
related: [record, export-share, go-live]
blogPost: commaview-0-0-164-carrotpilot-teslahw1-live-copies
---

## Canlı kopya veya tekrar oynatma

| | Canlı kopya | Tekrar oynatma |
| --- | --- | --- |
| Ne gösterir | Live View'un gösterdiğini, gösterdiği gibi | comma'nın kendi videosu, üzerine sürüş ekranı çizilmiş |
| Ne zaman hazır | Durduğunuz anda | Park edip **Tekrar oynatma oluştur**'a dokunduktan sonra |
| Ne kadar uzun | Depolama dışında sınır yok | Kayıt başına en fazla 10 dakika |
| Görüntü | 720p veya 1080p, saniyede 20 kare | En iyi görüntü: **Balanced**, **High** veya **Max** |

## Canlı yayındayken

Canlı kopya ve [canlı yayın](/tr/guides/go-live) tek bir kodlayıcıyı paylaşır. Yayın sırasında başlatılan bir kopya yayının kalitesine sahiptir. Ayarlar › Kayıtlar'daki **Her canlı yayını kaydet**, her canlı yayının gönderildiği hâliyle bir MP4'ünü Kayıt olmadan tutar.

## Gizlilik

Canlı kopyalar telefonunuzda kalır. Asla yüklenmez ve comma'nın eşleştirilmiş diğer telefonlarıyla asla paylaşılmaz. **CommaView'a gönder…** bir sürüş için comma'nın kendi verilerini gönderir, asla bir canlı kopyayı değil. Ses yalnızca bir mikrofon seçtiyseniz, sürücü kamerası yalnızca Sürücü kamerası açıkken kopyadadır.

## Güvenlik

Ayarlarınızı seçmeyi ve Kayıt'ı başlatmayı park hâlinde yapın. Sürerken CommaView'u kullanmayın: openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun.
