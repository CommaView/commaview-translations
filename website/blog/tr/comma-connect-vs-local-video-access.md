---
title: "comma connect mi, yerel video mu: hangisi ihtiyacınızı karşılar?"
description: "openpilot 0.11.2 sonrası comma connect, SSH ve CommaView karşılaştırması: park hâlinde canlı yayın, klipler, sürüşlerin saklanması, video kalitesi, gizlilik ve her birinin işi."
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - local video access
  - comma four
  - CommaView
heroLabel: "Karar rehberi"
draft: false
---

comma'nın kendi web uygulaması comma connect, çoğu sahibin sürüşlerine ilk baktığı yer ve pek çok iş için doğru yer. openpilot 0.11.2'den beri eskisinden fazlasını yapıyor: park hâlindeki bir aracı canlı yayınlayabiliyor ve cihazda MP4 klipler kesebiliyor. SSH veya CommaView ile yerel erişim farklı bir iş görür: videoyu doğrudan comma'dan, kendi ağınızda alır.

Kısa cevap:

- **Yakın tarihli bir sürüş, her yerden:** comma connect.
- **Park hâlindeki araca göz atmak:** comma connect'in canlı yayını.
- **Sürerken yolu fork'unuzun sürüş katmanıyla daha büyük bir ekranda izlemek:** CommaView'un Live View'u.
- **Geliştirme veya arşiv için ham kamera dosyaları:** SSH.
- **Az önce gördüğünüzün katmanlı bir klibi, telefonunuzda, yükleme olmadan:** CommaView'un Kayıt düğmesi.

## comma connect ne yapar

**Sürüşlerinizi bir süre bulutta tutar.** comma'nın [prime sayfası](https://comma.ai/prime), kayıtların “will upload to connect where they will be stored for 3 days” (connect'e yüklenip 3 gün saklanacağını) söylüyor. comma prime (ayda 24 $, yalnızca ABD, veri dahil) veya prime lite (ayda 14 $, mobil veri isterseniz kendi SIM kartınızla) ile connect onları bir yıl tutar.

**Varsayılan olarak gösterdiği küçük video.** comma'nın [günlük belgeleri](https://docs.comma.ai/concepts/logs/), connect'teki videonun qcamera dosyalarından, yani “lower res versions of the fcamera.hevc” (fcamera.hevc'nin düşük çözünürlüklü sürümlerinden) geldiğini söylüyor; bunlar yavaş bağlantıda hızlı yüklensin diye yapılıyor. Tam çözünürlüklü HEVC dosyaları, onları da yüklemediğiniz sürece comma'da kalır.

**0.11.2'den beri park hâlindeki bir aracı canlı yayınlayabilir.** [0.11.2 sürüm yazısı](https://blog.comma.ai/0112release/) (23 Ekim 2026), bir internet bağlantısı, “home Wi-Fi or comma prime LTE”, ve takılı bir comma power ile “you can livestream your road and driver cameras to see what is happening around your vehicle while it's parked.” (park hâlindeyken aracınızın çevresinde neler olduğunu görmek için yol ve sürücü kameralarınızı canlı yayınlayabileceğinizi) söylüyor. Yayını connect'te, her yerden izlersiniz.

**Klip de keser.** Aynı sürüm connect'e bir klip düğmesi ekliyor: bir sürüşün bir bölümünü seçin, “your comma will stitch and re-encode it as a widely supported MP4 (H.264).” (comma'nız onu birleştirip yaygın desteklenen bir MP4 (H.264) olarak yeniden kodlar). İşlem sürerken comma'yı açık bırakın, sonra klibi connect'ten indirin.

Bu gerçek bir ilerleme. Park hâlindeki aracınızı masanızdan görmek ya da bir arkadaşınıza dün geceki sürüşten bir klip göndermek istiyorsanız connect artık ikisini de yapıyor.

## comma connect'in yapmadıkları

- **Sürerken yayın yapmaz.** Canlı yayın park hâlindeki araç içindir.
- **openpilot'un sürüş katmanını çizmez.** Canlı yayın ve klipler kamera videosudur; comma'nın ekranında gördüğünüz yol çizgisi, şeritler, uyarılar veya hız yoktur.
- **İnternet gerekir.** Canlı yayın için ev Wi‑Fi'ınız veya prime'ın LTE'si gerekir; sürüşlerin de connect'te görünmeden önce yüklenmesi gerekir.
- **prime olmadan 3 gün sonra unutur.** Sonrasında connect, comma hâlâ saklıyor olsa bile sürüşü göstermez.

Bunların hiçbiri bir kusur değil. connect, aracınızı ve sürüşlerinizi nerede olursanız olun görmek için bir bulut hizmetidir.

## Yerel erişim ne yapar

Yerel erişim, videoyu comma'nın sunucularından değil, aynı ağdaki comma'nın kendisinden almak demektir.

### SSH: ham dosyalar

Her openpilot sürüşü comma'da birer dakikalık segmentler hâlinde, her biri kendi dosyalarıyla saklanır: `fcamera.hevc` (yol), `ecamera.hevc` (geniş açı yol), `dcamera.hevc` (sürücü), `qcamera.ts` (küçük önizleme) ve günlükler. comma onları sakladığı sürece SSH üzerinden herhangi birini kopyalayabilirsiniz; yer azaldığında en eski sürüşleri siler. Geliştirme veya kendi arşiviniz için tam çözünürlüklü video almanın yolu bu, ama sonuç paylaşılabilir bir klip değil, birer dakikalık HEVC dosyalarıdır. [comma görüntülerini indirme](/tr/blog/download-comma-dashcam-footage) rehberimiz bunu adım adım anlatıyor.

### CommaView: Android'de Live View ve Kayıtlar

CommaView, bir Android uygulaması ve comma'da küçük bir çalışma ortamı olan `commaviewd`'den oluşur; kamerayı ve sürüş verilerini kendi yerel ağınız üzerinden telefonunuza gönderir: Wi‑Fi'ınız ya da araçtaki bir hotspot, ister telefonunuzun, ister multimedya ünitenizin, ister comma'nınki olsun.

- **Sürerken Live View.** Üzerine fork'unuzun kendi ekranı çizilmiş yol kamerası, comma four'un veya comma 3X'in çizdiği gibi ya da CommaView'un kendi ekranı; bir telefonda, torpidodaki bir tablette veya bir Android multimedya ünitesinde. comma four'un ekranı 1,9 inç; telefonunuzunki çok daha büyük.
- **Telefonunuzda kayıtlar.** Live View'da Kayıt'a dokunun; park ettiğinizde CommaView o bölüm için comma'nın kendi videosunu, en fazla 10 dakika, indirir ve fork'unuzun ekranını telefonda üzerine çizer. Ya da Live View'un gösterdiğinin bir canlı kopyasını 720p veya 1080p olarak, 10 dakika sınırı olmadan kaydedin. Oynatın, paylaşın veya başka bir uygulamada açın.
- **Yayına başla.** Live View'un gösterdiğini, yolu ve katmanı, YouTube kanalınıza veya herhangi bir RTMP sunucusuna 720p veya 1080p olarak yayınlayın.
- **Abonelik yok, yükleme yok.** Live View ve kayıtlar comma'nızdan telefonunuza gider; kayıtlar siz silene kadar orada kalır. comma'nızın kameraları yalnızca onunla eşleşmiş telefonlara ve multimedya ünitelerine gider.

comma 3X ve comma four'da; openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 ve carrotpilot üzerinde, diğer fork'larda da sınırlı destekle çalışır. [Hangi fork'lar ve Live View her birinde ne çizer](/tr/forks).

## Yan yana

| Özellik | comma connect | CommaView |
| --- | --- | --- |
| Canlı video | Yol ve sürücü kameraları, park hâlinde | Yol kamerası, sürerken |
| Sürüş katmanı | Yok | Fork'unuzun ekranı veya CommaView'unki |
| Video nereye gider | İnternet üzerinden, connect'te izlenir | Kendi yerel ağınız (Wi‑Fi veya hotspot) üzerinden eşleşmiş telefonlarınıza |
| Gerekenler | İnternet, canlı yayın için bir comma power | Aynı ağda bir Android telefon, tablet veya multimedya ünitesi |
| Klipler | Sürüşün herhangi bir bölümü; comma'da kesilen ve connect'ten indirilen bir MP4 | Live View'da kaydettikleriniz: en fazla 10 dakikalık bir tekrar oynatma veya bir canlı kopya, katmanıyla |
| Sürüşler ne kadar kalır | 3 gün, prime ile bir yıl | Siz silene kadar telefonunuzda |
| Ücret | Ücretsiz ya da ayda prime 24 $ / lite 14 $ | Abonelik yok; CommaView yalnızca davetle katılınan bir Beta'da |

## İkisini de kullanın

İkisi aynı iş için yarışmıyor. Aracı her yerden görmek ve bulutta durmasını istediğiniz sürüşler için connect'i kullanın; yolu fork'unuzun katmanıyla daha büyük bir ekranda izlemek, gördüğünüzü kaydetmek ve yayınlamak için CommaView'u. Siz sürerken bir yolcu Live View'u izleyebilir; yalnız sürüyorsanız ona comma'nın kendi ekranı gibi davranın ve gözünüzü yoldan ayırmayın.

## Daha fazlası

- connect'in paketleri ve sürüşleri ne kadar tuttuğu için [comma prime](https://comma.ai/prime)
- Canlı yayın ve klipler için [openpilot 0.11.2](https://blog.comma.ai/0112release/)
- SSH üzerinden [comma görüntüleri nasıl indirilir](/tr/blog/download-comma-dashcam-footage)
- [CommaView'u kurun](/tr/guides/setup)

CommaView resmî değildir; comma.ai, sunnypilot veya birlikte çalıştığı herhangi bir openpilot fork'u ile bağlantılı değildir ve onlar tarafından onaylanmamıştır. Beta yazılımıdır ve bir güvenlik sistemi değildir: dikkatinizi asla sürüşten dağıtmasına izin vermeyin.
