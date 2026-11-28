---
title: "Usar CommaView en una AI box Android"
description: "Lleva Live View a la pantalla de CarPlay o Android Auto de tu coche con una AI box Android: conéctala, instala CommaView, ponla en la red de tu comma, empareja y ajusta."
topic: screens
order: 4
kind: walkthrough
lede: "Si tu coche trae de fábrica CarPlay o Android Auto **con cable**, una **AI box Android** puede llevar Live View de CommaView a la propia pantalla del coche, sin cambiar el equipo de audio y sin cables nuevos. La AI box es un pequeño ordenador Android que se conecta al puerto USB donde conectarías tu teléfono. CommaView funciona en la AI box, así que tu teléfono queda libre para llamadas y mapas."
parked: true
updated: 2026-11-27
needs:
  - title: "CarPlay o Android Auto con cable"
    text: "CarPlay con cable o Android Auto con cable de fábrica, a través de un puerto USB que transmita datos. Comprueba que la AI box admite lo que tiene tu coche."
  - title: "Una AI box con Android de verdad"
    text: "Android 8 o posterior que te deje instalar una app desde un archivo. Las cajas cerradas «de vídeo» y los simples adaptadores inalámbricos no pueden ejecutar CommaView. [Qué AI box comprar](/blog/android-ai-box-commaview)."
  - title: "CommaView en tu teléfono"
    text: "Configura primero tu comma desde tu teléfono y luego empareja la AI box. [Configurar CommaView](/es/guides/setup)."
howItWorks:
  - title: "Tu comma"
    text: "Envía Live View a la AI box por una red local."
    edge: "Wi‑Fi"
  - title: "AI box"
    text: "Ejecuta CommaView, como cualquier dispositivo Android."
    edge: "USB"
  - title: "Pantalla del coche"
    text: "Muestra la pantalla de la AI box, igual que muestra CarPlay."
steps:
  - id: plug-in
    title: "Conecta la AI box e instala CommaView"
    body: |
      Conecta la AI box al puerto USB de CarPlay o Android Auto del coche y deja que arranque. Conéctala por ahora a un Wi‑Fi con internet.

      En el navegador de la AI box, inicia sesión en [my.commaview.com](https://my.commaview.com) con el correo al que llegó tu invitación y toca **Download CommaView** en **Get the app**. Permite las instalaciones desde el navegador solo para esta instalación y luego vuelve a desactivarlo. Abre CommaView e inicia sesión.
    note: "Usa CommaView en el modo Android de la AI box, no con el CarPlay de tu teléfono pasado a través de ella."
  - id: network
    title: "Pon la AI box y el comma en la misma red"
    body: |
      Live View va directamente del comma a la AI box por una red local, no por internet, y sirve cualquier red en la que estén ambos.
    tabs:
      - label: "El punto de acceso de la AI box"
        body: "Las AI box con tarjeta SIM suelen poder compartir un punto de acceso. Actívalo y conecta el comma a él en **Ajustes › Red** del comma."
      - label: "El punto de acceso de tu teléfono"
        body: "Conecta la AI box y el comma al punto de acceso de tu teléfono. También obtienen internet por él."
      - label: "El punto de acceso del comma"
        body: "Activa el punto de acceso del comma (openpilot lo llama tethering) y únete a él desde la AI box."
    note: "La mayoría de las AI box también usan el Wi‑Fi para conectar tu teléfono por CarPlay inalámbrico, y algunas pierden su internet por Wi‑Fi mientras lo hacen. Desactiva cualquier VPN de la AI box."
  - id: pair
    title: "Empareja la AI box con tu comma"
    body: |
      En tu teléfono, abre los **Ajustes del dispositivo** del comma, toca **Emparejar otro teléfono** y, en **Añadir otro teléfono**, **Mostrar invitación**. En la AI box, toca **Emparejar un comma que ya usa CommaView**, elige tu comma y escribe el código o toca **Escanear código QR**. Todos los pasos: [Usar CommaView en una tablet o pantalla del coche](/es/guides/car-screens#step-pair).
  - id: edges
    title: "Aleja la app de los bordes que corta el coche"
    body: |
      Algunos coches recortan los bordes de lo que envía la AI box, y Android no lo sabe. Abre **Ajustes › Pantalla › Bordes de la pantalla**. Una línea marca dónde termina la app: mueve cada borde hacia dentro con **−** y **+** hasta que veas la línea en todo el contorno, y toca **Listo**. **Restablecer** lo desactiva.

      Luego comprueba que Inicio, Live View y Ajustes caben dentro.
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−** y **+** mueven cada borde hacia dentro; **Listo** lo guarda."
      - text: "**Tema**, también en **Ajustes › Pantalla**: **Igual que este dispositivo** sigue a la AI box."
  - id: auto
    title: "Deja que se abra sola"
    body: |
      En **Ajustes › Pantalla**, en **Abriendo Live View**:

      - **Abrir CommaView al iniciar este dispositivo**, para una AI box que se reinicia con el coche.
      - **Abrir CommaView al conectar Bluetooth**, eligiendo tu teléfono, para una AI box que en cambio se suspende.
      - **Abrir Live View al conectar**, para entrar directamente en Live View cuando tu comma se conecta con el coche encendido.

      Permite **Mostrar sobre otras apps** para que CommaView pueda abrirse solo. Sin ello, una notificación ofrece abrirlo.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Abrir Live View al conectar**."
  - id: check
    title: "Comprueba que Live View se reproduce y conduce"
    body: |
      Con el coche encendido, abre Live View en la AI box. Sus controles quedan en una barra en el lado del conductor, compacta en una pantalla baja. Comprueba que la imagen se reproduce y que no se corta nada antes de conducir.
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "**Grabar**, arriba de la barra."
      - target: details
        text: "**Detalles**, más abajo en la barra."
    note: "La pantalla de la AI box llega al coche como vídeo, así que Live View se codifica una vez más por el camino. Espera una imagen algo más suave y con un poco más de retraso que en un teléfono en la mano."
check: "La pantalla del coche muestra Inicio de CommaView y luego Live View con la píldora de la transmisión diciendo **En vivo**, y la línea de **Bordes de la pantalla** se ve en todo el contorno."
fixes:
  - q: "La AI box no puede instalar CommaView"
    a: "Algunas AI box bloquean las instalaciones desde el navegador. Descarga la app en un ordenador, cópiala con una memoria USB y ábrela desde el gestor de archivos de la AI box. Una AI box con un sistema cerrado y una lista fija de apps no puede instalarla en absoluto."
  - q: "La AI box no encuentra el comma"
    a: "Comprueba que ambos están en la misma red y que la AI box no ha soltado su Wi‑Fi por el CarPlay inalámbrico. Introduce la dirección IP del comma si hace falta: 192.168.43.1 en el punto de acceso del propio comma. Más en [Conectar en el coche](/es/guides/connect-in-the-car)."
  - q: "La imagen se entrecorta o no se reproduce"
    a: "El comma envía su cámara de carretera en HEVC (H.265) de 1928 × 1208, y los decodificadores de las AI box más baratas pueden no dar la talla. Si un decodificador falla, CommaView prueba solo los demás de la AI box. Live View dice **No se puede reproducir el vídeo de este comma** cuando ninguno puede: envía un informe de soporte desde la AI box."
  - q: "«Live View está abierto en otro dispositivo»"
    a: "Tu comma transmite a un solo teléfono o pantalla del coche a la vez. Vuelve a Inicio en CommaView en tu teléfono, y Live View empieza solo en la AI box."
  - q: "¿Puedo seguir usando CarPlay desde mi teléfono?"
    a: "Sí. La mayoría de las AI box pasan el CarPlay o Android Auto de tu teléfono de forma inalámbrica, y cambias entre eso y el Android de la AI box. CommaView funciona en el modo Android de la AI box."
  - q: "¿La AI box necesita una tarjeta SIM?"
    a: "No para Live View. Durante la beta, CommaView necesita internet de vez en cuando para renovar su pase de acceso, y se lo da el Wi‑Fi de casa, el punto de acceso de tu teléfono o una SIM en la AI box."
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## Cuatro tipos de «adaptador de CarPlay»

Las tiendas venden cuatro cosas muy distintas con el mismo nombre. Solo una ejecuta CommaView.

| Tipo | Qué hace | ¿Ejecuta CommaView? |
| --- | --- | --- |
| **AI box Android** | Android completo en la pantalla del coche, con apps instaladas como en un teléfono | **Sí** |
| **Caja cerrada «de vídeo»** | Unas pocas apps de streaming integradas en un sistema bloqueado | No |
| **Adaptador inalámbrico** | Hace inalámbrico el CarPlay o Android Auto con cable. Sin Android propio | No |
| **Pantalla portátil de CarPlay** | Una pantalla aparte para el CarPlay de tu teléfono, a menudo sin Android dentro | No |

[Las mejores AI box Android para CommaView](/blog/android-ai-box-commaview) compara las que vale la pena comprar. Un Tesla no tiene CarPlay ni Android Auto: usa [Browser View](/es/guides/browser-view).

Cuando actualices el entorno de ejecución de tu comma, actualiza antes CommaView en la AI box, como en todos los dispositivos que ven tu comma.

## Seguridad

Configura la AI box estacionado y luego no la toques. No manejes CommaView mientras conduces: mantén la vista en la carretera y las manos en el volante, como pide openpilot. Las alertas de tu comma y los instrumentos de tu coche van primero. CommaView solo muestra lo que ve el comma.
