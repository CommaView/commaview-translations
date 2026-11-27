---
title: "Wenn die Einrichtung anhält"
description: "Was die Meldungen der CommaView-Einrichtung bedeuten, in der Reihenfolge der Einrichtung: SSH, die Installation, dann die Kopplung. Finden Sie Ihre Meldung und was zu tun ist."
topic: troubleshooting
order: 1
kind: fixes
lede: "Die Einrichtung geht der Reihe nach vor: Sie meldet sich per SSH auf Ihrem comma an, installiert die Runtime von CommaView und koppelt dann Ihr Handy damit. Hält sie an, sagt ihre Meldung, welcher Teil gescheitert ist. Beheben Sie zuerst diesen Teil. Dass SSH funktioniert, beweist nur den ersten: Ein Kopplungscode kann nicht funktionieren, solange die Runtime nie gestartet ist."
parked: true
updated: 2026-11-27
needs:
  - title: "In P"
    text: "Das Auto in P mit deaktiviertem openpilot, und eingeschaltet: Ohne Dauerstrom-Kabel schaltet sich mit dem Auto auch das comma aus."
  - title: "Ein Netzwerk"
    text: "Ihr Handy im selben WLAN wie das comma oder in seinem Hotspot. Dass ein Laptop das comma erreicht, beweist nicht, dass Ihr Handy es kann."
steps:
  - id: read
    title: "Lesen, was die Einrichtung meldet, und die Details kopieren"
    body: |
      Scheitert die Installation, sagt die Einrichtung, was schiefging, ob Ihr comma auf den alten Stand zurückgesetzt wurde und was zu tun ist. Suchen Sie diesen Satz unten unter [Wenn es nicht funktioniert](#fixes).

      **Details kopieren** kopiert den Bericht, den der Support liest: die Version der App, das Release, die letzte Phase des Installationsprogramms und seine ganze Ausgabe. Fügen Sie ihn in eine E-Mail an support@commaview.com ein, wenn die Meldung das sagt.
    tabs:
      - label: "Die Installation ist gescheitert"
        body: "Die Einrichtung sagt, was gescheitert ist, und bietet **Details kopieren** an."
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**Details kopieren**."
          - target: install
            text: "**CommaView installieren** versucht es erneut, sobald Sie die Ursache behoben haben."
      - label: "SSH ist gescheitert"
        body: "Bevor etwas installiert wird, sagt die Einrichtung, warum sie nicht auf das comma kam, etwa **SSH-Anmeldung fehlgeschlagen**, und was zu prüfen ist."
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "Was schiefging und was zu prüfen ist."
  - id: address
    title: "Die Adresse des comma prüfen"
    body: |
      Die Einrichtung sucht commas im Netz Ihres Handys. Steht Ihres nicht in der Liste, tippen Sie auf **Mein comma fehlt** und geben Sie seine IP-Adresse ein. Auf Ihrem comma steht sie unter **Einstellungen → Netzwerk**: beim comma four unter dem Netzwerknamen auf der WLAN-Schaltfläche, beim comma 3X unter **Erweitert**.

      Das comma hat in jedem Netz eine andere Adresse: in Ihrem WLAN zu Hause, in einem Hotspot, in einem VPN. Nutzen Sie die Adresse für das Netz, in dem Ihr Handy gerade ist.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Ein comma, das die Einrichtung in diesem Netz gefunden hat."
      - text: "**Mein comma fehlt**: Geben Sie die IP-Adresse ein, wenn es nicht gefunden wird."
  - id: pair-code
    title: "Mit einem neuen Code koppeln"
    body: |
      Kopplungscodes sind kurzlebig und gelten nur einmal. Wird einer abgelehnt, geben Sie ihn nicht erneut ein: Holen Sie einen neuen. Nach einer manuellen Installation zeigt das Installationsprogramm einen; ein Handy, das schon mit dem comma gekoppelt ist, zeigt einen unter **Einstellungen des Geräts › Weiteres Handy oder Tablet koppeln**.
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**IP-Adresse des comma**."
      - target: pair-code
        text: "**Kopplungscode**. Bindestrich optional."
  - id: runs
    title: "Schon installiert? Dann koppeln"
    body: |
      Läuft CommaView schon auf dem comma, von einem anderen Handy oder einer früheren Einrichtung, müssen Sie nicht neu installieren. Tippen Sie auf der Startseite auf **comma hinzufügen**, dann auf **Adresse und Code eingeben**, und koppeln Sie mit der IP-Adresse des comma und einem Kopplungscode oder einer Einladung.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "Die IP-Adresse des comma."
      - target: pair-code
        text: "**Kopplungscode oder Einladung**."
      - target: pair
        text: "**comma koppeln**."
  - id: no-video
    title: "Installiert und gekoppelt, aber kein Video"
    body: |
      Nach der Kopplung ist ein fehlendes Bild ein Streaming-Problem, kein SSH-Problem. Live View sagt, was es sieht, etwa **Dieses comma ist nicht erreichbar**, und verbindet sich von selbst neu, wenn das comma antwortet. Siehe [CommaView findet Ihr comma nicht](/de/guides/comma-not-found).
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**Erneut versuchen**."
fixes:
  - q: "„SSH-Anmeldung fehlgeschlagen.“"
    a: "Prüfen Sie, ob der CommaView-Schlüssel bei GitHub hinzugefügt ist (beliebiger Titel) und SSH auf dem comma aktiviert ist. Haben Sie Ihren GitHub-Benutzernamen auf dem comma eingetragen, bevor Sie den Schlüssel hinzugefügt haben, entfernen Sie ihn und tragen Sie ihn neu ein, damit das comma Ihre Schlüssel erneut abruft."
  - q: "„Verbindung zu 192.168.1.50:22 abgelehnt. Prüfen Sie, ob SSH auf Ihrem comma aktiviert ist.“"
    a: "Gehen Sie auf dem comma zu **Einstellungen → Gerät → SSH** und schalten Sie SSH ein."
  - q: "„Zeitüberschreitung bei der Verbindung zu …“ oder „Keine Route zu …“"
    a: "Ihr Handy erreicht diese Adresse nicht. Prüfen Sie, ob Ihr Handy im selben WLAN wie das comma ist oder in seinem Hotspot, ob das comma wach ist (das Auto an) und ob die IP-Adresse die des comma in diesem Netz ist."
  - q: "„Kein comma unter … gefunden. Prüfen Sie die IP-Adresse.“"
    a: "Unter dieser Adresse hat nichts geantwortet. Prüfen Sie die IP-Adresse auf dem comma unter **Einstellungen → Netzwerk**."
  - q: "„Die SSH-Identität dieses comma hat sich seit der letzten Einrichtung geändert.“"
    a: "Haben Sie das comma zurückgesetzt oder neu geflasht, richten Sie es erneut ein."
  - q: "„CommaView konnte seinen SSH-Schlüssel auf diesem Handy nicht erstellen. Versuchen Sie es erneut oder nutzen Sie Ihren eigenen SSH-Schlüssel.“"
    a: "Tippen Sie auf **Erneut versuchen**, oder auf **Eigenen SSH-Schlüssel nutzen**, um ein Schlüsselpaar zu importieren, das Sie schon bei GitHub haben."
  - q: "„Installation wartet.“"
    a: "Das Auto fuhr, deshalb hat das comma die Installation eingereiht, statt die Fahrt zu unterbrechen. Legen Sie P ein, deaktivieren Sie openpilot, lassen Sie das Auto ein oder zwei Minuten eingeschaltet und tippen Sie dann auf **Einrichtung abschließen**."
  - q: "„Das Auto fährt, daher lief die Installation nicht.“"
    a: "Legen Sie P ein, deaktivieren Sie openpilot und versuchen Sie es erneut."
  - q: "„Auf Ihrem comma läuft schon eine andere Installation, Aktualisierung oder Reparatur von CommaView.“"
    a: "Warten Sie ein paar Minuten, bis sie fertig ist, und versuchen Sie es dann erneut."
  - q: "„Ihr comma konnte CommaView nicht herunterladen.“"
    a: "Das comma lädt die Runtime selbst herunter. Prüfen Sie, ob es mit dem Internet verbunden ist, per WLAN oder eigener SIM-Karte, und versuchen Sie es erneut. Ein Handy-Hotspot mit mobilen Daten funktioniert."
  - q: "„Der Download von CommaView kam unvollständig oder beschädigt auf Ihrem comma an.“"
    a: "Versuchen Sie es erneut. Passiert es wieder, kopieren Sie die Details und senden Sie sie an support@commaview.com."
  - q: "„Ihrem comma ging während der Installation der Speicher aus.“"
    a: "Versuchen Sie es später erneut. Passiert es wieder, kopieren Sie die Details und senden Sie sie an support@commaview.com."
  - q: "„CommaView unterstützt die Fahrsoftware auf Ihrem comma noch nicht.“"
    a: "Auf Ihrem comma läuft Software, auf der CommaView nicht installieren kann. [Prüfen Sie, mit welchen Forks es funktioniert](/de/guides/forks). Um Ihren anzufragen, kopieren Sie die Details und senden Sie sie an support@commaview.com."
  - q: "„CommaView kann seine Ansicht nicht sicher zu … hinzufügen“"
    a: "Ihr Fork ist einer, den CommaView nicht listet, und seine Prüfung hat ergeben, dass sein Bildschirm dort abweicht, wo CommaView sich anschließt. Auf Ihrem comma wurde nichts geändert. Um Ihren Fork anzufragen, kopieren Sie die Details und senden Sie sie an support@commaview.com."
  - q: "„comma 3 wird nicht unterstützt“"
    a: "CommaView funktioniert mit dem comma 3X und dem comma four. Das openpilot-Release des comma 3 ist upstream eingefroren und zeichnet seinen Bildschirm anders, deshalb kann CommaView seine Einblendungen nicht zeigen."
  - q: "„CommaView startete nach der Installation nicht auf Ihrem comma.“"
    a: "Starten Sie Ihr comma neu und versuchen Sie es erneut. Passiert es wieder, kopieren Sie die Details und senden Sie sie an support@commaview.com."
  - q: "„Prüfung fehlgeschlagen. Die CommaView-API unter 192.168.1.50:5002 war nicht erreichbar.“"
    a: "Die Installation ist fertig, aber Ihr Handy erreicht die Runtime nicht. Prüfen Sie, ob Ihr Handy noch im Netz des comma ist, und versuchen Sie es erneut. Funktioniert SSH von einem Computer aus, aber dies nicht, ist der Computer in einem Netz, in dem Ihr Handy nicht ist."
  - q: "„Kopplungscode konnte nicht eingelöst werden.“"
    a: "Der Code ist abgelaufen, wurde schon genutzt oder falsch eingegeben. Holen Sie einen neuen ([Schritt 3](#step-pair-code))."
  - q: "„Kopplung fehlgeschlagen: Die CommaView-Runtime-API war nicht erreichbar“"
    a: "Ihr Handy erreicht das comma unter dieser Adresse nicht. Prüfen Sie den Hotspot oder das Netz und versuchen Sie es erneut."
  - q: "„CommaView startet nach einem Neustart nicht von selbst“"
    a: "CommaView ist installiert, aber nichts startet es, wenn Ihr comma hochfährt: In `/data/continue.sh` Ihres comma fehlt die Zeile `exec ./launch_openpilot.sh`. Sobald sie da ist, installieren Sie CommaView erneut."
related: [setup, comma-not-found, support-bundle]
---

## Die Teile, die die Einrichtung durchläuft

Jeder Teil braucht den davor, also prüfen Sie sie in dieser Reihenfolge:

1. **SSH**, Port 22: So kommt die Einrichtung zum Installieren auf das comma. Es braucht Ihren GitHub-Schlüssel, Ihren GitHub-Benutzernamen auf dem comma und eingeschaltetes SSH.
2. **Die Installation**: Das comma lädt die Runtime herunter und installiert sie. Lesen Sie ihr Ergebnis, bevor Sie etwas Späteres prüfen.
3. **Die Runtime**, Port 5002 auf dem comma: Die Einrichtung prüft, ob sie antwortet, und koppelt dann mit ihr.
4. **Kopplung**: Ein einmaliger Kopplungscode gibt Ihrem Handy einen eigenen Schlüssel für das comma.
5. **Video**, Ports 8200 bis 8202: die Kameras von Live View.

Findet die Suche das comma nicht, Sie kennen aber seine Adresse, funktioniert das Eingeben genauso gut: Die Suche ist eine Bequemlichkeit, entscheidend ist, dass das comma erreichbar ist.

## Sicherheit

Führen Sie Einrichtung, Installationen und Fehlersuche durch, während das Auto in P ist und openpilot deaktiviert. Richten Sie während der Fahrt nie etwas ein und tippen Sie nicht in der App herum.
