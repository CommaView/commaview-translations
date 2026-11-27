---
title: "Comprueba que tu comma y tu fork son compatibles"
description: "CommaView funciona con openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot y OPGM, y sin garantías con otros forks."
topic: start
order: 2
kind: reference
lede: "CommaView muestra la cámara de carretera de tu comma con la superposición de conducción del software que usa. Funciona con openpilot y nueve de sus forks, en el comma 3X y el comma four, y, sin garantías, con otros forks de openpilot. La configuración comprueba qué fork usa tu comma antes de cambiar nada."
updated: 2026-11-27
needs:
  - title: "Un comma 3X o comma four"
    text: "El comma 3 no es compatible, tampoco las versiones de los forks para comma 3 como xnor-c3. [Por qué el comma 3 no es compatible](/es#faq-comma-3)."
  - title: "Tu fork, tal como funciona"
    text: "Instalado y funcionando como siempre. CommaView añade su entorno de ejecución a su lado y nunca cambia cómo conduce."
steps:
  - id: unlisted
    title: "En un fork que CommaView no incluye, la configuración te pregunta antes"
    body: |
      La configuración guiada comprueba de qué repositorio se instaló el software de tu comma e instala el hook de CommaView para ese fork. En un fork que no incluye, primero comprueba el fork, sin cambiar nada.
    tabs:
      - label: "Sin garantías"
        body: "Si CommaView puede añadir su vista, la configuración muestra **CommaView no ha verificado este fork**. Nombra el fork por su repositorio y explica qué se dibuja (las cámaras, la trayectoria, los carriles, el coche de delante, las alertas y la velocidad) y qué no (los botones, colores y widgets propios del fork). **Instalar de todos modos** instala en ese fork, y solo en ese. **Atrás** vuelve a la elección del comma; no se instaló nada."
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**Instalar de todos modos** añade la vista de CommaView a este fork, sin garantías."
      - label: "Solo vídeo (acceso anticipado)"
        body: "Para FrogPilot y KisaPilot, cuyas pantallas no admiten la vista de CommaView, los probadores con la opción Solo vídeo ven **Solo vídeo en este fork**: CommaView transmite las cámaras y dibuja su propia vista con los datos de conducción, sin cambiar nada en el fork. Aún no se ha probado en un comma. Sin la opción, la configuración dice que el fork no es compatible y no cambia nada."
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**Instalar solo vídeo**."
    note: "Cuando la comprobación rechaza un fork, la configuración dice «CommaView no puede añadir su vista a … de forma segura» y «No se cambió nada en tu comma.»"
  - id: details
    title: "Mira qué fork dibuja Live View"
    body: |
      En Live View, abre **Detalles**. La línea **Software** nombra el fork de tu comma, y un fork que CommaView no incluye aparece con su repositorio, por ejemplo «crwusiz/openpilot · best effort».
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**Detalles**, bajo la imagen."
      - text: "**Software**: el fork que usa tu comma."
related: [setup, overlays, uninstall]
---

## Forks compatibles

| Fork | De dónde viene | Compatible desde |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | La primera beta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | La primera beta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot, antes github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor** (versiones xnor y rx) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot, instalado desde i.carrotpilot.app | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

En un fork que no incluye, la configuración comprueba si CommaView puede añadir su vista y te pregunta antes; si no puede, se detiene y deja tu comma como estaba.

## Qué muestra cada fork

### openpilot

El software propio de comma.ai. Live View dibuja la pantalla del comma four, la del comma 3X o la superposición propia de CommaView, con tu velocidad, MÁX, el límite de velocidad, el coche de delante y los cambios de carril.

### sunnypilot

CommaView dibuja la pantalla de sunnypilot con lo que sunnypilot añade: los estados solo dirección y solo velocidad de MADS, la asistencia de límite de velocidad, la trayectoria arcoíris y los indicadores de punto ciego, y en la pantalla del comma 3X su señal de límite de velocidad, el control de crucero inteligente y la interfaz de desarrollador. Lee tus ajustes de sunnypilot, así que la pantalla coincide con la del comma.

### StarPilot

StarPilot muestra sus modos de conducción con colores, y CommaView usa los colores que eligió StarPilot: su borde, su trayectoria y sus widgets en las pantallas del comma four y del comma 3X, sus alertas y su elección de cámara, incluida la cámara del conductor.

Desactiva el ajuste **Disable Logging** de StarPilot. Detiene el codificador de vídeo desde el que transmite Live View.

### El openpilot de xnor-tech: xnor y rx

El openpilot de xnor-tech viene en dos versiones. Sus ramas **xnor** usan la pantalla de openpilot y sus ramas **rx** la de sunnypilot, cada una con los ports de coches de xnor-tech. CommaView dibuja la que use tu comma, con sus alertas tal como las escribe el comma.

En un Rivian con rx, el volante se pone verde mientras el coche gira por ángulo y azul mientras gira por par: el volante del comma four, y en la pantalla del comma 3X el del botón del modo experimental.

### AdventurePilot

AdventurePilot es un fork de sunnypilot con sus propios ports de coches. CommaView dibuja la pantalla de sunnypilot con lo que AdventurePilot añade:

- su indicador de centrado en el carril: una píldora con el empuje y el desplazamiento en la pantalla del comma 3X, una barra compacta en la del comma four;
- el chip CURVE en la pantalla del comma 3X, que parpadea mientras actúa el control de velocidad en curvas;
- el tinte del volante según el modo de dirección, y una barra de par que muestra la aceleración lateral mientras un Rivian gira por su canal de ángulo.

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 es un fork de sunnypilot que añade los coches Tesla HW1 (Autopilot 1). Su pantalla es la de sunnypilot, así que CommaView dibuja la pantalla de sunnypilot con todo lo que sunnypilot añade, y nombra el fork en la app.

Su `op fork update` no puede cambiar el fork mientras el hook de CommaView está instalado: primero [desinstala el entorno de ejecución de CommaView](/es/guides/uninstall), o usa el selector de forks en la pantalla del comma, que funciona como siempre.

### carrotpilot

carrotpilot es un fork de openpilot para coches Hyundai, Kia y Genesis, instalado desde `i.carrotpilot.app`. CommaView dibuja para él la pantalla de openpilot, con tu velocidad, la trayectoria, los carriles y el coche de delante. Lo que carrotpilot añade a su propia pantalla, como su navegación, los radares de velocidad y su HUD, aún no se dibuja.

La actualización automática de carrotpilot y las herramientas de Git de su página web quitan el hook de CommaView hasta que el comma se reinicia. La app pide el reinicio, y Live View vuelve después.

### BluePilot, dragonpilot y OPGM

Incluidos desde CommaView 0.0.166 con su entorno de ejecución. CommaView nombra cada uno y lo dibuja con el aspecto de su base: BluePilot como sunnypilot, dragonpilot y OPGM como openpilot, con el ALKA de dragonpilot mostrado como dirección. Un comma que usaba uno de ellos sin garantías pasa a él en el arranque siguiente a la actualización del entorno. Ninguno se ha conducido aún con CommaView. Los [paquetes de superposición](/es/guides/overlays) oficiales de CommaView dibujan más de las pantallas propias de BluePilot y dragonpilot.

## Forks que CommaView no incluye

Desde CommaView 0.0.165, con su entorno de ejecución en tu comma, la configuración puede añadir la vista de CommaView a un fork de openpilot que no incluye, sin garantías. Live View dibuja el fork con el aspecto de openpilot, o con el de sunnypilot cuando el fork parte de la pantalla de sunnypilot. Para deshacerlo, **Desinstalar entorno** en Ajustes del dispositivo deja los archivos del fork como estaban.

- **Sin garantías.** Las versiones de CommaView no se comprueban con tu fork. Si el fork se actualiza a algo que CommaView no puede seguir, la vista de CommaView se desactiva y tu fork conduce y muestra su propia pantalla como siempre, hasta que una versión de CommaView admita el cambio.
- **No todos los forks.** Los forks basados en la antigua pantalla nativa de openpilot no son compatibles (más abajo).
- **Tu sí vale para ese fork.** Si tu comma cambia a otro fork que CommaView no incluye, CommaView vuelve a preguntar en la configuración antes de añadir su vista ahí.

### Forks que pasan la comprobación de instalación (sin garantías)

Cada uno de estos **pasa la comprobación de instalación de CommaView; sin garantías, no probado en un coche.** Comprobado en noviembre de 2026, para las ramas indicadas, con el entorno de ejecución que instala CommaView 0.0.165: el instalador ofrece el fork, añade la vista de CommaView cuando aceptas y la comprueba, igual que haría en tu comma. Nada de esto se ha probado en un comma dentro de un coche, puede que un fork no admita todos los coches en ambos dispositivos, y la próxima actualización de un fork puede cambiar la respuesta.

| Fork | Ramas comprobadas | Dispositivos | Se dibuja como |
| --- | --- | --- | --- |
| **crwusiz** (github.com/crwusiz/openpilot) | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **Carrot de jixiexiaoge** (github.com/jixiexiaoge/openpilot) | Carrot | comma four, comma 3X | openpilot |
| **MoreTore** (github.com/MoreTore/openpilot) | release-mici | comma four | openpilot |
| **zoompilot** (github.com/zoompilot/zoompilot) | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato** (github.com/AlexandreSato/openpilot) | master | comma four, comma 3X | openpilot |
| **lukasloetkolben** (github.com/lukasloetkolben/openpilot) | master | comma four, comma 3X | openpilot |
| **mvl-boston** (github.com/mvl-boston/openpilot) | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub** (github.com/mouxangithub/openpilot) | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro** (github.com/programanichiro/openpilot) | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2** (github.com/infiniteCable2/openpilot) | master | comma four, comma 3X | sunnypilot |
| **herizon1054** (github.com/herizon1054/openpilot) | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot** (github.com/NotAutopilot/openpilot) | nap-release, naponsp-alpha | comma four, comma 3X | openpilot (nap-release), sunnypilot (naponsp-alpha) |

¿Tu fork no está aquí? Puede que funcione igualmente: la configuración lo comprueba antes de cambiar nada.

### No compatibles

Las pantallas de estos forks no admiten la vista de CommaView, así que la configuración lo indica y no cambia nada en tu comma:

- **FrogPilot** (github.com/FrogAi/FrogPilot). Usa la antigua pantalla nativa (Qt) de openpilot, que no tiene sitio para la vista de CommaView. Solo vídeo está en acceso anticipado.
- **KisaPilot** (github.com/kisapilot/openpilot). Su pantalla en Python está desactivada: usa la antigua pantalla nativa (Qt) de openpilot. Solo vídeo está en acceso anticipado.
- **IQ.Pilot** (github.com/IQLvbs/iqpilot). Desde octubre de 2026 funciona sobre su propio IQ.OS; la compatibilidad espera a que CommaView pueda admitirlo como un fork propio.
- **hikee9123** (github.com/hikee9123/openpilot). Usa la antigua pantalla nativa (Qt) de openpilot.

**Acceso anticipado: solo vídeo para FrogPilot y KisaPilot.** Con la opción Solo vídeo, la configuración ofrece reproducir sus cámaras en Live View con la superposición propia de CommaView en lugar de sus pantallas, sin cambiar nada en el fork. Aún no se ha probado en un comma. Sin la opción, la configuración sigue diciendo que no son compatibles y no cambia nada.

## Qué dispositivos comma

El comma 3X y el comma four. El comma 3 no es compatible, tampoco las versiones de los forks para comma 3 como xnor-c3: [por qué el comma 3 no es compatible](/es#faq-comma-3). La app funciona en un teléfono, una tablet o una pantalla del coche Android.

## Ramas de versión y de desarrollo

Antes de cada versión, el entorno de ejecución de CommaView se compila y se comprueba con las versiones de lanzamiento de estos forks. La rama nightly de openpilot y la rama dev de sunnypilot se comprueban cada día que cambian, como aviso temprano. Una rama de desarrollo puede cambiar más rápido que CommaView: si un cambio impide que se cargue el hook de CommaView, la pantalla y la conducción de tu fork siguen como siempre.

## ¿Tu fork no aparece?

Pruébalo sin garantías y pide que se incluya en el tablero de funciones de [my.commaview.com](https://my.commaview.com), o envía una idea desde la app (Ajustes › **Soporte y diagnóstico**). Un fork incluido se comprueba antes de cada versión. Consulta las [novedades](/whats-new) de cada versión.

## Preguntas

**¿CommaView cambia cómo conduce mi fork?** No. Añade un pequeño entorno de ejecución junto a tu fork y un pequeño hook en su interfaz de pantalla, para que CommaView pueda dibujar la misma trayectoria, los carriles y las alertas. La forma en que conduce tu coche no cambia.

**¿CommaView funciona con StarPilot?** Sí, desde CommaView 0.0.162. Live View muestra los colores, los widgets y la elección de cámara propios de StarPilot. Desactiva el ajuste **Disable Logging** de StarPilot, que detiene el codificador de vídeo desde el que transmite CommaView.

**¿CommaView funciona con carrotpilot?** Sí, desde CommaView 0.0.164. Live View dibuja para él la pantalla de openpilot; lo que carrotpilot añade a su propia pantalla, como su navegación y los radares de velocidad, aún no se dibuja. Cuando carrotpilot se actualiza solo, la app pide un reinicio que devuelve Live View.

**¿CommaView funciona con FrogPilot?** Todavía no: usa la antigua pantalla nativa (Qt) de openpilot, que no tiene sitio para la vista de CommaView, así que la configuración dice que no es compatible y no cambia nada. Solo vídeo está en acceso anticipado para FrogPilot y KisaPilot, para probadores.
