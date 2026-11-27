---
title: "Elegir la pantalla de conducción y añadir paquetes de superposición"
description: "Elige cómo dibuja Live View la carretera: la pantalla del comma four, la del comma 3X o la propia de CommaView. Luego añade un paquete de superposición con lo que tu fork dibuja en su pantalla."
topic: screens
order: 6
kind: walkthrough
lede: "Live View dibuja una pantalla de conducción sobre la cámara de carretera: la del **comma four**, la del **comma 3X** o la propia de **CommaView**. Las pantallas de comma se dibujan con el aspecto de tu fork. Los **paquetes de superposición** añaden lo que dibuja la pantalla de tu fork y CommaView no, como los indicadores híbridos de BluePilot o la trayectoria arcoíris de dragonpilot."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funciona"
    text: "CommaView en un teléfono Android, emparejado con tu comma. ¿Aún no? [Configurar CommaView](/es/guides/setup)."
  - title: "Sesión iniciada, para la tienda"
    text: "Los miembros exploran los paquetes de CommaView. Sin la sesión iniciada, puedes añadir un paquete desde un archivo o un enlace."
steps:
  - id: switch
    title: "Cambia de pantalla en Live View"
    body: |
      En Live View, toca el selector de pantalla de conducción. Lleva el nombre de la pantalla que muestra, y cada toque pasa a la siguiente: **comma 4**, **comma 3X**, **CommaView**, y vuelta a empezar. La que dejes elegida se conserva para la próxima vez.
    screen: phone-live-view
    clip: onroad-screen
    pins:
      - target: onroad-screen-button
        text: "El selector de pantalla de conducción, con el nombre de la pantalla que muestra."
    note: "Donde no cabe junto a los demás controles, está en **Más**, como **Pantalla de conducción**. Mientras se graba aparece atenuado: una grabación conserva la pantalla con la que empezó."
  - id: display
    title: "O elígela en Ajustes › Pantalla"
    body: |
      Para ver todas las pantallas antes de elegir, abre **Ajustes › Pantalla**. La tarjeta **Pantalla de conducción** muestra una vista previa de la pantalla elegida sobre una foto de carretera, encuadrada según las cámaras de tu comma y dibujada con el aspecto de tu fork. **Activado**, **Intervención** y **Desactivado**, debajo, cambian el momento que se muestra; no guardan nada.
    screen: settings-display
    pins:
      - target: onroad-screen-card
        text: "La vista previa de la pantalla elegida."
      - target: onroad-screen
        text: "**Pantalla de conducción**: tócala para ver la lista."
  - id: pick
    title: "Elige una pantalla"
    body: |
      Cada pantalla de la lista tiene una pequeña imagen y una nota:

      - **comma four**: MÁX sobre la carretera mientras cambia, con el volante y la confianza al lado.
      - **comma 3X**: un borde de estado, el recuadro MÁX, una velocidad grande y alertas en la parte inferior.
      - **CommaView**: una trayectoria fluida, un enganche al vehículo delantero y la velocidad, el estado y las alertas propios de CommaView.

      Elegir una la guarda y cambia la vista previa, sus opciones y Live View. Cualquier pantalla funciona en ambos commas.
    screen: settings-display-onroad-screens
    clip: display-pick
    pins:
      - target: comma-four-option
        text: "**comma four**."
      - target: comma-3x-option
        text: "**comma 3X**."
      - target: commaview-option
        text: "**CommaView**."
    note: "Las alertas, los avisos y el estado de la supervisión del conductor siempre usan los colores propios de tu comma, elijas la pantalla que elijas."
  - id: store
    title: "Abre la tienda de paquetes de superposición"
    body: |
      Abre **Ajustes › Paquetes de superposición**, o toca la tarjeta **Paquetes de superposición** en Inicio.
    tabs:
      - label: "Sesión iniciada"
        body: |
          La tienda muestra primero los paquetes **Oficiales** de CommaView y luego los de la **Comunidad**, todos revisados por CommaView. **Para tu comma** ofrece el paquete oficial del fork que usa tu comma. Busca, o filtra la lista con **Todos**, **Oficiales**, **Comunidad** y **Para mis commas**.
        screen: overlay-packs-store
        pins:
          - target: search
            text: "**Buscar paquetes**."
          - text: "**Para tu comma**: el paquete oficial para el fork de tu comma."
          - target: bluepilot-row
            text: "Los paquetes **Oficiales**, como BluePilot HUD."
          - target: yours
            text: "**Tus paquetes**: lo que hay en este teléfono."
      - label: "Desde un archivo o un enlace"
        body: |
          ¿Alguien compartió un archivo `.cvpack` o un enlace (GitHub, un gist, un adjunto de Discord)? Abre **Tus paquetes** y, en **Añadir un paquete tú mismo**, toca **Instalar desde un archivo** o **Pegar un enlace**. CommaView no ha revisado un paquete añadido así, y el diálogo de instalación lo indica.
  - id: install
    title: "Instala un paquete"
    body: |
      Toca un paquete para ver su vista previa, los forks en los que funciona (**Funciona en**) y lo que añade a Live View. Toca **Instalar** y luego **Instalar** otra vez en el diálogo. El paquete va a este teléfono y a tus commas emparejados.
    screen: overlay-pack-detail
    pins:
      - text: "La vista previa: Live View con el paquete. Tócala para ampliarla."
      - target: install
        text: "**Instalar**."
    note: "Un paquete oficial solo funciona en los forks para los que está hecho. Si ninguno de tus commas emparejados usa uno, el diálogo lo indica; se instala igualmente, pero no aparece en Live View hasta que alguno lo use."
  - id: drive
    title: "Míralo en tu próximo viaje"
    body: |
      Una vez instalado, la tienda indica que el paquete llega a tu comma cuando este teléfono lo alcanza, y que empieza ahí cuando el coche está apagado. En tu próximo viaje, abre Live View: el paquete dibuja en las pantallas comma four, comma 3X y CommaView, bajo las alertas propias de la pantalla de conducción.

      Para desactivar un paquete, abre **Tus paquetes**: cada paquete tiene un único interruptor, para este teléfono y todos los commas emparejados a la vez.
check: "En **Detalles** de Live View, la línea **Paquetes de superposición** nombra el paquete y dice que está **en ejecución**."
fixes:
  - q: "El selector de pantalla de conducción está atenuado"
    a: "Hay una grabación en curso. Detenla, o espera a que termine, y luego cambia."
  - q: "Detalles dice que el paquete «no es para este fork»"
    a: "El paquete está hecho para la pantalla de otro fork y no dibuja nada en la tuya. Los paquetes oficiales indican para qué forks son en **Funciona en**."
  - q: "El paquete aún no aparece en Live View"
    a: "Llega a tu comma cuando tu teléfono se conecta a él, y empieza ahí cuando el coche está apagado. Apaga y vuelve a encender el coche con tu teléfono en la red del comma, y luego abre Live View."
  - q: "«Inicia sesión para ver los paquetes de CommaView»"
    a: "La tienda muestra los paquetes de CommaView a los miembros con la sesión iniciada. Toca **Iniciar sesión**. Los paquetes que ya están en el teléfono siguen funcionando sin la sesión iniciada."
  - q: "«No se puede acceder a my.commaview.com»"
    a: "Comprueba la conexión a internet de este teléfono y toca **Reintentar**. **Tus paquetes** sigue mostrando todo lo que hay en el teléfono."
related: [live-view, record, forks]
blogPost: commaview-0-0-166-languages-browser-view
---

## Las opciones de cada pantalla

Bajo la vista previa, **Ajustes › Pantalla** muestra las opciones propias de la pantalla elegida:

- **Opciones de comma four**: **Encuadre de la vista previa** (igualar exactamente el encuadre del comma four, mostrar más de la cámara o recortarla para llenar esta pantalla) y **Panel de confianza compacto** (un panel y una bola más pequeños, para ver más vídeo).
- **Opciones de CommaView**: **Encuadre de la cámara** (**Rellenar** recorta la cámara para llenar una pantalla horizontal; **Cámara completa** la muestra entera, con franjas negras donde haga falta) y **Reducir movimiento**, que deja quietos la trayectoria, la velocidad y el enganche de CommaView.
- **comma 3X**: ninguna. Se dibuja como la dibuja el comma.

Después, **En todas las pantallas**: **Posición del conductor**, que refleja los controles, **Tema**, **Contraste diurno** para el sol y los reflejos, y **Bordes de la pantalla** para una pantalla del coche que corta los bordes de la imagen ([pantallas del coche](/es/guides/car-screens)).

Una reproducción que creas en Grabaciones dibuja lo que Live View dibujaba mientras grababas, elijas lo que elijas después.

## De dónde viene una superposición

CommaView no adivina qué dibujar. El entorno de ejecución de tu comma envía, junto al vídeo, los mismos datos de conducción que lee la propia pantalla de openpilot (la trayectoria, los carriles, el coche de delante, las velocidades, las alertas, la supervisión del conductor), y la app los dibuja en tu teléfono, alineados con la cámara que muestra. Cuando esos datos llegan tarde, faltan o son para otra cámara, CommaView deja fuera esa parte en lugar de dibujar algo que podría estar mal.

## Seguridad

Elige la pantalla e instala paquetes estacionado. No manejes CommaView mientras conduces: mantén la vista en la carretera y las manos en el volante, como pide openpilot. Una superposición es algo que mirar, no una ayuda a la conducción: las alertas de tu comma y los instrumentos de tu coche van primero. El icono de supervisión del conductor no demuestra atención, y la superposición de una reproducción sirve para repasar un viaje, no como prueba de lo que pasó exactamente.
