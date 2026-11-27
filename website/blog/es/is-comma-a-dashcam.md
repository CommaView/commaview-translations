---
title: "¿Es un comma una dashcam? Útil, pero no un sustituto"
description: "Una mirada prudente a las imágenes del comma tras openpilot 0.11.2: archivos de ruta, retención y clips de connect, almacenamiento local, accidentes, modo aparcamiento y dashcams."
date: 2026-11-06
slug: is-comma-a-dashcam
tags:
  - comma dashcam
  - comma device video
  - dashcam footage
  - openpilot
heroLabel: "La verdad sobre la dashcam"
draft: false
---

Un comma puede grabar imágenes útiles de la carretera y del habitáculo. Eso no lo convierte en un sustituto directo de una dashcam dedicada.

Las imágenes pueden ayudar a revisar rutas, depurar, exportar y dar contexto a un incidente. Pero una dashcam dedicada parte de otras premisas: capturar pruebas que resistan un accidente, almacenamiento extraíble sencillo, modo aparcamiento, cámara trasera y una recuperación tan simple como la de un electrodoméstico.

Si te importan unas imágenes fiables para un accidente o para el seguro, usa una dashcam dedicada junto al comma. Respuesta aburrida, respuesta correcta.

## Qué graba un comma

openpilot graba rutas mientras el dispositivo funciona. La documentación actual sobre el registro describe las rutas en segmentos, con archivos de cámara y de registro como:

- `fcamera.hevc`: vídeo de la cámara de carretera
- `ecamera.hevc`: vídeo de la cámara de carretera gran angular
- `dcamera.hevc`: vídeo de la cámara del conductor/habitáculo
- `qcamera.ts`: vídeo de vista previa a menor resolución
- `rlog.zst`: registro completo de la ruta
- `qlog.zst`: registro reducido de la ruta

Son datos muy útiles.

Pero no son un simple «clip de dashcam». Es el registro de rutas de openpilot: archivos segmentados, ID de ruta, comportamiento de subida, retención local, códecs, registros y herramientas.

## Dónde puede haber imágenes

Hay dos sitios donde la gente suele mirar primero:

1. **comma connect**, para viajes recientes visibles en la nube.
2. **el almacenamiento local del dispositivo**, para archivos que aún existen en el comma.

La [página de prime](https://comma.ai/prime) de comma dice que los viajes subidos se guardan en connect durante 3 días, o 1 año con comma prime. Por defecto, connect muestra el vídeo `qcamera` de menor resolución ([la documentación de registros de comma](https://docs.comma.ai/concepts/logs/)).

Desde [openpilot 0.11.2](https://blog.comma.ai/0112release/) (octubre de 2026), connect también puede cortar un clip de una parte de un viaje: el comma lo recodifica como MP4 mientras sigue encendido, y tú lo descargas de connect. Eso hace mucho más fácil que antes conseguir un clip para compartir.

El almacenamiento local de openpilot es otra cosa. En el hardware actual de comma, la zona práctica de datos de ruta está en `/data/media/0/realdata/`. Pero el almacenamiento local no es infinito. openpilot limpia cuando queda poco espacio, así que las rutas antiguas no son un archivo permanente.

Si algo importa, consérvalo cuanto antes.

## Por qué la gente sigue usando las imágenes del comma

Las imágenes del comma pueden ser realmente útiles.

Buenos usos:

- revisar qué pasó en una ruta
- depurar el comportamiento de openpilot
- comprobar el contexto de cámara y registros
- exportar clips o archivos HEVC en bruto
- compartir ejemplos para desarrollo o soporte
- alimentar flujos de reproducción y pruebas

Si ya tienes un comma, ignorar esas imágenes sería absurdo. Tienen valor.

El error es suponer que «valioso» significa «el mismo trabajo que una dashcam dedicada».

## Por qué no sustituye a una dashcam dedicada

Una dashcam dedicada suele estar pensada, ante todo, para capturar pruebas.

Eso suele significar almacenamiento sencillo, recuperación rápida, modos de aparcamiento, opciones de cámara trasera o interior, funcionamiento independiente y flujos pensados para conservar clips después de un incidente.

Un comma está hecho para ejecutar openpilot. Los datos de cámara existen porque openpilot necesita registro, desarrollo de modelos, depuración, revisión de rutas y las vistas previas de connect.

Esas prioridades se solapan con las de una dashcam, pero no son idénticas.

## Los puntos de riesgo

### Resistencia a accidentes y cortes de corriente

Si el dispositivo pierde la corriente, se daña o se apaga en mal momento, las imágenes recientes pueden ser más difíciles de recuperar o no estar completas.

Eso no significa que las imágenes del comma no sirvan en ningún incidente. Significa que no deberían ser tu único plan para tener pruebas.

### Modo aparcamiento

Las dashcams dedicadas suelen vender el modo aparcamiento con kit de cableado como función principal.

openpilot 0.11.2 permite transmitir en directo en connect las cámaras de carretera y del conductor de un coche aparcado, con conexión a internet y un comma power instalado. La entrada de comma lo describe como una forma de ver qué pasa alrededor del coche; no lo presenta como un grabador de incidentes en modo aparcamiento.

Considera la vigilancia del coche aparcado terreno de las dashcams dedicadas, salvo que tengas una configuración muy concreta y validada y entiendas los riesgos.

### Cobertura trasera

Las cámaras de carretera, gran angular y del conductor/habitáculo del comma no equivalen a una dashcam trasera.

Si te importa cubrir la parte trasera, usa hardware que grabe hacia atrás.

### Fricción al almacenar y exportar

Una dashcam suele buscar una recuperación de clips sencilla desde la microSD, una app o una pantalla.

Recuperar imágenes del comma puede implicar ventanas de visibilidad de connect, subidas manuales, ID de segmento, SSH/SFTP, archivos HEVC, limpieza local, VLC/ffmpeg/remuxing o herramientas auxiliares. Los nuevos clips de connect ayudan, pero el comma tiene que seguir encendido mientras hace uno, y el viaje tiene que seguir ahí.

Eso está bien para usuarios técnicos. No es tan sencillo como un electrodoméstico.

## Cuándo pueden bastar las imágenes del comma

Las imágenes del comma pueden bastar para:

- tener una referencia informal de la carretera
- revisar rutas de openpilot
- depurar y probar
- dar soporte al desarrollo
- exportar en local cuando la ruta todavía existe
- revisar un incidente poco después de que ocurra

Es una lista sólida.

Aun así, no convierte al comma en tu único grabador serio de pruebas.

## Cuándo añadir una dashcam

Usa una dashcam dedicada si te importa:

- tener imágenes fiables para un accidente o para el seguro
- vigilar el coche aparcado
- cubrir la parte trasera
- recuperar las imágenes de la forma más fácil posible
- tener almacenamiento extraíble
- grabar de forma independiente si el comma pierde la corriente
- una herramienta más sencilla para conductores no técnicos

La combinación no tiene nada de raro. Un comma puede ser genial para openpilot mientras una dashcam se encarga de la aburrida tarea de capturar pruebas.

## Dónde encaja CommaView

CommaView es una app de Android y un pequeño entorno de ejecución en el comma. Muestra en vivo la cámara de carretera del comma con la superposición de conducción de tu fork en tu teléfono, tablet o pantalla del coche Android, por tu propia red, y guarda en tu teléfono lo que grabas. Toca **Grabar** en Live View y, cuando aparques, descarga el vídeo del propio comma de ese tramo, hasta 10 minutos, y dibuja la superposición encima; o guarda una copia en vivo de lo que muestra Live View, sin límite de 10 minutos. No se sube nada, y las grabaciones se quedan en tu teléfono hasta que las eliminas. Graba cuando tocas **Grabar**, no por sí sola, así que no sirve de nada ante un incidente que no viste venir.

Eso hace mucho más fácil conseguir un clip de lo que viste. No convierte un comma en una dashcam crítica para la seguridad.

No garantiza que se conserven las pruebas.

No es una ayuda a la conducción.

Y solo funciona con el comma 3X y el comma four, no con el comma 3. CommaView no es oficial ni está afiliado a comma.ai, ni cuenta con su respaldo.

## Lista práctica después de un incidente

No es asesoramiento legal, solo un triaje práctico:

1. Deja de conducir y atiende primero la seguridad y las emergencias.
2. No confíes solo en la retención de connect.
3. Conserva o exporta los segmentos de ruta relevantes en cuanto puedas.
4. Si usas connect, identifica la ruta y la franja horaria que necesitas.
5. Si connect no muestra los archivos pero el dispositivo aún los tiene, usa SSH/SFTP autorizado por el propietario o una herramienta local de confianza.
6. Conserva los archivos originales siempre que puedas.
7. Evita ediciones destructivas o limpiezas hasta haber copiado las imágenes importantes.
8. Para asuntos legales o de seguros, habla con los profesionales adecuados.

Lo principal: actúa rápido, copia con cuidado y no des por hecho que las imágenes te van a esperar para siempre.

## La respuesta honesta

Un comma es una cámara y un grabador de datos útil para las rutas de openpilot. Puede aportar un contexto en vídeo valioso.

Pero si la pregunta es «¿puedo prescindir de una dashcam?», la respuesta prudente es no.

Usa las imágenes del comma para revisar rutas, depurar y trabajar en local. Usa una dashcam dedicada cuando lo que necesitas es capturar pruebas de forma fiable.
