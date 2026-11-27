---
title: "CommaView 0.0.164: carrotpilot, SunnyPilot-TeslaHW1 und Live-Kopien"
description: "CommaView 0.0.164 bringt carrotpilot und SunnyPilot-TeslaHW1 sowie Live-Kopien, die speichern, was Live View während der Fahrt zeigt. Dazu früher Zugang zu Navigation und Surround."
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot forks
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - recordings
heroLabel: "Release Notes"
draft: false
---

CommaView 0.0.164 ist für alle in der Beta da. Es bringt zwei weitere openpilot-Forks, **carrotpilot** und **SunnyPilot-TeslaHW1**, damit läuft CommaView jetzt mit sieben: openpilot, sunnypilot, StarPilot, dem openpilot von xnor-tech, AdventurePilot, SunnyPilot-TeslaHW1 und carrotpilot. Außerdem kommen **Live-Kopien**, die speichern, was Live View während der Fahrt zeigt, fertig in dem Moment, in dem Sie anhalten.

Dazu gehört die Runtime `v0.0.60-beta`, die die beiden neuen Forks erkennt. Aktualisieren Sie die Runtime aus der App, wenn sie es anbietet, und starten Sie das comma neu, wenn die App darum bittet.

## SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 ist ein sunnypilot-Fork, der Teslas mit HW1 (Autopilot 1) unterstützt. Sein Bildschirm ist der von sunnypilot, also zeichnet CommaView den Bildschirm von sunnypilot mit allem, was sunnypilot hinzufügt, und nennt den Fork in der App.

Eines sollten Sie wissen: Sein `op fork update` kann den Fork nicht wechseln, solange der Hook von CommaView installiert ist. Deinstallieren Sie CommaView vorher, oder nutzen Sie den Fork-Umschalter auf dem Bildschirm des comma, der wie gewohnt funktioniert.

## carrotpilot

carrotpilot ist ein openpilot-Fork für Hyundai, Kia und Genesis, installiert über `i.carrotpilot.app`. CommaView zeichnet dafür den Bildschirm von openpilot, mit Ihrer Geschwindigkeit, dem Fahrpfad, den Spuren und dem Vorderfahrzeug, und nennt den Fork in der App.

Vorerst zwei Einschränkungen:

- **Der eigene Bildschirm von carrotpilot wird noch nicht gezeichnet.** Was er dem Bildschirm von openpilot hinzufügt, etwa seine Navigation, Blitzer und sein HUD, erscheint nicht in Live View.
- **Seine Updates entfernen den Hook von CommaView bis zum nächsten Neustart des comma.** Das automatische Update von carrotpilot und die Git-Werkzeuge auf seiner Webseite setzen seine Dateien im laufenden Betrieb zurück. Dabei geht nichts kaputt: Die App bittet um einen Neustart, danach ist Live View wieder da.

## Live-Kopien

Bisher erstellte Aufnehmen eine Wiedergabe: Sobald Sie parken, lädt die App das eigene Video des comma herunter und zeichnet das HUD darüber. Das ist weiterhin das beste Bild, braucht nach der Fahrt aber eine Weile und endet nach 10 Minuten pro Aufnahme.

Unter Einstellungen › Aufnahmen › **Aufnehmen in Live View** wählen Sie jetzt, was Aufnehmen erstellt:

| Auswahl | Was Sie bekommen |
| --- | --- |
| Wiedergabe (Standard) | Das eigene Video des comma mit dem HUD darüber, erstellt, nachdem Sie geparkt haben. Das beste Bild, bis zu 10 Minuten pro Aufnahme. |
| Live-Kopie | Was Live View während der Fahrt zeigt, gespeichert auf Ihrem Handy und in Aufnahmen bereit, sobald Sie anhalten, ohne 10-Minuten-Grenze. |
| Beides | Jetzt eine Live-Kopie und nach der Fahrt die Wiedergabe. |

Eine Live-Kopie hat 720p (etwa 1,4 GB pro Stunde) oder 1080p (etwa 2,3 GB pro Stunde), mit 20 Bildern pro Sekunde. Sie läuft weiter, während Sie die App wechseln oder das Handy sperren, mit einer Benachrichtigung, über die Sie sie stoppen können. Sie endet sauber, bevor der Speicher Ihres Handys voll ist, und wenn die App während der Aufnahme schließt, behalten Sie alles bis auf die letzte Minute.

Live-Kopien bleiben auf Ihrem Handy und werden nie hochgeladen.

## Außerdem in 0.0.164

- **Einstellungen, die den ganzen Bildschirm nutzen.** Aufnahmen, Anzeige und Livestream sind aufgebaut wie Offline-Karten, in zwei Spalten, wo sie passen, und richten sich auf Tablets, Infotainment und quer gehaltenen Handys sauber aus.
- **Warum eine Installation fehlschlug.** Schlägt die Einrichtung, ein Runtime-Update oder eine Deinstallation fehl, sagt die App, was schiefging und was zu tun ist: ein Fork, den CommaView nicht unterstützt, ein Auto, das gerade fährt, kein Internet auf dem comma, ein beschädigter Download. Sie sagt, ob Ihr comma auf den alten Stand zurückgesetzt wurde, und **Details kopieren** kopiert den Bericht, den der Support braucht.
- **Schnellere Wiedergaben.** Eine Wiedergabe lädt nur das Video herunter, das sie zeigt, und die nächste Fahrt in der Warteschlange lädt schon, während eine erstellt wird. Eine Aufnahme, die durch das Schließen der App, die 10-Minuten-Grenze oder das Ausschalten des Autos abbrach, lässt sich jetzt ebenfalls zu einer Wiedergabe machen.
- **Die Qualität der Wiedergabe funktioniert wieder.** Balanced, High und Max erstellen wieder unterschiedliche Wiedergaben: Jede Wiedergabe war mit denselben 40 Mbit/s erstellt worden. High, der Standard, erstellt von einem comma 3X jetzt etwa halb so große Dateien.

## Früher Zugang: Navigation und Surround

Einige Funktionen sind in früher Entwicklung: **Navigation**, **Surround**, **Live gehen** und **An CommaView senden**. Wir geben sie hinter Feature-Flags an eine kleine Gruppe von Testern frei, während wir Rückmeldungen sammeln. Sie erscheinen also nur bei Konten, für die sie eingeschaltet sind.

- **Navigation** ist eine Zielführung mit Abbiegehinweisen, von Start bis Live View: Suchen Sie einen Ort, wählen Sie eine Route und folgen Sie dann der Abbiegekarte, den Sprachansagen und, auf dem Bildschirm von CommaView, den Pfeilen auf Ihrer Spur. Nach einer falschen Abzweigung steht in Sekunden eine neue Route. Sie dient nur der Anzeige: Nichts wird an Ihr comma oder Ihr Auto gesendet.
- **Surround** ist eine 3D-Ansicht der Straße rund um Ihr Auto: die Straße, wie die Kamera sie sieht, mit Fahrbahnlinien und Kreuzungen, und die Autos, Lkw und Ampeln um Sie herum.

Einige davon laufen über kostenpflichtige Dienste, etwa das Routing der Navigation, daher halten wir die Gruppe klein, bis wir wissen, was normale Nutzung kostet. Wenn Sie beim Testen helfen möchten, melden Sie sich auf unserem [Discord](https://discord.gg/UuMhz9K8ft), und erzählen Sie uns dann, wie sie sich auf Ihren Fahrten schlagen.

## So bekommen Sie es

CommaView ist in einer Beta nur mit Einladung. Wenn Sie dabei sind, bietet die App das Update auf 0.0.164 von selbst an. Aktualisieren Sie danach die Runtime auf Ihrem comma aus der App heraus und starten Sie das comma neu, wenn sie darum bittet. Runtime-Updates warten, bis das Auto in P steht und openpilot deaktiviert ist, damit keine Fahrt unterbrochen wird.

Neu bei CommaView? Die [Anleitung zur Einrichtung](/de/guides/setup) führt durch die Installation der App und die Verbindung mit Ihrem comma.

## Weiterlesen

- [Welche openpilot-Forks mit CommaView laufen](/de/forks), darunter [SunnyPilot-TeslaHW1](/de/forks#teslahw1) und [carrotpilot](/de/forks#carrotpilot)
- [Neuigkeiten](/de/whats-new) in jedem Release
- [Wie Releases von CommaView funktionieren](/de/guides/releases)

CommaView ist inoffiziell und nicht mit comma.ai, sunnypilot, carrotpilot oder SunnyPilot-TeslaHW1 verbunden. Es ist Beta-Software und kein Sicherheitssystem: Lassen Sie sich davon nie vom Fahren ablenken.
