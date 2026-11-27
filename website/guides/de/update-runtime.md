---
title: "Die Runtime Ihres comma aktualisieren"
description: "Aktualisieren Sie die CommaView-Runtime auf Ihrem comma über die Startseite oder die Einstellungen des Geräts. Das sichere Update wartet auf P, damit nie eine Fahrt unterbrochen wird."
topic: account
order: 1
kind: walkthrough
lede: "Die CommaView-Runtime auf Ihrem comma wird über die App aktualisiert, nie von selbst. Aktualisieren Sie zuerst CommaView, dann die Runtime, wenn die App sie anbietet. Fährt das Auto, reiht das **sichere Update** das Update auf dem comma ein und installiert es, sobald das Auto in P ist und openpilot deaktiviert."
updated: 2026-11-27
needs:
  - title: "Handy und comma zusammen"
    text: "Im selben WLAN wie das comma oder in seinem Hotspot."
  - title: "Das Auto an"
    text: "Lassen Sie das Auto eingeschaltet und in P. Ohne Dauerstrom-Kabel schaltet sich mit dem Auto auch das comma aus."
howItWorks:
  - title: "CommaView"
    text: "Jedes App-Release nennt die Runtime, mit der es getestet wurde, und bietet genau diese an."
  - title: "Ihr comma"
    text: "Lädt sie herunter, prüft und installiert sie, sobald das Auto in P ist."
    edge: "Neustart"
  - title: "Live View"
    text: "Startet wieder, sobald das comma neu gestartet ist."
steps:
  - id: app-first
    title: "Zuerst CommaView aktualisieren"
    body: |
      Die App installiert die Runtime, mit der sie getestet wurde. Aktualisieren Sie deshalb erst die App, dann die Runtime. Ist ein Update bereit, erscheint **Update** oben auf der Startseite und unter Einstellungen › **Über**. Tippen Sie darauf: **CommaView aktualisieren** nennt die Version, ihren Kanal und die Größe. Tippen Sie auf **Herunterladen**; CommaView lädt es im Hintergrund herunter und prüft es, dann bittet Android Sie, die Installation zu bestätigen.
    screen: app-update-offer
    pins:
      - target: download
        text: "**Herunterladen**."
      - target: channel
        text: "Der Kanal des Releases: **Beta**, oder **Alpha** für Tester."
    note: "Aktualisieren Sie CommaView auf jedem Handy, Tablet und Bildschirm im Auto, das dieses comma ansieht, bevor Sie seine Runtime aktualisieren."
  - id: open
    title: "Das Runtime-Update öffnen"
    tabs:
      - label: "Auf der Startseite"
        body: "Die Startseite zeigt **Runtime-Update bereit**, wenn eine neue Runtime für dieses comma bereit ist. Tippen Sie auf **Update ansehen**: Die Karte **Runtime-Update** zeigt die Versionen **Installiert** und **Verfügbar** und ob das Auto bereit ist. Tippen Sie auf **Runtime aktualisieren**, oder auf **Update einreihen**, während das Auto fährt."
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**Runtime-Update**: Installiert, Verfügbar und ob das Auto bereit ist."
          - target: update-runtime
            text: "**Runtime aktualisieren** (**Update einreihen**, während das Auto fährt)."
      - label: "In den Einstellungen des Geräts"
        body: "Öffnen Sie die **Einstellungen des Geräts** des comma, dann **Runtime** (dort steht **Update**, wenn eines bereit ist). Die Seite zeigt die installierte und die verfügbare Runtime. Tippen Sie auf **Jetzt aktualisieren**."
        screen: device-runtime
        pins:
          - target: update-now
            text: "**Jetzt aktualisieren**."
  - id: install
    title: "Installieren oder vom sicheren Update einreihen lassen"
    body: |
      In den Einstellungen des Geräts sagt der Dialog **Runtime-Update**, ob das Auto bereit ist.
    tabs:
      - label: "Das Auto ist in P"
        body: "Er meldet „Das Auto ist in P und openpilot nicht aktiv. Das Runtime-Update kann sicher starten.“ Tippen Sie auf **Update installieren**."
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**Update installieren**."
          - target: close
            text: "**Schließen** verschiebt es."
      - label: "Das Auto fährt"
        body: "Er meldet „Das Auto fährt. Das sichere Update reiht das Update auf dem comma ein und installiert es, sobald das Auto in P ist und openpilot deaktiviert.“ Tippen Sie auf **Sicheres Update…**, lesen Sie den Hinweis und tippen Sie auf **Sicheres Update starten**, sobald der kurze Countdown abgelaufen ist. Dasselbe passiert, wenn CommaView nicht feststellen konnte, ob das Auto fährt."
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**Sicheres Update…**, dann **Sicheres Update starten**."
    note: "CommaView stoppt nie openpilot oder Ihren Fork: Ein eingereihtes Update wartet auf P, und keine Fahrt wird unterbrochen."
  - id: progress
    title: "Laufen lassen"
    body: |
      Das comma lädt das Release herunter, prüft, ob es vollständig und unverändert ist, installiert es und startet CommaView neu, und die App zeigt jeden Schritt. Sie können die App wechseln oder Ihr Handy sperren: Das Update läuft weiter, und seine Benachrichtigung zeigt den Fortschritt.

      Bis das comma mit der Installation beginnt, stoppt **Update abbrechen** es, und auf Ihrem comma ändert sich nichts.
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "Die Schritte: Download, Prüfung, Installation, CommaView startet neu, Neu verbinden."
  - id: queued
    title: "Ein eingereihtes Update wartet auf P"
    body: |
      Ein eingereihtes Update erscheint auf der Karte **Runtime-Update** der Startseite als **Wartet, bis das Auto in P ist**. Es wird installiert, sobald das Auto ein paar Sekunden in P ist und openpilot deaktiviert. Lassen Sie das Auto während der Installation eingeschaltet.
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "**Wartet, bis das Auto in P ist**, mit seinem Schritt."
  - id: reboot
    title: "Zum Abschluss das comma neu starten"
    body: |
      Nach einem Runtime-Update braucht das comma einen Neustart, bevor CommaView wieder von ihm streamt: openpilot lädt den neuen Bildschirmcode von CommaView erst, wenn das comma neu startet. Die App startet es nie von selbst neu.

      Tippen Sie auf der Karte der Startseite auf **comma neu starten** oder im Dialog auf **comma jetzt neu starten**, während das Auto aus ist oder in P. openpilot hält etwa eine Minute an. Sie können es auch am comma selbst neu starten: **Einstellungen → Gerät → Neustart**.
check: "Der letzte Schritt des Updates meldet **Aktualisiert**, und die Einstellungen des Geräts zeigen die neue Runtime als **Aktuell**. Nach dem Neustart läuft Live View mit seinen Einblendungen."
fixes:
  - q: "„Die Runtime dieses comma ist neuer als die dieser App“"
    a: "Aktualisieren Sie CommaView und versuchen Sie es erneut. Auf dem comma wurde nichts geändert."
  - q: "„Update nötig“"
    a: "Diese App und die Runtime dieses comma sind nicht neu genug füreinander. Aktualisieren Sie zuerst CommaView, dann die Runtime."
  - q: "„Das comma hat … nicht installiert: Es nutzt …, das CommaView nicht listet“"
    a: "Das comma hat nichts geändert und die bisherige Runtime behalten. Um CommaView ohne Gewähr zu diesem Fork hinzuzufügen, richten Sie dieses comma erneut ein: Die Einrichtung prüft den Fork und fragt Sie zuerst."
  - q: "„Das Auto wurde bei jedem Start wieder eingeschaltet, daher hat das comma aufgehört, es zu versuchen“"
    a: "Legen Sie P ein, deaktivieren Sie openpilot und versuchen Sie es erneut."
  - q: "„Runtime-Update zurückgesetzt“"
    a: "Das comma hat die bisherige Runtime wiederhergestellt. Versuchen Sie es erneut, und wenn es wieder fehlschlägt, [senden Sie ein Support-Paket](/de/guides/support-bundle)."
  - q: "„CommaView aktualisiert oder deinstalliert bereits eine Runtime“"
    a: "Es läuft immer nur ein Runtime-Auftrag. Versuchen Sie es erneut, wenn er abgeschlossen ist."
  - q: "Keine Einblendungen oder Telemetrie nach dem Update"
    a: "Das comma ist noch nicht neu gestartet. Starten Sie es neu, während das Auto aus ist oder in P."
related: [releases, uninstall, another-phone]
---

## Warum Updates auf P warten

Beim Installieren der Runtime stoppt CommaView auf dem comma, während seine Dateien ersetzt werden, und seine Dienste starten neu. Deshalb macht das comma das nur, wenn das Auto in P ist und openpilot deaktiviert. Das sichere Update bittet openpilot nicht, in den Stand zu wechseln: Es reiht die Arbeit auf dem comma ein, das sie ausführt, sobald das Auto in P ist. Sie müssen das Auto nicht ausschalten; lassen Sie es eingeschaltet und in P.

Bevor sich auf dem comma etwas ändert, lädt es das Release herunter und prüft, ob es vollständig und unverändert ist. Schlägt eine Installation danach fehl, stellt das comma die bisherige Runtime wieder her.
