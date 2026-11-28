---
title: "Eine Fahrt in Live View aufnehmen"
description: "Tippen Sie in Live View auf „Aufnehmen“ und erstellen Sie nach dem Parken die Wiedergabe der Fahrt: das eigene Video des comma mit der Ansicht Ihres Forks darüber, auf Ihrem Handy gespeichert."
topic: recordings
order: 1
kind: walkthrough
lede: "**Aufnehmen** in Live View speichert eine Fahrt. Wenn Sie nichts anderes wählen, entsteht eine **Wiedergabe**: Nach dem Parken lädt CommaView das eigene Video des comma für den aufgenommenen Abschnitt herunter, bis zu 10 Minuten, und zeichnet auf Ihrem Handy die Fahransicht darüber. Nichts wird hochgeladen: Aufnahmen bleiben auf Ihrem Handy, bis Sie sie löschen."
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funktioniert"
    text: "CommaView auf Ihrem Handy, gekoppelt mit Ihrem comma. Noch nicht? [CommaView einrichten](/de/guides/setup), dann [Live View öffnen](/de/guides/live-view)."
  - title: "Das Auto an"
    text: "Aufnehmen startet, sobald das comma eine Fahrt begonnen hat, schalten Sie also zuerst das Auto ein. Starten Sie die Aufnahme in P, bevor Sie losfahren."
  - title: "Platz auf Ihrem Handy"
    text: "Eine Wiedergabe entsteht auf Ihrem Handy, aus dem Video des comma. Einstellungen › Aufnahmen zeigt den belegten und den freien Speicher."
howItWorks:
  - title: "Aufnehmen in Live View"
    text: "Öffnet das Aufnahmefenster des comma: Es behält die Daten der Fahransicht, solange Sie aufnehmen."
    edge: "nach dem Parken"
  - title: "Wiedergabe erstellen"
    text: "Das Handy lädt das Video des comma für diesen Abschnitt herunter, eine Fahrt nach der anderen."
  - title: "Aufnahmen"
    text: "Die Wiedergabe läuft auf Ihrem Handy, mit der Ansicht über dem Video."
steps:
  - id: choose
    title: "Wählen, was „Aufnehmen“ erstellt"
    body: |
      Tippen Sie auf **Einstellungen**, dann auf **Aufnahmen**. Unter **Aufnehmen in Live View** ist **Wiedergabe** gewählt, bis Sie es ändern: „Das beste Bild: das eigene Video des comma mit dem HUD darüber, erstellt nach dem Parken. Bis zu 10 Minuten pro Aufnahme.“

      **Live-Kopie** speichert stattdessen, was Live View zeigt, ohne Zeitlimit, und **Beides** erstellt beides. Dafür gibt es [eine eigene Anleitung](/de/guides/live-copy).
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Aufnehmen in Live View**: **Wiedergabe**, **Live-Kopie** oder **Beides**."
      - text: "**Wiedergabe** öffnet ihre Qualität: **Balanced**, **High** oder **Max**. Höhere Qualität braucht länger und erzeugt größere Dateien."
  - id: start
    title: "In Live View auf „Aufnehmen“ tippen"
    body: |
      Öffnen Sie bei eingeschaltetem Auto, noch in P, **Live View** und tippen Sie auf **Aufnehmen**. Kurz steht dort **Aufnahme startet**, während sich CommaView mit der Fahrt synchronisiert, dann läuft der Timer.
    screen: phone-live-view
    clip: record
    pins:
      - target: record-button
        text: "**Aufnehmen**. Auf einem Tablet, einem Infotainment oder einem quer gehaltenen Handy liegt es in der Leiste."
    warn: "Starten Sie die Aufnahme, bevor Sie losfahren, oder überlassen Sie sie einem Beifahrer. Tippen Sie während der Fahrt nicht in CommaView herum."
  - id: recording
    title: "Aufnehmen lassen"
    body: |
      Während der Aufnahme zeigt „Aufnehmen“ die Zeit, und **Details** meldet **Aufnahme ·** mit der Zeit. Tippen Sie erneut auf „Aufnehmen“, um zu stoppen. Eine Wiedergabe stoppt auch von selbst nach 10 Minuten und wenn Live View geschlossen wird.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "„Aufnehmen“ mit seinem Timer. Erneut antippen zum Stoppen."
      - target: recording
        text: "**Aufnahme ·** mit der Zeit, in **Details**."
      - text: "**Speichern** behält die letzten 3 Minuten und die nächste Minute, ohne „Aufnehmen“. Es wird nach dem Parken auf Ihr Handy kopiert."
    note: "**Speichern** erscheint nur, wo die Runtime Ihres comma ihre Fahrten auflistet. Ein Tippen in dieser nächsten Minute behält eine weitere Minute, bis zu 10 Minuten. Überlassen Sie das während der Fahrt einem Beifahrer."
  - id: make-replay
    title: "Parken, dann die Wiedergabe erstellen"
    body: |
      Öffnen Sie nach dem Parken **Aufnahmen** in der Leiste unten (auf einem größeren Bildschirm in der Seitenleiste). Die aufgenommene Fahrt meldet **Verarbeitung nötig**. Öffnen Sie sie und tippen Sie auf **Wiedergabe erstellen**: Die App meldet „Wiedergabe eingereiht. Verfolgen Sie sie in der Warteschlange.“

      Das comma teilt eine Fahrt nur, solange das Auto in P ist und openpilot deaktiviert. Lassen Sie also das Auto eingeschaltet und Ihr Handy im Netz des comma, bis die Wiedergabe erstellt ist. Ohne Dauerstrom-Kabel schaltet sich mit dem Auto auch das comma aus.
    screen: recordings-make-replay
    pins:
      - text: "**Wiedergabe erstellen**."
      - target: queue
        text: "**Warteschlange** zeigt jede Wiedergabe, die gerade erstellt wird, eine nach der anderen, mit Pausieren, Erneut versuchen und Entfernen."
    note: "**Wiedergabe erstellen** kann nach dem Parken bis zu einer Minute brauchen, bis es erscheint: Ein comma, das meldete, es fahre, wird eine Minute später erneut gefragt."
  - id: watch
    title: "In „Aufnahmen“ ansehen"
    body: |
      Ist sie erstellt, meldet die App **Wiedergabe erstellt** mit der Zahl ihrer Bilder, und die Fahrt läuft in „Aufnahmen“. Tippen Sie darauf, um sie anzusehen, auf Wunsch im Vollbild.
    screen: phone-recordings
    pins:
      - text: "Die Wiedergabe der Fahrt, unter dem Tag gruppiert."
      - target: filter
        text: "**Filter**: **Alle Fahrten**, **Bereit** oder **Verarbeitung nötig**, und welches comma."
check: "Die Zeile der Fahrt meldet nicht mehr **Verarbeitung nötig**, und sie läuft, wenn Sie darauf tippen. Um sie zu teilen oder woanders zu speichern, siehe [Aufnahmen teilen und exportieren](/de/guides/export-share)."
fixes:
  - q: "„Die Aufnahme kann starten, sobald das comma eine Fahrt begonnen hat.“"
    a: "Das comma ist geparkt. Schalten Sie das Auto ein, warten Sie, bis openpilot startet, und tippen Sie dann erneut auf „Aufnehmen“."
  - q: "„CommaView synchronisiert sich noch mit dieser Fahrt. Tippen Sie gleich erneut auf „Aufnehmen“.“"
    a: "„Aufnehmen“ braucht die Bildzeiten des comma, die mit seinen Fahrdaten kommen. Sie waren nach 5 Sekunden noch nicht da. Warten Sie einen Moment und tippen Sie erneut auf „Aufnehmen“."
  - q: "„CommaView empfängt keine Fahrdaten vom comma. Prüfen Sie die Verbindung und tippen Sie erneut auf „Aufnehmen“.“"
    a: "Das Video läuft vielleicht noch, aber die Fahrdaten sind ausgeblieben. Prüfen Sie, ob Ihr Handy noch im WLAN oder Hotspot des comma ist, und versuchen Sie es erneut. Meldet Live View **Fahrzeugdaten kommen nicht an**, starten Sie das comma neu."
  - q: "„Starten Sie zuerst das comma neu: CommaView wurde installiert, aktualisiert oder repariert und nimmt nach einem Neustart wieder auf.“"
    a: "Starten Sie das comma neu, während das Auto in P ist, und nehmen Sie dann erneut auf."
  - q: "„Speicher für Aufnahmen voll. Geben Sie Speicher frei und tippen Sie erneut auf „Aufnehmen“.“"
    a: "Löschen Sie in „Aufnahmen“ Fahrten, die Sie nicht mehr brauchen, oder wählen Sie unter **Einstellungen › Aufnahmen › Speicher** mit **Ändern** einen anderen Speicher."
  - q: "„Das comma hat keinen Platz mehr für die HUD-Daten dieser Fahrt (etwa 55 Minuten Aufnahmen). Nehmen Sie bei Ihrer nächsten Fahrt erneut auf.“"
    a: "Das comma behält pro Fahrt HUD-Daten für etwa 55 Minuten Aufnahmen. Erstellen Sie die Wiedergaben des Aufgenommenen und nehmen Sie bei der nächsten Fahrt erneut auf."
  - q: "„Legen Sie P ein, um diese Wiedergabe zu erstellen“, oder die Fahrt meldet „Wartet, bis Sie parken“"
    a: "Das comma teilt eine Fahrt nur im Stand, mit deaktiviertem openpilot. Legen Sie P ein und lassen Sie das Auto eingeschaltet. Die Wiedergabe wartet und fragt alle 15 Sekunden erneut; nach 30 Minuten Fahrt stoppt sie mit „Das Auto fuhr noch, daher konnte das comma diese Fahrt nicht teilen. Versuchen Sie es erneut, wenn Sie parken.“ Tippen Sie nach dem Parken in der Warteschlange auf **Erneut versuchen**."
  - q: "„Mit Comma Chameleon verbinden, um diese Wiedergabe zu erstellen“"
    a: "Ihr Handy erreichte das comma nicht, das die Fahrt aufgenommen hat (die Meldung nennt Ihres). Verbinden Sie Ihr Handy mit dem WLAN oder Hotspot des comma und tippen Sie dann in der Warteschlange auf **Erneut versuchen**. Siehe [CommaView findet Ihr comma nicht](/de/guides/comma-not-found)."
  - q: "„Fahrt vom comma gelöscht“"
    a: "Das comma hat diese Fahrt gelöscht, um Platz für neuere zu schaffen, bevor ihre Wiedergabe erstellt wurde, deshalb kann sie jetzt nicht mehr erstellt werden. Sie können die Aufnahme löschen. Eine Fahrt, die **Wiedergabe bald erstellen** meldet, ist kurz davor: Erstellen Sie sie, solange es geht."
  - q: "Die Wiedergabe meldet „HUD fehlt für 2 Min.“"
    a: "Das comma hat die Daten der Fahransicht für einen Teil der Aufnahme nicht gespeichert. Die Wiedergabe zeigt über diesem Abschnitt **HUD-Daten nicht verfügbar**, und die Angabe **HUD-Daten** in der Ansicht sagt, wie lange."
  - q: "„Wiedergabe erstellt: 4.860 Bilder. Sie endet früh, wo das comma den Strom verlor.“"
    a: "Das comma hat am Ende der Fahrt den Strom verloren, deshalb wurden ihre letzten Momente nicht gespeichert. „Aufnahmen“ meldet vielleicht **Ihr comma hat am Ende einer Fahrt vielleicht den Strom verloren**; dessen **So beheben Sie es** erklärt die Stromversorgung des comma und die Einstellung für die Zeit im Stand."
related: [live-copy, export-share, live-view]
---

## Wiedergabe, Live-Kopie oder beides

| „Aufnehmen“ erstellt | Was Sie bekommen |
| --- | --- |
| **Wiedergabe** (Standard) | Das eigene Video des comma mit der Fahransicht darüber, erstellt nach dem Parken. Das beste Bild, bis zu 10 Minuten pro Aufnahme, solange das comma die Fahrt noch hat. Nur die Straßen- und die Weitwinkelkamera: In einer Wiedergabe gibt es keine Fahrerkamera. |
| **Live-Kopie** | Was Live View zeigt, während der Fahrt auf Ihrem Handy gespeichert und sofort bereit, wenn Sie anhalten. Keine Wiedergabe zu erstellen und kein Zeitlimit. [Eine Live-Kopie aufnehmen](/de/guides/live-copy). |
| **Beides** | Sofort eine Live-Kopie und nach der Fahrt die Wiedergabe. Die Wiedergabe behält ihr Limit von 10 Minuten. |

## Wo Aufnahmen gespeichert werden

Aufnahmen bleiben auf Ihrem Handy. **Einstellungen › Aufnahmen › Speicher** zeigt den belegten und den freien Speicher, und **Ändern** wählt einen anderen, wenn Ihr Handy einen hat. Die Sicherung von Android und ein Umzug auf ein neues Handy lassen sie aus. **An CommaView senden** sendet nur die eigenen Daten des comma zu einer Fahrt, und nur, wenn Sie sie senden.

## Sicherheit

Starten Sie die Aufnahme, bevor Sie losfahren, und erstellen Sie Wiedergaben nach dem Parken. Bedienen Sie CommaView nicht während der Fahrt: Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt. CommaView ist keine Dashcam und kein Sicherheitssystem, und eine Aufnahme kann scheitern.
