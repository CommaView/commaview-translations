---
title: "comma connect oder lokales Video: Was erfüllt Ihren Zweck?"
description: "comma connect, SSH und CommaView nach openpilot 0.11.2 im Vergleich: Livestreams beim Parken, Clips, Aufbewahrung, Videoqualität, Datenschutz und wofür jedes da ist."
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - local video access
  - comma four
  - CommaView
heroLabel: "Entscheidungshilfe"
draft: false
---

comma connect, die eigene Web-App von comma, ist der Ort, an dem die meisten Besitzer ihre Fahrten zuerst ansehen, und für viele Aufgaben ist es der richtige Ort. Seit openpilot 0.11.2 kann es mehr als zuvor: Es kann ein geparktes Auto live streamen und MP4-Clips auf dem Gerät schneiden. Lokaler Zugriff, über SSH oder mit CommaView, erfüllt eine andere Aufgabe: Er holt das Video direkt vom comma, in Ihrem eigenen Netzwerk.

Die kurze Antwort:

- **Eine kürzliche Fahrt, von überall:** comma connect.
- **Nach dem geparkten Auto sehen:** der Livestream von comma connect.
- **Die Straße mit den Einblendungen Ihres Forks während der Fahrt ansehen, auf einem größeren Bildschirm:** Live View von CommaView.
- **Die rohen Kameradateien, für Entwicklung oder Archiv:** SSH.
- **Ein Clip dessen, was Sie gerade gesehen haben, mit Einblendungen, auf Ihrem Handy, ohne Upload:** Aufnehmen in CommaView.

## Was comma connect macht

**Es bewahrt Ihre Fahrten eine Weile in der Cloud auf.** Laut der [prime-Seite](https://comma.ai/prime) von comma werden Aufnahmen „zu connect hochgeladen, wo sie 3 Tage gespeichert werden“. Mit comma prime (24 $ im Monat, nur in den USA, Daten inklusive) oder prime lite (14 $ im Monat, mit eigener SIM, wenn Sie Mobilfunk wollen) behält connect sie ein Jahr.

**Standardmäßig zeigt es das kleine Video.** Laut der [Log-Dokumentation](https://docs.comma.ai/concepts/logs/) von comma stammt das Video in connect aus den qcamera-Dateien, „Versionen der fcamera.hevc in geringerer Auflösung“, die dafür gemacht sind, über eine langsame Verbindung schnell hochzuladen. Die HEVC-Dateien in voller Auflösung bleiben auf dem comma, außer Sie laden sie ebenfalls hoch.

**Seit 0.11.2 kann es ein geparktes Auto live streamen.** Laut dem [Beitrag zu 0.11.2](https://blog.comma.ai/0112release/) (23. Oktober 2026) können Sie mit einer Internetverbindung, „WLAN zu Hause oder LTE von comma prime“, und einem eingebauten comma power „Ihre Straßen- und Fahrerkamera live streamen, um zu sehen, was rund um Ihr Fahrzeug passiert, während es parkt“. Sie sehen es in connect, von überall.

**Es schneidet auch Clips.** Dasselbe Release bringt einen Knopf für Clips in connect: Wählen Sie einen Teil einer Fahrt, und „Ihr comma fügt ihn zusammen und kodiert ihn als weit unterstütztes MP4 (H.264) neu“. Lassen Sie das comma eingeschaltet, während es arbeitet, und laden Sie den Clip dann von connect herunter.

Das ist ein echter Fortschritt. Wenn Sie Ihr geparktes Auto vom Schreibtisch aus sehen oder einem Freund einen Clip der Fahrt von gestern Abend schicken wollen, kann connect jetzt beides.

## Was comma connect nicht macht

- **Es streamt nicht während der Fahrt.** Der Livestream ist für ein geparktes Auto.
- **Es zeichnet die Einblendungen von openpilot nicht.** Livestream und Clips sind Kameravideo, ohne den Fahrpfad, die Spuren, Warnungen oder die Geschwindigkeit, die Sie auf dem Bildschirm des comma sehen.
- **Es braucht das Internet.** Der Livestream braucht Ihr WLAN zu Hause oder das LTE von prime, und Fahrten müssen hochgeladen sein, bevor connect sie zeigen kann.
- **Ohne prime vergisst es nach 3 Tagen.** Danach zeigt connect die Fahrt nicht mehr, auch wenn das comma sie noch hat.

Nichts davon ist ein Mangel. connect ist ein Cloud-Dienst, um Ihr Auto und Ihre Fahrten zu sehen, wo immer Sie sind.

## Was lokaler Zugriff macht

Lokaler Zugriff heißt, das Video vom comma selbst zu holen, im selben Netzwerk, statt von den Servern von comma.

### SSH: die rohen Dateien

Jede openpilot-Fahrt wird auf dem comma in einminütigen Segmenten gespeichert, jedes mit eigenen Dateien: `fcamera.hevc` (Straße), `ecamera.hevc` (Straße, weitwinklig), `dcamera.hevc` (Fahrer), `qcamera.ts` (die kleine Vorschau) und die Logs. Über SSH können Sie jede davon kopieren, solange das comma sie noch hat; es löscht die ältesten Fahrten, wenn der Platz knapp wird. So bekommen Sie Video in voller Auflösung für die Entwicklung oder Ihr eigenes Archiv, aber es sind einminütige HEVC-Dateien, kein Clip, den Sie teilen können. Unsere Anleitung zum [Herunterladen von comma-Aufnahmen](/de/blog/download-comma-dashcam-footage) führt durch die Schritte.

### CommaView: Live View und Aufnahmen auf Android

CommaView ist eine Android-App und eine kleine Runtime auf dem comma, `commaviewd`, die die Kamera und die Fahrdaten über Ihr eigenes lokales Netzwerk an Ihr Handy sendet: Ihr WLAN oder einen Hotspot im Auto, ob von Ihrem Handy, Ihrem Infotainment oder vom comma.

- **Live View, während Sie fahren.** Die Straßenkamera mit dem eigenen Bildschirm Ihres Forks darauf, wie das comma four oder comma 3X ihn zeichnet, oder mit dem eigenen Bildschirm von CommaView, auf einem Handy, einem Tablet am Armaturenbrett oder einem Android-Infotainment. Der Bildschirm des comma four misst 1,9 Zoll; der Ihres Handys ist viel größer.
- **Aufnahmen auf Ihrem Handy.** Tippen Sie in Live View auf Aufnehmen, und sobald Sie parken, lädt CommaView das eigene Video des comma für diesen Abschnitt herunter, bis zu 10 Minuten, und zeichnet den Bildschirm Ihres Forks auf dem Handy darüber. Oder speichern Sie eine Live-Kopie dessen, was Live View zeigt, in 720p oder 1080p, ohne 10-Minuten-Grenze. Spielen Sie sie ab, teilen Sie sie oder öffnen Sie sie in einer anderen App.
- **Live gehen.** Streamen Sie, was Live View zeigt, Straße und Einblendungen, auf Ihren YouTube-Kanal oder einen beliebigen RTMP-Server, in 720p oder 1080p.
- **Kein Abo, kein Upload.** Live View und Aufnahmen gehen von Ihrem comma auf Ihr Handy, und Aufnahmen bleiben dort, bis Sie sie löschen. Die Kameras Ihres comma gehen nur an die damit gekoppelten Handys und Infotainments.

Es läuft mit dem comma 3X und dem comma four, auf openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 und carrotpilot, und auf anderen Forks ohne Gewähr. [Welche Forks, und was Live View auf jedem zeichnet](/de/forks).

## Im direkten Vergleich

| Funktion | comma connect | CommaView |
| --- | --- | --- |
| Live-Video | Straßen- und Fahrerkamera, beim Parken | Straßenkamera, während Sie fahren |
| Einblendungen zur Fahrt | Nein | Der Bildschirm Ihres Forks oder der von CommaView |
| Wohin das Video geht | Über das Internet, angesehen in connect | Ihr eigenes lokales Netzwerk (WLAN oder ein Hotspot), an Ihre gekoppelten Handys |
| Voraussetzungen | Internet, ein comma power für den Livestream | Ein Android-Handy, Tablet oder Infotainment im selben Netzwerk |
| Clips | Jeder Teil einer Fahrt, als MP4 auf dem comma geschnitten und von connect heruntergeladen | Was Sie in Live View aufgenommen haben: eine Wiedergabe von bis zu 10 Minuten oder eine Live-Kopie, mit Einblendungen |
| Wie lange Fahrten bleiben | 3 Tage, mit prime ein Jahr | Auf Ihrem Handy, bis Sie sie löschen |
| Kosten | Kostenlos, oder prime 24 $ / lite 14 $ im Monat | Kein Abo; CommaView ist in einer Beta nur mit Einladung |

## Beides nutzen

Die beiden konkurrieren nicht um dieselbe Aufgabe. Behalten Sie connect, um das Auto von überall zu sehen, und für Fahrten, die Sie in der Cloud haben wollen; nutzen Sie CommaView, um die Straße mit den Einblendungen Ihres Forks auf einem größeren Bildschirm zu sehen, aufzunehmen, was Sie gesehen haben, und es zu streamen. Ein Beifahrer kann Live View während der Fahrt ansehen; wenn Sie allein fahren, behandeln Sie es wie den Bildschirm des comma selbst und behalten Sie die Straße im Blick.

## Weiterlesen

- [comma prime](https://comma.ai/prime), zu den Tarifen von connect und wie lange es Fahrten behält
- [openpilot 0.11.2](https://blog.comma.ai/0112release/), zu Livestream und Clips
- [comma-Aufnahmen herunterladen](/de/blog/download-comma-dashcam-footage), über SSH
- [CommaView einrichten](/de/guides/setup)

CommaView ist inoffiziell und weder mit comma.ai, sunnypilot oder einem der openpilot-Forks, mit denen es läuft, verbunden noch von ihnen empfohlen. Es ist Beta-Software und kein Sicherheitssystem: Lassen Sie sich davon nie vom Fahren ablenken.
