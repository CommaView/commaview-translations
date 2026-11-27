---
title: "CommaView'u kurun"
description: "CommaView uygulamasını Android'e yükleyin, comma 3X veya comma four'unuzu hazırlayın ve rehberli kurulumun çalışma ortamını yükleyip comma'nızı eşleştirmesine izin verin."
topic: start
order: 1
kind: walkthrough
lede: "CommaView iki parçadan oluşur: Android telefonunuzdaki, tabletinizdeki veya multimedya ünitenizdeki uygulama ve comma'nızdaki küçük çalışma ortamı. Uygulamayı yükleyin; ardından uygulamadaki rehberli kurulum çalışma ortamını comma'nıza yükler, denetler ve eşleştirir. Birkaç dakika sürer; araç P konumunda ve openpilot devre dışıyken yapılır."
parked: true
updated: 2026-11-27
needs:
  - title: "Bir comma 3X veya comma four"
    text: "openpilot ya da [desteklenen bir fork](/tr/guides/forks) ile. comma 3 desteklenmiyor: openpilot sürümü kaynağında dondurulmuş ve ekranını farklı çiziyor, bu yüzden CommaView katmanını gösteremiyor. [comma 3 neden desteklenmiyor](/#faq-comma-3)."
  - title: "Bir Android cihaz ve davetiniz"
    text: "Android 8 veya üstü ve davetinizin geldiği e-posta adresi. CommaView beta aşamasında: davet edilen hesapla giriş yaparsınız."
  - title: "Aynı ağ"
    text: "Telefonunuz ve comma aynı yerel ağda: Wi‑Fi'nız, telefonunuzun hotspot'u, comma'nın kendi hotspot'u veya ikisinin de katılabildiği başka bir ağ. Araçta mısınız? [Ev Wi‑Fi'ı olmadan bağlanın](/tr/guides/connect-in-the-car)."
  - title: "Bir GitHub hesabı"
    text: "comma, verdiğiniz GitHub kullanıcı adındaki SSH anahtarlarını kabul eder. Anahtarı CommaView oluşturur; siz kurulum sırasında GitHub'a eklersiniz."
howItWorks:
  - title: "Telefonunuz"
    text: "GitHub'a eklediğiniz bir SSH anahtarı oluşturur."
    edge: "SSH"
  - title: "comma'nız"
    text: "Anahtarı GitHub kullanıcı adınızdan alır. CommaView çalışma ortamını fork'unuzun yanına yükler."
    edge: "yerel ağ"
  - title: "CommaView"
    text: "Çalışma ortamının yanıt verdiğini denetler ve comma'nızı kaydeder. Bundan sonra kendiliğinden yeniden bağlanır."
steps:
  - id: get-the-app
    title: "Uygulamayı edinin ve giriş yapın"
    body: |
      Android cihazınızda, davetinizin geldiği e-postayla [my.commaview.com](https://my.commaview.com) adresinde giriş yapın. **Get the app** altında **Download CommaView**'a dokunun. Dosyayı kontrol etmek isterseniz SHA-256 sağlama toplamı yanında gösterilir.

      İndirilen dosyayı açın. Android, tarayıcınızdan yüklemeye izin vermenizi ister: bu yükleme için izin verin, sonra yeniden kapatın.

      CommaView'u açın. Bir kez **CommaView'u geliştirmeye yardım edin** sorusunu sorar: **Gönder** veya **Gönderme**. Ardından giriş yapmanızı ister: **Giriş yap**'a dokunun ve davetinizin geldiği e-postayı kullanın. Bundan sonra erişim hakkı geçerli olduğu sürece çevrimdışı çalışır.
    tabs:
      - label: "CommaView'u geliştirmeye yardım edin"
        body: "Çökme raporları ve comma'nızın çalıştırdığı sürüş yazılımı; asla video, sürüşler, yerler veya isimler değil. Bunu istediğiniz zaman Ayarlar › **Gizlilik ve paylaşım**'dan değiştirebilirsiniz."
        screen: improve-commaview
        pins:
          - target: send
            text: "**Gönder**: sorunları düzeltmeye yardım etmek için çökme raporlarını gönderir."
          - target: dont-send
            text: "**Gönderme**: raporları telefonda tutar."
      - label: "Giriş yap"
        body: "Beta süresince CommaView davet edilen hesabınızı ister. **Giriş yap** tarayıcınızı açar."
        screen: sign-in
        pins:
          - target: sign-in
            text: "Davetinizin geldiği e-postayla **Giriş yap**."
    note: "Bir multimedya ünitesine veya aracınızın ekranındaki bir AI box'a mı yüklüyorsunuz? [Araç ekranları](/tr/guides/car-screens) ağını ve comma'nızla eşleştirmeyi anlatır."
  - id: connect
    title: "comma'nızı kurmaya başlayın"
    body: |
      Bildirimi okuyun, bunun resmî olmayan bir yazılım olduğunu ve güvenli kullanımdan sizin sorumlu olduğunuzu anladığınızı işaretleyin ve **Anladım — devam et**'e dokunun.

      **comma'nızı bağlayın** ekranında **CommaView'u comma'nıza kurun**'a dokunun.
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**CommaView'u comma'nıza kurun**: henüz CommaView çalıştırmayan bir comma için."
      - target: pair-runs
        text: "Başka bir telefondan zaten CommaView mı çalıştırıyor? Bunun yerine **CommaView çalıştıran bir comma eşleştirin**: [Başka bir telefon veya tablet ekleyin](/tr/guides/another-phone)."
  - id: setup-path
    title: "Bir kurulum yolu seçin"
    tabs:
      - label: "Rehberli kurulum"
        body: "**Rehberli kurulum**'u seçin (Önerilen olarak işaretli) ve **Rehberli kuruluma devam et**'e dokunun. CommaView bir SSH anahtarı oluşturur, bağlantıda size yol gösterir ve comma'nızı denetler. Sonraki adımlar bunu izler."
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**Rehberli kurulum**, Önerilen olarak işaretli."
          - target: continue
            text: "**Rehberli kuruluma devam et**."
      - label: "Manuel kurulum"
        body: "Yalnızca bilgisayarınızdan comma'ya `comma` kullanıcısıyla SSH zaten çalışıyorsa. **Manuel kurulum**'u, ardından **Manuel kuruluma devam et**'i seçin ve komutu terminalinizden çalıştırın. Yükleyici tek kullanımlık bir eşleştirme kodu gösterdiğinde **Komutu çalıştırdım**'a dokunun, comma'nızın IP'sini ve kodu girin ve **comma ekle**'ye dokunun. [Terminalden manuel kurulum](#manual-setup-from-a-terminal) her adımı içerir."
        screen: setup-manual-instructions
        pins:
          - text: "**Kopyalamak için dokunun** komutu kopyalar."
          - target: ran-command
            text: "Yükleyici eşleştirme kodunu gösterdiğinde **Komutu çalıştırdım**."
  - id: ssh-key
    title: "SSH anahtarını GitHub'a ekleyin"
    body: |
      CommaView bu telefon için bir SSH anahtarı oluşturur. **Anahtarı kopyala ve GitHub'ı aç**'a dokunun: açık anahtarı kopyalar ve GitHub'ın yeni SSH anahtarı sayfasını açar.

      GitHub'da anahtarı **Key** alanına yapıştırın, istediğiniz bir başlık verin (CommaView bir tane doldurur), ardından **Add SSH key** ile kaydedin. CommaView'a dönün ve **Devam**'a dokunun.
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**Anahtarı kopyala ve GitHub'ı aç**. “SSH anahtarı kopyalandı. GitHub açılıyor…” der."
      - target: own-key
        text: "**Kendi SSH anahtarımı kullan**, GitHub'da zaten olan bir anahtar çiftini içe aktarır."
      - target: continue
        text: "Anahtar GitHub'a kaydedildikten sonra **Devam**."
    note: "GitHub'da zaten bir anahtar çiftiniz mi var? Bunun yerine **Kendi SSH anahtarımı kullan** onu içe aktarır. Özel anahtar telefonunuzda kalır."
  - id: comma-ssh
    title: "comma'nızda SSH'yi açın"
    body: |
      comma'nın ekranında **Ayarlar → Cihaz → SSH**'ye gidin:

      1. GitHub kullanıcı adınızı girin.
      2. comma'nın GitHub anahtarlarınızı almasını bekleyin.
      3. SSH'yi açın.

      Ardından CommaView'a dönün ve **Devam**'a dokunun.
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "SSH açıldıktan sonra **Devam**."
    note: "comma anahtarlarınızı yalnızca bir kez, kullanıcı adını girdiğinizde alır. Anahtarı eklemeden önce mi girdiniz? Kaldırıp yeniden girin; comma anahtarları yeniden alsın."
  - id: choose-comma
    title: "comma'nızı seçin"
    body: |
      CommaView, bu Wi‑Fi ağında zaten CommaView çalıştıran comma'ları listeler; bu yüzden ilk kez kurduğunuz bir comma genellikle henüz orada değildir. **comma'm listede yok**'a dokunun ve IP adresini yazın. Ardından **CommaView'u yükle**'ye dokunun.

      IP'yi comma'da **Ayarlar → Ağ** altında bulursunuz: comma four'da Wi‑Fi düğmesindeki ağ adının altında, comma 3X'te **Gelişmiş** altında.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Zaten CommaView çalıştıran bir comma. Bu telefonda kayıtlı olan **Kayıt yeri: bu telefon** olarak işaretlenir."
      - text: "**comma'm listede yok**: IP adresini girin."
      - target: install
        text: "**CommaView'u yükle**."
  - id: safe-install
    title: "Güvenli yüklemeyi başlatın"
    body: |
      **Güvenli yükleme** iletişim kutusu yükleyeceği comma'yı adlandırır. Notu okuyun, ardından kısa geri sayımı bitince **Güvenli yüklemeyi başlat**'a dokunun.
    tabs:
      - label: "Araç P konumunda"
        body: "Araç P konumundaysa ve openpilot devrede değilse CommaView hemen yükler."
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "Geri sayımdan sonra **Güvenli yüklemeyi başlat**."
      - label: "Araç sürülüyor"
        body: "comma yüklemeyi sıraya alır ve araç P konumunda ve openpilot devre dışı olduğunda çalıştırır; böylece bir sürüş asla kesilmez. Kurulum **Yükleme sırada** gösterir: openpilot devre dışıyken vitesi P'ye alın, bir iki dakika bekleyin, ardından **Kurulumu bitir**'e dokunun."
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "Araç P konumuna alındıktan sonra **Kurulumu bitir**."
    note: "Ardından CommaView comma'ya SSH ile bağlanır, hangi comma olduğunu denetler ve uygulamanın bu sürümüyle test edilmiş çalışma ortamını yükler. Yüklemenin yanıt verdiğini denetler ve comma'nızı bu telefona kaydeder. İşlem bitene kadar telefonu aynı ağda tutun."
    warn: "Aracı çalışır durumda, P konumunda tutun. Güç kablo demeti yoksa aracı kapatmak comma'yı da kapatır ve yükleme durur."
  - id: ready
    title: "CommaView hazır"
    body: |
      comma'nız yüklendi, eşleştirildi ve bir sonraki açılışında kendiliğinden yeniden bağlanır.
    tabs:
      - label: "CommaView hazır"
        body: "**Bitti**'ye dokunun."
        screen: setup-done
        pins:
          - target: finish
            text: "**Bitti** sizi Ana sayfa'ya götürür."
      - label: "Kurulumu bitirmek için yeniden başlatın"
        body: "Kurulum bazen **Kurulumu bitirmek için yeniden başlatın** der: comma bir yeniden başlatmadan sonra telefonunuza yayın yapar. Araç kapalıyken veya openpilot devre dışıyken P konumunda **comma'yı yeniden başlat ve bitir**'e dokunun. openpilot yeniden başlarken yaklaşık bir dakika durur."
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**comma'yı yeniden başlat ve bitir**."
check: "Ana sayfa aracınızı, comma'sı **Bağlı** olarak, çalışma ortamını ve comma'nın adresini gösterir. **Live View'u aç**'a dokunun: yol canlı oynar, üzerinde yol ve öndeki araç çizilidir. Bundan sonra telefonunuz ve comma aynı ağdayken uygulama comma'nızı kendiliğinden bulur, adresi değişse bile."
fixes:
  - q: "SSH üzerinden bağlanılamadı"
    a: "comma'da **Ayarlar → Cihaz → SSH** altında SSH'nin açık olduğunu, GitHub kullanıcı adının size ait olduğunu ve CommaView anahtarının o GitHub hesabında bulunduğunu kontrol edin. Anahtarı kullanıcı adını girdikten sonra eklediyseniz, comma anahtarı alsın diye kullanıcı adını kaldırıp yeniden girin."
  - q: "comma'm listede yok"
    a: "İlk seferde bu beklenir: liste zaten CommaView çalıştıran comma'ları gösterir. **comma'm listede yok**'a dokunun ve IP adresini girin (comma'da **Ayarlar → Ağ**: comma four'da Wi‑Fi düğmesindeki ağ adının altında, comma 3X'te **Gelişmiş** altında). Telefonun comma ile aynı ağda olduğunu ve VPN kullanmadığını kontrol edin."
  - q: "Kurulum “Yükleme sırada” diyor"
    a: "comma aracın sürüldüğünü gördü, bu yüzden bekliyor. openpilot devre dışıyken vitesi P'ye alın, bir dakika bekleyin, ardından **Kurulumu bitir**'e dokunun. Aracı açık bırakın: güç kablo demeti yoksa aracı kapatmak comma'yı da kapatır."
  - q: "Kurulum comma'mın desteklenmediğini söylüyor"
    a: "comma 3'te kurulum durur ve **CommaView'u bir comma 3X veya comma four'a kurun** önerir. CommaView'un görünümünü ekranına ekleyemediği bir fork'ta kurulum bunu söyler ve hiçbir şeyi değiştirmez. [comma'nızın ve fork'unuzun desteklendiğini kontrol edin](/tr/guides/forks)."
  - q: "Eşleştirme kodu çalışmadı"
    a: "Eşleştirme kodları tek kullanımlıktır ve çabuk süresi dolar. Yeni bir kod için yükleyiciyi yeniden çalıştırın ve gösterildiği gibi yazdığınızı kontrol edin (kısa çizgi isteğe bağlıdır)."
  - q: "Bağlı ama video yok"
    a: "Kurulum ve eşleştirme tamam; sorun video akışında. comma'nın açık ve sürüşe hazır olduğunu kontrol edin, telefonu aynı ağda tutun ve Live View'u yeniden açın. **Bu comma'ya ulaşılamıyor** diyorsa [comma'nız bulunamıyor](/tr/guides/comma-not-found) sayfasına bakın."
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## Terminalden manuel kurulum

Yalnızca bilgisayarınızdan comma'ya `comma` kullanıcısıyla SSH zaten çalışıyorsa.

1. CommaView'da **Manuel kurulum**'u, ardından **Manuel kuruluma devam et**'i seçin. Uygulama, çalışma ortamının komutunu **Terminalinizden yükleyin** ekranında kopyalanmaya hazır gösterir (**Kopyalamak için dokunun**). Güncel sürümün çalışma ortamını yükleyen şu komuta benzer:

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. Komutu comma'nızla aynı Wi‑Fi ağındaki bir bilgisayardan, `COMMA_IP` yerine comma'nın IP adresini yazarak çalıştırın (comma'da **Ayarlar → Ağ**: comma four'da Wi‑Fi düğmesindeki ağ adının altında, comma 3X'te **Gelişmiş** altında). Bilgisayarınız yükleyiciyi indirir ve SSH onu comma'da `comma` kullanıcısıyla çalıştırır.
3. Yükleyici bitince CommaView comma'da başlar ve tek kullanımlık bir eşleştirme kodu gösterir.
4. CommaView'a dönüp **Komutu çalıştırdım**'a dokunun. **comma'nızı ekleyin** ekranında comma'nızı seçin veya IP'sini girin, eşleştirme kodunu yazın ve **comma ekle**'ye dokunun. Uygulama çalışma ortamını denetler ve comma'yı kaydeder.

## İlk sürüşünüzden önce

Sürmeden önce P konumunda deneyin.

- Ana sayfa comma'nızı **Bağlı** olarak gösterir.
- Live View oynar ve yol araçla birlikte hareket eder.
- Uygulama bir uyarı gösterirse veya onarım isterse, sürmeden önce halledin.
- Sürerken hiç ilginizi gerektirmeyecek şekilde ayarlayın.

Hâlâ takıldınız mı? [CommaView Discord](https://discord.gg/UuMhz9K8ft)'unda sorun veya uygulamadan geri bildirim gönderin. Destek günlük isterse [bir destek paketi gönderin](/tr/guides/support-bundle).
