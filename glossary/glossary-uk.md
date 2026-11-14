# Українська (Ukrainian) glossary

The words every Ukrainian string uses for CommaView's terms, so screens translated apart say the same thing. Where
openpilot already translates a term (`selfdrive/ui/translations/app_uk.po`, here read from sunnypilot's copy, which
carries openpilot's strings), its word is used, so the app says what the car's screen says. Machine drafted; a native
speaker's review is owed before release (the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`). Names don't decline; where
a case ending would be needed, a noun goes before them ("на пристрої comma", "у застосунку CommaView").

## Style

- The person is addressed formally, with **ви** and the plural imperative, as openpilot's Ukrainian does ("Ви впевнені,
  що хочете перезавантажити?", "Введіть пароль"). **ви / ваш** is lower case inside a sentence, as in openpilot's .po,
  capitalised only at the start of one.
- Ukrainian words, not Russian borrowings: **налаштування** (not «настройки»), **вимкнути** (not «виключити»),
  **застосунок** in sentences about the app, **поїздка**, **з’єднання**, **сповіщення**, **наразі**, **зберегти**.
- The apostrophe is the typographic **’** (U+2019) everywhere: з’єднання, ім’я, пам’ять, об’єкт. Never the ASCII `'`
  (which would need `\'` in Android's XML).
- Quotes are « » (nested „ “). Dashes: — with spaces around it. A space before a unit (`25.7 GB`); the numbers
  themselves come from the app's formatter.
- Buttons are short infinitives, as openpilot's and Android's Ukrainian write them: Скасувати, Готово, Зберегти,
  Видалити, Повторити, Продовжити, Відкрити, Закрити, Увімкнути, Вимкнути.
- No full stop on titles, buttons, row titles or pills; whole sentences in body text end with a full stop.
- Plurals give `one`, `few`, `many` and `other`: 1 запис, 2 записи, 5 записів, 1,5 запису (`other` is the fraction's
  form, the genitive singular). `one` covers 1, 21, 31…, `few` 2–4, 22–24…, `many` 0, 5–20, 25–30….
- Capitalisation: sentence case for titles and buttons (only the first word and names capitalised).
- Short words first: screens are checked at 200% text on a 360 dp phone, where a row's title holds about 12 Cyrillic
  letters and a row's subtitle about 14. A longer word on a title, label or short line is said in a shorter one or
  reworded (`після паркування`, not `після того, як ви припаркуєтеся`; `Енергія й чуйність Wi‑Fi`, not
  `Енергоспоживання …`). A hyphen doesn't help: Android doesn't break a line after one in the app's text, nor at a soft
  hyphen, so a compound must fit whole ([how-to-localize](../CONTRIBUTING.md#a-word-too-long-for-its-line)).
  A pill holds one line: Live View's CONNECTED is «З’єднано», since «ПІДКЛЮЧЕНО» runs past the Details pane at 2× text.

## Terms

| English | Українська | Note |
|---|---|---|
| Home (dock) | Головна | |
| Recordings | Записи | the section and its saved drives |
| Settings | Налаштування | |
| recording, a recording | запис | |
| drive (a trip the comma recorded) | поїздка | openpilot's ("зберігання поїздок") |
| replay | повтор | |
| live copy | жива копія | |
| saved moment | збережений момент | |
| Record | Запис | the rail's button |
| Go live / live streaming | Трансляція / пряма трансляція | |
| onroad screen | екран водіння | |
| onroad / offroad (the comma's state) | у дорозі / на стоянці | |
| design (an onroad screen's look) | дизайн | |
| overlay pack | пакет накладок | |
| fork | форк | as openpilot users say |
| runtime (commaviewd) | середовище виконання | |
| update / install / uninstall | оновити / встановити / видалити | openpilot's |
| reboot | перезавантажити | openpilot's; a title that can't hold «перезавантаження» says «перезапуск» («після перезапуску») |
| power off | вимкнути | openpilot's |
| pair / pairing | сполучити / сполучення | openpilot's "сполучення" (its button says «Підключити пристрій») |
| device (the comma) | пристрій | openpilot's |
| this phone / this device (the device CommaView runs on) | цей телефон / цей пристрій | openpilot's "телефон", "пристрій"; `common_this_phone` / `common_this_device`, a sentence's placeholder (how-to-localize.md, "This phone or this device"). Both masculine, inanimate: a sentence puts the slot only in the nominative or accusative ("%1$s зберігає", "Підключіть %1$s", "модель, яку має %1$s"), never after a preposition ("на цьому телефоні") or in the genitive |
| your phone / your device (`common_your_*`) | ваш телефон / ваш пристрій | both masculine, inanimate: nominative or accusative only, as цей телефон |
| connected / disconnected | підключено / відключено | openpilot's "підключити" |
| offline | офлайн | openpilot's |
| engaged / disengaged | активний / вимкнено | openpilot says «Вимкніть openpilot» / «Деактивуйте» for disengaging |
| override | втручання водія | |
| experimental mode | експериментальний режим | openpilot's |
| driver monitoring | моніторинг водія | openpilot's |
| driver camera | камера водія | openpilot's |
| road camera / wide camera | дорожня камера / ширококутна камера | |
| lead car | авто попереду | |
| speed limit | обмеження швидкості | |
| set speed / MAX | задана швидкість / МАКС | openpilot's MAX is МАКС |
| lane change | зміна смуги | openpilot's "смуга" |
| calibration | калібрування | openpilot's |
| driver position (left/right-hand drive) | місце водія (кермо зліва / справа) | |
| daylight contrast | денний контраст | |
| offline maps | офлайн-карти | the page's title is «Карти офлайн», two words that fit its header at 2× text |
| navigation | навігація | |
| Home / Work (places) | Дім / Робота | |
| vehicle location | місце авто | |
| account / sign in / sign out | обліковий запис / увійти / вийти | |
| leaderboard | таблиця лідерів | |
| achievement | досягнення | |
| privacy | конфіденційність | |
| diagnostics | діагностика | |
| report a problem | повідомити про проблему | |
| Details (Live View's pane) | Подробиці | |
| stream health | стан потоку | |
| storage | сховище | |
| hotspot | точка доступу | openpilot's |
| Live / Delayed (Live View's state) | Наживо / Із затримкою | |
| frame pacing | ритм кадрів | |
| inset (a picture in the picture) | врізка | |
| framing: Fill / Exact / Extend / Auto | Заповнити / Точно / Розширити / Авто | |
| camera framing | кадрування камери | |
| reduce motion | менше анімації | |
| screen edges | краї екрана | |
| View (Surround's) / chase / high / top-down | Вид / ззаду / згори / зверху | |
| vehicle detection / detector / model | виявлення авто / детектор / модель | |
| renderer | рендерер | |
| key (an API key, an SSH key) | ключ | public / private: відкритий / закритий ключ; openpilot's "SSH ключі" |
| dashboard (a service's) | панель керування | |
| reroute | перебудувати маршрут | |
| Where to? | Куди їдемо? | |
| map source | джерело карт | |
| Powered by | На основі | |
| steering / speed active, manual (the HUD's control line) | кермо активне / швидкість активна / вручну | review on a drive |
| steering only / speed only | лише кермо / лише швидкість | |
| blind spot | сліпа зона | |
| green light / lead car moving | зелене світло / авто попереду рушило | |
| safe update / install / repair | безпечне оновлення / встановлення / відновлення | |
| overlays (drawn on video) | накладки | not overlay packs (пакети накладок) |
| telemetry | телеметрія | |
| patch | патч | |
| in Park | на P | |
| power harness | кабель постійного живлення | |
| guided / manual setup | покрокове / ручне налаштування | |
| boot hook / runtime hook | хук завантаження / хук середовища | |
| vehicle security key | ключ безпеки авто | |
| pair code / invitation | код сполучення / запрошення | |
| phones with a key | телефони з ключем | |
| shared token | спільний токен | |
| development runtime | середовище для розробки | |
| controller | контролер | |
| best effort | без гарантій | |
| video only | лише відео | |
| widgets | віджети | |
| backup / restore | резервна копія / відновити | |
| read-only | лише читання | |
| head unit | мультимедійна система | |
| nearby devices | Пристрої поблизу | Android's permission |
| display over other apps | Показ поверх інших застосунків | Android's permission |
| set aside (saved lists) | відкладені | |
| Not now / Review | Не зараз / Переглянути | openpilot's "Переглянути" |
| queue | черга | |
| Needs processing | Потребує обробки | |
| pull drives | отримати поїздки | |
| whole drive | уся поїздка | |
| export | експорт / експортувати | |
| pack studio | студія пакетів | |
| clip | кліп | |
| log excerpt | уривок журналу | |
| support bundle | пакет для підтримки | |
| Driving insights | Статистика водіння | |
| contribute | зробити внесок | |
| route / segment (openpilot's) | маршрут / сегмент | openpilot's "сегмент" |
| Privacy & sharing | Приватність і обмін | the Settings page; not Конфіденційність, too long for the hub row at 2× text |
| stream key | ключ потоку | |
| destination (Go live's) | платформа | |
| Go live | Почати трансляцію | |
| YouTube Studio | Творча студія YouTube | YouTube's |
| Auto-start | Автозапуск | |
| Public / Unlisted / Private | Загальнодоступне / Не для всіх / Приватне | YouTube's |
| input (microphone) | джерело звуку | |
| car hands-free | гучний зв’язок авто | |
| metered / monthly limit | лімітне / місячний ліміт | openpilot's "лімітне з’єднання" |
| Your requests | Ваші запити | |
| Open / Closed (a request) | Відкрито / Закрито | |
| license | ліцензія | |
| map library | бібліотека карт | |
| map theme | тема карти | |
| spoken guidance | голосові підказки | |
| dev build | збірка для розробки | |
| access pass | перепустка | the account's |
| waitlist | список очікування | |
| beta member / admin | учасник Beta / адміністратор | |
| display name / public name | показуване ім’я / публічне ім’я | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | Цей тиждень / Минулий тиждень / За весь час | |
| finalized (a week) | підсумовано | |
| badge / share card | значок / картка для поширення | |
| Official / Community (packs) | Офіційні / Спільнота | |
| reviewed by CommaView / unreviewed | перевірено CommaView / не перевірено | |
| Update ready | Оновлення готове | |
| training collection | навчальна добірка | car detection's |
| recording metadata | метадані запису | |
| SSH identity (a comma's host key) | SSH-ідентичність | |
| keystore | сховище ключів | Android's |
| repository (a fork's) | репозиторій | |
| driving software | ПЗ водіння | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | повернуто як було | |
| app | застосунок | Android's Ukrainian; openpilot says «додаток» once |
| download / upload | завантажити / вивантажити | openpilot uses «завантаження» for uploads too; here they're told apart |
