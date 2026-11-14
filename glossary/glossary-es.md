# Español glossary

The words every Spanish string uses for CommaView's terms, so screens translated apart say the same thing. Where
openpilot already translates a term (`selfdrive/ui/translations/app_es.po`, taken from the `v0.10.1` tag: master no
longer has it), its word is used, so the app says what the car's screen says. Neutral international Spanish, as
openpilot's translation writes it. Machine drafted; a native speaker's review is owed before release
(the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`). Gender follows the thing
a name stands for: *el* comma (el dispositivo), *la* app, *el* fork.

## Style

- Address the person as **tú**, as openpilot's translation does ("¿Seguro que quieres apagar?", "Empareja tu
  dispositivo"). Imperatives in the tú form: Toca, Abre, Conecta, Introduce.
- Opening ¿ and ¡ always. Names of settings, switches and files quoted in running text take « » («Ubicación del
  vehículo», «Disable Logging»); text the person typed or said keeps the English's “ ”. Ellipsis stays ….
- Sentence case for titles and buttons (only the first word and names capitalised), as openpilot's lower-case
  strings do: "Modo experimental", "Restablecer calibración". openpilot's ALL-CAPS buttons are its own style; ours
  follow the English's case.
- Buttons are short infinitives: Cancelar, Listo, Guardar, Eliminar, Reintentar, Continuar, Abrir, Cerrar,
  Activar, Desactivar.
- No full stop on titles, buttons, row titles or pills; whole sentences in body text end with one.
- Spanish runs about 20–30 % longer than English: prefer the shorter common word, drop articles in pills and row
  subtitles, and drop a word the zh-TW drops in narrow places.
- Numbers keep the English digits and decimal point as the app formats them (the app formats, not the strings).

## Terms

| English | Español | Note |
|---|---|---|
| Home (dock) | Inicio | |
| Recordings | Grabaciones | the section and its saved drives |
| Settings | Ajustes | |
| recording, a recording | grabación | openpilot: "Grabar y subir" |
| drive (a trip the comma recorded) | viaje | |
| replay | reproducción | |
| live copy | copia en vivo | |
| saved moment | momento guardado | |
| Record | Grabar | the rail's button |
| Go live / live streaming | transmisión en vivo | |
| onroad screen | pantalla de conducción | |
| onroad / offroad (the comma's state) | en marcha / detenido | |
| design (an onroad screen's look) | diseño | |
| overlay pack | paquete de superposición | "paquete" alone where the context is clear |
| fork | fork | openpilot's own jargon; kept, masculine (el fork) |
| runtime (commaviewd) | entorno de ejecución | "entorno" alone in narrow places |
| update / install / uninstall | actualizar / instalar / desinstalar | openpilot's |
| reboot | reiniciar | openpilot's |
| power off | apagar | openpilot's |
| pair / pairing | emparejar / emparejamiento | openpilot's |
| device (the comma) | dispositivo | openpilot's |
| this phone / this device (`common_this_*`, the device CommaView runs on) | este teléfono / este dispositivo | openpilot says teléfono; both masculine with «este», so «de», «en», «con» and a masculine adjective («conectado», «emparejado», «lleno») fit either. The _start forms only capitalise: Este teléfono / Este dispositivo. A sentence that starts with the placeholder in English starts with it in Spanish too |
| your phone / your device (`common_your_*`) | tu teléfono / tu dispositivo | both masculine, as este teléfono / este dispositivo; Tu teléfono / Tu dispositivo at a sentence's start |
| connected / disconnected | conectado / desconectado | |
| offline | sin conexión | openpilot's |
| engaged / disengaged | activado / desactivado | openpilot: "Desactivar" for disengaging |
| override | intervención del conductor | |
| experimental mode | modo experimental | openpilot's |
| driver monitoring | supervisión del conductor | openpilot's |
| driver camera | cámara del conductor | openpilot's; Live View's short toggle is «Cámara int.» |
| road camera / wide camera | cámara de carretera / cámara gran angular | |
| lead car | vehículo delantero | |
| speed limit | límite de velocidad | |
| set speed / MAX | velocidad fijada / MÁX | openpilot's MAX is MÁX |
| lane change | cambio de carril | openpilot: "salida de carril" |
| calibration | calibración | openpilot's |
| driver position (left/right-hand drive) | posición del conductor (volante a la izquierda / derecha) | |
| daylight contrast | contraste diurno | |
| offline maps | mapas sin conexión | |
| navigation | navegación | |
| Home / Work (places) | Casa / Trabajo | |
| vehicle location | ubicación del vehículo | openpilot says vehículo |
| account / sign in / sign out | cuenta / iniciar sesión / cerrar sesión | |
| leaderboard | clasificación | |
| achievement | logro | |
| privacy | privacidad | |
| diagnostics | diagnóstico | |
| report a problem | informar de un problema | |
| Details (Live View's pane) | Detalles | |
| stream health | estado de la transmisión | |
| storage | almacenamiento | openpilot's |
| hotspot | punto de acceso | openpilot's "Tethering" toggle is its own name |
| Live / Delayed (Live View's state) | En vivo / Con retraso | |
| frame pacing | ritmo de fotogramas | |
| inset (a picture in the picture) | miniatura | |
| framing: Fill / Exact / Extend / Auto | Rellenar / Exacto / Extender / Auto | |
| camera framing | encuadre de la cámara | |
| reduce motion | reducir movimiento | |
| screen edges | bordes de la pantalla | |
| View (Surround's) / chase / high / top-down | Vista / persecución / elevada / cenital | |
| vehicle detection / detector / model | detección de vehículos / detector / modelo | |
| renderer | renderizador | |
| key (an API key, an SSH key) | clave | openpilot's "claves SSH"; public / private: clave pública / privada |
| dashboard (a service's) | panel | |
| reroute | recalcular ruta | |
| Where to? | ¿Adónde vas? | |
| map source | fuente del mapa | |
| Powered by | Con tecnología de | |
| steering / speed active, manual (the HUD's control line) | dirección activa / velocidad activa / manual | review on a drive |
| steering only / speed only | solo dirección / solo velocidad | |
| blind spot | punto ciego | |
| green light / lead car moving | semáforo en verde / el vehículo delantero arranca | |
| safe update / install / repair | actualización / instalación / reparación segura | |
| overlays (drawn on video) | superposiciones | not overlay packs |
| telemetry | telemetría | |
| patch | parche | |
| in Park | en P (estacionamiento) | "en P" in narrow places |
| power harness | arnés de alimentación | |
| guided / manual setup | configuración guiada / manual | openpilot's configuración |
| boot hook / runtime hook | hook de arranque / hook del entorno | developers' jargon, kept |
| vehicle security key | clave de seguridad del vehículo | |
| pair code / invitation | código de emparejamiento / invitación | |
| phones with a key | teléfonos con clave | |
| shared token | token compartido | |
| development runtime | entorno de desarrollo | |
| controller | mando | a game controller |
| best effort | sin garantías | |
| video only | solo vídeo | |
| widgets | widgets | Android's Spanish |
| backup / restore | copia de seguridad / restaurar | |
| read-only | solo lectura | |
| head unit | pantalla del coche | |
| nearby devices | dispositivos cercanos | Android's permission |
| display over other apps | mostrar sobre otras apps | Android's permission |
| set aside (saved lists) | apartado | |
| Not now / Review | Ahora no / Revisar | openpilot's REVIEW is REVISAR |
| queue | cola | |
| Needs processing | Pendiente de procesar | |
| pull drives | traer viajes | |
| whole drive | viaje completo | |
| export | exportar | |
| pack studio | estudio de paquetes | |
| clip | clip | |
| log excerpt | extracto del registro | |
| support bundle | paquete de soporte | |
| Driving insights | Estadísticas de conducción | |
| contribute | contribuir | |
| route / segment (openpilot's) | ruta / segmento | |
| Privacy & sharing | Privacidad y uso compartido | the Settings page |
| stream key | clave de transmisión | YouTube's |
| destination (Go live's) | destino | |
| Go live | Transmitir | |
| YouTube Studio | YouTube Studio | YouTube's own name in Spanish |
| Auto-start | Inicio automático | |
| Public / Unlisted / Private | Público / No listado / Privado | YouTube's |
| input (microphone) | entrada | |
| car hands-free | manos libres del coche | |
| car | coche | openpilot's |
| metered / monthly limit | de uso medido / límite mensual | |
| Your requests | Tus solicitudes | |
| Open / Closed (a request) | Abierta / Cerrada | |
| license | licencia | |
| map library | biblioteca de mapas | |
| map theme | tema del mapa | |
| spoken guidance | indicaciones por voz | |
| dev build | versión de desarrollo | |
| access pass | pase de acceso | the account's |
| waitlist | lista de espera | |
| beta member / admin | miembro Beta / administrador | |
| display name / public name | nombre visible / nombre público | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | Esta semana / Semana pasada / Total | |
| finalized (a week) | cerrada | |
| badge / share card | insignia / tarjeta para compartir | |
| Official / Community (packs) | Oficial / Comunidad | |
| reviewed by CommaView / unreviewed | revisado por CommaView / sin revisar | |
| Update ready | Actualización lista | |
| training collection | colección de entrenamiento | car detection's; openpilot's "guía de entrenamiento" |
| recording metadata | metadatos de la grabación | |
| SSH identity (a comma's host key) | identidad SSH | |
| keystore | almacén de claves | Android's |
| repository (a fork's) | repositorio | |
| driving software | software de conducción | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | dejar como estaba | |
