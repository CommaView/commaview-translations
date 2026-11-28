---
title: "comma'nızın ve fork'unuzun desteklendiğini kontrol edin"
description: "CommaView; openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot ve OPGM ile, diğer fork'larla sınırlı destekle çalışır."
topic: start
order: 2
kind: reference
lede: "CommaView, comma'nızın yol kamerasını çalıştırdığı yazılımın sürüş katmanıyla gösterir. comma 3X ve comma four üzerinde openpilot ve dokuz fork'uyla, sınırlı destekle de diğer openpilot fork'larıyla çalışır. Kurulum bir şeyi değiştirmeden önce comma'nızın hangi fork'u çalıştırdığını denetler."
updated: 2026-11-27
needs:
  - title: "Bir comma 3X veya comma four"
    text: "comma 3 desteklenmiyor; fork'ların xnor-c3 gibi comma 3 sürümleri de. [comma 3 neden desteklenmiyor](/#faq-comma-3)."
  - title: "Fork'unuz, çalıştığı hâliyle"
    text: "Her zamanki gibi yüklü ve çalışıyor. CommaView çalışma ortamını yanına ekler ve nasıl sürdüğünü asla değiştirmez."
steps:
  - id: unlisted
    title: "CommaView'un listelemediği bir fork'ta kurulum önce size sorar"
    body: |
      Rehberli kurulum, comma'nızın yazılımının hangi depodan yüklendiğini denetler ve o fork için CommaView kancasını yükler. Listelemediği bir fork'ta, hiçbir şeyi değiştirmeden önce fork'u denetler.
    tabs:
      - label: "Sınırlı destek"
        body: "CommaView görünümünü ekleyebiliyorsa kurulum **CommaView bu fork'u doğrulamadı** gösterir. Fork'u deposuyla adlandırır ve neyin çizildiğini (kameralar, yol, şeritler, öndeki araç, uyarılar ve hız) ve neyin çizilmediğini (fork'un kendi düğmeleri, renkleri ve widget'ları) söyler. **Yine de yükle** o fork'a, yalnızca ona yükler. **Geri** comma seçimine döner; hiçbir şey yüklenmez."
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**Yine de yükle**, CommaView görünümünü bu fork'a sınırlı destekle ekler."
      - label: "Yalnızca video (erken erişim)"
        body: "Ekranları CommaView görünümünü alamayan FrogPilot ve KisaPilot için, Yalnızca video bayrağı olan test kullanıcıları **Bu fork'ta yalnızca video** görür: CommaView kameraları yayınlar ve sürüş verilerinden kendi görünümünü çizer, fork'ta hiçbir şeyi değiştirmez. Henüz bir comma'da denenmedi. Bayrak olmadan kurulum fork'un desteklenmediğini söyler ve hiçbir şeyi değiştirmez."
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**Yalnızca videoyu yükle**."
    note: "Denetim bir fork'u reddettiğinde kurulum “CommaView görünümünü güvenle ekleyemiyor: …” ve “comma'nızda hiçbir şey değiştirilmedi.” der."
  - id: details
    title: "Live View'un hangi fork'u çizdiğini görün"
    body: |
      Live View'da **Ayrıntılar**'ı açın. **Yazılım** satırı comma'nızın fork'unu adlandırır; CommaView'un listelemediği bir fork deposuyla adlandırılır, örneğin “crwusiz/openpilot · best effort”.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "Görüntünün altında **Ayrıntılar**."
      - text: "**Yazılım**: comma'nızın çalıştırdığı fork."
related: [setup, overlays, uninstall]
---

## Desteklenen fork'lar

| Fork | Nereden gelir | Şu sürümden beri desteklenir |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | İlk beta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | İlk beta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot, eski adıyla github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor** (xnor ve rx sürümleri) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot, i.carrotpilot.app'ten yüklenir | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

Listelemediği bir fork'ta kurulum, CommaView'un görünümünü ekleyip ekleyemeyeceğini denetler ve önce size sorar; ekleyemiyorsa kurulum durur ve comma'nızı olduğu gibi bırakır.

## Her fork ne gösterir

### openpilot

comma.ai'nin kendi yazılımı. Live View comma four'un ekranını, comma 3X'inkini veya CommaView'un kendi katmanını; hızınız, MAKS, hız sınırı, öndeki araç ve şerit değiştirmelerle çizer.

### sunnypilot

CommaView, sunnypilot'un ekranını sunnypilot'un ekledikleriyle çizer: MADS'in yalnızca direksiyon ve yalnızca hız durumları, hız sınırı yardımı, gökkuşağı yol ve kör nokta göstergeleri; comma 3X ekranında ayrıca hız sınırı tabelası, akıllı hız sabitleyici ve geliştirici arayüzü. sunnypilot ayarlarınızı okur, böylece ekran comma'nınkiyle eşleşir.

### StarPilot

StarPilot sürüş modlarını renklerle gösterir ve CommaView StarPilot'un seçtiği renkleri kullanır: comma four ve comma 3X ekranlarında çerçevesi, yolu ve widget'ları, uyarıları ve sürücü kamerası dahil kamera seçimi.

StarPilot'un **Disable Logging** ayarını kapatın. Live View'un yayın yaptığı video kodlayıcıyı durdurur.

### xnor-tech'in openpilot'u: xnor ve rx

xnor-tech'in openpilot'u iki sürümde gelir. **xnor** dalları openpilot'un ekranını, **rx** dalları sunnypilot'unkini çalıştırır; ikisi de xnor-tech'in araç desteğiyle. CommaView comma'nızın hangisini çalıştırdığını, uyarılarını comma'nın yazdığı gibi çizer.

rx çalıştıran bir Rivian'da direksiyon simgesi araç açıyla yönlendirirken yeşil, torkla yönlendirirken mavi olur: comma four'un direksiyonu ve comma 3X ekranında deneysel mod düğmesininki.

### AdventurePilot

AdventurePilot, kendi araç desteği olan bir sunnypilot fork'udur. CommaView, sunnypilot'un ekranını AdventurePilot'un ekledikleriyle çizer:

- şerit ortalama göstergesi: comma 3X ekranında itme ve kaymayı gösteren bir hap, comma four'unkinde kompakt bir çubuk;
- comma 3X ekranında, viraj hız kontrolü devredeyken yanıp sönen CURVE etiketi;
- direksiyon modunun direksiyon rengi ve bir Rivian açı kanalından yönlendirirken yanal ivmeyi gösteren bir tork çubuğu.

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1, Tesla'nın HW1 (Autopilot 1) araçlarını ekleyen bir sunnypilot fork'udur. Ekranı sunnypilot'unkidir; bu yüzden CommaView sunnypilot'un ekranını sunnypilot'un eklediği her şeyle çizer ve uygulamada fork'u adlandırır.

`op fork update` komutu, CommaView kancası yüklüyken fork'u taşıyamaz: önce [CommaView'un çalışma ortamını kaldırın](/tr/guides/uninstall) veya comma'nın ekranındaki, her zamanki gibi çalışan fork değiştiriciyi kullanın.

### carrotpilot

carrotpilot, Hyundai, Kia ve Genesis araçları için `i.carrotpilot.app`'ten yüklenen bir openpilot fork'udur. CommaView onun için openpilot'un ekranını; hızınız, yol, şeritler ve öndeki araçla çizer. carrotpilot'un kendi ekranına eklediği navigasyon, hız kameraları ve HUD gibi şeyler henüz çizilmiyor.

carrotpilot'un otomatik güncellemesi ve web sayfasındaki Git araçları, comma yeniden başlayana kadar CommaView kancasını kaldırır. Uygulama yeniden başlatma ister ve sonrasında Live View geri gelir.

### BluePilot, dragonpilot ve OPGM

CommaView 0.0.166'dan itibaren, onun çalışma ortamıyla listelenir. CommaView her birini adlandırır ve tabanının görünümünde çizer: BluePilot'u sunnypilot, dragonpilot ve OPGM'yi openpilot olarak; dragonpilot'un ALKA'sı direksiyon olarak gösterilir. Bunlardan birini sınırlı destekle çalıştıran bir comma, çalışma ortamı güncellemesinden sonraki açılışta listelenen hâline geçer. Hiçbiri henüz CommaView ile sürülmedi. CommaView'un resmî [katman paketleri](/tr/guides/overlays), BluePilot'un ve dragonpilot'un kendi ekranlarından daha fazlasını çizer.

## CommaView'un listelemediği fork'lar

CommaView 0.0.165'ten itibaren, comma'nızda onun çalışma ortamıyla kurulum, CommaView görünümünü listelemediği bir openpilot fork'una sınırlı destekle ekleyebilir. Live View fork'u openpilot'un görünümünde ya da fork sunnypilot'un ekranı üzerine kuruluysa sunnypilot'unkinde çizer. Geri almak için Cihaz ayarları'ndaki **Çalışma ortamını kaldır**, fork'un dosyalarını eski hâline getirir.

- **Sınırlı destek.** CommaView sürümleri fork'unuza karşı denetlenmez. Fork kendini CommaView'un izleyemeyeceği bir şeye güncellerse CommaView görünümü kapanır ve fork'unuz bir CommaView sürümü değişikliği karşılayana kadar her zamanki gibi sürer ve kendi ekranını gösterir.
- **Her fork değil.** openpilot'un eski yerel ekranı üzerine kurulu fork'lar desteklenmez (aşağıda).
- **Onayınız o fork içindir.** comma'nız CommaView'un listelemediği başka bir fork'a geçerse CommaView, görünümünü oraya eklemeden önce kurulumda yeniden sorar.

### Yükleme denetimini geçen fork'lar (sınırlı destek)

Bunların her biri **CommaView'un yükleme denetimini geçer; sınırlı destek, araçta test edilmedi.** Kasım 2026'da, adı geçen dallar için CommaView 0.0.165'in yüklediği çalışma ortamına karşı denetlendi: yükleyici fork'u önerir, siz onaylayınca CommaView görünümünü ekler ve comma'nızda yapacağı gibi denetler. Buradakilerin hiçbiri araçtaki bir comma'da denenmedi, bir fork her aracı iki cihazda da desteklemeyebilir ve bir fork'un sonraki güncellemesi sonucu değiştirebilir.

| Fork | Denetlenen dallar | Cihazlar | Çizildiği görünüm |
| --- | --- | --- | --- |
| **crwusiz** (github.com/crwusiz/openpilot) | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **jixiexiaoge'nin Carrot'u** (github.com/jixiexiaoge/openpilot) | Carrot | comma four, comma 3X | openpilot |
| **MoreTore** (github.com/MoreTore/openpilot) | release-mici | comma four | openpilot |
| **zoompilot** (github.com/zoompilot/zoompilot) | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato** (github.com/AlexandreSato/openpilot) | master | comma four, comma 3X | openpilot |
| **lukasloetkolben** (github.com/lukasloetkolben/openpilot) | master | comma four, comma 3X | openpilot |
| **mvl-boston** (github.com/mvl-boston/openpilot) | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub** (github.com/mouxangithub/openpilot) | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro** (github.com/programanichiro/openpilot) | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2** (github.com/infiniteCable2/openpilot) | master | comma four, comma 3X | sunnypilot |
| **herizon1054** (github.com/herizon1054/openpilot) | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot** (github.com/NotAutopilot/openpilot) | nap-release, naponsp-alpha | comma four, comma 3X | openpilot (nap-release), sunnypilot (naponsp-alpha) |

Fork'unuz burada değil mi? Yine de çalışabilir: kurulum bir şeyi değiştirmeden önce onu denetler.

### Desteklenmeyenler

Bu fork'ların ekranları CommaView görünümünü alamaz; bu yüzden kurulum bunu söyler ve comma'nızda hiçbir şeyi değiştirmez:

- **FrogPilot** (github.com/FrogAi/FrogPilot). openpilot'un CommaView görünümüne yer olmayan eski yerel (Qt) ekranını çalıştırır. Yalnızca video erken erişimde.
- **KisaPilot** (github.com/kisapilot/openpilot). Python ekranı kapalı: openpilot'un eski yerel (Qt) ekranını çalıştırır. Yalnızca video erken erişimde.
- **IQ.Pilot** (github.com/IQLvbs/iqpilot). Ekim 2026'dan beri kendi IQ.OS'u üzerinde çalışıyor; destek, CommaView onu ayrı bir fork olarak destekleyebilene kadar bekliyor.
- **hikee9123** (github.com/hikee9123/openpilot). openpilot'un eski yerel (Qt) ekranını çalıştırır.

**Erken erişim: FrogPilot ve KisaPilot için yalnızca video.** Yalnızca video bayrağıyla kurulum, kameralarını Live View'da kendi ekranları yerine CommaView'un katmanıyla oynatmayı önerir ve fork'ta hiçbir şeyi değiştirmez. Henüz bir comma'da denenmedi. Bayrak olmadan kurulum hâlâ desteklenmediklerini söyler ve hiçbir şeyi değiştirmez.

## Hangi comma cihazları

comma 3X ve comma four. comma 3 desteklenmiyor; fork'ların xnor-c3 gibi comma 3 sürümleri de: [comma 3 neden desteklenmiyor](/#faq-comma-3). Uygulama bir Android telefonda, tablette veya multimedya ünitesinde çalışır.

## Sürüm ve geliştirme dalları

Her sürümden önce CommaView'un çalışma ortamı bu fork'ların sürüm yapılarına karşı derlenir ve denetlenir. openpilot'un nightly ve sunnypilot'un dev dalları, erken uyarı olarak değiştikleri her gün denetlenir. Bir geliştirme dalı CommaView'dan hızlı değişebilir: bir değişiklik CommaView kancasının yüklenmesini engellerse fork'unuzun ekranı ve sürüşü her zamanki gibi devam eder.

## Fork'unuz listede değil mi?

Sınırlı destekle deneyin ve [my.commaview.com](https://my.commaview.com) adresindeki özellik panosunda listelenmesini isteyin ya da uygulamadan bir fikir gönderin (Ayarlar › **Destek ve tanılama**). Listelenen bir fork her sürümden önce denetlenir. Her sürümdeki [yeniliklere](/whats-new) bakın.

## Sorular

**CommaView fork'umun sürüşünü değiştirir mi?** Hayır. Fork'unuzun yanına küçük bir çalışma ortamı ve ekran arayüzüne küçük bir kanca ekler; böylece CommaView aynı yolu, şeritleri ve uyarıları çizebilir. Aracınızın sürüşü değişmez.

**CommaView StarPilot ile çalışır mı?** Evet, CommaView 0.0.162'den itibaren. Live View StarPilot'un kendi renklerini, widget'larını ve kamera seçimini gösterir. CommaView'un yayın yaptığı video kodlayıcıyı durduran StarPilot'un **Disable Logging** ayarını kapatın.

**CommaView carrotpilot ile çalışır mı?** Evet, CommaView 0.0.164'ten itibaren. Live View onun için openpilot'un ekranını çizer; carrotpilot'un kendi ekranına eklediği navigasyon ve hız kameraları gibi şeyler henüz çizilmiyor. carrotpilot kendini güncelledikten sonra uygulama, Live View'u geri getiren bir yeniden başlatma ister.

**CommaView FrogPilot ile çalışır mı?** Henüz değil: openpilot'un CommaView görünümüne yer olmayan eski yerel (Qt) ekranını çalıştırır; bu yüzden kurulum desteklenmediğini söyler ve hiçbir şeyi değiştirmez. FrogPilot ve KisaPilot için yalnızca video, test kullanıcılarına erken erişimde.
