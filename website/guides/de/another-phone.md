---
title: "Ein weiteres Handy oder Tablet hinzufügen"
description: "Geben Sie einem weiteren Handy, Tablet oder Bildschirm im Auto mit einer 10-Minuten-Einladung einen eigenen Schlüssel zu Ihrem comma, und sehen und entfernen Sie die Handys, die einen haben."
topic: start
order: 4
kind: walkthrough
lede: "Jedes Handy, das Ihr comma ansieht, hat einen eigenen Schlüssel. Um ein weiteres Handy, Tablet oder einen Bildschirm im Auto hinzuzufügen, zeigen Sie eine Einladung auf einem Handy, das Ihr comma schon hat, und tippen oder scannen Sie sie auf dem neuen. Kein SSH, keine neue Einrichtung."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Ein Handy mit Schlüssel"
    text: "Ein Handy, das schon mit Ihrem comma gekoppelt ist, mit CommaView 0.0.166 oder neuer und der passenden Runtime. Noch nicht? [CommaView einrichten](/de/guides/setup)."
  - title: "CommaView auf dem neuen Gerät"
    text: "Installiert und angemeldet, mit 0.0.166 oder neuer. [App holen](/de/guides/setup#step-get-the-app)."
  - title: "Dasselbe Netzwerk"
    text: "Beide im selben WLAN wie das comma oder in seinem Hotspot."
howItWorks:
  - title: "Ihr Handy"
    text: "Bittet das comma um eine Einladung: einen Code oder einen QR-Code, 10 Minuten gültig."
  - title: "Das neue Handy"
    text: "Tritt mit der Einladung bei und bekommt einen eigenen Schlüssel."
    edge: "lokales Netzwerk"
  - title: "Ihr comma"
    text: "Teilt jedem Handy mit Schlüssel mit, dass ein neues einen hat."
steps:
  - id: device-settings
    title: "Auf Ihrem Handy „Weiteres Handy koppeln“ öffnen"
    body: |
      Öffnen Sie auf dem Handy, das Ihr comma schon hat, auf der Startseite die **Einstellungen des Geräts** des comma, dann **Weiteres Handy koppeln**.
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**Weiteres Handy koppeln**: ein kurzlebiger Code, damit sich ein anderes Handy oder Tablet verbinden kann."
  - id: show-invitation
    title: "Eine Einladung zeigen"
    body: |
      Unter **Handys mit Schlüssel** zeigt **Weiteres Handy hinzufügen** eine Einladung für ein Handy, das dieses comma noch nicht hat. Tippen Sie auf **Einladung zeigen**.
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**Einladung zeigen**."
      - text: "Die Handys mit einem Schlüssel zu diesem comma, dieses zuerst."
  - id: invitation
    title: "Die Einladung auf dem Bildschirm lassen"
    body: |
      **Weiteres Handy hinzufügen** zeigt einen Code in drei Gruppen, einen QR-Code und die IP-Adresse des comma. Die Einladung gilt 10 Minuten und nur einmal. Ist sie abgelaufen, zeigen Sie eine neue.
    screen: invitation-dialog
    pins:
      - target: code
        text: "Der Code, den Sie auf dem neuen Handy eingeben."
      - target: qr
        text: "Oder der QR-Code zum Scannen."
      - text: "**Läuft ab in …**: 10 Minuten ab dem Anzeigen."
  - id: add-comma
    title: "Auf dem neuen Handy das comma hinzufügen"
    body: |
      Tippen Sie auf dem neuen Handy unter **comma verbinden** auf **comma mit CommaView koppeln**. Ist dort schon ein comma, tippen Sie stattdessen auf der Startseite auf **comma hinzufügen**.

      Ihr comma erscheint unter **In diesem Netz**. Tippen Sie darauf, oder tippen Sie auf **QR-Code scannen** und scannen Sie die Einladung. Steht es nicht in der Liste, tippen Sie auf **Adresse und Code eingeben**.
    screen: add-comma
    pins:
      - target: found-comma
        text: "Ihr comma, in diesem Netz gefunden."
      - target: scan-qr
        text: "**QR-Code scannen**, um die Einladung zu scannen."
      - target: enter-address
        text: "**Adresse und Code eingeben**, wenn es nicht in der Liste steht."
  - id: pair
    title: "Einladung eingeben und koppeln"
    body: |
      Prüfen Sie die **comma-IP**, geben Sie die Einladung unter **Kopplungscode oder Einladung** ein (oder tippen Sie auf die QR-Schaltfläche, um sie zu scannen) und tippen Sie auf **comma koppeln**. Das neue Handy bekommt einen eigenen Schlüssel und zeigt Ihr comma auf der Startseite.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**comma-IP**, ausgefüllt bei einem gefundenen comma."
      - target: pair-code
        text: "**Kopplungscode oder Einladung**."
      - target: scan-qr
        text: "**Kopplungs-QR scannen**."
      - target: pair
        text: "**comma koppeln**."
  - id: new-key
    title: "Auf Ihren anderen Handys bestätigen"
    body: |
      Jedes Handy mit Schlüssel erfährt: **Ein neues Handy hat einen Schlüssel**, mit seinem Namen und dem Zeitpunkt. Tippen Sie auf **Es ist meins**. Gehört es nicht Ihnen, tippen Sie auf **Entfernen**; **Handys prüfen** öffnet **Weiteres Handy koppeln**, wo jedes Handy mit Schlüssel aufgelistet ist.
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "**Es ist meins**, für Ihr eigenes Handy oder Tablet."
      - target: review
        text: "**Handys prüfen** listet jedes Handy mit Schlüssel auf."
check: "Das neue Handy zeigt Ihr comma auf der Startseite und öffnet Live View. Auf Ihrem ersten Handy führt **Weiteres Handy koppeln** es unter **Handys mit Schlüssel** auf."
fixes:
  - q: "„Mit dieser Einladung ließ sich nicht beitreten“"
    a: "Sie ist vielleicht vertippt, abgelaufen oder schon genutzt. Zeigen Sie eine neue auf dem Handy, das dieses comma schon hat (in seinen Einstellungen des Geräts: **Weiteres Handy koppeln**, **Weiteres Handy hinzufügen**)."
  - q: "„Die Runtime dieses comma stammt aus der Zeit vor Handy-Schlüsseln“"
    a: "Aktualisieren Sie zuerst die Runtime des comma: [Die Runtime Ihres comma aktualisieren](/de/guides/update-runtime). Zeigen Sie dann die Einladung."
  - q: "„Dieses comma ist nicht erreichbar“"
    a: "Beide Handys müssen im selben WLAN wie das comma sein oder in seinem Hotspot. [Im Auto verbinden](/de/guides/connect-in-the-car)."
  - q: "„Kopplung fehlgeschlagen: Dieses comma koppelt nicht mehr per Code“"
    a: "Das comma nimmt das alte gemeinsame Token nicht mehr an. Fügen Sie das Handy von einem aus hinzu, das schon einen Schlüssel hat (in dessen Einstellungen: **Weiteres Handy hinzufügen**), oder richten Sie das comma erneut ein."
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## Ein Handy entfernen

Öffnen Sie auf einem Handy mit Schlüssel die **Einstellungen des Geräts** des comma, dann **Weiteres Handy koppeln**. Tippen Sie neben einem Handy in der Liste auf **Entfernen**. Es erreicht dieses comma erst wieder, wenn es erneut hinzugefügt wird, mit einer Einladung oder durch eine neue Einrichtung des comma.

## Handys mit einer älteren CommaView-Version

Vor 0.0.166 schickte jedes Handy dem comma dasselbe gemeinsame Token. Ein Handy mit 0.0.166 bekommt seinen Schlüssel bei der nächsten Verbindung, ohne erneutes Koppeln.

- **Ältere CommaView-Apps** unter **Weiteres Handy koppeln** zeigt, wie viele Tage ein Handy mit einer älteren CommaView-Version dieses comma noch mit dem gemeinsamen Token nutzen kann: 90 Tage, nachdem das erste Handy einen Schlüssel bekommen hat. Bis dahin koppelt **Kopplungscode für eine ältere App** ein Handy mit einer älteren CommaView-Version.
- **Jetzt stoppen** sorgt dafür, dass das comma das gemeinsame Token nicht mehr annimmt, sobald jedes Handy, das es nutzt, einen Schlüssel hat. Handys mit einer älteren CommaView-Version funktionieren dann nicht mehr mit diesem comma und können erst nach einem Update wieder koppeln.
- Danach braucht ein Handy ohne Schlüssel CommaView 0.0.166 oder neuer und eine Einladung.

Wenn Sie die Runtime Ihres comma aktualisieren, aktualisieren Sie zuerst CommaView auf jedem Gerät, das es ansieht, auch auf Bildschirmen im Auto.
