---
title: "CommaView einrichten"
description: "Installieren Sie die CommaView-App auf Android, bereiten Sie Ihr comma 3X oder comma four vor und lassen Sie die geführte Einrichtung die Runtime installieren und Ihr comma koppeln."
topic: start
order: 1
kind: walkthrough
lede: "CommaView besteht aus zwei Teilen: der App auf Ihrem Android-Handy, Tablet oder Infotainment und ihrer kleinen Runtime auf Ihrem comma. Installieren Sie die App, dann bringt die geführte Einrichtung in der App die Runtime auf Ihr comma, prüft sie und koppelt es. Das dauert ein paar Minuten, in P und mit deaktiviertem openpilot."
parked: true
updated: 2026-11-27
needs:
  - title: "Ein comma 3X oder comma four"
    text: "Mit openpilot oder einem [unterstützten Fork](/de/guides/forks). Das comma 3 wird nicht unterstützt: Sein openpilot-Release ist upstream eingefroren und zeichnet seinen Bildschirm anders, deshalb kann CommaView seine Einblendungen nicht zeigen. [Warum das comma 3 nicht unterstützt wird](/#faq-comma-3)."
  - title: "Ein Android-Gerät und Ihre Einladung"
    text: "Android 8 oder neuer und die E-Mail-Adresse, an die Ihre Einladung ging. CommaView ist in der Beta: Sie melden sich mit dem eingeladenen Konto an."
  - title: "Dasselbe Netzwerk"
    text: "Ihr Handy und das comma in einem lokalen Netzwerk: Ihr WLAN, der Hotspot Ihres Handys, der eigene Hotspot des comma oder ein anderes Netz, in das beide können. Im Auto? [Ohne WLAN zu Hause verbinden](/de/guides/connect-in-the-car)."
  - title: "Ein GitHub-Konto"
    text: "Das comma lässt SSH-Schlüssel des GitHub-Benutzernamens herein, den Sie ihm geben. CommaView erstellt den Schlüssel; Sie fügen ihn während der Einrichtung bei GitHub hinzu."
howItWorks:
  - title: "Ihr Handy"
    text: "Erstellt einen SSH-Schlüssel, den Sie bei GitHub hinzufügen."
    edge: "SSH"
  - title: "Ihr comma"
    text: "Holt den Schlüssel über Ihren GitHub-Benutzernamen. CommaView installiert seine Runtime neben Ihrem Fork."
    edge: "lokales Netzwerk"
  - title: "CommaView"
    text: "Prüft, ob die Runtime antwortet, und speichert Ihr comma. Ab dann verbindet es sich von selbst neu."
steps:
  - id: get-the-app
    title: "App holen und anmelden"
    body: |
      Melden Sie sich auf Ihrem Android-Gerät unter [my.commaview.com](https://my.commaview.com) mit der E-Mail-Adresse an, an die Ihre Einladung ging. Tippen Sie unter **Get the app** auf **Download CommaView**. Daneben steht die SHA-256-Prüfsumme, falls Sie die Datei prüfen möchten.

      Öffnen Sie den Download. Android bittet Sie, Installationen aus Ihrem Browser zu erlauben: Erlauben Sie es für diese Installation und schalten Sie es danach wieder aus.

      Öffnen Sie CommaView. Es fragt einmal, ob Sie **CommaView verbessern helfen** möchten: **Senden** oder **Nicht senden**. Dann bittet es Sie, sich anzumelden: Tippen Sie auf **Anmelden** und nutzen Sie die E-Mail-Adresse, an die Ihre Einladung ging. Danach funktioniert es offline, solange sein Zugangspass gültig ist.
    tabs:
      - label: "CommaView verbessern helfen"
        body: "Absturzberichte und welche Fahrsoftware Ihr comma nutzt, nie Videos, Fahrten, Orte oder Namen. Sie können es jederzeit unter Einstellungen › **Datenschutz & Teilen** ändern."
        screen: improve-commaview
        pins:
          - target: send
            text: "**Senden** schickt Absturzberichte, damit Probleme behoben werden können."
          - target: dont-send
            text: "**Nicht senden** behält sie auf dem Handy."
      - label: "Anmelden"
        body: "Während der Beta braucht CommaView Ihr eingeladenes Konto. **Anmelden** öffnet Ihren Browser."
        screen: sign-in
        pins:
          - target: sign-in
            text: "**Anmelden** mit der E-Mail-Adresse, an die Ihre Einladung ging."
    note: "Installieren Sie auf einem Infotainment oder einer AI-Box am Bildschirm Ihres Autos? [Bildschirme im Auto](/de/guides/car-screens) erklärt das Netzwerk und das Koppeln mit Ihrem comma."
  - id: connect
    title: "Ihr comma einrichten"
    body: |
      Lesen Sie den Hinweis, bestätigen Sie, dass Sie verstehen, dass es inoffizielle Software ist und Sie für den sicheren Gebrauch verantwortlich sind, und tippen Sie auf **Verstanden – weiter**.

      Tippen Sie unter **comma verbinden** auf **CommaView auf Ihrem comma einrichten**.
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**CommaView auf Ihrem comma einrichten**, für ein comma, auf dem CommaView noch nicht läuft."
      - target: pair-runs
        text: "Läuft schon CommaView darauf, von einem anderen Handy aus? Dann stattdessen **comma mit CommaView koppeln**: [Ein weiteres Handy oder Tablet hinzufügen](/de/guides/another-phone)."
  - id: setup-path
    title: "Einrichtungsweg wählen"
    tabs:
      - label: "Geführte Einrichtung"
        body: "Wählen Sie **Geführte Einrichtung** (als empfohlen markiert) und tippen Sie auf **Weiter zur geführten Einrichtung**. CommaView erstellt einen SSH-Schlüssel, führt Sie durch die Verbindung und prüft Ihr comma. Die nächsten Schritte folgen ihr."
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**Geführte Einrichtung**, als empfohlen markiert."
          - target: continue
            text: "**Weiter zur geführten Einrichtung**."
      - label: "Manuelle Einrichtung"
        body: "Nur wenn SSH von Ihrem Computer zum comma als Benutzer `comma` bereits funktioniert. Wählen Sie **Manuelle Einrichtung**, dann **Weiter zur manuellen Einrichtung**, und führen Sie den Befehl in Ihrem Terminal aus. Wenn das Installationsprogramm einen einmaligen Kopplungscode zeigt, tippen Sie auf **Befehl ausgeführt**, geben die IP-Adresse Ihres comma und den Code ein und tippen auf **comma hinzufügen**. [Manuelle Einrichtung im Terminal](#manuelle-einrichtung-im-terminal) beschreibt jeden Schritt."
        screen: setup-manual-instructions
        pins:
          - text: "**Zum Kopieren tippen** kopiert den Befehl."
          - target: ran-command
            text: "**Befehl ausgeführt**, sobald das Installationsprogramm seinen Kopplungscode zeigt."
  - id: ssh-key
    title: "SSH-Schlüssel bei GitHub hinzufügen"
    body: |
      CommaView erstellt einen SSH-Schlüssel für dieses Handy. Tippen Sie auf **Schlüssel kopieren, GitHub öffnen**: Das kopiert den öffentlichen Schlüssel und öffnet die Seite für neue SSH-Schlüssel bei GitHub.

      Fügen Sie den Schlüssel bei GitHub in das Feld **Key** ein, geben Sie ihm einen beliebigen Titel (CommaView trägt einen ein) und speichern Sie mit **Add SSH key**. Kehren Sie zu CommaView zurück und tippen Sie auf **Weiter**.
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**Schlüssel kopieren, GitHub öffnen**. Es meldet „SSH-Schlüssel kopiert. GitHub wird geöffnet…“"
      - target: own-key
        text: "**Eigenen SSH-Schlüssel nutzen** importiert ein Schlüsselpaar, das Sie schon bei GitHub haben."
      - target: continue
        text: "**Weiter**, sobald der Schlüssel bei GitHub gespeichert ist."
    note: "Haben Sie schon ein Schlüsselpaar bei GitHub? **Eigenen SSH-Schlüssel nutzen** importiert es stattdessen. Der private Schlüssel bleibt auf Ihrem Handy."
  - id: comma-ssh
    title: "SSH auf Ihrem comma einschalten"
    body: |
      Gehen Sie auf dem Bildschirm des comma zu **Einstellungen → Gerät → SSH**:

      1. Geben Sie Ihren GitHub-Benutzernamen ein.
      2. Warten Sie, bis das comma Ihre GitHub-Schlüssel abgerufen hat.
      3. Schalten Sie SSH ein.

      Kehren Sie dann zu CommaView zurück und tippen Sie auf **Weiter**.
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "**Weiter**, sobald SSH eingeschaltet ist."
    note: "Das comma ruft Ihre Schlüssel einmal ab, wenn Sie den Benutzernamen eingeben. Haben Sie ihn eingegeben, bevor Sie den Schlüssel hinzugefügt haben? Entfernen Sie ihn und geben Sie ihn erneut ein, damit das comma die Schlüssel neu abruft."
  - id: choose-comma
    title: "Ihr comma auswählen"
    body: |
      CommaView listet die commas in diesem WLAN, auf denen CommaView schon läuft. Ein comma, das Sie zum ersten Mal einrichten, steht deshalb meist noch nicht dort. Tippen Sie auf **Mein comma fehlt** und geben Sie seine IP-Adresse ein. Tippen Sie dann auf **CommaView installieren**.

      Die IP-Adresse finden Sie auf dem comma unter **Einstellungen → Netzwerk**: beim comma four unter dem Netzwerknamen auf der WLAN-Schaltfläche, beim comma 3X unter **Erweitert**.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Ein comma, auf dem CommaView schon läuft. Eines, das auf diesem Handy gespeichert ist, ist mit **Auf diesem Handy gespeichert** markiert."
      - text: "**Mein comma fehlt**: Geben Sie seine IP-Adresse ein."
      - target: install
        text: "**CommaView installieren**."
  - id: safe-install
    title: "Sichere Installation starten"
    body: |
      Der Dialog **Sichere Installation** nennt das comma, auf dem installiert wird. Lesen Sie den Hinweis und tippen Sie auf **Sichere Installation starten**, sobald der kurze Countdown abgelaufen ist.
    tabs:
      - label: "Das Auto ist in P"
        body: "Ist das Auto in P und openpilot nicht aktiv, installiert CommaView sofort."
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "**Sichere Installation starten**, nach dem Countdown."
      - label: "Das Auto fährt"
        body: "Das comma stellt die Installation zurück und führt sie aus, sobald das Auto in P ist und openpilot deaktiviert, damit keine Fahrt unterbrochen wird. Die Einrichtung zeigt **Installation wartet**: Legen Sie P ein, deaktivieren Sie openpilot, warten Sie ein oder zwei Minuten und tippen Sie dann auf **Einrichtung abschließen**."
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "**Einrichtung abschließen**, sobald das Auto in P ist."
    note: "Dann verbindet sich CommaView per SSH mit dem comma, prüft, welches comma es ist, und installiert die Runtime, mit der diese App-Version getestet wurde. Es prüft, ob die Installation antwortet, und speichert Ihr comma auf diesem Handy. Lassen Sie das Handy im selben Netzwerk, bis alles fertig ist."
    warn: "Lassen Sie das Auto eingeschaltet und in P. Ohne Dauerstrom-Kabel schaltet sich mit dem Auto auch das comma aus, und die Installation bricht ab."
  - id: ready
    title: "CommaView ist bereit"
    body: |
      Ihr comma ist installiert, gekoppelt und verbindet sich beim nächsten Start von selbst neu.
    tabs:
      - label: "CommaView ist bereit"
        body: "Tippen Sie auf **Fertig**."
        screen: setup-done
        pins:
          - target: finish
            text: "**Fertig** bringt Sie zur Startseite."
      - label: "Zum Abschluss neu starten"
        body: "Manchmal meldet die Einrichtung **Zum Abschluss neu starten**: Nach einem Neustart streamt das comma auf Ihr Handy. Tippen Sie auf **comma neu starten, abschließen**, während das Auto aus ist oder in P mit deaktiviertem openpilot. openpilot hält während des Neustarts etwa eine Minute an."
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**comma neu starten, abschließen**."
check: "Die Startseite zeigt Ihr Auto mit seinem comma als **Verbunden**, dazu die Runtime und die Adresse des comma. Tippen Sie auf **Live View öffnen**: Die Straße läuft live, mit dem Fahrpfad und dem Vorderfahrzeug darüber. Ab jetzt findet die App Ihr comma von selbst, wenn Handy und comma im selben Netzwerk sind, auch wenn sich seine Adresse ändert."
fixes:
  - q: "Keine Verbindung per SSH"
    a: "Prüfen Sie, ob SSH auf dem comma unter **Einstellungen → Gerät → SSH** eingeschaltet ist, ob der GitHub-Benutzername Ihrer ist und ob der CommaView-Schlüssel in diesem GitHub-Konto steht. Haben Sie den Schlüssel erst nach dem Benutzernamen hinzugefügt, entfernen Sie den Benutzernamen und geben ihn erneut ein, damit das comma den Schlüssel abruft."
  - q: "Mein comma steht nicht in der Liste"
    a: "Beim ersten Mal ist das normal: Die Liste zeigt commas, auf denen CommaView schon läuft. Tippen Sie auf **Mein comma fehlt** und geben Sie seine IP-Adresse ein (**Einstellungen → Netzwerk** auf dem comma: beim comma four unter dem Netzwerknamen auf der WLAN-Schaltfläche, beim comma 3X unter **Erweitert**). Prüfen Sie, ob das Handy im selben Netzwerk wie das comma ist und kein VPN nutzt."
  - q: "Die Einrichtung meldet „Installation wartet“"
    a: "Das comma hat bemerkt, dass das Auto fährt, und wartet deshalb. Legen Sie P ein, deaktivieren Sie openpilot, warten Sie eine Minute und tippen Sie dann auf **Einrichtung abschließen**. Lassen Sie das Auto eingeschaltet: Ohne Dauerstrom-Kabel schaltet sich mit dem Auto auch das comma aus."
  - q: "Die Einrichtung meldet, mein comma werde nicht unterstützt"
    a: "Auf einem comma 3 hält die Einrichtung an und bietet **CommaView auf einem comma 3X oder comma four einrichten** an. Auf einem Fork, dessen Bildschirm CommaView seine Ansicht nicht hinzufügen kann, sagt die Einrichtung das und ändert nichts. [Prüfen Sie, ob Ihr comma und Ihr Fork unterstützt werden](/de/guides/forks)."
  - q: "Der Kopplungscode hat nicht funktioniert"
    a: "Kopplungscodes gelten nur einmal und laufen schnell ab. Starten Sie das Installationsprogramm erneut, um einen neuen Code zu bekommen, und prüfen Sie, ob Sie ihn so eingegeben haben, wie er angezeigt wird (der Bindestrich ist optional)."
  - q: "Verbunden, aber kein Video"
    a: "Einrichtung und Kopplung sind erledigt; es geht um den Videostream. Prüfen Sie, ob das comma eingeschaltet und bereit für die Fahrt ist, lassen Sie das Handy im selben Netzwerk und öffnen Sie Live View erneut. Steht dort **Dieses comma ist nicht erreichbar**, lesen Sie [Ihr comma wird nicht gefunden](/de/guides/comma-not-found)."
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## Manuelle Einrichtung im Terminal

Nur wenn SSH von Ihrem Computer zum comma als Benutzer `comma` bereits funktioniert.

1. Wählen Sie in CommaView **Manuelle Einrichtung**, dann **Weiter zur manuellen Einrichtung**. Die App zeigt unter **Über Ihr Terminal installieren** den Befehl für ihre Runtime, bereit zum Kopieren (**Zum Kopieren tippen**). Er sieht aus wie dieser, der die Runtime des aktuellen Releases installiert:

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. Führen Sie ihn auf einem Computer im selben WLAN wie Ihr comma aus und ersetzen Sie `COMMA_IP` durch die IP-Adresse des comma (**Einstellungen → Netzwerk** auf dem comma: beim comma four unter dem Netzwerknamen auf der WLAN-Schaltfläche, beim comma 3X unter **Erweitert**). Ihr Computer lädt das Installationsprogramm herunter, und SSH führt es auf dem comma als Benutzer `comma` aus.
3. Wenn das Installationsprogramm fertig ist, startet CommaView auf dem comma und zeigt einen einmaligen Kopplungscode.
4. Tippen Sie zurück in CommaView auf **Befehl ausgeführt**. Wählen Sie unter **comma hinzufügen** Ihr comma aus oder geben Sie seine IP-Adresse ein, tippen Sie den Kopplungscode ein und tippen Sie auf **comma hinzufügen**. Die App prüft die Runtime und speichert das comma.

## Vor Ihrer ersten Fahrt

Probieren Sie es in P aus, bevor Sie losfahren.

- Die Startseite zeigt Ihr comma als **Verbunden**.
- Live View läuft, und der Fahrpfad bewegt sich mit dem Auto.
- Zeigt die App eine Warnung oder bittet um eine Reparatur, klären Sie das vor der Fahrt.
- Richten Sie alles so ein, dass es während der Fahrt nie Ihre Aufmerksamkeit braucht.

Kommen Sie nicht weiter? Fragen Sie im [CommaView-Discord](https://discord.gg/UuMhz9K8ft) oder senden Sie Feedback aus der App. Bittet der Support um Logs, [senden Sie ein Support-Paket](/de/guides/support-bundle).
