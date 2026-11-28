---
title: "CommaView findet Ihr comma nicht"
description: "Die Startseite meldet Offline, oder Live View erreicht Ihr comma nicht? Prüfen Sie das Netzwerk, die Adresse des comma und seine Kopplung, in dieser Reihenfolge."
topic: troubleshooting
order: 2
kind: fixes
lede: "CommaView spricht direkt über Ihr lokales Netzwerk mit Ihrem comma, ohne Cloud-Dienst dazwischen. Findet es das comma nicht, sind Ihr Handy und das comma fast immer in verschiedenen Netzen, das comma schläft bei ausgeschaltetem Auto, oder seine Adresse hat sich geändert. Prüfen Sie das zuerst, dann die Kopplung."
parked: true
updated: 2026-11-27
needs:
  - title: "Das Auto an"
    text: "Das comma schläft, wenn das Auto aus ist. Schalten Sie das Auto ein, in P."
  - title: "Ein Netzwerk"
    text: "Ihr Handy im selben WLAN wie das comma oder in seinem Hotspot. Im Auto: [im Auto verbinden](/de/guides/connect-in-the-car)."
steps:
  - id: home
    title: "Sehen, was die Startseite meldet"
    body: |
      Erreicht Ihr Handy das comma nicht, zeigt die Startseite es als **Offline**, mit **Neu verbinden** und einer Karte **Keine Verbindung?**: „Ihr Handy muss im selben WLAN wie das comma oder in seinem Hotspot sein. Das comma schläft, wenn das Auto aus ist.“

      Prüfen Sie beides und tippen Sie dann auf **Neu verbinden**.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Neu verbinden**."
      - target: cant-connect
        text: "Die Karte **Keine Verbindung?**."
  - id: live-view
    title: "In Live View: warten oder erneut versuchen"
    body: |
      Live View sagt, warum es angehalten hat. **Dieses comma ist nicht erreichbar** heißt, dass Ihr Handy es im Netzwerk nicht erreicht. Es verbindet sich von selbst neu, wenn das comma antwortet; **Erneut versuchen** versucht es sofort.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**Dieses comma ist nicht erreichbar**: warum Live View angehalten hat."
      - target: retry
        text: "**Erneut versuchen**."
  - id: network
    title: "Das Netzwerk Ihres Handys prüfen"
    body: |
      Öffnen Sie die WLAN-Einstellungen Ihres Handys und prüfen Sie, ob es mit dem Netz verbunden ist, in dem das comma ist: dasselbe WLAN zu Hause, der Hotspot Ihres Handys mit dem comma darin oder der eigene Hotspot des comma.

      - Ein Handy, das ein WLAN ohne Internet zugunsten mobiler Daten verlassen hat, erreicht das comma nicht. Verbinden Sie es erneut.
      - Ein VPN auf Ihrem Handy kann seinen Datenverkehr woandershin leiten. Schalten Sie es aus und versuchen Sie es erneut.
      - Manche Hotspots verhindern, dass sich die Geräte darin gegenseitig erreichen. Versuchen Sie ein anderes Netz, etwa den eigenen Hotspot des comma.
    note: "Die WLAN- und Hotspot-Einstellungen von Android sind nicht abgebildet: Sie sehen auf jedem Handy anders aus."
  - id: address
    title: "Die Adresse des comma prüfen"
    body: |
      Das comma bekommt eine neue Adresse, wenn es einem anderen Netz beitritt oder ein Router ihm eine neue gibt. CommaView findet es von selbst wieder, wenn es das comma im Netz sieht; wenn nicht, speichern Sie die Adresse selbst.

      Suchen Sie auf dem comma seine IP-Adresse unter **Einstellungen → Netzwerk**. Öffnen Sie in CommaView auf der Startseite die **Einstellungen des Geräts**, tippen Sie auf **Name oder Adresse ändern**, bearbeiten Sie **IP-Adresse**, geben Sie die Adresse des comma ein und tippen Sie auf **Speichern**.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "Die IP-Adresse des comma."
      - target: save
        text: "**Speichern**."
  - id: add
    title: "Immer noch nicht gefunden? Erneut hinzufügen"
    body: |
      Tippen Sie auf der Startseite auf **comma hinzufügen**. **In diesem Netz** listet commas mit CommaView im Netz Ihres Handys: Tippen Sie auf Ihres. Steht es nicht dort, tippen Sie auf **Adresse und Code eingeben**, oder auf **QR-Code scannen**, mit einem Handy, das schon damit gekoppelt ist.
    screen: add-comma
    pins:
      - target: found-comma
        text: "**In diesem Netz**: ein comma in der Nähe."
      - target: enter-address
        text: "**Adresse und Code eingeben**."
      - target: scan-qr
        text: "**QR-Code scannen**."
  - id: pair
    title: "Mit seiner Adresse und einem neuen Code koppeln"
    body: |
      Geben Sie die IP-Adresse des comma und einen Kopplungscode oder eine Einladung ein und tippen Sie auf **comma koppeln**. Codes laufen schnell ab: Ein Handy, das schon mit dem comma gekoppelt ist, zeigt einen neuen in den **Einstellungen des Geräts** unter **Weiteres Handy oder Tablet koppeln**.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "Die IP-Adresse des comma."
      - target: pair-code
        text: "**Kopplungscode oder Einladung**."
      - target: pair
        text: "**comma koppeln**."
    note: "Klappt es mit der eingegebenen Adresse, aber das comma erscheint nie von selbst, verbirgt das Netz die Suche von CommaView. Das ist in Ordnung: Entscheidend ist die Adresse."
check: "Die Startseite zeigt Ihr comma als **Verbunden**, und **Live View öffnen** öffnet das Bild."
fixes:
  - q: "„Dieses comma ist nicht erreichbar“"
    a: "Ihr Handy muss im selben WLAN wie das comma sein oder in seinem Hotspot. Live View verbindet sich neu, wenn es antwortet. Prüfen Sie das Netzwerk ([Schritt 3](#step-network)) und die Adresse des comma ([Schritt 4](#step-address))."
  - q: "„CommaView antwortet nicht“"
    a: "Das comma antwortet, aber CommaView darauf nicht. Es startet vielleicht gerade auf dem comma neu: Live View verbindet sich neu, sobald es zurück ist. Bleibt es so, starten Sie das comma im Stand neu."
  - q: "„Kein Video von diesem comma“"
    a: "Es antwortet, aber sein Video kam nicht zurück. Versuchen Sie es erneut, oder gehen Sie zurück und prüfen Sie das comma: openpilot startet vielleicht noch."
  - q: "„Live View ist auf einem anderen Gerät offen“"
    a: "Dieses comma streamt immer nur an ein Handy oder Infotainment. Gehen Sie in CommaView auf dem anderen Gerät zurück zur Startseite, dann startet Live View hier von selbst."
  - q: "„Das comma hat nicht rechtzeitig geantwortet.“"
    a: "Eine schwache oder ausgelastete Verbindung. Prüfen Sie, ob Ihr Handy im WLAN oder Hotspot des comma ist, gehen Sie wenn möglich näher heran und versuchen Sie es erneut."
  - q: "„Das comma hat die Verbindung abgelehnt. CommaView startet darauf vielleicht neu.“"
    a: "Warten Sie einen Moment, bis es zurück ist, und versuchen Sie es dann erneut."
  - q: "„Fahrzeugdaten kommen nicht an“"
    a: "Das Video kommt an, aber Geschwindigkeit, Signale und Warnungen des Autos nicht. Starten Sie das comma neu, um das zu beheben."
  - q: "„Kopplung fehlgeschlagen: Kopplungscode abgelaufen. Erzeugen Sie einen neuen Code und versuchen Sie es erneut.“"
    a: "Holen Sie einen neuen Code von einem Handy, das schon mit dem comma gekoppelt ist, unter **Einstellungen des Geräts › Weiteres Handy oder Tablet koppeln**, und koppeln Sie erneut."
  - q: "„Kopplung fehlgeschlagen: ungültiger Kopplungscode. Prüfen Sie den Code oder scannen Sie den QR-Code.“"
    a: "Prüfen Sie den eingegebenen Code (Bindestriche sind optional) oder scannen Sie stattdessen seinen QR-Code."
  - q: "„Runtime dieses comma aktualisieren“ oder „CommaView aktualisieren“"
    a: "Diese App und die Runtime des comma liegen zu weit auseinander, um miteinander zu sprechen. Aktualisieren Sie das Genannte: die Runtime in den Einstellungen des Geräts ([Die Runtime aktualisieren](/de/guides/update-runtime)) oder die App."
  - q: "„Gespeicherte commas unlesbar“"
    a: "Die auf diesem Handy gespeicherten commas ließen sich nicht lesen, deshalb wird keines gezeigt. Sie wurden nicht gelöscht. Versuchen Sie es erneut, oder tippen Sie auf **Neu beginnen** und koppeln Sie jedes comma erneut: Die alte Liste bleibt mindestens 90 Tage erhalten."
related: [connect-in-the-car, setup-troubleshooting, another-phone]
---

## Wie CommaView ein comma findet

- **Die Suche** findet commas mit CommaView im Netz Ihres Handys, damit Sie keine Adressen eingeben müssen. Manche Netze blockieren sie.
- **Die Adresse** ist das, womit sich CommaView verbindet. Sie einzugeben funktioniert, ob die Suche klappt oder nicht.
- **Die Kopplung** gibt Ihrem Handy mit einem kurzlebigen Code einen eigenen Schlüssel für das comma. Suche und Kopplung sind getrennt: Ein comma, das Ihr Handy erreicht, muss trotzdem gekoppelt werden.
- **Ein gespeichertes comma** wird an seiner Identität erkannt, nicht nur an seiner Adresse. Taucht es unter einer neuen Adresse auf, aktualisiert CommaView die gespeicherte.

## Sicherheit

Prüfen Sie Netzwerke und koppeln Sie im Stand. Tippen Sie während der Fahrt nicht in CommaView herum.
