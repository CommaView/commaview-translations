---
title: "So laden Sie Dashcam-Aufnahmen von einem comma herunter"
description: "Ein praktischer Leitfaden zu den Videodateien des comma, den Unterschieden zwischen comma 3, 3X und four und den sichersten Wegen, Routenaufnahmen zu exportieren."
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma device video
  - dashcam footage
  - openpilot tools
  - SSH
heroLabel: "comma-Leitfaden"
draft: false
---

Sie wollen Video von einem comma holen? Die üblichen Wege sind comma connect, Openpilot Toolkit oder direkter Zugriff über SSH/SFTP.

Was viele stolpern lässt, ist der Aufbau der Dateien. comma-Geräte zeichnen openpilot-Routen in kurzen Segmenten auf, nicht als einen riesigen Dashcam-Clip. Jedes Segment kann rohe Kameradateien, ein Vorschauvideo und Routen-Logs enthalten. Sobald das klar ist, wird der Export viel weniger rätselhaft.

Ein wichtiger Hinweis vorab: Ein comma kann nützlich sein für Aufnahmen der Straße, fürs Debuggen und zum Durchsehen von Routen, aber es ist kein direkter Ersatz für eine eigene Dashcam.

## comma-Geräte sind nützliche Kameras, keine perfekten Dashcams

Eine eigene Dashcam ist für die Beweissicherung gebaut: schneller Start, Unfallfestigkeit, Parkmodus, einfacher Dateiexport, Optionen für eine Heckkamera und Wechselspeicher.

Ein comma ist gebaut, um openpilot laufen zu lassen. Es zeichnet Routendaten auf, weil sie für Fahrmodelle, Debugging, die Vorschau in connect und die Entwicklung nützlich sind. Diese Aufnahmen können wertvoll sein, haben aber ihre Haken:

- Aufnahmen können schwerer zu holen sein, als eine SD-Karte herauszuziehen
- ein Unfall oder ein plötzlicher Stromausfall kann die letzten Aufnahmen kosten
- Aufnehmen im Parkmodus ist nicht das Hauptziel der Konstruktion
- eine nach hinten gerichtete Dashcam ist nicht dabei
- alte lokale Daten werden gelöscht, wenn das Gerät Platz braucht

Wenn verlässliche Unfallaufnahmen das Ziel sind, nutzen Sie eine echte Dashcam. Wenn es um openpilot-Routen, das Durchsehen für die Entwicklung oder lokalen Videoexport geht, lohnt es sich, den Weg mit dem comma zu lernen.

## Welche Dateien zeichnet openpilot auf?

Die offizielle Dokumentation zum Logging von openpilot beschreibt Routen als einminütige Segmente. Für jedes Segment zeichnet ein aktuelles openpilot diese Dateitypen auf:

| Datei | Was sie enthält |
| --- | --- |
| `fcamera.hevc` | Video der Straßenkamera, H.265/HEVC |
| `ecamera.hevc` | Video der Weitwinkel-Straßenkamera, H.265/HEVC |
| `dcamera.hevc` | Video der Fahrer-/Innenraumkamera, H.265/HEVC |
| `qcamera.ts` | H.264-Vorschau der Straßenkamera in geringerer Auflösung |
| `rlog.zst` | vollständige Routen-Logs |
| `qlog.zst` | kleinere, ausgedünnte Routen-Logs |

Das Video in comma connect ist das `qcamera.ts` in geringerer Auflösung. Kameraaufnahmen in voller Auflösung liegen in den HEVC-Dateien und müssen eventuell manuell über connect hochgeladen oder direkt vom Gerät kopiert werden.

Ältere Routen, ältere Forks oder ältere Dokumentation zeigen womöglich `rlog`/`qlog` ohne `.zst` oder ältere Log-Namen mit `.bz2`. Für ein aktuelles openpilot gelten die Namen oben.

## comma 3, comma 3X und comma four: Was ändert sich?

Zwei verschiedene Dinge werden oft vermischt: die Kamera-Hardware und der Aufbau der Dateien.

Die Kamera-Hardware unterscheidet sich je nach Generation:

| Gerät | Hinweise zu Kamera und Speicher |
| --- | --- |
| comma 3 | Drei 1080p-Kameras mit 120 dB HDR. Die Community-Dokumentation nennt mehrere Speichervarianten: 1 TB, 250 GB, späte 64 GB und frühe 32 GB. |
| comma 3X | Dieselbe Anordnung mit drei Kameras wie das comma 3, verbesserte Bildsensoren OX03C10, 140 dB HDR und meist mit 128 GB Speicher angegeben. |
| comma four | Laut comma hat es dieselbe Rechenleistung, dieselben Sensoren und dieselben Funktionen wie das comma 3X, aber in einem viel kleineren Gehäuse. Das System mit drei Kameras passt in die Fläche des 1,9-Zoll-Displays, mit zwei Kameras zur Straße und einer Innenraumkamera mit Nachtsicht. comma gibt 128 GB Speicher und 10 Stunden Aufnahmen an. |

Die Hinweise zu den Dateien hier gelten für alle drei. CommaView selbst läuft nur mit dem comma 3X und dem comma four.

Bei einem aktuellen openpilot ist der Aufbau der Dateien auf aller comma-Hardware praktisch gleich. Die aktuellen Segmentdateien sind `fcamera.hevc`, `ecamera.hevc`, `dcamera.hevc`, `qcamera.ts`, `rlog.zst` und `qlog.zst`.

Die Kameras können sich also physisch ändern, während die Namen beim Export vertraut bleiben. `fcamera.hevc` ist die Straßenkamera. `ecamera.hevc` ist die Weitwinkel-Straßenkamera. `dcamera.hevc` ist die Fahrer-/Innenraumkamera.

Wenn Sie einen eigenen Fork nutzen, prüfen Sie auf dem Gerät nach, bevor Sie annehmen, dass jede Datei vorhanden ist. Forks können die Aufnahme-Einstellungen ändern, und die Aufnahme der Fahrer-/Innenraumkamera kann von Einstellungen des Geräts abhängen.

## Wo liegen die Dateien lokal?

Auf comma-Hardware ist das aktuelle Log-Verzeichnis von openpilot:

```text
/data/media/0/realdata
```

In diesem Ordner bekommt jedes Routensegment einen eigenen Ordner mit Zeitstempel, zum Beispiel:

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

In diesem Ordner finden Sie Dateien wie:

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

Für direkten Zugriff über SSH/SFTP ist das der Ordner, mit dem Sie beginnen. Die offizielle Dokumentation erklärt, wie Sie sich über SSH mit einem comma 3X oder comma four verbinden, und openpilot nutzt `/data/media/0/realdata` als Log-Verzeichnis auf dem Gerät.

## Weg 1: comma connect nutzen

Für kürzliche Fahrten ist comma connect meist der einfachste Anfang.

Nutzen Sie connect, wenn:

- die Route neu ist
- das Gerät die Route erfolgreich hochgeladen hat
- das Vorschauvideo genügt
- Sie eine Weboberfläche statt SSH wollen
- Sie nur ein paar Clips oder Dateien brauchen

In connect finden viele Nutzer auch zuerst die Route und die Segmentnummern, die sie brauchen. Der Haken ist die Aufbewahrung: connect zeigt eine Route womöglich nicht mehr, bevor das Gerät sie lokal gelöscht hat. Zeigt connect eine Route nicht mehr, liegen die Dateien aber noch auf dem Gerät, lassen sie sich womöglich noch über SSH/SFTP retten.

Denken Sie auch daran, dass die Vorschau in connect auf `qcamera.ts` beruht. Wenn Sie Kameraaufnahmen in voller Auflösung brauchen, stellen Sie sicher, dass die vollständigen Videodateien hochgeladen sind, oder holen Sie die rohen HEVC-Dateien direkt.

## Weg 2: Openpilot Toolkit nutzen

Openpilot Toolkit ist ein Werkzeug aus der Community, das den lokalen Export weniger mühsam machen kann. Es hilft beim Einrichten von SSH, beim Durchsuchen von Dateien, bei der Vorschau von Fahrtvideos und beim Rohexport.

Nutzen Sie Openpilot Toolkit, wenn:

- Sie eine grafische Oberfläche wollen
- Sie SSH-Befehle nicht selbst schreiben wollen
- Sie Hilfe beim Einrichten der Schlüssel brauchen
- Sie Windows oder Android nutzen
- Sie Routenaufnahmen direkter durchsuchen und exportieren wollen

Für viele ist das der beste Mittelweg: mehr Kontrolle als connect, weniger Mühe als Handarbeit im Terminal.

## Weg 3: SSH oder SFTP direkt nutzen

Direkter Zugriff über SSH/SFTP gibt die meiste Kontrolle und die wenigste Anleitung.

Grob gesagt bedeutet SSH-Zugriff meist:

1. Ein GitHub-Konto mit SSH-Schlüsseln anlegen oder nutzen.
2. SSH in den Einstellungen des comma einschalten.
3. Ihren GitHub-Benutzernamen auf dem comma eingeben, damit es Ihre öffentlichen Schlüssel holen kann.
4. Als Benutzer `comma` auf Port `22` verbinden.

Nach dem Verbinden durchsuchen oder kopieren Sie aus:

```text
/data/media/0/realdata
```

Nutzen Sie den direkten Zugriff, wenn:

- Sie die rohen Dateien `fcamera.hevc`, `ecamera.hevc` oder `dcamera.hevc` brauchen
- connect die Datei, die Sie brauchen, nicht zeigt
- Sie eine ganze Route archivieren wollen
- Sie mit SFTP-Clients wie FileZilla oder WinSCP vertraut sind
- Sie mit `ssh`, `scp` oder `rsync` vertraut sind

Rohe `.hevc`-Dateien spielt VLC oft ab. Braucht eine andere App MP4, remuxen Sie mit ffmpeg, statt neu zu kodieren, wenn das geht.

## Welchen Weg sollten Sie nehmen?

Nehmen Sie comma connect, wenn die Fahrt neu ist und normales Durchsehen der Route genügt.

Nehmen Sie Openpilot Toolkit, wenn Sie einen freundlicheren lokalen Weg wollen, ohne jeden Schritt mit SSH/SFTP von Hand zu machen.

Nehmen Sie SSH oder SFTP, wenn Sie rohe Dateien, ältere lokale Dateien, vollständige Routenarchive oder direkte Kontrolle darüber brauchen, was kopiert wird.

## Wo CommaView dazupasst

CommaView ist eine Android-App, die lokal zuerst arbeitet: Kamera-Streaming vom comma, Einblendungen, Einrichtung der Runtime, Aufnahmen und Wiedergaben.

Das berührt dieselbe Welt des lokalen Kamerazugriffs, aber es ist nicht comma connect, nicht Openpilot Toolkit und keine klassische Dashcam. Es sollte weder als Fahrhilfe noch als einziges System zur Beweissicherung in einem Fahrzeug dienen.

CommaView läuft mit dem comma 3X und dem comma four, mit openpilot oder einem [unterstützten Fork](/de/forks): sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 oder carrotpilot. Das comma 3 wird nicht unterstützt: comma hat es auf ein eingefrorenes openpilot-Release mit Langzeitpflege gesetzt, aus dessen Bildschirm CommaView seine Einblendungen nicht zeichnen kann ([warum](/de/#faq-comma-3)).

## Weiterlesen

- Offizielle Dokumentation zum Logging von openpilot (auf Englisch): [Logging](https://docs.comma.ai/concepts/logs/)
- Offizielle SSH-Dokumentation von comma (auf Englisch): [Mit einem comma 3X oder comma four verbinden](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect: [comma.ai/connect](https://comma.ai/connect)
- openpilot-Wiki: [Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma: [Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit: [Projektseite](https://spektor56.github.io/OpenpilotToolkit/)
