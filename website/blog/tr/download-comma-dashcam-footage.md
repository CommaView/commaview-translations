---
title: "comma cihazından araç kamerası görüntüleri nasıl indirilir"
description: "comma video dosyaları, comma 3/3X/four arasındaki farklar ve rota görüntülerini dışa aktarmanın en güvenli yolları için uygulamalı bir rehber."
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma device video
  - dashcam footage
  - openpilot tools
  - SSH
heroLabel: "comma cihazı rehberi"
draft: false
---

Bir comma cihazından video mu almanız gerekiyor? Bilinen yollar comma connect, Openpilot Toolkit ya da doğrudan SSH/SFTP erişimi.

İnsanların takıldığı kısım dosya düzeni. comma cihazları openpilot rotalarını tek bir dev araç kamerası klibi olarak değil, kısa segmentler hâlinde kaydeder. Her segmentte ham kamera dosyaları, önizleme videosu ve rota günlükleri olabilir. Bunu kavradığınızda görüntüleri dışa aktarmak çok daha az gizemli olur.

Baştan önemli bir not: bir comma cihazı yol görüntüleri, hata ayıklama ve rota incelemesi için işe yarar, ama özel bir araç kamerasının yerine doğrudan geçemez.

## comma cihazları işe yarar kameralardır, kusursuz araç kameraları değil

Özel bir araç kamerası delil kaydı etrafında tasarlanır: hızlı açılış, kazaya dayanıklılık, park modu, kolay dosya aktarımı, arka kamera seçenekleri ve çıkarılabilir depolama.

Bir comma cihazı openpilot'u çalıştırmak için yapılır. Rota verilerini kaydeder, çünkü bu sürüş modelleri, hata ayıklama, connect önizlemeleri ve geliştirme için faydalıdır. O görüntüler değerli olabilir, ama bazı ödünlerle gelir:

- görüntüleri almak bir SD kartı çıkarmaktan daha zor olabilir
- bir kaza veya ani güç kaybı son görüntülere mal olabilir
- park modunda kayıt temel tasarım hedefi değildir
- arkaya bakan araç kamerası kapsamı yoktur
- cihaz yere ihtiyaç duyduğunda eski yerel veriler silinir

Amaç güvenilir kaza görüntüsüyse gerçek bir araç kamerası kullanın. Amaç openpilot rota görüntüleri, geliştirme incelemesi veya yerel video aktarımıysa comma'nın işleyişini öğrenmeye değer.

## openpilot hangi dosyaları kaydeder?

openpilot'un resmî günlük belgeleri rotaları birer dakikalık segmentler olarak tanımlar. Güncel openpilot her segment için şu dosya türlerini kaydeder:

| Dosya | İçeriği |
| --- | --- |
| `fcamera.hevc` | yol kamerası videosu, H.265/HEVC |
| `ecamera.hevc` | geniş açı yol kamerası videosu, H.265/HEVC |
| `dcamera.hevc` | sürücü/kabin kamerası videosu, H.265/HEVC |
| `qcamera.ts` | yol kamerasından düşük çözünürlüklü H.264 önizleme |
| `rlog.zst` | tam rota günlükleri |
| `qlog.zst` | daha küçük/seyreltilmiş rota günlükleri |

comma connect'te gösterilen video düşük çözünürlüklü `qcamera.ts`'dir. Tam çözünürlüklü kamera görüntüleri HEVC dosyalarındadır ve connect üzerinden elle yüklenmeleri ya da doğrudan cihazdan kopyalanmaları gerekebilir.

Eski rotalar, eski fork'lar veya eski belgeler `.zst` olmadan `rlog`/`qlog` ya da eski `.bz2` günlük adları gösterebilir. Güncel openpilot için yukarıdaki adları kullanın.

## comma 3, comma 3X ve comma four: ne değişiyor?

İnsanların karıştırdığı iki ayrı konu var: kamera donanımı ve dosya düzeni.

Kamera donanımı nesle göre farklı:

| Cihaz | Kamera/depolama notları |
| --- | --- |
| comma 3 | 120 dB HDR'li üç 1080p kamera. Topluluk belgeleri birkaç depolama türü listeler: 1TB, 250GB, geç dönem 64GB ve erken dönem 32GB. |
| comma 3X | comma 3 ile aynı üçlü kamera düzeni, yükseltilmiş OX03C10 görüntü sensörleri, 140 dB HDR ve genellikle 128GB depolama olarak listelenir. |
| comma four | comma onu comma 3X ile aynı işlem gücüne, sensör takımına ve işlevlere sahip, ama çok daha küçük bir gövdede olarak tanımlıyor. Üçlü kamera sistemi 1,9 inçlik ekranın kapladığı alana sığıyor: yola bakan iki kamera ve gece görüşlü bir kabin kamerası. comma 128GB depolama ve 10 saat görüntü belirtiyor. |

Buradaki dosya notları üçü için de geçerli. CommaView'un kendisi yalnızca comma 3X ve comma four ile çalışır.

Güncel openpilot için pratik dosya düzeni comma donanımları arasında ortaktır. Güncel segment dosyaları `fcamera.hevc`, `ecamera.hevc`, `dcamera.hevc`, `qcamera.ts`, `rlog.zst` ve `qlog.zst`'dir.

Yani kameralar fiziksel olarak değişebilir ama dışa aktarılan adlar tanıdık kalır. `fcamera.hevc` yol kamerasıdır. `ecamera.hevc` geniş açı yol kamerasıdır. `dcamera.hevc` sürücü/kabin kamerasıdır.

Özel bir fork kullanıyorsanız her dosyanın var olduğunu varsaymadan önce cihazda doğrulayın. Fork'lar kayıt ayarlarını değiştirebilir ve sürücü/kabin kaydı cihaz ayarlarına bağlı olabilir.

## Dosyalar yerelde nerede saklanır?

comma donanımında openpilot'un güncel günlük kök dizini şudur:

```text
/data/media/0/realdata
```

Bu klasörün içinde her rota segmentinin zaman damgalı kendi klasörü vardır, örneğin:

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

Şu tür dosyaları aradığınız klasör orasıdır:

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

Doğrudan SSH/SFTP ile çalışırken başlayacağınız klasör budur. Resmî belgeler bir comma 3X'e veya comma four'a SSH ile nasıl bağlanılacağını açıklar; openpilot da cihazdaki günlük kök dizini olarak `/data/media/0/realdata`'yı kullanır.

## Seçenek 1: comma connect'i kullanın

Yakın tarihli sürüşler için comma connect genellikle başlamanın en kolay yoludur.

connect'i şu durumlarda kullanın:

- rota yeni
- cihaz rotayı başarıyla yükledi
- önizleme videosu yeterli
- SSH yerine bir web arayüzü istiyorsunuz
- yalnızca birkaç klip veya dosyaya ihtiyacınız var

connect, birçok kullanıcının ihtiyaç duyduğu rota ve segment numaralarını ilk bulduğu yerdir. Sorun saklama süresi: connect, yerel cihaz silmeden önce bir rotayı göstermeyi bırakabilir. connect bir rotayı artık göstermiyor ama dosyalar hâlâ cihazdaysa SSH/SFTP ile kurtarılabilir.

connect önizlemelerinin `qcamera.ts` tabanlı olduğunu da unutmayın. Tam çözünürlüklü kamera görüntüsü gerekiyorsa tam video dosyalarının yüklendiğinden emin olun veya ham HEVC dosyalarını doğrudan alın.

## Seçenek 2: Openpilot Toolkit'i kullanın

Openpilot Toolkit, yerel aktarımı daha zahmetsiz hâle getirebilen bir topluluk aracıdır. SSH kurulumu, dosyalara göz atma, sürüş videosu önizleme ve ham dışa aktarma için akışlar içerir.

Openpilot Toolkit'i şu durumlarda kullanın:

- bir grafik arayüz istiyorsunuz
- SSH komutlarını elle yazmak istemiyorsunuz
- anahtarları kurmak için yardıma ihtiyacınız var
- Windows veya Android kullanıyorsunuz
- rota görüntülerine daha doğrudan göz atıp dışa aktarmak istiyorsunuz

Birçok kullanıcı için en iyi orta yol budur: connect'ten daha fazla kontrol, elle terminal işinden daha az zahmet.

## Seçenek 3: SSH veya SFTP'yi doğrudan kullanın

Doğrudan SSH/SFTP en çok kontrolü ve en az yardımı verir.

Genel hatlarıyla SSH erişimi genellikle şu demektir:

1. SSH anahtarları olan bir GitHub hesabı oluşturun veya kullanın.
2. comma cihaz ayarlarında SSH'yi etkinleştirin.
3. Açık anahtarlarınızı alabilmesi için comma cihazına GitHub kullanıcı adınızı girin.
4. `22` numaralı portta `comma` kullanıcısıyla bağlanın.

Bağlandıktan sonra şuradan göz atın veya kopyalayın:

```text
/data/media/0/realdata
```

Doğrudan erişimi şu durumlarda kullanın:

- ham `fcamera.hevc`, `ecamera.hevc` veya `dcamera.hevc` dosyalarına ihtiyacınız var
- connect ihtiyacınız olan dosyayı göstermiyor
- bir rotanın tamamını arşivlemek istiyorsunuz
- FileZilla veya WinSCP gibi SFTP istemcilerini rahatça kullanıyorsunuz
- `ssh`, `scp` veya `rsync` ile rahatsınız

Ham `.hevc` dosyaları çoğu zaman VLC'de oynar. Başka bir uygulama MP4 istiyorsa mümkün olduğunda yeniden kodlamak yerine ffmpeg ile remux yapın.

## Hangi yöntemi kullanmalısınız?

Sürüş yeniyse ve normal rota incelemesi yetiyorsa comma connect'i kullanın.

Her SSH/SFTP adımını elle yapmadan daha kolay bir yerel akış istiyorsanız Openpilot Toolkit'i kullanın.

Ham dosyalara, eski yerel dosyalara, eksiksiz rota arşivlerine ya da neyin kopyalanacağı üzerinde doğrudan kontrole ihtiyacınız varsa SSH veya SFTP kullanın.

## CommaView nereye oturuyor

CommaView; comma kamera yayını, katmanlar, çalışma ortamı kurulumu, kayıtlar ve tekrar oynatma için önce yerel çalışan bir Android uygulamasıdır.

Yerel kamera erişiminin aynı dünyasında yer alır, ama comma connect değildir, Openpilot Toolkit değildir ve geleneksel bir araç kamerası da değildir. Bir sürüş yardımcısı olarak ya da bir araçtaki tek delil kayıt sistemi olarak kullanılmamalıdır.

CommaView, openpilot veya [desteklenen bir fork](/tr/forks) çalıştıran comma 3X ve comma four ile çalışır: sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 veya carrotpilot. comma 3 desteklenmiyor: comma onu, ekranından CommaView'un katmanını çizemediği, dondurulmuş uzun vadeli bir openpilot sürümüne taşıdı ([neden](/tr/#faq-comma-3)).

## Daha fazlası

- Resmî openpilot günlük belgeleri: [Logging](https://docs.comma.ai/concepts/logs/)
- Resmî comma SSH belgeleri: [comma 3X veya comma four'a bağlanma](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect: [comma.ai/connect](https://comma.ai/connect)
- openpilot wiki: [Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma: [Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit: [proje sayfası](https://spektor56.github.io/OpenpilotToolkit/)
