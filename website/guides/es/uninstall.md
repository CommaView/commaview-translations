---
title: "Quitar CommaView de tu comma"
description: "Desinstala el entorno de ejecución de CommaView de tu comma en Ajustes del dispositivo, deja los archivos de tu fork como estaban y olvida el comma en tu teléfono."
topic: account
order: 3
kind: walkthrough
lede: "**Desinstalar entorno** quita CommaView de tu comma: revierte los hooks de CommaView, detiene su entorno de ejecución y quita `/data/commaview`. Tu fork sigue conduciendo como siempre. Úsalo para quitar CommaView o para volver a hacer la configuración guiada desde el principio."
parked: true
updated: 2026-11-27
needs:
  - title: "El teléfono y el comma juntos"
    text: "En el mismo Wi‑Fi que el comma, o en su punto de acceso. Ajustes del dispositivo necesita el comma para gestionar las actualizaciones y la desinstalación."
  - title: "El coche encendido, en P"
    text: "Si el coche está en marcha, el comma pone la desinstalación en cola hasta que esté en P con openpilot desactivado."
steps:
  - id: device-settings
    title: "Abre los Ajustes del dispositivo del comma"
    body: |
      Desde Inicio, abre los **Ajustes del dispositivo** de tu comma y luego **Entorno de ejecución** («Actualizar o quitar»).
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**Entorno de ejecución**: actualizar o quitar CommaView."
  - id: uninstall
    title: "Toca Desinstalar entorno"
    body: |
      Bajo la actualización del entorno, **Desinstalar entorno** quita CommaView de este comma. Después, la configuración guiada puede volver a hacerse desde el principio.
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**Desinstalar entorno**."
  - id: confirm
    title: "Confirma"
    body: |
      **Se quitará CommaView**: CommaView revierte sus hooks del entorno, se detiene y quita `/data/commaview` de este comma. El comma sigue guardado en tu teléfono. Toca **Desinstalar entorno** cuando termine su breve cuenta atrás.
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**Se quitará CommaView**, y qué implica."
      - text: "**Desinstalar entorno**, tras la cuenta atrás. **Cancelar** conserva CommaView."
    note: "Si el coche está en marcha, el comma pone la desinstalación en cola: CommaView se quita cuando el coche esté en P con openpilot desactivado, y sigue funcionando hasta entonces."
  - id: forget
    title: "Olvida el comma en tu teléfono, si quieres"
    body: |
      Ajustes del dispositivo indica ahora que se quitó el entorno. Para quitar también el comma de tu teléfono, toca **Olvidar este comma** al final de Ajustes del dispositivo: CommaView deja de mostrar este comma y elimina su clave de emparejamiento. Para quitar la propia app, desinstala CommaView desde los ajustes de Android como cualquier otra app.
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**Olvidar este comma**."
check: "El diálogo dice **Entorno desinstalado**, y Ajustes del dispositivo muestra el entorno como **Quitado**: «CommaView se desinstaló de tu comma. Ejecuta la configuración guiada para volver a instalarlo.»"
fixes:
  - q: "«La desinstalación falló por un error de permisos SSH»"
    a: "El comma no dejó entrar a este teléfono por SSH. Comprueba que SSH está activado en **Ajustes → Dispositivo → SSH** en el comma y que su usuario de GitHub tiene la clave de este teléfono, y toca **Volver a desinstalar**."
  - q: "«El comma no pudo desinstalar CommaView, así que lo dejó como estaba»"
    a: "No se quitó nada. Vuelve a intentarlo con el coche en P."
  - q: "«Desinstalación en cola hasta que el coche esté en P»"
    a: "El coche está en marcha. Ponlo en P con openpilot desactivado, déjalo encendido, y el comma quitará CommaView solo."
  - q: "El botón de desinstalar aparece en gris"
    a: "CommaView ya está actualizando o desinstalando un entorno. Vuelve a intentarlo cuando termine."
related: [setup, update-runtime, forks]
---

## Qué deja como estaba la desinstalación

- **En un fork incluido**, revierte el pequeño hook que CommaView añade a la interfaz de pantalla del fork.
- **En un fork que CommaView no incluye** (sin garantías), deja los archivos del fork como estaban.
- **Solo vídeo** no cambió nada en los archivos del fork, y la desinstalación quita el entorno de ejecución.

En SunnyPilot-TeslaHW1, desinstala el entorno antes de `op fork update`, que no puede cambiar el fork mientras el hook de CommaView está instalado. [Comprueba que tu comma y tu fork son compatibles](/es/guides/forks) tiene más detalles.

## Volver a configurar CommaView

Tras una desinstalación, el comma sigue guardado en tu teléfono. Ejecuta la [configuración guiada](/es/guides/setup) para volver a instalarlo como una instalación nueva.
