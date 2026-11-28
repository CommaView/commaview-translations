---
title: "CommaView'u comma'nızdan kaldırın"
description: "CommaView çalışma ortamını Cihaz ayarları'ndan comma'nızdan kaldırın, fork'unuzun dosyalarını eski hâline getirin ve telefonunuzda comma'yı unutun."
topic: account
order: 3
kind: walkthrough
lede: "**Çalışma ortamını kaldır**, CommaView'u comma'nızdan kaldırır: CommaView'un kancalarını geri alır, çalışma ortamını durdurur ve `/data/commaview`'u siler. Fork'unuz her zamanki gibi sürmeye devam eder. CommaView'u kaldırmak veya rehberli kurulumu baştan yeniden çalıştırmak için kullanın."
parked: true
updated: 2026-11-27
needs:
  - title: "Telefon ve comma bir arada"
    text: "comma ile aynı Wi‑Fi'da veya comma'nın hotspot'unda. Cihaz ayarları'nın güncellemeleri ve kaldırmayı yönetmek için comma'ya ihtiyacı var."
  - title: "Araç açık, P konumunda"
    text: "Araç sürülüyorsa comma, kaldırmayı araç P konumuna alınıp openpilot devre dışı olana kadar sıraya alır."
steps:
  - id: device-settings
    title: "comma'nın Cihaz ayarları'nı açın"
    body: |
      Ana sayfa'dan comma'nızın **Cihaz ayarları**'nı, ardından **Çalışma ortamı**'nı (“Güncelleyin veya kaldırın”) açın.
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**Çalışma ortamı**: CommaView'u güncelleyin veya kaldırın."
  - id: uninstall
    title: "Çalışma ortamını kaldır'a dokunun"
    body: |
      Çalışma ortamı güncellemesinin altındaki **Çalışma ortamını kaldır**, CommaView'u bu comma'dan kaldırır. Ardından rehberli kurulum baştan yeniden çalışabilir.
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**Çalışma ortamını kaldır**."
  - id: confirm
    title: "Onaylayın"
    body: |
      **CommaView kaldırılacak**: CommaView çalışma ortamı kancalarını geri alır, durur ve `/data/commaview`'u bu comma'dan siler. comma telefonunuzda kayıtlı kalır. Kısa geri sayımı bitince **Çalışma ortamını kaldır**'a dokunun.
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**CommaView kaldırılacak** ve bunun yaptıkları."
      - text: "Geri sayımdan sonra **Çalışma ortamını kaldır**. **İptal** CommaView'u tutar."
    note: "Araç sürülüyorsa comma kaldırmayı sıraya alır: CommaView, araç P konumuna alınıp openpilot devre dışı olduğunda kaldırılır ve o zamana kadar çalışmaya devam eder."
  - id: forget
    title: "İsterseniz comma'yı telefonunuzda unutun"
    body: |
      Cihaz ayarları artık çalışma ortamının kaldırıldığını söyler. comma'yı telefonunuzdan da kaldırmak için Cihaz ayarları'nın sonundaki **Bu comma'yı unut**'a dokunun: CommaView bu comma'yı göstermeyi bırakır ve eşleştirme anahtarını siler. Uygulamanın kendisini kaldırmak için CommaView'u, her uygulamada olduğu gibi Android'in ayarlarından kaldırın.
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**Bu comma'yı unut**."
check: "İletişim kutusu **Çalışma ortamı kaldırıldı** der ve Cihaz ayarları çalışma ortamını **Kaldırıldı** olarak gösterir: “CommaView, comma'nızdan kaldırıldı. Yeniden yüklemek için rehberli kurulumu çalıştırın.”"
fixes:
  - q: "“SSH izin hatası nedeniyle kaldırma başarısız oldu”"
    a: "comma bu telefonun SSH ile girmesine izin vermedi. comma'da **Ayarlar → Cihaz → SSH** altında SSH'nin açık olduğunu ve GitHub kullanıcı adında bu telefonun anahtarı bulunduğunu kontrol edin, ardından **Yeniden kaldır**'a dokunun."
  - q: "“comma, CommaView'u kaldıramadı ve olduğu gibi bıraktı”"
    a: "Hiçbir şey kaldırılmadı. Araç P konumundayken yeniden deneyin."
  - q: "“Kaldırma, araç P konumuna alınana kadar sırada”"
    a: "Araç sürülüyor. openpilot devre dışıyken vitesi P'ye alın, aracı açık tutun; comma CommaView'u kendiliğinden kaldırır."
  - q: "Kaldır düğmesi gri"
    a: "CommaView zaten bir çalışma ortamını güncelliyor veya kaldırıyor. Bittiğinde yeniden deneyin."
related: [setup, update-runtime, forks]
---

## Kaldırma neyi geri getirir

- **Listelenen bir fork'ta**, CommaView'un fork'un ekran arayüzüne eklediği küçük kancayı geri alır.
- **CommaView'un listelemediği bir fork'ta** (sınırlı destek), fork'un dosyalarını eski hâline getirir.
- **Yalnızca video**, fork'un dosyalarında hiçbir şeyi değiştirmedi; kaldırma çalışma ortamını kaldırır.

SunnyPilot-TeslaHW1'de, CommaView kancası yüklüyken fork'u taşıyamayan `op fork update` komutundan önce çalışma ortamını kaldırın. Daha fazlası [comma'nızın ve fork'unuzun desteklendiğini kontrol edin](/tr/guides/forks) sayfasında.

## CommaView'u yeniden kurmak

Bir kaldırmadan sonra comma telefonunuzda kayıtlı kalır. Temiz bir yükleme olarak yeniden yüklemek için [rehberli kurulumu](/tr/guides/setup) çalıştırın.
