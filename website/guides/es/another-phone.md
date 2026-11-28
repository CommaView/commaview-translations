---
title: "Añadir otro teléfono o tablet"
description: "Da a otro teléfono, tablet o pantalla del coche su propia clave para tu comma con una invitación de 10 minutos, y consulta y quita los teléfonos que tienen una."
topic: start
order: 4
kind: walkthrough
lede: "Cada teléfono que ve tu comma tiene su propia clave. Para añadir otro teléfono, tablet o pantalla del coche, muestra una invitación en un teléfono que ya tenga tu comma y escríbela o escanéala en el nuevo. Sin SSH y sin volver a configurar nada."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Un teléfono con clave"
    text: "Un teléfono ya emparejado con tu comma, con CommaView 0.0.166 o posterior y su entorno de ejecución. ¿Aún no? [Configurar CommaView](/es/guides/setup)."
  - title: "CommaView en el nuevo"
    text: "Instalado y con la sesión iniciada, en 0.0.166 o posterior. [Consigue la app](/es/guides/setup#step-get-the-app)."
  - title: "La misma red"
    text: "Ambos en el mismo Wi‑Fi que el comma, o en su punto de acceso."
howItWorks:
  - title: "Tu teléfono"
    text: "Pide al comma una invitación: un código o un código QR, válido durante 10 minutos."
  - title: "El teléfono nuevo"
    text: "Se une con la invitación y obtiene su propia clave."
    edge: "red local"
  - title: "Tu comma"
    text: "Avisa a cada teléfono con clave de que uno nuevo tiene una."
steps:
  - id: device-settings
    title: "En tu teléfono, abre Emparejar otro teléfono"
    body: |
      En el teléfono que ya tiene tu comma, abre los **Ajustes del dispositivo** del comma desde Inicio y luego **Emparejar otro teléfono**.
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**Emparejar otro teléfono**: un código de corta duración para que otro teléfono o tablet pueda conectarse."
  - id: show-invitation
    title: "Muestra una invitación"
    body: |
      En **Teléfonos con clave**, **Añadir otro teléfono** muestra una invitación para un teléfono que aún no tiene este comma. Toca **Mostrar invitación**.
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**Mostrar invitación**."
      - text: "Los teléfonos con clave para este comma, este primero."
  - id: invitation
    title: "Deja la invitación en pantalla"
    body: |
      **Añadir otro teléfono** muestra un código en tres grupos, un código QR y la dirección IP del comma. Vale durante 10 minutos y funciona una sola vez. Cuando caduque, muestra una nueva.
    screen: invitation-dialog
    pins:
      - target: code
        text: "El código que escribes en el teléfono nuevo."
      - target: qr
        text: "O el código QR que escaneas."
      - text: "**Caduca en …**: 10 minutos desde que se muestra."
  - id: add-comma
    title: "En el teléfono nuevo, añade el comma"
    body: |
      En el teléfono nuevo, toca **Emparejar un comma que ya usa CommaView** en **Conecta tu comma**. Si ya tiene un comma, toca **Añadir un comma** en Inicio.

      Tu comma aparece en **En esta red**. Tócalo, o toca **Escanear código QR** y escanea la invitación. Si no aparece, toca **Introducir dirección y código**.
    screen: add-comma
    pins:
      - target: found-comma
        text: "Tu comma, encontrado en esta red."
      - target: scan-qr
        text: "**Escanear código QR** para escanear la invitación."
      - target: enter-address
        text: "**Introducir dirección y código** cuando no aparece."
  - id: pair
    title: "Escribe la invitación y empareja"
    body: |
      Comprueba la **IP del comma**, escribe la invitación en **Código o invitación** (o toca el botón QR para escanearla) y toca **Emparejar comma**. El teléfono nuevo obtiene su propia clave y muestra tu comma en Inicio.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**IP del comma**, rellenada para un comma que encontró."
      - target: pair-code
        text: "**Código o invitación**."
      - target: scan-qr
        text: "**Escanear QR de emparejamiento**."
      - target: pair
        text: "**Emparejar comma**."
  - id: new-key
    title: "Confírmalo en tus otros teléfonos"
    body: |
      Cada teléfono con clave recibe el aviso **Un teléfono nuevo tiene clave**, con su nombre y cuándo. Toca **Es mío**. Si no es uno de los tuyos, toca **Quitar**; **Revisar teléfonos** abre **Emparejar otro teléfono**, donde aparecen todos los teléfonos con clave.
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "**Es mío**, para tu propio teléfono o tablet."
      - target: review
        text: "**Revisar teléfonos** muestra todos los teléfonos con clave."
check: "El teléfono nuevo muestra tu comma en Inicio y abre Live View. En tu primer teléfono, **Emparejar otro teléfono** lo muestra en **Teléfonos con clave**."
fixes:
  - q: "«No se pudo unir con esa invitación»"
    a: "Puede estar mal escrita, haber caducado o haberse usado ya. Muestra una nueva en el teléfono que ya tiene este comma (sus Ajustes del dispositivo, **Emparejar otro teléfono**, **Añadir otro teléfono**)."
  - q: "«El entorno de este comma es anterior a las claves de teléfono»"
    a: "Primero actualiza el entorno de ejecución del comma: [Actualizar el entorno de ejecución de tu comma](/es/guides/update-runtime). Después muestra la invitación."
  - q: "«No se puede alcanzar este comma»"
    a: "Ambos teléfonos deben estar en el mismo Wi‑Fi que el comma, o en su punto de acceso. [Conectar en el coche](/es/guides/connect-in-the-car)."
  - q: "«Falló el emparejamiento: este comma ya no se empareja con código»"
    a: "El comma ya no acepta el antiguo token compartido. Añade el teléfono desde uno que ya tenga clave (sus ajustes, **Añadir otro teléfono**) o vuelve a hacer la configuración del comma."
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## Quitar un teléfono

En un teléfono con clave, abre los **Ajustes del dispositivo** del comma y luego **Emparejar otro teléfono**. Toca **Quitar** junto a un teléfono de la lista. No podrá volver a alcanzar este comma hasta que se añada de nuevo, con una invitación o configurando el comma.

## Teléfonos con un CommaView anterior

Antes de 0.0.166, todos los teléfonos enviaban al comma el mismo token compartido. Un teléfono con 0.0.166 obtiene su clave la próxima vez que se conecta, sin volver a emparejarse.

- **Apps de CommaView anteriores**, en **Emparejar otro teléfono**, dice cuántos días más puede un teléfono con un CommaView anterior seguir usando este comma con el token compartido: 90 días desde que su primer teléfono obtiene una clave. Hasta entonces, **Código de emparejamiento para una app anterior** empareja un teléfono con un CommaView anterior.
- **Detener ya** hace que el comma deje de aceptar el token compartido, cuando todos los teléfonos que lo usan tengan clave. Los teléfonos con un CommaView anterior dejan entonces de funcionar con este comma y no pueden volver a emparejarse hasta que se actualicen.
- A partir de ahí, un teléfono sin clave necesita CommaView 0.0.166 o posterior y una invitación.

Cuando actualices el entorno de ejecución de tu comma, actualiza antes CommaView en todos los dispositivos que lo ven, también en las pantallas del coche.
