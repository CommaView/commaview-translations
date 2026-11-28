---
title: "CommaView 0.0.166: her telefona bir anahtar, 11 dil daha ve Browser View"
description: "CommaView 0.0.166 her telefona bir anahtar veriyor, 11 dil daha konuşuyor, Live View'u aracınızın tarayıcısında gösteriyor, sürüşleri telefonda tutuyor ve paket mağazasını açıyor."
date: 2026-11-16
slug: commaview-0-0-166-languages-browser-view
tags:
  - security
  - languages
  - browser view
  - recordings
  - overlay packs
heroLabel: "Sürüm notları"
draft: false
---

CommaView 0.0.166 Beta'daki herkes için yayında. Yeni çalışma ortamıyla **her telefon comma'nız için kendine ait bir anahtar alıyor** ve kimse yeniden eşleştirme yapmıyor. CommaView **11 dil daha** konuşuyor, **Browser View** ile Live View'u aracınızın web tarayıcısında gösteriyor, **Bu anı kaydet**, **Tüm sürüşü dışa aktar…** ve **Sürüşleri otomatik çek** ile sürüşlerinizi telefonunuzda tutuyor ve **katman paketleri mağazasını** açıyor.

`v0.0.62-beta` çalışma ortamıyla geliyor. **Önce CommaView'u güncelleyin**, sonra uygulama sunduğunda çalışma ortamını uygulamadan güncelleyin ve uygulama istediğinde comma'yı yeniden başlatın. Hâlâ 0.0.165'te olan bir telefon, comma'nızın ilk telefonu anahtarını aldıktan sonra 90 gün çalışmaya devam eder. comma'nızı 0.0.165'teki bir telefondan yeniden kurmayın: oradan yapılan kurulum eski çalışma ortamını geri getirir ve anahtarı olan telefonlar o çalışma ortamındaki comma'ya ulaşamaz.

## Her telefona bir anahtar

Yeni çalışma ortamıyla her telefon, eskiden her telefonun gönderdiği paylaşılan belirtecin yerine comma'nız için kendine ait bir anahtar alır. Anahtar asla ağ üzerinden geçmez ve kimse yeniden eşleştirme yapmaz: 0.0.166'daki bir telefon anahtarını bir sonraki bağlanışında alır.

- **Yeni bir telefon anahtar aldı.** Anahtarı olan her telefona başka biri anahtar aldığında haber verilir; **Benim**, **Kaldır** ve **Telefonları incele** seçenekleriyle. Sonuncusu, anahtarı olan her telefonun listelendiği Cihaz ayarları › Başka bir telefon eşleştir'i açar.
- **Telefon eklemek.** Anahtarı olan bir telefonda **Davet göster**, 10 dakika geçerli bir kod veya QR kodu verir.
- **Eski uygulamalar.** comma'nız, ilk telefonu anahtar aldıktan sonra 90 gün boyunca ya da biri **Şimdi durdur**'a dokunana kadar eski paylaşılan belirteci kabul eder. O zamana kadar **Eski bir uygulama için eşleştirme kodu**, eski bir CommaView kullanan telefonu eşleştirir. Sonrasında anahtarı olmayan bir telefonun 0.0.166'ya ve bir davete ihtiyacı olur.

## CommaView sizin dilinizde

Ayarlar › **Dil** artık İngilizcenin yanında Deutsch, Español, Français, 日本語, 한국어, Português (Brasil), ไทย, Türkçe, Українська, 简体中文 ve 繁體中文 seçeneklerini sunuyor. Varsayılan olan **Telefonun dili**, telefonunuzun dil listesinde CommaView'un sahip olduğu ilk dili, yoksa İngilizceyi kullanır; satır hangisini kullandığını söyler. Android 13 ve sonrasında Android'in uygulama başına dil ayarı da çalışır.

İngilizce dışındaki her dil **makine çevirisi** ve henüz hiçbirini anadili olan biri gözden geçirmedi; yanlış kelimeler ve tuhaf cümleler bekleyin. Ayarlar'ın üstündeki bir kart bunu söyler; **Geliştirmeye yardım edin** de herkesin daha iyi bir kelime önerebileceği CommaView çevirilerini açar. Bize [Discord](https://discord.gg/UuMhz9K8ft)'tan veya **Sorun bildirin veya fikir gönderin**'den de söyleyebilirsiniz: ekranı ve şu anda ne yazdığını belirtin.

- **comma'nızın ekranları comma'nızın dilinde kalır.** Bir fork'un etiketleri ve comma'nızın uyarıları aracınızın gösterdiği gibi çizilir; comma'nız Çince, Japonca, Korece veya Tayca olduğunda artık fork'un kendi yazı tipiyle.
- Sıralamanın onayı için **İngilizce metin geçerlidir**; **İngilizce göster** onu gösterir. Gizlilik politikası ve şartlar İngilizcedir.
- **Tarihler** dilinizin sırasını izler; Yayına başla'nın YouTube başlığı ve açıklaması, siz değiştirene kadar uygulamanın dilindedir.
- **Korece** satır sonunda kelimeleri bölmez. Android 13 ve öncesinde, bir comma'ya veya yere verdiğiniz Korece bir ad yine de bölünebilir.

## Browser View

Browser View, Live View'un gösterdiğini aracınızın web tarayıcısında gösterir; görüntüyü telefonunuz hotspot'u veya Wi‑Fi üzerinden sunar. Live View › Ayrıntılar › Browser View'dan başlatın, kısa bağlantıyı (`commaview.app/<code>`) aracın tarayıcısına yazın ve **Aç**'a dokunun. Bir Tesla'da önce **VPN adresini aç**'a dokunun.

Görüntü telefonunuzdan araca gider, asla internet üzerinden değil; yalnızca kısa bağlantının sayfası internetten gelir. Giriş yapmışsanız telefonunuz kendine ait bir ad ve güvenilir bir sertifika alır; böylece Tesla bir asma kilit ve daha akıcı H.264 görüntüyü gösterir. Giriş yapmamışsanız Tesla Temel görüntüyü alır.

- **Araçtaki denetimler**: Kayıt, Kaydet, Harita, sürüş ekranı, Yayına başla ve Sürücü kamerası; görüntünün yanında veya altında, asla üstünde değil.
- **Araçta internet yok mu?** **Adresleri göster** telefonun kendi adreslerini listeler.
- 720p veya 1080p, sekiz haneli kodlar ve Live View her açıldığında başlatmak için **Live View ile başlat**.

Bir Tesla'nınki dahil her adım: [Browser View](/tr/guides/browser-view).

Çalışırken telefonunuz, kısa bağlantının onu bulabilmesi için CommaView'un hesap hizmetine kodunu, portlarını ve özel adresini gönderir. Kodu bilen herkes, Browser View çalışırken ve beklenmedik şekilde durduktan sonra en fazla 2 saat boyunca bunları ve telefonunuzun `commaview.app` adını görebilir; ama hiçbiri telefonunuzun hotspot'u veya Wi‑Fi'ı olmadan bir şey açmaz. Browser View'un son çalışmasından 30 gün sonra silinirler. Telefonunuzun `commaview.app` adı ve son sertifikasının tarihi hesabınız durdukça kalır; ad, herkese açık sertifika kayıtlarında yer alır. Ayrıntılar [gizlilik politikasında](/privacy).

## Sürüşleriniz telefonunuzda

- **Bu anı kaydet.** Live View'un **Kaydet** düğmesi bir sürüşün son 3 dakikasını ve sonraki dakikasını saklar; o dakika içinde bir dokunuş daha bir dakika ekler, en fazla 10 dakikaya kadar. Sürerken hiçbir şey indirilmez: park ettiğinizde telefonunuzda bir MP4'e kopyalanır.
- **Tüm sürüşü dışa aktar…** Bir sürüşün Daha fazla menüsünde: yol kamerası tek bir MP4 olarak, 3,5 GB'ı aşınca parçalar hâlinde. Sayfa, bir şey indirilmeden önce ne kadar büyük olduğunu ve sığıp sığmadığını söyler.
- **Sürüşleri otomatik çek.** Ayarlar › Kayıtlar: yeni sürüşler, seçtiğiniz Wi‑Fi ağlarında yaklaşık yarım saatte bir, yalnızca Wi‑Fi üzerinden, onlara ayırdığınız alana kadar telefona kopyalanır. Bir saatlik sürüş yaklaşık 4,5 GB'tır.
- **Elektrik mi kesildi?** Kayıtlar, bir sürüş biterken comma'nızın elektriği kesildiğinde uyarır ve nasıl düzeltileceğini söyler.

Hepsi HUD'suz yol kamerasıdır ve comma'nız sürüşü sildikten sonra da telefonunuzda kalır.

## Katman paketleri

Ayarlar › **Katman paketleri** ya da Ana sayfadaki kart mağazayı açar. Paketler, fork'unuzun kendi ekranında çizdiklerini Live View'a ekler; BluePilot'un hibrit göstergeleri veya dragonpilot'un gökkuşağı yol çizgisi gibi. Üyeler CommaView'un **Resmî** paketlerine, **Topluluk** paketlerine ve **comma'nız için** olanlara göz atar; her birinde Live View'un çizdiği tasarım için bir önizleme vardır. **Paketleriniz**'de telefonunuz ve eşleşmiş her comma için tek bir anahtar vardır. Üyeliğiniz yoksa bir dosyadan veya bağlantıdan paket ekleyebilirsiniz.

## 0.0.166'da ayrıca

- Üyeler için **kendi Stadia Maps anahtarınızla navigasyon**: Ayarlar › Haritalar ve navigasyon › Stadia Maps anahtarınız.
- **BluePilot, dragonpilot ve OPGM**, yeni çalışma ortamıyla listelenen fork'lar. Henüz hiçbiri CommaView ile sürülmedi.
- **Daha fazla multimedya ünitesinde Live View**: telefonun video kod çözücüsü comma'nın videosunu oynatamadığında bir başkasını dener.
- Ayarlar › Ekran'da bir multimedya ünitesi açıldığında veya Bluetooth bağlandığında **CommaView'u kendiliğinden açma** ve **Bağlanınca Live View'u aç**. CommaView'u aracınızın kendi ekranında çalıştırmak için: [en iyi Android AI box'lar](/tr/blog/android-ai-box-commaview).
- **Fork'umun geliştiricisiyle paylaş**: kendiniz paylaşmanız için bir klip, bir özet ve CommaView'un günlüğü.
- **Live View neler olduğunu söylüyor**: beklediği bir yeniden başlatma, duran araç verisi, gecikmeli bir görüntü, neden yeniden bağlandığı, onu açık tutan başka bir cihaz.
- Üyeler için 0.0.166'dan itibaren **CommaView'u güncelleme**: önce sürüm, **İndirmeyi iptal et** ve indirme arka planda devam eder.
- **Ekran kenarları**, her platform için ayrı yayın hedefleri ve büyük metinde kesilen hiçbir şey.

## Erken erişim

X, Twitch, Kick ve Facebook'a canlı yayın, FrogPilot ve KisaPilot için Yalnızca video, fork ayarları, katman paketi oluşturma ve Surround, sınırlı bir test grubu için özellik bayraklarının arkasında kalıyor. Test etmeye yardım etmek isterseniz [Discord](https://discord.gg/UuMhz9K8ft) sunucumuzdan bize ulaşın ve sürüşlerinizde nasıl çalıştıklarını anlatmaya hazır olun.

## Nasıl güncellenir

CommaView yalnızca davetle katılınan bir Beta'da. Davetliyseniz uygulama 0.0.166'yı kendisi sunar. CommaView'u, sonra comma'nızın çalışma ortamını uygulamadan güncelleyin ve istendiğinde comma'yı yeniden başlatın. comma'nızı izleyen her telefonu ve multimedya ünitesini, ilki anahtarını aldıktan sonraki 90 gün içinde güncelleyin.

## Daha fazlası

- [Hangi openpilot fork'ları CommaView ile çalışıyor](/tr/forks)
- Her sürümde [Yenilikler](/tr/whats-new)
- [CommaView sürümleri nasıl çıkıyor](/tr/guides/releases)

CommaView resmî değildir; comma.ai, BluePilot, dragonpilot, OPGM veya adı geçen diğer fork'larla bağlantılı değildir. Beta yazılımıdır ve bir güvenlik sistemi değildir: dikkatinizi asla sürüşten dağıtmasına izin vermeyin.
