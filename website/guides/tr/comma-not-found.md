---
title: "CommaView comma'nızı bulamıyor"
description: "Ana sayfa Çevrimdışı mı diyor veya Live View comma'nıza ulaşamıyor mu? Ağı, comma'nın adresini ve eşleştirmesini bu sırayla kontrol edin."
topic: troubleshooting
order: 2
kind: fixes
lede: "CommaView comma'nızla arada bulut hizmeti olmadan, doğrudan yerel ağınız üzerinden konuşur. Onu bulamadığında, neredeyse her zaman telefonunuz ve comma farklı ağlardadır, araç kapalı olduğu için comma uyuyordur ya da adresi değişmiştir. Önce bunları, sonra eşleştirmeyi kontrol edin."
parked: true
updated: 2026-11-27
needs:
  - title: "Araç açık"
    text: "Araç kapalıyken comma uyur. Aracı P konumunda çalıştırın."
  - title: "Tek bir ağ"
    text: "Telefonunuz comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda. Araçta: [araçta bağlanın](/tr/guides/connect-in-the-car)."
steps:
  - id: home
    title: "Ana sayfa'nın ne dediğine bakın"
    body: |
      Telefonunuz comma'ya ulaşamadığında Ana sayfa onu **Çevrimdışı** olarak, **Yeniden bağlan** ile ve bir **Bağlanamıyor musunuz?** kartıyla gösterir: “telefonunuz comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda olmalı. Araç kapalıyken comma uyur.”

      İkisini de kontrol edin, ardından **Yeniden bağlan**'a dokunun.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Yeniden bağlan**."
      - target: cant-connect
        text: "**Bağlanamıyor musunuz?** kartı."
  - id: live-view
    title: "Live View'da: bekleyin veya yeniden deneyin"
    body: |
      Live View neden durduğunu söyler. **Bu comma'ya ulaşılamıyor**, telefonunuzun ağda comma'ya ulaşamadığı anlamına gelir. comma yanıt verdiğinde kendiliğinden yeniden bağlanır; **Yeniden dene** hemen yeniden dener.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**Bu comma'ya ulaşılamıyor**: Live View'un neden durduğu."
      - target: retry
        text: "**Yeniden dene**."
  - id: network
    title: "Telefonunuzun ağını kontrol edin"
    body: |
      Telefonunuzun Wi‑Fi ayarlarını açın ve comma'nın bulunduğu ağa bağlı olduğunu kontrol edin: aynı ev Wi‑Fi'ı, comma'nın bağlı olduğu telefon hotspot'unuz veya comma'nın kendi hotspot'u.

      - İnternetsiz bir Wi‑Fi'dan mobil veriye geçen bir telefon comma'ya ulaşamaz. Yeniden katılın.
      - Telefonunuzdaki bir VPN trafiği başka yere gönderebilir. Kapatıp yeniden deneyin.
      - Bazı hotspot'lar bağlı cihazların birbirine ulaşmasını engeller. comma'nın kendi hotspot'u gibi başka bir ağ deneyin.
    note: "Android'in Wi‑Fi ve hotspot ayarları gösterilmiyor: her telefonda farklı görünürler."
  - id: address
    title: "comma'nın adresini kontrol edin"
    body: |
      comma başka bir ağa katıldığında veya yönlendirici ona yeni bir adres verdiğinde yeni bir adres alır. CommaView onu ağda gördüğünde kendiliğinden yeniden bulur; bulamazsa adresini kendiniz kaydedin.

      comma'da IP adresini **Ayarlar → Ağ** altında bulun. CommaView'da Ana sayfa'dan **Cihaz ayarları**'nı açın, **Adı veya adresi değiştirin**'e dokunun, ardından **IP adresi**'ni düzenleyin, comma'nın adresini yazın ve **Kaydet**'e dokunun.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "comma'nın IP adresi."
      - target: save
        text: "**Kaydet**."
  - id: add
    title: "Hâlâ bulunamadı mı? Yeniden ekleyin"
    body: |
      Ana sayfa'da **comma ekle**'ye dokunun. **Bu ağda**, telefonunuzun ağında CommaView çalıştıran comma'ları listeler: kendinizinkine dokunun. Orada değilse **Adres ve kod girin**'e veya onunla zaten eşleştirilmiş bir telefonda **QR kodunu tara**'ya dokunun.
    screen: add-comma
    pins:
      - target: found-comma
        text: "**Bu ağda**: yakında bulunan bir comma."
      - target: enter-address
        text: "**Adres ve kod girin**."
      - target: scan-qr
        text: "**QR kodunu tara**."
  - id: pair
    title: "Adresi ve yeni bir kodla eşleştirin"
    body: |
      comma'nın IP'sini ve bir eşleştirme kodu ya da davet yazın, ardından **comma eşleştir**'e dokunun. Kodların süresi çabuk dolar: comma ile zaten eşleştirilmiş bir telefon **Cihaz ayarları**'nda, **Başka bir telefon veya tablet eşleştir** altında yenisini gösterir.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "comma'nın IP'si."
      - target: pair-code
        text: "**Eşleştirme kodu veya davet**."
      - target: pair
        text: "**comma eşleştir**."
    note: "Adresini yazmak işe yarıyor ama comma hiç kendiliğinden görünmüyorsa, ağ CommaView'un bulma özelliğini gizliyordur. Sorun değil: önemli olan adrestir."
check: "Ana sayfa comma'nızı **Bağlı** gösterir ve **Live View'u aç** görüntüyü açar."
fixes:
  - q: "“Bu comma'ya ulaşılamıyor”"
    a: "Telefonunuz comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda olmalı. comma yanıt verdiğinde Live View yeniden bağlanır. Ağı ([3. adım](#step-network)) ve comma'nın adresini ([4. adım](#step-address)) kontrol edin."
  - q: "“CommaView yanıt vermiyor”"
    a: "comma yanıt veriyor ama üzerindeki CommaView vermiyor. comma'da yeniden başlıyor olabilir: geri geldiğinde Live View yeniden bağlanır. Devam ederse comma'yı park hâlinde yeniden başlatın."
  - q: "“Bu comma'dan video yok”"
    a: "Yanıt veriyor ama videosu gelmedi. Yeniden deneyin veya geri dönüp comma'yı kontrol edin: openpilot hâlâ başlıyor olabilir."
  - q: "“Live View başka bir cihazda açık”"
    a: "Bu comma aynı anda tek bir telefona veya multimedya ünitesine yayın yapar. Diğerinde CommaView'da Ana sayfa'ya dönün; Live View burada kendiliğinden başlar."
  - q: "“comma zamanında yanıt vermedi.”"
    a: "Zayıf veya yoğun bir bağlantı. Telefonunuzun comma'nın Wi‑Fi'ında veya hotspot'unda olduğunu kontrol edin, mümkünse yaklaşın, ardından yeniden deneyin."
  - q: "“comma bağlantıyı reddetti. CommaView üzerinde yeniden başlıyor olabilir.”"
    a: "Geri gelmesi için biraz bekleyin, ardından yeniden deneyin."
  - q: "“Araç verileri gelmiyor”"
    a: "Video geliyor ama aracın hızı, sinyalleri ve uyarıları gelmiyor. Düzeltmek için comma'yı yeniden başlatın."
  - q: "“Eşleştirme başarısız: eşleştirme kodunun süresi doldu. Yeni bir kod oluşturup yeniden deneyin.”"
    a: "comma ile zaten eşleştirilmiş bir telefondan **Cihaz ayarları › Başka bir telefon veya tablet eşleştir** altında yeni bir kod alın ve yeniden eşleştirin."
  - q: "“Eşleştirme başarısız: geçersiz eşleştirme kodu. Kodu kontrol edin veya QR'ı tarayın.”"
    a: "Yazdığınız kodu kontrol edin (kısa çizgiler isteğe bağlıdır) veya bunun yerine QR kodunu tarayın."
  - q: "“Bu comma'nın çalışma ortamını güncelleyin” veya “CommaView'u güncelleyin”"
    a: "Bu uygulama ile comma'nın çalışma ortamı birbiriyle konuşamayacak kadar farklı. Hangisini söylüyorsa onu güncelleyin: çalışma ortamını Cihaz ayarları'ndan ([Çalışma ortamını güncelleyin](/tr/guides/update-runtime)) ya da uygulamayı."
  - q: "“Kayıtlı comma'larınız okunamıyor”"
    a: "Bu telefonda kayıtlı comma'lar okunamadı, bu yüzden hiçbiri gösterilmiyor. Silinmediler. Yeniden deneyin veya **Baştan başla** ile her comma'yı yeniden eşleştirin: eski liste en az 90 gün saklanır."
related: [connect-in-the-car, setup-troubleshooting, another-phone]
---

## CommaView bir comma'yı nasıl bulur

- **Bulma**, telefonunuzun ağında CommaView çalıştıran comma'ları bulur; böylece adres yazmazsınız. Bazı ağlar bunu engeller.
- **Adres**, CommaView'un bağlandığı şeydir. Adresi yazmak, bulma çalışsa da çalışmasa da işe yarar.
- **Eşleştirme**, kısa ömürlü bir kodla telefonunuza comma için kendi anahtarını verir. Bulma ve eşleştirme ayrıdır: telefonunuzun ulaşabildiği bir comma'nın yine de eşleştirilmesi gerekir.
- **Kayıtlı bir comma** yalnızca adresiyle değil kimliğiyle tanınır; bu yüzden yeni bir adreste göründüğünde CommaView kayıtlı adresi günceller.

## Güvenlik

Ağları kontrol etmeyi ve eşleştirmeyi park hâlinde yapın. Sürerken CommaView'da dokunarak gezinmeyin.
