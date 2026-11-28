---
title: "Im Auto ohne WLAN zu Hause verbinden"
description: "Bringen Sie Handy und comma im Auto in ein Netzwerk: den Hotspot Ihres Handys, des comma oder eines Bildschirms im Auto, und was zu tun ist, wenn CommaView das comma nicht erreicht."
topic: start
order: 3
kind: walkthrough
lede: "Live View geht direkt vom comma zu Ihrem Handy, über ein lokales Netzwerk, nicht über das Internet. Wessen Netzwerk das ist, spielt für CommaView keine Rolle: Ihr Handy und das comma müssen nur im selben sein. Im Auto ist das meist ein Hotspot."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView eingerichtet"
    text: "Ihr comma ist mit diesem Handy gekoppelt. Noch nicht? [CommaView einrichten](/de/guides/setup)."
  - title: "Kein VPN"
    text: "Schalten Sie jedes VPN auf dem Handy oder dem Bildschirm im Auto aus, während Sie CommaView nutzen."
howItWorks:
  - title: "Ihr comma"
    text: "Stellt Live View und Aufnahmen in dem Netzwerk bereit, in dem es ist."
    edge: "ein Hotspot"
  - title: "Ihr Handy"
    text: "Findet das comma in diesem Netzwerk von selbst, auch wenn sich seine Adresse ändert."
steps:
  - id: network
    title: "Handy und comma in ein Netzwerk bringen"
    body: |
      Wählen Sie, was zu Ihrem Auto passt: Am einfachsten ist meist das Netz, das mit dem Auto von selbst startet. Das comma verbinden Sie auf seinem eigenen Bildschirm unter **Einstellungen › Netzwerk** mit einem Netz.
    tabs:
      - label: "Hotspot Ihres Handys"
        body: "Schalten Sie den Hotspot Ihres Handys ein und verbinden Sie das comma damit. CommaView auf demselben Handy erreicht das comma darüber, und das comma bekommt darüber auch Internet."
      - label: "Hotspot des comma"
        body: "Schalten Sie den Hotspot des comma ein (openpilot nennt ihn Tethering: beim comma four **Einstellungen › Netzwerk › Tethering aktivieren**, beim comma 3X **Einstellungen › Netzwerk › Erweitert › Tethering aktivieren**) und verbinden Sie Ihr Handy in seinen WLAN-Einstellungen damit. Der Hotspot des comma bietet kein Internet."
      - label: "Hotspot eines Bildschirms im Auto"
        body: "Kann eine AI-Box oder ein Infotainment einen Hotspot teilen (viele mit SIM-Karte können das), schalten Sie ihn ein und verbinden Sie das comma damit, und Ihr Handy, falls Sie eines nutzen. Mehr unter [Bildschirme im Auto](/de/guides/car-screens)."
    note: "Manche Hotspots halten die Geräte darin voneinander getrennt. Findet CommaView das comma in einem nicht, versuchen Sie ein anderes."
  - id: home
    title: "CommaView öffnen"
    body: |
      Die Startseite zeigt Ihr comma als **Verbunden**, sobald es im neuen Netzwerk antwortet: CommaView findet es von selbst, auch unter einer neuen Adresse. Das comma schläft, wenn das Auto aus ist, also starten Sie zuerst das Auto.

      Zeigt die Startseite das comma offline mit **Keine Verbindung?**, prüfen Sie, ob das Handy im selben WLAN wie das comma ist oder in seinem Hotspot, und tippen Sie dann auf **Neu verbinden**.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Neu verbinden** versucht es erneut mit dem comma."
      - target: cant-connect
        text: "**Keine Verbindung?** sagt, was das Handy braucht: dasselbe WLAN wie das comma oder seinen Hotspot."
  - id: address
    title: "Wird es immer noch nicht gefunden, die Adresse eingeben"
    body: |
      Öffnen Sie die **Einstellungen des Geräts** des comma, dann **Name und Adresse**, und bearbeiten Sie seine IP-Adresse. Im eigenen Hotspot des comma ist sie **192.168.43.1** (bei jedem comma dieselbe). In jedem anderen Netz ist es die Adresse, die das comma unter **Einstellungen › Netzwerk** zeigt: beim comma four unter dem Netzwerknamen auf der WLAN-Schaltfläche, beim comma 3X unter **Erweitert**. Tippen Sie auf **Speichern**.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "Die IP-Adresse des comma in diesem Netz."
      - target: save
        text: "**Speichern**."
  - id: live-view
    title: "Live View öffnen"
    body: |
      Tippen Sie auf der Startseite auf **Live View öffnen**. Verliert das Handy das comma, sagt Live View warum und verbindet sich von selbst neu, wenn das comma antwortet. **Dieses comma ist nicht erreichbar** heißt, dass das Handy nicht im Netz des comma ist: Beheben Sie das und tippen Sie dann auf **Erneut versuchen**.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**Dieses comma ist nicht erreichbar**: warum Live View angehalten hat."
      - target: retry
        text: "**Erneut versuchen**, sobald das Handy wieder im Netz des comma ist."
check: "Die Startseite zeigt Ihr comma als **Verbunden**, und Live View zeigt die Straße mit dem Fahrpfad darüber."
fixes:
  - q: "„Dieses comma ist nicht erreichbar“"
    a: "Das Handy muss im selben WLAN wie das comma sein oder in seinem Hotspot. Prüfen Sie, mit welchem Netz das Handy verbunden ist (es ist vielleicht in ein bekanntes WLAN zurückgekehrt), schalten Sie jedes VPN aus und tippen Sie auf **Erneut versuchen**."
  - q: "„Live View ist auf einem anderen Gerät offen“"
    a: "Dieses comma streamt immer nur an ein Handy oder Infotainment. Gehen Sie in CommaView auf dem anderen Gerät zurück zur Startseite, dann startet Live View hier von selbst."
  - q: "„CommaView antwortet nicht“"
    a: "Es startet vielleicht gerade auf dem comma neu. Live View verbindet sich neu, sobald es zurück ist."
  - q: "CommaView sagt, es braucht Internet zum Erneuern"
    a: "Während der Beta erneuert CommaView ab und zu seinen Zugangspass, und der Hotspot des comma zählt nicht als Internet. Geben Sie dem Handy kurz mobile Daten oder ein WLAN mit Internet."
  - q: "In einem Hotspot ging es, in einem anderen nicht"
    a: "Manche Hotspots halten die Geräte darin voneinander getrennt, sodass das Handy das comma nicht sieht. Versuchen Sie ein anderes der Netze aus Schritt 1."
related: [comma-not-found, car-screens, browser-view, setup-troubleshooting]
---

## Suche, Kopplung und Adresse

Drei verschiedene Dinge müssen funktionieren, und wenn Sie wissen, welches davon scheitert, wissen Sie, was zu beheben ist:

- **Das comma finden.** CommaView sucht Ihr comma in dem Netz, in dem das Handy ist, und aktualisiert die gespeicherte Adresse, wenn es dasselbe comma woanders findet. Manche Netze blockieren diese Suche; die Adresse einzugeben (Schritt 3) umgeht das.
- **Es erreichen.** Das Handy muss das comma in diesem Netz erreichen. Ein Laptop, der sich per SSH mit dem comma verbindet, beweist nicht, dass das Handy es kann.
- **Kopplung.** Ist das comma erreicht, nutzt das Handy den Schlüssel, den es beim Koppeln bekommen hat. Ein Netzwechsel hebt die Kopplung nicht auf: Sie koppeln nicht erneut.
