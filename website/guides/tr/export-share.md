---
title: "Kayıtları paylaşın ve dışa aktarın"
description: "Kayıtlar'dan bir tekrar oynatmayı veya canlı kopyayı paylaşın, başka bir uygulamada açın ya da comma'nızdaki tüm bir sürüşü telefonunuza tek bir MP4 olarak dışa aktarın."
topic: recordings
order: 3
kind: walkthrough
lede: "Telefonunuzdaki her kayıt, Kayıtlar'daki **Kayıt işlemleri** menüsünden paylaşabileceğiniz, dosyalarınıza kaydedebileceğiniz veya başka bir uygulamada açabileceğiniz bir MP4'tür. **Tüm sürüşü dışa aktar…** de tüm bir sürüşün yol videosunu comma'nın kaydettiği gibi comma'nızdan telefonunuza kopyalar."
parked: true
updated: 2026-11-27
needs:
  - title: "Telefonunuzda bir kayıt"
    text: "Kayıtlar'da bir tekrar oynatma veya canlı kopya. Henüz yok mu? [Bir sürüşü kaydedin](/tr/guides/record) veya [canlı kopya kaydedin](/tr/guides/live-copy)."
  - title: "Tüm bir sürüş için"
    text: "Onu kaydeden comma; bu telefonla eşleştirilmiş, park hâlinde ve erişilebilir, sürüşlerini listeleyen bir çalışma ortamıyla."
steps:
  - id: open
    title: "Kaydı açın"
    body: |
      Alttaki çubuktan (daha büyük bir ekranda şeritten) **Kayıtlar**'ı açın ve sürüşe dokunun. Oynatıcısı ve bilgileriyle izleme ekranında açılır.
    screen: phone-recordings
    pins:
      - text: "Bir tekrar oynatma. Açmak için herhangi bir sürüşe dokunun."
      - target: live-copy-row
        text: "**Canlı kopya** olarak işaretli bir canlı kopya."
      - target: filter
        text: "**Filtre**: **Hazır** yalnızca paylaşılacak videosu olan sürüşleri gösterir."
  - id: actions
    title: "Kayıt işlemleri'ni açın"
    body: |
      İzleme ekranında, saat ve tarihin yanındaki Daha fazla düğmesi olan **Kayıt işlemleri**'ne dokunun.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Kayıt işlemleri**."
      - text: "**Tam ekran**, ekranın tamamında oynatır."
  - id: share
    title: "Paylaşın veya başka bir uygulamada açın"
    body: |
      **Paylaş**, videoyu Android'in paylaşım sayfasına verir; oradan gönderebilir veya dosyalarınıza kaydedebilirsiniz. **Başka bir uygulamada aç** başka bir video oynatıcıda oynatır.

      **Dosyalar**, bir sürüşün birkaç dosyası olduğunda her birini ayrı paylaşmak için listeler; örneğin uzun bir tüm sürüşün her parçası.
    screen: recordings-watch-menu
    pins:
      - target: share
        text: "**Paylaş**: Android'in paylaşım sayfası."
      - target: open-in
        text: "**Başka bir uygulamada aç**."
      - target: send
        text: "**CommaView'a gönder…** bunun yerine bu sürüşle ilgili bir sorunu CommaView'a gönderir: [Destek paketi gönderin](/tr/guides/support-bundle)."
    note: "Android'in paylaşım sayfası gösterilmiyor: Android'e aittir ve her telefonda farklı görünür."
    warn: "Bir video yoldan fazlasını gösterebilir: nerede ve ne zaman sürdüğünüzü, plakaları, yüzleri ve yerleri, Sürücü kamerası açıkken yapılan bir canlı kopyada sürücü kamerasını. Paylaşmadan önce kontrol edin."
  - id: export
    title: "Tüm bir sürüşü dışa aktarın"
    body: |
      comma'nızın kaydettiği bir sürüş için **Kayıt işlemleri**'nde **Tüm sürüşü dışa aktar…** bulunur. comma'nın tüm sürüş boyunca yol kamerasını, comma'nın kaydettiği gibi telefonunuzda tek bir MP4'e kopyalar. HUD'u yoktur: **Tekrar oynatma oluştur** sürüş ekranını kaydettiğiniz bölümlerin üzerine çizer.
    screen: recordings-watch-menu
    pins:
      - target: export-drive
        text: "**Tüm sürüşü dışa aktar…**"
  - id: export-sheet
    title: "Boyutu kontrol edin, ardından Dışa aktar'a dokunun"
    body: |
      Sayfa, comma'da sürüşün ne kadarı olduğunu, örneğin **23 dk · yaklaşık 1,7 GB**, ve telefonunuzdaki boş alanı söyler. **Dışa aktar**'a dokunun: “Tüm sürüş dışa aktarılıyor. comma park edildiğinde Kayıtlar'a kaydedilir.”

      Dışa aktar'a dokunana kadar hiçbir şey indirilmez. O andan itibaren comma sürüşü kopyalanırken saklar; o zamana kadar yer açmak için, en eski sürüşlerden başlayarak, onu yine silebilir.
    screen: recordings-export
    pins:
      - target: export
        text: "**Dışa aktar**."
      - target: cancel
        text: "**İptal**, dışa aktarmaz."
  - id: whole-drive
    title: "Tüm sürüşü Kayıtlar'da bulun"
    body: |
      Dışa aktarma, istediğiniz kaydın yanında kendi satırıdır: **Tüm sürüş**. Beklerken nedenini söyler, örneğin **Park etmeniz bekleniyor**, ardından ne kadar ilerlediğiyle **comma'dan kaydediliyor**. Kaydedildiğinde herhangi bir kayıt gibi oynar ve paylaşılır.
    screen: phone-recordings
    pins:
      - text: "Sürüşün başladığı zamanla adlandırılmış **Tüm sürüş** satırı."
    note: "Yaklaşık 45 dakikadan uzun yol videosu olan bir sürüş 3,5 GB'lık parçalar hâlinde kaydedilir: **Dosyalar** her birini listeler."
check: "Android'in paylaşım sayfası videoyla açılır. Tüm bir sürüş için satırı oynar ve izleme ekranındaki **Kaydedildi** bilgisi **Tüm sürüş · bu telefonda** der."
fixes:
  - q: "**Tüm sürüşü dışa aktar…** menüde yok"
    a: "comma'nızın kaydettiği bir sürüş için, o comma bu telefonla eşleştirilmişken ve çalışma ortamı sürüşlerini listelerken sunulur. Daha eskiyse [comma'nın çalışma ortamını güncelleyin](/tr/guides/update-runtime). Bir canlı kopyanın dışa aktarılacak comma sürüşü yoktur."
  - q: "**Tüm sürüşü dışa aktar…** gri: “Zaten dışa aktarıldı”, “Dışa aktarılıyor” veya “Kopyalama durdu: satırındaki Kaydetmeyi yeniden dene'yi kullanın”"
    a: "Sürüş daha önce dışa aktarıldı veya dışa aktarılması sürüyor. Durduysa **Tüm sürüş** satırını açın ve menüsünde **Kaydetmeyi yeniden dene**'yi seçin."
  - q: "“comma'da bu sürüş yok, bu yüzden dışa aktarılamaz.”"
    a: "comma daha yeni sürüşlere yer açmak için onu sildi. Hiçbir şey geri getiremez."
  - q: "“Bu sürüş comma'nın listelediği 50 sürüşten daha eski, bu yüzden kopyalamak için bulunamıyor.”"
    a: "comma'nız en yeni 50 sürüşünü listeler ve bu daha eski, bu yüzden dışa aktarma onu bulamıyor."
  - q: "“Yaklaşık 2,2 GB boş alan gerekiyor. Önce biraz yer açın.”"
    a: "Artık ihtiyacınız olmayan sürüşleri silin veya **Ayarlar › Kayıtlar**'da başka bir depolama seçin, ardından sayfayı yeniden açın."
  - q: "Tüm sürüş “Park etmeniz bekleniyor”, “comma'ya ulaşmak bekleniyor” veya “Live View açıkken bekleniyor” diyor"
    a: "Yalnızca comma park hâlindeyken, telefonunuzun erişiminde ve Live View göstermiyorken kopyalanır. Mümkün olduğunda kendiliğinden devam eder."
  - q: "“Video oynatıcı bulunamadı”"
    a: "Bu cihazda **Başka bir uygulamada aç** için başka bir video uygulaması yok. Kayıtlar'da oynatın veya dosyalarınıza kaydetmek için **Paylaş**'ı kullanın."
  - q: "“Bu tekrar oynatma burada oynatılamıyor. Başka bir uygulama deneyin.”"
    a: "**Başka bir uygulamada aç**'ı kullanın veya onu oynatan bir uygulamayla paylaşın."
related: [record, live-copy, support-bundle]
---

## Birkaçını aynı anda paylaşın

Seçmek için bir sürüşe basılı tutun, ardından eklemek için diğerlerine dokunun. Alttaki çubuk kaç tanesinin seçildiğini söyler. **Daha fazla** menüsünde, seçili her videoyu birlikte Android'in paylaşım sayfasına veren **Paylaş** vardır; çubukta **Sil** bulunur. Telefonunuzda henüz videosu olmayan bir sürüş dışarıda bırakılır ve işlem kaç tane aldığını söyler.

## Yeni sürüşleri otomatik çekin

**Ayarlar › Kayıtlar › Yeni sürüşleri çek**, her yeni sürüşün yol kamerasını dokunmadan eve getirir: telefonunuz ve comma'nız **Wi‑Fi ağları** altında seçtiğiniz bir Wi‑Fi'dayken ve araç park hâlindeyken yaklaşık her yarım saatte bir. Çekilen her sürüş, Kayıtlar'da tüm bir sürüş gibi HUD'suz bir **comma'dan** satırıdır. **Çekilen sürüşler için alan** kapladıkları alanı sınırlar: 10, 20 veya 50 GB ya da **Sınır yok**. Yer açmak için asla silinmezler.

## Nereye gider

Paylaşılan dosyalar yalnızca gönderdiğiniz yere gider. Kayıtlar telefonunuzda kalır; Android'in yedeklemesi ve yeni bir telefona aktarım onları dışarıda bırakır.
