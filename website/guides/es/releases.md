---
title: "Cómo funcionan las versiones de CommaView"
description: "Cómo se publican la app CommaView y el entorno de ejecución de tu comma: versiones alfa, luego una beta, descargas firmadas, entornos emparejados y actualizaciones que esperan a la P."
topic: account
order: 2
kind: reference
lede: "CommaView tiene dos partes que se actualizan juntas: la app de Android y el pequeño entorno de ejecución de tu comma. Así es como te llega una versión, y así se mantienen seguras las actualizaciones."
updated: 2026-11-27
steps:
  - id: version
    title: "Mira qué versión tienes"
    body: |
      Ajustes › **Acerca de** muestra la versión de la app y si está **Actualizada** o hay una actualización disponible, con su versión. CommaView consulta tu cuenta en busca de una versión nueva y te avisa cuando hay una lista.
    screen: support-about
    pins:
      - target: version
        text: "La versión de la app."
      - target: up-to-date
        text: "**Actualizada**, o la versión lista para ti."
  - id: app-update
    title: "Actualiza la app desde dentro"
    body: |
      Cuando hay una versión lista, **Actualizar** aparece arriba en Inicio y en **Acerca de**. **Actualiza CommaView** indica la versión y su canal: **Beta** para todos los invitados, o **Alfa**, «Una versión temprana para testers. Puede tener más problemas que la beta.» Toca **Descargar**: CommaView la descarga en segundo plano, la comprueba y luego Android te pide confirmar la instalación.
    screen: app-update-offer
    pins:
      - target: channel
        text: "El canal: **Beta** o **Alfa**."
      - target: download
        text: "**Descargar**. **Ahora no** lo deja para más tarde."
  - id: runtime
    title: "Luego actualiza el entorno de ejecución de tu comma"
    body: |
      Cada versión de la app indica el entorno de ejecución con el que se probó. Una vez actualizada la app, Inicio ofrece ese entorno con **Actualización del entorno lista**. Las actualizaciones del entorno empiezan desde la app, nunca solas. [Actualizar el entorno de ejecución de tu comma](/es/guides/update-runtime) tiene cada paso.
    screen: home-runtime-update
    pins:
      - target: update-card
        text: "**Actualización del entorno**: el entorno instalado y el disponible."
related: [update-runtime, uninstall, setup]
---

## Alfa y luego beta

- Cada versión sale primero como una serie de versiones alfa para unos pocos testers.
- Cuando una alfa se mantiene estable, se convierte en la beta de esa versión y llega a todos los invitados.
- Tu cuenta en [my.commaview.com](https://my.commaview.com) siempre ofrece la versión adecuada para ti.

## Firmadas y emparejadas

- Cada descarga de la app es una versión de lanzamiento firmada, nunca una versión de depuración, con su suma de comprobación SHA-256 al lado en my.commaview.com. La app comprueba el tamaño y la suma de comprobación de una actualización que descarga antes de ofrecer instalarla: «La descarga no coincidía con su suma de comprobación, así que no se instaló.»
- Cada versión de la app indica el entorno de ejecución con el que se probó, y la app instala exactamente ese en tu comma.
- A una app anterior nunca se le ofrece un entorno con el que no se haya probado. Un comma cuyo entorno es más nuevo que el que instala la app lo indica: actualiza CommaView y vuelve a intentarlo.

## Actualizar tu comma de forma segura

- Las actualizaciones del entorno empiezan desde Inicio o desde Ajustes del dispositivo, nunca solas.
- Las actualizaciones nunca interrumpen un viaje. Si el coche está en marcha, la actualización segura pone la actualización en cola y el comma la instala cuando el coche esté en P con openpilot desactivado. No hace falta apagar el coche.
- Tras una actualización del entorno, el comma necesita un reinicio antes de que CommaView vuelva a transmitir. La app te lo pide.
- Puedes quitar el entorno de ejecución desde Ajustes del dispositivo cuando quieras: [Quitar CommaView](/es/guides/uninstall).

## Dónde te enteras

- La app te avisa cuando hay una versión nueva lista.
- [Novedades](/whats-new) enumera cada cambio.
- Te escribimos por correo sobre los cambios importantes, y puedes enviar comentarios desde la app cuando quieras (Ajustes › **Soporte y diagnóstico**).
