---
title: "Araçta ev Wi‑Fi'ı olmadan bağlanın"
description: "Araçta telefonunuzu ve comma'yı tek bir ağa alın: telefonunuzun, comma'nın veya bir araç ekranının hotspot'u; CommaView comma'ya ulaşamadığında ne yapmalı."
topic: start
order: 3
kind: walkthrough
lede: "Live View, internet üzerinden değil, yerel bir ağ üzerinden doğrudan comma'dan telefonunuza gelir. CommaView ağın kime ait olduğuna bakmaz: telefonunuzun ve comma'nın aynı ağda olması yeterlidir. Araçta bu genellikle bir hotspot'tur."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView kurulmuş"
    text: "comma'nız bu telefonla eşleştirilmiş. Henüz değil mi? [CommaView'u kurun](/tr/guides/setup)."
  - title: "VPN yok"
    text: "CommaView'u kullanırken telefondaki veya araç ekranındaki VPN'i kapatın."
howItWorks:
  - title: "comma'nız"
    text: "Live View'u ve kayıtları bulunduğu ağda sunar."
    edge: "tek bir hotspot"
  - title: "Telefonunuz"
    text: "O ağda comma'yı kendiliğinden bulur, adresi değişse bile."
steps:
  - id: network
    title: "Telefonu ve comma'yı tek bir ağa alın"
    body: |
      Aracınıza uyanı seçin: araçla birlikte kendiliğinden açılan genellikle en zahmetsizidir. comma'yı bir ağa comma'nın kendi ekranında, **Ayarlar › Ağ** altında bağlarsınız.
    tabs:
      - label: "Telefonunuzun hotspot'u"
        body: "Telefonunuzun hotspot'unu açın ve comma'yı ona bağlayın. Aynı telefondaki CommaView comma'ya bunun üzerinden ulaşır ve comma da interneti buradan alır."
      - label: "comma'nın hotspot'u"
        body: "comma'nın hotspot'unu açın (openpilot buna tethering der: comma four'da **Ayarlar › Ağ › tethering'i etkinleştir**; comma 3X'te **Ayarlar › Ağ › Gelişmiş › Tethering'i etkinleştir**) ve telefonunuzun Wi‑Fi ayarlarından ona katılın. comma'nın hotspot'u internet vermez."
      - label: "Bir araç ekranının hotspot'u"
        body: "Bir AI box veya multimedya ünitesi hotspot paylaşabiliyorsa (SIM kartlı pek çoğu yapabilir), açın ve comma'yı, kullanıyorsanız telefonunuzu da ona bağlayın. [Araç ekranları](/tr/guides/car-screens) daha fazlasını anlatır."
    note: "Bazı hotspot'lar bağlı cihazları birbirinden ayırır. CommaView birinde comma'yı bulamazsa başkasını deneyin."
  - id: home
    title: "CommaView'u açın"
    body: |
      comma yeni ağda yanıt verdiğinde Ana sayfa onu **Bağlı** olarak gösterir: CommaView onu kendiliğinden, yeni bir adreste bile bulur. Araç kapalıyken comma uyur, bu yüzden önce aracı çalıştırın.

      Ana sayfa comma'yı **Bağlanamıyor musunuz?** ile çevrimdışı gösteriyorsa telefonun comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda olduğunu kontrol edin, ardından **Yeniden bağlan**'a dokunun.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Yeniden bağlan**, comma'yı yeniden dener."
      - target: cant-connect
        text: "**Bağlanamıyor musunuz?** telefonun neye ihtiyacı olduğunu söyler: comma ile aynı Wi‑Fi veya comma'nın hotspot'u."
  - id: address
    title: "Hâlâ bulunamıyorsa adresini girin"
    body: |
      comma'nın **Cihaz ayarları**'nı, ardından **Ad ve adres**'i açın ve IP adresini düzenleyin. comma'nın kendi hotspot'unda bu **192.168.43.1**'dir (her comma'da aynıdır). Başka herhangi bir ağda, comma'nın **Ayarlar › Ağ** altında gösterdiği adrestir: comma four'da Wi‑Fi düğmesindeki ağ adının altında, comma 3X'te **Gelişmiş** altında. **Kaydet**'e dokunun.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "comma'nın bu ağdaki IP adresi."
      - target: save
        text: "**Kaydet**."
  - id: live-view
    title: "Live View'u açın"
    body: |
      Ana sayfa'da **Live View'u aç**'a dokunun. Telefon comma'yı kaybederse Live View nedenini söyler ve comma yanıt verdiğinde kendiliğinden yeniden bağlanır. **Bu comma'ya ulaşılamıyor**, telefonun comma'nın ağında olmadığı anlamına gelir: bunu düzeltin, ardından **Yeniden dene**'ye dokunun.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**Bu comma'ya ulaşılamıyor**: Live View'un neden durduğu."
      - target: retry
        text: "Telefon comma'nın ağına döndüğünde **Yeniden dene**."
check: "Ana sayfa comma'nızı **Bağlı** gösterir ve Live View yolu, üzerine çizilmiş yolla oynatır."
fixes:
  - q: "“Bu comma'ya ulaşılamıyor”"
    a: "Telefon comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda olmalı. Telefonun hangi ağa katıldığını kontrol edin (bildiği bir Wi‑Fi'a geri dönmüş olabilir), VPN'i kapatın ve **Yeniden dene**'ye dokunun."
  - q: "“Live View başka bir cihazda açık”"
    a: "Bu comma aynı anda tek bir telefona veya multimedya ünitesine yayın yapar. Diğerinde CommaView'da Ana sayfa'ya dönün; Live View burada kendiliğinden başlar."
  - q: "“CommaView yanıt vermiyor”"
    a: "comma'da yeniden başlıyor olabilir. Geri geldiğinde Live View yeniden bağlanır."
  - q: "CommaView yenilemek için internete ihtiyaç duyduğunu söylüyor"
    a: "Beta süresince CommaView erişim hakkını ara sıra yeniler ve comma'nın hotspot'u internet sayılmaz. Telefona bir süreliğine mobil veri veya internetli bir Wi‑Fi verin."
  - q: "Bir hotspot'ta çalıştı, diğerinde çalışmadı"
    a: "Bazı hotspot'lar bağlı cihazları birbirinden ayırır, bu yüzden telefon comma'yı göremez. 1. adımdaki diğer ağlardan birini deneyin."
related: [comma-not-found, car-screens, browser-view, setup-troubleshooting]
---

## Bulma, eşleştirme ve adres

Üç ayrı şeyin çalışması gerekir; hangisinin başarısız olduğunu bilmek neyi düzelteceğinizi söyler:

- **comma'yı bulma.** CommaView comma'nızı telefonun bulunduğu ağda arar ve aynı comma'yı yeni bir yerde bulduğunda kayıtlı adresi günceller. Bazı ağlar bu aramayı engeller; adresi girmek (3. adım) bunu aşar.
- **Ona ulaşma.** Telefonun o ağda comma'ya ulaşması gerekir. comma'ya SSH ile bağlanabilen bir dizüstü bilgisayar, telefonun da ulaşabildiğini kanıtlamaz.
- **Eşleştirme.** Ulaşıldıktan sonra telefon, eşleştirirken aldığı anahtarı kullanır. Ağ değiştirmek eşleştirmeyi bozmaz: yeniden eşleştirmezsiniz.
