---
title: "Live View'dan bir sürüşü kaydedin"
description: "Live View'da Kayıt'a dokunun, park edince sürüşün tekrar oynatmasını oluşturun: comma'nın kendi videosu, üzerine fork'unuzun ekranı çizilmiş, telefonunuzda saklanır."
topic: recordings
order: 1
kind: walkthrough
lede: "Live View'daki **Kayıt** bir sürüşü kaydeder. Aksini seçmezseniz bir **tekrar oynatma** oluşturur: park ettiğinizde CommaView, kaydettiğiniz bölüm için comma'nın kendi videosunu en fazla 10 dakika indirir ve sürüş ekranını telefonunuzda üzerine çizer. Hiçbir şey yüklenmez: kayıtlar siz silene kadar telefonunuzda kalır."
parked: true
updated: 2026-11-27
needs:
  - title: "Live View çalışıyor"
    text: "Telefonunuzda, comma'nızla eşleştirilmiş CommaView. Henüz değil mi? [CommaView'u kurun](/tr/guides/setup), ardından [Live View'u açın](/tr/guides/live-view)."
  - title: "Araç açık"
    text: "Kayıt, comma bir sürüşe başladığında başlar; bu yüzden önce aracı çalıştırın. Kaydı yola çıkmadan önce, P konumunda başlatın."
  - title: "Telefonunuzda yer"
    text: "Tekrar oynatma telefonunuzda comma'nın videosundan oluşturulur. Ayarlar › Kayıtlar kullandığı depolamayı ve boş alanı gösterir."
howItWorks:
  - title: "Live View'da kayıt"
    text: "comma'nın kayıt penceresini açar: siz kaydederken sürüş ekranının verilerini tutar."
    edge: "park ettikten sonra"
  - title: "Tekrar oynatma oluştur"
    text: "Telefon o bölüm için comma'nın videosunu indirir, her seferinde bir sürüş."
  - title: "Kayıtlar"
    text: "Tekrar oynatma telefonunuzda, ekran videonun üzerine çizilmiş olarak oynar."
steps:
  - id: choose
    title: "Kayıt'ın ne oluşturacağını seçin"
    body: |
      **Ayarlar**'a, ardından **Kayıtlar**'a dokunun. **Live View'da kayıt** altında siz değiştirene kadar **Tekrar oynatma** seçilidir: “En iyi görüntü: comma'nın kendi videosu, üzerine HUD çizilmiş; park ettikten sonra oluşturulur. Kayıt başına en fazla 10 dakika.”

      **Canlı kopya** bunun yerine Live View'un gösterdiğini zaman sınırı olmadan kaydeder; **İkisi de** ikisini de oluşturur. Bunların [kendi rehberi](/tr/guides/live-copy) var.
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Live View'da kayıt**: **Tekrar oynatma**, **Canlı kopya** veya **İkisi de**."
      - text: "**Tekrar oynatma** kalitesini açar: **Balanced**, **High** veya **Max**. Daha yüksek kalitenin oluşturulması daha uzun sürer ve dosyalar daha büyük olur."
  - id: start
    title: "Live View'da Kayıt'a dokunun"
    body: |
      Araç açık ve hâlâ P konumundayken **Live View**'u açın ve **Kayıt**'a dokunun. CommaView sürüşle eşitlenirken bir an **Başlıyor…** yazar, sonra zamanlayıcısı işler.
    screen: phone-live-view
    clip: record
    pins:
      - target: record-button
        text: "**Kayıt**. Tablette, multimedya ünitesinde veya yan çevrilmiş telefonda şerittedir."
    warn: "Kaydı yola çıkmadan önce başlatın veya bir yolcuya bırakın. Sürerken CommaView'da dokunarak gezinmeyin."
  - id: recording
    title: "Kaydetmesine izin verin"
    body: |
      Kayıt sürerken Kayıt süreyi gösterir ve **Ayrıntılar** **Kaydediliyor ·** ile süreyi yazar. Durdurmak için Kayıt'a yeniden dokunun. Bir tekrar oynatma 10 dakikada ve Live View kapandığında da kendiliğinden durur.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Zamanlayıcısıyla Kayıt. Durdurmak için yeniden dokunun."
      - target: recording
        text: "**Ayrıntılar**'da **Kaydediliyor ·** süre."
      - text: "**Kaydet**, Kayıt olmadan son 3 dakikayı ve sonraki dakikayı tutar. Park ettiğinizde telefonunuza kopyalanır."
    note: "**Kaydet** yalnızca comma'nızın çalışma ortamı sürüşlerini listeleyebildiğinde görünür. O sonraki dakika içinde bir dokunuş bir dakika daha tutar, en fazla 10 dakikaya kadar. Sürerken bunu bir yolcuya bırakın."
  - id: make-replay
    title: "Park edin, ardından tekrar oynatmayı oluşturun"
    body: |
      Park ettikten sonra alttaki çubuktan (daha büyük bir ekranda şeritten) **Kayıtlar**'ı açın. Kaydettiğiniz sürüş **İşlenmesi gerekiyor** der. Açın ve **Tekrar oynatma oluştur**'a dokunun: uygulama “Tekrar oynatma sıraya alındı. Kuyruk'tan takip edin.” der.

      comma bir sürüşü yalnızca araç P konumunda ve openpilot devre dışıyken paylaşır; bu yüzden tekrar oynatma oluşturulana kadar aracı açık ve telefonunuzu comma'nın ağında tutun. Güç kablo demeti yoksa aracı kapatmak comma'yı da kapatır.
    screen: recordings-make-replay
    pins:
      - text: "**Tekrar oynatma oluştur**."
      - target: queue
        text: "**Kuyruk**, oluşturulan her tekrar oynatmayı sırayla, Duraklat, Yeniden dene ve Kaldır ile gösterir."
    note: "**Tekrar oynatma oluştur**'un park ettikten sonra görünmesi bir dakikayı bulabilir: sürüldüğünü söyleyen bir comma'ya bir dakika sonra yeniden sorulur."
  - id: watch
    title: "Kayıtlar'da izleyin"
    body: |
      Oluşturulduğunda uygulama kare sayısıyla **Tekrar oynatma oluşturuldu** der ve sürüş Kayıtlar'da oynar. İzlemek için dokunun, isterseniz tam ekran.
    screen: phone-recordings
    pins:
      - text: "Güne göre gruplanmış, sürüşün tekrar oynatması."
      - target: filter
        text: "**Filtre**: **Tüm sürüşler**, **Hazır** veya **İşlenmesi gerekiyor** ve hangi comma."
check: "Sürüşün satırı artık **İşlenmesi gerekiyor** demez ve dokunduğunuzda oynar. Paylaşmak veya başka bir yere kaydetmek için [Kayıtları paylaşın ve dışa aktarın](/tr/guides/export-share) sayfasına bakın."
fixes:
  - q: "“Kayıt, comma bir sürüşe başladığında başlayabilir.”"
    a: "comma sürüş dışında. Aracı çalıştırın ve openpilot'un başlamasını bekleyin, ardından Kayıt'a yeniden dokunun."
  - q: "“CommaView hâlâ bu sürüşle eşitleniyor. Biraz sonra yeniden Kayıt'ı deneyin.”"
    a: "Kayıt, comma'nın sürüş verileriyle gelen kare zamanlarına ihtiyaç duyar. 5 saniye içinde gelmediler. Biraz bekleyin ve Kayıt'a yeniden dokunun."
  - q: "“CommaView comma'dan sürüş verisi almıyor. Bağlantıyı kontrol edip yeniden Kayıt'ı deneyin.”"
    a: "Video hâlâ oynayabilir ama sürüş verileri durdu. Telefonunuzun hâlâ comma'nın Wi‑Fi'ında veya hotspot'unda olduğunu kontrol edin, ardından yeniden deneyin. Live View **Araç verileri gelmiyor** diyorsa comma'yı yeniden başlatın."
  - q: "“Önce comma'yı yeniden başlatın: CommaView yüklendi, güncellendi veya onarıldı ve yeniden başlatmadan sonra yeniden kayıt yapar.”"
    a: "Araç P konumundayken comma'yı yeniden başlatın, ardından yeniden kaydedin."
  - q: "“Kayıt depolaması dolu. Biraz yer açıp yeniden Kayıt'ı deneyin.”"
    a: "Artık ihtiyacınız olmayan sürüşleri Kayıtlar'da silin veya **Ayarlar › Kayıtlar › Depolama** altında **Değiştir** ile başka bir depolama seçin."
  - q: "“comma'da bu sürüşün HUD verileri için yer kalmadı (yaklaşık 55 dakikalık kayıt). Bir sonraki sürüşünüzde yeniden kaydedin.”"
    a: "comma her sürüş için yaklaşık 55 dakikalık kaydın HUD verilerini tutar. Kaydettiklerinizin tekrar oynatmalarını oluşturun ve bir sonraki sürüşte yeniden kaydedin."
  - q: "“Bu tekrar oynatmayı oluşturmak için vitesi P'ye alın” veya sürüş “Park etmeniz bekleniyor” diyor"
    a: "comma bir sürüşü yalnızca park hâlinde, openpilot devre dışıyken paylaşır. Vitesi P'ye alın ve aracı açık tutun. Tekrar oynatma bekler ve her 15 saniyede bir yeniden sorar; 30 dakikalık sürüşten sonra “Araç hâlâ sürülüyordu, bu yüzden comma bu sürüşü paylaşamadı. Park ettiğinizde yeniden deneyin.” ile durur. Park ettiğinizde Kuyruk'ta **Yeniden dene**'ye dokunun."
  - q: "“Bu tekrar oynatmayı oluşturmak için Comma Chameleon cihazına bağlanın”"
    a: "Telefonunuz sürüşü kaydeden comma'ya ulaşamadı (mesaj sizinkini adlandırır). Telefonunuzu comma'nın Wi‑Fi'ına veya hotspot'una bağlayın, ardından Kuyruk'ta **Yeniden dene**'ye dokunun. [CommaView comma'nızı bulamıyor](/tr/guides/comma-not-found) sayfasına bakın."
  - q: "“Sürüş comma'dan silindi”"
    a: "comma, tekrar oynatması oluşturulmadan önce daha yeni sürüşlere yer açmak için bu sürüşü sildi; bu yüzden artık oluşturulamaz. Kaydı silebilirsiniz. **Tekrar oynatmayı yakında oluşturun** diyen bir sürüş buna yakındır: fırsatınız varken oluşturun."
  - q: "Tekrar oynatma “HUD 2 dk boyunca eksik” diyor"
    a: "comma, kaydın bir bölümü için sürüş ekranının verilerini kaydetmedi. Tekrar oynatma o bölüm boyunca **HUD verileri kullanılamıyor** gösterir ve izleme ekranındaki **HUD verileri** bilgisi ne kadar sürdüğünü söyler."
  - q: "“Tekrar oynatma oluşturuldu: 4.860 kare. comma'nın gücünü kaybettiği yerde erken biter.”"
    a: "Sürüş biterken comma gücünü kaybetti, bu yüzden son anları kaydedilmedi. Kayıtlar **comma'nız bir sürüş biterken gücünü kaybetmiş olabilir** gösterebilir; **Nasıl düzeltilir** comma'nın gücünü ve sürüş dışı süre ayarını açıklar."
related: [live-copy, export-share, live-view]
---

## Tekrar oynatma, canlı kopya veya ikisi de

| Kayıt'ın oluşturduğu | Elde ettiğiniz |
| --- | --- |
| **Tekrar oynatma** (varsayılan) | comma'nın kendi videosu, üzerine sürüş ekranı çizilmiş, park ettikten sonra oluşturulur. En iyi görüntü, kayıt başına en fazla 10 dakika, comma'da sürüş hâlâ dururken. Yalnızca yol ve geniş açı kameraları: tekrar oynatmada sürücü kamerası yoktur. |
| **Canlı kopya** | Live View'un gösterdiği, siz sürerken telefonunuza kaydedilir ve durduğunuz anda hazırdır. Oluşturulacak tekrar oynatma ve zaman sınırı yok. [Canlı kopya kaydedin](/tr/guides/live-copy). |
| **İkisi de** | Şimdi bir canlı kopya, sürüşten sonra tekrar oynatma. Tekrar oynatmanın 10 dakikalık sınırı geçerlidir. |

## Kayıtlar nerede tutulur

Kayıtlar telefonunuzda kalır. **Ayarlar › Kayıtlar › Depolama** kullandıkları depolamayı ve boş alanı gösterir; telefonunuzda varsa **Değiştir** başka bir depolama seçer. Android'in yedeklemesi ve yeni bir telefona aktarım bunları dışarıda bırakır. **CommaView'a gönder…** bir sürüş için yalnızca comma'nın kendi verilerini, yalnızca siz gönderdiğinizde gönderir.

## Güvenlik

Kayıt'ı yola çıkmadan önce başlatın ve tekrar oynatmaları park ettikten sonra oluşturun. Sürerken CommaView'u kullanmayın: openpilot'un istediği gibi gözünüz yolda, elleriniz direksiyonda olsun. CommaView bir araç kamerası veya güvenlik sistemi değildir ve bir kayıt başarısız olabilir.
