---
title: "Usar CommaView en una tablet o pantalla del coche"
description: "Lleva Live View a una pantalla más grande: una pantalla del coche Android, una AI box Android en la pantalla del coche o una tablet en un soporte. Instalación, red, emparejamiento y diseño."
topic: screens
order: 3
kind: walkthrough
lede: "Las pantallas del comma 3X y del comma four son pequeñas. CommaView muestra Live View de tu comma en una más grande: una pantalla del coche Android, una AI box Android en la propia pantalla del coche, o un teléfono o una tablet en un soporte. La pantalla del coche usa su propia copia de CommaView, emparejada con tu comma."
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 o posterior"
    text: "Una pantalla del coche, una AI box, un teléfono o una tablet con Android 8 o posterior que te deje instalar una app."
  - title: "Tu invitación"
    text: "El correo al que llegó tu invitación de CommaView, para iniciar sesión en my.commaview.com y en la app."
  - title: "CommaView en tu teléfono"
    text: "Lo más fácil: configura primero tu comma desde tu teléfono y después empareja la pantalla del coche. [Configurar CommaView](/es/guides/setup)."
howItWorks:
  - title: "Tu comma"
    text: "Envía Live View por una red local, no por internet."
    edge: "punto de acceso o Wi‑Fi"
  - title: "La pantalla del coche"
    text: "Usa su propio CommaView, emparejado con tu comma."
steps:
  - id: install
    title: "Instala CommaView en la pantalla del coche"
    body: |
      En la pantalla del coche, la AI box, el teléfono o la tablet, abre su navegador web e inicia sesión en [my.commaview.com](https://my.commaview.com) con el correo al que llegó tu invitación. En **Get the app**, toca **Download CommaView**, abre la descarga y permite las instalaciones desde el navegador para esta, y luego vuelve a desactivarlo, como en la [guía de configuración](/es/guides/setup).

      Abre CommaView e inicia sesión. Durante la beta necesita internet de vez en cuando para renovar su pase de acceso, así que dale un Wi‑Fi con internet al menos de vez en cuando.
    note: "Algunas pantallas del coche y AI box bloquean las instalaciones desde el navegador. Descarga la app en un ordenador, cópiala con una memoria USB y ábrela desde el gestor de archivos del equipo."
  - id: network
    title: "Ponla en la misma red que el comma"
    body: |
      Live View va directamente del comma a la pantalla del coche por una red local. Solo tienen que estar en la misma, y en el coche suele ser un punto de acceso. Elige la que se enciende sola cuando arranca el coche: suele ser la más cómoda.
    tabs:
      - label: "El punto de acceso de la pantalla del coche"
        body: "Si la AI box o la pantalla del coche puede compartir un punto de acceso (muchas con tarjeta SIM pueden), actívalo y conecta el comma a él en **Ajustes › Red** del comma."
      - label: "El punto de acceso de tu teléfono"
        body: "Conecta el comma y la pantalla del coche al punto de acceso de tu teléfono. También obtienen internet por él."
      - label: "El punto de acceso del comma"
        body: "Activa el punto de acceso del comma (openpilot lo llama tethering: en un comma four, **Ajustes › Red › enable tethering**; en un comma 3X, **Ajustes › Red › Avanzado › Enable Tethering**) y únete a él desde la pantalla del coche."
      - label: "Wi‑Fi de casa"
        body: "En casa, ambos en tu Wi‑Fi. Útil para la configuración, pero se acaba cuando te vas en el coche."
    note: "Desactiva cualquier VPN de la pantalla del coche. Algunos puntos de acceso mantienen separados a los dispositivos conectados: si la pantalla del coche no encuentra el comma en uno, prueba con otro. Más en [Conectar en el coche](/es/guides/connect-in-the-car)."
  - id: pair
    title: "Emparéjala con tu comma"
    body: |
      Si tu comma ya usa CommaView desde tu teléfono, empareja la pantalla del coche en lugar de volver a configurarlo. Obtiene su propia clave.
    tabs:
      - label: "En tu teléfono"
        body: |
          Abre los **Ajustes del dispositivo** del comma y luego **Emparejar otro teléfono**. En **Añadir otro teléfono**, toca **Mostrar invitación**: un código para escribir, o un código QR, válido durante 10 minutos y de un solo uso.
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**Mostrar invitación**."
          - target: this-phone
            text: "Los teléfonos con clave, este marcado como **Este teléfono**. La pantalla del coche se une a ellos."
      - label: "En la pantalla del coche"
        body: |
          En **Conecta tu comma**, toca **Emparejar un comma que ya usa CommaView** (con un comma ya añadido, abre **Añadir un comma**). Elige tu comma y toca **Introducir su código**, o **Escanear código QR**. Si no aparece, toca **Introducir dirección y código**. Escribe la invitación en **Código o invitación** y toca **Emparejar comma**.
        screen: add-comma
        pins:
          - target: found-comma
            text: "Tu comma, encontrado en esta red."
          - target: scan-qr
            text: "**Escanear código QR**."
          - target: enter-address
            text: "**Introducir dirección y código**, si no aparece."
    note: "Tu teléfono dice entonces **Un teléfono nuevo tiene clave**. Toca **Es mío**. Todos los pasos: [Añadir otro teléfono o tablet](/es/guides/another-phone)."
  - id: fit
    title: "Ajústala a tu pantalla"
    body: |
      En una pantalla ancha, CommaView se organiza como un panel, con la navegación en una barra lateral. Deja el tamaño de texto del equipo en uno que puedas leer de un vistazo: CommaView se organiza según el espacio que tiene con ese tamaño.

      Los controles de Live View quedan en el lado del conductor. En **Auto**, CommaView sigue el lado que indica tu comma; para elegirlo tú, ve a **Ajustes › Pantalla › Posición del conductor**: **Auto**, **Volante a la izquierda** o **Volante a la derecha**. Refleja los controles en todas las pantallas.
    tabs:
      - label: "Tablet"
        body: "Inicio muestra el coche, tu semana, el mapa y tus viajes uno al lado de otro, con la barra al costado."
        screen: tablet-home
        pins:
          - target: home-tab
            text: "La barra: **Inicio**, **Grabaciones**, **Ajustes**."
          - target: open-live-view
            text: "**Abrir Live View**."
      - label: "Pantalla del coche"
        body: "El mismo panel, a la medida de una pantalla de salpicadero."
        screen: car-home
        pins:
          - target: home-tab
            text: "La barra: **Inicio**, **Grabaciones**, **Ajustes**."
          - target: open-live-view
            text: "**Abrir Live View**."
      - label: "A través de una AI box"
        body: |
          Algunos coches cortan los bordes de la imagen que envía una AI box, y Android no lo sabe. Abre **Ajustes › Pantalla › Bordes de la pantalla** y mueve cada borde hacia dentro hasta que veas la línea en todo el contorno. Luego comprueba que Inicio, Live View y Ajustes caben dentro. **Tema** puede seguir ahí a la pantalla del coche: **Igual que este dispositivo**.
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−** y **+** mueven cada borde hacia dentro; **Listo** lo guarda."
  - id: live-view
    title: "Abre Live View y comprueba que se reproduce"
    body: |
      Toca **Abrir Live View**, con el coche encendido. Sus controles quedan en una barra junto a la carretera, en el lado del conductor, compacta en una pantalla baja.
    tabs:
      - label: "Tablet"
        body: "**Detalles** se abre en un panel junto al vídeo."
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "Detalles, junto al vídeo."
          - target: record-button
            text: "**Grabar**."
          - target: go-live-button
            text: "**Transmitir**."
      - label: "Pantalla del coche"
        body: "La barra tiene Grabar, el selector de pantalla de conducción, Cámara int., Detalles y Salir."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Grabar**."
          - target: onroad-screen-button
            text: "El selector de pantalla de conducción."
          - target: driver-cam-button
            text: "**Cámara int.**"
          - target: details
            text: "**Detalles**, bajo Cámara int."
          - target: exit
            text: "**Salir**."
  - id: auto
    title: "Deja que se abra sola"
    body: |
      En **Ajustes › Pantalla**, en **Abriendo Live View**:

      - **Abrir Live View al conectar** abre Live View solo cuando tu comma se conecta con el coche encendido.
      - **Abrir CommaView al iniciar este dispositivo**, para una pantalla del coche que se reinicia con el coche. Una que en cambio se suspende puede tener su propia lista de apps de inicio.
      - **Abrir CommaView al conectar Bluetooth**: cuando se conecta el dispositivo que elijas, tu coche o, en una pantalla del coche, tu teléfono.

      Con **Mostrar sobre otras apps** permitido, CommaView se abre solo. Si no, una notificación ofrece abrirlo.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Abrir Live View al conectar**."
check: "Con el coche encendido, la pantalla del coche abre Live View, la píldora de la transmisión dice **En vivo** y todos los controles quedan dentro de los bordes de la pantalla."
fixes:
  - q: "¿Puedo usar CommaView con CarPlay o Android Auto?"
    a: "No desde tu teléfono. CommaView no es una app de CarPlay ni de Android Auto, y esas plataformas no dejan que las apps del teléfono muestren vídeo mientras el coche se mueve. Una AI box Android lo evita, porque es un dispositivo Android propio: CommaView funciona en la AI box y el coche muestra su pantalla. Consulta [Usar CommaView en una AI box Android](/es/guides/ai-box)."
  - q: "¿Funcionará en el Android Automotive integrado de mi coche (Google integrado)?"
    a: "Todavía no. Los coches con Google integrado solo instalan apps desde su propia Play Store, donde CommaView no está. Si lo pruebas de otra forma, cuéntanos cómo te fue."
  - q: "¿Puedo usar una pantalla del coche y mi teléfono con el mismo comma?"
    a: "Sí: empareja cada uno con el comma. Solo uno tiene Live View a la vez, así que cierra Live View en el otro primero. Live View dice **Live View está abierto en otro dispositivo** y empieza solo cuando vuelves a Inicio en el otro."
  - q: "Mi coche corta los bordes de la imagen"
    a: "Algunos coches recortan la imagen que envía una AI box, y Android no lo sabe. **Ajustes › Pantalla › Bordes de la pantalla** aleja la app de cada borde que fijes."
  - q: "La pantalla del coche no encuentra el comma"
    a: "CommaView encuentra el comma solo en la misma red, aunque cambie su dirección. Si no lo hace, introduce la dirección IP del comma: 192.168.43.1 en el punto de acceso del propio comma (es la misma en todos los commas) o, en cualquier otra red, la dirección IP que el comma muestra en **Ajustes › Red**: bajo el nombre de la red en el botón de Wi‑Fi en un comma four, o en **Avanzado** en un comma 3X."
  - q: "La pantalla del coche dejó de recibir vídeo tras una actualización del entorno"
    a: "Cuando actualices el entorno de ejecución de tu comma, actualiza antes CommaView en todos los dispositivos que lo ven, también en la pantalla del coche. Una pantalla del coche con un CommaView anterior sigue funcionando 90 días desde que el primer teléfono del comma obtiene su clave; después necesita CommaView 0.0.166 o posterior y una invitación."
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## Qué funciona mientras conduces

CommaView es una app de Android, así que necesita un dispositivo Android delante de ti. Cualquiera de estos puede usarlo mientras conduces:

- **Una pantalla del coche Android.** Una pantalla de recambio con Android 8 o posterior: CommaView se instala en ella como en un teléfono y funciona en la pantalla del coche mientras conduces.
- **Una «AI box» Android.** Un pequeño ordenador Android que se conecta al puerto de CarPlay o Android Auto con cable del coche y dibuja ahí su propia pantalla Android. CommaView funciona en la AI box, no en tu teléfono. Consulta [Usar CommaView en una AI box Android](/es/guides/ai-box).
- **Un teléfono o una tablet en un soporte.** Cualquier teléfono o tablet Android, en un soporte de salpicadero o de rejilla que no te tape la vista. La opción más sencilla, y la que más gente usa.

Un coche con navegador web, como un Tesla, puede mostrar Live View en él: consulta [Mostrar Live View en el navegador de tu coche](/es/guides/browser-view).

## Qué no funciona, y por qué

- **CarPlay y Android Auto desde tu teléfono.** CommaView no es una app de CarPlay ni de Android Auto. Esas plataformas no dejan que las apps del teléfono muestren vídeo mientras el coche se mueve.
- **Vídeo con el coche estacionado en CarPlay y Android Auto.** Apple y Google están añadiendo vídeo para algunos coches, pero solo estacionado, así que no puede mostrar Live View en carretera.
- **Duplicar tu teléfono en el coche.** Los adaptadores que duplican la pantalla de un teléfono a través de CarPlay o Android Auto no son compatibles. Usa en su lugar una AI box o una pantalla del coche Android que ejecute CommaView por sí misma.
- **Google integrado (Android Automotive).** Estos coches solo instalan apps desde su propia Play Store, donde CommaView no está.

## Hardware probado

Pantallas del coche con las que el equipo de CommaView ha conducido. CommaView debería funcionar en cualquier dispositivo con Android 8 o posterior, pero estos son los que hemos comprobado:

| Dispositivo | Tipo | Qué comprobamos |
| --- | --- | --- |
| **Pantalla del coche Doro** (Qualcomm QCM6125, Android 13, 1280 × 720) | Pantalla del coche | Live View en trayectos urbanos (octubre de 2026). |
| **Pantalla del coche Dasaita de 10,2″** (1280 × 720, en un Toyota RAV4) | Pantalla del coche | Live View conduciendo; subida de grabaciones, estacionado. |

**Ayúdanos a probar.** Cada pantalla del coche es distinta. Si usas CommaView en una pantalla del coche o una AI box, [cuéntanos cómo te fue](#cuéntanos-sobre-tu-pantalla-del-coche) y la añadiremos aquí cuando la hayamos comprobado.

## Cuéntanos sobre tu pantalla del coche

Envíanoslo desde la propia pantalla del coche, para que el informe incluya su modelo y su tamaño de pantalla:

1. En CommaView, en la pantalla del coche o la AI box, abre **Ajustes › Soporte y diagnóstico** y toca **Informar de un problema o enviar una idea**.
2. Elige **Idea** y activa **Este dispositivo: diagnóstico** (una idea lo deja desactivado): nos dice su marca, su modelo y su tamaño de pantalla.
3. En la nota, indica tu coche, la pantalla del coche o la AI box (marca y modelo), cómo está conectada (el punto de acceso de quién, o Wi‑Fi) y qué funcionó y qué no. Luego toca **Enviar**.

Encontrarás lo que enviaste, y nuestras respuestas, en Your feedback en [my.commaview.com](https://my.commaview.com/feedback). ¿Aún no estás en la beta, o la app no arranca? Cuéntanoslo en el [Discord de CommaView](https://discord.gg/UuMhz9K8ft).

## Seguridad

- Instala, empareja y ajusta el diseño estacionado. Comprueba que Live View se reproduce antes de conducir.
- No manejes CommaView mientras conduces. Mantén la vista en la carretera y las manos en el volante, como pide openpilot.
- Las alertas de tu comma y los instrumentos de tu coche van primero. CommaView solo muestra lo que ve el comma.
- Coloca el teléfono o la tablet donde no te tape la vista ni un airbag, y respeta las normas locales sobre pantallas en el coche.
