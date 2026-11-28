---
title: "So funktionieren CommaView-Releases"
description: "Wie die CommaView-App und die Runtime auf Ihrem comma veröffentlicht werden: erst Alphas, dann eine Beta, signierte Downloads, passende Runtimes und Updates, die auf P warten."
topic: account
order: 2
kind: reference
lede: "CommaView hat zwei Teile, die zusammen aktualisiert werden: die Android-App und die kleine Runtime auf Ihrem comma. So kommt ein Release zu Ihnen, und so bleiben Updates sicher."
updated: 2026-11-27
steps:
  - id: version
    title: "Sehen, welche Version Sie haben"
    body: |
      Einstellungen › **Über** zeigt die Version der App und ob sie **Aktuell** ist oder ein Update bereitsteht, mit dessen Version. CommaView fragt in Ihrem Konto nach neuen Releases und sagt Ihnen, wenn eines bereit ist.
    screen: support-about
    pins:
      - target: version
        text: "Die Version der App."
      - target: up-to-date
        text: "**Aktuell**, oder das Release, das für Sie bereitsteht."
  - id: app-update
    title: "Die App in der App aktualisieren"
    body: |
      Ist ein Release bereit, erscheint **Update** oben auf der Startseite und unter **Über**. **CommaView aktualisieren** nennt die Version und ihren Kanal: **Beta** für alle Eingeladenen oder **Alpha**, „Eine frühe Version für Tester. Sie kann mehr Fehler haben als die Beta.“ Tippen Sie auf **Herunterladen**: CommaView lädt es im Hintergrund herunter, prüft es, dann bittet Android Sie, die Installation zu bestätigen.
    screen: app-update-offer
    pins:
      - target: channel
        text: "Der Kanal: **Beta** oder **Alpha**."
      - target: download
        text: "**Herunterladen**. **Später** verschiebt es."
  - id: runtime
    title: "Dann die Runtime Ihres comma aktualisieren"
    body: |
      Jedes App-Release nennt die Runtime, mit der es getestet wurde. Ist die App aktualisiert, bietet die Startseite diese Runtime mit **Runtime-Update bereit** an. Runtime-Updates starten immer in der App, nie von selbst. [Die Runtime Ihres comma aktualisieren](/de/guides/update-runtime) beschreibt jeden Schritt.
    screen: home-runtime-update
    pins:
      - target: update-card
        text: "**Runtime-Update**: die installierte und die verfügbare Runtime."
related: [update-runtime, uninstall, setup]
---

## Erst Alpha, dann Beta

- Jede Version erscheint zuerst als Reihe von Alphas für wenige Tester.
- Bewährt sich eine Alpha, wird sie zur Beta dieser Version und geht an alle Eingeladenen.
- Ihr Konto unter [my.commaview.com](https://my.commaview.com) bietet immer das Release an, das für Sie passt.

## Signiert und abgestimmt

- Jeder App-Download ist ein signierter Release-Build, nie ein Debug-Build, mit seiner SHA-256-Prüfsumme daneben auf my.commaview.com. Die App prüft Größe und Prüfsumme eines heruntergeladenen Updates, bevor sie die Installation anbietet: „Der Download passte nicht zu seiner Prüfsumme und wurde daher nicht installiert.“
- Jedes App-Release nennt die Runtime, mit der es getestet wurde, und die App installiert genau diese auf Ihrem comma.
- Einer älteren App wird nie eine Runtime angeboten, mit der sie nicht getestet wurde. Hat ein comma eine neuere Runtime, als die App installiert, sagt sie das: Aktualisieren Sie CommaView und versuchen Sie es erneut.

## Ihr comma sicher aktualisieren

- Runtime-Updates starten auf der Startseite oder in den Einstellungen des Geräts, nie von selbst.
- Updates unterbrechen nie eine Fahrt. Fährt das Auto, reiht das sichere Update das Update ein, und das comma installiert es, sobald das Auto in P ist und openpilot deaktiviert. Sie müssen das Auto nicht ausschalten.
- Nach einem Runtime-Update braucht das comma einen Neustart, bevor CommaView wieder streamt. Die App bittet Sie darum.
- Sie können die Runtime jederzeit in den Einstellungen des Geräts entfernen: [CommaView entfernen](/de/guides/uninstall).

## Wo Sie davon erfahren

- Die App sagt Ihnen, wenn ein neues Release bereit ist.
- [Neuigkeiten](/whats-new) listet jede Änderung.
- Über wichtige Änderungen informieren wir Sie per E-Mail, und Sie können jederzeit Feedback aus der App senden (Einstellungen › **Support & Diagnose**).
