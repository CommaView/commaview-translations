---
title: "Compartir y exportar grabaciones"
description: "Comparte una reproducción o una copia en vivo desde Grabaciones, ábrela en otra app o exporta un viaje completo de tu comma como un solo MP4 en tu teléfono."
topic: recordings
order: 3
kind: walkthrough
lede: "Cada grabación en tu teléfono es un MP4 que puedes compartir, guardar en tus archivos o abrir en otra app, desde su menú **Acciones de la grabación** en Grabaciones. **Exportar el viaje completo…** también copia de tu comma a tu teléfono el vídeo de carretera de un viaje entero, tal como lo grabó el comma."
parked: true
updated: 2026-11-27
needs:
  - title: "Una grabación en tu teléfono"
    text: "Una reproducción o una copia en vivo en Grabaciones. ¿Aún no? [Grabar un viaje](/es/guides/record) o [grabar una copia en vivo](/es/guides/live-copy)."
  - title: "Para un viaje completo"
    text: "El comma que lo grabó, emparejado con este teléfono, estacionado y al alcance, y un entorno de ejecución que enumere sus viajes."
steps:
  - id: open
    title: "Abre la grabación"
    body: |
      Abre **Grabaciones** desde la barra inferior (la barra lateral en una pantalla más grande) y toca el viaje. Se abre en la vista de reproducción, con su reproductor y sus datos.
    screen: phone-recordings
    pins:
      - text: "Una reproducción. Toca cualquier viaje para abrirlo."
      - target: live-copy-row
        text: "Una copia en vivo, marcada **Copia en vivo**."
      - target: filter
        text: "**Filtrar**: **Listos** muestra solo los viajes con un vídeo que compartir."
  - id: actions
    title: "Abre Acciones de la grabación"
    body: |
      En la vista de reproducción, toca **Acciones de la grabación**, el botón Más junto a la hora y la fecha.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Acciones de la grabación**."
      - text: "**Pantalla completa** la reproduce en toda la pantalla."
  - id: share
    title: "Compártela o ábrela en otra app"
    body: |
      **Compartir** pasa el vídeo al menú para compartir de Android, donde puedes enviarlo o guardarlo en tus archivos. **Abrir en otra app** lo reproduce en otro reproductor de vídeo.

      **Archivos**, cuando un viaje tiene varios, muestra cada archivo para compartirlo por separado, como cada parte de un viaje completo largo.
    screen: recordings-watch-menu
    pins:
      - target: share
        text: "**Compartir**: el menú para compartir de Android."
      - target: open-in
        text: "**Abrir en otra app**."
      - target: send
        text: "**Enviar a CommaView…** envía en cambio a CommaView un problema con este viaje: [Enviar un paquete de soporte](/es/guides/support-bundle)."
    note: "El menú para compartir de Android no aparece en la imagen: es de Android y se ve distinto en cada teléfono."
    warn: "Un vídeo puede mostrar más que la carretera: dónde y cuándo condujiste, matrículas, caras y lugares, y la cámara del conductor en una copia en vivo hecha con Cámara int. activada. Revísalo antes de compartirlo."
  - id: export
    title: "Exporta un viaje completo"
    body: |
      Para un viaje que grabó tu comma, **Acciones de la grabación** tiene **Exportar el viaje completo…**. Copia la cámara de carretera del comma de todo el viaje en un solo MP4 en tu teléfono, exactamente como la grabó el comma. No tiene HUD: **Crear reproducción** dibuja la pantalla de conducción sobre las partes que grabaste.
    screen: recordings-watch-menu
    pins:
      - target: export-drive
        text: "**Exportar el viaje completo…**"
  - id: export-sheet
    title: "Comprueba el tamaño y toca Exportar"
    body: |
      La hoja dice cuánto del viaje tiene el comma, como **23 min · unos 1,7 GB**, y lo que hay libre en tu teléfono. Toca **Exportar**: «Exportando el viaje completo. Se guarda en Grabaciones cuando el comma esté estacionado.»

      No se descarga nada hasta que tocas Exportar. A partir de ahí el comma conserva el viaje mientras se copia; hasta entonces aún puede eliminarlo para hacer sitio, empezando por los viajes más antiguos.
    screen: recordings-export
    pins:
      - target: export
        text: "**Exportar**."
      - target: cancel
        text: "**Cancelar** lo deja."
  - id: whole-drive
    title: "Encuentra el viaje completo en Grabaciones"
    body: |
      La exportación es una fila propia, **Viaje completo**, junto a la grabación desde la que la pediste. Mientras espera dice por qué, como **Esperando a que estaciones**, y luego **Guardando desde el comma** con lo que lleva. Una vez guardada, se reproduce y se comparte como cualquier grabación.
    screen: phone-recordings
    pins:
      - text: "La fila **Viaje completo**, con el título de cuándo empezó el viaje."
    note: "Un viaje de más de unos 45 minutos de vídeo de carretera se guarda en partes de 3,5 GB: **Archivos** muestra cada una."
check: "Se abre el menú para compartir de Android con el vídeo. Para un viaje completo, su fila se reproduce y el dato **Guardado** de la vista de reproducción dice **El viaje completo · en este teléfono**."
fixes:
  - q: "**Exportar el viaje completo…** no está en el menú"
    a: "Se ofrece para un viaje que grabó tu comma, mientras ese comma está emparejado con este teléfono y su entorno de ejecución enumera sus viajes. [Actualiza el entorno de ejecución del comma](/es/guides/update-runtime) si es anterior. Una copia en vivo no tiene un viaje del comma que exportar."
  - q: "**Exportar el viaje completo…** aparece en gris: «Ya exportado», «Exportándose» o «Su copia se detuvo: Reintentar guardar en su fila»"
    a: "El viaje ya se exportó, o su exportación está en curso. Si se detuvo, abre la fila **Viaje completo** y elige **Reintentar guardar** en su menú."
  - q: "«El comma no tiene este viaje, así que no se puede exportar.»"
    a: "El comma lo eliminó para hacer sitio a viajes más nuevos. Nada puede recuperarlo."
  - q: "«Este viaje es anterior a los 50 que lista el comma, así que no se puede encontrar para copiarlo.»"
    a: "Tu comma enumera sus 50 viajes más recientes, y este es más antiguo, así que la exportación no lo encuentra."
  - q: "«Necesita unos 2,2 GB libres. Libera espacio primero.»"
    a: "Elimina los viajes que ya no necesites, o elige otro almacenamiento en **Ajustes › Grabaciones**, y vuelve a abrir la hoja."
  - q: "El viaje completo dice «Esperando a que estaciones», «Esperando a alcanzar el comma» o «Esperando mientras Live View está abierto»"
    a: "Solo se copia mientras el comma está estacionado, al alcance de tu teléfono y sin mostrar Live View. Continúa solo en cuanto puede."
  - q: "«No se encontró ningún reproductor de vídeo»"
    a: "No hay otra app de vídeo en este dispositivo para **Abrir en otra app**. Reprodúcelo en Grabaciones, o usa **Compartir** para guardarlo en tus archivos."
  - q: "«Esta reproducción no se puede reproducir aquí. Prueba con otra app.»"
    a: "Usa **Abrir en otra app**, o compártela con una app que la reproduzca."
related: [record, live-copy, support-bundle]
---

## Compartir varias a la vez

Mantén pulsado un viaje para seleccionarlo y toca otros para añadirlos. La barra inferior dice cuántos hay seleccionados. Su menú **Más** tiene **Compartir**, que pasa todos los vídeos seleccionados juntos al menú para compartir de Android, y la barra tiene **Eliminar**. Un viaje que aún no tiene vídeo en tu teléfono queda fuera, y la acción dice cuántos incluye.

## Traer viajes nuevos automáticamente

**Ajustes › Grabaciones › Traer viajes nuevos** trae a casa la cámara de carretera de cada viaje nuevo sin tocar nada: más o menos cada media hora, mientras tu teléfono y tu comma están en un Wi‑Fi que elijas en **Redes Wi‑Fi** y el coche está estacionado. Cada viaje traído es una fila **Del comma** en Grabaciones, sin HUD, como un viaje completo. **Espacio para viajes traídos** limita el espacio que ocupan: 10, 20 o 50 GB, o **Sin límite**. Nunca se eliminan para hacer sitio.

## Adónde van

Los archivos compartidos solo van adonde los envías. Las grabaciones se quedan en tu teléfono, y la copia de seguridad de Android y el paso a un teléfono nuevo las dejan fuera.
