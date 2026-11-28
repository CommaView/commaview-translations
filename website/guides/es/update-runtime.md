---
title: "Actualizar el entorno de ejecución de tu comma"
description: "Actualiza el entorno de ejecución de CommaView en tu comma desde Inicio o desde Ajustes del dispositivo. La actualización segura espera a la P, así que nunca interrumpe un viaje."
topic: account
order: 1
kind: walkthrough
lede: "El entorno de ejecución de CommaView en tu comma se actualiza desde la app, nunca solo. Actualiza primero CommaView y luego el entorno cuando la app lo ofrezca. Si el coche está en marcha, **Actualización segura** pone la actualización en cola en el comma y la instala cuando el coche esté en P con openpilot desactivado."
updated: 2026-11-27
needs:
  - title: "El teléfono y el comma juntos"
    text: "En el mismo Wi‑Fi que el comma, o en su punto de acceso."
  - title: "El coche encendido"
    text: "Deja el coche encendido, en P. Sin un arnés de alimentación, apagarlo también apaga el comma."
howItWorks:
  - title: "CommaView"
    text: "Cada versión de la app indica el entorno de ejecución con el que se probó, y ofrece exactamente ese."
  - title: "Tu comma"
    text: "Lo descarga, lo comprueba y lo instala cuando el coche está en P."
    edge: "reinicio"
  - title: "Live View"
    text: "Vuelve a empezar cuando el comma se reinicia."
steps:
  - id: app-first
    title: "Actualiza primero CommaView"
    body: |
      La app instala el entorno de ejecución con el que se probó, así que actualiza la app antes que el entorno. Cuando hay una actualización lista, **Actualizar** aparece arriba en Inicio y en Ajustes › **Acerca de**. Tócalo: **Actualiza CommaView** indica la versión, su canal y su tamaño. Toca **Descargar**; CommaView la descarga en segundo plano y la comprueba, y luego Android te pide confirmar la instalación.
    screen: app-update-offer
    pins:
      - target: download
        text: "**Descargar**."
      - target: channel
        text: "El canal de la versión: **Beta**, o **Alfa** para testers."
    note: "Actualiza CommaView en todos los teléfonos, tablets y pantallas del coche que ven este comma antes de actualizar su entorno de ejecución."
  - id: open
    title: "Abre la actualización del entorno"
    tabs:
      - label: "Desde Inicio"
        body: "Inicio muestra **Actualización del entorno lista** cuando hay un entorno nuevo para este comma. Toca **Revisar actualización**: la tarjeta **Actualización del entorno** muestra las versiones **Instalado** y **Disponible** y si el coche está listo. Toca **Actualizar entorno**, o **Poner en cola** mientras el coche está en marcha."
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**Actualización del entorno**: Instalado, Disponible y si el coche está listo."
          - target: update-runtime
            text: "**Actualizar entorno** (**Poner en cola** mientras el coche está en marcha)."
      - label: "Desde Ajustes del dispositivo"
        body: "Abre los **Ajustes del dispositivo** del comma y luego **Entorno de ejecución** (muestra **Actualizar** cuando hay uno listo). La página muestra el entorno instalado y el disponible. Toca **Actualizar ahora**."
        screen: device-runtime
        pins:
          - target: update-now
            text: "**Actualizar ahora**."
  - id: install
    title: "Instálala o deja que la actualización segura la ponga en cola"
    body: |
      Desde Ajustes del dispositivo, el diálogo **Actualización del entorno** dice si el coche está listo.
    tabs:
      - label: "El coche está en P"
        body: "Dice «El coche está en P y openpilot no está activado. Es seguro iniciar la actualización del entorno.» Toca **Instalar actualización**."
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**Instalar actualización**."
          - target: close
            text: "**Cerrar** lo deja para más tarde."
      - label: "El coche está en marcha"
        body: "Dice «El coche está en marcha. La actualización segura pone la actualización en cola en el comma y la instala cuando el coche esté en P con openpilot desactivado.» Toca **Actualización segura…**, lee la nota y toca **Iniciar actualización segura** cuando termine su breve cuenta atrás. Lo mismo ocurre cuando CommaView no pudo confirmar si el coche está en marcha."
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**Actualización segura…**, y luego **Iniciar actualización segura**."
    note: "CommaView nunca detiene openpilot ni tu fork: una actualización en cola espera a la P, y nunca se interrumpe un viaje."
  - id: progress
    title: "Deja que avance"
    body: |
      El comma descarga la versión, comprueba que está completa y sin alterar, la instala y reinicia CommaView, y la app muestra cada paso. Puedes cambiar de app o bloquear el teléfono: la actualización sigue, y su notificación muestra cuánto lleva.

      Hasta que el comma empieza a instalar, **Cancelar actualización** la detiene, y no cambia nada en tu comma.
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "Los pasos: Descargando, Verificando, Instalando, Reiniciando CommaView, Reconectando."
  - id: queued
    title: "Una actualización en cola espera a la P"
    body: |
      Una actualización en cola aparece en la tarjeta **Actualización del entorno** de Inicio como **Esperando a que el coche esté en P**. Se instala cuando el coche lleva unos segundos en P con openpilot desactivado. Deja el coche encendido mientras se instala.
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "**Esperando a que el coche esté en P**, con su paso."
  - id: reboot
    title: "Reinicia el comma para terminar"
    body: |
      Tras una actualización del entorno, el comma necesita un reinicio antes de que CommaView vuelva a transmitir desde él: openpilot solo carga el nuevo código de pantalla de CommaView cuando el comma se reinicia. La app nunca lo reinicia por su cuenta.

      Toca **Reiniciar comma** en la tarjeta de Inicio, o **Reiniciar el comma ahora** en el diálogo, con el coche apagado o en P. openpilot se detiene durante un minuto. También puedes reiniciarlo desde el propio comma: **Ajustes → Dispositivo → Reiniciar**.
check: "El último paso de la actualización dice **Actualizado**, y Ajustes del dispositivo muestra el entorno nuevo **Actualizado**. Tras el reinicio, Live View se reproduce con su superposición."
fixes:
  - q: "«El entorno de este comma es más nuevo que el que instala esta app»"
    a: "Actualiza CommaView y vuelve a intentarlo. No se cambió nada en el comma."
  - q: "«Se necesita actualizar»"
    a: "Esta app y el entorno de este comma no son lo bastante nuevos el uno para el otro. Actualiza primero CommaView y luego el entorno."
  - q: "«El comma no instaló …: usa …, que no figura en CommaView»"
    a: "El comma no cambió nada y mantuvo el entorno que tenía. Para añadir CommaView a ese fork sin garantías, vuelve a hacer la configuración de este comma: comprueba el fork y te pregunta antes."
  - q: "«El coche volvió a arrancar cada vez que empezaba, así que el comma dejó de intentarlo»"
    a: "Pon el coche en P con openpilot desactivado y vuelve a intentarlo."
  - q: "«Actualización del entorno revertida»"
    a: "El comma dejó el entorno que tenía. Vuelve a intentarlo y, si vuelve a fallar, [envía un paquete de soporte](/es/guides/support-bundle)."
  - q: "«CommaView ya está actualizando o desinstalando un entorno»"
    a: "Solo se ejecuta una tarea del entorno a la vez. Vuelve a intentarlo cuando termine."
  - q: "Sin superposiciones ni telemetría tras la actualización"
    a: "El comma aún no se ha reiniciado. Reinícialo con el coche apagado o en P."
related: [releases, uninstall, another-phone]
---

## Por qué las actualizaciones esperan a la P

Instalar el entorno de ejecución detiene CommaView en el comma mientras se sustituyen sus archivos y reinicia sus servicios, así que el comma solo lo hace con el coche en P y openpilot desactivado. La actualización segura no pide a openpilot que se detenga: pone el trabajo en cola en el comma, que lo ejecuta cuando el coche está en P. No hace falta apagar el coche; déjalo encendido, en P.

Antes de cambiar nada en el comma, descarga la versión y comprueba que está completa y sin alterar. Si una instalación falla después de eso, el comma deja el entorno que tenía.
