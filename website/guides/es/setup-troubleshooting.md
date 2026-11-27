---
title: "Solucionar una configuración que se detiene"
description: "Qué significan los mensajes de la configuración de CommaView, en el orden en que avanza: SSH, la instalación y el emparejamiento. Busca el mensaje que ves y qué hacer."
topic: troubleshooting
order: 1
kind: fixes
lede: "La configuración va por orden: entra en tu comma por SSH, instala el entorno de ejecución de CommaView y después empareja tu teléfono con él. Cuando se detiene, su mensaje dice qué parte falló, así que corrige primero esa parte. Que SSH funcione solo demuestra la primera: un código de emparejamiento no puede funcionar si el entorno nunca arrancó."
parked: true
updated: 2026-11-27
needs:
  - title: "En P"
    text: "El coche en P con openpilot desactivado, y encendido: sin un arnés de alimentación, apagarlo también apaga el comma."
  - title: "Una sola red"
    text: "Tu teléfono en el mismo Wi‑Fi que el comma, o en su punto de acceso. Que un portátil alcance el comma no demuestra que tu teléfono pueda."
steps:
  - id: read
    title: "Lee lo que dice la configuración y copia los detalles"
    body: |
      Cuando la instalación falla, la configuración dice qué salió mal, si tu comma quedó como estaba y qué hacer. Busca esa frase más abajo, en [Si no funciona](#fixes).

      **Copiar detalles** copia el informe que lee soporte: la versión de la app, la versión publicada, la última etapa del instalador y toda su salida. Pégalo en un correo a support@commaview.com cuando el mensaje lo pida.
    tabs:
      - label: "Falló la instalación"
        body: "La configuración dice qué falló y ofrece **Copiar detalles**."
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**Copiar detalles**."
          - target: install
            text: "**Instalar CommaView** lo vuelve a intentar cuando hayas corregido la causa."
      - label: "Falló SSH"
        body: "Antes de instalar nada, la configuración dice por qué no pudo entrar en el comma, como **Falló la autenticación SSH**, y qué revisar."
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "Qué salió mal y qué revisar."
  - id: address
    title: "Revisa la dirección del comma"
    body: |
      La configuración busca commas en la red de tu teléfono. Si el tuyo no aparece, toca **Mi comma no aparece** y escribe su dirección IP. En tu comma, está en **Ajustes → Red**: bajo el nombre de la red en el botón de Wi‑Fi en un comma four, o en **Avanzado** en un comma 3X.

      El comma tiene una dirección distinta en cada red: el Wi‑Fi de casa, un punto de acceso, una VPN. Usa la de la red en la que está ahora tu teléfono.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Un comma que la configuración encontró en esta red."
      - text: "**Mi comma no aparece**: escribe la dirección IP cuando no lo encuentra."
  - id: pair-code
    title: "Empareja con un código nuevo"
    body: |
      Los códigos de emparejamiento duran poco y funcionan una sola vez. Si rechaza uno, no lo vuelvas a escribir: consigue uno nuevo. Tras una instalación manual, el instalador muestra uno; un teléfono ya emparejado con el comma muestra uno en **Ajustes del dispositivo › Emparejar otro teléfono o tablet**.
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**Dirección IP del comma**."
      - target: pair-code
        text: "**Código de emparejamiento**. El guion es opcional."
  - id: runs
    title: "¿Ya está instalado? Empareja en su lugar"
    body: |
      Si el comma ya usa CommaView, desde otro teléfono o por una configuración anterior, no hace falta volver a instalar. En Inicio, toca **Añadir un comma**, luego **Introducir dirección y código**, y empareja con la IP del comma y un código de emparejamiento o una invitación.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "La IP del comma."
      - target: pair-code
        text: "**Código o invitación**."
      - target: pair
        text: "**Emparejar comma**."
  - id: no-video
    title: "Instalado y emparejado, pero sin vídeo"
    body: |
      Pasado el emparejamiento, que falte la imagen es un problema de transmisión, no de SSH. Live View dice lo que ve, como **No se puede alcanzar este comma**, y se reconecta solo cuando el comma responde. Consulta [CommaView no encuentra tu comma](/es/guides/comma-not-found).
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**Reintentar**."
fixes:
  - q: "«Falló la autenticación SSH.»"
    a: "Comprueba que la clave de CommaView está en GitHub (con cualquier título) y que SSH está activado en el comma. Si introdujiste tu usuario de GitHub en el comma antes de añadir la clave, quítalo y vuelve a introducirlo para que el comma descargue tus claves de nuevo."
  - q: "«Conexión rechazada en 192.168.1.50:22. Asegúrate de que SSH está activado en tu comma.»"
    a: "En el comma, ve a **Ajustes → Dispositivo → SSH** y activa SSH."
  - q: "«Se agotó el tiempo de conexión con …» o «No hay ruta a …»"
    a: "Tu teléfono no alcanza esa dirección. Comprueba que tu teléfono está en el mismo Wi‑Fi que el comma, o en su punto de acceso, que el comma está despierto (con el coche encendido) y que la dirección IP es la del comma en esta red."
  - q: "«No se encontró ningún comma en … Comprueba la dirección IP.»"
    a: "Nada respondió en esa dirección. Comprueba la IP en **Ajustes → Red** del comma."
  - q: "«La identidad SSH de este comma cambió desde la última configuración.»"
    a: "Si restableciste o reinstalaste el comma, vuelve a hacer la configuración."
  - q: "«CommaView no pudo crear su clave SSH en este teléfono. Vuelve a intentarlo o usa tu propia clave SSH.»"
    a: "Toca **Reintentar**, o **Usar mi propia clave SSH** para importar un par de claves que ya tienes en GitHub."
  - q: "«Instalación en cola.»"
    a: "El coche estaba en marcha, así que el comma puso la instalación en cola en lugar de interrumpir el viaje. Pon el coche en P con openpilot desactivado, déjalo uno o dos minutos con el coche encendido y toca **Finalizar configuración**."
  - q: "«El coche está en marcha, así que la instalación no se ejecutó.»"
    a: "Pon el coche en P con openpilot desactivado y vuelve a intentarlo."
  - q: "«Ya hay otra instalación, actualización o reparación de CommaView en curso en tu comma.»"
    a: "Espera unos minutos a que termine y vuelve a intentarlo."
  - q: "«Tu comma no pudo descargar CommaView.»"
    a: "El comma descarga el entorno de ejecución por sí mismo. Comprueba que tiene internet, por Wi‑Fi o por su propia SIM, y vuelve a intentarlo. Sirve el punto de acceso de un teléfono con datos móviles."
  - q: "«La descarga de CommaView llegó a tu comma incompleta o dañada.»"
    a: "Vuelve a intentarlo. Si vuelve a pasar, copia los detalles y envíalos a support@commaview.com."
  - q: "«Tu comma se quedó sin espacio de almacenamiento durante la instalación.»"
    a: "Vuelve a intentarlo más tarde. Si vuelve a pasar, copia los detalles y envíalos a support@commaview.com."
  - q: "«CommaView aún no es compatible con el software de conducción de tu comma.»"
    a: "Tu comma usa un software en el que CommaView no puede instalarse. [Comprueba con qué forks funciona](/es/guides/forks). Para pedir el tuyo, copia los detalles y envíalos a support@commaview.com."
  - q: "«CommaView no puede añadir su vista a … de forma segura»"
    a: "Tu fork es uno que CommaView no incluye, y su comprobación vio que su pantalla difiere donde CommaView se conecta a ella. No se cambió nada en tu comma. Para pedir tu fork, copia los detalles y envíalos a support@commaview.com."
  - q: "«El comma 3 no es compatible»"
    a: "CommaView funciona con el comma 3X y el comma four. La versión de openpilot del comma 3 está congelada y dibuja su pantalla de otra forma, así que CommaView no puede mostrar su superposición."
  - q: "«CommaView no arrancó en tu comma después de la instalación.»"
    a: "Reinicia tu comma y vuelve a intentarlo. Si vuelve a pasar, copia los detalles y envíalos a support@commaview.com."
  - q: "«Falló la verificación. No se pudo acceder a la API de CommaView en 192.168.1.50:5002.»"
    a: "La instalación terminó, pero tu teléfono no alcanza el entorno de ejecución. Comprueba que tu teléfono sigue en la red del comma y vuelve a intentarlo. Si SSH funciona desde un ordenador pero esto no, el ordenador está en una red en la que tu teléfono no está."
  - q: "«No se pudo canjear el código de emparejamiento. Genera un código nuevo y vuelve a intentarlo.»"
    a: "El código caducó, ya se usó o se escribió mal. Consigue uno nuevo ([paso 3](#step-pair-code))."
  - q: "«Falló el emparejamiento: no se pudo acceder a la API del entorno de CommaView»"
    a: "Tu teléfono no alcanza el comma en esa dirección. Revisa el punto de acceso o la red y vuelve a intentarlo."
  - q: "«CommaView no arrancará solo tras reiniciar»"
    a: "CommaView está instalado, pero nada lo inicia cuando arranca tu comma: el `/data/continue.sh` de tu comma no tiene la línea `exec ./launch_openpilot.sh`. Cuando la tenga, vuelve a instalar CommaView."
related: [setup, comma-not-found, support-bundle]
---

## Las partes por las que pasa la configuración

Cada parte necesita la anterior, así que revísalas en este orden:

1. **SSH**, puerto 22: cómo entra la configuración en el comma para instalar. Necesita tu clave en GitHub, tu usuario de GitHub en el comma y SSH activado.
2. **La instalación**: el comma descarga el entorno de ejecución y lo instala. Lee su resultado antes de pasar a lo siguiente.
3. **El entorno de ejecución**, puerto 5002 en el comma: la configuración comprueba que responde y luego se empareja con él.
4. **El emparejamiento**: un código de emparejamiento de un solo uso da a tu teléfono su propia clave para el comma.
5. **El vídeo**, puertos 8200 a 8202: las cámaras de Live View.

Si la detección no encuentra el comma pero conoces su dirección, escribirla funciona igual de bien: la detección es una comodidad, y lo que importa es alcanzar el comma.

## Seguridad

Haz la configuración, las instalaciones y la solución de problemas con el coche en P y openpilot desactivado. Nunca configures ni toques la app mientras conduces.
