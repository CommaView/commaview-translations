---
title: "CommaView 0.0.165: Live gehen für alle, An CommaView senden und Autoerkennung"
description: "CommaView 0.0.165 bringt Live gehen für alle und An CommaView senden für jedes Mitglied, lässt Mitglieder Fahrten zur Autoerkennung beitragen und läuft auf mehr Forks."
date: 2026-11-01
updatedDate: 2026-11-13
slug: commaview-0-0-165-go-live-send-to-commaview
tags:
  - live streaming
  - YouTube
  - recordings
  - openpilot forks
  - privacy
heroLabel: "Release Notes"
draft: false
---

CommaView 0.0.165 ist für alle in der Beta da. **Live gehen** gibt es jetzt für alle und **An CommaView senden** für jedes Mitglied, für eine Fahrt oder mehrere auf einmal. Mit der neuen Runtime können Mitglieder **Fahrten zur Autoerkennung beitragen**, CommaView installiert jetzt auf **mehr openpilot-Forks**, ohne Gewähr, und die Kameras und Daten Ihres comma gehen **nur an die damit gekoppelten Handys**.

Dazu gehört die Runtime `v0.0.61-beta`. **Aktualisieren Sie zuerst CommaView auf jedem Handy und Infotainment, das Ihr comma ansieht**, dann die Runtime aus der App, wenn sie es anbietet, und starten Sie das comma neu, wenn die App darum bittet. Ein Handy oder Infotainment, das auf 0.0.164 oder älter bleibt, bekommt von einem comma mit Runtime v0.0.61 oder neuer kein Video.

## Live gehen

Live gehen war in 0.0.164 im frühen Zugang. Jetzt gibt es das für alle: **Live gehen** in Live View streamt, was Live View zeigt, die Straße und die Einblendungen von CommaView, auf Ihren YouTube-Kanal oder einen beliebigen RTMP-Server, in 720p oder 1080p.

Richten Sie es einmal unter Einstellungen › Livestream ein: **Mit YouTube anmelden**, das jede Übertragung für Sie anlegt, startet und beendet, oder speichern Sie einen Streamschlüssel oder Server. Live gehen erscheint dann in Live View, oder in dessen Menü **Mehr**, wo der Bildschirm keinen Platz dafür hat.

- **Wer zusehen kann** hat eine eigene Zeile unter Einstellungen › Livestream und steht anfangs auf Nicht gelistet. Wer zusieht, sieht, wo Sie fahren.
- **Ton** ist aus, außer Sie wählen das Mikrofon Ihres comma oder Ihres Handys. Er geht in Ihren Stream und Ihre Live-Kopien, nie an CommaView.
- Hat das WLAN Ihres comma kein Internet, nutzt der Stream die mobilen Daten Ihres Handys. Die Einstellungen sagen ungefähr, wie viel pro Stunde.
- Die Anmeldung bei YouTube und Live gehen funktionieren jetzt auch, wenn ein VPN das Standardnetz Ihres Handys ist.

Die Karte und die Abbiegekarte der Navigation sind nie im Stream.

## An CommaView senden

An CommaView senden gibt es jetzt für jedes Mitglied. Wählen Sie in Aufnahmen eine Fahrt, die Ihr comma aufgenommen hat, oder mehrere, dann **An CommaView senden**, mit einer Notiz dazu, was passiert ist. Wir bekommen von jeder Fahrt das Video der Straßen- und der Weitwinkelkamera und ihr Log, damit wir das Problem sehen können; nie die Fahrerkamera, den Ton oder die Fahrgestellnummer Ihres Autos.

Jede Fahrt wird erst von Ihrem comma heruntergeladen und dann hochgeladen, eine nach der anderen, die älteste zuerst. Lassen Sie das comma also eingeschaltet und geparkt, bis das erledigt ist. CommaView nimmt 20 Uploads pro Tag und Konto an; weitere warten bis zum nächsten Tag.

Dasselbe Fenster **An CommaView senden** trägt jetzt alles, was Sie uns schicken: ein **Problem** oder eine **Idee**, Ihre Notiz und jeden Anhang, den Sie mit **Ansehen** öffnen oder weglassen können. Es öffnet sich aus Einstellungen › Support & Diagnose, aus **Melden** bei jedem Fehler und aus dem Menü Mehr einer Aufnahme.

## Zur Autoerkennung beitragen

Surround, weiterhin im frühen Zugang, lässt einen eigenen Autodetektor auf Ihrem Handy laufen. Mitglieder können jetzt mit ihren Fahrten helfen, ihn zu trainieren. Sie brauchen dafür die neue Runtime auf Ihrem comma.

- **Mit einem Tippen:** **Zur Autoerkennung beitragen** im Menü Mehr einer Fahrt, oder für mehrere ausgewählte Fahrten.
- **Automatisch:** Schalten Sie **Fahrten automatisch beitragen** unter Einstellungen › Datenschutz & Teilen › Autoerkennung ein. Die letzten Fahrten Ihres comma werden hochgeladen, jede, die es noch hat, wenn Ihr Handy und das comma in einem Netz sind, das Sie erlauben, bis zu einem Tageslimit. Nicht im Energiesparmodus und nicht, während Sie Live View nutzen oder aufnehmen.

**Beiträge hochladen über** wählt diese Netze. **Netze, die ich wähle**, die Voreinstellung, listet die mobilen Daten Ihres Handys und die WLAN-Netze, die Ihr comma gespeichert hat; haken Sie die an, die genutzt werden sollen, jedes auf Wunsch mit einem Monatslimit. Beiträge sind etwa 110 MB pro Minute Fahrt. Wenn Ihr comma einem WLAN beitritt, das es noch nicht genutzt hat, fragen Start und eine Benachrichtigung, ob es hinzugefügt werden soll. Ihr comma sagt, in welchem Netz es ist, daher braucht CommaView Ihren Standort nicht.

Wissen Sie, was Sie geben, bevor Sie es geben:

- **Ein Beitrag ist die ganze Fahrt:** das Video der Straßen- und der Weitwinkelkamera und ihr Log, einschließlich der Strecke, vom Anfang bis zum Ende.
- **Er ist endgültig.** Er wird Teil der Trainingsdaten von CommaView und lässt sich später nicht entfernen. Nichts verbindet ihn mit Ihnen oder Ihrem comma.
- **comma connect wartet.** Während eine Fahrt gesendet wird, behält Ihr comma sie bis zu einen Tag, damit openpilot sie nicht löscht, und der Uploader von openpilot überspringt sie so lange.

Die App erklärt das einmal vor Ihrem ersten Beitrag, und Beitragen bleibt aus, bis Sie es einschalten.

## Mehr openpilot-Forks, ohne Gewähr

CommaView installiert jetzt auf mehr openpilot-Forks, ohne Gewähr. Es listet openpilot und sechs seiner Forks und prüft jeden davon vor jedem Release. Auf jedem anderen openpilot-Fork brach die Einrichtung bisher ab. Jetzt prüft sie den Fork, ohne etwas zu ändern, und wenn CommaView seine Ansicht hinzufügen kann, sagt sie „CommaView hat diesen Fork nicht geprüft“: was gezeichnet wird (die Kameras, der Fahrpfad, die Spuren, das Vorderfahrzeug, Warnungen und Geschwindigkeit) und was nicht. **Trotzdem installieren** installiert nur auf diesem Fork.

Live View zeichnet ihn im Look von openpilot, oder von sunnypilot, wenn der Fork auf dem Bildschirm von sunnypilot aufbaut, und nennt ihn, etwa „BluePilotDev/bluepilot · best effort“. **Runtime deinstallieren** in den Einstellungen des Geräts stellt die Dateien des Forks wieder her.

Geprüft im November 2026 bestehen dragonpilot, BluePilot, crwusiz, opgm, zoompilot, Carrot von jixiexiaoge, NotAutopilot und weitere die Installationsprüfung; in keinem Auto getestet. [Die Forks und die geprüften Branches](/de/forks#install-check) stehen auf der Seite der unterstützten Forks.

Zwei Einschränkungen:

- **Ohne Gewähr.** Die Releases von CommaView werden nicht gegen Ihren Fork geprüft. Aktualisiert sich der Fork zu etwas, dem CommaView nicht folgen kann, schaltet sich die Ansicht von CommaView ab, und der Fork fährt wie gewohnt.
- **Der eigene Bildschirm des Forks wird nicht gezeichnet.** Seine Knöpfe, Farben und Widgets erscheinen nicht in Live View, und Forks, die auf dem älteren nativen Bildschirm von openpilot aufbauen, werden gar nicht unterstützt.

## Nur gekoppelte Handys

Mit der neuen Runtime gehen die Kameras und Daten Ihres comma nur an die Handys und Infotainments, die damit gekoppelt sind. Hat ein anderes Gerät die Kamera, sagt Live View „Ein anderes Gerät nutzt die Kamera dieses comma“ und versucht es von selbst erneut.

Auch die Installationen der Runtime erholen sich jetzt. Ein Stromausfall oder Neustart mitten in der Installation stellt das vorherige Release wieder her, eine Installation läuft weiter, wenn die App nicht mehr zuhört, und ein Download, der hängt, macht dort weiter, wo er stehen blieb.

## Außerdem in 0.0.165

- **Mehrere Fahrten auf einmal.** Wählen Sie Fahrten in Aufnahmen, um sie gemeinsam zu teilen, ihre Wiedergaben zu erstellen, sie zu senden oder zu löschen.
- **Live View passt auf jeden Bildschirm.** Seine Bedienelemente scrollen nicht mehr und schneiden **Verlassen** nicht mehr ab: Was nicht passt, kommt in **Mehr**, und größerer Text verschiebt Bedienelemente nach Mehr, statt etwas zu verkleinern. Live View belastet das Handy auch weniger und kommt von selbst wieder in Gang, statt einzufrieren.
- **Ihre Anfragen.** Wenn Sie angemeldet ein Problem melden oder eine Idee senden, können wir antworten. Einstellungen › Support & Diagnose › **Ihre Anfragen** zeigt unsere Antworten, Sie bekommen eine E-Mail, und das Gespräch geht auf my.commaview.com weiter.
- **Einstellungen, neu geordnet.** Datenschutz & Teilen sagt, was Ihr Handy verlässt. **CommaView verbessern helfen** fragt einmal, ob Absturzberichte gesendet werden sollen und welche Fahrsoftware auf Ihrem comma läuft.
- **Die Bestenliste, für jedes Mitglied.** Sie hängt nicht mehr an einem Feature-Flag.
- **Experimentalmodus auf neuerem openpilot.** Auf dem Nightly von openpilot und sunnypilot dev, wo es den Chill-Modus nicht mehr gibt, zeigt Live View den Experimentalmodus so wie openpilot.
- **CommaView unterstützen.** Einstellungen › Support & Diagnose › **CommaView unterstützen** öffnet unsere Seite bei [Buy Me a Coffee](https://buymeacoffee.com/commaview), um Hosting, Tests und die iOS-App mitzufinanzieren. Sie schaltet nichts frei.
- **Korrekturen.** Ein Infotainment mit Android 16 schließt CommaView in Live View nicht mehr, wenn sein Video-Decoder ausfällt, und der comma-3X-Bildschirm von StarPilot zeichnet seine Kamera auf Infotainments, die sie schwarz zeigten.

## Früher Zugang: Navigation und Surround

**Navigation**, **Surround**, **Surround V2** und **Experimentelle Tools** bleiben hinter Feature-Flags bei einer kleinen Gruppe von Testern, während wir Rückmeldungen sammeln.

- **Navigation** zeigt jetzt während einer Fahrt eine Karte in Live View, neben dem Video oder in seiner Ecke, und ohne Fahrt **Wohin?**. Auf der Eckkarte sind Beenden und Stummschalten immer da, Beenden lässt sich 8 Sekunden lang rückgängig machen, und Sie können sagen, wohin es gehen soll.
- **Die Karte der Navigation** hat jetzt einen hellen und einen dunklen Stil, die bei Sonnenaufgang und Sonnenuntergang am Ort Ihres comma wechseln, damit sie auch in der Sonne lesbar ist. Wählen Sie Auto, Wie das Handy, Hell oder Dunkel unter Einstellungen › Karten & Navigation › Kartenstil.
- **Surround V2** ist ein experimenteller zweiter Renderer für Surround, unter Einstellungen › Experimentelle Tools.

Einige davon laufen über kostenpflichtige Dienste, etwa das Routing der Navigation, daher halten wir die Gruppe vorerst klein. Wenn Sie beim Testen helfen möchten, melden Sie sich auf unserem [Discord](https://discord.gg/UuMhz9K8ft), und erzählen Sie uns dann, wie sie sich auf Ihren Fahrten schlagen.

## So aktualisieren Sie

CommaView ist in einer Beta nur mit Einladung. Wenn Sie dabei sind, bietet die App 0.0.165 von selbst an.

1. Aktualisieren Sie CommaView auf **jedem Handy und Infotainment**, das Sie mit Ihrem comma nutzen.
2. Aktualisieren Sie dann die Runtime Ihres comma aus der App.
3. Starten Sie das comma neu, wenn die App darum bittet. Runtime-Updates warten, bis das Auto in P steht und openpilot deaktiviert ist, damit keine Fahrt unterbrochen wird.

Neu bei CommaView? Die [Anleitung zur Einrichtung](/de/guides/setup) führt durch die Installation der App und die Verbindung mit Ihrem comma.

## Weiterlesen

- [Welche openpilot-Forks mit CommaView laufen](/de/forks), und [Forks, die es nicht listet](/de/forks#unlisted)
- [Neuigkeiten](/de/whats-new) in jedem Release
- [Wie Releases von CommaView funktionieren](/de/guides/releases)
- [Datenschutz-Erklärung](/privacy) (auf Englisch): was Live gehen, An CommaView senden und Beiträge teilen

CommaView ist inoffiziell und nicht mit comma.ai, sunnypilot oder einem der openpilot-Forks verbunden, mit denen es läuft. Es ist Beta-Software und kein Sicherheitssystem: Lassen Sie sich davon nie vom Fahren ablenken.

## Korrektur vom 13. November 2026

Unter **Zur Autoerkennung beitragen** stand in diesem Beitrag, dass nichts einen Beitrag mit Ihnen oder Ihrem comma verbindet. Das ging zu weit. Ein Beitrag nennt weder Sie noch Ihr comma, aber die Strecke und das Video einer Fahrt können zeigen, wo Sie fahren. Ab der nächsten App-Version sagt die App das und bittet Sie vor Ihrem nächsten Beitrag erneut um Zustimmung; die [Datenschutz-Erklärung](/privacy) sagte bereits, dass ein Beitrag die Strecke der Fahrt enthält. Der Rest des Beitrags ist so, wie er veröffentlicht wurde.
