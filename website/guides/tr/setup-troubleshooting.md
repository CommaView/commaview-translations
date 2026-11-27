---
title: "Yarıda kalan bir kurulumu düzeltin"
description: "CommaView kurulum mesajlarının anlamı, kurulumun sırasıyla: SSH, yükleme, ardından eşleştirme. Gördüğünüz mesajı ve ne yapacağınızı bulun."
topic: troubleshooting
order: 1
kind: fixes
lede: "Kurulum sırayla ilerler: comma'nıza SSH ile girer, CommaView'un çalışma ortamını yükler, ardından telefonunuzu onunla eşleştirir. Durduğunda mesajı hangi bölümün başarısız olduğunu söyler; önce o bölümü düzeltin. SSH'nin çalışması yalnızca ilkini kanıtlar: çalışma ortamı hiç başlamadıysa bir eşleştirme kodu işe yaramaz."
parked: true
updated: 2026-11-27
needs:
  - title: "P konumunda"
    text: "Araç P konumunda, openpilot devre dışı ve araç çalışır durumda: güç kablo demeti yoksa aracı kapatmak comma'yı da kapatır."
  - title: "Tek bir ağ"
    text: "Telefonunuz comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda. Bir dizüstü bilgisayarın comma'ya ulaşması, telefonunuzun da ulaşabildiğini kanıtlamaz."
steps:
  - id: read
    title: "Kurulumun ne dediğini okuyun ve ayrıntıları kopyalayın"
    body: |
      Yükleme başarısız olduğunda kurulum neyin yanlış gittiğini, comma'nızın eski hâline getirilip getirilmediğini ve ne yapmanız gerektiğini söyler. Bu cümleyi aşağıda [Çalışmazsa](#fixes) altında bulun.

      **Ayrıntıları kopyala**, desteğin okuduğu raporu kopyalar: uygulamanın sürümü, yayın, yükleyicinin son aşaması ve tüm çıktısı. Mesaj söylediğinde bunu support@commaview.com adresine bir e-postaya yapıştırın.
    tabs:
      - label: "Yükleme başarısız oldu"
        body: "Kurulum neyin başarısız olduğunu söyler ve **Ayrıntıları kopyala** sunar."
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**Ayrıntıları kopyala**."
          - target: install
            text: "**CommaView'u yükle**, nedeni düzelttikten sonra yeniden dener."
      - label: "SSH başarısız oldu"
        body: "Bir şey yüklenmeden önce kurulum comma'ya neden giremediğini, örneğin **SSH kimlik doğrulaması başarısız**, ve neyi kontrol etmeniz gerektiğini söyler."
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "Neyin yanlış gittiği ve neyin kontrol edileceği."
  - id: address
    title: "comma'nın adresini kontrol edin"
    body: |
      Kurulum telefonunuzun ağında comma'ları arar. Sizinki listede yoksa **comma'm listede yok**'a dokunun ve IP adresini yazın. comma'nızda bu **Ayarlar → Ağ** altındadır: comma four'da Wi‑Fi düğmesindeki ağ adının altında, comma 3X'te **Gelişmiş** altında.

      comma'nın her ağda farklı bir adresi vardır: ev Wi‑Fi'ınız, bir hotspot, bir VPN. Telefonunuzun şu anda bulunduğu ağın adresini kullanın.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Kurulumun bu ağda bulduğu bir comma."
      - text: "**comma'm listede yok**: bulunamadığında IP adresini yazın."
  - id: pair-code
    title: "Yeni bir kodla eşleştirin"
    body: |
      Eşleştirme kodları kısa ömürlüdür ve bir kez çalışır. Biri reddedilirse yeniden yazmayın: yenisini alın. Manuel yüklemeden sonra yükleyici bir tane gösterir; comma ile zaten eşleştirilmiş bir telefon **Cihaz ayarları › Başka bir telefon veya tablet eşleştir** altında bir tane gösterir.
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**comma IP adresi**."
      - target: pair-code
        text: "**Eşleştirme kodu**. Kısa çizgi isteğe bağlı."
  - id: runs
    title: "Zaten yüklü mü? Bunun yerine eşleştirin"
    body: |
      comma başka bir telefondan veya önceki bir kurulumdan zaten CommaView çalıştırıyorsa yeniden yüklemeniz gerekmez. Ana sayfa'da **comma ekle**'ye, ardından **Adres ve kod girin**'e dokunun ve comma'nın IP'si ile bir eşleştirme kodu veya davetle eşleştirin.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "comma'nın IP'si."
      - target: pair-code
        text: "**Eşleştirme kodu veya davet**."
      - target: pair
        text: "**comma eşleştir**."
  - id: no-video
    title: "Yüklendi ve eşleştirildi ama video yok"
    body: |
      Eşleştirmeden sonra eksik bir görüntü SSH değil, yayın sorunudur. Live View gördüğünü söyler, örneğin **Bu comma'ya ulaşılamıyor**, ve comma yanıt verdiğinde kendiliğinden yeniden bağlanır. [CommaView comma'nızı bulamıyor](/tr/guides/comma-not-found) sayfasına bakın.
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**Yeniden dene**."
fixes:
  - q: "“SSH kimlik doğrulaması başarısız.”"
    a: "CommaView anahtarının GitHub'da olduğunu (başlık fark etmez) ve comma'da SSH'nin açık olduğunu kontrol edin. GitHub kullanıcı adınızı comma'ya anahtarı eklemeden önce girdiyseniz, comma anahtarlarınızı yeniden alsın diye kaldırıp yeniden girin."
  - q: "“192.168.1.50:22 adresinde bağlantı reddedildi. comma'nızda SSH'nin etkin olduğundan emin olun.”"
    a: "comma'da **Ayarlar → Cihaz → SSH**'ye gidin ve SSH'yi açın."
  - q: "“… adresine bağlantı zaman aşımına uğradı” veya “… adresine rota yok”"
    a: "Telefonunuz o adrese ulaşamıyor. Telefonunuzun comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda olduğunu, comma'nın uyanık olduğunu (araç açık) ve IP adresinin comma'nın bu ağdaki adresi olduğunu kontrol edin."
  - q: "“… adresinde comma bulunamadı. IP adresini kontrol edin.”"
    a: "O adreste hiçbir şey yanıt vermedi. comma'nın **Ayarlar → Ağ** bölümündeki IP'yi kontrol edin."
  - q: "“Bu comma'nın SSH kimliği, son kurulumundan bu yana değişti.”"
    a: "comma'yı sıfırladıysanız veya yeniden yazılım yüklediyseniz kurulumu yeniden çalıştırın."
  - q: "“CommaView bu telefonda SSH anahtarını oluşturamadı. Yeniden deneyin veya kendi SSH anahtarınızı kullanın.”"
    a: "**Yeniden dene**'ye veya GitHub'da zaten olan bir anahtar çiftini içe aktarmak için **Kendi SSH anahtarımı kullan**'a dokunun."
  - q: "“Yükleme sırada.”"
    a: "Araç sürülüyordu, bu yüzden comma sürüşü kesmek yerine yüklemeyi sıraya aldı. openpilot devre dışıyken vitesi P'ye alın, araç açıkken bir iki dakika bekleyin, ardından **Kurulumu bitir**'e dokunun."
  - q: "“Araç sürülüyor, bu yüzden yükleme işlemi çalışmadı.”"
    a: "openpilot devre dışıyken vitesi P'ye alın, ardından yeniden deneyin."
  - q: "“comma'nızda başka bir CommaView yükleme, güncelleme veya onarım işlemi zaten çalışıyor.”"
    a: "Bitmesi için birkaç dakika bekleyin, ardından yeniden deneyin."
  - q: "“comma'nız CommaView'u indiremedi.”"
    a: "comma çalışma ortamını kendisi indirir. Wi‑Fi veya kendi SIM'i üzerinden internete bağlı olduğunu kontrol edin, ardından yeniden deneyin. Mobil verili bir telefon hotspot'u işe yarar."
  - q: "“CommaView indirmesi comma'nıza eksik veya bozuk ulaştı.”"
    a: "Yeniden deneyin. Tekrar olursa ayrıntıları kopyalayıp support@commaview.com adresine gönderin."
  - q: "“yükleme işlemi sırasında comma'nızın depolama alanı doldu.”"
    a: "Daha sonra yeniden deneyin. Tekrar olursa ayrıntıları kopyalayıp support@commaview.com adresine gönderin."
  - q: "“CommaView, comma'nızdaki sürüş yazılımını henüz desteklemiyor.”"
    a: "comma'nız CommaView'un yüklenemediği bir yazılım çalıştırıyor. [Hangi fork'larla çalıştığını kontrol edin](/tr/guides/forks). Kendi fork'unuzu istemek için ayrıntıları kopyalayıp support@commaview.com adresine gönderin."
  - q: "“CommaView görünümünü güvenle ekleyemiyor: …”"
    a: "Fork'unuz CommaView'un listelemediği bir fork ve denetim, ekranının CommaView'un bağlandığı yerde farklı olduğunu buldu. comma'nızda hiçbir şey değiştirilmedi. Fork'unuzu istemek için ayrıntıları kopyalayıp support@commaview.com adresine gönderin."
  - q: "“comma 3 desteklenmiyor”"
    a: "CommaView comma 3X ve comma four ile çalışır. comma 3'ün openpilot sürümü kaynağında dondurulmuş ve ekranını farklı çiziyor, bu yüzden CommaView katmanını gösteremiyor."
  - q: "“yükleme işleminden sonra CommaView comma'nızda başlamadı.”"
    a: "comma'nızı yeniden başlatın, ardından yeniden deneyin. Tekrar olursa ayrıntıları kopyalayıp support@commaview.com adresine gönderin."
  - q: "“Doğrulama başarısız. 192.168.1.50:5002 adresindeki CommaView API'sine ulaşılamadı.”"
    a: "Yükleme bitti ama telefonunuz çalışma ortamına ulaşamıyor. Telefonunuzun hâlâ comma'nın ağında olduğunu kontrol edin, ardından yeniden deneyin. SSH bir bilgisayardan çalışıyor da bu çalışmıyorsa, bilgisayar telefonunuzun olmadığı bir ağdadır."
  - q: "“Eşleştirme kodu kullanılamadı. Yeni bir kod oluşturup yeniden deneyin.”"
    a: "Kodun süresi doldu, zaten kullanıldı veya yanlış yazıldı. Yenisini alın ([3. adım](#step-pair-code))."
  - q: "“Eşleştirme başarısız: CommaView çalışma ortamı API'sine ulaşılamadı”"
    a: "Telefonunuz o adreste comma'ya ulaşamıyor. Hotspot'u veya ağı kontrol edin, ardından yeniden deneyin."
  - q: "“CommaView yeniden başlatmadan sonra kendiliğinden başlamayacak”"
    a: "CommaView yüklü ama comma'nız açılırken onu hiçbir şey başlatmıyor: comma'nızın `/data/continue.sh` dosyasında `exec ./launch_openpilot.sh` satırı yok. Bu satır eklendiğinde CommaView'u yeniden yükleyin."
related: [setup, comma-not-found, support-bundle]
---

## Kurulumun geçtiği bölümler

Her bölüm bir öncekine ihtiyaç duyar, bu yüzden bu sırayla kontrol edin:

1. **SSH**, port 22: kurulumun yüklemek için comma'ya nasıl girdiği. GitHub anahtarınıza, comma'daki GitHub kullanıcı adınıza ve açık SSH'ye ihtiyaç duyar.
2. **Yükleme**: comma çalışma ortamını indirir ve yükler. Sonraki bir şeye bakmadan önce sonucunu okuyun.
3. **Çalışma ortamı**, comma'da port 5002: kurulum yanıt verdiğini denetler, ardından onunla eşleştirir.
4. **Eşleştirme**: tek kullanımlık bir eşleştirme kodu telefonunuza comma için kendi anahtarını verir.
5. **Video**, port 8200 ile 8202 arası: Live View'un kameraları.

Bulma comma'yı bulamıyor ama adresini biliyorsanız, yazmak da aynı işi görür: bulma bir kolaylıktır, önemli olan comma'ya ulaşmaktır.

## Güvenlik

Kurulumu, yüklemeleri ve sorun gidermeyi araç P konumunda ve openpilot devre dışıyken yapın. Sürerken asla kurulum yapmayın veya uygulamada dokunarak gezinmeyin.
