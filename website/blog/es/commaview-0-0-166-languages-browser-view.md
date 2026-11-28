---
title: "CommaView 0.0.166: una clave para cada teléfono, 11 idiomas más y Browser View"
description: "CommaView 0.0.166 da a cada teléfono una clave, habla 11 idiomas más, muestra Live View en el navegador de tu coche, guarda viajes en tu teléfono y abre la tienda de paquetes."
date: 2026-11-16
slug: commaview-0-0-166-languages-browser-view
tags:
  - security
  - languages
  - browser view
  - recordings
  - overlay packs
heroLabel: "Notas de versión"
draft: false
---

CommaView 0.0.166 ya está disponible para todos en la beta. Con el nuevo entorno de ejecución, **cada teléfono recibe su propia clave** para tu comma, y nadie tiene que volver a emparejar. CommaView habla **11 idiomas más**, muestra Live View en el navegador web de tu coche con **Browser View**, guarda tus viajes en tu teléfono con **Guardar este momento**, **Exportar el viaje completo…** y **Traer viajes automáticamente**, y abre la **tienda de paquetes de superposición**.

Llega con el entorno de ejecución `v0.0.62-beta`. **Actualiza primero CommaView**, luego el entorno desde la app cuando te lo ofrezca, y reinicia el comma cuando la app te lo pida. Un teléfono que siga en 0.0.165 sigue funcionando durante 90 días después de que el primer teléfono de tu comma reciba su clave. No vuelvas a configurar tu comma desde un teléfono con 0.0.165: la configuración desde él vuelve a poner el entorno antiguo, y los teléfonos con clave no pueden llegar al comma con él.

## Una clave para cada teléfono

Con el nuevo entorno de ejecución, cada teléfono recibe su propia clave para tu comma, en lugar del token compartido que enviaban todos los teléfonos. La clave nunca cruza la red y nadie tiene que volver a emparejar: un teléfono con 0.0.166 recibe su clave la próxima vez que se conecta.

- **Un teléfono nuevo tiene clave.** Cada teléfono con clave recibe un aviso cuando otro recibe una, con **Es mío**, **Quitar** y **Revisar teléfonos**, que abre **Ajustes del dispositivo › Emparejar otro teléfono**, donde aparecen todos los teléfonos con clave.
- **Añadir un teléfono.** **Mostrar invitación** en un teléfono con clave da un código o un código QR, válido durante 10 minutos.
- **Apps anteriores.** Tu comma acepta el antiguo token compartido durante 90 días después de que su primer teléfono reciba una clave, o hasta que alguien toque **Detener ya**. Hasta entonces, **Código de emparejamiento para una app anterior** empareja un teléfono con una versión anterior de CommaView. Después, un teléfono sin clave necesita 0.0.166 y una invitación.

## CommaView en tu idioma

**Ajustes › Idioma** ahora ofrece Deutsch, Español, Français, 日本語, 한국어, Português (Brasil), ไทย, Türkçe, Українська, 简体中文 y 繁體中文 además del inglés. **Idioma del teléfono**, la opción predeterminada, toma el primer idioma de la lista de tu teléfono que tenga CommaView, o si no el inglés, y la fila dice cuál está usando. En Android 13 y posterior, también funciona el ajuste de idioma por app de Android.

Todos los idiomas salvo el inglés están **traducidos automáticamente**, y ningún hablante nativo ha revisado ninguno todavía, así que espera palabras equivocadas y frases torpes. Una tarjeta en lo alto de Ajustes lo avisa, y **Ayuda a mejorarla** abre las traducciones de CommaView, donde cualquiera puede proponer una palabra mejor. También puedes decírnoslo en [Discord](https://discord.gg/UuMhz9K8ft) o desde **Informar de un problema o enviar una idea**: indica la pantalla y lo que dice ahora.

- **Las pantallas de tu comma siguen en el idioma de tu comma.** Las etiquetas de un fork y las alertas de tu comma se dibujan como las muestra tu coche, ahora con la fuente propia del fork cuando tu comma está en chino, japonés, coreano o tailandés.
- **El texto en inglés es el que vale** para el consentimiento de la clasificación, y **Ver en inglés** lo muestra. La política de privacidad y los términos están en inglés.
- **Las fechas** siguen el orden de tu idioma, y el título y la descripción de YouTube de Transmitir, hasta que los cambies, están en el idioma de la app.
- **El coreano** mantiene las palabras enteras al final de una línea. En Android 13 y anteriores, un nombre en coreano que hayas dado a un comma o a un lugar todavía puede partirse.

## Browser View

Browser View muestra lo que muestra Live View en el navegador web de tu coche, servido por tu teléfono a través de su punto de acceso o del Wi‑Fi. Inícialo desde **Live View › Detalles › Browser View**, escribe el enlace corto, `commaview.app/<code>`, en el navegador del coche y toca **Abrir**. En un Tesla, primero **Activar dirección VPN**.

La imagen va de tu teléfono al coche, nunca por internet; solo la página del enlace corto lo hace. Con la sesión iniciada, tu teléfono recibe un nombre propio y un certificado de confianza, así que un Tesla muestra un candado y la imagen H.264, más fluida. Sin sesión iniciada, un Tesla recibe la imagen básica.

- **Controles en el coche**: **Grabar**, **Guardar**, **Mapa**, la pantalla de conducción, **Transmitir** y **Cámara int.**, junto a la imagen o debajo, nunca encima.
- **¿Sin internet en el coche?** **Mostrar direcciones** muestra las direcciones propias del teléfono.
- 720p o 1080p, códigos de ocho dígitos, e **Iniciar con Live View** para que arranque cada vez que se abre Live View.

Cada paso, incluido el de un Tesla: [Browser View](/es/guides/browser-view).

Mientras funciona, tu teléfono envía al servicio de cuentas de CommaView su código, sus puertos y su dirección privada, para que el enlace corto pueda encontrarlo. Cualquiera con el código puede verlos, y el nombre `commaview.app` de tu teléfono, mientras Browser View funciona y hasta 2 horas después si se detiene de forma inesperada, pero ninguno abre nada sin el punto de acceso o el Wi‑Fi de tu teléfono. Se eliminan 30 días después de la última vez que funcionó Browser View. El nombre `commaview.app` de tu teléfono y la fecha de su último certificado se conservan mientras exista tu cuenta, y el nombre aparece en los registros públicos de certificados. [La política de privacidad](/privacy) (en inglés) tiene los detalles.

## Tus viajes en tu teléfono

- **Guardar este momento.** **Guardar** en Live View conserva los últimos 3 minutos y el minuto siguiente de un viaje; otro toque dentro de ese minuto añade un minuto, hasta 10 minutos. No se descarga nada mientras conduces: cuando aparcas, se copia en un MP4 en tu teléfono.
- **Exportar el viaje completo…** En el menú **Más** de un viaje: la cámara de carretera en un solo MP4, en partes si pasa de 3,5 GB. La hoja dice cuánto ocupa y si cabe antes de descargar nada.
- **Traer viajes automáticamente.** **Ajustes › Grabaciones**: los viajes nuevos se copian a casa más o menos cada media hora en las redes Wi‑Fi que elijas, solo por Wi‑Fi, hasta el espacio que les des. Una hora de conducción son unos 4,5 GB.
- **¿Se quedó sin corriente?** **Grabaciones** avisa cuando tu comma se quedó sin corriente al terminar un viaje, y dice cómo solucionarlo.

Todo es la cámara de carretera sin HUD, y se queda en tu teléfono aunque tu comma borre el viaje al rotar.

## Paquetes de superposición

**Ajustes › Paquetes de superposición**, o la tarjeta de **Inicio**, abre la tienda. Los paquetes añaden a Live View lo que tu fork dibuja en su propia pantalla, como los indicadores híbridos de BluePilot o la trayectoria arcoíris de dragonpilot. Los miembros exploran los paquetes **Oficiales** de CommaView, los de la **Comunidad** y **Para tu comma**, cada uno con una vista previa para el diseño que dibuja Live View. **Tus paquetes** tiene un interruptor para tu teléfono y cada comma emparejado. Sin membresía, puedes añadir un paquete desde un archivo o un enlace.

## También en 0.0.166

- **Navegación con tu propia clave de Stadia Maps**, para miembros: **Ajustes › Mapas y navegación › Tu clave de Stadia Maps**.
- **BluePilot, dragonpilot y OPGM** pasan a ser forks de la lista, con el nuevo entorno de ejecución. Ninguno se ha conducido aún con CommaView.
- **Live View en más pantallas del coche**: cuando el decodificador de vídeo del teléfono no puede reproducir el vídeo del comma, prueba otro.
- **Abrir CommaView solo** cuando arranca una pantalla del coche o se conecta el Bluetooth, y **Abrir Live View al conectar**, en **Ajustes › Pantalla**. Para usar CommaView en la pantalla de tu propio coche: [las mejores cajas de IA Android](/es/blog/android-ai-box-commaview).
- **Compartir con el desarrollador de mi fork…**: un clip, un resumen y el registro de CommaView, para que lo compartas tú.
- **Live View dice qué pasa**: un reinicio que está esperando, datos del coche que dejaron de llegar, una imagen con retraso, por qué se está reconectando, otro dispositivo que lo tiene abierto.
- **Actualizar CommaView**, para miembros, desde 0.0.166: primero la versión, **Cancelar descarga**, y la descarga sigue en segundo plano.
- **Bordes de la pantalla**, destinos de Transmitir para cada plataforma, y nada cortado con texto grande.

## Acceso anticipado

Transmitir a X, Twitch, Kick y Facebook, **Solo vídeo** para FrogPilot y KisaPilot, los ajustes del fork, la creación de paquetes de superposición y Surround siguen activados por cuenta, para un grupo limitado de testers. Si quieres ayudar a probarlos, escríbenos en nuestro [Discord](https://discord.gg/UuMhz9K8ft) y prepárate para contarnos qué tal van en tus viajes.

## Cómo actualizar

CommaView está en una beta solo por invitación. Si estás dentro, la app te ofrece 0.0.166 por sí sola. Actualiza CommaView, luego el entorno de ejecución de tu comma desde la app, y reinicia el comma cuando te lo pida. Actualiza cada teléfono y pantalla del coche que vea tu comma en los 90 días siguientes a que el primero reciba su clave.

## Para saber más

- [Qué forks de openpilot funcionan con CommaView](/forks)
- [Novedades](/whats-new) de cada versión
- [Cómo funcionan las versiones de CommaView](/es/guides/releases)

CommaView no es oficial ni está afiliado a comma.ai, BluePilot, dragonpilot, OPGM ni los demás forks mencionados. Es software beta y no es un sistema de seguridad: nunca dejes que te distraiga de la conducción.
