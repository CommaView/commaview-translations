---
title: "comma cihazı bir araç kamerası mı? İşe yarar, ama yerini tutmaz"
description: "openpilot 0.11.2 sonrası comma görüntülerine güvenlik odaklı bir bakış: rota dosyaları, connect'te saklama ve klipler, yerel depolama, kaza görüntüsü, park modu ve araç kameraları."
date: 2026-11-06
slug: is-comma-a-dashcam
tags:
  - comma dashcam
  - comma device video
  - dashcam footage
  - openpilot
heroLabel: "Araç kamerası gerçekleri"
draft: false
---

Bir comma cihazı işe yarar yol ve kabin görüntüleri kaydedebilir. Bu, onu özel bir araç kamerasının doğrudan yerine geçen bir şey yapmaz.

Görüntüler rota incelemesine, hata ayıklamaya, dışa aktarmaya ve bir olayın bağlamını anlamaya yardım edebilir. Ama özel bir araç kamerası farklı varsayımlar üzerine kuruludur: kazaya dayanıklı delil kaydı, basit çıkarılabilir depolama, park modu, arka kamera kapsamı ve bir ev aleti kadar kolay erişim.

Güvenilir kaza veya sigorta görüntüsü sizin için önemliyse comma cihazının yanında özel bir araç kamerası kullanın. Sıkıcı cevap, doğru cevap.

## Bir comma cihazı ne kaydeder

openpilot cihaz çalışırken rotaları kaydeder. Güncel günlük belgeleri rotaları segment tabanlı olarak, şu gibi kamera ve günlük dosyalarıyla tanımlar:

- `fcamera.hevc` — yol kamerası videosu
- `ecamera.hevc` — geniş açı yol kamerası videosu
- `dcamera.hevc` — sürücü/kabin kamerası videosu
- `qcamera.ts` — düşük çözünürlüklü önizleme videosu
- `rlog.zst` — tam rota günlüğü
- `qlog.zst` — daha küçük rota günlüğü

Bu çok faydalı bir veri.

Ama tek, basit bir “araç kamerası klibi” de değil. Bu, openpilot'un rota kaydı: segmentlere ayrılmış dosyalar, rota kimlikleri, yükleme davranışı, yerel saklama, kodekler, günlükler ve araçlar.

## Görüntüler nerede bulunabilir

İnsanların ilk baktığı iki genel yer var:

1. Bulutta görünen yakın tarihli sürüşler için **comma connect**.
2. comma cihazında hâlâ duran dosyalar için **cihazın yerel depolaması**.

comma'nın [prime sayfası](https://comma.ai/prime), yüklenen sürüşlerin connect'te 3 gün, comma prime ile 1 yıl saklandığını söylüyor. Varsayılan olarak connect düşük çözünürlüklü `qcamera` videosunu gösterir ([comma'nın günlük belgeleri](https://docs.comma.ai/concepts/logs/)).

[openpilot 0.11.2](https://blog.comma.ai/0112release/) (Ekim 2026) sürümünden beri connect bir sürüşün bir bölümünden klip de kesebiliyor: comma açık kaldığı sürece onu MP4 olarak yeniden kodlar, siz de connect'ten indirirsiniz. Bu, paylaşılabilir tek bir klip almayı eskisinden çok daha kolay hâle getiriyor.

Yerel openpilot depolaması farklıdır. Güncel comma donanımında pratik rota verisi alanı `/data/media/0/realdata/` altındadır. Ama yerel depolama sonsuz değil. openpilot'un yer azaldığında temizleme davranışı var; yani eski rotalar kalıcı bir arşiv değildir.

Önemli bir şey varsa onu hemen saklayın.

## İnsanlar comma görüntülerini neden yine de kullanıyor

comma görüntüleri gerçekten işe yarayabilir.

İyi kullanımlar şunlardır:

- bir rotada ne olduğunu incelemek
- openpilot'un davranışında hata ayıklamak
- kamera/günlük bağlamını kontrol etmek
- klipleri veya ham HEVC dosyalarını dışa aktarmak
- geliştirme veya destek örnekleri paylaşmak
- tekrar oynatma/test akışlarını beslemek

Zaten bir comma cihazınız varsa o görüntüleri görmezden gelmek saçma olur. Değerlidir.

Hata, “değerli”nin “özel bir araç kamerasıyla aynı iş” anlamına geldiğini varsaymaktır.

## Neden özel bir araç kamerasının yerini tutmaz

Özel bir araç kamerası genellikle önce delil kaydı için yapılır.

Bu çoğu zaman basit depolama, hızlı erişim, park modları, arka veya iç kamera seçenekleri, bağımsız çalışma ve bir olaydan sonra klipleri korumaya göre tasarlanmış akışlar demektir.

Bir comma cihazı openpilot'u çalıştırmak için yapılır. Kamera verisi, openpilot'un günlük kaydına, model geliştirmeye, hata ayıklamaya, rota incelemesine ve connect önizleme akışlarına ihtiyacı olduğu için vardır.

Bu öncelikler araç kamerası ihtiyaçlarıyla örtüşür, ama aynı değildir.

## Risk alanları

### Kaza ve güç kaybına dayanıklılık

Cihaz gücünü kaybederse, hasar görürse veya yanlış zamanda kapanırsa son görüntüleri kurtarmak zorlaşabilir ya da görüntüler eksik olabilir.

Bu, comma görüntülerinin her olayda işe yaramaz olduğu anlamına gelmez. Tek delil planınız olmaması gerektiği anlamına gelir.

### Park modu

Özel araç kameraları sabit kablo kitiyle park modunu çoğu zaman temel özellik olarak satar.

openpilot 0.11.2, internet bağlantısı ve takılı bir comma power ile park hâlindeki bir aracın yol ve sürücü kameralarını connect'te canlı yayınlamanızı sağlıyor. comma'nın yazısı bunu aracın çevresinde neler olduğunu görmenin bir yolu olarak tanımlıyor; park modunda bir olay kaydedicisi olarak sunmuyor.

Çok özel, doğrulanmış bir kurulumunuz yoksa ve riskleri anlamıyorsanız park gözetimini özel araç kameralarının işi olarak görün.

### Arka kapsama

comma'nın yol, geniş açı yol ve kabin/sürücü kameraları arkaya bakan bir araç kamerasıyla aynı şey değildir.

Arka kapsama önemliyse arkayı kaydeden bir donanım kullanın.

### Depolama ve dışa aktarma zahmeti

Bir araç kamerası genellikle microSD, uygulama veya ekrandan basit klip erişimini hedefler.

comma'dan görüntü almak connect'in görünürlük süreleri, elle yükleme, segment kimlikleri, SSH/SFTP, HEVC dosyaları, yerel temizlik, VLC/ffmpeg/remux veya yardımcı araçlar gerektirebilir. connect'in yeni klipleri yardımcı oluyor, ama klip hazırlanırken comma açık kalmalı ve sürüş hâlâ orada olmalı.

Teknik kullanıcılar için bu sorun değil. Ama bir ev aleti kadar basit değil.

## comma görüntüleri ne zaman yeterli olabilir

comma görüntüleri şunlar için yeterli olabilir:

- gündelik yol görüntüsü başvurusu
- openpilot rota incelemesi
- hata ayıklama ve test
- geliştirme desteği
- rota hâlâ duruyorken yerel aktarım
- bir olayı gerçekleştikten kısa süre sonra incelemek

Güçlü bir liste.

Yine de comma cihazını tek ciddi delil kaydediciniz yapmaz.

## Ne zaman bir araç kamerası eklenmeli

Şunları önemsiyorsanız özel bir araç kamerası kullanın:

- güvenilir kaza veya sigorta görüntüsü
- park gözetimi
- arka kapsama
- mümkün olan en kolay erişim
- çıkarılabilir depolama
- comma cihazı gücünü kaybederse bağımsız kayıt
- teknik olmayan sürücüler için daha basit bir araç

Bu ikili tuhaf değil. Bir comma cihazı openpilot işleri için harika olabilirken bir araç kamerası sıkıcı delil kaydını üstlenir.

## CommaView nereye oturuyor

CommaView, bir Android uygulaması ve comma'da küçük bir çalışma ortamıdır. comma'nın yol kamerasını fork'unuzun sürüş katmanıyla telefonunuzda, tabletinizde veya Android multimedya ünitenizde, kendi ağınız üzerinden canlı gösterir ve kaydettiklerinizi telefonunuza kaydeder. Live View'da Kayıt'a dokunun; park ettiğinizde o bölüm için comma'nın kendi videosunu, en fazla 10 dakika, indirir ve katmanı üzerine çizer. Ya da Live View'un gösterdiğinin bir canlı kopyasını 10 dakika sınırı olmadan kaydedin. Hiçbir şey yüklenmez ve kayıtlar siz silene kadar telefonunuzda kalır. Siz Kayıt'a dokunduğunuzda kaydeder, kendiliğinden değil; yani gelmesini görmediğiniz bir olayda yardımcı olmaz.

Bu, gördüğünüzün klibini almayı çok kolaylaştırır. Bir comma cihazını güvenlik açısından kritik bir araç kamerasına dönüştürmez.

Delillerin korunmasını garanti etmez.

Bir sürüş yardımcısı değildir.

Ve yalnızca comma 3X ve comma four ile çalışır, comma 3 ile değil. CommaView resmî değildir; comma.ai ile bağlantılı değildir ve comma.ai tarafından onaylanmamıştır.

## Bir olaydan sonra pratik kontrol listesi

Hukuki tavsiye değil, sadece pratik bir önceliklendirme:

1. Sürmeyi bırakın ve önce güvenlik/acil durum ihtiyaçlarıyla ilgilenin.
2. Yalnızca connect'in saklama süresine güvenmeyin.
3. İlgili rota segmentlerini mümkün olan en kısa sürede saklayın/dışa aktarın.
4. connect kullanıyorsanız ihtiyacınız olan rotayı ve zaman aralığını belirleyin.
5. connect dosyaları göstermiyor ama cihazda hâlâ duruyorsa sahibinin yetki verdiği SSH/SFTP'yi veya güvenilir bir yerel aracı kullanın.
6. Mümkünse orijinal dosyaları saklayın.
7. Önemli görüntüler kopyalanana kadar yıkıcı düzenlemelerden veya temizlikten kaçının.
8. Hukuki/sigorta konuları için uygun uzmanlarla konuşun.

Ana fikir: hızlı davranın, dikkatle kopyalayın ve görüntülerin sonsuza kadar bekleyeceğini varsaymayın.

## Dürüst cevap

Bir comma cihazı, openpilot rotaları için işe yarar bir kamera ve veri kaydedicidir. Değerli bir video bağlamı sağlayabilir.

Ama soru “araç kamerasından vazgeçebilir miyim?” ise güvenli cevap hayır.

comma görüntülerini rota incelemesi, hata ayıklama ve yerel işler için kullanın. Güvenilir delil kaydı gerektiğinde özel bir araç kamerası kullanın.
