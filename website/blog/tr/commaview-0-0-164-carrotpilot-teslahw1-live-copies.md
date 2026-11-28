---
title: "CommaView 0.0.164: carrotpilot, SunnyPilot-TeslaHW1 ve canlı kopyalar"
description: "CommaView 0.0.164; carrotpilot ve SunnyPilot-TeslaHW1'i, sürerken Live View'un gösterdiğini kaydeden canlı kopyaları ve Navigasyon ile Surround'a erken erişimi getiriyor."
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot forks
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - recordings
heroLabel: "Sürüm notları"
draft: false
---

CommaView 0.0.164 Beta'daki herkes için yayında. İki openpilot fork'u daha ekliyor, **carrotpilot** ve **SunnyPilot-TeslaHW1**; böylece CommaView artık yedi tanesiyle çalışıyor: openpilot, sunnypilot, StarPilot, xnor-tech'in openpilot'u, AdventurePilot, SunnyPilot-TeslaHW1 ve carrotpilot. Ayrıca, siz sürerken Live View'un gösterdiğini kaydeden ve durduğunuz anda hazır olan **canlı kopyaları** getiriyor.

Yeni iki fork'u tanıyan `v0.0.60-beta` çalışma ortamıyla geliyor. Uygulama sunduğunda çalışma ortamını uygulamadan güncelleyin ve uygulama istediğinde comma'yı yeniden başlatın.

## SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1, Tesla'nın HW1 (Autopilot 1) araçlarını ekleyen bir sunnypilot fork'u. Ekranı sunnypilot'un ekranı olduğu için CommaView sunnypilot'un ekranını sunnypilot'un eklediği her şeyle çizer ve uygulamada fork'un adını gösterir.

Bilmeniz gereken bir şey: `op fork update` komutu, CommaView'un kancası yüklüyken fork'u değiştiremez. Önce CommaView'u kaldırın ya da comma'nın ekranındaki fork değiştiriciyi kullanın; o her zamanki gibi çalışır.

## carrotpilot

carrotpilot, Hyundai, Kia ve Genesis araçları için bir openpilot fork'u; `i.carrotpilot.app` üzerinden yüklenir. CommaView onun için openpilot'un ekranını hızınız, yol çizgisi, şeritler ve öndeki araçla birlikte çizer ve uygulamada fork'un adını gösterir.

Şimdilik iki sınır var:

- **carrotpilot'un kendi ekranı henüz çizilmiyor.** openpilot'un ekranına eklediği navigasyon, hız kameraları ve HUD gibi şeyler Live View'da görünmez.
- **Güncellemeleri, comma yeniden başlatılana kadar CommaView'un kancasını kaldırır.** carrotpilot'un otomatik güncellemesi ve web sayfasındaki Git araçları, çalışırken dosyalarını sıfırlar. Hiçbir şey bozulmaz: uygulama yeniden başlatma ister ve Live View ardından geri gelir.

## Canlı kopyalar

Şimdiye kadar Kayıt bir tekrar oynatma oluşturuyordu: park ettiğinizde uygulama comma'nın kendi videosunu indirir ve HUD'u üzerine çizer. Bu hâlâ en iyi görüntü, ama sürüşten sonra biraz zaman alır ve kayıt başına 10 dakikada durur.

Ayarlar › Kayıtlar › **Live View'da kayıt** artık Kayıt'ın ne oluşturacağını seçmenizi sağlıyor:

| Seçenek | Elde ettiğiniz |
| --- | --- |
| Tekrar oynatma (varsayılan) | Üzerine HUD çizilmiş, comma'nın kendi videosu; park ettikten sonra oluşturulur. En iyi görüntü, kayıt başına en fazla 10 dakika. |
| Canlı kopya | Sürerken Live View'un gösterdiği; telefonunuza kaydedilir ve durduğunuz anda Kayıtlar'da hazırdır, 10 dakika sınırı yoktur. |
| İkisi de | Hemen bir canlı kopya, sürüşten sonra da tekrar oynatma. |

Canlı kopya saniyede 20 karede 720p (saatte yaklaşık 1,4 GB) veya 1080p (saatte yaklaşık 2,3 GB) olur. Uygulama değiştirdiğinizde veya telefonu kilitlediğinizde de devam eder; onu durdurabileceğiniz bir bildirim gösterir. Telefonunuzun depolama alanı dolmadan düzgünce durur; kayıt sırasında uygulama kapanırsa son dakika dışında her şey sizde kalır.

Canlı kopyalar telefonunuzda kalır ve asla yüklenmez.

## 0.0.164'te ayrıca

- **Tüm ekranı kullanan ayarlar.** Kayıtlar, Ekran ve Canlı yayın sayfaları Çevrimdışı haritalar gibi, sığdığında iki sütun hâlinde yerleşir; tabletlerde, multimedya ünitelerinde ve yan tutulan telefonlarda düzgün hizalanır.
- **Bir kurulum neden başarısız oldu.** Kurulum, çalışma ortamı güncellemesi veya kaldırma başarısız olursa uygulama neyin ters gittiğini ve ne yapılacağını söyler: CommaView'un desteklemediği bir fork, aracın sürülüyor olması, comma'da internet olmaması, bozuk bir indirme. comma'nızın eski hâline getirilip getirilmediğini söyler; **Ayrıntıları kopyala** da desteğin ihtiyaç duyduğu raporu kopyalar.
- **Daha hızlı tekrar oynatmalar.** Tekrar oynatma yalnızca gösterdiği videoyu indirir ve biri oluşturulurken kuyruktaki sonraki sürüş indirilir. Uygulamanın kapanması, 10 dakika sınırı veya aracın kapanmasıyla yarıda kalan bir kayıt da artık tekrar oynatmaya dönüştürülebilir.
- **Tekrar oynatma kalitesi yine çalışıyor.** Balanced, High ve Max yine farklı tekrar oynatmalar üretiyor: her tekrar oynatma aynı 40 Mbit/s ile oluşturuluyordu. Varsayılan olan High, bir comma 3X'ten artık yaklaşık yarı boyutta dosyalar üretiyor.

## Erken erişim: Navigasyon ve Surround

Bazı özellikler erken geliştirme aşamasında: **Navigasyon**, **Surround**, **Yayına başla** ve **CommaView'a gönder**. Geri bildirim toplarken bunları özellik bayraklarının arkasında sınırlı bir test grubuna açıyoruz; bu yüzden yalnızca bunların açık olduğu hesaplarda görünürler.

- **Navigasyon**, Ana sayfadan Live View'a kadar adım adım yönlendirme: bir yer arayın, bir rota seçin, sonra dönüş kartını, sesli yönlendirmeyi ve CommaView ekranında şeridinize çizilen okları izleyin. Yanlış bir dönüşte birkaç saniye içinde yeni rota bulunur. Yalnızca görüntüdür: comma'nıza veya aracınıza hiçbir şey gönderilmez.
- **Surround**, aracınızın çevresindeki yolun 3B görünümü: kameranın gördüğü yol, şerit çizgileri ve kavşaklarıyla, çevrenizdeki otomobiller, kamyonlar ve trafik ışıklarıyla.

Navigasyon'un rota hesaplaması gibi bazıları ücretli hizmetlerle çalışıyor; bu yüzden normal kullanımın maliyetini öğrenene kadar grubu küçük tutuyoruz. Test etmeye yardım etmek isterseniz [Discord](https://discord.gg/UuMhz9K8ft) sunucumuzdan bize ulaşın ve sürüşlerinizde nasıl çalıştıklarını anlatmaya hazır olun.

## Nasıl edinilir

CommaView yalnızca davetle katılınan bir Beta'da. Davetliyseniz uygulama 0.0.164 güncellemesini kendisi sunar. Güncellendikten sonra comma'nızdaki çalışma ortamını uygulamadan güncelleyin, sonra istendiğinde comma'yı yeniden başlatın. Çalışma ortamı güncellemeleri araç P konumunda ve openpilot devre dışıyken yapılır; böylece bir sürüş asla yarıda kesilmez.

CommaView'da yeni misiniz? [Kurulum rehberi](/tr/guides/setup), uygulamayı yüklemeyi ve comma'nızı bağlamayı adım adım anlatır.

## Daha fazlası

- [Hangi openpilot fork'ları CommaView ile çalışıyor](/tr/forks); [SunnyPilot-TeslaHW1](/tr/forks#teslahw1) ve [carrotpilot](/tr/forks#carrotpilot) dahil
- Her sürümde [Yenilikler](/tr/whats-new)
- [CommaView sürümleri nasıl çıkıyor](/tr/guides/releases)

CommaView resmî değildir; comma.ai, sunnypilot, carrotpilot veya SunnyPilot-TeslaHW1 ile bağlantılı değildir. Beta yazılımıdır ve bir güvenlik sistemi değildir: dikkatinizi asla sürüşten dağıtmasına izin vermeyin.
