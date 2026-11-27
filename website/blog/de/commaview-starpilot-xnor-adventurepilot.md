---
title: "CommaView läuft jetzt mit StarPilot, xnor und AdventurePilot"
description: "CommaView 0.0.163 bringt das openpilot von xnor-tech und AdventurePilot, nach StarPilot in 0.0.162. Was jeder openpilot-Fork in Live View auf comma 3X und comma four zeigt."
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "Release Notes"
draft: false
---

CommaView läuft jetzt mit fünf openpilot-Builds: **openpilot**, **sunnypilot**, **StarPilot**, **dem openpilot von xnor-tech** (seinen Builds xnor und rx) und **AdventurePilot**. StarPilot kam mit CommaView 0.0.162, die Beta 0.0.163 bringt xnor und AdventurePilot dazu. Auf jedem davon zeichnet Live View den eigenen Bildschirm des Forks auf Ihrem Android-Handy, Tablet oder Infotainment, mit allem, was dieser Fork hinzufügt.

Bisher brach die Einrichtung auf diesen Forks mit „unsupported upstream remote“ ab. Mit der App 0.0.163 und ihrer Runtime installiert und koppelt sie wie auf openpilot.

## Was jeder Fork in Live View zeigt

CommaView rät nicht anhand des Fork-Namens. Die Runtime auf Ihrem comma sagt der App, was der Bildschirm des Forks hinzufügt, und die App zeichnet es auf dem Bildschirm des comma four, dem des comma 3X oder dem eigenen von CommaView.

| Fork | Was CommaView zeichnet |
| --- | --- |
| openpilot | Die Bildschirme von comma four und comma 3X oder die eigenen Einblendungen von CommaView |
| sunnypilot | Den Bildschirm von sunnypilot: MADS, den Tempolimit-Assistenten, den Regenbogen-Fahrpfad, die Anzeigen für den toten Winkel und seine Ergänzungen für das comma 3X |
| StarPilot | Die Farben, Widgets, Warnungen und die Kamerawahl von StarPilot |
| xnor | Den Bildschirm von openpilot auf den xnor-Builds, den von sunnypilot auf rx und die Lenkrad-Färbung von rx für Rivian |
| AdventurePilot | Den Bildschirm von sunnypilot mit seiner Anzeige für die Spurzentrierung, dem CURVE-Chip und der Färbung für den Lenkmodus |

## StarPilot

StarPilot zeigt seine Fahrmodi über Farben, und CommaView nutzt die Farben, die StarPilot gewählt hat: Rahmen, Fahrpfad und Widgets, die Warnungen und die Kamerawahl, auch die Fahrerkamera. Schalten Sie vorher die StarPilot-Einstellung **Disable Logging** aus: Sie stoppt den Video-Encoder, von dem Live View streamt.

## Das openpilot von xnor-tech: xnor und rx

Das openpilot von xnor-tech gibt es in zwei Builds aus einem Repository. Seine **xnor**-Branches laufen mit dem Bildschirm von openpilot, seine **rx**-Branches mit dem von sunnypilot, jeweils mit den Fahrzeug-Ports von xnor-tech. CommaView erkennt, welcher auf Ihrem comma läuft, und zeichnet diesen Bildschirm, mit den Warnungen so, wie das comma sie schreibt.

Bei einem Rivian mit rx zeigt das Lenkrad, wie das Auto lenkt: grün, solange es über den Winkel lenkt, blau, solange es über das Drehmoment lenkt. CommaView zeichnet dieselben Farben auf das Lenkrad des comma four und auf den Knopf für den Experimentalmodus des comma 3X.

## AdventurePilot

AdventurePilot ist ein sunnypilot-Fork mit eigenen Fahrzeug-Ports. CommaView zeichnet den Bildschirm von sunnypilot mit dem, was AdventurePilot hinzufügt:

- seine **Anzeige für die Spurzentrierung**, eine Pille mit Schub und Versatz auf dem Bildschirm des comma 3X und ein schmaler Balken auf dem des comma four;
- den **CURVE-Chip** auf dem Bildschirm des comma 3X, der blinkt, während die Kurvengeschwindigkeitsregelung eingreift;
- die **Färbung für den Lenkmodus** auf dem Lenkrad und einen Drehmomentbalken, der die Querbeschleunigung zeigt, während ein Rivian über seinen Winkelkanal lenkt.

## So bekommen Sie es

CommaView ist in einer Beta nur mit Einladung. Wenn Sie dabei sind, bietet die App das Update auf 0.0.163 von selbst an. Aktualisieren Sie nach dem App-Update die Runtime auf Ihrem comma aus der App heraus und starten Sie das comma neu, wenn sie darum bittet. Runtime-Updates warten, bis das Auto in P steht und openpilot deaktiviert ist, damit keine Fahrt unterbrochen wird.

Neu bei CommaView? Die [Anleitung zur Einrichtung](/de/guides/setup) führt durch die Installation der App und die Verbindung mit Ihrem comma.

## Was sich nicht geändert hat

- CommaView läuft auf dem **comma 3X** und dem **comma four**. Das comma 3 wird weiterhin nicht unterstützt, auch nicht die comma-3-Builds der Forks wie xnor-c3 ([warum](/de/#faq-comma-3)).
- CommaView ändert nie, wie Ihr Fork fährt. Es legt eine kleine Runtime daneben und einen kleinen Hook in seine Bildschirmoberfläche, damit es denselben Fahrpfad, dieselben Spuren und Warnungen zeichnen kann.
- Auf einem Fork, den CommaView noch nicht unterstützt, bricht die Einrichtung ab und lässt Ihr comma, wie es war. Sie können sich Ihren Fork auf dem Feature-Board unter my.commaview.com wünschen.

## Weiterlesen

- [Welche openpilot-Forks mit CommaView laufen](/de/forks), mit dem, was jeder zeigt
- [Neuigkeiten](/de/whats-new) in jedem Release
- [Wie Releases von CommaView funktionieren](/de/guides/releases)

CommaView ist inoffiziell und nicht mit comma.ai, sunnypilot, StarPilot, xnor-tech oder AdventurePilot verbunden. Es ist Beta-Software und kein Sicherheitssystem: Lassen Sie sich davon nie vom Fahren ablenken.
