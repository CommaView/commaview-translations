---
title: "CommaView sürümleri nasıl çıkar"
description: "CommaView uygulaması ve comma'nızdaki çalışma ortamı nasıl yayımlanır: alfalar, ardından bir beta, imzalı indirmeler, eşleşen çalışma ortamları ve P konumunu bekleyen güncellemeler."
topic: account
order: 2
kind: reference
lede: "CommaView'un birlikte güncellenen iki parçası vardır: Android uygulaması ve comma'nızdaki küçük çalışma ortamı. Bir sürümün size nasıl ulaştığı ve güncellemelerin nasıl güvenli kaldığı burada."
updated: 2026-11-27
steps:
  - id: version
    title: "Hangi sürümde olduğunuzu görün"
    body: |
      Ayarlar › **Hakkında**, uygulamanın sürümünü ve **Güncel** olup olmadığını ya da sürümüyle birlikte bir güncellemenin mevcut olduğunu gösterir. CommaView yeni bir sürüm için hesabınızı denetler ve biri hazır olduğunda size söyler.
    screen: support-about
    pins:
      - target: version
        text: "Uygulamanın sürümü."
      - target: up-to-date
        text: "**Güncel** veya sizin için hazır olan sürüm."
  - id: app-update
    title: "Uygulamayı kendi içinden güncelleyin"
    body: |
      Bir sürüm hazır olduğunda **Güncelle**, Ana sayfa'nın üstünde ve **Hakkında**'da görünür. **CommaView'u güncelle** sürümü ve kanalını adlandırır: davet edilen herkes için **Beta** veya **Alfa**, “Test edenler için erken bir sürüm. Betadan daha fazla sorunu olabilir.” **İndir**'e dokunun: CommaView onu arka planda indirir, denetler, ardından Android yüklemeyi onaylamanızı ister.
    screen: app-update-offer
    pins:
      - target: channel
        text: "Kanal: **Beta** veya **Alfa**."
      - target: download
        text: "**İndir**. **Şimdi değil** sonraya bırakır."
  - id: runtime
    title: "Ardından comma'nızın çalışma ortamını güncelleyin"
    body: |
      Her uygulama sürümü birlikte test edildiği çalışma ortamını adlandırır. Uygulama güncellendikten sonra Ana sayfa o çalışma ortamını **Çalışma ortamı güncellemesi hazır** ile sunar. Çalışma ortamı güncellemeleri kendiliğinden değil, uygulamadan başlar. [comma'nızın çalışma ortamını güncelleyin](/tr/guides/update-runtime) her adımı içerir.
    screen: home-runtime-update
    pins:
      - target: update-card
        text: "**Çalışma ortamı güncellemesi**: yüklü ve mevcut çalışma ortamı."
related: [update-runtime, uninstall, setup]
---

## Önce alfa, sonra beta

- Her sürüm önce birkaç test kullanıcısına bir dizi alfa olarak yayımlanır.
- Bir alfa sağlam kalınca o sürümün betası olur ve davet edilen herkese gider.
- [my.commaview.com](https://my.commaview.com) adresindeki hesabınız her zaman size uygun sürümü sunar.

## İmzalı ve eşleşen

- Her uygulama indirmesi imzalı bir sürüm yapısıdır, asla bir hata ayıklama yapısı değil; SHA-256 sağlama toplamı my.commaview.com'da yanında gösterilir. Uygulama indirdiği bir güncellemenin boyutunu ve sağlama toplamını, yüklemeyi önermeden önce denetler: “İndirme sağlama toplamıyla eşleşmediği için yüklenmedi.”
- Her uygulama sürümü birlikte test edildiği çalışma ortamını adlandırır ve uygulama comma'nıza tam olarak onu yükler.
- Eski bir uygulamaya, birlikte test edilmediği bir çalışma ortamı asla sunulmaz. Çalışma ortamı uygulamanın yüklediğinden daha yeni olan bir comma bunu söyler: CommaView'u güncelleyin, ardından yeniden deneyin.

## comma'nızı güvenle güncellemek

- Çalışma ortamı güncellemeleri kendiliğinden değil, Ana sayfa'dan veya Cihaz ayarları'ndan başlar.
- Güncellemeler bir sürüşü asla kesmez. Araç sürülüyorsa Güvenli güncelleme güncellemeyi sıraya alır ve comma, araç P konumunda ve openpilot devre dışıyken yükler. Aracı kapatmanız gerekmez.
- Bir çalışma ortamı güncellemesinden sonra, CommaView yeniden yayın yapmadan önce comma'nın yeniden başlatılması gerekir. Uygulama bunu ister.
- Çalışma ortamını istediğiniz zaman Cihaz ayarları'ndan kaldırabilirsiniz: [CommaView'u kaldırın](/tr/guides/uninstall).

## Nereden haberiniz olur

- Uygulama yeni bir sürüm hazır olduğunda size söyler.
- [Yenilikler](/whats-new) her değişikliği listeler.
- Önemli değişiklikler hakkında size e-posta göndeririz ve uygulamadan istediğiniz zaman geri bildirim gönderebilirsiniz (Ayarlar › **Destek ve tanılama**).
