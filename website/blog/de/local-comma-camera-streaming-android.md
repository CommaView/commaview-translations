---
title: "Lokales Streaming der comma-Kamera auf Android: was CommaView macht"
description: "CommaView streamt die Straßenkamera Ihres comma mit ihren Einblendungen über Ihr eigenes Netzwerk auf Android: Live View, Aufnahmen, Live gehen und was es nicht macht."
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma camera streaming
  - comma four
  - Android app
  - CommaView
  - local streaming
heroLabel: "Was es kann"
draft: false
---

CommaView streamt die Straßenkamera Ihres comma, mit ihren Einblendungen zur Fahrt, über Ihr eigenes Netzwerk auf ein Android-Handy, Tablet oder Infotainment. Keine Cloud sitzt zwischen dem comma und Ihrem Handy, und nichts muss erst hochgeladen werden.

Es besteht aus zwei Teilen: der App CommaView und einer kleinen Runtime auf dem comma, `commaviewd`, die der App die Kamera und die Fahrdaten liefert. Die geführte Einrichtung installiert die Runtime und prüft sie.

## Warum überhaupt streamen

Der Bildschirm des comma four misst 1,9 Zoll. Er ist gut für das, was er tut, aber er ist klein, und Besitzer sagen das auch. Die anderen Wege des comma zu Video sind für andere Aufgaben gemacht:

- **comma connect** behält hochgeladene Fahrten 3 Tage lang, mit comma prime ein Jahr ([comma.ai/prime](https://comma.ai/prime)). Seit [openpilot 0.11.2](https://blog.comma.ai/0112release/) kann es die Straßen- und die Fahrerkamera live streamen, während das Auto parkt, über das Internet und mit einem eingebauten comma power, und MP4-Clips auf dem comma schneiden.
- **SSH** gibt Ihnen die rohen einminütigen HEVC-Segmente aus dem Speicher des comma.

Keiner davon zeigt die Straße mit den Einblendungen von openpilot, während Sie fahren. Dafür ist CommaView da.

## Was CommaView macht

### Live View

Die Straßenkamera, live, mit dem eigenen Bildschirm Ihres Forks darauf: dem des comma four, dem des comma 3X oder dem von CommaView, mit Ihrer Geschwindigkeit, MAX, dem Tempolimit, dem Vorderfahrzeug und Spurwechseln in einem Block. Live View zeichnet den Bildschirm jedes Forks mit dem, was dieser Fork hinzufügt, von MADS bei sunnypilot bis zum eigenen HUD von StarPilot. Es läuft mit bis zu 20 Bildern pro Sekunde wie das comma und läuft im Bild-im-Bild weiter.

Auf einem Tablet oder einem Android-Infotainment ordnet sich CommaView wie ein Armaturenbrett an, mit den Bedienelementen von Live View auf der Fahrerseite.

### Aufnahmen

Tippen Sie in Live View auf Aufnehmen, und sobald Sie parken, lädt CommaView das eigene Video des comma für diesen Abschnitt herunter, bis zu 10 Minuten, und zeichnet den Bildschirm Ihres Forks auf Ihrem Handy darüber: eine Wiedergabe. Spielen Sie sie ab, teilen Sie sie oder öffnen Sie sie in einer anderen App. Eine Live-Kopie speichert, was Live View während der Fahrt zeigt, in 720p oder 1080p, fertig in dem Moment, in dem Sie anhalten, ohne 10-Minuten-Grenze. Aufnahmen bleiben auf Ihrem Handy, bis Sie sie löschen.

### Live gehen

Live gehen streamt, was Live View zeigt, die Straße und die Einblendungen von CommaView, auf Ihren YouTube-Kanal oder einen beliebigen RTMP-Server, in 720p oder 1080p. Melden Sie sich einmal mit YouTube an, und es legt jede Übertragung an, startet und beendet sie. Streams starten als Nicht gelistet; wer zusieht, sieht, wo Sie fahren.

### Nur gekoppelte Handys

Die Kameras und Daten Ihres comma gehen nur an die damit gekoppelten Handys und Infotainments. Video, Fahrten und Orte gehen von Ihrem comma an Ihr Handy und nirgendwo sonst hin, es sei denn, Sie senden, streamen oder tragen sie bei.

## Was das Internet braucht

Live View und Aufnahmen nicht: Sie gehen direkt vom comma auf Ihr Handy, im selben lokalen Netzwerk: Ihr WLAN oder ein Hotspot im Auto von Ihrem Handy, Infotainment, Ihrer AI-Box oder dem comma. Die Anmeldung, Updates von App und Runtime, die Karte in Standort des Autos, die Bestenliste, Live gehen und alles, was Sie an CommaView senden, brauchen es.

## Womit es läuft

Mit dem comma 3X und dem comma four, auf openpilot, sunnypilot, StarPilot, dem openpilot von xnor-tech, AdventurePilot, SunnyPilot-TeslaHW1 und carrotpilot. Andere openpilot-Forks laufen ohne Gewähr: Die Einrichtung prüft den Fork und fragt Sie, bevor sie installiert. Das comma 3 wird nicht unterstützt: Es läuft auf einem eingefrorenen openpilot-Release, aus dessen Bildschirm CommaView seine Einblendungen nicht zeichnen kann. [Unterstützte Forks](/de/forks).

Sie brauchen ein Android-Handy, Tablet oder Infotainment mit Android 8 oder neuer.

## Was CommaView nicht ist

- **Nicht comma connect.** Es bewahrt keine Fahrten in einer Cloud auf und zeigt Ihr Auto nicht vom anderen Ende der Stadt. Nutzen Sie dafür connect.
- **Keine Dashcam.** [Nutzen Sie eine eigene Dashcam](/de/blog/is-comma-a-dashcam), wenn Sie beweistaugliche Aufnahmen von Unfällen oder vom Parken brauchen.
- **Keine Fahrhilfe und kein Sicherheitssystem.** Es zeigt, was das comma sieht; maßgeblich ist die Straße.

## Sicher nutzen

Richten Sie CommaView im Stand ein. Ein Beifahrer kann Live View während der Fahrt ansehen; wenn Sie allein fahren, behandeln Sie es wie den Bildschirm des comma selbst und behalten Sie die Straße im Blick.

CommaView ist in einer Beta nur mit Einladung. [Tragen Sie sich in die Liste ein](https://my.commaview.com/join), und wir schreiben Ihnen, wenn Sie an der Reihe sind.

CommaView ist inoffiziell und weder mit comma.ai, sunnypilot oder einem der openpilot-Forks, mit denen es läuft, verbunden noch von ihnen empfohlen. Es ist Beta-Software und kein Sicherheitssystem: Lassen Sie sich davon nie vom Fahren ablenken.
