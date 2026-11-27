---
title: "Prüfen, ob Ihr comma und Ihr Fork unterstützt werden"
description: "CommaView funktioniert mit openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot und OPGM, und ohne Gewähr mit anderen Forks."
topic: start
order: 2
kind: reference
lede: "CommaView zeigt die Straßenkamera Ihres comma mit den Fahr-Einblendungen der Software, die darauf läuft. Es funktioniert mit openpilot und neun seiner Forks, auf dem comma 3X und dem comma four, und ohne Gewähr mit anderen openpilot-Forks. Die Einrichtung prüft, welchen Fork Ihr comma nutzt, bevor sie etwas ändert."
updated: 2026-11-27
needs:
  - title: "Ein comma 3X oder comma four"
    text: "Das comma 3 wird nicht unterstützt, auch nicht die comma-3-Builds der Forks wie xnor-c3. [Warum das comma 3 nicht unterstützt wird](/#faq-comma-3)."
  - title: "Ihr Fork, so wie er läuft"
    text: "Installiert und wie gewohnt in Betrieb. CommaView fügt seine Runtime daneben hinzu und ändert nie, wie er fährt."
steps:
  - id: unlisted
    title: "Auf einem Fork, den CommaView nicht listet, fragt die Einrichtung zuerst"
    body: |
      Die geführte Einrichtung prüft, aus welchem Repository die Software Ihres comma installiert wurde, und installiert den Hook von CommaView für diesen Fork. Auf einem Fork, den sie nicht listet, prüft sie den Fork zuerst, ohne etwas zu ändern.
    tabs:
      - label: "Ohne Gewähr"
        body: "Kann CommaView seine Ansicht hinzufügen, zeigt die Einrichtung **CommaView hat diesen Fork nicht geprüft**. Sie nennt den Fork nach seinem Repository und sagt, was gezeichnet wird (Kameras, Pfad, Spuren, Vorderfahrzeug, Hinweise und Tempo) und was nicht (eigene Knöpfe, Farben und Widgets des Forks). **Trotzdem installieren** installiert auf diesem Fork, und nur auf diesem. **Zurück** führt zur Auswahl des comma zurück; nichts wurde installiert."
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**Trotzdem installieren** fügt diesem Fork die Ansicht von CommaView hinzu, ohne Gewähr."
      - label: "Nur Video (früher Zugang)"
        body: "Für FrogPilot und KisaPilot, deren Bildschirme die Ansicht von CommaView nicht aufnehmen können, sehen Tester mit dem Merkmal „Nur Video“ **Nur Video auf diesem Fork**: CommaView streamt die Kameras und zeichnet seine eigene Ansicht aus den Fahrdaten, ohne etwas am Fork zu ändern. Auf einem comma wurde das noch nicht ausprobiert. Ohne das Merkmal sagt die Einrichtung, dass der Fork nicht unterstützt wird, und ändert nichts."
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**Nur Video installieren**."
    note: "Lehnt die Prüfung einen Fork ab, meldet die Einrichtung „CommaView kann seine Ansicht nicht sicher zu … hinzufügen“ und „Auf Ihrem comma wurde nichts geändert.“"
  - id: details
    title: "Sehen, welchen Fork Live View zeichnet"
    body: |
      Öffnen Sie in Live View **Details**. Die Zeile **Software** nennt den Fork Ihres comma, und ein Fork, den CommaView nicht listet, wird nach seinem Repository benannt, etwa „crwusiz/openpilot · ohne Gewähr“.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**Details**, unter dem Bild."
      - text: "**Software**: der Fork, den Ihr comma nutzt."
related: [setup, overlays, uninstall]
---

## Unterstützte Forks

| Fork | Woher er kommt | Unterstützt seit |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | Der ersten Beta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | Der ersten Beta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot, früher github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor** (Builds xnor und rx) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot, installiert von i.carrotpilot.app | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

Auf einem Fork, den sie nicht listet, prüft die Einrichtung, ob CommaView seine Ansicht hinzufügen kann, und fragt Sie zuerst; wo das nicht geht, hält die Einrichtung an und lässt Ihr comma, wie es war.

## Was jeder Fork zeigt

### openpilot

Die eigene Software von comma.ai. Live View zeichnet die Ansicht des comma four, des comma 3X oder die eigenen Einblendungen von CommaView, mit Ihrer Geschwindigkeit, MAX, dem Tempolimit, dem Vorderfahrzeug und Spurwechseln.

### sunnypilot

CommaView zeichnet die Ansicht von sunnypilot mit dem, was sunnypilot hinzufügt: die Zustände „Nur Lenkung“ und „Nur Tempo“ von MADS, den Tempolimit-Assistenten, den Regenbogenpfad und die Anzeigen für den toten Winkel, und auf der Ansicht des comma 3X sein Tempolimit-Schild, Smart Cruise und die Entwickler-Oberfläche. Es liest Ihre sunnypilot-Einstellungen, damit die Ansicht der des comma entspricht.

### StarPilot

StarPilot zeigt seine Fahrmodi über Farben, und CommaView nutzt die Farben, die StarPilot gewählt hat: seinen Rahmen, Pfad und seine Widgets auf den Ansichten comma four und comma 3X, seine Hinweise und seine Kamerawahl, einschließlich der Fahrerkamera.

Schalten Sie die StarPilot-Einstellung **Disable Logging** aus. Sie stoppt den Video-Encoder, von dem Live View streamt.

### openpilot von xnor-tech: xnor und rx

Das openpilot von xnor-tech gibt es in zwei Builds. Seine **xnor**-Branches nutzen die Ansicht von openpilot und seine **rx**-Branches die von sunnypilot, jeweils mit den Fahrzeugportierungen von xnor-tech. CommaView zeichnet, was Ihr comma nutzt, mit seinen Hinweisen so, wie das comma sie schreibt.

Bei einem Rivian mit rx wird das Lenkrad grün, solange das Auto über den Winkel lenkt, und blau, solange es über das Drehmoment lenkt: das Lenkrad des comma four, und auf der Ansicht des comma 3X das der Schaltfläche für den Experimentalmodus.

### AdventurePilot

AdventurePilot ist ein sunnypilot-Fork mit eigenen Fahrzeugportierungen. CommaView zeichnet die Ansicht von sunnypilot mit dem, was AdventurePilot hinzufügt:

- seine Anzeige für die Spurzentrierung: eine Pille mit Schub und Versatz auf der Ansicht des comma 3X, ein kompakter Balken auf der des comma four;
- den Chip CURVE auf der Ansicht des comma 3X, der blinkt, solange die Kurvengeschwindigkeitsregelung eingreift;
- die Färbung des Lenkrads nach Lenkmodus und einen Drehmomentbalken, der die Querbeschleunigung zeigt, solange ein Rivian über seinen Winkelkanal lenkt.

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 ist ein sunnypilot-Fork, der Teslas mit HW1 (Autopilot 1) hinzufügt. Seine Ansicht ist die von sunnypilot, also zeichnet CommaView die Ansicht von sunnypilot mit allem, was sunnypilot hinzufügt, und nennt den Fork in der App.

Sein `op fork update` kann den Fork nicht wechseln, solange der Hook von CommaView installiert ist: [Deinstallieren Sie zuerst die Runtime von CommaView](/de/guides/uninstall), oder nutzen Sie den Fork-Umschalter auf dem Bildschirm des comma, der wie gewohnt funktioniert.

### carrotpilot

carrotpilot ist ein openpilot-Fork für Hyundai, Kia und Genesis, installiert von `i.carrotpilot.app`. CommaView zeichnet dafür die Ansicht von openpilot, mit Ihrer Geschwindigkeit, dem Pfad, den Spuren und dem Vorderfahrzeug. Was carrotpilot seiner eigenen Ansicht hinzufügt, etwa seine Navigation, Blitzer und sein HUD, wird noch nicht gezeichnet.

Das Auto-Update von carrotpilot und die Git-Werkzeuge auf seiner Webseite entfernen den Hook von CommaView bis zum nächsten Neustart des comma. Die App bittet um den Neustart, und danach kommt Live View zurück.

### BluePilot, dragonpilot und OPGM

Gelistet ab CommaView 0.0.166 mit seiner Runtime. CommaView nennt jeden davon und zeichnet ihn im Stil seiner Basis: BluePilot wie sunnypilot, dragonpilot und OPGM wie openpilot, wobei ALKA von dragonpilot als Lenkung gezeigt wird. Ein comma, das einen davon ohne Gewähr nutzte, wechselt beim Hochfahren nach dem Runtime-Update zu ihm. Mit keinem davon ist CommaView schon gefahren. Die offiziellen [Overlay-Pakete](/de/guides/overlays) von CommaView zeichnen mehr von den eigenen Ansichten von BluePilot und dragonpilot.

## Forks, die CommaView nicht listet

Ab CommaView 0.0.165, mit seiner Runtime auf Ihrem comma, kann die Einrichtung die Ansicht von CommaView ohne Gewähr einem openpilot-Fork hinzufügen, den sie nicht listet. Live View zeichnet den Fork im Stil von openpilot, oder von sunnypilot, wenn der Fork auf der Ansicht von sunnypilot aufbaut. Um das rückgängig zu machen, stellt **Runtime deinstallieren** in den Einstellungen des Geräts die Dateien des Forks wieder her, wie sie waren.

- **Ohne Gewähr.** Die Releases von CommaView werden nicht gegen Ihren Fork geprüft. Aktualisiert sich der Fork zu etwas, dem CommaView nicht folgen kann, schaltet sich die Ansicht von CommaView ab, und Ihr Fork fährt und zeigt seine eigene Ansicht wie gewohnt, bis ein CommaView-Release mit der Änderung umgehen kann.
- **Nicht jeder Fork.** Forks auf Basis der älteren nativen Ansicht von openpilot werden nicht unterstützt (siehe unten).
- **Ihr Ja gilt für diesen Fork.** Wechselt Ihr comma zu einem anderen Fork, den CommaView nicht listet, fragt CommaView in der Einrichtung erneut, bevor es dort seine Ansicht hinzufügt.

### Forks, die die Installationsprüfung bestehen (ohne Gewähr)

Jeder davon **besteht die Installationsprüfung von CommaView; ohne Gewähr, nicht in einem Auto getestet.** Geprüft im November 2026, für die genannten Branches, mit der Runtime, die CommaView 0.0.165 installiert: Das Installationsprogramm bietet den Fork an, fügt die Ansicht von CommaView hinzu, sobald Sie zustimmen, und prüft sie, wie es das auf Ihrem comma täte. Nichts davon wurde auf einem comma in einem Auto ausprobiert, ein Fork unterstützt vielleicht nicht jedes Auto auf beiden Geräten, und das nächste Update eines Forks kann die Antwort ändern.

| Fork | Geprüfte Branches | Geräte | Gezeichnet als |
| --- | --- | --- | --- |
| **crwusiz** (github.com/crwusiz/openpilot) | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **jixiexiaoge’s Carrot** (github.com/jixiexiaoge/openpilot) | Carrot | comma four, comma 3X | openpilot |
| **MoreTore** (github.com/MoreTore/openpilot) | release-mici | comma four | openpilot |
| **zoompilot** (github.com/zoompilot/zoompilot) | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato** (github.com/AlexandreSato/openpilot) | master | comma four, comma 3X | openpilot |
| **lukasloetkolben** (github.com/lukasloetkolben/openpilot) | master | comma four, comma 3X | openpilot |
| **mvl-boston** (github.com/mvl-boston/openpilot) | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub** (github.com/mouxangithub/openpilot) | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro** (github.com/programanichiro/openpilot) | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2** (github.com/infiniteCable2/openpilot) | master | comma four, comma 3X | sunnypilot |
| **herizon1054** (github.com/herizon1054/openpilot) | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot** (github.com/NotAutopilot/openpilot) | nap-release, naponsp-alpha | comma four, comma 3X | openpilot (nap-release), sunnypilot (naponsp-alpha) |

Ihr Fork ist nicht dabei? Er funktioniert vielleicht trotzdem: Die Einrichtung prüft ihn, bevor sie etwas ändert.

### Nicht unterstützt

Die Bildschirme dieser Forks können die Ansicht von CommaView nicht aufnehmen. Die Einrichtung sagt das und ändert nichts an Ihrem comma:

- **FrogPilot** (github.com/FrogAi/FrogPilot). Er nutzt die ältere native (Qt-)Ansicht von openpilot, die keinen Platz für die Ansicht von CommaView hat. „Nur Video“ ist im frühen Zugang.
- **KisaPilot** (github.com/kisapilot/openpilot). Seine Python-Ansicht ist abgeschaltet: Er nutzt die ältere native (Qt-)Ansicht von openpilot. „Nur Video“ ist im frühen Zugang.
- **IQ.Pilot** (github.com/IQLvbs/iqpilot). Seit Oktober 2026 läuft er auf seinem eigenen IQ.OS; die Unterstützung wartet, bis CommaView ihn als eigenen Fork unterstützen kann.
- **hikee9123** (github.com/hikee9123/openpilot). Er nutzt die ältere native (Qt-)Ansicht von openpilot.

**Früher Zugang: nur Video für FrogPilot und KisaPilot.** Mit dem Merkmal „Nur Video“ bietet die Einrichtung an, ihre Kameras in Live View mit den eigenen Einblendungen von CommaView statt ihrer eigenen Ansichten abzuspielen, ohne etwas am Fork zu ändern. Auf einem comma wurde das noch nicht ausprobiert. Ohne das Merkmal sagt die Einrichtung weiterhin, dass sie nicht unterstützt werden, und ändert nichts.

## Welche comma-Geräte

Das comma 3X und das comma four. Das comma 3 wird nicht unterstützt, auch nicht die comma-3-Builds der Forks wie xnor-c3: [warum das comma 3 nicht unterstützt wird](/#faq-comma-3). Die App läuft auf einem Android-Handy, -Tablet oder -Infotainment.

## Release- und Entwicklungs-Branches

Vor jedem Release wird die Runtime von CommaView gegen die Release-Builds dieser Forks gebaut und geprüft. Der Nightly-Branch von openpilot und der Dev-Branch von sunnypilot werden an jedem Tag geprüft, an dem sie sich ändern, als Frühwarnung. Ein Entwicklungs-Branch kann sich schneller ändern als CommaView: Hindert eine Änderung den Hook von CommaView am Laden, laufen Ansicht und Fahren Ihres Forks wie gewohnt weiter.

## Ihr Fork ist nicht gelistet?

Probieren Sie ihn ohne Gewähr aus, und wünschen Sie sich auf dem Feature-Board unter [my.commaview.com](https://my.commaview.com), dass er gelistet wird, oder senden Sie eine Idee aus der App (Einstellungen › **Support & Diagnose**). Ein gelisteter Fork wird vor jedem Release geprüft. Siehe [Neuigkeiten](/whats-new) zu jedem Release.

## Fragen

**Ändert CommaView, wie mein Fork fährt?** Nein. Es fügt neben Ihrem Fork eine kleine Runtime hinzu und einen kleinen Hook in seine Bildschirmoberfläche, damit CommaView denselben Pfad, dieselben Spuren und Hinweise zeichnen kann. Wie Ihr Auto fährt, ändert sich nicht.

**Funktioniert CommaView mit StarPilot?** Ja, ab CommaView 0.0.162. Live View zeigt die eigenen Farben, Widgets und die Kamerawahl von StarPilot. Schalten Sie die StarPilot-Einstellung **Disable Logging** aus, die den Video-Encoder stoppt, von dem CommaView streamt.

**Funktioniert CommaView mit carrotpilot?** Ja, ab CommaView 0.0.164. Live View zeichnet dafür die Ansicht von openpilot; was carrotpilot seiner eigenen Ansicht hinzufügt, etwa seine Navigation und Blitzer, wird noch nicht gezeichnet. Nachdem carrotpilot sich selbst aktualisiert hat, bittet die App um einen Neustart, der Live View zurückbringt.

**Funktioniert CommaView mit FrogPilot?** Noch nicht: Er nutzt die ältere native (Qt-)Ansicht von openpilot, die keinen Platz für die Ansicht von CommaView hat, deshalb sagt die Einrichtung, dass er nicht unterstützt wird, und ändert nichts. „Nur Video“ ist für FrogPilot und KisaPilot im frühen Zugang, für Tester.
