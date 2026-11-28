---
title: "Başka bir telefon veya tablet ekleyin"
description: "Başka bir telefona, tablete veya araç ekranına 10 dakikalık bir davetle comma'nız için kendi anahtarını verin; anahtarı olan telefonları görün ve kaldırın."
topic: start
order: 4
kind: walkthrough
lede: "comma'nızı izleyen her telefonun kendi anahtarı vardır. Başka bir telefon, tablet veya araç ekranı eklemek için comma'nız zaten kayıtlı olan bir telefonda bir davet gösterin ve yenisinde yazın ya da tarayın. SSH yok, yeniden kurulum yok."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Anahtarı olan bir telefon"
    text: "comma'nızla zaten eşleştirilmiş, CommaView 0.0.166 veya üstü ve onun çalışma ortamıyla bir telefon. Henüz yok mu? [CommaView'u kurun](/tr/guides/setup)."
  - title: "Yeni cihazda CommaView"
    text: "Yüklenmiş ve giriş yapılmış, 0.0.166 veya üstü. [Uygulamayı edinin](/tr/guides/setup#step-get-the-app)."
  - title: "Aynı ağ"
    text: "İkisi de comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda."
howItWorks:
  - title: "Telefonunuz"
    text: "comma'dan bir davet ister: 10 dakika geçerli bir kod veya QR kodu."
  - title: "Yeni telefon"
    text: "Davetle katılır ve kendi anahtarını alır."
    edge: "yerel ağ"
  - title: "comma'nız"
    text: "Anahtarı olan her telefona yeni birinin anahtar aldığını bildirir."
steps:
  - id: device-settings
    title: "Telefonunuzda Başka bir telefon eşleştir'i açın"
    body: |
      comma'nız zaten kayıtlı olan telefonda Ana sayfa'dan comma'nın **Cihaz ayarları**'nı, ardından **Başka bir telefon eşleştir**'i açın.
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**Başka bir telefon eşleştir**: başka bir telefonun veya tabletin bağlanabilmesi için kısa ömürlü bir kod."
  - id: show-invitation
    title: "Bir davet gösterin"
    body: |
      **Anahtarı olan telefonlar** altında **Başka bir telefon ekle**, bu comma'ya henüz sahip olmayan bir telefon için davet gösterir. **Davet göster**'e dokunun.
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**Davet göster**."
      - text: "Bu comma için anahtarı olan telefonlar, önce bu telefon."
  - id: invitation
    title: "Daveti ekranda tutun"
    body: |
      **Başka bir telefon ekle**, üç gruplu bir kod, bir QR kodu ve comma'nın IP adresini gösterir. 10 dakika geçerlidir ve bir kez kullanılır. Süresi dolunca yenisini gösterin.
    screen: invitation-dialog
    pins:
      - target: code
        text: "Yeni telefona yazılacak kod."
      - target: qr
        text: "Ya da taranacak QR kodu."
      - text: "**Kalan süre: …**: gösterildiği andan itibaren 10 dakika."
  - id: add-comma
    title: "Yeni telefonda comma'yı ekleyin"
    body: |
      Yeni telefonda **comma'nızı bağlayın** ekranında **CommaView çalıştıran bir comma eşleştirin**'e dokunun. Telefonda zaten bir comma varsa bunun yerine Ana sayfa'da **comma ekle**'ye dokunun.

      comma'nız **Bu ağda** altında görünür. Ona dokunun veya **QR kodunu tara**'ya dokunup daveti tarayın. Listede yoksa **Adres ve kod girin**'e dokunun.
    screen: add-comma
    pins:
      - target: found-comma
        text: "Bu ağda bulunan comma'nız."
      - target: scan-qr
        text: "Daveti taramak için **QR kodunu tara**."
      - target: enter-address
        text: "Listede yoksa **Adres ve kod girin**."
  - id: pair
    title: "Daveti yazın ve eşleştirin"
    body: |
      **comma IP**'yi kontrol edin, daveti **Eşleştirme kodu veya davet** alanına yazın (veya taramak için QR düğmesine dokunun) ve **comma eşleştir**'e dokunun. Yeni telefon kendi anahtarını alır ve comma'nızı Ana sayfa'da gösterir.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**comma IP**, bulunan bir comma için doldurulmuş."
      - target: pair-code
        text: "**Eşleştirme kodu veya davet**."
      - target: scan-qr
        text: "**Eşleştirme QR'ını tara**."
      - target: pair
        text: "**comma eşleştir**."
  - id: new-key
    title: "Diğer telefonlarınızda onaylayın"
    body: |
      Anahtarı olan her telefona bildirilir: **Yeni bir telefonun anahtarı var**, adıyla ve zamanıyla. **Benim**'e dokunun. Sizin değilse **Kaldır**'a dokunun; **Telefonları incele**, anahtarı olan her telefonun listelendiği **Başka bir telefon eşleştir**'i açar.
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "Kendi telefonunuz veya tabletiniz için **Benim**."
      - target: review
        text: "**Telefonları incele**, anahtarı olan her telefonu listeler."
check: "Yeni telefon comma'nızı Ana sayfa'da gösterir ve Live View'u açar. İlk telefonunuzda **Başka bir telefon eşleştir** onu **Anahtarı olan telefonlar** altında listeler."
fixes:
  - q: "“Bu davetle katılınamadı”"
    a: "Yanlış yazılmış, süresi dolmuş veya kullanılmış olabilir. Bu comma'ya zaten sahip olan telefonda yenisini gösterin (Cihaz ayarları, **Başka bir telefon eşleştir**, **Başka bir telefon ekle**)."
  - q: "“Bu comma'nın çalışma ortamı telefon anahtarlarından önceki bir sürüm”"
    a: "Önce comma'nın çalışma ortamını güncelleyin: [comma'nızın çalışma ortamını güncelleyin](/tr/guides/update-runtime). Ardından daveti gösterin."
  - q: "“Bu comma'ya ulaşılamıyor”"
    a: "İki telefon da comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda olmalı. [Araçta bağlanın](/tr/guides/connect-in-the-car)."
  - q: "“Eşleştirme başarısız: bu comma artık kodla eşleşmiyor”"
    a: "comma eski paylaşılan belirteci kabul etmeyi bıraktı. Telefonu zaten anahtarı olan bir telefondan ekleyin (ayarları, **Başka bir telefon ekle**) veya comma'nın kurulumunu yeniden çalıştırın."
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## Bir telefonu kaldırın

Anahtarı olan bir telefonda comma'nın **Cihaz ayarları**'nı, ardından **Başka bir telefon eşleştir**'i açın. Listedeki bir telefonun yanındaki **Kaldır**'a dokunun. O telefon, bir davetle veya comma yeniden kurularak tekrar eklenene kadar bu comma'ya bir daha ulaşamaz.

## Eski bir CommaView kullanan telefonlar

0.0.166'dan önce her telefon comma'ya aynı paylaşılan belirteci gönderiyordu. 0.0.166 kullanan bir telefon, bir sonraki bağlanışında yeniden eşleştirme olmadan anahtarını alır.

- **Başka bir telefon eşleştir**'deki **Eski CommaView uygulamaları**, eski bir CommaView kullanan bir telefonun paylaşılan belirteçle bu comma'yı kaç gün daha kullanabileceğini söyler: ilk telefonu anahtar aldıktan sonra 90 gün. O zamana kadar **Eski bir uygulama için eşleştirme kodu**, eski bir CommaView kullanan bir telefonu eşleştirir.
- **Şimdi durdur**, onu kullanan her telefonun anahtarı olduğunda comma'nın paylaşılan belirteci kabul etmesini durdurur. Eski bir CommaView kullanan telefonlar bundan sonra bu comma ile çalışmaz ve güncellenene kadar yeniden eşleştirilemez.
- Bundan sonra anahtarı olmayan bir telefon CommaView 0.0.166 veya üstüne ve bir davete ihtiyaç duyar.

comma'nızın çalışma ortamını güncellediğinizde, önce onu izleyen her cihazda, araç ekranları dahil, CommaView'u güncelleyin.
