---
title: "CommaView auf einer Android-AI-Box ausführen"
description: "Bringen Sie Live View mit einer Android-AI-Box auf den CarPlay- oder Android-Auto-Bildschirm Ihres Autos: einstecken, CommaView installieren, ins Netz des comma bringen, koppeln und anpassen."
topic: screens
order: 4
kind: walkthrough
lede: "Hat Ihr Auto ab Werk **kabelgebundenes** CarPlay oder Android Auto, kann eine **Android-AI-Box** Live View von CommaView auf den Bildschirm des Autos bringen, ohne neues Radio und ohne Verkabelung. Die Box ist ein kleiner Android-Computer, den Sie in den USB-Anschluss stecken, an den Sie sonst Ihr Handy anschließen. CommaView läuft auf der Box, Ihr Handy bleibt also frei für Anrufe und Karten."
parked: true
updated: 2026-11-27
needs:
  - title: "Kabelgebundenes CarPlay oder Android Auto"
    text: "Kabelgebundenes CarPlay oder Android Auto ab Werk, über einen USB-Anschluss, der Daten überträgt. Prüfen Sie, ob die Box das unterstützt, was Ihr Auto hat."
  - title: "Eine Box mit echtem Android"
    text: "Android 8 oder neuer, mit dem Sie eine App aus einer Datei installieren können. Geschlossene „Video“-Boxen und einfache Funkadapter können CommaView nicht ausführen. [Welche Box Sie kaufen sollten](/blog/android-ai-box-commaview)."
  - title: "CommaView auf Ihrem Handy"
    text: "Richten Sie Ihr comma zuerst von Ihrem Handy aus ein und koppeln Sie dann die Box. [CommaView einrichten](/de/guides/setup)."
howItWorks:
  - title: "Ihr comma"
    text: "Sendet Live View über ein lokales Netzwerk an die Box."
    edge: "WLAN"
  - title: "AI-Box"
    text: "Führt CommaView aus, wie jedes Android-Gerät."
    edge: "USB"
  - title: "Bildschirm des Autos"
    text: "Zeigt den Bildschirm der Box, so wie er CarPlay zeigt."
steps:
  - id: plug-in
    title: "Die Box einstecken und CommaView installieren"
    body: |
      Stecken Sie die Box in den CarPlay- oder Android-Auto-USB-Anschluss des Autos und lassen Sie sie starten. Verbinden Sie sie fürs Erste mit einem WLAN mit Internet.

      Melden Sie sich im Browser der Box unter [my.commaview.com](https://my.commaview.com) mit der E-Mail-Adresse an, an die Ihre Einladung ging, und tippen Sie unter **Get the app** auf **Download CommaView**. Erlauben Sie Installationen aus dem Browser für diese eine Installation und schalten Sie das danach wieder aus. Öffnen Sie CommaView und melden Sie sich an.
    note: "Führen Sie CommaView im Android-Modus der Box aus, nicht mit durchgereichtem CarPlay Ihres Handys."
  - id: network
    title: "Box und comma ins selbe Netzwerk bringen"
    body: |
      Live View geht über ein lokales Netzwerk direkt vom comma zur Box, nicht über das Internet, und jedes Netz, in dem beide sind, reicht.
    tabs:
      - label: "Hotspot der Box"
        body: "Boxen mit SIM-Karte können meist einen Hotspot teilen. Schalten Sie ihn ein und verbinden Sie das comma unter **Einstellungen › Netzwerk** auf dem comma damit."
      - label: "Hotspot Ihres Handys"
        body: "Verbinden Sie Box und comma mit dem Hotspot Ihres Handys. Darüber bekommen sie auch Internet."
      - label: "Hotspot des comma"
        body: "Schalten Sie den Hotspot des comma ein (openpilot nennt ihn Tethering) und verbinden Sie die Box damit."
    note: "Die meisten Boxen nutzen das WLAN auch, um Ihr Handy für kabelloses CarPlay zu verbinden, und manche verlieren dabei ihr WLAN-Internet. Schalten Sie jedes VPN auf der Box aus."
  - id: pair
    title: "Die Box mit Ihrem comma koppeln"
    body: |
      Öffnen Sie auf Ihrem Handy die **Einstellungen des Geräts** des comma, tippen Sie auf **Weiteres Handy koppeln** und unter **Weiteres Handy hinzufügen** auf **Einladung zeigen**. Tippen Sie auf der Box auf **comma mit CommaView koppeln**, wählen Sie Ihr comma und geben Sie den Code ein oder tippen Sie auf **QR-Code scannen**. Alle Schritte: [CommaView auf einem Tablet oder Bildschirm im Auto nutzen](/de/guides/car-screens#step-pair).
  - id: edges
    title: "Die App von Rändern fernhalten, die das Auto abschneidet"
    body: |
      Manche Autos beschneiden die Ränder dessen, was die Box sendet, und Android merkt das nicht. Öffnen Sie **Einstellungen › Anzeige › Ränder des Bildschirms**. Eine Linie markiert, wo die App endet: Schieben Sie jeden Rand mit **−** und **+** nach innen, bis Sie die Linie rundum sehen, und tippen Sie dann auf **Fertig**. **Zurücksetzen** schaltet es aus.

      Prüfen Sie dann, ob Startseite, Live View und Einstellungen hineinpassen.
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−** und **+** schieben jeden Rand nach innen; **Fertig** übernimmt es."
      - text: "**Design**, ebenfalls unter **Einstellungen › Anzeige**: **Wie dieses Gerät** folgt der Box."
  - id: auto
    title: "Von selbst öffnen lassen"
    body: |
      Unter **Einstellungen › Anzeige**, bei **Live View wird geöffnet**:

      - **CommaView beim Start dieses Geräts öffnen**, für eine Box, die mit dem Auto neu startet.
      - **CommaView öffnen, wenn sich Bluetooth verbindet**, mit Ihrem Handy als Gerät, für eine Box, die stattdessen schläft.
      - **Live View bei Verbindung öffnen**, um direkt in Live View zu gehen, sobald sich Ihr comma bei eingeschaltetem Auto verbindet.

      Erlauben Sie **Über anderen Apps einblenden**, damit sich CommaView von selbst öffnen kann. Ohne das bietet eine Benachrichtigung an, es zu öffnen.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Live View bei Verbindung öffnen**."
  - id: check
    title: "Prüfen, ob Live View läuft, dann losfahren"
    body: |
      Öffnen Sie bei eingeschaltetem Auto Live View auf der Box. Seine Bedienelemente liegen in einer Leiste auf der Fahrerseite, kompakt auf einem niedrigen Bildschirm. Prüfen Sie vor der Fahrt, ob das Bild läuft und nichts abgeschnitten ist.
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "**Aufnehmen**, oben in der Leiste."
      - target: details
        text: "**Details**, weiter unten in der Leiste."
    note: "Der Bildschirm der Box erreicht das Auto als Video, Live View wird unterwegs also noch einmal kodiert. Rechnen Sie mit einem etwas weicheren und etwas späteren Bild als auf einem Handy in der Hand."
check: "Der Bildschirm des Autos zeigt die Startseite von CommaView, dann Live View mit der Stream-Anzeige **Live**, und die Linie von **Ränder des Bildschirms** ist rundum zu sehen."
fixes:
  - q: "Die Box kann CommaView nicht installieren"
    a: "Manche Boxen blockieren Installationen aus dem Browser. Laden Sie die App auf einem Computer herunter, kopieren Sie sie per USB-Stick hinüber und öffnen Sie sie im Dateimanager der Box. Eine Box mit geschlossenem System und fester App-Liste kann sie gar nicht installieren."
  - q: "Die Box findet das comma nicht"
    a: "Prüfen Sie, ob beide im selben Netz sind und ob die Box ihr WLAN nicht für kabelloses CarPlay aufgegeben hat. Geben Sie bei Bedarf die IP-Adresse des comma ein: 192.168.43.1 im eigenen Hotspot des comma. Mehr unter [Im Auto verbinden](/de/guides/connect-in-the-car)."
  - q: "Das Bild ruckelt oder läuft nicht"
    a: "Das comma sendet seine Straßenkamera als 1928 × 1208 HEVC (H.265), und die Decoder der billigsten Boxen schaffen das manchmal nicht. Scheitert ein Decoder, probiert CommaView von selbst die anderen der Box. Kann keiner es abspielen, meldet Live View **Video dieses comma nicht abspielbar**: Senden Sie einen Support-Bericht von der Box."
  - q: "„Live View ist auf einem anderen Gerät offen“"
    a: "Ihr comma streamt immer nur an ein Handy oder Infotainment. Gehen Sie in CommaView auf Ihrem Handy zurück zur Startseite, dann startet Live View auf der Box von selbst."
  - q: "Kann ich CarPlay von meinem Handy weiter nutzen?"
    a: "Ja. Die meisten Boxen reichen CarPlay oder Android Auto Ihres Handys kabellos durch, und Sie wechseln zwischen diesem und dem Android der Box. CommaView läuft im Android-Modus der Box."
  - q: "Braucht die Box eine SIM-Karte?"
    a: "Nicht für Live View. Während der Beta braucht CommaView ab und zu Internet, um seinen Zugangspass zu erneuern; das liefert das WLAN zu Hause, der Hotspot Ihres Handys oder eine SIM-Karte in der Box."
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## Vier Arten von „CarPlay-Adapter“

Im Handel heißen vier ganz verschiedene Dinge gleich. Nur eines führt CommaView aus.

| Art | Was es tut | Führt CommaView aus? |
| --- | --- | --- |
| **Android-AI-Box** | Volles Android auf dem Bildschirm des Autos, Apps wie auf einem Handy installiert | **Ja** |
| **Geschlossene „Video“-Box** | Ein paar eingebaute Streaming-Apps auf einem abgeschotteten System | Nein |
| **Funkadapter** | Macht kabelgebundenes CarPlay oder Android Auto kabellos. Kein eigenes Android | Nein |
| **Tragbarer CarPlay-Bildschirm** | Ein eigener Bildschirm für das CarPlay Ihres Handys, innen oft kein Android | Nein |

[Die besten Android-AI-Boxen für CommaView](/blog/android-ai-box-commaview) vergleicht die Boxen, die sich lohnen. Ein Tesla hat weder CarPlay noch Android Auto: Nutzen Sie stattdessen [Browser View](/de/guides/browser-view).

Wenn Sie die Runtime Ihres comma aktualisieren, aktualisieren Sie zuerst CommaView auf der Box, wie auf jedem Gerät, das Ihr comma ansieht.

## Sicherheit

Richten Sie die Box im Stand ein und lassen Sie sie dann in Ruhe. Bedienen Sie CommaView nicht während der Fahrt: Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt. Die Warnungen Ihres comma und die Instrumente Ihres Autos haben Vorrang. CommaView zeigt nur, was das comma sieht.
