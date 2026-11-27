---
title: "CommaView 0.0.165: Transmitir para todos, Enviar a CommaView y detección de coches"
description: "CommaView 0.0.165 abre Transmitir a todos y Enviar a CommaView a cada miembro, permite aportar viajes a la detección de coches y añade más forks de openpilot, sin garantías."
date: 2026-11-01
updatedDate: 2026-11-13
slug: commaview-0-0-165-go-live-send-to-commaview
tags:
  - live streaming
  - YouTube
  - recordings
  - openpilot forks
  - privacy
heroLabel: "Notas de versión"
draft: false
---

CommaView 0.0.165 ya está disponible para todos en la beta. **Transmitir** ya es para todos, y **Enviar a CommaView** para cada miembro, con un viaje o varios a la vez. Con el nuevo entorno de ejecución, los miembros pueden **aportar viajes a la detección de coches**, CommaView ahora se instala en **más forks de openpilot**, sin garantías, y las cámaras y los datos de tu comma van **solo a los teléfonos emparejados con él**.

Llega con el entorno de ejecución `v0.0.61-beta`. **Actualiza primero CommaView en cada teléfono y pantalla del coche que vea tu comma**, luego actualiza el entorno desde la app cuando te lo ofrezca y reinicia el comma cuando la app te lo pida. Un teléfono o una pantalla del coche que se quede en 0.0.164 o anterior no recibe vídeo de un comma con el entorno v0.0.61 o posterior.

## Transmitir

**Transmitir** estaba en acceso anticipado en 0.0.164. Ahora es para todos: **Transmitir** en Live View emite lo que muestra Live View, la carretera y la superposición de CommaView, a tu canal de YouTube o a cualquier servidor RTMP, a 720p o 1080p.

Configúralo una vez en **Ajustes › Transmisión en vivo**: **Iniciar sesión con YouTube**, que crea, inicia y termina cada emisión por ti, o guarda una clave de transmisión o un servidor. Después, **Transmitir** aparece en Live View, o en su menú **Más** cuando la pantalla no tiene sitio.

- **Quién puede verla** tiene su propia fila en **Ajustes › Transmisión en vivo** y empieza en **No listado**. Quien la vea sabe por dónde conduces.
- El **Sonido** está desactivado salvo que elijas el micrófono de tu comma o el de tu teléfono. Va a tu transmisión y a tus copias en vivo, nunca a CommaView.
- Cuando el Wi‑Fi de tu comma no tiene internet, la transmisión usa los datos móviles de tu teléfono. Ajustes indica más o menos cuántos por hora.
- El inicio de sesión con YouTube y **Transmitir** ahora funcionan cuando una VPN es la red predeterminada de tu teléfono.

El mapa y la tarjeta de giro de Navegación nunca aparecen en una transmisión.

## Enviar a CommaView

**Enviar a CommaView** ya es para cada miembro. En **Grabaciones**, elige un viaje que haya grabado tu comma, o selecciona varios, y luego **Enviar a CommaView** con una nota sobre lo que pasó. Recibimos el vídeo de carretera y gran angular de cada viaje y su registro, para poder ver el problema; nunca la cámara del conductor, el sonido ni el VIN de tu coche.

Cada viaje se descarga de tu comma antes de subirse, de uno en uno y empezando por el más antiguo, así que mantén el comma encendido y aparcado hasta que termine. CommaView acepta 20 subidas al día por cuenta; las demás esperan al día siguiente.

La misma hoja **Enviar a CommaView** ahora lleva todo lo que nos envías: un **Problema** o una **Idea**, tu nota y cada adjunto, que puedes abrir con **Ver** o dejar fuera. Se abre desde **Ajustes › Soporte y diagnóstico**, desde el botón **Informar** de cualquier error y desde el menú **Más** de una grabación.

## Contribuir a la detección de coches

Surround, todavía en acceso anticipado, ejecuta su propio detector de coches en tu teléfono. Ahora los miembros pueden ayudar a entrenarlo con sus viajes. Necesitas el nuevo entorno de ejecución en tu comma.

- **Con un toque:** **Contribuir a la detección de coches**, en el menú **Más** de un viaje, o para varios viajes seleccionados.
- **Automáticamente:** activa **Contribuir viajes automáticamente** en **Ajustes › Privacidad y uso compartido › Detección de coches**. Los viajes recientes de tu comma se suben, cualquier viaje que aún tenga, cuando tu teléfono y el comma están en una red que permites, hasta un límite diario. No con el ahorro de batería activado, ni mientras usas Live View o grabas.

**Subir contribuciones en** elige esas redes. **Redes que elija**, la opción predeterminada, muestra los datos móviles de tu teléfono y los Wi‑Fi que tiene guardados tu comma; marca los que quieras usar, cada uno con un límite mensual si lo quieres. Las contribuciones ocupan unos 110 MB por minuto de viaje. Cuando tu comma se une a un Wi‑Fi que no había usado, **Inicio** y una notificación te preguntan si quieres añadirlo. Tu comma dice en qué red está, así que CommaView no necesita tu ubicación.

Ten claro lo que das antes de darlo:

- **Una contribución es el viaje completo:** su vídeo de carretera y gran angular y su registro, incluido por dónde fue, de principio a fin.
- **Es para siempre.** Pasa a formar parte de la colección de entrenamiento de CommaView y no se puede retirar después. Nada la vincula a ti ni a tu comma.
- **comma connect espera.** Mientras se envía un viaje, tu comma lo guarda hasta un día para que openpilot no lo borre, y mientras tanto el subidor de openpilot lo salta.

La app explica esto una vez antes de tu primera contribución, y contribuir sigue desactivado hasta que lo activas.

## Más forks de openpilot, sin garantías

CommaView ahora se instala en más forks de openpilot, sin garantías. Muestra openpilot y seis de sus forks, y comprueba cada uno antes de cada versión. En cualquier otro fork de openpilot, la configuración se detenía. Ahora comprueba el fork, sin cambiar nada, y si CommaView puede añadir su vista, dice "CommaView no ha verificado este fork": qué se dibuja (las cámaras, la trayectoria, los carriles, el vehículo delantero, las alertas y la velocidad) y qué no. **Instalar de todos modos** instala solo en ese fork.

Live View lo dibuja con el aspecto de openpilot, o con el de sunnypilot cuando el fork parte de la pantalla de sunnypilot, y muestra su nombre, como "BluePilotDev/bluepilot · best effort". **Desinstalar entorno**, en **Ajustes del dispositivo**, devuelve los archivos del fork a su sitio.

Comprobado en noviembre de 2026: dragonpilot, BluePilot, crwusiz, opgm, zoompilot, el Carrot de jixiexiaoge, NotAutopilot y otros pasan su comprobación de instalación; no se han probado en un coche. [Los forks y las ramas comprobadas](/forks#install-check) están en la página de forks compatibles.

Dos límites:

- **Sin garantías.** Las versiones de CommaView no se comprueban con tu fork. Si el fork se actualiza a algo que CommaView no puede seguir, la vista de CommaView se desactiva y el fork conduce como siempre.
- **La pantalla propia del fork no se dibuja.** Sus botones, colores y widgets no aparecen en Live View, y los forks basados en la antigua pantalla nativa de openpilot no son compatibles en absoluto.

## Solo teléfonos emparejados

Con el nuevo entorno de ejecución, las cámaras y los datos de tu comma solo van a los teléfonos y pantallas del coche emparejados con él. Cuando otro tiene la cámara, Live View dice "Otro dispositivo está usando la cámara de este comma" y vuelve a intentarlo solo.

Las instalaciones del entorno ahora también se recuperan. Un corte de corriente o un reinicio a mitad de la instalación devuelve la versión anterior, una instalación sigue adelante cuando la app deja de escuchar, y una descarga que se atasca continúa donde se quedó.

## También en 0.0.165

- **Varios viajes a la vez.** Selecciona viajes en **Grabaciones** para compartirlos, hacer sus reproducciones, enviarlos o eliminarlos juntos.
- **Live View cabe en cualquier pantalla.** Sus controles ya no se desplazan ni cortan **Salir**: lo que no cabe va a **Más**, y un texto más grande mueve controles a **Más** en lugar de encoger nada. Live View también es más ligero para el teléfono, y se recupera solo en lugar de congelarse.
- **Tus solicitudes.** Cuando informas de un problema o envías una idea con la sesión iniciada, podemos responderte. **Ajustes › Soporte y diagnóstico › Tus solicitudes** muestra nuestras respuestas, recibes un correo y la conversación sigue en my.commaview.com.
- **Ajustes reorganizados.** **Privacidad y uso compartido** dice qué sale de tu teléfono. **Ayuda a mejorar CommaView** pregunta una vez si enviar informes de fallos y qué software de conducción usa tu comma.
- **La clasificación, para cada miembro.** Ya no depende de una activación por cuenta.
- **Modo experimental en openpilot más reciente.** En la nightly de openpilot y en sunnypilot dev, donde el modo chill ya no existe, Live View muestra el modo experimental como lo hace openpilot.
- **Apoyar a CommaView.** **Ajustes › Soporte y diagnóstico › Apoyar a CommaView** abre nuestra página de [Buy Me a Coffee](https://buymeacoffee.com/commaview), para ayudar a cubrir el alojamiento, las pruebas y la app de iOS. No desbloquea nada.
- **Correcciones.** Una pantalla del coche con Android 16 ya no cierra CommaView en Live View cuando falla su decodificador de vídeo, y la pantalla del comma 3X de StarPilot dibuja su cámara en las pantallas del coche que la mostraban en negro.

## Acceso anticipado: Navegación y Surround

**Navegación**, **Surround**, **Surround V2** y **Herramientas experimentales** siguen con un grupo limitado de testers, activadas por cuenta, mientras recogemos opiniones.

- **Navegación** ahora muestra un mapa en Live View durante un trayecto, junto al vídeo o en su esquina, y **¿Adónde vas?** cuando no hay trayecto. En el mapa de la esquina, terminar y silenciar están siempre a mano, terminar se puede deshacer durante 8 segundos, y puedes decir adónde ir.
- **El mapa de Navegación** ahora tiene temas **Claro** y **Oscuro**, que cambian al amanecer y al anochecer donde está tu comma, para que se lea bien al sol. Elige **Auto**, **Igual que el teléfono**, **Claro** u **Oscuro** en **Ajustes › Mapas y navegación › Tema del mapa**.
- **Surround V2** es un segundo renderizador experimental para Surround, en **Ajustes › Herramientas experimentales**.

Algunas funcionan con servicios de pago, como el cálculo de rutas de Navegación, así que por ahora mantenemos el grupo pequeño. Si quieres ayudar a probarlas, escríbenos en nuestro [Discord](https://discord.gg/UuMhz9K8ft) y prepárate para contarnos qué tal van en tus viajes.

## Cómo actualizar

CommaView está en una beta solo por invitación. Si estás dentro, la app te ofrece 0.0.165 por sí sola.

1. Actualiza CommaView en **cada teléfono y pantalla del coche** que uses con tu comma.
2. Después, actualiza el entorno de ejecución de tu comma desde la app.
3. Reinicia el comma cuando la app te lo pida. Las actualizaciones del entorno esperan a que el coche esté en P con openpilot desactivado, así que nunca interrumpen un viaje.

¿Eres nuevo en CommaView? La [guía de configuración](/es/guides/setup) explica cómo instalar la app y conectar tu comma.

## Para saber más

- [Qué forks de openpilot funcionan con CommaView](/forks), y [los forks que no figuran](/forks#unlisted)
- [Novedades](/whats-new) de cada versión
- [Cómo funcionan las versiones de CommaView](/es/guides/releases)
- [Política de privacidad](/privacy) (en inglés), sobre lo que comparten Transmitir, Enviar a CommaView y las contribuciones

CommaView no es oficial ni está afiliado a comma.ai, sunnypilot ni ningún fork de openpilot con el que funciona. Es software beta y no es un sistema de seguridad: nunca dejes que te distraiga de la conducción.

## Corrección, 13 de noviembre de 2026

En **Contribuir a la detección de coches**, esta entrada decía que nada en una contribución la vincula a ti ni a tu comma. Eso era ir demasiado lejos. Una contribución no te nombra ni a ti ni a tu comma, pero la ruta y el vídeo de un viaje pueden mostrar por dónde conduces. Desde la próxima versión de la app, la app lo dice y te pide que vuelvas a aceptar antes de tu siguiente contribución; la [política de privacidad](/privacy) ya decía que una contribución incluye la ruta del viaje. El resto de la entrada sigue como se publicó.
