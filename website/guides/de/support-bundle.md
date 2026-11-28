---
title: "Ein Support-Paket senden"
description: "Lassen Sie die Diagnose an, lassen Sie das Problem erneut auftreten und senden Sie dann unter Einstellungen › Support & Diagnose einen Bericht mit den Logs Ihres Handys und Ihres comma."
topic: troubleshooting
order: 3
kind: walkthrough
lede: "Ein Support-Paket ist eine kleine ZIP-Datei mit dem, was die CommaView-App auf Ihrem Handy und ihre Runtime auf Ihrem comma gesehen haben. Damit finden wir ein Problem, ohne in Ihrem Auto zu sitzen. Es enthält nur Logs: kein Video, keinen Standort."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Diagnose an"
    text: "**Diagnose auf diesem Handy speichern** ist an, sofern niemand es ausgeschaltet hat. Prüfen Sie das, bevor das Problem erneut auftritt."
  - title: "Mit Ihrem comma verbunden"
    text: "Für die Logs Ihres comma zeigt die Startseite Ihr comma beim Senden als **Verbunden**."
  - title: "Zum Senden angemeldet"
    text: "Zum Senden brauchen Sie Ihr Beta-Konto. Abgemeldet funktioniert **Als Datei speichern** trotzdem."
howItWorks:
  - title: "Ihr Handy"
    text: "Behält seine Logs und Zähler Ihrer letzten 10 Fahrten."
  - title: "Ihr comma"
    text: "Fügt beim Tippen auf Senden die Logs seiner Runtime hinzu, ohne Standort, FIN, IDs, WLAN-Namen und Tokens."
    edge: "beim Tippen auf Senden"
  - title: "Das CommaView-Team"
    text: "Liest es in privatem Speicher und antwortet per E-Mail."
steps:
  - id: open
    title: "Support & Diagnose öffnen"
    body: |
      Tippen Sie in CommaView unten in der Leiste auf **Einstellungen**. Auf einem Tablet oder Infotainment ist es in der Leiste an der Seite. Tippen Sie auf **Support & Diagnose**, weit unten, vor „Über“.
    screen: support-settings
    pins:
      - text: "**Support & Diagnose**."
  - id: keep-diagnostics
    title: "Diagnose auf diesem Handy speichern"
    body: |
      **Diagnose auf diesem Handy speichern** ist an, sofern niemand es ausgeschaltet hat: Die App behält ihre Logs und Zähler Ihrer letzten 10 Fahrten, damit ein Bericht sagen kann, was passiert ist. Ist es aus, schalten Sie es ein und lassen Sie das Problem dann erneut auftreten.
    screen: support-diagnostics
    pins:
      - target: keep-diagnostics
        text: "**Diagnose auf diesem Handy speichern**."
    note: "Die Diagnose bleibt auf diesem Handy, bis Sie einen Bericht senden: Sie wird nie automatisch hochgeladen."
  - id: happen-again
    title: "Es im Stand erneut auftreten lassen"
    body: |
      Verbinden Sie sich wie gewohnt mit Ihrem comma: Ihr Handy im WLAN oder Hotspot des comma, und die Startseite zeigt Ihr comma als **Verbunden**. Tun Sie, was schiefging; öffnen Sie zum Beispiel Live View, wechseln Sie zu der Fahransicht, die sich falsch verhält, und lassen Sie sie 10 bis 20 Sekunden offen. Notieren Sie ungefähr, wann es passiert ist und was Sie getan haben. Eine Bildschirmaufnahme hilft auch.
    warn: "Lassen Sie es in P auftreten. Passiert es nur auf der Straße, lassen Sie es geschehen und senden Sie den Bericht, sobald Sie geparkt haben: Die Aufzeichnung wartet auf Sie. Tippen Sie während der Fahrt nie in der App herum."
  - id: open-send
    title: "„An CommaView senden“ öffnen"
    body: |
      Tippen Sie unter **Support & Diagnose** auf **Problem melden oder Idee senden**.

      Oder beginnen Sie beim Problem: Wo die App einen Fehler zeigt, tippen Sie auf **Melden**; bei einer Aufnahme wählen Sie unter **Aktionen für Aufnahmen** den Punkt **An CommaView senden…**. Jedes öffnet dasselbe Blatt, mit dem Passenden schon ausgefüllt.
    screen: support-diagnostics
    pins:
      - target: report
        text: "**Problem melden oder Idee senden**."
  - id: send
    title: "Auswählen, was mitgeht, und senden"
    body: |
      Wählen Sie **Problem** und beschreiben Sie, was passiert ist. Lassen Sie unter **Angehängt** die Einträge **Dieses Handy: Diagnose** und die Logs Ihres comma eingeschaltet. **Ansehen** zeigt genau, was jeder enthält. Unter den Zeilen listet das Blatt, was mit jedem Bericht mitgeht: die App-Version, Modell und Android-Version Ihres Handys sowie Fahrsoftware und Einrichtung Ihres comma.

      Tippen Sie auf **Senden**: „Wird gesendet. Läuft im Hintergrund und wartet auf eine Verbindung.“
    screen: support-send-feedback
    pins:
      - target: problem
        text: "**Problem** oder **Idee**."
      - text: "**Angehängt**: Jede Zeile hat einen Schalter und **Ansehen**."
      - target: send
        text: "**Senden**."
    note: "Senden Sie, während die App mit Ihrem comma verbunden ist: Sie fragt das comma beim Tippen auf Senden nach seinen Logs. Ist das comma aus oder außer Reichweite, sagt das Paket warum und enthält trotzdem die Logs der App."
  - id: save-file
    title: "Oder als Datei speichern"
    body: |
      Hat der Support um die Datei selbst gebeten, oder sind Sie nicht angemeldet? Tippen Sie statt auf Senden auf **Als Datei speichern**. Die App erstellt dasselbe Paket, eine kleine `.zip`, und öffnet das Teilen-Menü von Android. Senden Sie es dorthin, wo der Support es haben möchte: als Direktnachricht auf Discord, per E-Mail oder als Link zu einem Cloud-Speicher.
    screen: support-share-bug-report
    pins:
      - target: save-file
        text: "**Als Datei speichern**."
  - id: afterwards
    title: "Unsere Antwort lesen"
    body: |
      Wenn wir antworten, kommt die Antwort per E-Mail, und sie steht zusammen mit Ihrem Bericht unter [Your feedback](https://my.commaview.com/feedback) auf my.commaview.com. Antworten Sie uns dort, bis wir den Bericht schließen; danach können Sie ihn 30 Tage lang wieder öffnen. **Ihre Anfragen** unter **Support & Diagnose** listet sie ebenfalls.
    screen: support-diagnostics
    pins:
      - target: your-requests
        text: "**Ihre Anfragen**: Antworten und Ihre Gespräche mit CommaView."
check: "Das Blatt schließt sich mit „Wird gesendet. Läuft im Hintergrund und wartet auf eine Verbindung.“, und der Bericht erscheint unter **Ihre Anfragen**, sobald er gesendet ist."
fixes:
  - q: "Das Paket enthält keine Logs des comma"
    a: "Die App erreichte Ihr comma beim Tippen auf Senden nicht, oder seine Zeile unter **Angehängt** war aus. Prüfen Sie, ob die Startseite Ihr comma als **Verbunden** zeigt, bevor Sie „An CommaView senden“ öffnen, und lassen Sie die Zeile Ihres comma eingeschaltet. Bittet die App Sie, Ihr comma erneut zu koppeln, koppeln Sie es zuerst und senden Sie dann erneut."
  - q: "Auf der Senden-Schaltfläche steht **Zum Senden anmelden**"
    a: "Sie sind abgemeldet. Tippen Sie darauf, um sich mit Ihrem Beta-Konto anzumelden, oder nutzen Sie **Als Datei speichern**."
  - q: "„Die Anhänge sind größer als die 25 MB, die ein Bericht tragen kann. Schalten Sie einen aus oder nutzen Sie „Als Datei speichern“.“"
    a: "Schalten Sie einen Anhang aus, den Sie nicht brauchen, oder tippen Sie auf **Als Datei speichern** und senden Sie die Datei dorthin, wo der Support es wünscht."
  - q: "Beim Tippen auf „Als Datei speichern“ passiert nichts"
    a: "Android hat auf diesem Gerät keine App, die eine Datei annehmen kann. Auf Infotainments ist das häufig. [Senden Sie es](#step-send) stattdessen an CommaView, oder speichern Sie es von einem Handy mit CommaView."
  - q: "„Der Bericht ließ sich nicht vorbereiten. Prüfen Sie den lokalen Speicher und versuchen Sie es erneut.“"
    a: "Die App konnte das Paket nicht schreiben, meist weil das Gerät zu wenig Speicher hat. Geben Sie Platz frei und versuchen Sie es erneut."
related: [setup-troubleshooting, comma-not-found, releases]
---

## Was ein Support-Paket enthält

- **Dieses Handy: Diagnose.** Die Diagnose-Logs und Zähler von CommaView auf diesem Handy: Fehler bei Videostream, Darstellung, Verbindung und Aufnahme, mit App-Version, Modell und Android-Version des Handys. Mit Navigation auch, wie viele Ortssuchen jeder Art geklappt haben oder gescheitert sind, nie wonach Sie gesucht haben.
- **Die Logs Ihres comma.** Ist die Zeile Ihres comma an: Logs, Zähler und Einstellungen der CommaView-Runtime, welche openpilot-Prozesse gestoppt sind und warum, und Zeilen zu Speichermangel aus dem Kernel des comma.
- **Nie in einem Paket.** Kein Video, kein GPS-Standort, keine FIN und keine rohen Fahrtdaten: Eine Aufnahme, die Sie senden, geht neben dem Paket mit, nicht darin. Eine aktuelle comma-Runtime entfernt GPS-Koordinaten, FINs, WLAN-Namen, öffentliche IP-Adressen, Tokens und die vollständige Dongle-ID, bevor sie ihre Logs sendet.
- **Nur wenn Sie senden.** Ein Paket verlässt Ihr Handy nur, wenn Sie auf Senden oder „Als Datei speichern“ tippen. Eine gespeicherte Datei geht nur dorthin, wohin Sie sie schicken. Lokale IP-Adressen, Sitzungs-IDs und Versionsangaben können enthalten bleiben, teilen Sie ein Paket also nur mit Menschen, denen Sie vertrauen.

## Wohin es geht und wie lange

Ein gesendetes Paket geht in den privaten Speicher von CommaView, wo nur das CommaView-Team es öffnet. Es wird 180 Tage nach dem Senden gelöscht, oder früher, sofort, wenn Sie uns darum bitten oder Ihr Konto löschen ([Datenschutz](/privacy)). Schreiben Sie dafür an support@commaview.com.

Um zu entfernen, was die App auf diesem Handy speichert, tippen Sie unter **Support & Diagnose** auf **Lokale Diagnosedaten löschen**. Ihre Aufnahmen werden dabei nie gelöscht. Um ab dann nur noch den Verlauf der Aufnahmefehler zu behalten, schalten Sie auf derselben Seite **Diagnose auf diesem Handy speichern** aus.

Nicht sicher, wohin Sie es senden sollen? Fragen Sie im [CommaView-Discord](https://discord.gg/UuMhz9K8ft).
