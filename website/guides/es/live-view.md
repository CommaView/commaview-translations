---
title: "Mira tu comma en Live View"
description: "Abre Live View para ver en tu teléfono la cámara de carretera de tu comma y su pantalla de conducción, y conoce sus controles, Detalles y lo que dice cuando algo va mal."
topic: screens
order: 1
kind: walkthrough
lede: "**Live View** muestra en directo la cámara de carretera de tu comma, con la pantalla de conducción dibujada encima: la del comma four, la del comma 3X o la propia de CommaView. Llega directamente del comma por tu propia red, no por internet."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView está configurado"
    text: "CommaView en un teléfono Android, emparejado con tu comma. ¿Aún no? [Configurar CommaView](/es/guides/setup)."
  - title: "El coche está encendido"
    text: "openpilot solo envía vídeo en marcha. Con el coche apagado, Live View espera y empieza solo cuando arranca el coche."
  - title: "Una sola red"
    text: "Tu teléfono y tu comma en el mismo Wi‑Fi o punto de acceso. En el coche, consulta [Conectar en el coche](/es/guides/connect-in-the-car)."
steps:
  - id: open
    title: "Abre Live View desde Inicio"
    body: |
      En **Inicio**, con tu comma conectado y el coche encendido, toca **Abrir Live View**. La carretera aparece en unos segundos, con la píldora de la transmisión diciendo **En vivo**.
    screen: phone-home
    pins:
      - target: open-live-view
        text: "**Abrir Live View**, el botón principal de Inicio."
    note: "Con el coche apagado, Live View dice **Tu comma está conectado, pero no en marcha**. Empieza solo cuando arranca el coche, o al momento con **Actualizar**."
  - id: controls
    title: "Conoce los controles bajo la imagen"
    body: |
      Con el teléfono en vertical, los controles quedan bajo el vídeo:

      - **Grabar** guarda este tramo del viaje. Consulta [Grabar un viaje](/es/guides/record).
      - **Guardar** conserva los últimos 3 minutos y el minuto siguiente del viaje.
      - El selector de pantalla de conducción, con el nombre de la pantalla que muestra (**CommaView**, **comma 4**, **comma 3X**), pasa a la siguiente con cada toque. Consulta [Elegir la pantalla de conducción](/es/guides/overlays).
      - **Transmitir** emite lo que muestra Live View, una vez configurado. Consulta [Transmitir en vivo](/es/guides/go-live).
      - **Cámara int.** muestra la cámara del conductor en una esquina de la imagen.
      - **Detalles** abre los datos y las tarjetas de Live View.

      Lo que no cabe con el ancho y el tamaño de texto de tu teléfono va a **Más**. Nada se reduce ni se corta.
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**Grabar**."
      - target: onroad-screen-button
        text: "El selector de pantalla de conducción."
      - target: driver-cam-button
        text: "**Cámara int.**"
      - target: go-live-button
        text: "**Transmitir**, una vez configurada la transmisión en vivo."
      - text: "**Más** guarda lo que no cabe."
    note: "Mientras se graba, el selector de pantalla de conducción y **Cámara int.** aparecen atenuados: elígelos antes de tocar **Grabar**."
  - id: details
    title: "Abre Detalles"
    body: |
      Toca **Detalles**, o sube la hoja de la parte inferior de la pantalla. Muestra cómo va la transmisión, el vídeo, el entorno de ejecución, el software de tu comma y su dirección, si estás grabando o transmitiendo, y la tarjeta **Browser View**. Sus enlaces abren **Grabaciones** y los **Ajustes del dispositivo** de tu comma.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "La hoja **Detalles**."
      - text: "El resumen: el estado de la transmisión, el vídeo y el entorno de ejecución."
      - target: recordings-link
        text: "**Grabaciones**."
      - target: device-settings-link
        text: "**Ajustes del dispositivo** de este comma."
  - id: turn
    title: "Gira el teléfono o usa una pantalla más grande"
    body: |
      Pon el teléfono de lado y el vídeo ocupa la pantalla, con los controles en una barra en el lado del conductor. **Detalles** se abre junto a la imagen, y **Salir** cierra Live View.
    tabs:
      - label: "Teléfono de lado"
        body: "La barra tiene los mismos controles. En una pantalla baja se vuelve compacta."
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "**Grabar**, arriba de la barra."
          - target: more
            text: "**Más** contiene **Cámara int.** y **Detalles**."
          - target: exit
            text: "**Salir** cierra Live View."
      - label: "Tablet o pantalla del coche"
        body: "En una pantalla ancha, la barra se queda en el lado del conductor. Consulta [Usar CommaView en una pantalla del coche](/es/guides/car-screens)."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Grabar**."
          - target: onroad-screen-button
            text: "El selector de pantalla de conducción."
          - target: driver-cam-button
            text: "**Cámara int.**"
          - target: details
            text: "**Detalles**."
          - target: exit
            text: "**Salir**."
  - id: auto
    title: "Deja que Live View se abra solo"
    body: |
      Para un teléfono o una pantalla del coche que solo está ahí para mostrar Live View, abre **Ajustes › Pantalla** y activa **Abrir Live View al conectar**, en **Abriendo Live View**. Live View se abre solo cuando tu comma se conecta con el coche encendido. Si lo cierras, se queda cerrado hasta la próxima vez.

      **Mantener la barra de estado**, justo debajo, muestra el reloj del sistema sobre Live View en lugar de usar toda la pantalla.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Abrir Live View al conectar**."
  - id: leave
    title: "Sal de Live View cuando termines"
    body: |
      Toca **Salir**, o atrás, cuando hayas estacionado. Salir de Live View también termina Transmitir, Browser View y las copias en vivo. Live View está abierto en un solo teléfono o pantalla del coche a la vez, así que ciérralo en uno antes de abrirlo en otro.
check: "La píldora de la transmisión dice **En vivo**, la carretera se mueve y el estado de la transmisión en Detalles dice **Buena**."
fixes:
  - q: "«Tu comma está conectado, pero no en marcha»"
    a: "El coche está apagado u openpilot no ha arrancado. Live View vuelve solo en los 30 segundos siguientes al arranque del coche, o toca **Actualizar**."
  - q: "«No se puede alcanzar este comma»"
    a: "Tu teléfono debe estar en el mismo Wi‑Fi que el comma, o en su punto de acceso. Live View se reconecta cuando el comma responde, o toca **Reintentar**. ¿Sigue sin funcionar? Consulta [CommaView no encuentra tu comma](/es/guides/comma-not-found)."
  - q: "«Live View está abierto en otro dispositivo»"
    a: "Tu comma transmite a un solo teléfono o pantalla del coche a la vez. Vuelve a Inicio en CommaView en el otro, y Live View empieza aquí solo."
  - q: "«No llegan los datos del coche»"
    a: "Llega el vídeo, pero no la velocidad, los intermitentes ni las alertas del coche. Reinicia el comma para solucionarlo."
  - q: "«Vídeo con retraso»"
    a: "No ha llegado un fotograma nuevo en un segundo. Live View lo indica junto a la imagen y se reconecta solo si el vídeo no vuelve."
  - q: "«No se puede reproducir el vídeo de este comma»"
    a: "Ninguno de los decodificadores de vídeo del teléfono pudo reproducirlo. CommaView sigue intentándolo. Envía un informe de soporte desde Ajustes para que CommaView lo investigue: consulta [Enviar un informe de soporte](/es/guides/support-bundle)."
related: [overlays, record, browser-view, car-screens]
---

## Seguridad

Abre Live View estacionado y luego no lo toques. No manejes CommaView mientras conduces: mantén la vista en la carretera y las manos en el volante, como pide openpilot. Las alertas de tu comma y los instrumentos de tu coche van primero. CommaView solo muestra lo que ve el comma.
