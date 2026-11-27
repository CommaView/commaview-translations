---
title: "Auf YouTube oder einem anderen Server live gehen"
description: "Streamen Sie, was Live View zeigt, die Straße und ihre Fahransicht, auf Ihren YouTube-Kanal oder einen RTMP-Server, in 720p oder 1080p. Einmal einrichten, dann aus Live View live gehen."
topic: screens
order: 5
kind: walkthrough
lede: "**Live gehen** streamt, was Live View zeigt, die Straße und ihre Fahransicht, von Ihrem Handy auf Ihren YouTube-Kanal oder einen beliebigen RTMP-Server, in 720p oder 1080p. Richten Sie es einmal in den Einstellungen ein und starten Sie es dann aus Live View."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funktioniert"
    text: "CommaView auf einem Android-Handy, gekoppelt mit Ihrem comma. Noch nicht? [CommaView einrichten](/de/guides/setup)."
  - title: "Ein Ziel zum Streamen"
    text: "Ein YouTube-Kanal zum Anmelden, oder ein Streamschlüssel aus YouTube Studio oder von einem anderen RTMP-Server."
  - title: "Internet auf dem Handy"
    text: "Hat das WLAN des comma kein Internet, nutzt der Stream die mobilen Daten Ihres Handys: etwa 1,4 GB pro Stunde bei 720p."
howItWorks:
  - title: "Ihr comma"
    text: "Sendet Live View wie gewohnt an Ihr Handy."
  - title: "Ihr Handy"
    text: "Streamt, was Live View zeichnet: 20 Bilder pro Sekunde, 720p oder 1080p."
    edge: "Internet"
  - title: "YouTube oder Ihr Server"
    text: "Zeigt es allen, die Sie zusehen lassen."
steps:
  - id: settings
    title: "Einstellungen › Livestream öffnen"
    body: |
      Öffnen Sie **Einstellungen** und tippen Sie auf **Livestream**. Bis Sie ihn eingerichtet haben, steht in der Zeile **Einrichten**.
    screen: support-settings
    pins:
      - target: live-streaming-row
        text: "**Livestream**."
  - id: destination
    title: "Wählen, wohin gestreamt wird"
    tabs:
      - label: "Mit YouTube anmelden"
        body: |
          Tippen Sie auf **Mit YouTube anmelden**. Die Anmeldung von Google öffnet sich in Ihrem Browser, wo Sie Konto und Kanal wählen. Angemeldet erstellt „Live gehen“ jede Übertragung auf Ihrem Kanal, und YouTube startet sie von selbst: kein Streamschlüssel, nichts in YouTube Studio zu drücken. Die Karte **Ziel** zeigt dann Ihren Kanal, **Angemeldet**.
        screen: settings-live-streaming
        pins:
          - target: destination-row
            text: "**Ziel**: Ihr Kanal, angemeldet."
        note: "Die Anmeldeseiten von Google sind nicht abgebildet."
      - label: "Ein Streamschlüssel oder Server"
        body: |
          Tippen Sie auf **Streamschlüssel nutzen** (oder **Ziel einrichten**), wählen Sie die **Plattform**, **YouTube** oder **Anderer Server**, und fügen Sie den Streamschlüssel ein. Für YouTube: In YouTube Studio auf Erstellen › Livestream starten › Stream gehen, den Streamschlüssel kopieren und dort Autostart einschalten, damit jede Übertragung startet, sobald das Video ankommt. Für einen anderen Server fügen Sie auch seine `rtmp://`- oder `rtmps://`-Adresse ein. Tippen Sie auf **Ziel speichern**.
        screen: settings-live-streaming-destination
        pins:
          - target: platform
            text: "**Plattform**."
          - target: stream-key
            text: "Der Streamschlüssel. Er bleibt nur auf diesem Handy und wird nur an den Server gesendet, für den er ist."
          - target: save
            text: "**Ziel speichern**."
        note: "`rtmp://` sendet Ihren Streamschlüssel unverschlüsselt. Nutzen Sie `rtmps://`, wenn Ihr Server es anbietet."
  - id: choices
    title: "Zuschauer, Qualität und Ton prüfen"
    body: |
      - **Wer zusehen kann** (bei YouTube angemeldet): **Öffentlich**, **Nicht gelistet** oder **Privat**. Voreingestellt ist **Nicht gelistet**. Mit einem Streamschlüssel wählen Sie es in YouTube Studio. Wer zusieht, sieht, wo Sie fahren.
      - **Titel und Beschreibung** (bei YouTube angemeldet): wie jede Übertragung heißt, mit Chips für Datum, Auto und mehr.
      - **Qualität**: 720p oder 1080p, jeweils mit den ungefähren mobilen Daten pro Stunde.
      - **Ton**: aus, wenn Sie nicht das Mikrofon Ihres comma oder dieses Handys wählen. Alle im Auto sind zu hören, auch Beifahrer. Der Ton geht nur in Ihren Stream und Ihre Live-Kopien, nie an CommaView.

      **Bevor Sie live gehen** fasst alles zusammen: Datenverbrauch, Fahrerkamera und wann der Stream stoppt.
    screen: settings-live-streaming
    pins:
      - text: "**Titel und Beschreibung**."
      - target: sound-row
        text: "**Ton**."
  - id: go
    title: "In Live View auf „Live gehen“ tippen"
    body: |
      Öffnen Sie Live View und tippen Sie auf **Live gehen**. Kurz steht dort, dass der Stream startet, dann zeigt es, wie lange Sie schon live sind. Starten Sie es, bevor Sie losfahren, und lassen Sie es dann in Ruhe.
    screen: phone-live-view
    pins:
      - target: go-live-button
        text: "**Live gehen**. Wo es nicht passt, steht es unter **Mehr**."
    warn: "Der Stream zeigt die Fahrerkamera, sobald **Fahrercam** an ist, und **Fahrercam** meldet dann **Live**. Schalten Sie **Fahrercam** aus, um die Fahrerkamera aus dem Stream zu halten."
  - id: share
    title: "Den Zuschauer-Link teilen"
    body: |
      In **Details** meldet die Zeile des Streams **Live** und wie lange, mit der Senderate, den verbrauchten Daten und dem Netz. Bei YouTube angemeldet teilt **Link teilen** darunter den `youtu.be`-Link Ihrer Übertragung.
    screen: phone-live-view-go-live
    pins:
      - target: stop-live
        text: "**Live gehen**, live, mit seinem Timer."
      - target: streaming
        text: "**Live** und wie lange."
      - target: share-watch-link
        text: "**Link teilen**."
  - id: stop
    title: "Den Stream nach dem Parken stoppen"
    body: |
      Tippen Sie erneut auf **Live gehen**, um zu stoppen. Der Stream stoppt auch, wenn Sie Live View verlassen, über **Stoppen** in seiner Benachrichtigung und von selbst eine Minute, nachdem sein Video stoppt. Er läuft weiter, wenn Sie die App wechseln oder das Handy sperren.
check: "**Live gehen** in Live View zeigt einen laufenden Timer in den Live-Farben, Details meldet **Live**, und Ihre Übertragung läuft auf YouTube oder Ihrem Server."
fixes:
  - q: "In Live View gibt es kein „Live gehen“"
    a: "Der Livestream ist noch nicht eingerichtet: Details meldet **Richten Sie den Livestream in den Einstellungen ein, um von hier live zu gehen**. Oder es steht unter **Mehr**, wenn nicht alle Bedienelemente passen."
  - q: "„Streamschlüssel unter Einstellungen › Livestream hinzufügen“"
    a: "„Live gehen“ hat kein Ziel. Melden Sie sich unter **Einstellungen › Livestream** bei YouTube an oder fügen Sie dort einen Streamschlüssel hinzu."
  - q: "Die YouTube-Übertragung startet mit einem Streamschlüssel nicht"
    a: "Mit einem Streamschlüssel starten Sie jede Übertragung in YouTube Studio mit „Live gehen“, oder schalten Sie dort Autostart ein. Mit YouTube angemeldet startet sie von selbst."
  - q: "„Der Schlüssel enthält ein Leerzeichen“"
    a: "Kopieren Sie den Schlüssel erneut aus Ihrem Streamingdienst und fügen Sie ihn ein."
  - q: "„Kein Ton: Browser View läuft ohne“"
    a: "„Live gehen“ teilt das Bild von Browser View, und das hat keinen Ton. Stoppen Sie Browser View, bevor Sie live gehen, um Ton zu haben. Dasselbe gilt für eine Aufnahme, die ohne Ton gestartet ist."
  - q: "Der Stream stoppt von selbst"
    a: "Live View sagt jedes Mal in einer Meldung, warum. Ein Stream stoppt außerdem eine Minute, nachdem sein Video stoppt, und wenn Sie Live View verlassen."
related: [live-view, browser-view, live-copy]
blogPost: commaview-0-0-165-go-live-send-to-commaview
---

## Eine Kopie jedes Streams behalten

**Einstellungen › Aufnahmen › Jeden Livestream speichern** speichert von jedem „Live gehen“ eine MP4 in „Aufnahmen“, so wie sie gesendet wurde, in der Qualität des Streams. Sie bleibt auf Ihrem Handy. Siehe [Eine Live-Kopie behalten](/de/guides/live-copy).

## Was im Stream ist und was nicht

- **Darin:** die Straße mit der Fahransicht darüber und die Fahrerkamera, solange **Fahrercam** an ist.
- **Nicht darin:** die Bedienelemente von Live View, Details und Meldungen. Die Karte der Navigation nur mit **Karte im Stream**, wo die Einstellungen das anbieten, und nur die Karte in der Ecke der CommaView-Ansicht.
- „Aufnehmen“ und „Live gehen“ sind unabhängig: Sie können eine Fahrt gleichzeitig aufnehmen und streamen.

## Sicherheit

Richten Sie „Live gehen“ im Stand ein und starten Sie es dort, dann lassen Sie es in Ruhe. Bedienen Sie CommaView nicht während der Fahrt: Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt. Wer zusieht, sieht, wo Sie fahren.
