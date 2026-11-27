---
title: "Android'de yerel comma kamera yayını: CommaView ne yapar"
description: "CommaView, comma'nızın yol kamerasını sürüş katmanıyla kendi ağınız üzerinden Android'e yayınlar: Live View, Kayıtlar, canlı yayın ve yapmadıkları."
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma camera streaming
  - comma four
  - Android app
  - CommaView
  - local streaming
heroLabel: "Kime uygun"
draft: false
---

CommaView, comma'nızın yol kamerasını sürüş katmanıyla birlikte kendi ağınız üzerinden bir Android telefona, tablete veya multimedya ünitesine yayınlar. comma ile telefonunuz arasında bir bulut yoktur ve önce hiçbir şeyin yüklenmesi gerekmez.

İki parçadan oluşur: CommaView uygulaması ve comma'da, kamerayı ve sürüş verilerini uygulamaya sunan küçük bir çalışma ortamı olan `commaviewd`. Rehberli kurulum çalışma ortamını yükler ve kontrol eder.

## Neden yayınlamalı

comma four'un ekranı 1,9 inç. Yaptığı iş için iyi bir ekran, ama küçük ve sahipleri de bunu söylüyor. comma'nın video almak için sunduğu diğer yollar başka işler için yapılmış:

- **comma connect**, yüklenen sürüşleri 3 gün, comma prime ile bir yıl tutar ([comma.ai/prime](https://comma.ai/prime)). [openpilot 0.11.2](https://blog.comma.ai/0112release/) sürümünden beri araç park hâlindeyken yol ve sürücü kameralarını internet üzerinden, takılı bir comma power ile canlı yayınlayabilir ve comma'da MP4 klipler kesebilir.
- **SSH**, comma'nın depolamasından ham, birer dakikalık HEVC segmentlerini almanızı sağlar.

İkisi de sürerken yolu openpilot'un sürüş katmanıyla göstermez. CommaView bunun için var.

## CommaView ne yapar

### Live View

Canlı yol kamerası, üzerine fork'unuzun kendi ekranı çizilmiş olarak: comma four'unki, comma 3X'inki ya da hızınızı, MAKS'ı, hız sınırını, öndeki aracı ve şerit değiştirmeleri tek bir kümede toplayan CommaView'un kendi ekranı. Live View her fork'un ekranını o fork'un eklediklerle çizer; sunnypilot'un MADS'ından StarPilot'un kendi HUD'una kadar. comma'nın saniyede 20 karesine kadar çalışır ve resim içinde resim modunda devam eder.

Bir tablette veya Android multimedya ünitesinde CommaView, Live View denetimleri sürücü tarafında olacak şekilde bir panel düzenine geçer.

### Kayıtlar

Live View'da Kayıt'a dokunun; park ettiğinizde CommaView o bölüm için comma'nın kendi videosunu, en fazla 10 dakika, indirir ve fork'unuzun ekranını telefonunuzda üzerine çizer: bu bir tekrar oynatmadır. Oynatın, paylaşın veya başka bir uygulamada açın. Canlı kopya, sürerken Live View'un gösterdiğini 720p veya 1080p olarak kaydeder; durduğunuz anda hazırdır ve 10 dakika sınırı yoktur. Kayıtlar siz silene kadar telefonunuzda kalır.

### Yayına başla

Yayına başla, Live View'un gösterdiğini, yolu ve CommaView'un katmanını, YouTube kanalınıza veya herhangi bir RTMP sunucusuna 720p veya 1080p olarak yayınlar. YouTube ile bir kez giriş yapın; her yayını o oluşturur, başlatır ve bitirir. Yayınlar Liste dışı olarak başlar; izleyen herkes nerede sürdüğünüzü görür.

### Yalnızca eşleşmiş telefonlar

comma'nızın kameraları ve verileri yalnızca onunla eşleşmiş telefonlara ve multimedya ünitelerine gider. Video, sürüşler ve yerler, siz göndermedikçe, yayınlamadıkça veya katkı olarak vermedikçe comma'nızdan telefonunuza gider ve başka hiçbir yere gitmez.

## Neler internet gerektirir

Live View ve kayıtlar gerektirmez: aynı yerel ağ üzerinden doğrudan comma'dan telefonunuza giderler; Wi‑Fi'ınız ya da araçta telefonunuzun, multimedya ünitenizin, bir AI box'ın veya comma'nın hotspot'u. Giriş yapmak, uygulama ve çalışma ortamı güncellemeleri, Araç konumu'ndaki harita, sıralama, Yayına başla ve CommaView'a gönderdiğiniz her şey internet gerektirir.

## Neyle çalışır

comma 3X ve comma four; openpilot, sunnypilot, StarPilot, xnor-tech'in openpilot'u, AdventurePilot, SunnyPilot-TeslaHW1 ve carrotpilot üzerinde. Diğer openpilot fork'ları sınırlı destekle çalışır: kurulum fork'u kontrol eder ve yüklemeden önce size sorar. comma 3 desteklenmiyor: ekranından CommaView'un katmanını çizemediği, dondurulmuş bir openpilot sürümünde. [Desteklenen fork'lar](/tr/forks).

Android 8 veya sonrasını çalıştıran bir Android telefon, tablet veya multimedya ünitesi gerekir.

## CommaView ne değildir

- **comma connect değildir.** Sürüşleri bir bulutta tutmaz ve aracınızı şehrin öbür ucundan göstermez. Bunun için connect'i kullanın.
- **Araç kamerası değildir.** Delil niteliğinde kaza veya park görüntüsü gerekiyorsa [özel bir araç kamerası kullanın](/tr/blog/is-comma-a-dashcam).
- **Bir sürüş yardımcısı veya güvenlik sistemi değildir.** comma'nın gördüğünü gösterir; asıl doğruyu yol söyler.

## Güvenle kullanın

CommaView'u park hâlindeyken kurun. Siz sürerken bir yolcu Live View'u izleyebilir; yalnız sürüyorsanız ona comma'nın kendi ekranı gibi davranın ve gözünüzü yoldan ayırmayın.

CommaView yalnızca davetle katılınan bir Beta'da. [Listeye katılın](https://my.commaview.com/join), sıranız geldiğinde size e-posta gönderelim.

CommaView resmî değildir; comma.ai, sunnypilot veya birlikte çalıştığı herhangi bir openpilot fork'u ile bağlantılı değildir ve onlar tarafından onaylanmamıştır. Beta yazılımıdır ve bir güvenlik sistemi değildir: dikkatinizi asla sürüşten dağıtmasına izin vermeyin.
