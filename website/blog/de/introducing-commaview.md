---
title: "CommaView stellt sich vor: lokales Kamera-Streaming für comma-Geräte"
description: "CommaView ist eine Android-App für lokales Kamera-Streaming vom comma, Einblendungen im MICI-Stil, die Einrichtung der Runtime, Aufnahmen und Wiedergaben von Fahrten."
date: 2026-05-02
slug: introducing-commaview
tags:
  - CommaView
  - comma device camera streaming
  - Android app
  - openpilot tools
heroLabel: "Produktnotizen"
draft: false
---

CommaView gibt es, weil der lokale Zugriff auf die Kamera eines comma sich wie ein echtes Produkt anfühlen sollte, nicht wie ein Haufen Skripte, die an einer SSH-Sitzung kleben.

Das Ziel ist einfach: ein Android-Gerät mit Ihrem comma koppeln, die Straßenkamera lokal streamen, nützliche Einblendungen zur Fahrt zeigen und die Einrichtung im besten Sinne langweilig machen.

## Warum lokal zuerst?

CommaView will kein Cloud-Dashboard sein. Die App spricht über Ihre lokale Verbindung mit Ihrem comma und hält den Kern der Arbeit nah an der Hardware.

Das ist wichtig, weil eine App, die die Kamera des comma lokal streamt, schnell, verständlich und datensparsam bleiben kann. Niemand sollte ein Konto brauchen, nur um zu sehen, was das eigene Gerät sieht.

## Was CommaView übernimmt

Die aktuelle Alpha konzentriert sich auf das, was das Testen im Alltag weniger lästig macht:

- lokales Streaming der Straßenkamera auf Android
- Einblendungen im MICI-Stil für Fahrpfad, Spuren, Status und Fahrerüberwachung
- geführte Einrichtung der Runtime für den Dienst `commaviewd` auf dem comma
- Aufnahmen von Fahrten und Export von Wiedergaben
- passende Versionen von App und Runtime, damit Tester zueinander passende Builds installieren

## Warum zuerst Android?

CommaView gibt es nur für Android, weil Android für diese Arbeit das praktische Ziel ist: Handys, Tablets, Sideloading, lokale Netzwerke und autotaugliche Hardware passen dort besser zusammen.

Dieser Fokus hält die App scharf, statt sie für jede denkbare Plattform zu verwässern.

## Wie es weitergeht

Früher Zugang für Tester hilft, die Installation robuster zu machen, die Kompatibilität der Geräte zu prüfen und die Ausrichtung der Live-Einblendungen für mehr Autos und comma-Setups zu verbessern.

Wenn Sie dabei sein wollen, tragen Sie sich auf der Startseite für den frühen Zugang ein. Im Blog erscheinen Release Notes, Neuigkeiten für Tester und technische Notizen, während CommaView wächst.
