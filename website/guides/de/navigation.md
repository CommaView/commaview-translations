---
title: "Mit Ihrem eigenen Schlüssel für Stadia Maps navigieren"
description: "Fügen Sie Ihren Schlüssel für Stadia Maps hinzu, suchen Sie auf der Startseite einen Ort, wählen Sie eine Route und folgen Sie der Abbiegekarte in Live View. Senden Sie den Ort auch an Ihr comma."
topic: navigation
order: 1
kind: walkthrough
lede: "**Navigation** führt Sie in Live View zu einem Ort. Suchen Sie ihn auf der Startseite mit **Wohin?**, wählen Sie eine Route, tippen Sie auf **Start** und folgen Sie dann der Abbiegekarte und den Sprachansagen. Routen kommen von Stadia Maps mit Ihrem eigenen Schlüssel, der verschlüsselt auf Ihrem Handy bleibt. Die Führung ist nur eine Anzeige und steuert nie das Auto."
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "Angemeldet"
    text: "CommaView 0.0.167 oder neuer, angemeldet mit Ihrem Beta-Konto. Abgemeldet wird Navigation nicht angeboten."
  - title: "Ein Schlüssel für Stadia Maps"
    text: "Ein API-Schlüssel aus Ihrem eigenen Stadia-Maps-Konto. Routen werden unter Ihrem Konto und dessen Bedingungen angefragt."
  - title: "Standort des Autos an"
    text: "Die Führung folgt dem GPS Ihres comma. Schalten Sie auf der Startseite **Standort des Autos** für Ihr comma ein."
  - title: "Internet auf Ihrem Handy"
    text: "Für Suchen und Routen. Sie laufen über mobile Daten, wenn das WLAN des comma kein Internet hat."
howItWorks:
  - title: "Wohin?"
    text: "Findet Orte in der Nähe Ihres comma, aus den Daten von OpenStreetMap (Photon)."
    edge: "Ihr Schlüssel"
  - title: "Stadia Maps"
    text: "Plant die Routen, angefragt von Ihrem Handy mit Ihrem Schlüssel. Nichts läuft über CommaView."
  - title: "Live View"
    text: "Führt Sie ab der Position Ihres comma: Abbiegekarte, Karte und Sprachansagen."
steps:
  - id: open
    title: "Karten & Navigation öffnen"
    body: |
      Tippen Sie auf **Einstellungen**, dann auf **Karten & Navigation**. Angemeldet ist das die Zeile, wo früher „Offline-Karten“ stand.
    screen: support-settings
    pins:
      - target: maps-row
        text: "**Karten & Navigation**."
  - id: get-key
    title: "Einen Schlüssel bei Stadia Maps holen"
    body: |
      Unter **Ihr Schlüssel für Stadia Maps** meldet **API-Schlüssel** den Wert **Nicht hinzugefügt**. Tippen Sie auf **Schlüssel bei Stadia Maps holen**: Das öffnet die Registrierung von Stadia in Ihrem Browser. Registrieren Sie sich und kopieren Sie dann Ihren API-Schlüssel aus Ihrem Stadia-Maps-Dashboard.
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**Ihr Schlüssel für Stadia Maps**: „Routen brauchen deinen eigenen Stadia-Maps-Schlüssel…“"
      - target: get-key
        text: "**Schlüssel bei Stadia Maps holen** öffnet die Registrierung von Stadia."
      - target: add-key
        text: "**Hinzufügen**, sobald Sie Ihren Schlüssel kopiert haben."
    note: "Die Website von Stadia ist nicht abgebildet: Sie gehört Stadia. Ihr Dashboard zeigt Nutzung, Tarif und Limits Ihres Schlüssels."
  - id: add-key
    title: "Einfügen, dann „Prüfen und speichern“"
    body: |
      Tippen Sie zurück in CommaView auf **Hinzufügen**. Tippen Sie auf **Einfügen**, um Ihren Schlüssel ins Feld zu setzen, dann auf **Prüfen und speichern**. Um den Schlüssel zu prüfen, fragt CommaView bei Stadia Maps eine kurze Route zwischen zwei festen Punkten an, nichts von Ihnen: **Wird bei Stadia Maps geprüft…**. Ist er angenommen, zeigt **API-Schlüssel** ihn maskiert, etwa **•••• e1f0**.
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "**Ihr Stadia-Maps-API-Schlüssel**, maskiert."
      - target: paste
        text: "**Einfügen** aus der Zwischenablage."
      - target: check-and-save
        text: "**Prüfen und speichern**."
    note: "„Nur auf diesem Handy, verschlüsselt. Wird vor dem Speichern mit einer kurzen Route bei Stadia Maps geprüft.“ Er ist nie in einem Support-Paket oder einem Absturzbericht."
  - id: where-to
    title: "Auf der Startseite auf „Wohin?“ tippen"
    body: |
      Tippen Sie im Stand auf der Startseite unter der Karte Ihres comma auf **Wohin?**. Geben Sie einen Ort oder eine Adresse ein, oder tippen Sie aufs Mikrofon, um ihn zu sagen. Haben Sie sie gespeichert, sind **Zuhause** und **Arbeit** auf der Karte nur ein Tippen entfernt.
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**Wohin?** öffnet die Suche."
      - target: voice
        text: "**Wohin? per Sprache**."
      - target: home-chip
        text: "**Zuhause**, sobald Sie es gespeichert haben."
  - id: pick
    title: "Den Ort wählen"
    body: |
      Die Ergebnisse liegen in der Nähe Ihres comma, jedes mit Adresse und Entfernung, danach Ihre gespeicherten und letzten Orte. Tippen Sie auf den gewünschten.
    screen: navigation-search
    pins:
      - target: search-field
        text: "**Orte oder Adressen suchen**."
      - target: first-result
        text: "Ein Ergebnis, mit Adresse und Entfernung von Ihrem comma."
    note: "Während das Auto fährt, ist Tippen aus: „Tippen ist während der Fahrt aus. Nutzen Sie Sprache oder einen gespeicherten Ort.“"
  - id: start
    title: "Eine Route wählen und auf „Start“ tippen"
    body: |
      Die Routenvorschau zeigt die Route auf einer Karte, Fahrzeit, Entfernung und Ankunftszeit. Jede Route hat einen Chip: **Schnellste**, **Route 2** und so weiter. Tippen Sie auf **Start**: Die Führung beginnt und Live View öffnet sich.

      **Als Zuhause speichern** und **Als Arbeit speichern** behalten den Ort für ein Tippen auf der Startseite.
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "Die Routen: **Schnellste**, **Route 2**…"
      - target: start
        text: "**Start**."
      - target: save-home
        text: "**Als Zuhause speichern**, und daneben **Als Arbeit speichern**."
  - id: follow
    title: "In Live View folgen"
    body: |
      Die Abbiegekarte zeigt das nächste Abbiegen: den Pfeil, die Entfernung, die Anweisung und den Schritt danach, sowie die Ankunftszeit. Etwa 20 Sekunden vor jedem Abbiegen kommt eine Sprachansage, eine weitere kurz davor und eine bei der Ankunft. In der eigenen Fahransicht von CommaView werden Winkel auf Ihre Spur gemalt und quer über die Ausfahrt der Abbiegung.

      Verpassen Sie eine Abbiegung, kommt innerhalb von Sekunden eine neue Route. Die Fahrt endet von selbst, sobald Sie angekommen sind und ausgeschaltet haben.
    tabs:
      - label: "Handy"
        body: |
          Hochkant liegen Abbiegekarte und Karte unter dem Video.
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "Die Abbiegekarte."
          - target: end
            text: "**Navigation beenden**."
          - target: mute
            text: "**Sprachansage stummschalten**."
          - target: map-button
            text: "**Karte** blendet die Karte für die Fahrt aus und wieder ein."
      - label: "Bildschirm im Auto"
        body: |
          Auf einem Infotainment mit Platz neben dem Video liegen Karte und Abbiegekarte dort in einem eigenen Bereich. Wo kein Platz ist, blendet die CommaView-Ansicht die Karte in die Ecke des Videos ein. Ziehen Sie den Trenner, um die Breite des Bereichs zu ändern.
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "Die Abbiegekarte."
          - target: divider
            text: "Der Trenner, um die Breite der Karte zu ändern."
          - target: map-button
            text: "**Karte**."
    warn: "Richten Sie die Fahrt im Stand ein. Tippen Sie während der Fahrt nicht in CommaView herum: Abbiegekarte und Stimme sind dafür da, dass Sie es nicht müssen, und die Warnungen von openpilot und Ihrem Auto haben Vorrang."
  - id: send
    title: "Den Ort an Ihr comma senden, wenn Ihr Fork einen annimmt"
    body: |
      Unter **Start** bietet die Routenvorschau **An comma senden** für Forks an, deren eigene Navigation ein Ziel annimmt: StarPilot, carrotpilot und die Navigation (Alpha) von openpilot, mit der von sunnypilot darauf aufbauend. Andere Forks zeigen es nicht.

      Tippen Sie darauf. CommaView fragt zuerst und sagt, was der Fork mit seinen aktuellen Einstellungen am Fahren ändert, etwa vor Kurven abbremsen. Tippen Sie auf **Senden**: „An Ihren comma gesendet. StarPilot plant dort seine eigene Route.“ Der Fork plant mit seinem eigenen Dienst, seine Route kann also von der von CommaView abweichen. **Vom comma entfernen** nimmt das Ziel wieder herunter, und das Beenden der Fahrt entfernt es ebenfalls.
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**Senden**."
    note: "**Jede Fahrt an dieses comma senden**, unter „An comma senden“, sendet jede Fahrt, wenn Sie auf „Start“ tippen. Es pausiert von selbst, wenn sich die Fahreinstellungen des Forks ändern, bis Sie erneut zustimmen."
check: "Unter **Karten & Navigation** zeigt **API-Schlüssel** Ihren Schlüssel maskiert, und die Routenvorschau meldet **Routen von Stadia Maps · Die Führung ist nur Anzeige und steuert nie das Auto.**"
fixes:
  - q: "„Füge deinen eigenen Stadia-Maps-Schlüssel hinzu, um Routen zu erhalten: Einstellungen › Karten & Navigation.“"
    a: "Es ist noch kein Schlüssel gespeichert. Tippen Sie in der Routenvorschau auf **Schlüssel hinzufügen**, oder folgen Sie [Schritt 2 und 3](#step-get-key). „Wohin?“, Suche und Orte funktionieren auch ohne."
  - q: "„Stadia Maps hat diesen Schlüssel nicht angenommen (401). Prüfen Sie, ob er vollständig aus Ihrem Dashboard kopiert ist.“"
    a: "Kopieren Sie den Schlüssel erneut vollständig aus Ihrem Stadia-Maps-Dashboard und fügen Sie ihn noch einmal ein."
  - q: "„Das ist kein Schlüssel für Stadia Maps.“"
    a: "Was Sie eingefügt haben, sieht nicht wie ein API-Schlüssel aus, deshalb wurde nichts gesendet. Kopieren Sie den API-Schlüssel aus Ihrem Stadia-Maps-Dashboard: Buchstaben, Ziffern und Bindestriche."
  - q: "„Stadia Maps hat diesen Schlüssel abgelehnt (403): Sein Tarif enthält vielleicht kein Routing.“"
    a: "Prüfen Sie Ihren Tarif in Ihrem Stadia-Maps-Dashboard."
  - q: "„Ihr Schlüssel für Stadia Maps ist über seinem Limit (429)“"
    a: "Die Guthaben dieses Monats sind aufgebraucht, oder er hat gerade zu oft angefragt. Prüfen Sie ihn in Ihrem Stadia-Maps-Dashboard. Die App fragt fünf Minuten lang nicht mehr mit ihm an."
  - q: "„Stadia Maps war zum Prüfen des Schlüssels nicht erreichbar. Prüfen Sie die Internetverbindung von diesem Handy und versuchen Sie es erneut.“"
    a: "Ihr Handy hat gerade kein Internet. Versuchen Sie es erneut mit mobilen Daten oder einem WLAN mit Internet."
  - q: "Auf der Startseite gibt es kein **Wohin?**"
    a: "Navigation gibt es ab CommaView 0.0.167 für angemeldete Mitglieder. Abgemeldet, oder mit einem Pass, der sich nicht bestätigen lässt, wird sie nicht angeboten. In Festlandchina ist sie aus."
  - q: "Die Abbiegekarte meldet „Standort des Autos ist aus“"
    a: "Die Führung braucht die Position Ihres comma. Schalten Sie auf der Startseite **Standort des Autos** für dieses comma ein."
  - q: "Die Abbiegekarte meldet „Wartet auf GPS“"
    a: "Die Führung beginnt mit der ersten Positionsbestimmung Ihres comma. Geben Sie ihm unter freiem Himmel einen Moment."
  - q: "„Zu weit für eine Fahrt“"
    a: "Die Navigation plant Routen zu Orten bis 1.500 km (930 Meilen) entfernt. Wählen Sie einen Zwischenstopp und fahren Sie von dort weiter."
  - q: "**An comma senden** fehlt"
    a: "Es erscheint nur in der Routenvorschau und nur für einen Fork, dessen Navigation ein Ziel annimmt: StarPilot, carrotpilot oder die Navigation (Alpha) von openpilot oder sunnypilot."
  - q: "„Dein comma ist nicht erreichbar, um ihm diese Fahrt zu senden.“"
    a: "Verbinden Sie dieses Handy mit demselben Netz wie Ihr comma und tippen Sie dann auf **Erneut versuchen**."
  - q: "„Die Navigation (Alpha) von openpilot ist auf Ihrem comma aus.“"
    a: "Tippen Sie im Stand auf **Navigation (Alpha) einschalten**. Bei Release-Builds, die sie bei jedem Start ausschalten, lässt sie sich noch nicht dauerhaft einschalten."
related: [live-view, car-screens, overlays]
---

## Die Karte in Live View

**Einstellungen › Karten & Navigation › Karte in Live View** legt fest, wo sie erscheint:

- **Anordnung**: **Automatisch** (neben dem Video, wo Platz ist, sonst in der Ecke), **Neben dem Video** oder **In der Ecke**. Die Ansichten comma 3X, comma four, StarPilot und Surround zeigen die Karte immer neben dem Video.
- **Breite neben dem Video** stellen Sie ein, indem Sie in Live View den Trenner ziehen. **Zurücksetzen** stellt sie zurück.
- **Kartenstil**: **Wie die App** (Standard: hell, solange CommaView hell ist, dunkel, solange es dunkel ist), **Auto** (hell von Sonnenaufgang bis Sonnenuntergang dort, wo Ihr comma ist), **Wie das Handy**, **Hell** oder **Dunkel**. Er gilt für jede Karte: die in Live View, die Standortkarte auf der Startseite, **Standort des Autos** und die Routenvorschau.

## Sprachansagen und Ihre Orte

- **Sprachansagen** schaltet die Ansagen aus und ein. Der Lautsprecher der Abbiegekarte, **Sprachansage stummschalten**, ist dieselbe Einstellung.
- **Ihre Orte**: **Zuhause** und **Arbeit** sowie **Letzte Orte**, auf diesem Handy gespeichert. **Löschen** entfernt die letzten Orte.

## Ein Ort aus einer anderen App

Teilen Sie in Google Maps oder einer anderen Karten-App einen Ort und wählen Sie **Mit CommaView navigieren**. Seine Routenvorschau öffnet sich auf der Startseite, wie die eines gespeicherten Orts.

## Mapbox

Bietet Ihr Konto das an, kann Einstellungen › Karten & Navigation statt mit Stadia Maps mit Ihrem eigenen Mapbox-Token routen.

## Datenschutz

Ihr Schlüssel für Stadia Maps bleibt nur auf diesem Handy, verschlüsselt, und wird nie protokolliert oder in ein Support-Paket gelegt. Routen gehen damit von Ihrem Handy an Stadia Maps; nichts geht an den Kontodienst von CommaView. Suchen gehen an Photon, in der Nähe der Position Ihres comma. Wenn Sie Ihren Schlüssel löschen oder sich abmelden, wird er vom Handy entfernt.

## Sicherheit

Richten Sie eine Fahrt im Stand ein und lassen Sie sich von Abbiegekarte und Stimme führen. Navigation ist nur eine Anzeige: Sie lenkt nie, bremst nie und ändert nichts an dem, was openpilot tut. Bedienen Sie CommaView nicht während der Fahrt: Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt.
