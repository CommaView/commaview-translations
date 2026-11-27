---
title: "CommaView von Ihrem comma entfernen"
description: "Deinstallieren Sie die CommaView-Runtime in den Einstellungen des Geräts, stellen Sie die Dateien Ihres Forks wieder her und vergessen Sie das comma auf Ihrem Handy."
topic: account
order: 3
kind: walkthrough
lede: "**Runtime deinstallieren** entfernt CommaView von Ihrem comma: Es macht die Hooks von CommaView rückgängig, stoppt seine Runtime und löscht `/data/commaview`. Ihr Fork fährt weiter wie immer. Nutzen Sie es, um CommaView zu entfernen oder die geführte Einrichtung von vorn zu starten."
parked: true
updated: 2026-11-27
needs:
  - title: "Handy und comma zusammen"
    text: "Im selben WLAN wie das comma oder in seinem Hotspot. Die Einstellungen des Geräts brauchen das comma, um Updates und das Entfernen zu verwalten."
  - title: "Das Auto an, in P"
    text: "Fährt das Auto, stellt das comma die Deinstallation zurück, bis es in P ist und openpilot deaktiviert."
steps:
  - id: device-settings
    title: "Die Einstellungen des Geräts öffnen"
    body: |
      Öffnen Sie auf der Startseite die **Einstellungen des Geräts** Ihres comma, dann **Runtime** („Aktualisieren oder entfernen“).
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**Runtime**: CommaView aktualisieren oder entfernen."
  - id: uninstall
    title: "Auf „Runtime deinstallieren“ tippen"
    body: |
      Unter dem Runtime-Update entfernt **Runtime deinstallieren** CommaView von diesem comma. Danach kann die geführte Einrichtung von vorn laufen.
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**Runtime deinstallieren**."
  - id: confirm
    title: "Bestätigen"
    body: |
      **CommaView wird entfernt**: CommaView macht seine Runtime-Hooks rückgängig, stoppt und löscht `/data/commaview` von diesem comma. Das comma bleibt auf Ihrem Handy gespeichert. Tippen Sie auf **Runtime deinstallieren**, sobald der kurze Countdown abgelaufen ist.
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**CommaView wird entfernt**, und was das bewirkt."
      - text: "**Runtime deinstallieren**, nach dem Countdown. **Abbrechen** behält CommaView."
    note: "Fährt das Auto, stellt das comma die Deinstallation zurück: CommaView wird entfernt, sobald das Auto in P ist und openpilot deaktiviert, und läuft bis dahin weiter."
  - id: forget
    title: "Das comma auf Ihrem Handy vergessen, wenn Sie möchten"
    body: |
      Die Einstellungen des Geräts melden nun, dass die Runtime entfernt wurde. Um das comma auch von Ihrem Handy zu nehmen, tippen Sie am Ende der Einstellungen des Geräts auf **Dieses comma vergessen**: CommaView zeigt dieses comma nicht mehr und löscht seinen Kopplungs-Schlüssel. Um die App selbst zu entfernen, deinstallieren Sie CommaView wie jede andere App in den Android-Einstellungen.
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**Dieses comma vergessen**."
check: "Der Dialog meldet **Runtime deinstalliert**, und die Einstellungen des Geräts zeigen die Runtime als **Entfernt**: „CommaView wurde von Ihrem comma deinstalliert. Starten Sie die geführte Einrichtung, um es neu zu installieren.“"
fixes:
  - q: "„Deinstallation fehlgeschlagen: fehlende SSH-Rechte“"
    a: "Das comma hat dieses Handy nicht per SSH hereingelassen. Prüfen Sie, ob SSH auf dem comma unter **Einstellungen → Gerät → SSH** eingeschaltet ist und sein GitHub-Benutzername den Schlüssel dieses Handys hat, und tippen Sie dann auf **Erneut deinstallieren**."
  - q: "„Das comma konnte CommaView nicht deinstallieren und hat es gelassen, wie es war“"
    a: "Es wurde nichts entfernt. Versuchen Sie es erneut, während das Auto in P ist."
  - q: "„Deinstallation wartet, bis das Auto in P ist“"
    a: "Das Auto fährt. Legen Sie P ein, deaktivieren Sie openpilot, lassen Sie das Auto eingeschaltet, und das comma entfernt CommaView von selbst."
  - q: "Die Schaltfläche zum Deinstallieren ist ausgegraut"
    a: "CommaView aktualisiert oder deinstalliert gerade schon eine Runtime. Versuchen Sie es erneut, wenn das abgeschlossen ist."
related: [setup, update-runtime, forks]
---

## Was die Deinstallation wiederherstellt

- **Auf einem gelisteten Fork** macht sie den kleinen Hook rückgängig, den CommaView der Bildschirmoberfläche des Forks hinzufügt.
- **Auf einem Fork, den CommaView nicht listet** (ohne Gewähr), stellt sie die Dateien des Forks wieder her, wie sie waren.
- **Nur Video** hat nichts an den Dateien des Forks geändert, und die Deinstallation entfernt die Runtime.

Deinstallieren Sie auf SunnyPilot-TeslaHW1 die Runtime vor `op fork update`, denn das kann den Fork nicht wechseln, solange der Hook von CommaView installiert ist. Mehr dazu unter [Prüfen Sie, ob Ihr comma und Ihr Fork unterstützt werden](/de/guides/forks).

## CommaView erneut einrichten

Nach einer Deinstallation bleibt das comma auf Ihrem Handy gespeichert. Starten Sie die [geführte Einrichtung](/de/guides/setup), um es als frische Installation neu zu installieren.
