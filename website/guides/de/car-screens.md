---
title: "CommaView auf einem Tablet oder Bildschirm im Auto nutzen"
description: "Live View von CommaView auf einem größeren Bildschirm: Android-Infotainment, Android-AI-Box am Bildschirm des Autos oder Tablet in einer Halterung. Installation, Netzwerk, Kopplung und Layout."
topic: screens
order: 3
kind: walkthrough
lede: "Die Bildschirme von comma 3X und comma four sind klein. CommaView zeigt Live View Ihres comma auf einem größeren: einem Android-Infotainment, einer Android-AI-Box am Bildschirm des Autos oder einem Handy oder Tablet in einer Halterung. Der Bildschirm im Auto führt seine eigene Kopie von CommaView aus, gekoppelt mit Ihrem comma."
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 oder neuer"
    text: "Ein Infotainment, eine AI-Box, ein Handy oder Tablet mit Android 8 oder neuer, auf dem Sie eine App installieren können."
  - title: "Ihre Einladung"
    text: "Die E-Mail-Adresse, an die Ihre CommaView-Einladung ging, zum Anmelden auf my.commaview.com und in der App."
  - title: "CommaView auf Ihrem Handy"
    text: "Am einfachsten: Richten Sie Ihr comma zuerst von Ihrem Handy aus ein und koppeln Sie dann den Bildschirm im Auto. [CommaView einrichten](/de/guides/setup)."
howItWorks:
  - title: "Ihr comma"
    text: "Sendet Live View über ein lokales Netzwerk, nicht über das Internet."
    edge: "Hotspot oder WLAN"
  - title: "Der Bildschirm im Auto"
    text: "Führt sein eigenes CommaView aus, gekoppelt mit Ihrem comma."
steps:
  - id: install
    title: "CommaView auf dem Bildschirm im Auto installieren"
    body: |
      Öffnen Sie auf dem Infotainment, der AI-Box, dem Handy oder Tablet den Webbrowser und melden Sie sich unter [my.commaview.com](https://my.commaview.com) mit der E-Mail-Adresse an, an die Ihre Einladung ging. Tippen Sie unter **Get the app** auf **Download CommaView**, öffnen Sie den Download und erlauben Sie für diese eine Installation Installationen aus dem Browser; schalten Sie das danach wieder aus, wie in der [Einrichtungsanleitung](/de/guides/setup).

      Öffnen Sie CommaView und melden Sie sich an. Während der Beta braucht es ab und zu Internet, um seinen Zugangspass zu erneuern. Geben Sie ihm also zumindest hin und wieder ein WLAN mit Internet.
    note: "Manche Infotainments und Boxen blockieren Installationen aus dem Browser. Laden Sie die App auf einem Computer herunter, kopieren Sie sie per USB-Stick hinüber und öffnen Sie sie im Dateimanager des Geräts."
  - id: network
    title: "Ins selbe Netzwerk wie das comma bringen"
    body: |
      Live View geht über ein lokales Netzwerk direkt vom comma zum Bildschirm im Auto. Beide müssen nur im selben sein, und im Auto ist das meist ein Hotspot. Wählen Sie das Netz, das mit dem Auto von selbst startet: Das ist meist am einfachsten.
    tabs:
      - label: "Hotspot des Bildschirms im Auto"
        body: "Kann die AI-Box oder das Infotainment einen Hotspot teilen (viele mit SIM-Karte können das), schalten Sie ihn ein und verbinden Sie das comma unter **Einstellungen › Netzwerk** auf dem comma damit."
      - label: "Hotspot Ihres Handys"
        body: "Verbinden Sie das comma und den Bildschirm im Auto mit dem Hotspot Ihres Handys. Darüber bekommen sie auch Internet."
      - label: "Hotspot des comma"
        body: "Schalten Sie den Hotspot des comma ein (openpilot nennt ihn Tethering: beim comma four **Einstellungen › Netzwerk › Tethering aktivieren**, beim comma 3X **Einstellungen › Netzwerk › Erweitert › Tethering aktivieren**) und verbinden Sie den Bildschirm im Auto damit."
      - label: "WLAN zu Hause"
        body: "Zu Hause beide in Ihrem WLAN. Praktisch für die Einrichtung, aber es endet, sobald Sie losfahren."
    note: "Schalten Sie jedes VPN auf dem Bildschirm im Auto aus. Manche Hotspots halten die Geräte darin voneinander getrennt: Findet der Bildschirm im Auto das comma in einem nicht, versuchen Sie ein anderes. Mehr unter [Im Auto verbinden](/de/guides/connect-in-the-car)."
  - id: pair
    title: "Mit Ihrem comma koppeln"
    body: |
      Läuft CommaView auf Ihrem comma schon über Ihr Handy, koppeln Sie den Bildschirm im Auto, statt es neu einzurichten. Er bekommt einen eigenen Schlüssel.
    tabs:
      - label: "Auf Ihrem Handy"
        body: |
          Öffnen Sie die **Einstellungen des Geräts** des comma, dann **Weiteres Handy koppeln**. Tippen Sie unter **Weiteres Handy hinzufügen** auf **Einladung zeigen**: ein Code zum Eingeben oder ein QR-Code, 10 Minuten gültig und nur einmal nutzbar.
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**Einladung zeigen**."
          - target: this-phone
            text: "Die Handys mit Schlüssel, dieses markiert als **Dieses Handy**. Der Bildschirm im Auto kommt hinzu."
      - label: "Auf dem Bildschirm im Auto"
        body: |
          Tippen Sie unter **comma verbinden** auf **comma mit CommaView koppeln** (ist schon ein comma hinzugefügt, öffnen Sie stattdessen **comma hinzufügen**). Wählen Sie Ihr comma und tippen Sie auf **Kopplungscode eingeben** oder **QR-Code scannen**. Steht es nicht in der Liste, tippen Sie auf **Adresse und Code eingeben**. Geben Sie die Einladung unter **Kopplungscode oder Einladung** ein und tippen Sie auf **comma koppeln**.
        screen: add-comma
        pins:
          - target: found-comma
            text: "Ihr comma, in diesem Netz gefunden."
          - target: scan-qr
            text: "**QR-Code scannen**."
          - target: enter-address
            text: "**Adresse und Code eingeben**, wenn es nicht in der Liste steht."
    note: "Ihr Handy meldet dann **Ein neues Handy hat einen Schlüssel**. Tippen Sie auf **Es ist meins**. Alle Schritte: [Ein weiteres Handy oder Tablet hinzufügen](/de/guides/another-phone)."
  - id: fit
    title: "An Ihren Bildschirm anpassen"
    body: |
      Auf einem breiten Bildschirm ordnet sich CommaView als Dashboard an, mit der Navigation in einer Leiste an der Seite. Lassen Sie die Textgröße des Geräts so, dass Sie sie auf einen Blick lesen können: CommaView ordnet sich nach dem Platz an, den es bei dieser Größe hat.

      Die Bedienelemente von Live View liegen auf der Fahrerseite. Bei **Auto** folgt CommaView der Seite, die Ihr comma meldet; um sie selbst festzulegen, wählen Sie **Einstellungen › Anzeige › Fahrerseite**: **Auto**, **Linkslenker** oder **Rechtslenker**. Das spiegelt die Bedienelemente auf jeder Ansicht.
    tabs:
      - label: "Tablet"
        body: "Die Startseite zeigt das Auto, Ihre Woche, die Karte und Ihre Fahrten nebeneinander, mit der Leiste an der Seite."
        screen: tablet-home
        pins:
          - target: home-tab
            text: "Die Leiste: **Start**, **Aufnahmen**, **Einstellungen**."
          - target: open-live-view
            text: "**Live View öffnen**."
      - label: "Infotainment"
        body: "Dasselbe Dashboard, passend für einen Bildschirm im Armaturenbrett."
        screen: car-home
        pins:
          - target: home-tab
            text: "Die Leiste: **Start**, **Aufnahmen**, **Einstellungen**."
          - target: open-live-view
            text: "**Live View öffnen**."
      - label: "Über eine AI-Box"
        body: |
          Manche Autos schneiden die Ränder des Bildes ab, das eine AI-Box sendet, und Android merkt das nicht. Öffnen Sie **Einstellungen › Anzeige › Ränder des Bildschirms** und schieben Sie jeden Rand nach innen, bis Sie die Linie rundum sehen. Prüfen Sie dann, ob Startseite, Live View und Einstellungen hineinpassen. **Design** kann dort dem Bildschirm im Auto folgen: **Wie dieses Gerät**.
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−** und **+** schieben jeden Rand nach innen; **Fertig** übernimmt es."
  - id: live-view
    title: "Live View öffnen und prüfen, ob es läuft"
    body: |
      Tippen Sie bei eingeschaltetem Auto auf **Live View öffnen**. Seine Bedienelemente liegen in einer Leiste neben der Straße, auf der Fahrerseite, kompakt auf einem niedrigen Bildschirm.
    tabs:
      - label: "Tablet"
        body: "**Details** öffnet sich in einem Bereich neben dem Video."
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "Details, neben dem Video."
          - target: record-button
            text: "**Aufnehmen**."
          - target: go-live-button
            text: "**Live gehen**."
      - label: "Infotainment"
        body: "Die Leiste enthält Aufnehmen, den Umschalter der Fahransicht, Fahrercam, Details und Verlassen."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Aufnehmen**."
          - target: onroad-screen-button
            text: "Der Umschalter der Fahransicht."
          - target: driver-cam-button
            text: "**Fahrercam**."
          - target: details
            text: "**Details**, unter Fahrercam."
          - target: exit
            text: "**Verlassen**."
  - id: auto
    title: "Von selbst öffnen lassen"
    body: |
      Unter **Einstellungen › Anzeige**, bei **Live View wird geöffnet**:

      - **Live View bei Verbindung öffnen** öffnet Live View von selbst, wenn sich Ihr comma bei eingeschaltetem Auto verbindet.
      - **CommaView beim Start dieses Geräts öffnen**, für ein Infotainment, das mit dem Auto neu startet. Eines, das stattdessen schläft, hat vielleicht eine eigene Liste von Apps, die es startet.
      - **CommaView öffnen, wenn sich Bluetooth verbindet**: wenn sich das gewählte Gerät verbindet, Ihr Auto oder, auf einem Infotainment, Ihr Handy.

      Ist **Über anderen Apps einblenden** erlaubt, öffnet sich CommaView von selbst. Sonst bietet eine Benachrichtigung an, es zu öffnen.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Live View bei Verbindung öffnen**."
check: "Bei eingeschaltetem Auto öffnet der Bildschirm im Auto Live View, die Stream-Anzeige meldet **Live**, und jedes Bedienelement liegt innerhalb der Bildschirmränder."
fixes:
  - q: "Kann ich CommaView über CarPlay oder Android Auto nutzen?"
    a: "Nicht vom Handy aus. CommaView ist keine CarPlay- oder Android-Auto-App, und diese Plattformen lassen Handy-Apps kein Video zeigen, während das Auto fährt. Eine Android-AI-Box umgeht das, weil sie ein eigenes Android-Gerät ist: CommaView läuft auf der Box, und das Auto zeigt den Bildschirm der Box. Siehe [CommaView auf einer Android-AI-Box ausführen](/de/guides/ai-box)."
  - q: "Funktioniert es mit dem eingebauten Android Automotive meines Autos (Google integriert)?"
    a: "Noch nicht. Autos mit Google integriert installieren Apps nur aus ihrem eigenen Play Store, und dort ist CommaView nicht. Probieren Sie es auf anderem Weg, erzählen Sie uns, wie es lief."
  - q: "Kann ich einen Bildschirm im Auto und mein Handy mit demselben comma nutzen?"
    a: "Ja: Koppeln Sie jedes Gerät mit dem comma. Immer nur eines hat Live View, verlassen Sie Live View also zuerst auf dem anderen. Live View meldet **Live View ist auf einem anderen Gerät offen** und startet von selbst, sobald Sie auf dem anderen Gerät zur Startseite zurückgehen."
  - q: "Mein Auto schneidet die Ränder des Bildes ab"
    a: "Manche Autos beschneiden das Bild, das eine AI-Box sendet, und Android merkt das nicht. **Einstellungen › Anzeige › Ränder des Bildschirms** hält die App von jedem eingestellten Rand fern."
  - q: "Der Bildschirm im Auto findet das comma nicht"
    a: "CommaView findet das comma im selben Netz von selbst, auch wenn sich seine Adresse ändert. Wenn nicht, geben Sie die IP-Adresse des comma ein: 192.168.43.1 im eigenen Hotspot des comma (bei jedem comma dieselbe), in jedem anderen Netz die IP-Adresse, die das comma unter **Einstellungen › Netzwerk** zeigt: beim comma four unter dem Netzwerknamen auf der WLAN-Schaltfläche, beim comma 3X unter **Erweitert**."
  - q: "Nach einem Runtime-Update bekommt der Bildschirm im Auto kein Video mehr"
    a: "Wenn Sie die Runtime Ihres comma aktualisieren, aktualisieren Sie zuerst CommaView auf jedem Gerät, das es ansieht, auch auf dem Bildschirm im Auto. Ein Bildschirm im Auto mit einer älteren CommaView-Version funktioniert noch 90 Tage, nachdem das erste Handy des comma seinen Schlüssel bekommen hat; danach braucht er CommaView 0.0.166 oder neuer und eine Einladung."
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## Was während der Fahrt funktioniert

CommaView ist eine Android-App und braucht deshalb ein Android-Gerät vor Ihnen. Jedes davon kann es während der Fahrt ausführen:

- **Ein Android-Infotainment.** Ein nachgerüstetes Infotainment mit Android 8 oder neuer: CommaView wird darauf wie auf einem Handy installiert und läuft während der Fahrt auf dem Bildschirm des Autos.
- **Eine Android-„AI-Box“.** Ein kleiner Android-Computer, der in den kabelgebundenen CarPlay- oder Android-Auto-Anschluss des Autos gesteckt wird und dort seinen eigenen Android-Bildschirm zeichnet. CommaView läuft auf der Box, nicht auf Ihrem Handy. Siehe [CommaView auf einer Android-AI-Box ausführen](/de/guides/ai-box).
- **Ein Handy oder Tablet in einer Halterung.** Jedes Android-Handy oder -Tablet, in einer Armaturenbrett- oder Lüftungshalterung, die Ihnen nicht die Sicht nimmt. Der einfachste Weg, und der, den die meisten nutzen.

Ein Auto mit Webbrowser, etwa ein Tesla, kann Live View stattdessen darin zeigen: siehe [Live View im Browser Ihres Autos zeigen](/de/guides/browser-view).

## Was nicht funktioniert, und warum

- **CarPlay und Android Auto vom Handy.** CommaView ist keine CarPlay- oder Android-Auto-App. Diese Plattformen lassen Handy-Apps kein Video zeigen, während das Auto fährt.
- **Video im Stand in CarPlay und Android Auto.** Apple und Google bringen Video für manche Autos, aber nur im Stand, deshalb kann es Live View auf der Straße nicht zeigen.
- **Das Handy aufs Auto spiegeln.** Adapter, die den Bildschirm eines Handys über CarPlay oder Android Auto spiegeln, werden nicht unterstützt. Nutzen Sie stattdessen eine Android-AI-Box oder ein Infotainment, das CommaView selbst ausführt.
- **Google integriert (Android Automotive).** Diese Autos installieren Apps nur aus ihrem eigenen Play Store, und dort ist CommaView nicht.

## Getestete Hardware

Bildschirme im Auto, mit denen das CommaView-Team gefahren ist. CommaView sollte auf jedem Gerät mit Android 8 oder neuer laufen, aber diese haben wir geprüft:

| Gerät | Art | Was wir geprüft haben |
| --- | --- | --- |
| **Doro-Infotainment** (Qualcomm QCM6125, Android 13, 1280 × 720) | Infotainment | Live View auf Stadtfahrten (Oktober 2026). |
| **Dasaita-Infotainment, 10,2″** (1280 × 720, in einem Toyota RAV4) | Infotainment | Live View während der Fahrt; Hochladen von Aufnahmen im Stand. |

**Helfen Sie beim Testen.** Jeder Bildschirm im Auto ist anders. Nutzen Sie CommaView auf einem Infotainment oder einer Box, [erzählen Sie uns, wie es lief](#erzählen-sie-uns-von-ihrem-bildschirm-im-auto), und wir nehmen es hier auf, sobald wir es geprüft haben.

## Erzählen Sie uns von Ihrem Bildschirm im Auto

Senden Sie es uns vom Bildschirm im Auto selbst, damit der Bericht sein Modell und seine Bildschirmgröße enthält:

1. Öffnen Sie in CommaView auf dem Infotainment oder der Box **Einstellungen › Support & Diagnose** und tippen Sie auf **Problem melden oder Idee senden**.
2. Wählen Sie **Idee** und schalten Sie dann **Dieses Gerät: Diagnose** ein (bei einer Idee ist es aus): Daraus erfahren wir Marke, Modell und Bildschirmgröße.
3. Nennen Sie in der Notiz Ihr Auto, das Infotainment oder die Box (Marke und Modell), wie es verbunden ist (wessen Hotspot oder WLAN) und was funktioniert hat und was nicht. Tippen Sie dann auf **Senden**.

Was Sie gesendet haben und unsere Antworten finden Sie unter „Your feedback“ auf [my.commaview.com](https://my.commaview.com/feedback). Noch nicht in der Beta, oder die App startet nicht? Erzählen Sie es uns im [CommaView-Discord](https://discord.gg/UuMhz9K8ft).

## Sicherheit

- Installieren, koppeln und richten Sie das Layout im Stand ein. Prüfen Sie, ob Live View läuft, bevor Sie losfahren.
- Bedienen Sie CommaView nicht während der Fahrt. Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt.
- Die Warnungen Ihres comma und die Instrumente Ihres Autos haben Vorrang. CommaView zeigt nur, was das comma sieht.
- Befestigen Sie ein Handy oder Tablet so, dass es weder die Sicht noch einen Airbag behindert, und beachten Sie die örtlichen Regeln zu Bildschirmen im Auto.
