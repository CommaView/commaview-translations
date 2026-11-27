---
title: "Grabar un viaje desde Live View"
description: "Toca Grabar en Live View y crea la reproducción del viaje al estacionar: el vídeo propio del comma con la pantalla de tu fork dibujada encima, guardado en tu teléfono."
topic: recordings
order: 1
kind: walkthrough
lede: "**Grabar** en Live View guarda un viaje. Salvo que elijas otra cosa, crea una **reproducción**: cuando estacionas, CommaView descarga el vídeo propio del comma de lo que grabaste, hasta 10 minutos, y dibuja encima la pantalla de conducción en tu teléfono. No se sube nada: las grabaciones se quedan en tu teléfono hasta que las eliminas."
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funciona"
    text: "CommaView en tu teléfono, emparejado con tu comma. ¿Aún no? [Configurar CommaView](/es/guides/setup) y luego [abrir Live View](/es/guides/live-view)."
  - title: "El coche encendido"
    text: "Grabar empieza cuando el comma ha iniciado un viaje, así que enciende primero el coche. Empieza a grabar en P, antes de arrancar."
  - title: "Espacio en tu teléfono"
    text: "La reproducción se crea en tu teléfono a partir del vídeo del comma. Ajustes › Grabaciones muestra el almacenamiento que usa y lo que queda libre."
howItWorks:
  - title: "Grabar en Live View"
    text: "Abre la ventana de captura del comma: guarda los datos de la pantalla de conducción mientras grabas."
    edge: "al estacionar"
  - title: "Crear reproducción"
    text: "El teléfono descarga el vídeo del comma de ese tramo, un viaje cada vez."
  - title: "Grabaciones"
    text: "La reproducción se ve en tu teléfono, con la pantalla dibujada sobre el vídeo."
steps:
  - id: choose
    title: "Elige qué crea Grabar"
    body: |
      Toca **Ajustes** y luego **Grabaciones**. En **Grabar en Live View**, **Reproducción** está elegida hasta que la cambies: «La mejor imagen: el vídeo propio del comma con el HUD dibujado encima, creada cuando estacionas. Hasta 10 minutos por grabación.»

      **Copia en vivo** guarda en su lugar lo que muestra Live View, sin límite de tiempo, y **Ambas** crea las dos. Tienen [su propia guía](/es/guides/live-copy).
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Grabar en Live View**: **Reproducción**, **Copia en vivo** o **Ambas**."
      - text: "**Reproducción** abre su calidad: **Balanced**, **High** o **Max**. Más calidad tarda más en crearse y genera archivos más grandes."
  - id: start
    title: "Toca Grabar en Live View"
    body: |
      Con el coche encendido y aún en P, abre **Live View** y toca **Grabar**. Durante un momento dice **Iniciando…** mientras CommaView se sincroniza con el viaje, y luego corre su temporizador.
    screen: phone-live-view
    clip: record
    pins:
      - target: record-button
        text: "**Grabar**. En una tablet, una pantalla del coche o un teléfono de lado, está en la barra."
    warn: "Empieza a grabar antes de arrancar, o deja que lo haga un pasajero. No toques CommaView mientras conduces."
  - id: recording
    title: "Deja que grabe"
    body: |
      Mientras graba, Grabar muestra el tiempo y **Detalles** dice **Grabando ·** y el tiempo. Toca Grabar de nuevo para detenerlo. Una reproducción también se detiene sola a los 10 minutos, y al cerrar Live View.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Grabar, con su temporizador. Tócalo de nuevo para detenerlo."
      - target: recording
        text: "**Grabando ·** el tiempo, en **Detalles**."
      - text: "**Guardar** conserva los últimos 3 minutos y el minuto siguiente, sin Grabar. Se copia a tu teléfono cuando estacionas."
    note: "**Guardar** solo aparece donde el entorno de ejecución de tu comma enumera sus viajes. Un toque dentro de ese minuto siguiente conserva otro minuto, hasta 10 minutos. Déjaselo a un pasajero mientras conduces."
  - id: make-replay
    title: "Estaciona y crea la reproducción"
    body: |
      Una vez estacionado, abre **Grabaciones** desde la barra inferior (la barra lateral en una pantalla más grande). El viaje que grabaste dice **Pendientes de procesar**. Ábrelo y toca **Crear reproducción**: la app dice «Reproducción en cola. Síguela en Cola.»

      El comma solo comparte un viaje mientras el coche está en P con openpilot desactivado, así que deja el coche encendido y tu teléfono en la red del comma hasta que se cree la reproducción. Sin un arnés de alimentación, apagar el coche también apaga el comma.
    screen: recordings-make-replay
    pins:
      - text: "**Crear reproducción**."
      - target: queue
        text: "**Cola** muestra cada reproducción que se está creando, una cada vez, con Pausar, Reintentar y Quitar."
    note: "**Crear reproducción** puede tardar hasta un minuto en aparecer después de estacionar: a un comma que dijo que estaba en marcha se le vuelve a preguntar un minuto después."
  - id: watch
    title: "Mírala en Grabaciones"
    body: |
      Cuando está creada, la app dice **Reproducción creada** con su número de fotogramas, y el viaje se reproduce en Grabaciones. Tócalo para verlo, a pantalla completa si quieres.
    screen: phone-recordings
    pins:
      - text: "La reproducción del viaje, agrupada bajo el día."
      - target: filter
        text: "**Filtrar**: **Todos los viajes**, **Listos** o **Pendientes de procesar**, y qué comma."
check: "La fila del viaje ya no dice **Pendientes de procesar**, y se reproduce al tocarla. Para compartirla o guardarla en otro sitio, consulta [Compartir y exportar grabaciones](/es/guides/export-share)."
fixes:
  - q: "«Se puede grabar cuando el comma haya empezado un viaje.»"
    a: "El comma está detenido. Enciende el coche y espera a que arranque openpilot, y vuelve a tocar Grabar."
  - q: "«CommaView aún se está sincronizando con este viaje. Vuelve a tocar Grabar en un momento.»"
    a: "Grabar necesita los tiempos de fotograma del comma, que llegan con sus datos de conducción. No habían llegado en 5 segundos. Espera un momento y vuelve a tocar Grabar."
  - q: "«CommaView no recibe datos de conducción del comma. Revisa la conexión y vuelve a tocar Grabar.»"
    a: "Puede que el vídeo siga reproduciéndose, pero los datos de conducción se detuvieron. Comprueba que tu teléfono sigue en el Wi‑Fi o el punto de acceso del comma y vuelve a intentarlo. Si Live View dice **No llegan los datos del coche**, reinicia el comma."
  - q: "«Reinicia antes el comma: CommaView se instaló, actualizó o reparó, y vuelve a grabar tras un reinicio.»"
    a: "Reinicia el comma con el coche en P y vuelve a grabar."
  - q: "«El almacenamiento de grabaciones está lleno. Libera espacio y vuelve a tocar Grabar.»"
    a: "Elimina en Grabaciones los viajes que ya no necesites, o elige otro almacenamiento en **Ajustes › Grabaciones › Almacenamiento** con **Cambiar**."
  - q: "«El comma no tiene más espacio para los datos del HUD de este viaje (unos 55 minutos de grabaciones). Vuelve a grabar en tu próximo viaje.»"
    a: "El comma guarda hasta unos 55 minutos de datos del HUD de grabaciones por viaje. Crea las reproducciones de lo que grabaste y vuelve a grabar en el próximo viaje."
  - q: "«Pon la P para crear esta reproducción», o el viaje dice «Esperando a que estaciones»"
    a: "El comma solo comparte un viaje estacionado, con openpilot desactivado. Pon el coche en P y déjalo encendido. La reproducción espera y vuelve a preguntar cada 15 segundos; tras 30 minutos de conducción se detiene con «El coche aún estaba en marcha, así que el comma no pudo compartir este viaje. Reintenta cuando estés estacionado.» Toca **Reintentar** en Cola cuando hayas estacionado."
  - q: "«Conéctate a Comma Chameleon para crear esta reproducción»"
    a: "Tu teléfono no pudo alcanzar el comma que grabó el viaje (aparece el nombre del tuyo). Conecta tu teléfono al Wi‑Fi o al punto de acceso del comma y toca **Reintentar** en Cola. Consulta [CommaView no encuentra tu comma](/es/guides/comma-not-found)."
  - q: "«Viaje eliminado del comma»"
    a: "El comma eliminó este viaje para hacer sitio a otros más nuevos antes de que se creara su reproducción, así que ya no se puede crear. Puedes eliminar la grabación. Un viaje que dice **Crea la reproducción pronto** está cerca de eso: créala mientras puedas."
  - q: "La reproducción dice «Falta el HUD durante 2 min»"
    a: "El comma no guardó los datos de la pantalla de conducción durante parte de la grabación. La reproducción muestra **Datos del HUD no disponibles** en ese tramo, y el dato **Datos del HUD** de la vista de reproducción dice cuánto tiempo."
  - q: "«Reproducción creada: 4.860 fotogramas. Termina antes, donde el comma perdió la alimentación.»"
    a: "El comma perdió la alimentación al terminar el viaje, así que no se guardaron sus últimos momentos. Grabaciones puede mostrar **Puede que tu comma perdiera alimentación al terminar un viaje**; su **Cómo solucionarlo** explica la alimentación del comma y el ajuste del tiempo detenido."
related: [live-copy, export-share, live-view]
---

## Reproducción, copia en vivo o ambas

| Grabar crea | Qué obtienes |
| --- | --- |
| **Reproducción** (la opción por defecto) | El vídeo propio del comma con la pantalla de conducción dibujada encima, creada cuando estacionas. La mejor imagen, hasta 10 minutos por grabación, mientras el comma aún tenga el viaje. Solo las cámaras de carretera y gran angular: una reproducción no tiene cámara del conductor. |
| **Copia en vivo** | Lo que muestra Live View, guardado en tu teléfono mientras conduces y listo en cuanto paras. Sin reproducción que crear y sin límite de tiempo. [Grabar una copia en vivo](/es/guides/live-copy). |
| **Ambas** | Una copia en vivo al momento y la reproducción tras el viaje. La reproducción mantiene su límite de 10 minutos. |

## Dónde se guardan las grabaciones

Las grabaciones se quedan en tu teléfono. **Ajustes › Grabaciones › Almacenamiento** muestra el almacenamiento que usan y lo que queda libre, y **Cambiar** elige otro cuando tu teléfono lo tiene. La copia de seguridad de Android y el paso a un teléfono nuevo las dejan fuera. **Enviar a CommaView** solo envía los datos propios del comma de un viaje, y solo cuando tú lo envías.

## Seguridad

Inicia Grabar antes de arrancar y crea las reproducciones cuando hayas estacionado. No manejes CommaView mientras conduces: mantén la vista en la carretera y las manos en el volante, como pide openpilot. CommaView no es una cámara de salpicadero ni un sistema de seguridad, y una grabación puede fallar.
