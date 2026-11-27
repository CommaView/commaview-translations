---
title: "Transmisión local de la cámara del comma en Android: qué hace CommaView"
description: "CommaView transmite la cámara de carretera de tu comma con su superposición a Android por tu propia red: Live View, Grabaciones, Transmitir y lo que no hace."
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma camera streaming
  - comma four
  - Android app
  - CommaView
  - local streaming
heroLabel: "Para qué sirve"
draft: false
---

CommaView transmite la cámara de carretera de tu comma, con su superposición de conducción, a un teléfono, una tablet o una pantalla del coche Android por tu propia red. No hay ninguna nube entre el comma y tu teléfono, y no hace falta subir nada antes.

Son dos piezas: la app CommaView y un pequeño entorno de ejecución en el comma, `commaviewd`, que sirve la cámara y los datos de conducción a la app. La configuración guiada instala el entorno y lo comprueba.

## ¿Para qué transmitirla?

La pantalla del comma four mide 1,9 pulgadas. Es una buena pantalla para lo que hace, pero es pequeña, y sus dueños lo dicen. Las otras formas de obtener vídeo del comma están pensadas para otras tareas:

- **comma connect** guarda los viajes subidos durante 3 días, o un año con comma prime ([comma.ai/prime](https://comma.ai/prime)). Desde [openpilot 0.11.2](https://blog.comma.ai/0112release/) puede transmitir en directo las cámaras de carretera y del conductor con el coche aparcado, por internet, con un comma power instalado, y cortar clips MP4 en el comma.
- **SSH** te da los segmentos HEVC en bruto de un minuto del almacenamiento del comma.

Ninguna muestra la carretera con la superposición de conducción de openpilot mientras conduces. Para eso está CommaView.

## Qué hace CommaView

### Live View

La cámara de carretera, en vivo, con la pantalla propia de tu fork dibujada encima: la del comma four, la del comma 3X o la propia de CommaView, con tu velocidad, MÁX, el límite de velocidad, el vehículo delantero y los cambios de carril en un solo bloque. Live View dibuja la pantalla de cada fork con lo que ese fork añade, desde el MADS de sunnypilot hasta el HUD propio de StarPilot. Funciona hasta a los 20 fotogramas por segundo del comma y sigue en imagen en imagen.

En una tablet o una pantalla del coche Android, CommaView se organiza como un salpicadero, con los controles de Live View del lado del conductor.

### Grabaciones

Toca **Grabar** en Live View y, cuando aparques, CommaView descarga el vídeo del propio comma de ese tramo, hasta 10 minutos, y dibuja encima la pantalla de tu fork en tu teléfono: una reproducción. Reprodúcela, compártela o ábrela en otra app. Una copia en vivo guarda lo que muestra Live View mientras conduces, a 720p o 1080p, lista en cuanto te detienes y sin límite de 10 minutos. Las grabaciones se quedan en tu teléfono hasta que las eliminas.

### Transmitir

**Transmitir** emite lo que muestra Live View, la carretera y la superposición de CommaView, a tu canal de YouTube o a cualquier servidor RTMP, a 720p o 1080p. Inicia sesión con YouTube una vez y la app crea, inicia y termina cada emisión. Las transmisiones empiezan como **No listado**; quien las vea sabe por dónde conduces.

### Solo teléfonos emparejados

Las cámaras y los datos de tu comma solo van a los teléfonos y pantallas del coche emparejados con él. El vídeo, los viajes y los lugares van de tu comma a tu teléfono y a ningún otro sitio, salvo que los envíes, los transmitas o los aportes.

## Qué necesita internet

Live View y las grabaciones no: van directas del comma a tu teléfono, en la misma red local: tu Wi‑Fi, o un punto de acceso en el coche desde tu teléfono, la pantalla del coche, una caja de IA o el comma. Sí lo necesitan iniciar sesión, las actualizaciones de la app y del entorno, el mapa de **Ubicación del vehículo**, la clasificación, Transmitir y todo lo que envíes a CommaView.

## Con qué funciona

El comma 3X y el comma four, con openpilot, sunnypilot, StarPilot, el openpilot de xnor-tech, AdventurePilot, SunnyPilot-TeslaHW1 y carrotpilot. Otros forks de openpilot funcionan sin garantías: la configuración comprueba el fork y te pregunta antes de instalar. El comma 3 no es compatible: está en una versión congelada de openpilot de cuya pantalla CommaView no puede sacar su superposición. [Forks compatibles](/forks).

Necesitas un teléfono, una tablet o una pantalla del coche Android con Android 8 o posterior.

## Qué no es CommaView

- **No es comma connect.** No guarda viajes en la nube ni te muestra el coche desde la otra punta de la ciudad. Para eso, usa connect.
- **No es una dashcam.** [Usa una dashcam dedicada](/es/blog/is-comma-a-dashcam) si necesitas imágenes de accidentes o de aparcamiento con valor de prueba.
- **No es una ayuda a la conducción ni un sistema de seguridad.** Muestra lo que ve el comma; la carretera es la fuente de verdad.

## Úsalo con seguridad

Configura CommaView con el coche aparcado. Un pasajero puede ver Live View mientras conduces; si conduces solo, trátalo como la pantalla del propio comma y no apartes la vista de la carretera.

CommaView está en una beta solo por invitación. [Únete a la lista](https://my.commaview.com/join) y te escribiremos cuando sea tu turno.

CommaView no es oficial ni está afiliado a comma.ai, sunnypilot ni ningún fork de openpilot con el que funciona, ni cuenta con su respaldo. Es software beta y no es un sistema de seguridad: nunca dejes que te distraiga de la conducción.
