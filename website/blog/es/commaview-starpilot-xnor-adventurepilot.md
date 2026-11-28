---
title: "CommaView ya funciona con StarPilot, xnor y AdventurePilot"
description: "CommaView 0.0.163 añade el openpilot de xnor-tech y AdventurePilot, tras StarPilot en 0.0.162. Qué muestra cada fork de openpilot en Live View en el comma 3X y el comma four."
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "Notas de versión"
draft: false
---

CommaView ya funciona con cinco versiones de openpilot: **openpilot**, **sunnypilot**, **StarPilot**, **el openpilot de xnor-tech** (sus versiones xnor y rx) y **AdventurePilot**. StarPilot llegó en CommaView 0.0.162, y la beta 0.0.163 añade xnor y AdventurePilot. En cada uno, Live View dibuja la pantalla propia del fork en tu teléfono, tablet o pantalla del coche Android, con lo que ese fork le añade.

Hasta ahora, la configuración en estos forks se detenía con "unsupported upstream remote". Con la app 0.0.163 y su entorno de ejecución, se instala y se empareja igual que en openpilot.

## Qué muestra cada fork en Live View

CommaView no adivina por el nombre del fork. El entorno de ejecución de tu comma le dice a la app qué añade la pantalla del fork, y la app lo dibuja en la pantalla del comma four, en la del comma 3X o en la propia de CommaView.

| Fork | Qué dibuja CommaView |
| --- | --- |
| openpilot | Las pantallas del comma four y del comma 3X, o la superposición propia de CommaView |
| sunnypilot | La pantalla de sunnypilot: MADS, la asistencia de límite de velocidad, la trayectoria arcoíris, los indicadores de punto ciego y sus añadidos del comma 3X |
| StarPilot | Los colores, widgets, alertas y elección de cámara de StarPilot |
| xnor | La pantalla de openpilot en las versiones xnor, la de sunnypilot en rx, y el tinte del volante de Rivian de rx |
| AdventurePilot | La pantalla de sunnypilot con su indicador de centrado en el carril, el chip CURVE y el tinte del modo de dirección |

## StarPilot

StarPilot muestra sus modos de conducción con colores, y CommaView usa los colores que eligió StarPilot: su borde, su trayectoria y sus widgets, sus alertas y su elección de cámara, incluida la cámara del conductor. Desactiva primero el ajuste **Disable Logging** de StarPilot: detiene el codificador de vídeo del que transmite Live View.

## El openpilot de xnor-tech: xnor y rx

El openpilot de xnor-tech viene en dos versiones de un mismo repositorio. Sus ramas **xnor** usan la pantalla de openpilot y sus ramas **rx** la de sunnypilot, cada una con los ports de coches de xnor-tech. CommaView detecta cuál ejecuta tu comma y dibuja esa pantalla, con sus alertas tal como las escribe el comma.

En un Rivian con rx, el volante muestra cómo gira el coche: verde mientras gira por ángulo, azul mientras gira por par. CommaView dibuja los mismos colores en el volante del comma four y en el botón de modo experimental del comma 3X.

## AdventurePilot

AdventurePilot es un fork de sunnypilot con sus propios ports de coches. CommaView dibuja la pantalla de sunnypilot con lo que añade AdventurePilot:

- su **indicador de centrado en el carril**, una píldora con el empuje y el desplazamiento en la pantalla del comma 3X y una barra compacta en la del comma four;
- el **chip CURVE** en la pantalla del comma 3X, que parpadea mientras actúa el control de velocidad en curvas;
- el **tinte del modo de dirección** en el volante, y una barra de par que muestra la aceleración lateral mientras un Rivian gira por su canal de ángulo.

## Cómo conseguirlo

CommaView está en una beta solo por invitación. Si estás dentro, la app te ofrece la actualización 0.0.163 por sí sola. Cuando la app se actualice, actualiza el entorno de ejecución de tu comma desde la app y reinicia el comma cuando te lo pida. Las actualizaciones del entorno esperan a que el coche esté en P con openpilot desactivado, así que nunca interrumpen un viaje.

¿Eres nuevo en CommaView? La [guía de configuración](/es/guides/setup) explica cómo instalar la app y conectar tu comma.

## Lo que no ha cambiado

- CommaView funciona en el **comma 3X** y el **comma four**. El comma 3 sigue sin ser compatible, tampoco las versiones de los forks para comma 3, como xnor-c3 ([por qué](/es#faq-comma-3)).
- CommaView nunca cambia cómo conduce tu fork. Añade un pequeño entorno de ejecución a su lado y un pequeño hook en su interfaz en pantalla, para poder dibujar la misma trayectoria, los mismos carriles y las mismas alertas.
- En un fork que CommaView aún no admite, la configuración se detiene y deja tu comma como estaba. Puedes pedir tu fork en el tablero de propuestas de my.commaview.com.

## Para saber más

- [Qué forks de openpilot funcionan con CommaView](/forks), con lo que muestra cada uno
- [Novedades](/whats-new) de cada versión
- [Cómo funcionan las versiones de CommaView](/es/guides/releases)

CommaView no es oficial ni está afiliado a comma.ai, sunnypilot, StarPilot, xnor-tech ni AdventurePilot. Es software beta y no es un sistema de seguridad: nunca dejes que te distraiga de la conducción.
