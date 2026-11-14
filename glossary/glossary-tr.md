# Türkçe (Turkish) glossary

The words every Turkish string uses for CommaView's terms, so screens translated apart say the same thing. Where
openpilot already translates a term (`openpilot/selfdrive/ui/translations/app_tr.po`, taken from the `v0.10.1` tag:
master no longer has it), its word is used, so the app says what the car's screen says. Machine drafted; a native
speaker's review is owed before release (the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`).

## Style

- The formal **siz** throughout, as openpilot's Turkish: requests end in **-in / -ın / -un / -ün** ("bağlanın",
  "yeniden deneyin"), questions in **… emin misiniz?** ("Yeniden başlatmak istediğinizden emin misiniz?"),
  possessives in **-iniz** ("cihazınız", "hesabınız").
- Buttons are short, as Android's Turkish writes them: the bare verb or a noun (İptal, Bitti, Kaydet, Sil,
  Tekrar dene, Devam, Aç, Kapat, Tamam). Titles, rows and buttons are in sentence case ("Kalibrasyonu sıfırla"),
  as Android's Turkish, not openpilot's Title Case.
- No full stop on titles, buttons, row titles or pills; whole sentences in body text end with a full stop. Quotes are
  “ ” (nested ‘ ’), never straight quotes. The ellipsis stays …, as the English has it.
- **Dotted and dotless i**: the capital of i is **İ** and of ı is **I** (İptal, İndir, İleri, IŞIK). Upper-case
  words are written out, never left to a plain ASCII `toUpperCase()` (openpilot's AKTİF, MAKS, ÇEVRİMDIŞI).
- **Suffixes after a name** follow how it's said and take an apostrophe: openpilot'u / openpilot'a / openpilot'ta,
  comma'yı / comma'ya / comma'da / comma'nın ("koma"), CommaView'u / CommaView'a / CommaView'da ("komavyu"),
  YouTube'a / YouTube'da, Live View'a, Wi‑Fi'a (openpilot's), fork'u / fork'lar.
- **After a placeholder** (`%1$s`), whose last vowel isn't known, the sentence puts a noun after it and the suffix on
  the noun ("%1$s cihazına", "%1$s adlı fork", "%1$s dosyası"), or uses a form that doesn't vary (`için`, `ile`,
  `olarak`, a colon: "Bağlanıyor: %1$s"). Only where neither reads well does it take the form that fits most values,
  after an apostrophe. After a number (`%1$d`) the counted noun follows ("%1$d sürüş", "%1$d dakika"); Turkish
  doesn't pluralise a noun after a number, so `one` and `other` often read the same.
- **This phone / this device** (`common_this_phone` / `common_this_device`, a sentence's placeholder): **bu telefon** /
  **bu cihaz**. Both end in a voiced consonant after a back vowel, so the dative, locative, ablative, -daki and -la
  agree (telefona/cihaza, telefonda/cihazda, telefondan/cihazdan, telefondaki/cihazdaki, telefonla/cihazla) and are
  written straight onto the placeholder without an apostrophe ("%1$sda kayıtlı"). The accusative and genitive differ
  (telefonu/cihazı, telefonun/cihazın), so sentences don't use them: "this phone's X" is "%1$sdaki X", "pair this
  phone" is "%1$sla eşleştirin" or "eşleştirmeyi %1$sdan yapın". The placeholder is lower case mid-sentence, so a
  sentence whose English doesn't start with it doesn't start with it in Turkish either.
- Numbers and units: a space before a unit (`25.7 GB`, `5 dk`). The percent sign stays where the English puts it,
  since the number is formatted by the app (Turkish would write %50).

## Terms

| English | Türkçe | Note |
|---|---|---|
| Home (dock) | Ana sayfa | |
| Recordings | Kayıtlar | the section and its saved drives |
| Settings | Ayarlar | |
| recording, a recording | kayıt | |
| drive (a trip the comma recorded) | sürüş | openpilot's ("sürüş depolaması") |
| replay | tekrar oynatma | "Tekrar oynat" as a button |
| live copy | canlı kopya | |
| saved moment | kaydedilen an | |
| Record | Kayıt | the rail's button; Kaydet is Save |
| Go live / live streaming | canlı yayın | |
| onroad screen | sürüş ekranı | |
| onroad / offroad (the comma's state) | sürüşte / sürüş dışı | |
| design (an onroad screen's look) | tasarım | |
| overlay pack | katman paketi | |
| fork | fork | Turkish openpilot users say fork; fork'u, fork'lar |
| runtime (commaviewd) | çalışma ortamı | review: some would keep "runtime" |
| update / install / uninstall | güncelle / yükle / kaldır | openpilot's |
| reboot | yeniden başlat | openpilot's |
| power off | kapat | openpilot's |
| pair / pairing | eşleştir / eşleştirme | openpilot's (its button says EŞLE) |
| device (the comma) | cihaz | openpilot's |
| this phone | bu telefon | openpilot's telefon; where a sentence takes the placeholder, see the next row |
| this phone / this device (the device CommaView runs on) | bu telefon / bu cihaz | `common_this_phone` / `common_this_device`: only -a, -da, -dan, -daki, -la after the placeholder (Style) |
| your phone / your device (`common_your_*`) | telefonunuz / cihazınız | both end in -(u/ı)nuz after a back vowel, so -a, -da, -dan, -daki, -la agree; the accusative (telefonunuzu/cihazınızı) differs, so "keep your phone…" is "Lütfen %1$s … kalsın" |
| connected / disconnected | bağlı / bağlantı kesildi | |
| offline | çevrimdışı | openpilot's |
| engaged / disengaged | devrede / devre dışı | openpilot's ("devreden çık") |
| override | sürücü müdahalesi | |
| experimental mode | Deneysel mod | openpilot's |
| driver monitoring | sürücü izleme | openpilot's |
| driver camera | sürücü kamerası | openpilot's |
| road camera / wide camera | yol kamerası / geniş açı kamerası | |
| lead car | öndeki araç | openpilot's |
| speed limit | hız sınırı | |
| set speed / MAX | ayarlı hız / MAKS | openpilot's MAX is MAKS |
| lane change | şerit değiştirme | openpilot's şerit |
| calibration | kalibrasyon | openpilot's |
| driver position (left/right-hand drive) | sürücü konumu (soldan / sağdan direksiyonlu) | |
| daylight contrast | gün ışığı kontrastı | |
| offline maps | çevrimdışı haritalar | |
| navigation | navigasyon | |
| Home / Work (places) | Ev / İş | |
| vehicle location | araç konumu | |
| account / sign in / sign out | hesap / giriş yap / çıkış yap | |
| leaderboard | sıralama | |
| achievement | başarım | |
| privacy | gizlilik | |
| diagnostics | tanılama | |
| report a problem | sorun bildir | |
| Details (Live View's pane) | Ayrıntılar | |
| stream health | akış durumu | |
| storage | depolama | openpilot's |
| hotspot | hotspot | Android's Turkish; openpilot's tethering strings are mistranslated |
| Live / Delayed (Live View's state) | Canlı / Gecikmeli | |
| frame pacing | kare zamanlaması | |
| inset (a picture in the picture) | küçük pencere | |
| framing: Fill / Exact / Extend / Auto | Doldur / Birebir / Genişlet / Otomatik | |
| camera framing | kamera kadrajı | |
| reduce motion | hareketi azalt | |
| screen edges | ekran kenarları | |
| View (Surround's) / chase / high / top-down | Görünüm / takip / yüksek / üstten | |
| vehicle detection / detector / model | araç algılama / algılayıcı / algılama modeli | |
| renderer | oluşturucu | |
| key (an API key, an SSH key) | anahtar | openpilot's SSH anahtarı; public / private: açık anahtar / özel anahtar |
| dashboard (a service's) | panel | |
| reroute | rotayı yeniden hesapla | |
| Where to? | Nereye? | |
| map source | harita kaynağı | |
| Powered by | Kaynak: | |
| steering / speed active, manual (the HUD's control line) | direksiyon etkin / hız etkin / manuel | review on a drive |
| steering only / speed only | yalnızca direksiyon / yalnızca hız | |
| blind spot | kör nokta | |
| green light / lead car moving | yeşil ışık / öndeki araç hareket etti | |
| safe update / install / repair | güvenli güncelleme / güvenli yükleme / güvenli onarım | |
| overlays (drawn on video) | katmanlar | not overlay packs (katman paketleri) |
| telemetry | telemetri | |
| patch | yama | |
| in Park | P konumunda | "Vitesi P'ye alın" |
| power harness | güç kablo demeti | openpilot's old Qt text had "emniyet kemeri", a mistake |
| guided / manual setup | rehberli kurulum / manuel kurulum | |
| boot hook / runtime hook | açılış kancası / çalışma ortamı kancası | |
| vehicle security key | araç güvenlik anahtarı | |
| pair code / invitation | eşleştirme kodu / davet kodu | |
| phones with a key | anahtarı olan telefonlar | |
| shared token | paylaşılan belirteç | |
| development runtime | geliştirme çalışma ortamı | |
| controller | denetleyici | |
| best effort | sınırlı destek | works, without a promise; review |
| video only | yalnızca video | |
| widgets | widget'lar | Android's Turkish |
| backup / restore | yedekle / geri yükle | |
| read-only | salt okunur | |
| head unit | multimedya ünitesi | |
| nearby devices | Yakındaki cihazlar | Android's permission |
| display over other apps | Diğer uygulamaların üzerinde göster | Android's permission |
| set aside (saved lists) | kenara ayır | |
| Not now / Review | Şimdi değil / Gözden geçir | openpilot's REVIEW is GÖZDEN GEÇİR |
| queue | kuyruk | |
| Needs processing | İşlenmesi gerekiyor | |
| pull drives | sürüşleri çek | |
| whole drive | tüm sürüş | |
| export | dışa aktar | |
| pack studio | paket stüdyosu | |
| clip | klip | |
| log excerpt | günlük kesiti | |
| support bundle | destek paketi | |
| Driving insights | Sürüş istatistikleri | |
| contribute | katkıda bulun | |
| route / segment (openpilot's) | rota / segment | openpilot's segment |
| Privacy & sharing | Gizlilik ve paylaşım | the Settings page |
| stream key | yayın anahtarı | |
| destination (Go live's) | yayın hedefi | |
| Go live | Yayına başla | |
| YouTube Studio | YouTube Studio | YouTube's Turkish keeps it |
| Auto-start | Otomatik başlat | |
| Public / Unlisted / Private | Herkese açık / Liste dışı / Gizli | YouTube's |
| input (microphone) | giriş | |
| car hands-free | araç eller serbest | |
| metered / monthly limit | sınırlı / aylık sınır | openpilot's "sınırsız bir ağ" for unmetered |
| Your requests | Talepleriniz | |
| Open / Closed (a request) | Açık / Kapalı | |
| license | lisans | |
| map library | harita kitaplığı | |
| map theme | harita teması | |
| spoken guidance | sesli yönlendirme | |
| dev build | geliştirici sürümü | |
| access pass | erişim hakkı | the account's |
| waitlist | bekleme listesi | |
| beta member / admin | Beta üyesi / yönetici | |
| display name / public name | görünen ad / herkese açık ad | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | Bu hafta / Geçen hafta / Tüm zamanlar | |
| finalized (a week) | kesinleşti | |
| badge / share card | rozet / paylaşım kartı | |
| Official / Community (packs) | Resmî / Topluluk | |
| reviewed by CommaView / unreviewed | CommaView inceledi / incelenmedi | |
| Update ready | Güncelleme hazır | |
| training collection | eğitim verisi toplama | openpilot's eğitim verisi |
| recording metadata | kayıt meta verileri | |
| SSH identity (a comma's host key) | SSH kimliği | |
| keystore | anahtar deposu | Android's |
| repository (a fork's) | depo | |
| driving software | sürüş yazılımı | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | eski hâline getirildi | |
