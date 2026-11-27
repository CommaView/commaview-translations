---
title: "Grabar una copia en vivo de lo que muestra Live View"
description: "Una copia en vivo guarda en tu teléfono lo que muestra Live View mientras conduces, lista en Grabaciones en cuanto paras, sin el límite de 10 minutos. Nunca se sube."
topic: recordings
order: 2
kind: walkthrough
lede: "Una **copia en vivo** guarda en tu teléfono, mientras conduces, lo que muestra Live View: la carretera y su pantalla de conducción. Está lista en Grabaciones en cuanto paras: sin reproducción que crear y sin límite de 10 minutos. Las copias en vivo se quedan en tu teléfono y nunca se suben."
appVersion: "0.0.164"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funciona"
    text: "CommaView en tu teléfono, emparejado con tu comma. ¿Aún no? [Configurar CommaView](/es/guides/setup)."
  - title: "Espacio en tu teléfono"
    text: "Unos 1,4 GB por hora a 720p, o 2,3 GB por hora a 1080p. Una copia en vivo siempre deja 500 MB libres."
howItWorks:
  - title: "Live View"
    text: "Dibuja la carretera y la pantalla de conducción, como siempre."
    edge: "mientras conduces"
  - title: "Tu teléfono"
    text: "Codifica lo que dibuja Live View en un MP4, a 20 fotogramas por segundo."
  - title: "Grabaciones"
    text: "La copia está lista en cuanto paras."
steps:
  - id: choose
    title: "Elige Copia en vivo o Ambas"
    body: |
      Toca **Ajustes** y luego **Grabaciones**. En **Grabar en Live View**, elige qué crea Grabar. Se guarda en cuanto eliges.
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Grabar en Live View**: **Reproducción**, **Copia en vivo** o **Ambas**."
    tabs:
      - label: "Copia en vivo"
        body: |
          «Lo que muestra Live View, listo en cuanto paras. Sin reproducción que crear y sin límite de tiempo.»
      - label: "Ambas"
        body: |
          «Una copia en vivo al momento y la reproducción tras el viaje. La reproducción mantiene su límite de 10 minutos.» La reproducción se crea cuando estacionas, como muestra [Grabar un viaje](/es/guides/record).
  - id: quality
    title: "Elige su calidad y su sonido"
    body: |
      Con una copia en vivo elegida, la página añade sus filas. **Calidad de la copia en vivo** es **720p** hasta que elijas **1080p**. **Sonido** está desactivado salvo que elijas un micrófono: el del comma o el de este teléfono. Es el mismo Sonido que en Ajustes › Transmisión en vivo.
    screen: settings-recordings
    pins:
      - text: "**Calidad de la copia en vivo**: 720p (unos 1,4 GB por hora) o 1080p (unos 2,3 GB por hora)."
      - text: "**Sonido**: desactivado, el micrófono del comma o el de este teléfono."
    note: "Una copia en vivo muestra lo que muestra Live View, también la miniatura de la cámara del conductor mientras **Cámara int.** está activada. Desactiva Cámara int. en Live View para dejar fuera la cámara del conductor."
  - id: record
    title: "Toca Grabar en Live View"
    body: |
      Con el coche encendido y aún en P, abre **Live View** y toca **Grabar**. Corre su temporizador y **Detalles** dice **Grabando ·** y el tiempo, como en cualquier grabación. Toca Grabar de nuevo para detenerla.

      Sigue grabando mientras cambias de app o bloqueas el teléfono, con una notificación, **Grabando una copia en vivo**, que tiene su temporizador y **Detener**. Cerrar Live View la termina.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Grabar, con su temporizador. Tócalo de nuevo para detenerlo."
      - target: recording
        text: "**Grabando ·** el tiempo, en **Detalles**."
    warn: "Empieza a grabar antes de arrancar, o deja que lo haga un pasajero. No toques CommaView mientras conduces."
  - id: find
    title: "Encuéntrala en Grabaciones"
    body: |
      Abre **Grabaciones**. La copia lleva la marca **Copia en vivo**, bajo el día, con su duración y su tamaño. Durante un momento después de detenerla dice **Guardando la copia en vivo…** con lo que lleva; después se reproduce.

      Con **Ambas**, el viaje tiene dos filas: la copia en vivo y la reproducción, que espera a que la crees al estacionar.
    screen: phone-recordings
    pins:
      - target: live-copy-row
        text: "La fila marcada **Copia en vivo**."
      - text: "Con **Ambas**, la reproducción del viaje, en una fila propia."
  - id: watch
    title: "Mírala, compártela o elimínala"
    body: |
      Toca la copia para verla. Sus datos añaden **Versión** (**Copia en vivo**, o **Copia en vivo · también reproducción** con Ambas), **Calidad** y **Sonido**. **Acciones de la grabación** tiene **Compartir**, **Abrir en otra app**, **Seleccionar** y **Eliminar**.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Acciones de la grabación**: Compartir, Abrir en otra app, Seleccionar y Eliminar."
      - text: "**Pantalla completa**."
check: "La copia se reproduce en Grabaciones en cuanto se guarda, y la **Versión** de la vista de reproducción dice **Copia en vivo**."
fixes:
  - q: "«No hay espacio suficiente para una copia en vivo: siempre deja 500 MB libres en este teléfono. Elimina en Grabaciones los viajes que ya no necesites.»"
    a: "Elimina los viajes que ya no necesites, o elige otro almacenamiento en **Ajustes › Grabaciones › Almacenamiento**. La tarjeta Almacenamiento dice aproximadamente cuántas horas de copias en vivo caben."
  - q: "«Copia en vivo detenida: este teléfono está casi lleno. Está guardada en Grabaciones; siempre deja 500 MB libres.»"
    a: "Lo grabado se conserva. Libera espacio antes del próximo viaje."
  - q: "«Copia en vivo detenida: un minuto sin vídeo del comma. Lo grabado se guarda en Grabaciones.»"
    a: "El teléfono perdió el comma durante un minuto, así que la copia terminó. Comprueba que tu teléfono se queda en el Wi‑Fi o el punto de acceso del comma. Consulta [CommaView no encuentra tu comma](/es/guides/comma-not-found)."
  - q: "«Esta copia en vivo llegó a 3.5 GB, el máximo de un archivo: continúa en una nueva en Grabaciones.»"
    a: "No se pierde nada: el viaje continúa en una segunda copia en vivo, en su propia fila de Grabaciones."
  - q: "«La reproducción se detuvo en su límite de 10 minutos. La copia en vivo sigue grabando.»"
    a: "Con **Ambas**, solo la reproducción se detiene a los 10 minutos. La copia en vivo sigue hasta que la detengas."
  - q: "«Grabando solo una copia en vivo. La reproducción no pudo iniciarse: …»"
    a: "Con **Ambas**, la copia graba aunque la parte de la reproducción no pueda, por ejemplo mientras el comma necesita un reinicio o este teléfono no está emparejado con él. El mensaje dice por qué."
  - q: "La fila dice «Necesita 1,2 GB libres para guardar»"
    a: "Las partes de la copia se conservan hasta que haya espacio para unirlas en un solo vídeo. Elimina los viajes que ya no necesites y se guardará sola."
  - q: "Su dato **Guardada** dice «Recuperada tras cerrarse la app: puede faltar su último minuto»"
    a: "La app se cerró mientras grababa, así que la copia se montó con lo que se había escrito: todo salvo, como mucho, el último minuto."
  - q: "«CommaView solo puede seguir transmitiendo y grabando mientras está en pantalla: Android no le dejó ejecutarse en segundo plano.»"
    a: "Android impidió que CommaView funcionara en segundo plano. Mantén Live View en pantalla mientras grabas."
related: [record, export-share, go-live]
blogPost: commaview-0-0-164-carrotpilot-teslahw1-live-copies
---

## Copia en vivo o reproducción

| | Copia en vivo | Reproducción |
| --- | --- | --- |
| Qué muestra | Lo que mostró Live View, tal como lo mostró | El vídeo propio del comma, con la pantalla de conducción dibujada encima |
| Cuándo está lista | En cuanto paras | Después de estacionar y tocar **Crear reproducción** |
| Cuánto dura | Sin límite salvo el almacenamiento | Hasta 10 minutos por grabación |
| Imagen | 720p o 1080p, 20 fotogramas por segundo | La mejor imagen: **Balanced**, **High** o **Max** |

## Mientras transmites

Una copia en vivo y [Transmitir](/es/guides/go-live) comparten un mismo codificador. Una copia iniciada mientras transmites tiene la calidad de la transmisión. **Guardar cada transmisión en vivo**, en Ajustes › Grabaciones, conserva un MP4 de cada transmisión, tal como se envió, sin Grabar.

## Privacidad

Las copias en vivo se quedan en tu teléfono. Nunca se suben ni se comparten con los demás teléfonos emparejados con el comma. **Enviar a CommaView** envía los datos propios del comma de un viaje, nunca una copia en vivo. El sonido solo está en una copia si elegiste un micrófono, y la cámara del conductor solo mientras Cámara int. está activada.

## Seguridad

Elige tus ajustes e inicia Grabar estacionado. No manejes CommaView mientras conduces: mantén la vista en la carretera y las manos en el volante, como pide openpilot.
