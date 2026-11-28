---
title: "CommaView тепер працює зі StarPilot, xnor та AdventurePilot"
description: "CommaView 0.0.163 додає openpilot від xnor-tech і AdventurePilot після StarPilot у 0.0.162. Що кожен форк openpilot показує в Live View на comma 3X і comma four."
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "Нотатки до випуску"
draft: false
---

CommaView тепер працює з п’ятьма збірками openpilot: **openpilot**, **sunnypilot**, **StarPilot**, **openpilot від xnor-tech** (його збірки xnor і rx) та **AdventurePilot**. StarPilot з’явився в CommaView 0.0.162, а Beta 0.0.163 додає xnor і AdventurePilot. На кожному з них Live View малює власний екран форка на вашому телефоні, планшеті чи мультимедійній системі на Android — разом із тим, що цей форк додає.

Досі налаштування на цих форках зупинялося з повідомленням «unsupported upstream remote». Із застосунком 0.0.163 і його середовищем виконання воно встановлює й сполучає так само, як на openpilot.

## Що кожен форк показує в Live View

CommaView не вгадує за назвою форка. Середовище виконання на вашому comma повідомляє застосунку, що додає екран форка, і застосунок малює це на екрані comma four, comma 3X або на власному екрані CommaView.

| Форк | Що малює CommaView |
| --- | --- |
| openpilot | Екрани comma four і comma 3X або власну накладку CommaView |
| sunnypilot | Екран sunnypilot: MADS, асистент обмеження швидкості, райдужну траєкторію, індикатори сліпих зон і його доповнення для comma 3X |
| StarPilot | Кольори, віджети, сповіщення й вибір камери StarPilot |
| xnor | Екран openpilot на збірках xnor, екран sunnypilot на rx і колір керма Rivian від rx |
| AdventurePilot | Екран sunnypilot з індикатором центрування в смузі, позначкою CURVE і кольором режиму керування |

## StarPilot

StarPilot показує режими водіння кольором, і CommaView використовує кольори, які обрав StarPilot: рамку, траєкторію й віджети, сповіщення та вибір камери, зокрема камеру водія. Спершу вимкніть налаштування StarPilot **Disable Logging**: воно зупиняє відеокодер, з якого транслює Live View.

## openpilot від xnor-tech: xnor і rx

openpilot від xnor-tech має дві збірки з одного репозиторію. Його гілки **xnor** працюють з екраном openpilot, а гілки **rx** — з екраном sunnypilot, обидві з портами авто від xnor-tech. CommaView визначає, яку з них запущено на вашому comma, і малює відповідний екран зі сповіщеннями так, як їх пише comma.

На Rivian з rx кермо показує, як авто керує: зеленим, коли воно керує за кутом, синім — коли за крутним моментом. CommaView малює ті самі кольори на кермі comma four і на кнопці експериментального режиму comma 3X.

## AdventurePilot

AdventurePilot — форк sunnypilot з власними портами авто. CommaView малює екран sunnypilot з тим, що додає AdventurePilot:

- **індикатор центрування в смузі**: плашка з поштовхом і зміщенням на екрані comma 3X і компактна смужка на comma four;
- **позначку CURVE** на екрані comma 3X, яка блимає, коли діє контроль швидкості в поворотах;
- **колір режиму керування** на кермі та смужку крутного моменту, що показує бокове прискорення, коли Rivian керує через канал кута.

## Як отримати

CommaView перебуває в Beta лише за запрошеннями. Якщо ви в ній, застосунок сам запропонує оновлення 0.0.163. Після оновлення застосунку оновіть середовище виконання на comma із застосунку, а потім перезавантажте comma, коли він попросить. Оновлення середовища виконання чекають, доки авто стоїть на P, а openpilot вимкнено, тож поїздку ніколи не буде перервано.

Уперше з CommaView? [Посібник із налаштування](/uk/guides/setup) крок за кроком пояснює, як встановити застосунок і підключити comma.

## Що не змінилося

- CommaView працює на **comma 3X** і **comma four**. comma 3 і далі не підтримується, зокрема збірки форків для comma 3, як-от xnor-c3 ([чому](/uk/#faq-comma-3)).
- CommaView ніколи не змінює того, як їздить ваш форк. Він додає поруч невелике середовище виконання й невеликий хук в екранний інтерфейс, щоб малювати ту саму траєкторію, смуги й сповіщення.
- На форку, який CommaView ще не підтримує, налаштування зупиняється й залишає comma як було. Попросити підтримку свого форка можна на дошці ідей на my.commaview.com.

## Докладніше

- [Які форки openpilot працюють із CommaView](/uk/forks) і що показує кожен
- [Що нового](/uk/whats-new) в кожному випуску
- [Як влаштовані випуски CommaView](/uk/guides/releases)

CommaView — неофіційне програмне забезпечення, не пов’язане з comma.ai, sunnypilot, StarPilot, xnor-tech чи AdventurePilot. Це Beta і не система безпеки: ніколи не дозволяйте йому відволікати вас від дороги.
