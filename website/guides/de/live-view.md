---
title: "Ihr comma in Live View ansehen"
description: "Öffnen Sie Live View, um die Straßenkamera Ihres comma und seine Fahransicht auf dem Handy zu sehen, und lernen Sie die Bedienung, die Details und seine Meldungen bei Problemen kennen."
topic: screens
order: 1
kind: walkthrough
lede: "**Live View** zeigt die Straßenkamera Ihres comma live, mit der Fahransicht darüber: der des comma four, des comma 3X oder der eigenen von CommaView. Das Bild kommt direkt vom comma über Ihr eigenes Netzwerk, nicht über das Internet."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView ist eingerichtet"
    text: "CommaView auf einem Android-Handy, gekoppelt mit Ihrem comma. Noch nicht? [CommaView einrichten](/de/guides/setup)."
  - title: "Das Auto ist an"
    text: "openpilot sendet Video nur unterwegs. Bei ausgeschaltetem Auto wartet Live View und startet von selbst, sobald das Auto startet."
  - title: "Ein Netzwerk"
    text: "Ihr Handy und Ihr comma im selben WLAN oder Hotspot. Im Auto siehe [Im Auto verbinden](/de/guides/connect-in-the-car)."
steps:
  - id: open
    title: "Live View auf der Startseite öffnen"
    body: |
      Tippen Sie unter **Start** bei verbundenem comma und eingeschaltetem Auto auf **Live View öffnen**. Nach wenigen Sekunden erscheint die Straße, und die Stream-Anzeige meldet **Live**.
    screen: phone-home
    pins:
      - target: open-live-view
        text: "**Live View öffnen**, die Hauptschaltfläche der Startseite."
    note: "Bei ausgeschaltetem Auto meldet Live View **Ihr comma ist online, fährt aber nicht**. Es startet von selbst, wenn das Auto startet, oder sofort mit **Aktualisieren**."
  - id: controls
    title: "Die Bedienelemente unter dem Bild kennenlernen"
    body: |
      Hochkant liegen die Bedienelemente unter dem Video:

      - **Aufnehmen** speichert diesen Abschnitt der Fahrt. Siehe [Eine Fahrt aufnehmen](/de/guides/record).
      - **Speichern** behält die letzten 3 Minuten und die nächste Minute der Fahrt.
      - Der Umschalter der Fahransicht, benannt nach der Ansicht, die er zeigt (**CommaView**, **comma 4**, **comma 3X**), wechselt mit jedem Tippen zur nächsten. Siehe [Die Fahransicht wählen](/de/guides/overlays).
      - **Live gehen** streamt, was Live View zeigt, sobald Sie es eingerichtet haben. Siehe [Live gehen](/de/guides/go-live).
      - **Fahrercam** zeigt die Fahrerkamera in einer Ecke des Bildes.
      - **Details** öffnet die Angaben und Karten von Live View.

      Was bei der Breite und Textgröße Ihres Handys nicht passt, landet unter **Mehr**. Nichts wird verkleinert oder abgeschnitten.
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**Aufnehmen**."
      - target: onroad-screen-button
        text: "Der Umschalter der Fahransicht."
      - target: driver-cam-button
        text: "**Fahrercam**."
      - target: go-live-button
        text: "**Live gehen**, sobald der Livestream eingerichtet ist."
      - text: "**Mehr** enthält, was nicht passt."
    note: "Während einer Aufnahme sind der Umschalter der Fahransicht und **Fahrercam** abgeblendet: Wählen Sie sie, bevor Sie auf **Aufnehmen** tippen."
  - id: details
    title: "Details öffnen"
    body: |
      Tippen Sie auf **Details** oder ziehen Sie das Blatt am unteren Bildschirmrand hoch. Es zeigt, wie es dem Stream geht, das Video, die Runtime, die Software und Adresse Ihres comma, ob Sie aufnehmen oder streamen, und die Karte **Browser View**. Seine Links öffnen **Aufnahmen** und die **Einstellungen des Geräts** Ihres comma.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "Das Blatt **Details**."
      - text: "Die Übersicht: Stream-Zustand, Video und Runtime."
      - target: recordings-link
        text: "**Aufnahmen**."
      - target: device-settings-link
        text: "**Einstellungen des Geräts** für dieses comma."
  - id: turn
    title: "Das Handy drehen oder einen größeren Bildschirm nutzen"
    body: |
      Drehen Sie das Handy quer, dann füllt das Video den Bildschirm, mit den Bedienelementen in einer Leiste auf der Fahrerseite. **Details** öffnet sich neben dem Bild, und **Verlassen** beendet Live View.
    tabs:
      - label: "Handy quer"
        body: "Die Leiste enthält dieselben Bedienelemente. Auf einem niedrigen Bildschirm wird sie kompakt."
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "**Aufnehmen**, oben in der Leiste."
          - target: more
            text: "**Mehr** enthält **Fahrercam** und **Details**."
          - target: exit
            text: "**Verlassen** beendet Live View."
      - label: "Tablet oder Bildschirm im Auto"
        body: "Auf einem breiten Bildschirm bleibt die Leiste auf der Fahrerseite. Siehe [CommaView auf einem Bildschirm im Auto nutzen](/de/guides/car-screens)."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Aufnehmen**."
          - target: onroad-screen-button
            text: "Der Umschalter der Fahransicht."
          - target: driver-cam-button
            text: "**Fahrercam**."
          - target: details
            text: "**Details**."
          - target: exit
            text: "**Verlassen**."
  - id: auto
    title: "Live View von selbst öffnen lassen"
    body: |
      Für ein Handy oder Infotainment, das nur Live View zeigen soll, öffnen Sie **Einstellungen › Anzeige** und schalten unter **Live View wird geöffnet** die Option **Live View bei Verbindung öffnen** ein. Live View öffnet sich dann von selbst, wenn sich Ihr comma bei eingeschaltetem Auto verbindet. Verlassen Sie es, bleibt es bis zum nächsten Mal geschlossen.

      **Statusleiste behalten**, direkt darunter, zeigt die Uhr des Systems über Live View, statt den ganzen Bildschirm zu nutzen.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Live View bei Verbindung öffnen**."
  - id: leave
    title: "Live View verlassen, wenn Sie fertig sind"
    body: |
      Tippen Sie auf **Verlassen** oder auf Zurück, sobald Sie geparkt haben. Wenn Sie Live View verlassen, enden auch „Live gehen“, Browser View und Live-Kopien. Live View ist immer nur auf einem Handy oder Infotainment offen; verlassen Sie es also auf dem einen, bevor Sie es auf einem anderen öffnen.
check: "Die Stream-Anzeige meldet **Live**, die Straße bewegt sich, und der Stream-Zustand unter Details meldet **Gut**."
fixes:
  - q: "„Ihr comma ist online, fährt aber nicht“"
    a: "Das Auto ist aus, oder openpilot ist nicht gestartet. Live View kommt innerhalb von 30 Sekunden nach dem Start des Autos von selbst zurück, oder tippen Sie auf **Aktualisieren**."
  - q: "„Dieses comma ist nicht erreichbar“"
    a: "Ihr Handy muss im selben WLAN wie das comma sein oder in seinem Hotspot. Live View verbindet sich neu, wenn das comma antwortet, oder tippen Sie auf **Erneut versuchen**. Immer noch nichts? Siehe [CommaView findet Ihr comma nicht](/de/guides/comma-not-found)."
  - q: "„Live View ist auf einem anderen Gerät offen“"
    a: "Ihr comma streamt immer nur an ein Handy oder Infotainment. Gehen Sie in CommaView auf dem anderen Gerät zurück zur Startseite, dann startet Live View hier von selbst."
  - q: "„Fahrzeugdaten kommen nicht an“"
    a: "Das Video kommt an, aber Geschwindigkeit, Signale und Warnungen des Autos nicht. Starten Sie das comma neu, um das zu beheben."
  - q: "„Video verzögert“"
    a: "Seit einer Sekunde ist kein neues Bild angekommen. Live View zeigt das neben dem Bild an und verbindet sich von selbst neu, wenn das Video nicht zurückkommt."
  - q: "„Video dieses comma nicht abspielbar“"
    a: "Keiner der Videodecoder des Handys konnte es abspielen. CommaView versucht es weiter. Senden Sie einen Support-Bericht aus den Einstellungen, damit CommaView sich das ansehen kann: siehe [Einen Support-Bericht senden](/de/guides/support-bundle)."
related: [overlays, record, browser-view, car-screens]
---

## Sicherheit

Öffnen Sie Live View im Stand und lassen Sie es dann in Ruhe. Bedienen Sie CommaView nicht während der Fahrt: Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt. Die Warnungen Ihres comma und die Instrumente Ihres Autos haben Vorrang. CommaView zeigt nur, was das comma sieht.
