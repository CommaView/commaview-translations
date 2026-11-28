---
title: "Ist ein comma eine Dashcam? Nützlich, aber kein Ersatz"
description: "Ein Blick auf comma-Aufnahmen nach openpilot 0.11.2, Sicherheit zuerst: Routendateien, Aufbewahrung und Clips in connect, lokaler Speicher, Unfallaufnahmen, Parkmodus und Dashcams."
date: 2026-11-06
slug: is-comma-a-dashcam
tags:
  - comma dashcam
  - comma device video
  - dashcam footage
  - openpilot
heroLabel: "Dashcam-Realitätscheck"
draft: false
---

Ein comma kann nützliche Aufnahmen der Straße und des Innenraums machen. Das macht es nicht zu einem direkten Ersatz für eine eigene Dashcam.

Die Aufnahmen helfen beim Durchsehen von Routen, beim Debuggen, bei Exporten und um einen Vorfall einzuordnen. Eine eigene Dashcam ist aber auf andere Annahmen hin gebaut: unfallfeste Beweissicherung, einfacher Wechselspeicher, Parkmodus, eine Heckkamera und ein Abrufen, so einfach wie bei einem Haushaltsgerät.

Wenn verlässliche Aufnahmen für einen Unfall oder die Versicherung wichtig sind, betreiben Sie eine eigene Dashcam neben dem comma. Langweilige Antwort, richtige Antwort.

## Was ein comma aufnimmt

openpilot zeichnet Routen auf, solange das Gerät läuft. Die aktuelle Dokumentation zum Logging beschreibt Routen als segmentbasiert, mit Kamera- und Log-Dateien wie:

- `fcamera.hevc` — Video der Straßenkamera
- `ecamera.hevc` — Video der Weitwinkel-Straßenkamera
- `dcamera.hevc` — Video der Fahrer-/Innenraumkamera
- `qcamera.ts` — Vorschauvideo in geringerer Auflösung
- `rlog.zst` — vollständiges Routen-Log
- `qlog.zst` — kleineres Routen-Log

Das sind sehr nützliche Daten.

Es ist aber auch kein einfacher „Dashcam-Clip“. Es ist das Routen-Logging von openpilot: segmentierte Dateien, Routen-IDs, Upload-Verhalten, lokale Aufbewahrung, Codecs, Logs und Werkzeuge.

## Wo Aufnahmen verfügbar sein können

Es gibt zwei große Orte, an denen man zuerst sucht:

1. **comma connect** für kürzliche Fahrten, die in der Cloud sichtbar sind.
2. **Der lokale Speicher des Geräts** für Dateien, die noch auf dem comma liegen.

Laut der [prime-Seite](https://comma.ai/prime) von comma werden hochgeladene Fahrten 3 Tage in connect aufbewahrt, mit comma prime 1 Jahr. Standardmäßig zeigt connect das Video `qcamera` in geringerer Auflösung ([comma-Dokumentation zu Logs](https://docs.comma.ai/concepts/logs/)).

Seit [openpilot 0.11.2](https://blog.comma.ai/0112release/) (Oktober 2026) kann connect auch einen Clip aus einem Teil einer Fahrt schneiden: Das comma kodiert ihn als MP4 neu, solange es eingeschaltet bleibt, und Sie laden ihn von connect herunter. Damit ist ein teilbarer Clip viel leichter zu bekommen als früher.

Der lokale Speicher von openpilot ist etwas anderes. Auf aktueller comma-Hardware liegen die Routendaten praktisch unter `/data/media/0/realdata/`. Aber der lokale Speicher ist nicht unendlich. openpilot räumt auf, wenn der Platz knapp wird, ältere Routen sind also kein dauerhaftes Archiv.

Wenn etwas wichtig ist, sichern Sie es zügig.

## Warum man comma-Aufnahmen trotzdem nutzt

comma-Aufnahmen können wirklich nützlich sein.

Gute Einsatzzwecke sind:

- nachsehen, was auf einer Route passiert ist
- das Verhalten von openpilot debuggen
- Kamera- und Log-Kontext prüfen
- Clips oder rohe HEVC-Dateien exportieren
- Beispiele für Entwicklung oder Support teilen
- Wiedergabe- und Test-Workflows füttern

Wer schon ein comma hat, wäre schlecht beraten, diese Aufnahmen zu ignorieren. Sie sind wertvoll.

Der Fehler ist die Annahme, „wertvoll“ heiße „dieselbe Aufgabe wie eine eigene Dashcam“.

## Warum es keine eigene Dashcam ersetzt

Eine eigene Dashcam ist meist zuerst für die Beweissicherung gebaut.

Das heißt oft: einfacher Speicher, schnelles Abrufen, Parkmodi, Optionen für Heck- oder Innenraumkameras, unabhängiger Betrieb und Abläufe, die darauf ausgelegt sind, Clips nach einem Ereignis zu sichern.

Ein comma ist gebaut, um openpilot laufen zu lassen. Die Kameradaten gibt es, weil openpilot Logging, Modellentwicklung, Debugging, das Durchsehen von Routen und die Vorschau in connect braucht.

Diese Prioritäten überschneiden sich mit dem, was eine Dashcam braucht, aber sie sind nicht dieselben.

## Die Risikobereiche

### Unfälle und Stromausfall

Verliert das Gerät den Strom, wird es beschädigt oder schaltet es im falschen Moment ab, sind die letzten Aufnahmen womöglich schwerer zu retten oder unvollständig.

Das heißt nicht, dass comma-Aufnahmen bei jedem Vorfall nutzlos sind. Es heißt, dass sie nicht Ihr einziger Plan für Beweise sein sollten.

### Parkmodus

Eigene Dashcams verkaufen den Parkmodus mit festem Anschluss oft als Kernfunktion.

Mit openpilot 0.11.2 können Sie die Straßen- und die Fahrerkamera eines geparkten Autos in connect live streamen, mit einer Internetverbindung und einem eingebauten comma power. Der Beitrag von comma beschreibt das als Weg, zu sehen, was rund um das Auto passiert; als Ereignisrekorder für den Parkmodus stellt er es nicht dar.

Betrachten Sie die Überwachung beim Parken als Sache einer eigenen Dashcam, es sei denn, Sie haben ein sehr spezielles, geprüftes Setup und kennen die Risiken.

### Abdeckung nach hinten

Die Straßen-, Weitwinkel- und Fahrer-/Innenraumkameras des comma sind nicht dasselbe wie eine nach hinten gerichtete Dashcam.

Wenn die Sicht nach hinten wichtig ist, nutzen Sie Hardware, die nach hinten aufnimmt.

### Mühe bei Speicher und Export

Eine Dashcam zielt meist auf einfaches Abrufen von Clips über microSD, App oder Display.

Beim comma kann das Abrufen bedeuten: Sichtbarkeitsfenster in connect, manuelles Hochladen, Segment-IDs, SSH/SFTP, HEVC-Dateien, lokales Aufräumen, VLC/ffmpeg/Remuxen oder Hilfswerkzeuge. Die neuen Clips in connect helfen, aber das comma muss eingeschaltet bleiben, während es einen erstellt, und die Fahrt muss noch da sein.

Für technisch versierte Nutzer ist das in Ordnung. So einfach wie ein Haushaltsgerät ist es nicht.

## Wann comma-Aufnahmen genügen können

comma-Aufnahmen können genügen für:

- gelegentliche Aufnahmen der Straße zum Nachschauen
- das Durchsehen von openpilot-Routen
- Debugging und Tests
- Unterstützung bei der Entwicklung
- lokalen Export, solange die Route noch existiert
- das Nachsehen eines Ereignisses kurz danach

Das ist eine starke Liste.

Trotzdem wird das comma damit nicht zu Ihrem einzigen ernsthaften Beweisrekorder.

## Wann eine Dashcam dazukommt

Nutzen Sie eine eigene Dashcam, wenn Ihnen Folgendes wichtig ist:

- verlässliche Aufnahmen für Unfall oder Versicherung
- Überwachung beim Parken
- Sicht nach hinten
- möglichst einfaches Abrufen
- Wechselspeicher
- unabhängige Aufnahme, falls das comma den Strom verliert
- ein einfacheres Werkzeug für Fahrer ohne Technikwissen

Die Kombination ist nicht seltsam. Ein comma kann für openpilot großartig sein, während eine Dashcam die langweilige Beweissicherung übernimmt.

## Wo CommaView dazupasst

CommaView ist eine Android-App und eine kleine Runtime auf dem comma. Es zeigt die Straßenkamera des comma mit den Einblendungen Ihres Forks live auf Ihrem Handy, Tablet oder Android-Infotainment, über Ihr eigenes Netzwerk, und speichert, was Sie aufnehmen, auf Ihrem Handy. Tippen Sie in Live View auf Aufnehmen, und sobald Sie parken, lädt es das eigene Video des comma für diesen Abschnitt herunter, bis zu 10 Minuten, und zeichnet die Einblendungen darüber; oder speichern Sie eine Live-Kopie dessen, was Live View zeigt, ohne 10-Minuten-Grenze. Nichts wird hochgeladen, und Aufnahmen bleiben auf Ihrem Handy, bis Sie sie löschen. Es nimmt auf, wenn Sie auf Aufnehmen tippen, nicht von selbst, und hilft daher nicht bei einem Ereignis, das Sie nicht kommen sahen.

So ist ein Clip dessen, was Sie gesehen haben, viel leichter zu bekommen. Ein comma wird dadurch nicht zu einer sicherheitskritischen Dashcam.

Es garantiert keine Beweissicherung.

Es ist keine Fahrhilfe.

Und es läuft nur mit dem comma 3X und dem comma four, nicht mit dem comma 3. CommaView ist inoffiziell und weder mit comma.ai verbunden noch von comma.ai empfohlen.

## Praktische Checkliste nach einem Vorfall

Keine Rechtsberatung, nur praktische Ersthilfe:

1. Halten Sie an und kümmern Sie sich zuerst um Sicherheit und Notfälle.
2. Verlassen Sie sich nicht allein auf die Aufbewahrung in connect.
3. Sichern und exportieren Sie die betroffenen Routensegmente, sobald es praktisch geht.
4. Wenn Sie connect nutzen, bestimmen Sie die Route und das Zeitfenster, das Sie brauchen.
5. Zeigt connect die Dateien nicht, hat das Gerät sie aber noch, nutzen Sie SSH/SFTP mit Zustimmung des Besitzers oder ein vertrauenswürdiges lokales Werkzeug.
6. Behalten Sie die Originaldateien, wenn möglich.
7. Vermeiden Sie zerstörende Bearbeitungen oder Aufräumen, bis wichtige Aufnahmen kopiert sind.
8. Bei rechtlichen oder Versicherungsfragen sprechen Sie mit den passenden Fachleuten.

Das Wichtigste: zügig handeln, sorgfältig kopieren und nicht annehmen, dass die Aufnahmen ewig warten.

## Die ehrliche Antwort

Ein comma ist eine nützliche Kamera und ein Datenrekorder für openpilot-Routen. Es kann wertvollen Videokontext liefern.

Aber wenn die Frage lautet „Kann ich mir eine Dashcam sparen?“, ist die sichere Antwort: Nein.

Nutzen Sie comma-Aufnahmen zum Durchsehen von Routen, zum Debuggen und für lokale Abläufe. Nutzen Sie eine eigene Dashcam, wenn verlässliche Beweissicherung die Anforderung ist.
