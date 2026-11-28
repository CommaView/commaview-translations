---
title: "CommaView 0.0.166: ein Schlüssel für jedes Handy, 11 weitere Sprachen und Browser View"
description: "CommaView 0.0.166 gibt jedem Handy einen Schlüssel, spricht 11 weitere Sprachen, zeigt Live View im Browser Ihres Autos, behält Fahrten auf dem Handy und öffnet den Paket-Store."
date: 2026-11-16
slug: commaview-0-0-166-languages-browser-view
tags:
  - security
  - languages
  - browser view
  - recordings
  - overlay packs
heroLabel: "Release Notes"
draft: false
---

CommaView 0.0.166 ist für alle in der Beta da. Mit der neuen Runtime bekommt **jedes Handy einen eigenen Schlüssel** für Ihr comma, und niemand muss neu koppeln. CommaView spricht **11 weitere Sprachen**, zeigt Live View mit **Browser View** im Webbrowser Ihres Autos, behält Ihre Fahrten mit **Diesen Moment speichern**, **Ganze Fahrt exportieren…** und **Fahrten automatisch abrufen** auf Ihrem Handy und öffnet den **Store für Overlay-Pakete**.

Dazu gehört die Runtime `v0.0.62-beta`. **Aktualisieren Sie zuerst CommaView**, dann die Runtime aus der App, wenn sie es anbietet, und starten Sie das comma neu, wenn die App darum bittet. Ein Handy, das noch auf 0.0.165 ist, funktioniert weiter, 90 Tage lang, nachdem das erste Handy Ihres comma seinen Schlüssel bekommen hat. Richten Sie Ihr comma nicht von einem Handy mit 0.0.165 neu ein: Die Einrichtung von dort bringt die alte Runtime zurück, und Handys mit Schlüssel erreichen das comma damit nicht.

## Ein Schlüssel für jedes Handy

Mit der neuen Runtime bekommt jedes Handy einen eigenen Schlüssel für Ihr comma, statt des gemeinsamen Tokens, das bisher jedes Handy sendete. Der Schlüssel geht nie über das Netzwerk, und niemand muss neu koppeln: Ein Handy mit 0.0.166 bekommt seinen Schlüssel, sobald es sich das nächste Mal verbindet.

- **Ein neues Handy hat einen Schlüssel.** Jedes Handy mit Schlüssel erfährt, wenn ein anderes einen bekommt, mit **Es ist meins**, **Entfernen** und **Handys prüfen**, das Einstellungen des Geräts › Weiteres Handy koppeln öffnet, wo jedes Handy mit Schlüssel aufgelistet ist.
- **Ein Handy hinzufügen.** **Einladung zeigen** auf einem Handy mit Schlüssel gibt einen Code oder einen QR-Code, gültig für 10 Minuten.
- **Ältere Apps.** Ihr comma nimmt das alte gemeinsame Token noch 90 Tage an, nachdem sein erstes Handy einen Schlüssel bekommen hat, oder bis jemand auf **Jetzt stoppen** tippt. Bis dahin koppelt **Kopplungscode für eine ältere App** ein Handy mit einer älteren CommaView-Version. Danach braucht ein Handy ohne Schlüssel 0.0.166 und eine Einladung.

## CommaView in Ihrer Sprache

Einstellungen › **Sprache** bietet jetzt neben English auch Deutsch, Español, Français, 日本語, 한국어, Português (Brasil), ไทย, Türkçe, Українська, 简体中文 und 繁體中文. **Sprache des Handys**, die Voreinstellung, nimmt die erste Sprache in der Liste Ihres Handys, die CommaView hat, sonst Englisch, und die Zeile sagt, welche sie gerade nutzt. Ab Android 13 funktioniert auch die Sprache pro App von Android.

Jede Sprache außer Englisch ist **maschinell übersetzt**, und noch kein Muttersprachler hat eine davon geprüft. Rechnen Sie also mit falschen Wörtern und holprigen Sätzen. Eine Karte oben in den Einstellungen sagt das, und **Beim Verbessern helfen** öffnet die Übersetzungen von CommaView, wo jeder ein besseres Wort vorschlagen kann. Sie können es uns auch auf [Discord](https://discord.gg/UuMhz9K8ft) sagen oder über **Problem melden oder Idee senden**: Nennen Sie den Bildschirm und was er jetzt sagt.

- **Die Bildschirme Ihres comma bleiben in der Sprache Ihres comma.** Die Beschriftungen eines Forks und die Warnungen Ihres comma werden so gezeichnet, wie Ihr Auto sie zeigt, jetzt in der eigenen Schrift des Forks, wenn Ihr comma auf Chinesisch, Japanisch, Koreanisch oder Thai eingestellt ist.
- **Der englische Text gilt** für die Einwilligung zur Bestenliste, und **Auf Englisch anzeigen** zeigt ihn. Datenschutz-Erklärung und Nutzungsbedingungen sind auf Englisch.
- **Datumsangaben** folgen der Reihenfolge Ihrer Sprache, und Titel und Beschreibung von Live gehen auf YouTube sind in der Sprache der App, bis Sie sie ändern.
- **Koreanisch** hält Wörter am Zeilenende zusammen. Unter Android 13 und älter kann ein koreanischer Name, den Sie einem comma oder einem Ort gegeben haben, noch umbrechen.

## Browser View

Browser View zeigt, was Live View zeigt, im Webbrowser Ihres Autos, geliefert von Ihrem Handy über seinen Hotspot oder sein WLAN. Starten Sie es über Live View › Details › Browser View, tippen Sie den kurzen Link `commaview.app/<code>` in den Browser des Autos und tippen Sie auf **Öffnen**. In einem Tesla zuerst **VPN-Adresse an**.

Das Bild geht von Ihrem Handy ins Auto, nie über das Internet; nur die Seite des kurzen Links tut das. Wenn Sie angemeldet sind, bekommt Ihr Handy einen eigenen Namen und ein vertrauenswürdiges Zertifikat, sodass ein Tesla ein Schloss und das flüssigere H.264-Bild zeigt. Abgemeldet bekommt ein Tesla das **Einfache Bild**.

- **Bedienung im Auto**: Aufnehmen, Speichern, Karte, die Fahransicht, Live gehen und Fahrercam, neben oder unter dem Bild, nie darüber.
- **Kein Internet im Auto?** **Adressen zeigen** listet die eigenen Adressen des Handys.
- 720p oder 1080p, achtstellige Codes und **Mit Live View starten**, damit es startet, wann immer Live View sich öffnet.

Jeder Schritt, auch für einen Tesla: [Browser View](/de/guides/browser-view).

Während es läuft, sendet Ihr Handy dem Kontodienst von CommaView seinen Code, seine Ports und seine private Adresse, damit der kurze Link es findet. Jeder mit dem Code kann sie sehen, ebenso den `commaview.app`-Namen Ihres Handys, solange Browser View läuft und bis zu 2 Stunden, nachdem es unerwartet endete, aber nichts davon öffnet etwas ohne den Hotspot oder das WLAN Ihres Handys. Sie werden 30 Tage nach dem letzten Lauf von Browser View gelöscht. Der `commaview.app`-Name Ihres Handys und das Datum seines letzten Zertifikats bleiben, solange Ihr Konto besteht, und der Name steht in öffentlichen Zertifikats-Logs. [Die Datenschutz-Erklärung](/privacy) (auf Englisch) hat die Details.

## Ihre Fahrten auf Ihrem Handy

- **Diesen Moment speichern.** **Speichern** in Live View behält die letzten 3 Minuten und die nächste Minute einer Fahrt; ein weiteres Tippen innerhalb dieser Minute fügt eine Minute hinzu, bis zu 10 Minuten. Während der Fahrt wird nichts heruntergeladen: Sobald Sie parken, wird es als MP4 auf Ihr Handy kopiert.
- **Ganze Fahrt exportieren…** Im Menü Mehr einer Fahrt: die Straßenkamera als ein MP4, ab 3,5 GB in Teilen. Das Fenster sagt, wie groß es ist und ob es passt, bevor etwas heruntergeladen wird.
- **Fahrten automatisch abrufen.** Einstellungen › Aufnahmen: Neue Fahrten werden etwa jede halbe Stunde in den WLAN-Netzen, die Sie wählen, nach Hause kopiert, nur über WLAN, bis zu dem Platz, den Sie ihnen geben. Eine Stunde Fahrt sind etwa 4,5 GB.
- **Strom verloren?** Aufnahmen warnt, wenn Ihr comma am Ende einer Fahrt den Strom verloren hat, und sagt, wie Sie das beheben.

All das ist die Straßenkamera ohne HUD und bleibt auf Ihrem Handy, auch nachdem Ihr comma die Fahrt überschrieben hat.

## Overlay-Pakete

Einstellungen › **Overlay-Pakete**, oder die Karte auf Start, öffnet den Store. Pakete fügen Live View hinzu, was Ihr Fork auf seinem eigenen Bildschirm zeichnet, etwa die Hybrid-Anzeigen von BluePilot oder den Regenbogen-Fahrpfad von dragonpilot. Mitglieder stöbern in den Paketen **Offiziell** von CommaView, denen der **Community** und **Für Ihr comma**, jedes mit einer Vorschau für das Design, das Live View zeichnet. **Ihre Pakete** hat einen Schalter für Ihr Handy und jedes gekoppelte comma. Ohne Mitgliedschaft können Sie ein Paket aus einer Datei oder über einen Link hinzufügen.

## Außerdem in 0.0.166

- **Navigation mit Ihrem eigenen Schlüssel für Stadia Maps**, für Mitglieder: Einstellungen › Karten & Navigation › Ihr Schlüssel für Stadia Maps.
- **BluePilot, dragonpilot und OPGM** sind gelistete Forks, mit der neuen Runtime. Mit keinem davon ist bisher jemand mit CommaView gefahren.
- **Live View auf mehr Infotainments**: Wenn der Video-Decoder des Handys das Video des comma nicht abspielen kann, versucht es einen anderen.
- **CommaView von selbst öffnen**, wenn ein Infotainment startet oder Bluetooth sich verbindet, und **Live View bei Verbindung öffnen**, unter Einstellungen › Anzeige. CommaView auf dem eigenen Bildschirm Ihres Autos: [die besten Android-AI-Boxen](/de/blog/android-ai-box-commaview).
- **Mit dem Entwickler meines Forks teilen…**: ein Clip, eine Zusammenfassung und das Log von CommaView, die Sie selbst teilen.
- **Live View sagt, was passiert**: ein Neustart, auf den es wartet, Fahrzeugdaten, die ausgefallen sind, ein verzögertes Bild, warum es sich neu verbindet, ein anderes Gerät, auf dem es offen ist.
- **CommaView aktualisieren**, für Mitglieder, ab 0.0.166: zuerst die Version, **Download abbrechen**, und der Download läuft im Hintergrund weiter.
- **Ränder des Bildschirms**, Ziele für Live gehen für jede Plattform und nichts mehr abgeschnitten bei großem Text.

## Früher Zugang

Live gehen auf X, Twitch, Kick und Facebook, Nur Video für FrogPilot und KisaPilot, die Fork-Einstellungen, das Erstellen von Overlay-Paketen und Surround bleiben hinter Feature-Flags bei einer kleinen Gruppe von Testern. Wenn Sie beim Testen helfen möchten, melden Sie sich auf unserem [Discord](https://discord.gg/UuMhz9K8ft), und erzählen Sie uns dann, wie sie sich auf Ihren Fahrten schlagen.

## So aktualisieren Sie

CommaView ist in einer Beta nur mit Einladung. Wenn Sie dabei sind, bietet die App 0.0.166 von selbst an. Aktualisieren Sie CommaView, dann die Runtime Ihres comma aus der App, und starten Sie das comma neu, wenn sie darum bittet. Aktualisieren Sie jedes Handy und Infotainment, das Ihr comma ansieht, innerhalb von 90 Tagen, nachdem das erste seinen Schlüssel bekommen hat.

## Weiterlesen

- [Welche openpilot-Forks mit CommaView laufen](/de/forks)
- [Neuigkeiten](/de/whats-new) in jedem Release
- [Wie Releases von CommaView funktionieren](/de/guides/releases)

CommaView ist inoffiziell und nicht mit comma.ai, BluePilot, dragonpilot, OPGM oder den anderen genannten Forks verbunden. Es ist Beta-Software und kein Sicherheitssystem: Lassen Sie sich davon nie vom Fahren ablenken.
