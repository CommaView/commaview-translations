---
title: "Cómo descargar las imágenes de dashcam de un comma"
description: "Una guía práctica sobre los archivos de vídeo del comma, las diferencias entre comma 3, 3X y four, y las formas más seguras de exportar las imágenes de una ruta."
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma device video
  - dashcam footage
  - openpilot tools
  - SSH
heroLabel: "Guía del comma"
draft: false
---

¿Necesitas sacar vídeo de un comma? Los caminos habituales son comma connect, Openpilot Toolkit o el acceso directo por SSH/SFTP.

Lo que confunde a la gente es la organización de los archivos. Los comma graban las rutas de openpilot en segmentos cortos, no en un único clip de dashcam enorme. Cada segmento puede incluir archivos de cámara en bruto, vídeo de vista previa y registros de la ruta. Una vez que lo entiendes, exportar imágenes deja de ser un misterio.

Una nota importante de entrada: un comma puede ser útil para grabar la carretera, depurar y revisar rutas, pero no es un sustituto directo de una dashcam dedicada.

## Los comma son cámaras útiles, no dashcams perfectas

Una dashcam dedicada está pensada para capturar pruebas: arranque rápido, resistencia a accidentes, modo aparcamiento, exportación sencilla de archivos, opciones de cámara trasera y almacenamiento extraíble.

Un comma está hecho para ejecutar openpilot. Graba datos de ruta porque son útiles para los modelos de conducción, la depuración, las vistas previas de connect y el desarrollo. Esas imágenes pueden ser valiosas, pero tienen sus contrapartidas:

- recuperar las imágenes puede ser más difícil que sacar una tarjeta SD
- un accidente o un corte repentino de corriente puede hacer perder las imágenes recientes
- grabar en modo aparcamiento no es su objetivo principal
- no incluye la cobertura de una dashcam trasera
- los datos locales antiguos se borran cuando el dispositivo necesita espacio

Si lo que buscas son imágenes fiables de un accidente, usa una dashcam de verdad. Si lo que buscas son imágenes de rutas de openpilot, revisión para desarrollo o exportar vídeo en local, merece la pena aprender cómo funciona el comma.

## ¿Qué archivos graba openpilot?

La documentación oficial de registro de openpilot describe las rutas como segmentos de un minuto. Para cada segmento, el openpilot actual graba estos tipos de archivo:

| Archivo | Qué contiene |
| --- | --- |
| `fcamera.hevc` | vídeo de la cámara de carretera, H.265/HEVC |
| `ecamera.hevc` | vídeo de la cámara de carretera gran angular, H.265/HEVC |
| `dcamera.hevc` | vídeo de la cámara del conductor/habitáculo, H.265/HEVC |
| `qcamera.ts` | vista previa H.264 a menor resolución de la cámara de carretera |
| `rlog.zst` | registros completos de la ruta |
| `qlog.zst` | registros reducidos de la ruta |

El vídeo que muestra comma connect es el `qcamera.ts`, de menor resolución. Las imágenes de cámara a resolución completa están en los archivos HEVC, y puede que tengas que subirlas a mano desde connect o copiarlas directamente del dispositivo.

Las rutas antiguas, los forks antiguos o la documentación antigua pueden mostrar `rlog`/`qlog` sin `.zst`, o nombres de registro `.bz2` más antiguos. Para el openpilot actual, usa los nombres de arriba.

## comma 3, comma 3X y comma four: ¿qué cambia?

Hay dos cosas distintas que la gente mezcla: el hardware de las cámaras y la organización de los archivos.

El hardware de las cámaras cambia según la generación:

| Dispositivo | Cámaras y almacenamiento |
| --- | --- |
| comma 3 | Tres cámaras de 1080p con HDR de 120 dB. La documentación de la comunidad recoge varias versiones de almacenamiento: 1 TB, 250 GB, 64 GB (tardía) y 32 GB (temprana). |
| comma 3X | La misma disposición de tres cámaras que el comma 3, con sensores de imagen OX03C10 mejorados, HDR de 140 dB y, según suele indicarse, 128 GB de almacenamiento. |
| comma four | comma lo describe con el mismo procesador, los mismos sensores y las mismas funciones que el comma 3X, pero en un formato físico mucho más pequeño. El sistema de tres cámaras cabe en la huella de la pantalla de 1,9 pulgadas, con dos cámaras hacia la carretera y una cámara de habitáculo con visión nocturna. comma indica 128 GB de almacenamiento y 10 horas de imágenes. |

Las notas sobre archivos de aquí valen para los tres. CommaView en sí solo funciona con el comma 3X y el comma four.

En el openpilot actual, la organización práctica de archivos es la misma en todo el hardware de comma. Los archivos de segmento actuales son `fcamera.hevc`, `ecamera.hevc`, `dcamera.hevc`, `qcamera.ts`, `rlog.zst` y `qlog.zst`.

Es decir, las cámaras pueden cambiar físicamente mientras los nombres de exportación siguen siendo los de siempre. `fcamera.hevc` es la cámara de carretera. `ecamera.hevc` es la cámara de carretera gran angular. `dcamera.hevc` es la cámara del conductor/habitáculo.

Si usas un fork personalizado, compruébalo en el dispositivo antes de dar por hecho que están todos los archivos. Los forks pueden cambiar los ajustes de grabación, y la grabación del conductor/habitáculo puede depender de los ajustes del dispositivo.

## ¿Dónde se guardan los archivos en local?

En el hardware de comma, la raíz de registros actual de openpilot es:

```text
/data/media/0/realdata
```

Dentro de esa carpeta, cada segmento de ruta tiene su propia carpeta con fecha y hora, por ejemplo:

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

En esa carpeta es donde buscas archivos como:

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

Para trabajar directamente por SSH/SFTP, esta es la carpeta por la que empezar. La documentación oficial explica cómo conectarse a un comma 3X o un comma four por SSH, y openpilot usa `/data/media/0/realdata` como raíz de registros en el dispositivo.

## Opción 1: usar comma connect

Para los viajes recientes, comma connect suele ser el sitio más fácil para empezar.

Usa connect cuando:

- la ruta es reciente
- el dispositivo subió la ruta correctamente
- te basta con el vídeo de vista previa
- prefieres una interfaz web a SSH
- solo necesitas unos pocos clips o archivos

connect también es donde muchos usuarios identifican primero la ruta y los números de segmento que necesitan. El problema es la retención: connect puede dejar de mostrar una ruta antes de que el dispositivo la haya borrado. Si connect ya no muestra una ruta pero los archivos siguen en el dispositivo, puede que aún los recuperes por SSH/SFTP.

Recuerda también que las vistas previas de connect se basan en `qcamera.ts`. Si necesitas las imágenes de cámara a resolución completa, asegúrate de que se suben los archivos de vídeo completos o saca directamente los archivos HEVC en bruto.

## Opción 2: usar Openpilot Toolkit

Openpilot Toolkit es una herramienta de la comunidad que puede hacer menos penosa la exportación local. Incluye flujos para configurar SSH, explorar archivos, ver vídeos de viajes y exportarlos en bruto.

Usa Openpilot Toolkit cuando:

- quieres una interfaz gráfica
- no quieres escribir los comandos SSH a mano
- necesitas ayuda para configurar las claves
- usas Windows o Android
- quieres explorar y exportar las imágenes de una ruta de forma más directa

Para muchos usuarios es el mejor término medio: más control que connect y menos fricción que trabajar a mano en la terminal.

## Opción 3: usar SSH o SFTP directamente

El acceso directo por SSH/SFTP da el máximo control y la mínima ayuda.

En líneas generales, el acceso por SSH suele consistir en:

1. Crear o usar una cuenta de GitHub con claves SSH.
2. Activar SSH en los ajustes del comma.
3. Introducir tu usuario de GitHub en el comma para que pueda obtener tus claves públicas.
4. Conectarte como usuario `comma` en el puerto `22`.

Una vez conectado, explora o copia desde:

```text
/data/media/0/realdata
```

Usa el acceso directo cuando:

- necesitas los archivos `fcamera.hevc`, `ecamera.hevc` o `dcamera.hevc` en bruto
- connect no muestra el archivo que necesitas
- quieres archivar una ruta entera
- te manejas con clientes SFTP como FileZilla o WinSCP
- te manejas con `ssh`, `scp` o `rsync`

Los archivos `.hevc` en bruto suelen reproducirse en VLC. Si otra app necesita MP4, remuxa con ffmpeg en lugar de recodificar siempre que puedas.

## ¿Qué método usar?

Usa comma connect si el viaje es reciente y te basta con una revisión normal de la ruta.

Usa Openpilot Toolkit si quieres un flujo local más amable sin hacer a mano cada paso de SSH/SFTP.

Usa SSH o SFTP si necesitas archivos en bruto, archivos locales más antiguos, archivos completos de rutas o control directo sobre lo que se copia.

## Dónde encaja CommaView

CommaView es una app de Android, local primero, para transmitir la cámara del comma, con superposiciones, configuración del entorno de ejecución, grabaciones y reproducciones.

Se mueve en el mismo terreno del acceso local a la cámara, pero no es comma connect, ni Openpilot Toolkit, ni una dashcam tradicional. No debe usarse como ayuda a la conducción ni como único sistema de captura de pruebas en un vehículo.

CommaView funciona con el comma 3X y el comma four, con openpilot o un [fork compatible](/forks): sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 o carrotpilot. El comma 3 no es compatible: comma lo pasó a una versión de openpilot congelada y de soporte a largo plazo, de cuya pantalla CommaView no puede sacar su superposición ([por qué](/es#faq-comma-3)).

## Para saber más

- Documentación oficial de registro de openpilot: [Logging](https://docs.comma.ai/concepts/logs/)
- Documentación oficial de SSH de comma: [conectarse a un comma 3X o comma four](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect: [comma.ai/connect](https://comma.ai/connect)
- Wiki de openpilot: [Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma: [Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit: [página del proyecto](https://spektor56.github.io/OpenpilotToolkit/)
