---
title: "Die Fahransicht wählen und Overlay-Pakete hinzufügen"
description: "Wählen Sie, wie Live View die Straße zeichnet: die Ansicht des comma four, des comma 3X oder die eigene von CommaView. Fügen Sie dann ein Overlay-Paket für das hinzu, was Ihr Fork selbst zeichnet."
topic: screens
order: 6
kind: walkthrough
lede: "Live View zeichnet eine Fahransicht über die Straßenkamera: die des **comma four**, des **comma 3X** oder die eigene von **CommaView**. Die comma-Ansichten werden im Stil Ihres Forks gezeichnet. **Overlay-Pakete** fügen hinzu, was die eigene Ansicht Ihres Forks zeichnet und CommaView nicht, etwa die Hybrid-Anzeigen von BluePilot oder den Regenbogenpfad von dragonpilot."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funktioniert"
    text: "CommaView auf einem Android-Handy, gekoppelt mit Ihrem comma. Noch nicht? [CommaView einrichten](/de/guides/setup)."
  - title: "Für den Store angemeldet"
    text: "Mitglieder sehen die Pakete von CommaView. Abgemeldet können Sie trotzdem ein Paket aus einer Datei oder über einen Link hinzufügen."
steps:
  - id: switch
    title: "In Live View die Ansicht wechseln"
    body: |
      Tippen Sie in Live View auf den Umschalter der Fahransicht. Er ist nach der Ansicht benannt, die er zeigt, und jedes Tippen wechselt zur nächsten: **comma 4**, **comma 3X**, **CommaView** und wieder von vorn. Die Ansicht, bei der Sie aufhören, bleibt fürs nächste Mal.
    screen: phone-live-view
    clip: onroad-screen
    pins:
      - target: onroad-screen-button
        text: "Der Umschalter der Fahransicht, benannt nach der Ansicht, die er zeigt."
    note: "Passt er nicht neben die anderen Bedienelemente, steht er unter **Mehr**, als **Fahransicht**. Während einer Aufnahme ist er abgeblendet: Eine Aufnahme behält die Ansicht, mit der sie begonnen hat."
  - id: display
    title: "Oder unter Einstellungen › Anzeige wählen"
    body: |
      Um jede Ansicht vor der Wahl zu sehen, öffnen Sie **Einstellungen › Anzeige**. Die Karte **Fahransicht** zeigt eine Vorschau der gewählten Ansicht auf einem Straßenfoto, mit dem Bildausschnitt Ihrer comma-Kameras und im Stil Ihres Forks. **Aktiv**, **Eingriff** und **Deaktiviert** darunter ändern den gezeigten Moment; sie speichern nichts.
    screen: settings-display
    pins:
      - target: onroad-screen-card
        text: "Die Vorschau der gewählten Ansicht."
      - target: onroad-screen
        text: "**Fahransicht**: Tippen Sie darauf, um die Liste zu sehen."
  - id: pick
    title: "Eine Ansicht wählen"
    body: |
      Jede Ansicht in der Liste hat ein kleines Bild und eine Notiz:

      - **comma four**: MAX über der Straße, wenn es sich ändert, Lenkrad und Konfidenz daneben.
      - **comma 3X**: ein Statusrahmen, das MAX-Feld, ein großes Tempo und Hinweise am unteren Rand.
      - **CommaView**: ein fließender Pfad, eine Zielerfassung des Vorderfahrzeugs und eigene Tempo-, Status- und Hinweisanzeigen von CommaView.

      Die Wahl wird gespeichert und ändert die Vorschau, ihre Optionen und Live View. Jede Ansicht funktioniert auf beiden comma-Modellen.
    screen: settings-display-onroad-screens
    clip: display-pick
    pins:
      - target: comma-four-option
        text: "**comma four**."
      - target: comma-3x-option
        text: "**comma 3X**."
      - target: commaview-option
        text: "**CommaView**."
    note: "Hinweise, Warnungen und der Status der Fahrerüberwachung nutzen immer die Farben Ihres comma, egal welche Ansicht Sie wählen."
  - id: store
    title: "Den Store für Overlay-Pakete öffnen"
    body: |
      Öffnen Sie **Einstellungen › Overlay-Pakete**, oder tippen Sie auf der Startseite auf die Karte **Overlay-Pakete**.
    tabs:
      - label: "Angemeldet"
        body: |
          Der Store listet zuerst die **offiziellen** Pakete von CommaView, dann die der **Community**, jedes von CommaView geprüft. **Für Ihr comma** bietet das offizielle Paket für den Fork an, den Ihr comma nutzt. Suchen Sie, oder grenzen Sie die Liste mit **Alle**, **Offiziell**, **Community** und **Für meine commas** ein.
        screen: overlay-packs-store
        pins:
          - target: search
            text: "**Pakete suchen**."
          - text: "**Für Ihr comma**: das offizielle Paket für den Fork Ihres comma."
          - target: bluepilot-row
            text: "Die **offiziellen** Pakete, etwa BluePilot HUD."
          - target: yours
            text: "**Ihre Pakete**: was auf diesem Handy ist."
      - label: "Aus einer Datei oder über einen Link"
        body: |
          Hat jemand eine `.cvpack`-Datei oder einen Link geteilt (GitHub, ein Gist, ein Discord-Anhang)? Öffnen Sie **Ihre Pakete** und tippen Sie unter **Paket selbst hinzufügen** auf **Aus Datei installieren** oder **Link einfügen**. Ein so hinzugefügtes Paket hat CommaView nicht geprüft, und der Installationsdialog sagt das.
  - id: install
    title: "Ein Paket installieren"
    body: |
      Tippen Sie auf ein Paket, um seine Vorschau zu sehen, die Forks, mit denen es **funktioniert**, und was es Live View hinzufügt. Tippen Sie auf **Installieren** und im Dialog erneut auf **Installieren**. Das Paket geht auf dieses Handy und auf Ihre gekoppelten commas.
    screen: overlay-pack-detail
    pins:
      - text: "Die Vorschau: Live View mit dem Paket. Zum Vergrößern antippen."
      - target: install
        text: "**Installieren**."
    note: "Ein offizielles Paket läuft nur auf den Forks, für die es gemacht ist. Nutzt keines Ihrer gekoppelten commas einen davon, sagt der Dialog das; es wird trotzdem installiert, erscheint aber erst in Live View, wenn eines es tut."
  - id: drive
    title: "Bei der nächsten Fahrt ansehen"
    body: |
      Nach der Installation sagt der Store, dass das Paket auf Ihr comma geht, sobald dieses Handy es erreicht, und dort startet, wenn das Auto aus ist. Öffnen Sie bei Ihrer nächsten Fahrt Live View: Das Paket zeichnet auf den Ansichten comma four, comma 3X und CommaView, unter den eigenen Hinweisen der Fahransicht.

      Um ein Paket auszuschalten, öffnen Sie **Ihre Pakete**: Jedes Paket hat einen Schalter, für dieses Handy und jedes gekoppelte comma zusammen.
check: "In den **Details** von Live View nennt die Zeile **Overlay-Pakete** das Paket und meldet, dass es **läuft**."
fixes:
  - q: "Der Umschalter der Fahransicht ist abgeblendet"
    a: "Eine Aufnahme läuft. Stoppen Sie sie oder warten Sie, bis sie endet, und wechseln Sie dann."
  - q: "Die Details melden, das Paket sei „nicht für diesen Fork“"
    a: "Das Paket ist für die Ansicht eines anderen Forks gemacht und zeichnet auf Ihrer nichts. Offizielle Pakete sagen unter **Funktioniert mit**, für welche Forks sie sind."
  - q: "Das Paket ist noch nicht in Live View"
    a: "Es erreicht Ihr comma, sobald Ihr Handy sich damit verbindet, und startet dort, wenn das Auto aus ist. Schalten Sie das Auto aus und wieder ein, während Ihr Handy im Netz des comma ist, und öffnen Sie dann Live View."
  - q: "„Anmelden, um die Pakete von CommaView zu sehen“"
    a: "Der Store zeigt die Pakete von CommaView angemeldeten Mitgliedern. Tippen Sie auf **Anmelden**. Pakete, die schon auf dem Handy sind, funktionieren auch abgemeldet weiter."
  - q: "„my.commaview.com nicht erreichbar“"
    a: "Prüfen Sie die Internetverbindung dieses Handys und tippen Sie dann auf **Erneut versuchen**. **Ihre Pakete** listet weiterhin alles, was auf dem Handy ist."
related: [live-view, record, forks]
blogPost: commaview-0-0-166-languages-browser-view
---

## Die Optionen jeder Ansicht

Unter der Vorschau zeigt **Einstellungen › Anzeige** die eigenen Optionen der gewählten Ansicht:

- **Optionen für comma four**: **Vorschau-Ausschnitt** (genau den Ausschnitt des comma four, mehr vom Kamerabild, oder zugeschnitten, um diesen Bildschirm zu füllen) und **Kompaktes Konfidenzfeld** (ein kleineres Feld und eine kleinere Kugel, für mehr Video).
- **Optionen für CommaView**: **Bildausschnitt** (**Füllen** schneidet das Kamerabild zu, um ein Querformat-Display zu füllen; **Ganzes Kamerabild** zeigt alles, mit schwarzen Balken, wo nötig) und **Bewegung reduzieren**, das Pfad, Tempo und Zielerfassung von CommaView ruhig hält.
- **comma 3X**: keine. Sie wird so gezeichnet, wie das comma sie zeichnet.

Dann, **Auf jeder Ansicht**: **Fahrerseite**, die die Bedienelemente spiegelt, **Design**, **Kontrast bei Tageslicht** für Sonne und Blendung, und **Ränder des Bildschirms** für einen Bildschirm im Auto, der die Ränder des Bildes abschneidet ([Bildschirme im Auto](/de/guides/car-screens)).

Eine Wiedergabe, die Sie in „Aufnahmen“ erstellen, zeichnet, was Live View während der Aufnahme gezeichnet hat, egal was Sie später wählen.

## Woher eine Einblendung kommt

CommaView rät nicht, was es zeichnen soll. Die Runtime auf Ihrem comma sendet neben dem Video dieselben Fahrdaten, die die eigene Ansicht von openpilot liest (Pfad, Fahrspuren, das Vorderfahrzeug, Geschwindigkeiten, Hinweise, Fahrerüberwachung), und die App zeichnet sie auf Ihrem Handy, passend zur gezeigten Kamera. Kommen diese Daten zu spät, fehlen sie oder sind sie für eine andere Kamera gedacht, lässt CommaView diesen Teil weg, statt etwas zu zeichnen, das falsch sein könnte.

## Sicherheit

Wählen Sie die Ansicht und installieren Sie Pakete im Stand. Bedienen Sie CommaView nicht während der Fahrt: Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt. Eine Einblendung ist etwas zum Ansehen, keine Fahrhilfe: Die Warnungen Ihres comma und die Instrumente Ihres Autos haben Vorrang. Das Symbol der Fahrerüberwachung beweist keine Aufmerksamkeit, und die Einblendung einer Wiedergabe dient dem Rückblick auf eine Fahrt, nicht als Beweis dafür, was genau passiert ist.
