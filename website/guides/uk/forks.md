---
title: "Перевірте, чи підтримуються ваш comma і форк"
description: "CommaView працює з openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot і OPGM, а з іншими форками — без гарантій."
topic: start
order: 2
kind: reference
lede: "CommaView показує дорожню камеру вашого comma з накладкою водіння того ПЗ, що на ньому працює. Він працює з openpilot і дев’ятьма його форками на comma 3X і comma four, а без гарантій — з іншими форками openpilot. Перш ніж щось змінювати, налаштування перевіряє, який форк на вашому comma."
updated: 2026-11-27
needs:
  - title: "comma 3X або comma four"
    text: "comma 3 не підтримується, зокрема збірки форків для comma 3, як-от xnor-c3. [Чому comma 3 не підтримується](/#faq-comma-3)."
  - title: "Ваш форк — як є"
    text: "Встановлений і працює як зазвичай. CommaView додає поруч своє середовище виконання й ніколи не змінює те, як форк керує авто."
steps:
  - id: unlisted
    title: "На форку не з переліку CommaView налаштування спершу питає вас"
    body: |
      Покрокове налаштування перевіряє, з якого репозиторію встановлено ПЗ вашого comma, і встановлює хук CommaView для цього форка. На форку не з переліку воно спершу перевіряє форк, нічого не змінюючи.
    tabs:
      - label: "Без гарантій"
        body: "Якщо CommaView може додати свій вид, налаштування показує **CommaView не перевіряв цей форк**. Воно називає форк за репозиторієм і каже, що малюється (камери, траєкторія, смуги, авто попереду, попередження й швидкість), а що ні (власні кнопки, кольори й віджети форка). **Усе одно встановити** встановлює на цей форк і лише на нього. **Назад** повертає до вибору comma; нічого не встановлено."
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**Усе одно встановити** додає вид CommaView до цього форка без гарантій."
      - label: "Лише відео (ранній доступ)"
        body: "Для FrogPilot і KisaPilot, екрани яких не приймають вид CommaView, тестувальники з прапорцем «Лише відео» бачать **Лише відео на цьому форку**: CommaView транслює камери й малює власний вид із даних водіння, нічого не змінюючи у форку. На comma цього ще не випробовували. Без прапорця налаштування каже, що форк не підтримується, і нічого не змінює."
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**Встановити лише відео**."
    note: "Коли перевірка відхиляє форк, налаштування пише «CommaView не може безпечно додати свій вид до …» і «На вашому comma нічого не змінено.»"
  - id: details
    title: "Подивіться, який форк малює Live View"
    body: |
      У Live View відкрийте **Подробиці**. Рядок **ПЗ** називає форк вашого comma, а форк не з переліку CommaView названо за репозиторієм, наприклад «crwusiz/openpilot · best effort».
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**Подробиці**, під зображенням."
      - text: "**ПЗ**: форк, що працює на вашому comma."
related: [setup, overlays, uninstall]
---

## Підтримувані форки

| Форк | Звідки | Підтримується з |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | Першої бети |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | Першої бети |
| **StarPilot** | github.com/StarPilotHQ/StarPilot, раніше github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor** (збірки xnor і rx) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot, встановлюється з i.carrotpilot.app | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

На форку не з переліку налаштування перевіряє, чи може CommaView додати свій вид, і спершу питає вас; якщо не може, налаштування зупиняється й залишає comma як був.

## Що показує кожен форк

### openpilot

Власне ПЗ comma.ai. Live View малює екран comma four, comma 3X або власну накладку CommaView — з вашою швидкістю, МАКС, обмеженням швидкості, авто попереду й змінами смуги.

### sunnypilot

CommaView малює екран sunnypilot з тим, що додає sunnypilot: стани «лише кермо» й «лише швидкість» від MADS, помічник обмеження швидкості, райдужну траєкторію й індикатори сліпих зон, а на екрані comma 3X — його знак обмеження швидкості, smart cruise та інтерфейс розробника. Він читає ваші налаштування sunnypilot, тож екран збігається з тим, що на comma.

### StarPilot

StarPilot показує свої режими водіння кольором, і CommaView використовує кольори, вибрані StarPilot: рамку, траєкторію й віджети на екранах comma four і comma 3X, попередження і вибір камери, зокрема камери водія.

Вимкніть налаштування StarPilot **Disable Logging**. Воно зупиняє відеокодер, з якого транслює Live View.

### openpilot від xnor-tech: xnor і rx

openpilot від xnor-tech має дві збірки. Гілки **xnor** працюють з екраном openpilot, а гілки **rx** — з екраном sunnypilot, обидві з підтримкою авто від xnor-tech. CommaView малює ту, що на вашому comma, з попередженнями так, як їх пише comma.

На Rivian із rx кермо зеленіє, коли авто кермує за кутом, і синіє, коли за моментом: кермо на comma four, а на екрані comma 3X — кнопка експериментального режиму.

### AdventurePilot

AdventurePilot — форк sunnypilot із власною підтримкою авто. CommaView малює екран sunnypilot з тим, що додає AdventurePilot:

- індикатор центрування в смузі: плашка з поштовхом і зміщенням на екрані comma 3X, компактна смуга на екрані comma four;
- позначка CURVE на екрані comma 3X, що блимає, поки діє контроль швидкості в поворотах;
- колір керма за режимом кермування і смуга моменту, що показує бічне прискорення, поки Rivian кермує через кутовий канал.

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 — форк sunnypilot, що додає авто Tesla HW1 (Autopilot 1). Його екран — екран sunnypilot, тож CommaView малює екран sunnypilot з усім, що додає sunnypilot, і називає форк у застосунку.

Його `op fork update` не може перемкнути форк, поки встановлено хук CommaView: спершу [видаліть середовище виконання CommaView](/uk/guides/uninstall) або скористайтеся перемикачем форків на екрані comma, що працює як зазвичай.

### carrotpilot

carrotpilot — форк openpilot для авто Hyundai, Kia і Genesis, що встановлюється з `i.carrotpilot.app`. CommaView малює для нього екран openpilot з вашою швидкістю, траєкторією, смугами й авто попереду. Те, що carrotpilot додає на свій екран, як-от навігацію, камери швидкості й HUD, поки не малюється.

Автооновлення carrotpilot і Git-інструменти на його вебсторінці прибирають хук CommaView до перезавантаження comma. Застосунок просить перезавантажити, і після цього Live View повертається.

### BluePilot, dragonpilot і OPGM

У переліку з CommaView 0.0.166 з його середовищем виконання. CommaView називає кожен і малює в стилі його основи: BluePilot — як sunnypilot, dragonpilot і OPGM — як openpilot, причому ALKA від dragonpilot показано як кермування. comma, що працював на одному з них без гарантій, переходить у перелік під час завантаження після оновлення середовища виконання. Жоден ще не їздив із CommaView. Офіційні [пакети накладок](/uk/guides/overlays) CommaView малюють більше з власних екранів BluePilot і dragonpilot.

## Форки не з переліку CommaView

Починаючи з CommaView 0.0.165, з його середовищем виконання на comma, налаштування може без гарантій додати вид CommaView до форка openpilot не з переліку. Live View малює форк у стилі openpilot або sunnypilot, якщо форк побудовано на екрані sunnypilot. Щоб скасувати це, **Видалити середовище виконання** в Налаштування пристрою повертає файли форка як було.

- **Без гарантій.** Випуски CommaView не перевіряються з вашим форком. Якщо форк оновиться до чогось, за чим CommaView не встигає, вид CommaView вимкнеться, а форк кермуватиме й показуватиме свій екран як зазвичай, доки випуск CommaView не врахує зміну.
- **Не будь-який форк.** Форки на старішому нативному екрані openpilot не підтримуються (нижче).
- **Ваша згода стосується цього форка.** Якщо comma перейде на інший форк не з переліку, CommaView знову спитає в налаштуванні, перш ніж додати туди свій вид.

### Форки, що проходять перевірку встановлення (без гарантій)

Кожен із них **проходить перевірку встановлення CommaView; без гарантій, не випробувано в авто.** Перевірено в листопаді 2026 року для названих гілок із середовищем виконання, яке встановлює CommaView 0.0.165: інсталятор пропонує форк, додає вид CommaView після вашої згоди й перевіряє його, як зробив би на вашому comma. Нічого з цього не випробовували на comma в авто, форк може не підтримувати кожне авто на обох пристроях, а наступне оновлення форка може змінити результат.

| Форк | Перевірені гілки | Пристрої | Малюється як |
| --- | --- | --- | --- |
| **crwusiz** (github.com/crwusiz/openpilot) | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **Carrot від jixiexiaoge** (github.com/jixiexiaoge/openpilot) | Carrot | comma four, comma 3X | openpilot |
| **MoreTore** (github.com/MoreTore/openpilot) | release-mici | comma four | openpilot |
| **zoompilot** (github.com/zoompilot/zoompilot) | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato** (github.com/AlexandreSato/openpilot) | master | comma four, comma 3X | openpilot |
| **lukasloetkolben** (github.com/lukasloetkolben/openpilot) | master | comma four, comma 3X | openpilot |
| **mvl-boston** (github.com/mvl-boston/openpilot) | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub** (github.com/mouxangithub/openpilot) | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro** (github.com/programanichiro/openpilot) | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2** (github.com/infiniteCable2/openpilot) | master | comma four, comma 3X | sunnypilot |
| **herizon1054** (github.com/herizon1054/openpilot) | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot** (github.com/NotAutopilot/openpilot) | nap-release, naponsp-alpha | comma four, comma 3X | openpilot (nap-release), sunnypilot (naponsp-alpha) |

Вашого форка тут немає? Він усе одно може працювати: налаштування перевірить його, перш ніж щось змінювати.

### Не підтримуються

Екрани цих форків не приймають вид CommaView, тож налаштування повідомляє про це й нічого не змінює на comma:

- **FrogPilot** (github.com/FrogAi/FrogPilot). Працює на старішому нативному (Qt) екрані openpilot, де немає місця для виду CommaView. «Лише відео» — у ранньому доступі.
- **KisaPilot** (github.com/kisapilot/openpilot). Його екран на Python вимкнено: він працює на старішому нативному (Qt) екрані openpilot. «Лише відео» — у ранньому доступі.
- **IQ.Pilot** (github.com/IQLvbs/iqpilot). З жовтня 2026 року працює на власній IQ.OS; підтримка чекає, доки CommaView зможе підтримувати його як окремий форк.
- **hikee9123** (github.com/hikee9123/openpilot). Працює на старішому нативному (Qt) екрані openpilot.

**Ранній доступ: лише відео для FrogPilot і KisaPilot.** З прапорцем «Лише відео» налаштування пропонує відтворювати їхні камери в Live View з власною накладкою CommaView замість їхніх екранів, нічого не змінюючи у форку. На comma цього ще не випробовували. Без прапорця налаштування й далі каже, що вони не підтримуються, і нічого не змінює.

## Які пристрої comma

comma 3X і comma four. comma 3 не підтримується, зокрема збірки форків для comma 3, як-от xnor-c3: [чому comma 3 не підтримується](/#faq-comma-3). Застосунок працює на Android-телефоні, планшеті чи мультимедійній системі.

## Гілки випусків і розробки

Перед кожним випуском середовище виконання CommaView збирається й перевіряється з випускними збірками цих форків. Гілки nightly openpilot і dev sunnypilot перевіряються щодня, коли змінюються, — як раннє попередження. Гілка розробки може змінюватися швидше за CommaView: якщо зміна не дає хуку CommaView завантажитися, екран і кермування вашого форка працюють як зазвичай.

## Вашого форка немає в переліку?

Спробуйте без гарантій і попросіть додати його до переліку на дошці функцій на [my.commaview.com](https://my.commaview.com) або надішліть ідею із застосунку (Налаштування › **Підтримка й діагностика**). Форк із переліку перевіряється перед кожним випуском. Дивіться, [що нового](/whats-new) в кожному випуску.

## Запитання

**Чи змінює CommaView те, як кермує мій форк?** Ні. Він додає невелике середовище виконання поруч із форком і невеликий хук в екранний інтерфейс, щоб CommaView міг малювати ту саму траєкторію, смуги й попередження. Те, як їде ваше авто, не змінюється.

**Чи працює CommaView зі StarPilot?** Так, з CommaView 0.0.162. Live View показує власні кольори, віджети й вибір камери StarPilot. Вимкніть налаштування StarPilot **Disable Logging**, яке зупиняє відеокодер, з якого транслює CommaView.

**Чи працює CommaView із carrotpilot?** Так, з CommaView 0.0.164. Live View малює для нього екран openpilot; те, що carrotpilot додає на свій екран, як-от навігацію й камери швидкості, поки не малюється. Після самооновлення carrotpilot застосунок просить перезавантажити comma, щоб повернути Live View.

**Чи працює CommaView із FrogPilot?** Поки ні: він працює на старішому нативному (Qt) екрані openpilot, де немає місця для виду CommaView, тож налаштування каже, що він не підтримується, і нічого не змінює. «Лише відео» для FrogPilot і KisaPilot — у ранньому доступі для тестувальників.
