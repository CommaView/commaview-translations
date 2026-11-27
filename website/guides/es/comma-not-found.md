---
title: "CommaView no encuentra tu comma"
description: "¿Inicio dice Sin conexión o Live View no alcanza tu comma? Revisa la red, la dirección del comma y su emparejamiento, en ese orden."
topic: troubleshooting
order: 2
kind: fixes
lede: "CommaView habla con tu comma directamente por tu red local, sin ningún servicio en la nube de por medio. Cuando no lo encuentra, casi siempre es que tu teléfono y el comma están en redes distintas, que el comma duerme con el coche apagado o que su dirección cambió. Revisa eso primero y luego su emparejamiento."
parked: true
updated: 2026-11-27
needs:
  - title: "El coche encendido"
    text: "El comma duerme cuando el coche está apagado. Enciende el coche, en P."
  - title: "Una sola red"
    text: "Tu teléfono en el mismo Wi‑Fi que el comma, o en su punto de acceso. En el coche: [conectar en el coche](/es/guides/connect-in-the-car)."
steps:
  - id: home
    title: "Mira qué dice Inicio"
    body: |
      Cuando tu teléfono no alcanza el comma, Inicio lo muestra **Sin conexión**, con **Reconectar**, y una tarjeta **¿No se puede conectar?**: «Tu teléfono debe estar en el mismo Wi‑Fi que el comma, o en su punto de acceso. El comma se suspende con el coche apagado.»

      Comprueba ambas cosas y toca **Reconectar**.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Reconectar**."
      - target: cant-connect
        text: "La tarjeta **¿No se puede conectar?**."
  - id: live-view
    title: "En Live View: espera o reintenta"
    body: |
      Live View dice por qué se detuvo. **No se puede alcanzar este comma** significa que tu teléfono no lo alcanza en la red. Se reconecta solo cuando el comma responde; **Reintentar** lo intenta ya.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**No se puede alcanzar este comma**: por qué se detuvo Live View."
      - target: retry
        text: "**Reintentar**."
  - id: network
    title: "Revisa la red de tu teléfono"
    body: |
      Abre los ajustes de Wi‑Fi de tu teléfono y comprueba que está conectado a la red en la que está el comma: el mismo Wi‑Fi de casa, el punto de acceso de tu teléfono con el comma conectado, o el punto de acceso del propio comma.

      - Un teléfono que dejó un Wi‑Fi sin internet para usar datos móviles no alcanza el comma. Vuelve a conectarlo.
      - Una VPN en tu teléfono puede enviar su tráfico a otra parte. Desactívala y vuelve a intentarlo.
      - Algunos puntos de acceso impiden que los dispositivos conectados se alcancen entre sí. Prueba otra red, como el punto de acceso del propio comma.
    note: "Los ajustes de Wi‑Fi y de punto de acceso de Android no aparecen en la imagen: se ven distintos en cada teléfono."
  - id: address
    title: "Revisa la dirección del comma"
    body: |
      El comma obtiene una dirección nueva cuando se une a otra red, o cuando un router le da otra. CommaView lo vuelve a encontrar solo cuando lo ve en la red; si no, guarda tú su dirección.

      En el comma, busca su dirección IP en **Ajustes → Red**. En CommaView, abre **Ajustes del dispositivo** desde Inicio, toca **Cambiar el nombre o la dirección**, edita **Dirección IP**, escribe la dirección del comma y toca **Guardar**.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "La dirección IP del comma."
      - target: save
        text: "**Guardar**."
  - id: add
    title: "¿Sigue sin aparecer? Vuelve a añadirlo"
    body: |
      En Inicio, toca **Añadir un comma**. **En esta red** muestra los commas que usan CommaView en la red de tu teléfono: toca el tuyo. Si no está, toca **Introducir dirección y código**, o **Escanear código QR** en un teléfono ya emparejado con él.
    screen: add-comma
    pins:
      - target: found-comma
        text: "**En esta red**: un comma encontrado cerca."
      - target: enter-address
        text: "**Introducir dirección y código**."
      - target: scan-qr
        text: "**Escanear código QR**."
  - id: pair
    title: "Empareja con su dirección y un código nuevo"
    body: |
      Escribe la IP del comma y un código de emparejamiento o una invitación, y toca **Emparejar comma**. Los códigos caducan pronto: un teléfono ya emparejado con el comma muestra uno nuevo en **Ajustes del dispositivo**, en **Emparejar otro teléfono o tablet**.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "La IP del comma."
      - target: pair-code
        text: "**Código o invitación**."
      - target: pair
        text: "**Emparejar comma**."
    note: "Si escribir su dirección funciona pero el comma nunca aparece solo, la red oculta la detección de CommaView. No pasa nada: lo que importa es la dirección."
check: "Inicio muestra tu comma **Conectado**, y **Abrir Live View** abre la imagen."
fixes:
  - q: "«No se puede alcanzar este comma»"
    a: "Tu teléfono debe estar en el mismo Wi‑Fi que el comma, o en su punto de acceso. Live View se reconecta cuando responde. Revisa la red ([paso 3](#step-network)) y la dirección del comma ([paso 4](#step-address))."
  - q: "«CommaView no responde»"
    a: "El comma responde, pero CommaView en él no. Puede que se esté reiniciando en el comma: Live View se reconecta cuando vuelva. Si sigue así, reinicia el comma, estacionado."
  - q: "«No hay vídeo de este comma»"
    a: "Responde, pero su vídeo no volvió. Reintenta, o vuelve atrás y revisa el comma: puede que openpilot aún esté arrancando."
  - q: "«Live View está abierto en otro dispositivo»"
    a: "Este comma transmite a un solo teléfono o pantalla del coche a la vez. Vuelve a Inicio en CommaView en el otro, y Live View empieza aquí solo."
  - q: "«El comma no respondió a tiempo.»"
    a: "Una conexión débil o saturada. Comprueba que tu teléfono está en el Wi‑Fi o el punto de acceso del comma, más cerca de él si puedes, y reintenta."
  - q: "«El comma rechazó la conexión. Puede que CommaView se esté reiniciando en él.»"
    a: "Espera un momento a que vuelva y reintenta."
  - q: "«No llegan los datos del coche»"
    a: "Llega el vídeo, pero no la velocidad, los intermitentes ni las alertas del coche. Reinicia el comma para solucionarlo."
  - q: "«Falló el emparejamiento: el código caducó. Genera uno nuevo y vuelve a intentarlo.»"
    a: "Obtén un código nuevo en un teléfono ya emparejado con el comma, en **Ajustes del dispositivo › Emparejar otro teléfono o tablet**, y vuelve a emparejar."
  - q: "«Falló el emparejamiento: código no válido. Revisa el código o escanea el QR.»"
    a: "Revisa el código que escribiste (los guiones son opcionales), o escanea su código QR."
  - q: "«Actualiza el entorno de este comma» o «Actualiza CommaView»"
    a: "Esta app y el entorno de ejecución del comma están demasiado alejados para entenderse. Actualiza lo que indique: el entorno desde Ajustes del dispositivo ([Actualizar el entorno de ejecución](/es/guides/update-runtime)), o la app."
  - q: "«No se pueden leer tus commas guardados»"
    a: "Los commas guardados en este teléfono no se pudieron leer, así que no se muestra ninguno. No se han eliminado. Vuelve a intentarlo, o toca **Empezar de nuevo** y vuelve a emparejar cada comma: la lista anterior se conserva al menos 90 días."
related: [connect-in-the-car, setup-troubleshooting, another-phone]
---

## Cómo encuentra CommaView un comma

- **La detección** encuentra los commas que usan CommaView en la red de tu teléfono, para que no tengas que escribir direcciones. Algunas redes la bloquean.
- **La dirección** es a lo que se conecta CommaView. Escribirla funciona tanto si la detección funciona como si no.
- **El emparejamiento** da a tu teléfono su propia clave para el comma, con un código de corta duración. La detección y el emparejamiento son cosas distintas: un comma que tu teléfono alcanza aún tiene que emparejarse.
- **Un comma guardado** se reconoce por su identidad, no solo por su dirección, así que cuando aparece en una dirección nueva CommaView actualiza la guardada.

## Seguridad

Revisa las redes y empareja estacionado. No toques CommaView mientras conduces.
