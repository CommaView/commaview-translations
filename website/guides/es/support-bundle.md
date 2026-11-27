---
title: "Enviar un paquete de soporte"
description: "Deja el diagnóstico activado, haz que el problema vuelva a ocurrir y envía un informe con los registros de tu teléfono y de tu comma desde Ajustes › Soporte y diagnóstico."
topic: troubleshooting
order: 3
kind: walkthrough
lede: "Un paquete de soporte es un pequeño zip con lo que vio la app CommaView en tu teléfono y lo que vio su entorno de ejecución en tu comma. Nos permite encontrar un problema sin estar en tu coche. Solo contiene registros: ni vídeo ni ubicación."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Diagnóstico activado"
    text: "**Guardar diagnóstico en este teléfono**, activado salvo que alguien lo haya desactivado. Compruébalo antes de que el problema vuelva a ocurrir."
  - title: "Conectado a tu comma"
    text: "Para los registros de tu comma, Inicio muestra tu comma **Conectado** cuando envías."
  - title: "Sesión iniciada para enviar"
    text: "Enviar necesita tu cuenta de la beta. Sin la sesión iniciada, **Guardar como archivo** sigue funcionando."
howItWorks:
  - title: "Tu teléfono"
    text: "Guarda sus registros y contadores de tus últimos 10 viajes."
  - title: "Tu comma"
    text: "Añade los registros de su entorno cuando tocas Enviar, sin ubicación, VIN, identificadores, nombres de Wi‑Fi ni tokens."
    edge: "cuando tocas Enviar"
  - title: "El equipo de CommaView"
    text: "Lo lee en un almacenamiento privado y responde por correo."
steps:
  - id: open
    title: "Abre Soporte y diagnóstico"
    body: |
      En CommaView, toca **Ajustes** en la barra inferior. En una tablet o una pantalla del coche está en la barra lateral. Toca **Soporte y diagnóstico**, casi al final, antes de Acerca de.
    screen: support-settings
    pins:
      - text: "**Soporte y diagnóstico**."
  - id: keep-diagnostics
    title: "Guarda el diagnóstico en este teléfono"
    body: |
      **Guardar diagnóstico en este teléfono** está activado salvo que alguien lo haya desactivado: la app guarda sus registros y contadores de tus últimos 10 viajes, para que un informe pueda decir qué pasó. Si está desactivado, actívalo y haz que el problema vuelva a ocurrir.
    screen: support-diagnostics
    pins:
      - target: keep-diagnostics
        text: "**Guardar diagnóstico en este teléfono**."
    note: "El diagnóstico se queda en este teléfono hasta que envías un informe: nunca se sube automáticamente."
  - id: happen-again
    title: "Haz que vuelva a ocurrir, estacionado"
    body: |
      Conéctate a tu comma como siempre: tu teléfono en el Wi‑Fi o el punto de acceso del comma, e Inicio mostrando tu comma **Conectado**. Haz lo que salió mal; por ejemplo, abre Live View, cambia a la pantalla de conducción que falla y déjala ahí entre 10 y 20 segundos. Apunta más o menos cuándo pasó y qué hiciste. Una grabación de pantalla también ayuda.
    warn: "Haz que ocurra en P. Si solo pasa en carretera, deja que pase y envía el informe cuando hayas estacionado: el registro te espera. Nunca toques la app mientras conduces."
  - id: open-send
    title: "Abre Enviar a CommaView"
    body: |
      En **Soporte y diagnóstico**, toca **Informar de un problema o enviar una idea**.

      O empieza desde el problema: donde la app muestra un fallo, toca su **Informar**; para una grabación, elige **Enviar a CommaView…** en sus **Acciones de la grabación**. Cada uno abre la misma hoja, con lo relevante ya rellenado.
    screen: support-diagnostics
    pins:
      - target: report
        text: "**Informar de un problema o enviar una idea**."
  - id: send
    title: "Elige qué se envía y envía"
    body: |
      Elige **Problema** y cuenta qué pasó. En **Adjuntos**, deja activados **Este teléfono: diagnóstico** y los registros de tu comma. **Ver** muestra exactamente qué contiene cada uno. Bajo las filas, la hoja enumera lo que va con cada informe: la versión de la app, el modelo de tu teléfono y su versión de Android, y el software de conducción y la configuración de tu comma.

      Toca **Enviar**: «Enviando. Se envía en segundo plano y espera a tener conexión.»
    screen: support-send-feedback
    pins:
      - target: problem
        text: "**Problema** o **Idea**."
      - text: "**Adjuntos**: cada fila tiene un interruptor y **Ver**."
      - target: send
        text: "**Enviar**."
    note: "Envía mientras la app está conectada a tu comma: pide al comma sus registros cuando tocas Enviar. Si el comma está apagado o fuera de alcance, el paquete dice por qué y aun así contiene los registros propios de la app."
  - id: save-file
    title: "O guárdalo como archivo"
    body: |
      ¿Soporte te pidió el archivo en sí, o no has iniciado sesión? Toca **Guardar como archivo** en lugar de Enviar. La app crea el mismo paquete, un pequeño `.zip`, y abre el menú para compartir de Android. Envíalo adonde te pidió soporte: un mensaje directo en Discord, un correo o un enlace a una nube.
    screen: support-share-bug-report
    pins:
      - target: save-file
        text: "**Guardar como archivo**."
  - id: afterwards
    title: "Lee nuestra respuesta"
    body: |
      Cuando respondemos, la respuesta llega por correo y está en [Your feedback](https://my.commaview.com/feedback) en my.commaview.com junto a tu informe. Contéstanos ahí hasta que lo cerremos; puedes reabrirlo durante 30 días después. **Tus solicitudes**, en **Soporte y diagnóstico**, también las enumera.
    screen: support-diagnostics
    pins:
      - target: your-requests
        text: "**Tus solicitudes**: las respuestas y tus conversaciones con CommaView."
check: "La hoja se cierra con «Enviando. Se envía en segundo plano y espera a tener conexión.», y el informe aparece en **Tus solicitudes** una vez enviado."
fixes:
  - q: "El paquete no tiene registros del comma"
    a: "La app no pudo alcanzar tu comma cuando tocaste Enviar, o su fila en **Adjuntos** estaba desactivada. Comprueba que Inicio muestra tu comma **Conectado** antes de abrir Enviar a CommaView, y deja activada la fila de tu comma. Si la app te pide volver a emparejar tu comma, emparéjalo primero y vuelve a enviar."
  - q: "Enviar dice **Inicia sesión para enviar**"
    a: "No has iniciado sesión. Tócalo para iniciar sesión con tu cuenta de la beta, o usa **Guardar como archivo**."
  - q: "«Los adjuntos superan los 25 MB que admite un informe. Desactiva uno o usa Guardar como archivo.»"
    a: "Desactiva un adjunto que no necesites, o toca **Guardar como archivo** y envía el archivo adonde te pida soporte."
  - q: "No pasa nada al tocar Guardar como archivo"
    a: "Android no tiene en este dispositivo ninguna app que acepte un archivo. Es habitual en las pantallas del coche. [Envíalo](#step-send) a CommaView en su lugar, o guárdalo desde un teléfono con CommaView."
  - q: "«No se pudo preparar el informe. Revisa el almacenamiento local y vuelve a intentarlo.»"
    a: "La app no pudo escribir el paquete, normalmente porque al dispositivo le falta almacenamiento. Libera espacio y vuelve a intentarlo."
related: [setup-troubleshooting, comma-not-found, releases]
---

## Qué hay en un paquete de soporte

- **El diagnóstico de este teléfono.** Los registros y contadores de diagnóstico de CommaView en este teléfono: la transmisión de vídeo, el dibujo, la conexión y los errores de grabación, con la versión de la app y el modelo del teléfono y su versión de Android. Con Navegación, también cuántas búsquedas de lugares de cada tipo funcionaron o fallaron, nunca qué buscaste.
- **Los registros de tu comma.** Con la fila de tu comma activada: los registros, contadores y ajustes del entorno de ejecución de CommaView, qué procesos de openpilot se detuvieron y por qué, y las líneas de falta de memoria del kernel del comma.
- **Nunca en un paquete.** Ni vídeo, ni ubicación GPS, ni VIN, ni telemetría de conducción sin procesar: una grabación que envías va junto al paquete, no dentro. Un entorno de ejecución del comma al día quita las coordenadas GPS, los VIN, los nombres de Wi‑Fi, las direcciones IP públicas, los tokens y el ID completo del dongle antes de enviar sus registros.
- **Solo cuando envías.** Un paquete solo sale de tu teléfono cuando tocas Enviar o Guardar como archivo. Un archivo que guardas solo va adonde lo envías. Pueden quedar direcciones IP locales, identificadores de sesión y detalles de versiones, así que comparte un paquete solo con personas de confianza.

## Adónde va y durante cuánto tiempo

Un paquete que envías va al almacenamiento privado de CommaView, donde solo lo abre el equipo de CommaView. Se elimina 180 días después de enviarlo, o antes, al momento, cuando nos lo pides o eliminas tu cuenta ([Privacidad](/privacy)). Para pedirlo, escribe a support@commaview.com.

Para quitar lo que la app guarda en este teléfono, toca **Borrar datos de diagnóstico locales** en **Soporte y diagnóstico**. Nunca elimina tus grabaciones. Para guardar desde entonces solo el historial de errores de grabación, desactiva **Guardar diagnóstico en este teléfono** en la misma página.

¿No sabes adónde enviarlo? Pregunta en el [Discord de CommaView](https://discord.gg/UuMhz9K8ft).
