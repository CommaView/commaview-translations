---
title: "CommaView 0.0.165: herkes için canlı yayın, CommaView'a gönder ve araç algılama"
description: "CommaView 0.0.165 canlı yayını herkese, CommaView'a gönder'i her üyeye açıyor; üyeler araç algılamaya katkıda bulunabiliyor ve daha fazla fork sınırlı destekle geliyor."
date: 2026-11-01
updatedDate: 2026-11-13
slug: commaview-0-0-165-go-live-send-to-commaview
tags:
  - live streaming
  - YouTube
  - recordings
  - openpilot forks
  - privacy
heroLabel: "Sürüm notları"
draft: false
---

CommaView 0.0.165 Beta'daki herkes için yayında. **Canlı yayın** artık herkese, **CommaView'a gönder** de her üyeye açık; tek bir sürüş veya aynı anda birkaç sürüş için. Yeni çalışma ortamıyla üyeler **sürüşleriyle araç algılamaya katkıda bulunabiliyor**, CommaView artık **daha fazla openpilot fork'una** sınırlı destekle yükleniyor ve comma'nızın kameraları ile verileri **yalnızca onunla eşleşmiş telefonlara** gidiyor.

`v0.0.61-beta` çalışma ortamıyla geliyor. **Önce comma'nızı izleyen her telefon ve multimedya ünitesinde CommaView'u güncelleyin**, sonra uygulama sunduğunda çalışma ortamını uygulamadan güncelleyin ve uygulama istediğinde comma'yı yeniden başlatın. 0.0.164 veya daha eski sürümde kalan bir telefon ya da multimedya ünitesi, v0.0.61 veya sonraki çalışma ortamını kullanan bir comma'dan görüntü alamaz.

## Canlı yayın

Canlı yayın 0.0.164'te erken erişimdeydi. Artık herkese açık: Live View'daki **Yayına başla**, Live View'un gösterdiğini, yani yolu ve CommaView'un katmanını, YouTube kanalınıza veya herhangi bir RTMP sunucusuna 720p veya 1080p olarak yayınlar.

Ayarlar › Canlı yayın'da bir kez kurun: her yayını sizin için oluşturan, başlatan ve bitiren **YouTube ile giriş yap**'ı kullanın ya da bir yayın anahtarı veya sunucu kaydedin. Ardından Yayına başla, Live View'da ya da ekranda yer olmadığında **Daha fazla** menüsünde görünür.

- **Kimler izleyebilir**, Ayarlar › Canlı yayın'da kendi satırına sahip ve Liste dışı olarak başlar. İzleyen herkes nerede sürdüğünüzü görür.
- **Ses**, comma'nızın veya telefonunuzun mikrofonunu seçmediğiniz sürece kapalıdır. Yayınınıza ve canlı kopyalarınıza girer, asla CommaView'a gitmez.
- comma'nızın Wi‑Fi'ında internet olmadığında yayın telefonunuzun mobil verisini kullanır. Ayarlar saatte yaklaşık ne kadar harcadığını söyler.
- YouTube'a giriş ve Yayına başla, telefonunuzun varsayılan ağı bir VPN olduğunda da artık çalışıyor.

Navigasyon'un haritası ve dönüş kartı asla yayında yer almaz.

## CommaView'a gönder

CommaView'a gönder artık her üyeye açık. Kayıtlar'da comma'nızın kaydettiği bir sürüşü seçin ya da birkaçını işaretleyin, sonra ne olduğunu anlatan bir notla **CommaView'a gönder**'e dokunun. Her sürüşün yol ve geniş açı videosunu ve günlüğünü alırız, böylece sorunu görebiliriz; sürücü kamerasını, sesi veya aracınızın şasi numarasını (VIN) asla almayız.

Her sürüş yüklenmeden önce comma'nızdan indirilir; teker teker ve en eskiden başlayarak. Bu yüzden bitene kadar comma'yı açık ve park hâlinde tutun. CommaView her hesap için günde 20 yükleme alır; fazlası ertesi günü bekler.

Aynı **CommaView'a gönder** sayfası artık bize gönderdiğiniz her şeyi taşıyor: bir **Sorun** veya **Fikir**, notunuz ve **Gör** ile açabileceğiniz ya da dışarıda bırakabileceğiniz her ek. Ayarlar › Destek ve tanılama'dan, herhangi bir hatanın **Bildir** düğmesinden ve bir kaydın Daha fazla menüsünden açılır.

## Araç algılamaya katkıda bulunun

Hâlâ erken erişimde olan Surround, telefonunuzda kendi araç algılayıcısını çalıştırır. Üyeler artık sürüşleriyle onu eğitmeye yardım edebilir. comma'nızda yeni çalışma ortamı olmalı.

- **Bir dokunuşla:** bir sürüşün Daha fazla menüsünde ya da seçili birkaç sürüş için **Araç algılamaya katkıda bulun**.
- **Otomatik olarak:** Ayarlar › Gizlilik ve paylaşım › Araç algılama'da **Sürüşlerle otomatik katkıda bulun**'u açın. comma'nızın son sürüşleri (hâlâ sakladığı herhangi bir sürüş) telefonunuz ve comma izin verdiğiniz bir ağdayken, günlük bir sınıra kadar yüklenir. Pil tasarrufunda ya da Live View'u kullanırken veya kayıt yaparken yüklenmez.

**Katkıların yükleneceği ağlar** bu ağları seçer. Varsayılan olan **Seçtiğim ağlar**, telefonunuzun mobil verisini ve comma'nızın kayıtlı Wi‑Fi ağlarını listeler; kullanılacakları işaretleyin, isterseniz her birine aylık sınır koyun. Katkılar sürüşün dakikası başına yaklaşık 110 MB'tır. comma'nız daha önce kullanmadığı bir Wi‑Fi ağına katıldığında Ana sayfa ve bir bildirim onu eklemek isteyip istemediğinizi sorar. comma'nız hangi ağda olduğunu kendisi söyler, bu yüzden CommaView'un konumunuza ihtiyacı yoktur.

Vermeden önce ne verdiğinizi bilin:

- **Katkı sürüşün tamamıdır:** yol ve geniş açı videosu ile günlüğü, gittiği yerler dahil, baştan sona.
- **Kalıcıdır.** CommaView'un eğitim verisinin bir parçası olur ve sonradan kaldırılamaz. Onu size veya comma'nıza bağlayan hiçbir şey yoktur.
- **comma connect bekler.** Bir sürüş gönderilirken comma'nız openpilot onu silmesin diye en fazla bir gün saklar; openpilot'un yükleyicisi de bu sırada onu atlar.

Uygulama bunu ilk katkınızdan önce bir kez açıklar; katkı siz açana kadar kapalı kalır.

## Daha fazla openpilot fork'u, sınırlı destekle

CommaView artık daha fazla openpilot fork'una sınırlı destekle yükleniyor. openpilot'u ve altı fork'unu listeliyor ve her birini her sürümden önce kontrol ediyor. Başka bir openpilot fork'unda kurulum eskiden dururdu. Artık hiçbir şeyi değiştirmeden fork'u kontrol eder ve CommaView görünümünü ekleyebiliyorsa “CommaView bu fork'u doğrulamadı” der: neyin çizildiğini (kameralar, yol çizgisi, şeritler, öndeki araç, uyarılar ve hız) ve neyin çizilmediğini. **Yine de yükle** yalnızca o fork'a yükler.

Live View onu openpilot'un görünümüyle, fork sunnypilot'un ekranı üzerine kuruluysa sunnypilot'unkiyle çizer ve “BluePilotDev/bluepilot · best effort” gibi adını gösterir. Cihaz ayarları'ndaki **Çalışma ortamını kaldır**, fork'un dosyalarını geri koyar.

Kasım 2026'da kontrol edildi: dragonpilot, BluePilot, crwusiz, opgm, zoompilot, jixiexiaoge'nin Carrot'u, NotAutopilot ve daha fazlası kurulum kontrolünden geçiyor; araçta test edilmedi. [Kontrol edilen fork'lar ve dallar](/tr/forks#install-check) desteklenen fork'lar sayfasında.

İki sınır:

- **Sınırlı destek.** CommaView sürümleri fork'unuza karşı kontrol edilmez. Fork kendini CommaView'un izleyemeyeceği bir şeye güncellerse CommaView'un görünümü kapanır ve fork her zamanki gibi sürer.
- **Fork'un kendi ekranı çizilmez.** Düğmeleri, renkleri ve widget'ları Live View'da görünmez; openpilot'un eski yerel ekranı üzerine kurulu fork'lar ise hiç desteklenmez.

## Yalnızca eşleşmiş telefonlar

Yeni çalışma ortamıyla comma'nızın kameraları ve verileri yalnızca onunla eşleşmiş telefonlara ve multimedya ünitelerine gider. Kamerayı başka biri kullanırken Live View “Bu comma'nın kamerasını başka bir cihaz kullanıyor” der ve kendiliğinden yeniden dener.

Çalışma ortamının kurulumları artık kendini de toparlıyor. Kurulum sırasında elektrik kesilmesi veya yeniden başlatma önceki sürümü geri getirir, uygulama dinlemeyi bıraktığında kurulum devam eder ve takılan bir indirme kaldığı yerden sürer.

## 0.0.165'te ayrıca

- **Aynı anda birkaç sürüş.** Kayıtlar'da sürüşleri seçip birlikte paylaşın, tekrar oynatmalarını oluşturun, gönderin veya silin.
- **Live View her ekrana sığıyor.** Denetimleri artık kaymıyor ve **Çık**'ı kesmiyor: sığmayan **Daha fazla**'ya gider, büyük metin de bir şeyi küçültmek yerine denetimleri **Daha fazla**'ya taşır. Live View telefonu da daha az yoruyor ve donmak yerine kendini yeniden çalıştırıyor.
- **Talepleriniz.** Giriş yapmışken bir sorun bildirdiğinizde veya fikir gönderdiğinizde yanıt verebiliyoruz. Ayarlar › Destek ve tanılama › **Talepleriniz** yanıtlarımızı gösterir, size e-posta gelir ve konuşma my.commaview.com'da sürer.
- **Yeniden düzenlenen Ayarlar.** Gizlilik ve paylaşım, telefonunuzdan neyin çıktığını söyler. **CommaView'u geliştirmeye yardım edin**, kilitlenme raporlarının ve comma'nızın çalıştırdığı sürüş yazılımının gönderilip gönderilmeyeceğini bir kez sorar.
- **Sıralama, her üye için.** Artık bir özellik bayrağına bağlı değil.
- **Yeni openpilot'ta Deneysel mod.** chill modunun kalktığı openpilot nightly ve sunnypilot dev'de Live View, Deneysel modu openpilot gibi gösterir.
- **CommaView'u destekleyin.** Ayarlar › Destek ve tanılama › **CommaView'u destekleyin**, barındırma, test ve iOS uygulamasının masraflarına yardım için [Buy Me a Coffee](https://buymeacoffee.com/commaview) sayfamızı açar. Hiçbir şeyin kilidini açmaz.
- **Düzeltmeler.** Android 16 bir multimedya ünitesi, video kod çözücüsü başarısız olduğunda Live View'da CommaView'u artık kapatmıyor; StarPilot'un comma 3X ekranı da görüntüyü siyah gösteren multimedya ünitelerinde kamerasını çiziyor.

## Erken erişim: Navigasyon ve Surround

**Navigasyon**, **Surround**, **Surround V2** ve **Deneysel araçlar**, geri bildirim toplarken özellik bayraklarının arkasında sınırlı bir test grubunda kalıyor.

- **Navigasyon** artık bir yolculuk sırasında Live View'da, videonun yanında veya köşesinde bir harita gösteriyor, yolculuk yokken de **Nereye?** gösteriyor. Köşe haritasında Bitir ve Sesi kapat her zaman orada; Bitir 8 saniye boyunca geri alınabilir ve nereye gideceğinizi sesle söyleyebilirsiniz.
- **Navigasyon'un haritası** artık Açık ve Koyu temalara sahip; comma'nızın bulunduğu yerde gün doğumu ve batımında değişir, böylece güneşte de okunur. Ayarlar › Haritalar ve navigasyon › Harita teması'nda **Otomatik**, **Telefonla aynı**, **Açık** veya **Koyu**'yu seçin.
- **Surround V2**, Surround için deneysel ikinci bir oluşturucu; Ayarlar › Deneysel araçlar altında.

Navigasyon'un rota hesaplaması gibi bazıları ücretli hizmetlerle çalışıyor; bu yüzden grubu şimdilik küçük tutuyoruz. Test etmeye yardım etmek isterseniz [Discord](https://discord.gg/UuMhz9K8ft) sunucumuzdan bize ulaşın ve sürüşlerinizde nasıl çalıştıklarını anlatmaya hazır olun.

## Nasıl güncellenir

CommaView yalnızca davetle katılınan bir Beta'da. Davetliyseniz uygulama 0.0.165'i kendisi sunar.

1. comma'nızla kullandığınız **her telefonda ve multimedya ünitesinde** CommaView'u güncelleyin.
2. Sonra comma'nızın çalışma ortamını uygulamadan güncelleyin.
3. Uygulama istediğinde comma'yı yeniden başlatın. Çalışma ortamı güncellemeleri araç P konumunda ve openpilot devre dışıyken yapılır; böylece bir sürüş asla yarıda kesilmez.

CommaView'da yeni misiniz? [Kurulum rehberi](/tr/guides/setup), uygulamayı yüklemeyi ve comma'nızı bağlamayı adım adım anlatır.

## Daha fazlası

- [Hangi openpilot fork'ları CommaView ile çalışıyor](/tr/forks) ve [listelemediği fork'lar](/tr/forks#unlisted)
- Her sürümde [Yenilikler](/tr/whats-new)
- [CommaView sürümleri nasıl çıkıyor](/tr/guides/releases)
- Canlı yayın, CommaView'a gönder ve katkıların neyi paylaştığı için [Gizlilik politikası](/privacy) (İngilizce)

CommaView resmî değildir; comma.ai, sunnypilot veya birlikte çalıştığı herhangi bir openpilot fork'u ile bağlantılı değildir. Beta yazılımıdır ve bir güvenlik sistemi değildir: dikkatinizi asla sürüşten dağıtmasına izin vermeyin.

## Düzeltme, 13 Kasım 2026

**Araç algılamaya katkıda bulunun** bölümünde bu yazı, bir katkıda onu size veya comma'nıza bağlayan hiçbir şey olmadığını söylüyordu. Bu fazla ileri gitti. Bir katkı ne sizin ne de comma'nızın adını taşır, ama bir sürüşün rotası ve videosu nerede sürdüğünüzü gösterebilir. Bir sonraki uygulama sürümünden itibaren uygulama bunu söylüyor ve bir sonraki katkınızdan önce yeniden onay istiyor; [gizlilik politikası](/privacy) bir katkının sürüşün rotasını içerdiğini zaten söylüyordu. Yazının geri kalanı yayımlandığı gibidir.
