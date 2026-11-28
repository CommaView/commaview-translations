---
title: "Live View im Browser Ihres Autos zeigen"
description: "Browser View zeigt Live View von CommaView im eigenen Webbrowser Ihres Autos, auch bei Tesla, bereitgestellt von Ihrem Handy über seinen Hotspot. Im Auto muss nichts installiert werden."
topic: screens
order: 2
kind: walkthrough
lede: "**Browser View** zeigt, was Live View zeigt, im eigenen Webbrowser Ihres Autos. Ihr Handy liefert es über seinen Hotspot oder sein WLAN ans Auto, deshalb muss im Auto nichts installiert werden. Es wurde für Autos wie Tesla gemacht, die einen Browser, aber kein CarPlay oder Android Auto haben, und es funktioniert in jedem Browser, der Ihr Handy erreicht."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funktioniert"
    text: "CommaView auf einem Android-Handy, gekoppelt mit Ihrem comma. Noch nicht? [CommaView einrichten](/de/guides/setup)."
  - title: "Ein Browser im Auto"
    text: "Ein Tesla, ein anderes Auto mit Webbrowser oder ein Tablet oder Laptop im Auto."
  - title: "Ein Netzwerk"
    text: "Das Auto und Ihr comma im Hotspot Ihres Handys oder in einem anderen Netz, das alle drei teilen."
howItWorks:
  - title: "Ihr comma"
    text: "Sendet Live View wie gewohnt an Ihr Handy."
  - title: "Ihr Handy"
    text: "Liefert das Bild als Webseite, geschützt durch einen achtstelligen Code."
    edge: "Hotspot"
  - title: "Der Browser des Autos"
    text: "Öffnet die Seite: 20 Bilder pro Sekunde, 720p oder 1080p, bis zu vier Browser."
steps:
  - id: hotspot
    title: "Das Auto mit dem Hotspot Ihres Handys verbinden"
    body: |
      Schalten Sie den Hotspot Ihres Handys ein und verbinden Sie das Auto in seinen WLAN-Einstellungen damit. Prüfen Sie, ob das Auto mit Ihrem Handy verbunden ist und nicht mit einem WLAN, das es schon kennt. Verbinden Sie auch Ihr comma mit dem Hotspot, falls es noch nicht darin ist: Ihr Handy braucht Ihr comma wie gewohnt.
    note: "**In einem Tesla** schalten Sie zuerst das WLAN Ihres Handys aus, damit der Hotspot mobile Daten teilt."
  - id: start
    title: "Browser View in den Details von Live View starten"
    body: |
      Öffnen Sie auf dem Handy **Live View**, dann **Details**. Weit unten sagt die Karte **Browser View**, was sie tut und was sie CommaView mitteilt. Tippen Sie auf **Starten**.
    screen: live-view-browser-view
    clip: browser-view-start
    pins:
      - target: browser-view-card
        text: "Die Karte **Browser View**, weit unten in **Details**."
      - target: start-button
        text: "**Starten**. Geben Sie dem Handy beim ersten Mal ein paar Sekunden, um sein Zertifikat zu holen."
      - target: privacy-policy
        text: "Was Browser View CommaView mitteilt, während es läuft, und die **Datenschutz-Erklärung**."
  - id: vpn
    title: "Im Tesla die VPN-Adresse einschalten"
    tabs:
      - label: "Tesla"
        body: |
          Der Browser eines Tesla öffnet die Adressen nicht, die ein Hotspot vergibt. Tippen Sie auf der Karte auf **VPN-Adresse an** und erlauben Sie es, wenn Android fragt, ob CommaView ein VPN einrichten darf. Ihr Handy bekommt eine Adresse, die der Tesla öffnet: `169.254.99.1`. Sie leitet keinen Datenverkehr, und jede andere VPN-App ist aus, solange sie an ist.
        screen: live-view-browser-view-vpn
        pins:
          - target: short-link
            text: "Der Kurzlink, auch für den Tesla: **Im Browser des Autos, auch bei Tesla, öffnen**."
          - target: vpn-address
            text: "Die Adressen des Handys über die VPN-Adresse, `169.254.99.1`."
        note: "Die Frage von Android zum VPN ist nicht abgebildet: Sie gehört zu Android und sieht auf jedem Handy anders aus."
      - label: "Anderes Auto"
        body: |
          Hier ist nichts zu tun: Die Browser anderer Autos öffnen die Adresse des Hotspots. Weiter zum nächsten Schritt.
  - id: open
    title: "Den Kurzlink im Browser des Autos eingeben"
    body: |
      Die Karte zeigt einen Kurzlink mit Ihrem achtstelligen Code, etwa `commaview.app/48291374`. Geben Sie ihn im Browser des Autos ein und tippen Sie auf **Öffnen**. Ist das Auto online und CommaView angemeldet, findet die Seite Ihr Handy und öffnet Live View über eine sichere Verbindung: ein Schloss, keine Warnung und das flüssigste Bild.
    screen: live-view-browser-view-on
    pins:
      - target: short-link
        text: "Der Kurzlink zum Eingeben im Auto, mit Ihrem Code."
      - target: show-addresses
        text: "**Kein Internet im Auto? Adressen zeigen**: die eigenen Adressen des Handys."
      - target: quality
        text: "**Bild von Browser View**: 720p oder 1080p."
      - target: stop-button
        text: "**Stoppen** beendet Browser View."
    warn: "**Kein Internet im Auto?** Der Kurzlink braucht es. Nutzen Sie stattdessen die eigene Adresse des Handys: siehe [Kein Internet im Auto](#kein-internet-im-auto)."
  - id: bookmark
    title: "Die Seite als Lesezeichen speichern"
    body: |
      Die Adresse der Seite bleibt gleich. Öffnen Sie also beim nächsten Mal, wenn das Auto online ist, das Lesezeichen, statt den Kurzlink einzugeben.
check: "Die Karte auf dem Handy sagt, wer zusieht und was der Browser des Autos darstellt, etwa **1 Browser schaut zu** und `Tesla 2025.20.6 · H.264 over HTTPS via the VPN name · 20 fps`."
fixes:
  - q: "„Wartet auf den Browser des Autos“, und nichts öffnet sich"
    a: "Prüfen Sie, ob das Auto mit dem Hotspot Ihres Handys verbunden ist und nicht mit einem anderen WLAN. Schalten Sie im Tesla die VPN-Adresse ein ([Schritt 3](#step-vpn))."
  - q: "„Aktivieren Sie den Hotspot von diesem Handy“"
    a: "Das Handy ist weder in einem WLAN noch hat es einen Hotspot, den das Auto teilen könnte. Die Adresse erscheint innerhalb von 5 Sekunden, nachdem eines davon eingeschaltet ist."
  - q: "Der Kurzlink meldet, die VPN-Adresse sei aus"
    a: "Schalten Sie sie auf der Karte ein und laden Sie die Seite neu."
  - q: "Eine Warnung, an der Sie nicht vorbeikommen"
    a: "Nutzen Sie den Kurzlink, während das Auto online ist, oder das einfache Bild ([Kein Internet im Auto](#kein-internet-im-auto))."
  - q: "Das Bild stoppt in D"
    a: "Ob der Browser eines Autos während der Fahrt weiter zeichnet, entscheidet der Autohersteller. Die Berichtszeile der Karte zeigt, was das Auto darstellt („0 fps · Ausgeblendet“ ist ein Bild, das das Auto angehalten hat). Nennen Sie uns Ihr Auto und seine Softwareversion: Schalten Sie vor der Fahrt **Diagnose auf diesem Handy speichern** ein und senden Sie danach in den Einstellungen **Problem melden oder Idee senden**."
related: [car-screens, ai-box, go-live]
blogPost: commaview-0-0-166-languages-browser-view
---

## Kein Internet im Auto

Der Kurzlink braucht ein Auto, das online ist, für seine Seite: über die mobilen Daten des Hotspots oder die eigene Verbindung des Autos. Ohne Internet öffnen Sie direkt die Adresse des Handys. Tippen Sie auf der Karte auf **Kein Internet im Auto? Adressen zeigen**:

- **Bestes Bild**, eine HTTPS-Adresse wie `https://192.168.43.1:8443/48291374`. Der Browser warnt zuerst, weil das Handy diese Adresse selbst signiert: Bestätigen Sie die Warnung, um fortzufahren. Der Browser eines Tesla lässt Sie nicht daran vorbei.
- **Einfaches Bild**, dieselbe Adresse über HTTP, etwa `192.168.43.1:8090/48291374`. In keinem Browser eine Warnung, auch bei Tesla, aber ein Bild mit geringerer Qualität, weniger flüssig.

Ist die VPN-Adresse an, zeigt die Karte stattdessen deren Adressen: `https://169.254.99.1:8443/<code>` und `169.254.99.1:8090/<code>`. Nutzen Sie in einem Tesla ohne Internet die einfache.

Die Hotspot-Adresse Ihres Handys kann vom Beispiel abweichen; die Karte zeigt immer die richtige, mit einer Schaltfläche zum Kopieren daneben.

## Optionen auf der Karte

- **Bild von Browser View: 720p oder 1080p.** 1080p ist schärfer und belastet Handy und Hotspot mehr. 720p, bis Sie etwas wählen.
- **Mit Live View starten.** Browser View startet bei jedem Öffnen von Live View, mit der VPN-Adresse, wenn sie an ist. Stoppen Sie es, bleibt es gestoppt, bis Live View das nächste Mal öffnet.
- **Neuer Code.** Erstellt einen neuen achtstelligen Code, damit eine Adresse, die jemand anderes gesehen hat, nicht mehr funktioniert. Öffnen Sie die neue Adresse im Auto.
- **Bedienung im Auto.** Aufnehmen, Moment speichern und die anderen Bedienelemente von Live View liegen unter dem Bild oder daneben auf der Fahrerseite, nie darüber. **Bedienung im Auto** auf der Karte schaltet sie aus.
- **Die Fahrerkamera** erscheint auch im Auto, solange **Fahrercam** in Live View an ist.

## Während es läuft

- **Browser View läuft weiter, wenn das Handy gesperrt ist** oder in einer anderen App. Seine Benachrichtigung meldet „Live View wird in Browser View gezeigt“, und ihr **Stoppen** beendet es.
- **Wenn Sie Live View verlassen, endet es**, wie auch „Live gehen“ und Live-Kopien.
- **„Live gehen“ neben Browser View** teilt dessen Bild. Startet ein Stream, während Browser View allein läuft, hat er keinen Ton: Stoppen Sie für Ton zuerst Browser View.

## Datenschutz und Sicherheit

- Das Bild geht nur an Browser im Hotspot oder WLAN Ihres Handys, die den Code haben. Nie über mobile Daten und nie über die Server von CommaView.
- Zehn falsche Codes in einer Minute von einem Gerät sperren es für eine Minute aus, und ein Gerät, das schon zusieht, sieht weiter zu.
- Während Browser View läuft, sendet Ihr Handy dem Kontodienst von CommaView seinen Code, seine Ports, ob die VPN-Adresse an ist und die private Adresse des Hotspots oder WLANs, damit der Kurzlink Ihr Handy findet. Wer den Code hat, kann diese Angaben und den `commaview.app`-Namen Ihres Handys sehen, solange Browser View läuft und bis zu 2 Stunden, nachdem es unerwartet gestoppt hat; keine davon öffnet etwas ohne den Hotspot oder das WLAN Ihres Handys. Sie werden 30 Tage nach der letzten Nutzung von Browser View gelöscht. Der `commaview.app`-Name Ihres Handys und das Datum seines letzten Zertifikats bleiben, solange Ihr Konto besteht. Zertifikate sind öffentlich, deshalb bleibt dieser Name in Certificate-Transparency-Logs; er sagt nichts über Sie, Ihr Auto oder Ihr comma. Einzelheiten stehen in [der Datenschutz-Erklärung](/privacy).
- Die VPN-Adresse ist Ihre Wahl, wird nie von selbst eingeschaltet und leitet keinen Datenverkehr.

## Fragen

**Brauche ich eine AI-Box oder ein neues Infotainment?** Nein. Browser View nutzt den Browser, den Ihr Auto schon hat. Hat Ihr Auto stattdessen CarPlay oder Android Auto, kann eine [Android-AI-Box](/blog/android-ai-box-commaview) CommaView direkt auf dem Bildschirm des Autos ausführen.

**Verbraucht es meine mobilen Daten?** Das Bild nicht: Es geht über den Hotspot vom Handy zum Auto. Die Seite des Kurzlinks und die eigene Nutzung des Hotspots durch das Auto schon.

**Kann der Hotspot meines comma das statt dem meines Handys übernehmen?** Bei den meisten Browsern ja: Verbinden Sie Handy und Auto mit dem Hotspot des comma und öffnen Sie die Adresse, die die Karte zeigt. Ein Tesla braucht die VPN-Adresse, und die funktioniert nur für ein Auto im Hotspot des Handys selbst.

## Sicherheit

Richten Sie Browser View im Stand ein und lassen Sie es dann in Ruhe. Bedienen Sie CommaView nicht während der Fahrt: Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt. Die Warnungen Ihres comma und die Instrumente Ihres Autos haben Vorrang. CommaView zeigt nur, was das comma sieht.
