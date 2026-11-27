---
title: "Aufnahmen teilen und exportieren"
description: "Teilen Sie eine Wiedergabe oder Live-Kopie aus „Aufnahmen“, öffnen Sie sie in einer anderen App, oder exportieren Sie eine ganze Fahrt von Ihrem comma als eine MP4 auf Ihr Handy."
topic: recordings
order: 3
kind: walkthrough
lede: "Jede Aufnahme auf Ihrem Handy ist eine MP4, die Sie teilen, in Ihren Dateien speichern oder in einer anderen App öffnen können, über ihr Menü **Aktionen für Aufnahmen** in „Aufnahmen“. **Ganze Fahrt exportieren…** kopiert außerdem das Straßenvideo einer ganzen Fahrt von Ihrem comma auf Ihr Handy, so wie das comma es aufgenommen hat."
parked: true
updated: 2026-11-27
needs:
  - title: "Eine Aufnahme auf Ihrem Handy"
    text: "Eine Wiedergabe oder Live-Kopie in „Aufnahmen“. Noch nicht? [Eine Fahrt aufnehmen](/de/guides/record) oder [eine Live-Kopie aufnehmen](/de/guides/live-copy)."
  - title: "Für eine ganze Fahrt"
    text: "Das comma, das sie aufgenommen hat, gekoppelt mit diesem Handy, geparkt und in Reichweite, und eine Runtime, die ihre Fahrten auflistet."
steps:
  - id: open
    title: "Die Aufnahme öffnen"
    body: |
      Öffnen Sie **Aufnahmen** in der Leiste unten (auf einem größeren Bildschirm in der Seitenleiste) und tippen Sie auf die Fahrt. Sie öffnet sich in der Ansicht, mit ihrem Player und ihren Angaben.
    screen: phone-recordings
    pins:
      - text: "Eine Wiedergabe. Tippen Sie auf eine Fahrt, um sie zu öffnen."
      - target: live-copy-row
        text: "Eine Live-Kopie, markiert als **Live-Kopie**."
      - target: filter
        text: "**Filter**: **Bereit** zeigt nur Fahrten mit einem Video zum Teilen."
  - id: actions
    title: "„Aktionen für Aufnahmen“ öffnen"
    body: |
      Tippen Sie in der Ansicht auf **Aktionen für Aufnahmen**, die Schaltfläche „Mehr“ neben Uhrzeit und Datum.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Aktionen für Aufnahmen**."
      - text: "**Vollbild** spielt sie über den ganzen Bildschirm ab."
  - id: share
    title: "Teilen oder in einer anderen App öffnen"
    body: |
      **Teilen** übergibt das Video an das Teilen-Menü von Android, wo Sie es senden oder in Ihren Dateien speichern können. **In anderer App öffnen** spielt es in einem anderen Videoplayer ab.

      **Dateien** listet bei einer Fahrt mit mehreren Dateien jede einzeln zum Teilen, etwa jeden Teil einer langen ganzen Fahrt.
    screen: recordings-watch-menu
    pins:
      - target: share
        text: "**Teilen**: das Teilen-Menü von Android."
      - target: open-in
        text: "**In anderer App öffnen**."
      - target: send
        text: "**An CommaView senden…** schickt stattdessen ein Problem mit dieser Fahrt an CommaView: [Ein Support-Paket senden](/de/guides/support-bundle)."
    note: "Das Teilen-Menü von Android ist nicht abgebildet: Es gehört zu Android und sieht auf jedem Handy anders aus."
    warn: "Ein Video kann mehr zeigen als die Straße: wo und wann Sie gefahren sind, Kennzeichen, Gesichter und Orte, und die Fahrerkamera in einer Live-Kopie, die mit eingeschalteter „Fahrercam“ entstand. Prüfen Sie es, bevor Sie es teilen."
  - id: export
    title: "Eine ganze Fahrt exportieren"
    body: |
      Für eine Fahrt, die Ihr comma aufgenommen hat, enthält **Aktionen für Aufnahmen** den Punkt **Ganze Fahrt exportieren…**. Er kopiert die Straßenkamera des comma für die ganze Fahrt als eine MP4 auf Ihr Handy, genau so, wie das comma sie aufgenommen hat. Sie hat kein HUD: **Wiedergabe erstellen** zeichnet die Fahransicht über die aufgenommenen Teile.
    screen: recordings-watch-menu
    pins:
      - target: export-drive
        text: "**Ganze Fahrt exportieren…**"
  - id: export-sheet
    title: "Die Größe prüfen, dann auf „Exportieren“ tippen"
    body: |
      Das Blatt sagt, wie viel von der Fahrt das comma hat, etwa **23 Min. · etwa 1,7 GB**, und wie viel auf Ihrem Handy frei ist. Tippen Sie auf **Exportieren**: „Die ganze Fahrt wird exportiert. Sie wird unter Aufnahmen gespeichert, sobald das comma parkt.“

      Nichts wird heruntergeladen, bevor Sie auf „Exportieren“ tippen. Ab dann behält das comma die Fahrt, während sie kopiert wird; bis dahin kann es sie noch löschen, um Platz zu schaffen, die ältesten Fahrten zuerst.
    screen: recordings-export
    pins:
      - target: export
        text: "**Exportieren**."
      - target: cancel
        text: "**Abbrechen** lässt es."
  - id: whole-drive
    title: "Die ganze Fahrt in „Aufnahmen“ finden"
    body: |
      Der Export ist eine eigene Zeile, **Ganze Fahrt**, neben der Aufnahme, aus der Sie ihn angefordert haben. Während er wartet, sagt er warum, etwa **Wartet, bis Sie parken**, dann **Wird vom comma gespeichert** mit dem Fortschritt. Ist er gespeichert, lässt er sich wie jede Aufnahme abspielen und teilen.
    screen: phone-recordings
    pins:
      - text: "Die Zeile **Ganze Fahrt**, benannt nach dem Beginn der Fahrt."
    note: "Eine Fahrt mit mehr als etwa 45 Minuten Straßenvideo wird in Teilen zu 3,5 GB gespeichert: **Dateien** listet jeden."
check: "Das Teilen-Menü von Android öffnet sich mit dem Video. Bei einer ganzen Fahrt läuft ihre Zeile, und die Angabe **Gespeichert** meldet **Die ganze Fahrt · auf diesem Handy**."
fixes:
  - q: "**Ganze Fahrt exportieren…** fehlt im Menü"
    a: "Es wird für eine Fahrt angeboten, die Ihr comma aufgenommen hat, solange dieses comma mit diesem Handy gekoppelt ist und seine Runtime ihre Fahrten auflistet. [Aktualisieren Sie die Runtime des comma](/de/guides/update-runtime), wenn sie älter ist. Eine Live-Kopie hat keine Fahrt auf dem comma zum Exportieren."
  - q: "**Ganze Fahrt exportieren…** ist ausgegraut: „Schon exportiert“, „Wird exportiert“ oder „Ihre Kopie wurde gestoppt: „Speichern wiederholen“ in ihrer Zeile“"
    a: "Die Fahrt wurde schon exportiert, oder ihr Export läuft. Ist er gestoppt, öffnen Sie die Zeile **Ganze Fahrt** und wählen Sie in ihrem Menü **Speichern wiederholen**."
  - q: "„Das comma hat diese Fahrt nicht, daher lässt sie sich nicht exportieren.“"
    a: "Das comma hat sie gelöscht, um Platz für neuere Fahrten zu schaffen. Nichts kann sie zurückholen."
  - q: "„Diese Fahrt ist älter als die 50, die das comma listet, daher lässt sie sich nicht zum Kopieren finden.“"
    a: "Ihr comma listet seine 50 neuesten Fahrten, und diese ist älter, deshalb findet der Export sie nicht."
  - q: "„Braucht etwa 2,2 GB frei. Geben Sie zuerst Speicher frei.“"
    a: "Löschen Sie Fahrten, die Sie nicht mehr brauchen, oder wählen Sie unter **Einstellungen › Aufnahmen** einen anderen Speicher, und öffnen Sie das Blatt dann erneut."
  - q: "Die ganze Fahrt meldet „Wartet, bis Sie parken“, „Wartet auf das comma“ oder „Wartet, solange Live View offen ist“"
    a: "Sie wird nur kopiert, solange das comma geparkt ist, in Reichweite Ihres Handys und Live View nicht zeigt. Sie läuft von selbst weiter, sobald das möglich ist."
  - q: "„Kein Videoplayer gefunden“"
    a: "Für **In anderer App öffnen** gibt es auf diesem Gerät keine andere Video-App. Spielen Sie es in „Aufnahmen“ ab, oder speichern Sie es mit **Teilen** in Ihren Dateien."
  - q: "„Diese Wiedergabe lässt sich hier nicht abspielen. Versuchen Sie eine andere App.“"
    a: "Nutzen Sie **In anderer App öffnen**, oder teilen Sie sie mit einer App, die sie abspielt."
related: [record, live-copy, support-bundle]
---

## Mehrere auf einmal teilen

Halten Sie eine Fahrt gedrückt, um sie auszuwählen, und tippen Sie dann auf weitere, um sie hinzuzufügen. Die Leiste unten sagt, wie viele ausgewählt sind. Ihr Menü **Mehr** enthält **Teilen**, das jedes ausgewählte Video zusammen an das Teilen-Menü von Android übergibt, und die Leiste hat **Löschen**. Eine Fahrt, deren Video noch nicht auf Ihrem Handy ist, wird ausgelassen, und die Aktion sagt, wie viele sie übernimmt.

## Neue Fahrten automatisch abrufen

**Einstellungen › Aufnahmen › Neue Fahrten abrufen** holt die Straßenkamera jeder neuen Fahrt ohne Tippen nach Hause: etwa jede halbe Stunde, solange Ihr Handy und Ihr comma in einem WLAN sind, das Sie unter **WLANs** wählen, und das Auto geparkt ist. Jede abgerufene Fahrt ist in „Aufnahmen“ eine Zeile **Vom comma**, ohne HUD, wie eine ganze Fahrt. **Platz für abgerufene Fahrten** begrenzt ihren Speicher: 10, 20 oder 50 GB, oder **Kein Limit**. Sie werden nie gelöscht, um Platz zu schaffen.

## Wohin sie gehen

Geteilte Dateien gehen nur dorthin, wohin Sie sie senden. Aufnahmen bleiben auf Ihrem Handy, und die Sicherung von Android und ein Umzug auf ein neues Handy lassen sie aus.
