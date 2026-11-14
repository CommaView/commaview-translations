# Deutsch glossary

The words every German string uses for CommaView's terms, so screens translated apart say the same thing. Where
openpilot already translates a term (`selfdrive/ui/translations/app_de.po`, taken from the `v0.10.1` tag since
master no longer has it; its older Qt `main_de.ts` where the .po has none), its word is used, so the app says what
the car's screen says. Machine drafted; a native speaker's review is owed before release
(the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **SSH**, **QR**,
**Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`).

One exception: **Wi‑Fi** is **WLAN**, as openpilot's German, Android's German and every German phone say it.

## Style

- Address the person as **Sie** (Ihr, Ihnen), as openpilot's current translation does ("Sind Sie sicher …",
  "Ihr Gerät"). Its older Qt translation said du; the .po replaced it.
- Short, common words first: screens are checked at 200% text on a 360 dp phone, where a row's title holds about 15
  letters and a narrow one (a row's subtitle, a rail's button) 11 or 12. A compound longer than that on a button,
  pill, title or label is said in two or more words (`Standort des Autos`, not `Fahrzeugstandort`; `Kontrast bei
  Tageslicht`, not `Tageslicht-Kontrast`; `Tempo aktiv`, not `Geschwindigkeitsregelung aktiv`) or as a shorter word
  (`Bildausschnitt`, `Fahrercam`). A hyphen doesn't help: Android doesn't break a line after one in the app's text,
  nor at a soft hyphen (`&#173;`), so the whole compound, hyphens and all, must fit its line
  ([how-to-localize](../CONTRIBUTING.md#a-word-too-long-for-its-line)). Soft hyphens aren't used.
  English loanwords take a hyphen to a German noun (`Live-Kopie`, `SSH-Schlüssel`, `WLAN-Netz`).
- Buttons are infinitives or short nouns, as Android's and openpilot's German: Abbrechen, Fertig, Speichern,
  Löschen, Erneut versuchen, Weiter, Öffnen, Schließen, Aktivieren, Deaktivieren.
- No full stop on titles, buttons, row titles or pills; whole sentences in body text end with one.
- Quotes are „…“ (nested ‚…‘). Ellipsis stays …. A space between a number and its unit (`25,7 GB`), as the
  formatters give it; numbers come formatted from the locale.
- Nouns are capitalised as German requires; otherwise sentence case, never English title case.

## Terms

| English | Deutsch | Note |
|---|---|---|
| Home (dock) | Start | |
| Recordings | Aufnahmen | the section and its saved drives |
| Settings | Einstellungen | |
| recording, a recording | Aufnahme | |
| drive (a trip the comma recorded) | Fahrt | |
| replay | Wiedergabe | |
| live copy | Live-Kopie | |
| saved moment | gespeicherter Moment | |
| Record | Aufnehmen | the rail's button |
| Go live / live streaming | Livestream | |
| onroad screen | Fahransicht | |
| onroad / offroad (the comma's state) | unterwegs / geparkt | |
| design (an onroad screen's look) | Design | |
| overlay pack | Overlay-Paket | |
| fork | Fork | openpilot's own jargon; kept |
| runtime (commaviewd) | Runtime | the developers' word in German too |
| update / install / uninstall | Update / installieren / deinstallieren | openpilot's |
| reboot | Neustart / neu starten | openpilot's |
| power off | Ausschalten | openpilot's |
| pair / pairing | koppeln / Kopplung | openpilot's |
| device (the comma) | Gerät | openpilot's |
| this phone / this device (the device CommaView runs on) | Handy / Gerät (mid-sentence); Dieses Handy / Dieses Gerät (`_start`) | both neuter, so every article agrees: the sentence writes "dieses %1$s" or "auf diesem %1$s" itself; a `_start` slot opens its sentence as the subject; no genitive (write "von diesem %1$s"). openpilot says Telefon; Handy is the everyday word. `common_this_*`, how-to-localize.md, "This phone or this device" |
| your phone / your device (the device CommaView runs on) | Handy / Gerät (mid-sentence); Ihr Handy / Ihr Gerät (`_start`) | `common_your_*`: the sentence writes "Ihr %1$s" or "Ihrem %1$s" itself, as it writes "dieses" for this phone |
| connected / disconnected | verbunden / getrennt | |
| Device settings (the comma's page) | Einstellungen des Geräts | two words, to fit its title and button at 2× text |
| Stadia Maps key | Schlüssel für Stadia Maps | |
| offline | offline | openpilot's |
| engaged / disengaged | aktiv / deaktiviert | openpilot says deaktivieren for disengaging |
| override | Fahrereingriff | |
| experimental mode | Experimentalmodus | openpilot's |
| driver monitoring | Fahrerüberwachung | openpilot's |
| driver camera | Fahrerkamera | openpilot's; Live View's control "Driver cam" is **Fahrercam** (fits the rail at 2× text) |
| road camera / wide camera | Straßenkamera / Weitwinkelkamera | |
| lead car | Vorderfahrzeug | |
| speed limit | Tempolimit | |
| set speed / MAX | Sollgeschwindigkeit / MAX | openpilot's MAX |
| lane change | Spurwechsel | |
| calibration | Kalibrierung | openpilot's |
| driver position (left/right-hand drive) | Fahrerseite (Linkslenker / Rechtslenker) | |
| daylight contrast | Tageslicht-Kontrast | |
| offline maps | Offline-Karten | |
| navigation | Navigation | |
| Home / Work (places) | Zuhause / Arbeit | |
| vehicle location | Standort des Autos | two words, to fit a card's title at 2× text (openpilot says Fahrzeug) |
| account / sign in / sign out | Konto / Anmelden / Abmelden | openpilot's comma-Konto |
| leaderboard | Bestenliste | |
| achievement | Erfolg | |
| privacy | Datenschutz | privacy policy: Datenschutz-Erklärung (hyphenated for narrow screens); terms: Nutzungsbedingungen, on buttons Bedingungen |
| diagnostics | Diagnose | |
| report a problem | Problem melden | |
| Details (Live View's pane) | Details | |
| stream health | Stream-Zustand | |
| storage | Speicher | |
| hotspot | Hotspot | openpilot says Tethering for the setting; Hotspot is the phone's word |
| Live / Delayed (Live View's state) | Live / Verzögert | |
| frame pacing | Bildtakt | |
| inset (a picture in the picture) | Bild-im-Bild | |
| framing: Fill / Exact / Extend / Auto | Füllen / Exakt / Erweitert / Auto | |
| camera framing | Kamera-Ausschnitt | |
| reduce motion | Bewegung reduzieren | |
| screen edges | Bildschirmränder | |
| View (Surround's) / chase / high / top-down | Ansicht / Verfolgen / Hoch / Von oben | |
| vehicle detection / detector / model | Fahrzeugerkennung / Detektor / Erkennungsmodell | |
| renderer | Renderer | |
| key (an API key, an SSH key) | Schlüssel | SSH-Schlüssel (openpilot's), API-Schlüssel; public / private: öffentlich / privat |
| dashboard (a service's) | Dashboard | |
| reroute | Neu berechnen | |
| Where to? | Wohin? | |
| map source | Kartenquelle | |
| Powered by | Bereitgestellt von | |
| steering / speed active, manual (the HUD's control line) | Lenkung aktiv / Tempo aktiv / Manuell | review on a drive |
| steering only / speed only | Nur Lenkung / Nur Tempo | |
| blind spot | toter Winkel | |
| green light / lead car moving | Grün / Vorderfahrzeug fährt an | |
| safe update / install / repair | sicheres Update / sichere Installation / sichere Reparatur | |
| overlays (drawn on video) | Einblendungen | not overlay packs (Overlay-Paket) |
| telemetry | Telemetrie | |
| patch | Patch | |
| in Park | in P | |
| power harness | Dauerstrom-Kabel | |
| guided / manual setup | Geführte / Manuelle Einrichtung | openpilot's Einrichtung |
| boot hook / runtime hook | Boot-Hook / Runtime-Hook | |
| vehicle security key | Sicherheits-Schlüssel des Autos | hyphenated: a 20-letter word breaks at 200% text |
| pair code / invitation | Kopplungscode / Einladung | |
| phones with a key | Handys mit Schlüssel | |
| shared token | gemeinsames Token | |
| development runtime | Entwicklungs-Runtime | |
| controller | Controller | |
| best effort | ohne Gewähr | |
| video only | Nur Video | |
| widgets | Widgets | |
| backup / restore | Sicherung / Wiederherstellen | |
| read-only | schreibgeschützt | |
| head unit | Infotainment | the car's own screen |
| nearby devices | Geräte in der Nähe | Android's permission |
| display over other apps | Über anderen Apps einblenden | Android's permission |
| set aside (saved lists) | zurückgelegt | |
| Not now / Review | Später / Ansehen | openpilot's REVIEW is ANSEHEN |
| queue | Warteschlange | |
| Needs processing | Verarbeitung nötig | |
| pull drives | Fahrten abrufen | |
| whole drive | ganze Fahrt | |
| export | Exportieren | |
| pack studio | Paket-Studio | |
| clip | Clip | |
| log excerpt | Log-Auszug | |
| support bundle | Support-Paket | |
| Driving insights | Fahrstatistik | |
| contribute | Mitwirken | |
| route / segment (openpilot's) | Route / Segment | |
| Privacy & sharing | Datenschutz & Teilen | the Settings page |
| stream key | Streamschlüssel | YouTube's |
| destination (Go live's) | Ziel | |
| Go live | Live gehen | |
| YouTube Studio | YouTube Studio | |
| Auto-start | Autostart | |
| Public / Unlisted / Private | Öffentlich / Nicht gelistet / Privat | YouTube's |
| input (microphone) | Eingang | |
| car hands-free | Freisprechanlage | |
| metered / monthly limit | getaktet / Monatslimit | openpilot's getaktet |
| Your requests | Ihre Anfragen | |
| Open / Closed (a request) | Offen / Erledigt | |
| license | Lizenz | |
| map library | Kartenbibliothek | |
| map theme | Kartenstil | |
| spoken guidance | Sprachansagen | |
| dev build | Dev-Build | |
| access pass | Zugangspass | the account's |
| waitlist | Warteliste | |
| beta member / admin | Beta-Mitglied / Admin | |
| display name / public name | Anzeigename / öffentlicher Name | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | Diese Woche / Letzte Woche / Gesamt | |
| finalized (a week) | abgeschlossen | |
| badge / share card | Abzeichen / Teilen-Karte | |
| Official / Community (packs) | Offiziell / Community | |
| reviewed by CommaView / unreviewed | von CommaView geprüft / ungeprüft | |
| Update ready | Update bereit | |
| training collection | Trainingsdaten | car detection's |
| recording metadata | Aufnahme-Metadaten | |
| SSH identity (a comma's host key) | SSH-Identität | |
| keystore | Schlüsselspeicher | Android's |
| repository (a fork's) | Repository | |
| driving software | Fahrsoftware | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | auf den alten Stand zurücksetzen | |
