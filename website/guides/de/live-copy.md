---
title: "Eine Live-Kopie von Live View aufnehmen"
description: "Eine Live-Kopie speichert während der Fahrt auf Ihrem Handy, was Live View zeigt, sofort bereit in „Aufnahmen“, wenn Sie anhalten, ohne 10-Minuten-Limit. Nie hochgeladen."
topic: recordings
order: 2
kind: walkthrough
lede: "Eine **Live-Kopie** speichert während der Fahrt auf Ihrem Handy, was Live View zeigt: die Straße und ihre Fahransicht. Sie ist in „Aufnahmen“ bereit, sobald Sie anhalten: keine Wiedergabe zu erstellen und kein 10-Minuten-Limit. Live-Kopien bleiben auf Ihrem Handy und werden nie hochgeladen."
appVersion: "0.0.164"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View funktioniert"
    text: "CommaView auf Ihrem Handy, gekoppelt mit Ihrem comma. Noch nicht? [CommaView einrichten](/de/guides/setup)."
  - title: "Platz auf Ihrem Handy"
    text: "Etwa 1,4 GB pro Stunde bei 720p oder 2,3 GB pro Stunde bei 1080p. Eine Live-Kopie lässt immer 500 MB frei."
howItWorks:
  - title: "Live View"
    text: "Zeichnet wie immer die Straße und die Fahransicht."
    edge: "während der Fahrt"
  - title: "Ihr Handy"
    text: "Kodiert, was Live View zeichnet, als MP4 mit 20 Bildern pro Sekunde."
  - title: "Aufnahmen"
    text: "Die Kopie ist bereit, sobald Sie anhalten."
steps:
  - id: choose
    title: "Live-Kopie oder Beides wählen"
    body: |
      Tippen Sie auf **Einstellungen**, dann auf **Aufnahmen**. Wählen Sie unter **Aufnehmen in Live View**, was „Aufnehmen“ erstellt. Die Wahl gilt sofort.
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Aufnehmen in Live View**: **Wiedergabe**, **Live-Kopie** oder **Beides**."
    tabs:
      - label: "Live-Kopie"
        body: |
          „Was Live View zeigt, sofort bereit, wenn Sie stoppen. Keine Wiedergabe zu erstellen und kein Zeitlimit.“
      - label: "Beides"
        body: |
          „Sofort eine Live-Kopie und nach der Fahrt die Wiedergabe. Die Wiedergabe behält ihr Limit von 10 Minuten.“ Die Wiedergabe wird nach dem Parken erstellt, wie [Eine Fahrt aufnehmen](/de/guides/record) zeigt.
  - id: quality
    title: "Qualität und Ton wählen"
    body: |
      Ist eine Live-Kopie gewählt, ergänzt die Seite ihre Zeilen. **Qualität der Live-Kopie** ist **720p**, bis Sie **1080p** wählen. **Ton** ist aus, wenn Sie kein Mikrofon wählen: das des comma oder das dieses Handys. Es ist derselbe Ton wie unter Einstellungen › Livestream.
    screen: settings-recordings
    pins:
      - text: "**Qualität der Live-Kopie**: 720p (etwa 1,4 GB pro Stunde) oder 1080p (etwa 2,3 GB pro Stunde)."
      - text: "**Ton**: aus, das Mikrofon des comma oder das dieses Handys."
    note: "Eine Live-Kopie zeigt, was Live View zeigt, auch das Bild-im-Bild der Fahrerkamera, solange **Fahrercam** an ist. Schalten Sie „Fahrercam“ in Live View aus, um die Fahrerkamera draußen zu lassen."
  - id: record
    title: "In Live View auf „Aufnehmen“ tippen"
    body: |
      Öffnen Sie bei eingeschaltetem Auto, noch in P, **Live View** und tippen Sie auf **Aufnehmen**. Der Timer läuft, und **Details** meldet **Aufnahme ·** mit der Zeit, wie bei jeder Aufnahme. Tippen Sie erneut auf „Aufnehmen“, um zu stoppen.

      Die Aufnahme läuft weiter, wenn Sie die App wechseln oder das Handy sperren, mit einer Benachrichtigung **Live-Kopie wird aufgenommen**, die ihren Timer und **Stoppen** hat. Wenn Sie Live View schließen, endet sie.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "„Aufnehmen“ mit seinem Timer. Erneut antippen zum Stoppen."
      - target: recording
        text: "**Aufnahme ·** mit der Zeit, in **Details**."
    warn: "Starten Sie die Aufnahme, bevor Sie losfahren, oder überlassen Sie sie einem Beifahrer. Tippen Sie während der Fahrt nicht in CommaView herum."
  - id: find
    title: "In „Aufnahmen“ finden"
    body: |
      Öffnen Sie **Aufnahmen**. Die Kopie ist als **Live-Kopie** markiert, unter dem Tag, mit Länge und Größe. Kurz nach dem Stoppen meldet sie **Live-Kopie wird gespeichert…** mit dem Fortschritt; dann lässt sie sich abspielen.

      Mit **Beides** hat die Fahrt zwei Zeilen: die Live-Kopie und die Wiedergabe, die wartet, bis Sie sie nach dem Parken erstellen.
    screen: phone-recordings
    pins:
      - target: live-copy-row
        text: "Die als **Live-Kopie** markierte Zeile."
      - text: "Mit **Beides** die Wiedergabe der Fahrt, in einer eigenen Zeile."
  - id: watch
    title: "Ansehen, teilen oder löschen"
    body: |
      Tippen Sie auf die Kopie, um sie anzusehen. Ihre Angaben ergänzen **Version** (**Live-Kopie**, oder mit „Beides“ **Live-Kopie · auch eine Wiedergabe**), **Qualität** und **Ton**. **Aktionen für Aufnahmen** enthält **Teilen**, **In anderer App öffnen**, **Auswählen** und **Löschen**.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Aktionen für Aufnahmen**: Teilen, In anderer App öffnen, Auswählen und Löschen."
      - text: "**Vollbild**."
check: "Die Kopie läuft in „Aufnahmen“, sobald sie gespeichert ist, und ihre **Version** meldet **Live-Kopie**."
fixes:
  - q: "„Nicht genug Platz für eine Live-Kopie: Sie lässt immer 500 MB auf diesem Handy frei. Löschen Sie unter Aufnahmen Fahrten, die Sie nicht mehr brauchen.“"
    a: "Löschen Sie Fahrten, die Sie nicht mehr brauchen, oder wählen Sie unter **Einstellungen › Aufnahmen › Speicher** einen anderen Speicher. Die Karte „Speicher“ sagt, wie viele Stunden Live-Kopien ungefähr hineinpassen."
  - q: "„Live-Kopie gestoppt: Dieses Handy ist fast voll. Sie ist unter Aufnahmen gespeichert; sie lässt immer 500 MB frei.“"
    a: "Das Aufgenommene bleibt erhalten. Geben Sie vor der nächsten Fahrt Speicher frei."
  - q: "„Live-Kopie gestoppt: eine Minute kein Video vom comma. Das Aufgenommene ist unter Aufnahmen gespeichert.“"
    a: "Das Handy hat das comma eine Minute lang verloren, deshalb endete die Kopie. Prüfen Sie, ob Ihr Handy im WLAN oder Hotspot des comma bleibt. Siehe [CommaView findet Ihr comma nicht](/de/guides/comma-not-found)."
  - q: "„Diese Live-Kopie hat 3,5 GB erreicht, das Maximum einer Datei: Sie geht unter Aufnahmen in einer neuen weiter.“"
    a: "Nichts geht verloren: Die Fahrt geht in einer zweiten Live-Kopie weiter, mit einer eigenen Zeile in „Aufnahmen“."
  - q: "„Die Wiedergabe hat ihr Limit von 10 Minuten erreicht. Die Live-Kopie nimmt weiter auf.“"
    a: "Mit **Beides** stoppt nur die Wiedergabe nach 10 Minuten. Die Live-Kopie läuft weiter, bis Sie sie stoppen."
  - q: "„Es wird nur eine Live-Kopie aufgenommen. Die Wiedergabe konnte nicht starten: …“"
    a: "Mit **Beides** nimmt die Kopie auf, auch wenn die Wiedergabe es nicht kann, etwa weil das comma einen Neustart braucht oder dieses Handy nicht mit ihm gekoppelt ist. Die Meldung sagt warum."
  - q: "Die Zeile meldet „Braucht 1,2 GB frei zum Speichern“"
    a: "Die Teile der Kopie bleiben erhalten, bis Platz ist, sie zu einem Video zusammenzufügen. Löschen Sie Fahrten, die Sie nicht mehr brauchen, dann wird sie von selbst gespeichert."
  - q: "Ihre Angabe **Gespeichert** meldet „Nach Schließen der App wiederhergestellt: Die letzte Minute fehlt vielleicht“"
    a: "Die App wurde während der Aufnahme geschlossen, deshalb wurde die Kopie aus dem Geschriebenen zusammengesetzt: alles bis auf höchstens die letzte Minute."
  - q: "„CommaView kann nur streamen und aufnehmen, solange es im Vordergrund ist: Android hat es nicht im Hintergrund laufen lassen.“"
    a: "Android hat verhindert, dass CommaView im Hintergrund läuft. Lassen Sie Live View während der Aufnahme auf dem Bildschirm."
related: [record, export-share, go-live]
blogPost: commaview-0-0-164-carrotpilot-teslahw1-live-copies
---

## Live-Kopie oder Wiedergabe

| | Live-Kopie | Wiedergabe |
| --- | --- | --- |
| Was sie zeigt | Was Live View gezeigt hat, so wie es das gezeigt hat | Das eigene Video des comma, mit der Fahransicht darüber |
| Wann sie bereit ist | Sobald Sie anhalten | Nach dem Parken und einem Tippen auf **Wiedergabe erstellen** |
| Wie lang | Kein Limit außer dem Speicher | Bis zu 10 Minuten pro Aufnahme |
| Bild | 720p oder 1080p, 20 Bilder pro Sekunde | Das beste Bild: **Balanced**, **High** oder **Max** |

## Während Sie live sind

Eine Live-Kopie und [Live gehen](/de/guides/go-live) teilen sich einen Encoder. Eine Kopie, die während eines Streams startet, hat die Qualität des Streams. **Jeden Livestream speichern** unter Einstellungen › Aufnahmen behält von jedem „Live gehen“ eine MP4, so wie sie gesendet wurde, ohne „Aufnehmen“.

## Datenschutz

Live-Kopien bleiben auf Ihrem Handy. Sie werden nie hochgeladen und nie mit den anderen gekoppelten Handys des comma geteilt. **An CommaView senden** sendet die eigenen Daten des comma zu einer Fahrt, nie eine Live-Kopie. Ton ist nur in einer Kopie, wenn Sie ein Mikrofon gewählt haben, und die Fahrerkamera nur, solange „Fahrercam“ an ist.

## Sicherheit

Wählen Sie Ihre Einstellungen und starten Sie die Aufnahme im Stand. Bedienen Sie CommaView nicht während der Fahrt: Behalten Sie die Augen auf der Straße und die Hände am Lenkrad, wie openpilot es verlangt.
