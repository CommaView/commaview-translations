---
title: "CommaView 0.0.164: carrotpilot, SunnyPilot-TeslaHW1 y copias en vivo"
description: "CommaView 0.0.164 añade carrotpilot y SunnyPilot-TeslaHW1, y copias en vivo que guardan lo que muestra Live View mientras conduces. Y acceso anticipado a Navegación y Surround."
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot forks
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - recordings
heroLabel: "Notas de versión"
draft: false
---

CommaView 0.0.164 ya está disponible para todos en la beta. Añade dos forks de openpilot más, **carrotpilot** y **SunnyPilot-TeslaHW1**, así que CommaView ya funciona con siete: openpilot, sunnypilot, StarPilot, el openpilot de xnor-tech, AdventurePilot, SunnyPilot-TeslaHW1 y carrotpilot. También trae las **copias en vivo**, que guardan lo que muestra Live View mientras conduces, listas en cuanto te detienes.

Llega con el entorno de ejecución `v0.0.60-beta`, que reconoce los dos forks nuevos. Actualiza el entorno desde la app cuando te lo ofrezca y reinicia el comma cuando la app te lo pida.

## SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 es un fork de sunnypilot que añade los coches Tesla HW1 (Autopilot 1). Su pantalla es la de sunnypilot, así que CommaView dibuja la pantalla de sunnypilot con todo lo que sunnypilot añade, y muestra el nombre del fork en la app.

Algo que conviene saber: su `op fork update` no puede cambiar el fork mientras el hook de CommaView está instalado. Desinstala CommaView primero, o usa el selector de forks de la pantalla del comma, que funciona como siempre.

## carrotpilot

carrotpilot es un fork de openpilot para coches Hyundai, Kia y Genesis, que se instala desde `i.carrotpilot.app`. CommaView dibuja para él la pantalla de openpilot, con tu velocidad, la trayectoria, los carriles y el vehículo delantero, y muestra el nombre del fork en la app.

Dos límites, por ahora:

- **La pantalla propia de carrotpilot aún no se dibuja.** Lo que añade a la pantalla de openpilot, como su navegación, los radares de velocidad y su HUD, no aparece en Live View.
- **Sus actualizaciones quitan el hook de CommaView hasta que el comma se reinicia.** La actualización automática de carrotpilot y las herramientas de Git de su página web restablecen sus archivos mientras funciona. No se rompe nada: la app pide un reinicio y Live View vuelve después.

## Copias en vivo

Hasta ahora, **Grabar** hacía una reproducción: cuando aparcas, la app descarga el vídeo del propio comma y dibuja el HUD encima. Sigue siendo la mejor imagen, pero tarda un rato después del viaje y se detiene a los 10 minutos por grabación.

Ahora **Ajustes › Grabaciones › Grabar en Live View** te deja elegir qué hace **Grabar**:

| Opción | Qué obtienes |
| --- | --- |
| **Reproducción** (la predeterminada) | El vídeo del propio comma con el HUD dibujado encima, hecho cuando aparcas. La mejor imagen, hasta 10 minutos por grabación. |
| **Copia en vivo** | Lo que muestra Live View mientras conduces, guardado en tu teléfono y listo en **Grabaciones** en cuanto te detienes, sin límite de 10 minutos. |
| **Ambas** | Una copia en vivo ahora, y la reproducción después del viaje. |

Una copia en vivo es de 720p (unos 1,4 GB por hora) o 1080p (unos 2,3 GB por hora), a 20 fotogramas por segundo. Sigue grabando mientras cambias de app o bloqueas el teléfono, con una notificación desde la que puedes detenerla. Se detiene limpiamente antes de que se llene el almacenamiento de tu teléfono y, si la app se cierra mientras graba, conservas todo menos el último minuto.

Las copias en vivo se quedan en tu teléfono y nunca se suben.

## También en 0.0.164

- **Ajustes que usan toda la pantalla.** **Grabaciones**, **Pantalla** y **Transmisión en vivo** se organizan como **Mapas sin conexión**, en dos columnas donde caben, y se alinean en tablets, pantallas del coche y teléfonos en horizontal.
- **Por qué falló una instalación.** Si falla la configuración, una actualización del entorno o una desinstalación, la app dice qué salió mal y qué hacer: un fork que CommaView no admite, el coche en marcha, el comma sin internet, una descarga dañada. Dice si tu comma quedó como estaba, y **Copiar detalles** copia el informe que necesita el soporte.
- **Reproducciones más rápidas.** Una reproducción descarga solo el vídeo que muestra, y el siguiente viaje de la cola se descarga mientras se hace otro. Una grabación interrumpida porque se cerró la app, por el límite de 10 minutos o porque se apagó el coche ahora también se puede convertir en reproducción.
- **La calidad de la reproducción vuelve a funcionar.** Balanced, High y Max vuelven a hacer reproducciones distintas: todas se estaban haciendo a los mismos 40 Mbit/s. High, la predeterminada, ahora hace archivos de más o menos la mitad de tamaño desde un comma 3X.

## Acceso anticipado: Navegación y Surround

Algunas funciones están en desarrollo temprano: **Navegación**, **Surround**, **Transmitir** y **Enviar a CommaView**. Las estamos abriendo a un grupo limitado de testers, activadas por cuenta, mientras recogemos opiniones, así que solo aparecen en las cuentas que las tienen activadas.

- **Navegación** son indicaciones paso a paso desde **Inicio** hasta Live View: busca un lugar, elige una ruta y sigue la tarjeta de giro, las indicaciones por voz y, en la pantalla de CommaView, los chevrones pintados en tu carril. Si te equivocas de giro, encuentra una ruta nueva en segundos. Solo muestra: no se envía nada a tu comma ni a tu coche.
- **Surround** es una vista 3D de la carretera alrededor de tu coche: la carretera como la ve la cámara, con sus líneas de carril y sus cruces, y los coches, camiones y semáforos a tu alrededor.

Algunas funcionan con servicios de pago, como el cálculo de rutas de Navegación, así que mantenemos el grupo pequeño hasta saber cuánto cuesta un uso normal. Si quieres ayudar a probarlas, escríbenos en nuestro [Discord](https://discord.gg/UuMhz9K8ft) y prepárate para contarnos qué tal van en tus viajes.

## Cómo conseguirlo

CommaView está en una beta solo por invitación. Si estás dentro, la app te ofrece la actualización 0.0.164 por sí sola. Cuando se actualice, actualiza el entorno de ejecución de tu comma desde la app y reinicia el comma cuando te lo pida. Las actualizaciones del entorno esperan a que el coche esté en P con openpilot desactivado, así que nunca interrumpen un viaje.

¿Eres nuevo en CommaView? La [guía de configuración](/es/guides/setup) explica cómo instalar la app y conectar tu comma.

## Para saber más

- [Qué forks de openpilot funcionan con CommaView](/forks), incluidos [SunnyPilot-TeslaHW1](/forks#teslahw1) y [carrotpilot](/forks#carrotpilot)
- [Novedades](/whats-new) de cada versión
- [Cómo funcionan las versiones de CommaView](/es/guides/releases)

CommaView no es oficial ni está afiliado a comma.ai, sunnypilot, carrotpilot ni SunnyPilot-TeslaHW1. Es software beta y no es un sistema de seguridad: nunca dejes que te distraiga de la conducción.
