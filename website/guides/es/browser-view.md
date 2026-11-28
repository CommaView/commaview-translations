---
title: "Muestra Live View en el navegador de tu coche"
description: "Browser View muestra Live View de CommaView en el propio navegador web de tu coche, también en un Tesla, servido por tu teléfono a través de su punto de acceso. Nada que instalar en el coche."
topic: screens
order: 2
kind: walkthrough
lede: "**Browser View** muestra lo que muestra Live View en el propio navegador web de tu coche. Tu teléfono lo sirve al coche por su punto de acceso o su Wi‑Fi, así que no hay nada que instalar en el coche. Se creó para coches como un Tesla, que tienen navegador pero no CarPlay ni Android Auto, y funciona en cualquier navegador que pueda alcanzar tu teléfono."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funciona"
    text: "CommaView en un teléfono Android, emparejado con tu comma. ¿Aún no? [Configurar CommaView](/es/guides/setup)."
  - title: "Un navegador en el coche"
    text: "Un Tesla, otro coche con navegador web, o una tablet o un portátil en el coche."
  - title: "Una sola red"
    text: "El coche y tu comma en el punto de acceso de tu teléfono, o en cualquier red que compartan los tres."
howItWorks:
  - title: "Tu comma"
    text: "Envía Live View a tu teléfono, como siempre."
  - title: "Tu teléfono"
    text: "Sirve la imagen como una página web, protegida por un código de ocho dígitos."
    edge: "punto de acceso"
  - title: "El navegador del coche"
    text: "Abre la página: 20 fotogramas por segundo, 720p o 1080p, hasta cuatro navegadores."
steps:
  - id: hotspot
    title: "Conecta el coche al punto de acceso de tu teléfono"
    body: |
      Activa el punto de acceso de tu teléfono y conecta el coche a él desde los ajustes de Wi‑Fi del coche. Comprueba que el coche se unió a tu teléfono y no a un Wi‑Fi que ya conocía. Conecta también tu comma al punto de acceso si aún no lo está: tu teléfono sigue necesitando tu comma, como siempre.
    note: "**En un Tesla**, desactiva primero el Wi‑Fi de tu teléfono, para que el punto de acceso comparta los datos móviles."
  - id: start
    title: "Inicia Browser View desde Detalles en Live View"
    body: |
      Abre **Live View** en el teléfono y luego **Detalles**. Casi al final, la tarjeta **Browser View** explica qué hace y qué le comunica a CommaView. Toca **Iniciar**.
    screen: live-view-browser-view
    clip: browser-view-start
    pins:
      - target: browser-view-card
        text: "La tarjeta **Browser View**, casi al final de **Detalles**."
      - target: start-button
        text: "**Iniciar**. La primera vez, dale al teléfono unos segundos para obtener su certificado."
      - target: privacy-policy
        text: "Qué comunica Browser View a CommaView mientras funciona, y la **Política de privacidad**."
  - id: vpn
    title: "En un Tesla, activa la dirección VPN"
    tabs:
      - label: "Tesla"
        body: |
          El navegador de un Tesla no abre las direcciones que reparte un punto de acceso. En la tarjeta, toca **Activar dirección VPN** y acepta cuando Android pregunte si CommaView puede configurar una VPN. Tu teléfono obtiene una dirección que el Tesla sí abre, `169.254.99.1`. No lleva tráfico, y cualquier otra app de VPN queda desactivada mientras está activa.
        screen: live-view-browser-view-vpn
        pins:
          - target: short-link
            text: "El enlace corto, también para el Tesla: **En el navegador del coche, también en un Tesla, abre**."
          - target: vpn-address
            text: "Las direcciones del teléfono en la dirección VPN, `169.254.99.1`."
        note: "La propia pregunta de Android sobre la VPN no aparece en la imagen: es de Android y se ve distinta en cada teléfono."
      - label: "Otro coche"
        body: |
          Aquí no hay nada que hacer: los navegadores de otros coches abren la dirección del punto de acceso. Pasa al siguiente paso.
  - id: open
    title: "Escribe el enlace corto en el navegador del coche"
    body: |
      La tarjeta muestra un enlace corto con tu código de ocho dígitos, como `commaview.app/48291374`. Escríbelo en el navegador del coche y toca **Abrir**. Con el coche conectado a internet y CommaView con la sesión iniciada, la página encuentra tu teléfono y abre Live View por una conexión segura: un candado, sin avisos y con la imagen más fluida.
    screen: live-view-browser-view-on
    pins:
      - target: short-link
        text: "El enlace corto que escribes en el coche, con tu código."
      - target: show-addresses
        text: "**¿Sin internet en el coche? Mostrar direcciones**: las direcciones propias del teléfono."
      - target: quality
        text: "**Imagen de Browser View**: 720p o 1080p."
      - target: stop-button
        text: "**Detener** termina Browser View."
    warn: "**¿Sin internet en el coche?** El enlace corto lo necesita. Usa en su lugar la dirección propia del teléfono: consulta [Sin internet en el coche](#sin-internet-en-el-coche)."
  - id: bookmark
    title: "Guarda la página en marcadores"
    body: |
      La dirección de la página no cambia, así que la próxima vez, con el coche conectado a internet, abre el marcador en lugar de escribir el enlace corto.
check: "La tarjeta del teléfono dice quién está mirando y qué dibuja el navegador del coche, como **1 navegador mirando** y `Tesla 2025.20.6 · H.264 over HTTPS via the VPN name · 20 fps`."
fixes:
  - q: "«Esperando el navegador del coche» y no se abre nada"
    a: "Comprueba que el coche se unió al punto de acceso de tu teléfono y no a otro Wi‑Fi. En un Tesla, activa la dirección VPN ([paso 3](#step-vpn))."
  - q: "«Activa el punto de acceso de este teléfono»"
    a: "El teléfono no está ni en un Wi‑Fi ni en un punto de acceso que el coche pueda compartir. La dirección aparece en los 5 segundos siguientes a que se active cualquiera de los dos."
  - q: "El enlace corto dice que la dirección VPN está desactivada"
    a: "Actívala en la tarjeta y vuelve a cargar la página."
  - q: "Un aviso que no puedes saltar"
    a: "Usa el enlace corto con el coche conectado a internet, o la imagen básica ([Sin internet en el coche](#sin-internet-en-el-coche))."
  - q: "La imagen se detiene en D"
    a: "Que el navegador de un coche siga dibujando mientras conduces depende del fabricante. La línea de informe de la tarjeta dice qué dibuja el coche («0 fps · hidden» es una imagen que el coche detuvo). Dinos tu coche y la versión de su software: activa **Guardar diagnóstico en este teléfono** antes de conducir y después envía **Informar de un problema o enviar una idea** desde Ajustes."
related: [car-screens, ai-box, go-live]
blogPost: commaview-0-0-166-languages-browser-view
---

## Sin internet en el coche

El enlace corto necesita que el coche tenga internet para su página, a través de los datos móviles del punto de acceso o de la propia conexión del coche. Sin internet, abre directamente la dirección del teléfono. En la tarjeta, toca **¿Sin internet en el coche? Mostrar direcciones**:

- **Mejor imagen**, una dirección HTTPS como `https://192.168.43.1:8443/48291374`. El navegador avisa primero, porque el teléfono firma esta dirección por sí mismo: acepta el aviso para continuar. El navegador de un Tesla no te deja pasarlo.
- **Imagen básica**, la misma dirección por HTTP, como `192.168.43.1:8090/48291374`. Sin aviso en ningún navegador, tampoco en un Tesla, pero con una imagen de menor calidad y menos fluida.

Con la dirección VPN activada, la tarjeta muestra sus direcciones, `https://169.254.99.1:8443/<code>` y `169.254.99.1:8090/<code>`. En un Tesla sin internet, usa la básica.

La dirección del punto de acceso de tu teléfono puede ser distinta de la del ejemplo; la tarjeta siempre muestra la correcta, con un botón Copiar junto a cada una.

## Opciones de la tarjeta

- **Imagen de Browser View: 720p o 1080p.** 1080p es más nítida y exige más al teléfono y al punto de acceso. 720p mientras no elijas otra.
- **Iniciar con Live View.** Browser View empieza cada vez que se abre Live View, con la dirección VPN si está activada. Si lo detienes, sigue detenido hasta que Live View vuelva a abrirse.
- **Código nuevo.** Crea un código nuevo de ocho dígitos, para que deje de funcionar una dirección que otra persona vio. Abre la nueva dirección en el coche.
- **Controles en el coche.** Grabar, Guardar momento y los demás controles de Live View quedan bajo la imagen o a su lado en el lado del conductor, nunca encima. **Controles en el coche** en la tarjeta los desactiva.
- **La cámara del conductor** también se ve en el coche mientras **Cámara int.** está activada en Live View.

## Mientras funciona

- **Browser View sigue funcionando con el teléfono bloqueado** o en otra app. Su notificación dice «Mostrando Live View en Browser View», y su **Detener** lo termina.
- **Salir de Live View lo termina**, igual que termina Transmitir y las copias en vivo.
- **Transmitir junto a Browser View** comparte su imagen. Si se inicia mientras Browser View funciona solo, la transmisión no tiene sonido: detén Browser View primero para tener sonido.

## Privacidad y seguridad

- La imagen solo va a navegadores en el punto de acceso o el Wi‑Fi de tu teléfono que tengan el código. Nunca por datos móviles y nunca a través de los servidores de CommaView.
- Diez códigos incorrectos en un minuto desde un dispositivo lo bloquean durante un minuto, y un dispositivo que ya está mirando sigue igual.
- Mientras Browser View funciona, tu teléfono envía al servicio de cuentas de CommaView su código, sus puertos, si la dirección VPN está activada y la dirección privada del punto de acceso o del Wi‑Fi, para que el enlace corto pueda encontrar tu teléfono. Cualquiera que tenga el código puede verlos, junto con el nombre `commaview.app` de tu teléfono, mientras Browser View funciona y hasta 2 horas después de que se detenga de forma inesperada; ninguno de ellos abre nada sin el punto de acceso o el Wi‑Fi de tu teléfono. Se eliminan 30 días después de la última vez que funcionó Browser View. El nombre `commaview.app` de tu teléfono y la fecha de su último certificado se conservan mientras exista tu cuenta. Los certificados son públicos, así que ese nombre queda en los registros de Certificate Transparency; no dice nada de ti, de tu coche ni de tu comma. [La política de privacidad](/privacy) tiene los detalles.
- La dirección VPN es decisión tuya, nunca se activa sola y no lleva tráfico.

## Preguntas

**¿Necesito una AI box o una pantalla del coche nueva?** No. Browser View usa el navegador que tu coche ya tiene. Si tu coche tiene CarPlay o Android Auto, una [AI box Android](/blog/android-ai-box-commaview) puede ejecutar CommaView en la propia pantalla del coche.

**¿Usa mis datos móviles?** La imagen no: va del teléfono al coche por el punto de acceso. La página del enlace corto y el uso que el propio coche hace del punto de acceso sí.

**¿Puede hacerlo el punto de acceso de mi comma en lugar del de mi teléfono?** Para la mayoría de los navegadores, sí: pon el teléfono y el coche en el punto de acceso del comma y abre la dirección que muestra la tarjeta. Un Tesla necesita la dirección VPN, que solo funciona con un coche conectado al punto de acceso del propio teléfono.

## Seguridad

Configura Browser View estacionado y luego no lo toques. No manejes CommaView mientras conduces: mantén la vista en la carretera y las manos en el volante, como pide openpilot. Las alertas de tu comma y los instrumentos de tu coche van primero. CommaView solo muestra lo que ve el comma.
