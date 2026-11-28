---
title: "Conectar en el coche sin el Wi‑Fi de casa"
description: "Pon tu teléfono y tu comma en una misma red en el coche: el punto de acceso de tu teléfono, el del comma o el de una pantalla del coche, y qué hacer si CommaView no alcanza el comma."
topic: start
order: 3
kind: walkthrough
lede: "Live View va directamente del comma a tu teléfono por una red local, no por internet. A CommaView no le importa de quién sea la red: tu teléfono y el comma solo tienen que estar en la misma. En el coche, suele ser un punto de acceso."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView configurado"
    text: "Tu comma emparejado con este teléfono. ¿Aún no? [Configurar CommaView](/es/guides/setup)."
  - title: "Sin VPN"
    text: "Desactiva cualquier VPN del teléfono o de la pantalla del coche mientras usas CommaView."
howItWorks:
  - title: "Tu comma"
    text: "Ofrece Live View y las grabaciones en la red en la que está."
    edge: "un punto de acceso"
  - title: "Tu teléfono"
    text: "Encuentra el comma solo en esa red, aunque cambie su dirección."
steps:
  - id: network
    title: "Pon el teléfono y el comma en una misma red"
    body: |
      Elige la que mejor encaje con tu coche: la que se enciende sola cuando arranca el coche suele ser la más cómoda. El comma se une a una red desde su propia pantalla, en **Ajustes › Red**.
    tabs:
      - label: "El punto de acceso de tu teléfono"
        body: "Activa el punto de acceso de tu teléfono y une el comma a él. CommaView, en el mismo teléfono, alcanza el comma a través de él, y el comma también obtiene internet por él."
      - label: "El punto de acceso del comma"
        body: "Activa el punto de acceso del comma (openpilot lo llama tethering: en un comma four, **Ajustes › Red › enable tethering**; en un comma 3X, **Ajustes › Red › Avanzado › Enable Tethering**) y únete a él desde los ajustes de Wi‑Fi de tu teléfono. El punto de acceso del comma no da internet."
      - label: "El punto de acceso de una pantalla del coche"
        body: "Si una AI box o una pantalla del coche puede compartir un punto de acceso (muchas con tarjeta SIM pueden), actívalo y une a él el comma, y tu teléfono si usas uno. [Pantallas del coche](/es/guides/car-screens) tiene más detalles."
    note: "Algunos puntos de acceso mantienen separados a los dispositivos conectados. Si CommaView no encuentra el comma en uno, prueba con otro."
  - id: home
    title: "Abre CommaView"
    body: |
      Inicio muestra tu comma **Conectado** en cuanto responde en la nueva red: CommaView lo encuentra solo, incluso en una dirección nueva. El comma duerme cuando el coche está apagado, así que arranca el coche primero.

      Si Inicio muestra el comma sin conexión con **¿No se puede conectar?**, comprueba que el teléfono está en el mismo Wi‑Fi que el comma, o en su punto de acceso, y toca **Reconectar**.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Reconectar** vuelve a intentar con el comma."
      - target: cant-connect
        text: "**¿No se puede conectar?** dice qué necesita el teléfono: el mismo Wi‑Fi que el comma, o su punto de acceso."
  - id: address
    title: "Si sigue sin aparecer, introduce su dirección"
    body: |
      Abre los **Ajustes del dispositivo** del comma, luego **Nombre y dirección**, y edita su dirección IP. En el punto de acceso del propio comma es **192.168.43.1** (es la misma en todos los commas). En cualquier otra red, es la dirección que el comma muestra en **Ajustes › Red**: bajo el nombre de la red en el botón de Wi‑Fi en un comma four, o en **Avanzado** en un comma 3X. Toca **Guardar**.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "La dirección IP del comma en esta red."
      - target: save
        text: "**Guardar**."
  - id: live-view
    title: "Abre Live View"
    body: |
      Toca **Abrir Live View** en Inicio. Si el teléfono pierde el comma, Live View dice por qué y se reconecta solo cuando el comma responde. **No se puede alcanzar este comma** significa que el teléfono no está en la red del comma: corrígelo y toca **Reintentar**.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**No se puede alcanzar este comma**: por qué se detuvo Live View."
      - target: retry
        text: "**Reintentar**, cuando el teléfono vuelva a la red del comma."
check: "Inicio muestra tu comma **Conectado**, y Live View reproduce la carretera con la trayectoria dibujada encima."
fixes:
  - q: "«No se puede alcanzar este comma»"
    a: "El teléfono debe estar en el mismo Wi‑Fi que el comma, o en su punto de acceso. Comprueba a qué red se unió el teléfono (puede haber vuelto a un Wi‑Fi conocido), desactiva cualquier VPN y toca **Reintentar**."
  - q: "«Live View está abierto en otro dispositivo»"
    a: "Este comma transmite a un solo teléfono o pantalla del coche a la vez. Vuelve a Inicio en CommaView en el otro, y Live View empieza aquí solo."
  - q: "«CommaView no responde»"
    a: "Puede que se esté reiniciando en el comma. Live View se reconecta cuando vuelva."
  - q: "CommaView dice que necesita internet para renovar"
    a: "Durante la beta, CommaView renueva de vez en cuando su pase de acceso, y el punto de acceso del comma no cuenta como internet. Dale al teléfono datos móviles o un Wi‑Fi con internet un momento."
  - q: "Funcionó en un punto de acceso y en otro no"
    a: "Algunos puntos de acceso mantienen separados a los dispositivos conectados, así que el teléfono no ve el comma. Prueba otra de las redes del paso 1."
related: [comma-not-found, car-screens, browser-view, setup-troubleshooting]
---

## Detección, emparejamiento y la dirección

Tienen que funcionar tres cosas distintas, y saber cuál falló te dice qué corregir:

- **Encontrar el comma.** CommaView busca tu comma en la red en la que está el teléfono y actualiza la dirección guardada cuando encuentra el mismo comma en otro sitio. Algunas redes bloquean esa búsqueda; introducir la dirección (paso 3) lo evita.
- **Alcanzarlo.** El teléfono tiene que poder alcanzar el comma en esa red. Que un portátil pueda conectarse por SSH al comma no demuestra que el teléfono pueda.
- **Emparejamiento.** Una vez alcanzado, el teléfono usa la clave que obtuvo al emparejarse. Cambiar de red no deshace el emparejamiento: no tienes que volver a emparejar.
