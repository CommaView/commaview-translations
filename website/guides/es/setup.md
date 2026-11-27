---
title: "Configurar CommaView"
description: "Instala la app CommaView en Android, prepara tu comma 3X o comma four y deja que la configuración guiada instale el entorno de ejecución y empareje tu comma."
topic: start
order: 1
kind: walkthrough
lede: "CommaView tiene dos partes: la app en tu teléfono, tablet o pantalla del coche Android, y su pequeño entorno de ejecución en tu comma. Instala la app y la configuración guiada pone el entorno en tu comma, lo comprueba y lo empareja. Tarda unos minutos, con el coche en P y openpilot desactivado."
parked: true
updated: 2026-11-27
needs:
  - title: "Un comma 3X o comma four"
    text: "Con openpilot o un [fork compatible](/es/guides/forks). El comma 3 no es compatible: su versión de openpilot está congelada y dibuja su pantalla de otra forma, así que CommaView no puede mostrar su superposición. [Por qué el comma 3 no es compatible](/es#faq-comma-3)."
  - title: "Un dispositivo Android y tu invitación"
    text: "Android 8 o posterior, y el correo al que llegó tu invitación. CommaView está en beta: inicias sesión con la cuenta invitada."
  - title: "La misma red"
    text: "Tu teléfono y el comma en una misma red local: tu Wi‑Fi, el punto de acceso de tu teléfono, el del propio comma o cualquier otra a la que ambos puedan unirse. ¿Estás en el coche? [Conectar sin el Wi‑Fi de casa](/es/guides/connect-in-the-car)."
  - title: "Una cuenta de GitHub"
    text: "El comma acepta las claves SSH del usuario de GitHub que le indiques. CommaView crea la clave; tú la añades a GitHub durante la configuración."
howItWorks:
  - title: "Tu teléfono"
    text: "Crea una clave SSH, que añades a GitHub."
    edge: "SSH"
  - title: "Tu comma"
    text: "Toma la clave de tu usuario de GitHub. CommaView instala su entorno de ejecución junto a tu fork."
    edge: "red local"
  - title: "CommaView"
    text: "Comprueba que el entorno responde y guarda tu comma. A partir de ahí se reconecta solo."
steps:
  - id: get-the-app
    title: "Consigue la app e inicia sesión"
    body: |
      En tu dispositivo Android, inicia sesión en [my.commaview.com](https://my.commaview.com) con el correo al que llegó tu invitación. En **Get the app**, toca **Download CommaView**. Al lado se muestra su suma de comprobación SHA-256 por si quieres verificar el archivo.

      Abre la descarga. Android te pide que permitas instalaciones desde tu navegador: permítelo para esta instalación y luego vuelve a desactivarlo.

      Abre CommaView. Una sola vez te pregunta si quieres **Ayuda a mejorar CommaView**: **Enviar** o **No enviar**. Después te pide iniciar sesión: toca **Iniciar sesión** y usa el correo al que llegó tu invitación. A partir de ahí funciona sin conexión mientras su pase de acceso sea válido.
    tabs:
      - label: "Ayuda a mejorar CommaView"
        body: "Informes de fallos y qué software de conducción usa tu comma, nunca vídeo, viajes, lugares ni nombres. Puedes cambiarlo cuando quieras en Ajustes › **Privacidad y uso compartido**."
        screen: improve-commaview
        pins:
          - target: send
            text: "**Enviar** informes de fallos para ayudar a corregir problemas."
          - target: dont-send
            text: "**No enviar** los deja en el teléfono."
      - label: "Iniciar sesión"
        body: "Durante la beta, CommaView necesita tu cuenta invitada. **Iniciar sesión** abre tu navegador."
        screen: sign-in
        pins:
          - target: sign-in
            text: "**Iniciar sesión** con el correo al que llegó tu invitación."
    note: "¿Lo instalas en una pantalla del coche o en una AI box conectada a la pantalla del coche? [Pantallas del coche](/es/guides/car-screens) explica su red y cómo emparejarla con tu comma."
  - id: connect
    title: "Empieza a configurar tu comma"
    body: |
      Lee el aviso, marca que entiendes que es software no oficial y que eres responsable de usarlo con seguridad, y toca **Entendido, continuar**.

      En **Conecta tu comma**, toca **Configurar CommaView en tu comma**.
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**Configurar CommaView en tu comma**, para un comma que aún no usa CommaView."
      - target: pair-runs
        text: "¿Ya usa CommaView desde otro teléfono? Elige **Emparejar un comma que ya usa CommaView**: [Añadir otro teléfono o tablet](/es/guides/another-phone)."
  - id: setup-path
    title: "Elige cómo configurarlo"
    tabs:
      - label: "Configuración guiada"
        body: "Elige **Configuración guiada** (está marcada como Recomendado) y toca **Continuar con la configuración guiada**. CommaView crea una clave SSH, te guía en la conexión y comprueba tu comma. Los pasos siguientes la siguen."
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**Configuración guiada**, marcada como Recomendado."
          - target: continue
            text: "**Continuar con la configuración guiada**."
      - label: "Configuración manual"
        body: "Solo si SSH ya funciona desde tu ordenador al comma como usuario `comma`. Elige **Configuración manual**, luego **Continuar con la configuración manual**, y ejecuta el comando desde tu terminal. Cuando el instalador muestre un código de emparejamiento de un solo uso, toca **Ya ejecuté el comando**, introduce la IP de tu comma y el código, y toca **Añadir un comma**. [Configuración manual desde un terminal](#configuración-manual-desde-un-terminal) tiene cada paso."
        screen: setup-manual-instructions
        pins:
          - text: "**Toca para copiar** copia el comando."
          - target: ran-command
            text: "**Ya ejecuté el comando**, cuando el instalador muestre su código de emparejamiento."
  - id: ssh-key
    title: "Añade la clave SSH a GitHub"
    body: |
      CommaView crea una clave SSH para este teléfono. Toca **Copiar clave y abrir GitHub**: copia la clave pública y abre la página de nueva clave SSH de GitHub.

      En GitHub, pega la clave en el campo **Key**, ponle cualquier título (CommaView rellena uno) y guárdala con **Add SSH key**. Vuelve a CommaView y toca **Continuar**.
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**Copiar clave y abrir GitHub**. Dice «Clave SSH copiada. Abriendo GitHub…»"
      - target: own-key
        text: "**Usar mi propia clave SSH** importa un par de claves que ya tienes en GitHub."
      - target: continue
        text: "**Continuar**, cuando la clave esté guardada en GitHub."
    note: "¿Ya tienes un par de claves en GitHub? **Usar mi propia clave SSH** lo importa. La clave privada se queda en tu teléfono."
  - id: comma-ssh
    title: "Activa SSH en tu comma"
    body: |
      En la pantalla del comma, ve a **Ajustes → Dispositivo → SSH**:

      1. Introduce tu usuario de GitHub.
      2. Espera a que el comma descargue tus claves de GitHub.
      3. Activa SSH.

      Luego vuelve a CommaView y toca **Continuar**.
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "**Continuar**, cuando SSH esté activado."
    note: "El comma descarga tus claves una sola vez, al introducir el usuario. ¿Lo introdujiste antes de añadir la clave? Quítalo y vuelve a introducirlo para que el comma descargue las claves de nuevo."
  - id: choose-comma
    title: "Elige tu comma"
    body: |
      CommaView muestra los commas de esta red Wi‑Fi que ya usan CommaView, así que un comma que configuras por primera vez normalmente aún no aparece. Toca **Mi comma no aparece** y escribe su dirección IP. Luego toca **Instalar CommaView**.

      Encontrarás la IP en el comma, en **Ajustes → Red**: bajo el nombre de la red en el botón de Wi‑Fi en un comma four, o en **Avanzado** en un comma 3X.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Un comma que ya usa CommaView. Uno guardado en este teléfono lleva la marca **Guardado en este teléfono**."
      - text: "**Mi comma no aparece**: introduce su dirección IP."
      - target: install
        text: "**Instalar CommaView**."
  - id: safe-install
    title: "Inicia la instalación segura"
    body: |
      El diálogo **Instalación segura** indica en qué comma se instala. Lee la nota y toca **Iniciar instalación segura** cuando termine su breve cuenta atrás.
    tabs:
      - label: "El coche está en P"
        body: "Si el coche está en P y openpilot no está activado, CommaView se instala ya."
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "**Iniciar instalación segura**, tras la cuenta atrás."
      - label: "El coche está en marcha"
        body: "El comma pone la instalación en cola y la ejecuta cuando el coche está en P con openpilot desactivado, así que nunca interrumpe un viaje. La configuración muestra **Instalación en cola**: pon el coche en P con openpilot desactivado, espera uno o dos minutos y toca **Finalizar configuración**."
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "**Finalizar configuración**, cuando el coche esté en P."
    note: "Después CommaView se conecta al comma por SSH, comprueba qué comma es e instala el entorno de ejecución con el que se probó esta versión de la app. Comprueba que la instalación responde y guarda tu comma en este teléfono. Mantén el teléfono en la misma red hasta que termine."
    warn: "Deja el coche encendido, en P. Sin un arnés de alimentación, apagar el coche también apaga el comma, y eso detiene la instalación."
  - id: ready
    title: "CommaView está listo"
    body: |
      Tu comma está instalado, emparejado, y se reconecta solo la próxima vez que arranque.
    tabs:
      - label: "CommaView está listo"
        body: "Toca **Listo**."
        screen: setup-done
        pins:
          - target: finish
            text: "**Listo** te lleva a Inicio."
      - label: "Reinicia para terminar"
        body: "A veces la configuración dice **Reinicia para terminar**: el comma transmite a tu teléfono tras un reinicio. Toca **Reiniciar comma y terminar** con el coche apagado o en P con openpilot desactivado. openpilot se detiene durante un minuto mientras reinicia."
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**Reiniciar comma y terminar**."
check: "Inicio muestra tu coche con su comma **Conectado**, el entorno de ejecución y la dirección del comma. Toca **Abrir Live View**: la carretera se ve en directo, con la trayectoria y el coche de delante dibujados encima. A partir de ahora la app encuentra tu comma sola cuando tu teléfono y el comma están en la misma red, aunque cambie su dirección."
fixes:
  - q: "No se pudo conectar por SSH"
    a: "Comprueba que SSH está activado en **Ajustes → Dispositivo → SSH** en el comma, que el usuario de GitHub es el tuyo y que la clave de CommaView está en esa cuenta de GitHub. Si añadiste la clave después de introducir el usuario, quita el usuario y vuelve a introducirlo para que el comma descargue la clave."
  - q: "Mi comma no aparece en la lista"
    a: "Es normal la primera vez: la lista muestra los commas que ya usan CommaView. Toca **Mi comma no aparece** e introduce su dirección IP (**Ajustes → Red** en el comma: bajo el nombre de la red en el botón de Wi‑Fi en un comma four, o en **Avanzado** en un comma 3X). Comprueba que el teléfono está en la misma red que el comma y no usa una VPN."
  - q: "La configuración dice «Instalación en cola»"
    a: "El comma vio que el coche estaba en marcha, así que espera. Pon el coche en P con openpilot desactivado, espera un minuto y toca **Finalizar configuración**. Deja el coche encendido: sin un arnés de alimentación, apagarlo también apaga el comma."
  - q: "La configuración dice que mi comma no es compatible"
    a: "En un comma 3, la configuración se detiene y ofrece **Configurar CommaView en un comma 3X o comma four**. En un fork a cuya pantalla CommaView no puede añadir su vista, la configuración lo indica y no cambia nada. [Comprueba que tu comma y tu fork son compatibles](/es/guides/forks)."
  - q: "El código de emparejamiento no funcionó"
    a: "Los códigos de emparejamiento son de un solo uso y caducan pronto. Vuelve a ejecutar el instalador para obtener uno nuevo y comprueba que lo escribiste tal como aparece (el guion es opcional)."
  - q: "Conectado, pero sin vídeo"
    a: "La configuración y el emparejamiento están hechos; el problema es la transmisión de vídeo. Comprueba que el comma está encendido y listo para conducir, mantén el teléfono en la misma red y vuelve a abrir Live View. Si dice **No se puede alcanzar este comma**, consulta [No se encuentra tu comma](/es/guides/comma-not-found)."
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## Configuración manual desde un terminal

Solo si SSH ya funciona desde tu ordenador al comma como usuario `comma`.

1. En CommaView elige **Configuración manual** y luego **Continuar con la configuración manual**. La app muestra el comando para su entorno de ejecución en **Instalar desde tu terminal**, listo para copiar (**Toca para copiar**). Se parece a este, que instala el entorno de la versión actual:

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. Ejecútalo desde un ordenador en la misma red Wi‑Fi que tu comma, sustituyendo `COMMA_IP` por la dirección IP del comma (**Ajustes → Red** en el comma: bajo el nombre de la red en el botón de Wi‑Fi en un comma four, o en **Avanzado** en un comma 3X). Tu ordenador descarga el instalador y SSH lo ejecuta en el comma como usuario `comma`.
3. Cuando el instalador termina, CommaView arranca en el comma y muestra un código de emparejamiento de un solo uso.
4. De vuelta en CommaView, toca **Ya ejecuté el comando**. En **Añade tu comma**, selecciona tu comma o introduce su IP, escribe el código de emparejamiento y toca **Añadir un comma**. La app comprueba el entorno de ejecución y guarda el comma.

## Antes de tu primer viaje

Pruébalo en P antes de conducir.

- Inicio muestra tu comma como **Conectado**.
- Live View se reproduce y la trayectoria se mueve con el coche.
- Si la app muestra un aviso o pide una reparación, resuélvelo antes de conducir.
- Déjalo configurado para que nunca necesite tu atención mientras conduces.

¿Sigues atascado? Pregunta en el [Discord de CommaView](https://discord.gg/UuMhz9K8ft) o envía comentarios desde la app. Si soporte te pide registros, [envía un paquete de soporte](/es/guides/support-bundle).
