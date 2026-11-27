---
title: "Navegar con tu propia clave de Stadia Maps"
description: "Añade tu clave de Stadia Maps, busca un lugar en Inicio, elige una ruta y sigue su tarjeta de giros y sus indicaciones por voz en Live View. Envía también el lugar a tu comma."
topic: navigation
order: 1
kind: walkthrough
lede: "**Navegación** te guía a un lugar en Live View. Búscalo en Inicio con **¿Adónde vas?**, elige una ruta, toca **Iniciar** y sigue la tarjeta de giros y las indicaciones por voz. Las rutas vienen de Stadia Maps con tu propia clave, que se queda cifrada en tu teléfono. Las indicaciones son solo informativas y nunca controlan el coche."
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "Sesión iniciada"
    text: "CommaView 0.0.167 o posterior, con la sesión iniciada con tu cuenta de la beta. La navegación no se ofrece sin la sesión iniciada."
  - title: "Una clave de Stadia Maps"
    text: "Una clave de API de tu propia cuenta de Stadia Maps. Las rutas se piden con tu cuenta y según sus condiciones."
  - title: "Ubicación del vehículo activada"
    text: "Las indicaciones siguen el GPS de tu comma. Activa **Ubicación del vehículo** para tu comma en Inicio."
  - title: "Internet en tu teléfono"
    text: "Para búsquedas y rutas. Van por datos móviles cuando el Wi‑Fi del comma no tiene internet."
howItWorks:
  - title: "¿Adónde vas?"
    text: "Encuentra lugares cerca de tu comma, con los datos de OpenStreetMap (Photon)."
    edge: "tu clave"
  - title: "Stadia Maps"
    text: "Planifica las rutas, que pide tu teléfono con tu clave. Nada pasa por CommaView."
  - title: "Live View"
    text: "Te guía desde la posición de tu comma: la tarjeta de giros, el mapa y las indicaciones por voz."
steps:
  - id: open
    title: "Abre Mapas y navegación"
    body: |
      Toca **Ajustes** y luego **Mapas y navegación**. Con la sesión iniciada, es la fila donde antes estaban los mapas sin conexión.
    screen: support-settings
    pins:
      - target: maps-row
        text: "**Mapas y navegación**."
  - id: get-key
    title: "Obtén una clave de Stadia Maps"
    body: |
      En **Tu clave de Stadia Maps**, **Clave de API** dice **Sin añadir**. Toca **Obtener una clave de Stadia Maps**: abre el registro de Stadia en tu navegador. Regístrate y copia tu clave de API desde tu panel de Stadia Maps.
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**Tu clave de Stadia Maps**: «Las rutas necesitan tu propia clave de Stadia Maps…»"
      - target: get-key
        text: "**Obtener una clave de Stadia Maps** abre el registro de Stadia."
      - target: add-key
        text: "**Añadir**, cuando hayas copiado tu clave."
    note: "El sitio de Stadia no aparece en la imagen: es suyo. Su panel muestra el uso, el plan y los límites de tu clave."
  - id: add-key
    title: "Pégala y toca Comprobar y guardar"
    body: |
      De vuelta en CommaView, toca **Añadir**. Toca **Pegar** para poner tu clave en el campo y luego **Comprobar y guardar**. Para comprobar la clave, CommaView pide a Stadia Maps una ruta corta entre dos puntos fijos, nada tuyo: **Comprobando con Stadia Maps…**. Una vez aceptada, **Clave de API** la muestra oculta, como **•••• e1f0**.
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "**Tu clave de API de Stadia Maps**, oculta."
      - target: paste
        text: "**Pegar** desde el portapapeles."
      - target: check-and-save
        text: "**Comprobar y guardar**."
    note: "«Se guarda solo en este teléfono, cifrada. Se comprueba con una ruta corta a Stadia Maps antes de guardarla.» Nunca va en un paquete de soporte ni en un informe de fallos."
  - id: where-to
    title: "Toca ¿Adónde vas? en Inicio"
    body: |
      Estacionado, toca **¿Adónde vas?** en Inicio, bajo la tarjeta de tu comma. Escribe un lugar o una dirección, o toca el micrófono para decirlo. Una vez guardados, **Casa** y **Trabajo** quedan a un toque en la tarjeta.
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**¿Adónde vas?** abre la búsqueda."
      - target: voice
        text: "**¿Adónde vas? por voz**."
      - target: home-chip
        text: "**Casa**, una vez guardada."
  - id: pick
    title: "Elige el lugar"
    body: |
      Los resultados están cerca de tu comma, cada uno con su dirección y su distancia, y después tus lugares guardados y recientes. Toca el que quieras.
    screen: navigation-search
    pins:
      - target: search-field
        text: "**Buscar lugares o direcciones**."
      - target: first-result
        text: "Un resultado, con su dirección y su distancia a tu comma."
    note: "No se puede escribir con el coche en movimiento: «No se puede escribir con el coche en movimiento. Usa la voz o un lugar guardado.»"
  - id: start
    title: "Elige una ruta y toca Iniciar"
    body: |
      La vista previa de la ruta la muestra en un mapa, con el tiempo, la distancia y la hora de llegada. Cada ruta tiene una ficha: **Más rápida**, **Ruta 2** y así. Toca **Iniciar**: empiezan las indicaciones y se abre Live View.

      **Guardar como Casa** y **Guardar como Trabajo** dejan el lugar a un toque en Inicio.
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "Las rutas: **Más rápida**, **Ruta 2**…"
      - target: start
        text: "**Iniciar**."
      - target: save-home
        text: "**Guardar como Casa**, y **Guardar como Trabajo** al lado."
  - id: follow
    title: "Síguela en Live View"
    body: |
      La tarjeta de giros muestra el siguiente giro: su flecha, la distancia, la instrucción y el paso siguiente, y cuándo llegarás. Una indicación por voz llega unos 20 segundos antes de cada giro, otra justo antes y una al llegar. En la pantalla de conducción propia de CommaView, se pintan flechas en tu carril y a lo ancho de la salida del giro.

      Si te saltas un giro, llega una ruta nueva en segundos. El viaje termina solo cuando has llegado y apagado el coche.
    tabs:
      - label: "Teléfono"
        body: |
          En vertical, la tarjeta de giros y el mapa quedan bajo el vídeo.
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "La tarjeta de giros."
          - target: end
            text: "**Terminar navegación**."
          - target: mute
            text: "**Silenciar la voz de indicaciones**."
          - target: map-button
            text: "**Mapa** oculta el mapa durante el viaje y lo vuelve a mostrar."
      - label: "Pantalla del coche"
        body: |
          En una pantalla del coche, donde hay sitio junto al vídeo, el mapa y la tarjeta de giros quedan ahí en un panel propio. Donde no lo hay, la pantalla de CommaView funde el mapa en la esquina del vídeo. Arrastra el divisor para cambiar el ancho del panel.
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "La tarjeta de giros."
          - target: divider
            text: "El divisor, para cambiar el ancho del mapa."
          - target: map-button
            text: "**Mapa**."
    warn: "Prepara el viaje estacionado. No toques CommaView mientras conduces: la tarjeta de giros y la voz están ahí para que no tengas que hacerlo, y las alertas de openpilot y de tu coche van primero."
  - id: send
    title: "Envía el lugar a tu comma, si tu fork lo admite"
    body: |
      Bajo **Iniciar**, la vista previa de la ruta tiene **Enviar al comma** para los forks cuya propia navegación admite un destino: StarPilot, carrotpilot y la navegación (alfa) de openpilot, con la de sunnypilot basada en ella. Otros forks no lo muestran.

      Tócalo. CommaView pregunta antes y explica qué hace el fork en la conducción con sus ajustes actuales, como reducir la velocidad en las curvas. Toca **Enviar**: «Enviado a tu comma. StarPilot planifica allí su propia ruta.» El fork calcula la ruta con su propio servicio, así que puede diferir de la de CommaView. **Quitar del comma** lo quita de nuevo, y terminar el viaje también lo borra.
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**Enviar**."
    note: "**Enviar cada viaje a este comma**, bajo Enviar al comma, envía cada viaje cuando tocas Iniciar. Se pausa solo si cambian los ajustes de conducción del fork, hasta que vuelvas a aceptar."
check: "En **Mapas y navegación**, **Clave de API** muestra tu clave oculta, y la vista previa de la ruta dice **Routing by Stadia Maps · Las indicaciones son solo informativas y nunca controlan el coche.**"
fixes:
  - q: "«Añade tu propia clave de Stadia Maps para obtener rutas: Ajustes › Mapas y navegación.»"
    a: "Aún no hay ninguna clave guardada. Toca **Añadir tu clave** en la vista previa de la ruta, o sigue [los pasos 2 y 3](#step-get-key). ¿Adónde vas?, la búsqueda y los lugares funcionan sin ella."
  - q: "«Stadia Maps no aceptó esta clave (401). Comprueba que la copiaste completa desde tu panel.»"
    a: "Vuelve a copiar la clave entera desde tu panel de Stadia Maps y pégala otra vez."
  - q: "«Eso no es una clave de Stadia Maps.»"
    a: "Lo que pegaste no tiene forma de clave de API, así que no se envió nada. Copia la clave de API de tu panel de Stadia Maps: letras, dígitos y guiones."
  - q: "«Stadia Maps rechazó esta clave (403): puede que su plan no incluya rutas.»"
    a: "Revisa tu plan en tu panel de Stadia Maps."
  - q: "«Tu clave de Stadia Maps superó su límite (429)»"
    a: "Se agotaron sus créditos de este mes o hizo demasiadas peticiones seguidas. Revísala en tu panel de Stadia Maps. La app no vuelve a usarla durante cinco minutos."
  - q: "«No se pudo contactar con Stadia Maps para comprobar la clave. Comprueba la conexión a internet de este teléfono y vuelve a intentarlo.»"
    a: "Tu teléfono no tiene internet ahora mismo. Vuelve a intentarlo con datos móviles o con un Wi‑Fi que tenga internet."
  - q: "No hay **¿Adónde vas?** en Inicio"
    a: "La navegación es para miembros con la sesión iniciada desde CommaView 0.0.167. Sin la sesión iniciada, o con un pase que no se puede verificar, no se ofrece. No está disponible en China continental."
  - q: "La tarjeta de giros dice «Ubicación del vehículo desactivada»"
    a: "Las indicaciones necesitan la posición de tu comma. Activa **Ubicación del vehículo** para este comma en Inicio."
  - q: "La tarjeta de giros dice «Esperando GPS»"
    a: "Las indicaciones empiezan con la primera posición de tu comma. Dale un momento a cielo abierto."
  - q: "«Está demasiado lejos para un solo viaje»"
    a: "La navegación planifica rutas a lugares de hasta 1500 km (930 millas). Elige una parada en el camino y continúa desde allí."
  - q: "**Enviar al comma** no aparece"
    a: "Solo aparece en la vista previa de la ruta, y solo para un fork cuya navegación admite un destino: StarPilot, carrotpilot, o la navegación (alfa) de openpilot o de sunnypilot."
  - q: "«No se puede contactar con tu comma para enviarle este viaje.»"
    a: "Conecta este teléfono a la misma red que tu comma y toca **Reintentar**."
  - q: "«La navegación (alfa) de openpilot está desactivada en tu comma.»"
    a: "Toca **Activar la navegación (alfa)**, estacionado. En las versiones de lanzamiento que la desactivan cada vez que arrancan, aún no se puede dejar activada."
related: [live-view, car-screens, overlays]
---

## El mapa en Live View

**Ajustes › Mapas y navegación › Mapa de Live View** elige dónde va:

- **Disposición**: **Automático** (junto al vídeo donde hay sitio, si no en la esquina), **Junto al vídeo** o **En la esquina**. Las pantallas comma 3X, comma four, StarPilot y Surround siempre muestran el mapa junto al vídeo.
- **Ancho junto al vídeo** se ajusta arrastrando el divisor en Live View. **Restablecer** lo devuelve a su valor.
- **Tema del mapa**: **Igual que la app** (el predeterminado: claro mientras CommaView está en claro; oscuro mientras está en oscuro), **Auto** (claro de la salida a la puesta del sol donde esté tu comma), **Igual que el teléfono**, **Claro** u **Oscuro**. Se aplica a todos los mapas: el de Live View, la tarjeta de ubicación de Inicio, **Ubicación del vehículo** y la vista previa de la ruta.

## Indicaciones por voz y tus lugares

- **Indicaciones por voz** activa y desactiva las indicaciones habladas. El altavoz de la tarjeta de giros, **Silenciar la voz de indicaciones**, es el mismo ajuste.
- **Tus lugares**: **Casa** y **Trabajo**, y **Lugares recientes**, guardados en este teléfono. **Borrar** quita los recientes.

## Un lugar desde otra app

En Google Maps u otra app de mapas, comparte un lugar y elige **Navegar con CommaView**. Su vista previa de la ruta se abre en Inicio, como la de un lugar guardado.

## Mapbox

Si tu cuenta lo ofrece, Ajustes › Mapas y navegación puede calcular rutas con tu propio token de Mapbox en lugar de Stadia Maps.

## Privacidad

Tu clave de Stadia Maps se guarda solo en este teléfono, cifrada, y nunca se registra ni va en un paquete de soporte. Las rutas van de tu teléfono a Stadia Maps con ella; nada va al servicio de cuentas de CommaView. Las búsquedas van a Photon, cerca de la posición de tu comma. Borrar tu clave, o cerrar sesión, la quita del teléfono.

## Seguridad

Prepara un viaje estacionado y deja que la tarjeta de giros y la voz te guíen. La navegación es solo informativa: nunca gira, frena ni cambia lo que hace openpilot. No manejes CommaView mientras conduces: mantén la vista en la carretera y las manos en el volante, como pide openpilot.
