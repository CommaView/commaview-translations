---
title: "Transmitir en vivo a YouTube u otro servidor"
description: "Transmite lo que muestra Live View, la carretera y su pantalla de conducción, a tu canal de YouTube o a cualquier servidor RTMP, a 720p o 1080p. Configúralo una vez y transmite desde Live View."
topic: screens
order: 5
kind: walkthrough
lede: "**Transmitir** emite lo que muestra Live View, la carretera y su pantalla de conducción, desde tu teléfono a tu canal de YouTube o a cualquier servidor RTMP, a 720p o 1080p. Configúralo una vez en Ajustes y luego inícialo desde Live View."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funciona"
    text: "CommaView en un teléfono Android, emparejado con tu comma. ¿Aún no? [Configurar CommaView](/es/guides/setup)."
  - title: "Un sitio al que transmitir"
    text: "Un canal de YouTube con el que iniciar sesión, o una clave de transmisión de YouTube Studio o de otro servidor RTMP."
  - title: "Internet en el teléfono"
    text: "Cuando el Wi‑Fi del comma no tiene internet, la transmisión usa los datos móviles de tu teléfono: unos 1,4 GB por hora a 720p."
howItWorks:
  - title: "Tu comma"
    text: "Envía Live View a tu teléfono, como siempre."
  - title: "Tu teléfono"
    text: "Transmite lo que dibuja Live View: 20 fotogramas por segundo, 720p o 1080p."
    edge: "internet"
  - title: "YouTube o tu servidor"
    text: "Lo muestra a quien dejes verlo."
steps:
  - id: settings
    title: "Abre Ajustes › Transmisión en vivo"
    body: |
      Abre **Ajustes** y toca **Transmisión en vivo**. Hasta que la configures, su fila dice **Configurar**.
    screen: support-settings
    pins:
      - target: live-streaming-row
        text: "**Transmisión en vivo**."
  - id: destination
    title: "Elige adónde transmitir"
    tabs:
      - label: "Iniciar sesión con YouTube"
        body: |
          Toca **Iniciar sesión con YouTube**. El inicio de sesión de Google se abre en tu navegador, donde eliges la cuenta y el canal. Con la sesión iniciada, Transmitir crea cada emisión en tu canal y YouTube la inicia solo: sin clave de transmisión y sin pulsar nada en YouTube Studio. La tarjeta **Destino** muestra entonces tu canal, **Sesión iniciada**.
        screen: settings-live-streaming
        pins:
          - target: destination-row
            text: "**Destino**: tu canal, con la sesión iniciada."
        note: "Las páginas de inicio de sesión de Google no aparecen en la imagen."
      - label: "Una clave de transmisión o un servidor"
        body: |
          Toca **Usar una clave de transmisión** (o **Configurar destino**), elige la **Plataforma**, **YouTube** u **Otro servidor**, y pega la clave de transmisión. Para YouTube: en YouTube Studio, Crear › Emitir en directo › Emisión, copia la clave de transmisión y activa ahí el inicio automático para que cada emisión empiece cuando llegue el vídeo. Para otro servidor, pega también su dirección `rtmp://` o `rtmps://`. Toca **Guardar destino**.
        screen: settings-live-streaming-destination
        pins:
          - target: platform
            text: "**Plataforma**."
          - target: stream-key
            text: "La clave de transmisión. Se guarda solo en este teléfono y solo se envía al servidor al que corresponde."
          - target: save
            text: "**Guardar destino**."
        note: "`rtmp://` envía tu clave de transmisión sin cifrar. Usa `rtmps://` si tu servidor lo ofrece."
  - id: choices
    title: "Revisa quién puede verla, la calidad y el sonido"
    body: |
      - **Quién puede verla** (con la sesión iniciada en YouTube): **Público**, **No listado** o **Privado**. Empieza en **No listado**. Con una clave de transmisión, elígelo en YouTube Studio. Quien la vea sabe por dónde conduces.
      - **Título y descripción** (con la sesión iniciada en YouTube): cómo se llama cada emisión, con fichas para la fecha, el coche y más.
      - **Calidad**: 720p o 1080p, con los datos móviles aproximados que usa cada una por hora.
      - **Sonido**: desactivado salvo que elijas el micrófono de tu comma o el de este teléfono. Se oye a todos en el coche, pasajeros incluidos. Solo va a tu transmisión y a tus copias en vivo, nunca a CommaView.

      **Antes de transmitir** lo resume todo: el uso de datos, la cámara del conductor y cuándo se detiene la transmisión.
    screen: settings-live-streaming
    pins:
      - text: "**Título y descripción**."
      - target: sound-row
        text: "**Sonido**."
  - id: go
    title: "Toca Transmitir en Live View"
    body: |
      Abre Live View y toca **Transmitir**. Dice **Iniciando…** y luego muestra cuánto tiempo llevas en vivo. Inícialo antes de salir y luego no lo toques.
    screen: phone-live-view
    pins:
      - target: go-live-button
        text: "**Transmitir**. Donde no cabe, está en **Más**."
    warn: "La transmisión muestra la cámara del conductor siempre que **Cámara int.** está activada, y **Cámara int.** dice entonces **En vivo**. Desactiva **Cámara int.** para dejar la cámara del conductor fuera de la transmisión."
  - id: share
    title: "Comparte el enlace para verla"
    body: |
      En **Detalles**, la fila de la transmisión dice **Transmitiendo** y cuánto tiempo, con la tasa que envía, los datos usados y la red. Con la sesión iniciada en YouTube, **Compartir enlace**, debajo, comparte el enlace `youtu.be` de tu emisión.
    screen: phone-live-view-go-live
    pins:
      - target: stop-live
        text: "**Transmitir**, en vivo, con su temporizador."
      - target: streaming
        text: "**Transmitiendo** y cuánto tiempo."
      - target: share-watch-link
        text: "**Compartir enlace**."
  - id: stop
    title: "Detén la transmisión cuando hayas estacionado"
    body: |
      Toca **Transmitir** de nuevo para detenerla. La transmisión también se detiene al salir de Live View, con **Detener** en su notificación, y sola un minuto después de que se detenga su vídeo. Sigue cuando cambias de app o bloqueas el teléfono.
check: "**Transmitir** en Live View muestra un temporizador en marcha con los colores de en vivo, Detalles dice **Transmitiendo** y tu emisión se reproduce en YouTube o en tu servidor."
fixes:
  - q: "No hay Transmitir en Live View"
    a: "La transmisión en vivo aún no está configurada: Detalles dice **Configura la transmisión en vivo en Ajustes para transmitir desde aquí**. O está en **Más**, donde no caben todos los controles."
  - q: "«Añade tu clave de transmisión en Ajustes › Transmisión en vivo»"
    a: "Transmitir no tiene adónde emitir. Inicia sesión con YouTube, o añade una clave de transmisión, en **Ajustes › Transmisión en vivo**."
  - q: "La emisión de YouTube no empieza con una clave de transmisión"
    a: "Con una clave de transmisión, inicia cada emisión con Emitir en directo en YouTube Studio, o activa ahí el inicio automático. Con la sesión iniciada con YouTube, empieza sola."
  - q: "«Esa clave tiene un espacio»"
    a: "Vuelve a copiar la clave de tu servicio de streaming y pégala."
  - q: "«Sin sonido: Browser View funciona sin él»"
    a: "Transmitir comparte la imagen de Browser View, que no tiene sonido. Detén Browser View antes de transmitir para tener sonido. Lo mismo vale para una grabación que empezó sin sonido."
  - q: "La transmisión se detiene sola"
    a: "Live View siempre dice por qué en un mensaje. Una transmisión también se detiene un minuto después de que se detenga su vídeo, y cuando sales de Live View."
related: [live-view, browser-view, live-copy]
blogPost: commaview-0-0-165-go-live-send-to-commaview
---

## Guarda una copia de cada transmisión

**Ajustes › Grabaciones › Guardar cada transmisión en vivo** guarda en Grabaciones un MP4 de cada transmisión, tal como se envió, con la calidad de la transmisión. Se queda en tu teléfono. Consulta [Guardar una copia en vivo](/es/guides/live-copy).

## Qué hay en la transmisión y qué no

- **Incluye:** la carretera y la pantalla de conducción dibujada encima, y la cámara del conductor mientras **Cámara int.** está activada.
- **No incluye:** los controles de Live View, Detalles ni los mensajes. El mapa de navegación solo con **Mapa en la transmisión** activado, donde Ajustes lo ofrece, y solo el mapa de la esquina de CommaView.
- Grabar y Transmitir son independientes: puedes grabar y transmitir un viaje a la vez.

## Seguridad

Configura e inicia Transmitir estacionado y luego no lo toques. No manejes CommaView mientras conduces: mantén la vista en la carretera y las manos en el volante, como pide openpilot. Quien te vea sabe por dónde conduces.
