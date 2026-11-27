---
title: "¿comma connect o vídeo local? Cuál hace lo que necesitas"
description: "comma connect, SSH y CommaView comparados tras openpilot 0.11.2: transmisión con el coche aparcado, clips, retención de viajes, calidad, privacidad y para qué sirve cada uno."
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - local video access
  - comma four
  - CommaView
heroLabel: "Comparativa para decidir"
draft: false
---

comma connect, la app web de comma, es donde la mayoría de los dueños miran primero sus viajes, y para muchas tareas es el sitio adecuado. Desde openpilot 0.11.2 hace más que antes: puede transmitir en directo un coche aparcado y cortar clips MP4 en el dispositivo. El acceso local, por SSH o con CommaView, hace otro trabajo: saca el vídeo directamente del comma por tu propia red.

La respuesta corta:

- **Un viaje reciente, desde cualquier sitio:** comma connect.
- **Echar un vistazo al coche mientras está aparcado:** la transmisión en directo de comma connect.
- **Ver la carretera con la superposición de conducción de tu fork mientras conduces, en una pantalla más grande:** Live View de CommaView.
- **Los archivos de cámara en bruto, para desarrollo o para archivar:** SSH.
- **Un clip de lo que acabas de ver, con la superposición, en tu teléfono y sin subir nada:** **Grabar** de CommaView.

## Qué hace comma connect

**Guarda tus viajes en la nube, durante un tiempo.** La [página de prime](https://comma.ai/prime) de comma dice que las grabaciones «se suben a connect, donde se guardan durante 3 días». Con comma prime (24 $ al mes, solo en EE. UU., datos incluidos) o prime lite (14 $ al mes, con tu propia SIM si quieres datos móviles), connect las guarda un año.

**Lo que muestra por defecto es el vídeo pequeño.** La [documentación de registros](https://docs.comma.ai/concepts/logs/) de comma dice que el vídeo de connect sale de los archivos qcamera, «versiones de menor resolución de fcamera.hevc», hechas para subirse rápido con una conexión lenta. Los archivos HEVC a resolución completa se quedan en el comma salvo que también los subas.

**Desde 0.11.2, puede transmitir en directo un coche aparcado.** La [entrada de la versión 0.11.2](https://blog.comma.ai/0112release/) (23 de octubre de 2026) dice que con conexión a internet, «el Wi‑Fi de casa o el LTE de comma prime», y un comma power instalado, «puedes transmitir en directo tus cámaras de carretera y del conductor para ver qué pasa alrededor de tu vehículo mientras está aparcado». Lo ves en connect, desde cualquier sitio.

**También corta clips.** La misma versión añade un botón de clips en connect: eliges una parte de un viaje y «tu comma la une y la recodifica como un MP4 (H.264) ampliamente compatible». Deja el comma encendido mientras trabaja y luego descarga el clip de connect.

Es un avance real. Si quieres ver tu coche aparcado desde tu mesa, o mandar a un amigo un clip del viaje de anoche, connect ya hace las dos cosas.

## Qué no hace comma connect

- **No transmite mientras conduces.** La transmisión en directo es para un coche aparcado.
- **No dibuja la superposición de conducción de openpilot.** La transmisión y los clips son vídeo de cámara, sin la trayectoria, los carriles, las alertas ni la velocidad que ves en la pantalla del comma.
- **Necesita internet.** La transmisión necesita el Wi‑Fi de casa o el LTE de prime, y los viajes tienen que subirse antes de que connect pueda mostrarlos.
- **Olvida a los 3 días sin prime.** Pasado ese tiempo, connect deja de mostrar el viaje, aunque el comma aún lo tenga.

Nada de eso es un defecto. connect es un servicio en la nube para ver tu coche y tus viajes estés donde estés.

## Qué hace el acceso local

Acceso local significa obtener el vídeo del propio comma, en la misma red, en lugar de los servidores de comma.

### SSH: los archivos en bruto

Cada viaje de openpilot se guarda en el comma en segmentos de un minuto, cada uno con sus archivos: `fcamera.hevc` (carretera), `ecamera.hevc` (carretera gran angular), `dcamera.hevc` (conductor), `qcamera.ts` (la vista previa pequeña) y los registros. Por SSH puedes copiar cualquiera mientras el comma los tenga; borra los viajes más antiguos cuando se queda sin espacio. Es la forma de obtener vídeo a resolución completa para desarrollo o para tu propio archivo, pero son archivos HEVC de un minuto, no un clip que puedas compartir. Nuestra guía para [descargar las imágenes del comma](/es/blog/download-comma-dashcam-footage) lo explica paso a paso.

### CommaView: Live View y Grabaciones en Android

CommaView es una app de Android y un pequeño entorno de ejecución en el comma, `commaviewd`, que envía la cámara y los datos de conducción a tu teléfono por tu propia red local: tu Wi‑Fi, o un punto de acceso en el coche, sea el de tu teléfono, el de la pantalla del coche o el del comma.

- **Live View, mientras conduces.** La cámara de carretera con la pantalla propia de tu fork dibujada encima, como la dibuja el comma four o el comma 3X, o con la pantalla propia de CommaView, en un teléfono, una tablet en el salpicadero o una pantalla del coche Android. La pantalla del comma four mide 1,9 pulgadas; la de tu teléfono es mucho más grande.
- **Grabaciones en tu teléfono.** Toca **Grabar** en Live View y, cuando aparques, CommaView descarga el vídeo del propio comma de ese tramo, hasta 10 minutos, y dibuja encima la pantalla de tu fork en el teléfono. O guarda una copia en vivo de lo que muestra Live View, a 720p o 1080p, sin límite de 10 minutos. Reprodúcela, compártela o ábrela en otra app.
- **Transmitir.** Emite lo que muestra Live View, la carretera y la superposición, a tu canal de YouTube o a cualquier servidor RTMP, a 720p o 1080p.
- **Sin suscripción y sin subidas.** Live View y las grabaciones van de tu comma a tu teléfono, y las grabaciones se quedan ahí hasta que las eliminas. Las cámaras de tu comma solo van a los teléfonos y pantallas del coche emparejados con él.

Funciona con el comma 3X y el comma four, con openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 y carrotpilot, y con otros forks sin garantías. [Qué forks, y qué dibuja Live View en cada uno](/forks).

## Lado a lado

| Función | comma connect | CommaView |
| --- | --- | --- |
| Vídeo en vivo | Cámaras de carretera y del conductor, con el coche aparcado | Cámara de carretera, mientras conduces |
| Superposición de conducción | No | La pantalla de tu fork, o la de CommaView |
| Por dónde va el vídeo | Por internet, y se ve en connect | Por tu propia red local (Wi‑Fi o un punto de acceso), a tus teléfonos emparejados |
| Necesita | Internet, y un comma power para la transmisión | Un teléfono, una tablet o una pantalla del coche Android en la misma red |
| Clips | Cualquier parte de un viaje, como MP4 cortado en el comma y descargado de connect | Lo que grabaste en Live View: una reproducción de hasta 10 minutos, o una copia en vivo, con la superposición |
| Cuánto duran los viajes | 3 días, un año con prime | En tu teléfono hasta que los eliminas |
| Coste | Gratis, o prime 24 $ / lite 14 $ al mes | Sin suscripción; CommaView está en una beta solo por invitación |

## Usa los dos

No compiten por la misma tarea. Quédate con connect para ver el coche desde cualquier sitio y para los viajes que quieras en la nube; usa CommaView para ver la carretera con la superposición de tu fork en una pantalla más grande, grabar lo que viste y transmitirlo. Un pasajero puede ver Live View mientras conduces; si conduces solo, trátalo como la pantalla del propio comma y no apartes la vista de la carretera.

## Para saber más

- [comma prime](https://comma.ai/prime), sobre los planes de connect y cuánto tiempo guarda los viajes
- [openpilot 0.11.2](https://blog.comma.ai/0112release/), sobre la transmisión en directo y los clips
- [Cómo descargar las imágenes del comma](/es/blog/download-comma-dashcam-footage), por SSH
- [Configurar CommaView](/es/guides/setup)

CommaView no es oficial ni está afiliado a comma.ai, sunnypilot ni ningún fork de openpilot con el que funciona, ni cuenta con su respaldo. Es software beta y no es un sistema de seguridad: nunca dejes que te distraiga de la conducción.
