# Français glossary

The words every French string uses for CommaView's terms, so screens translated apart say the same thing. Where
openpilot already translates a term (`selfdrive/ui/translations/app_fr.po`, taken from openpilot `v0.10.1`: master no
longer has it), its word is used, so the app says what the car's screen says. Machine drafted; a native speaker's
review is owed before release (the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`). A name that starts a
sentence stays lower case (openpilot's own French does: « openpilot roule par défaut… »).

## Style

- Address the person as **vous**, as openpilot's translation does (« Êtes-vous sûr de vouloir redémarrer ? »,
  « Associez votre appareil »). Never tu.
- French typography: a narrow no-break space (U+202F) before `;` `:` `!` `?` and inside « » (« Live View »). The
  build script that wrote these files puts it in; keep it when editing by hand. Quotes are « », nested “ ”.
- Apostrophes are the straight `'`, escaped `\'` in the XML. Ellipsis stays …, as the English has it.
- Buttons are short infinitives, as Android's French writes them: Annuler, OK, Enregistrer, Supprimer, Réessayer,
  Continuer, Ouvrir, Fermer, Activer, Désactiver.
- Titles, buttons, row titles and pills: sentence case (only the first word capitalised), no full stop. Whole
  sentences in body text end with a full stop.
- French runs long: prefer the shorter common word, drop articles in labels where French allows it
  (« Trajet complet », not « Le trajet complet »). « application » in sentences, « appli » only where Android's
  own French uses it.
- Numbers keep the English's placeholders; the formatters give French separators.
- Plurals: `one` (0 and 1 in French), `many` (large numbers in CLDR) and `other`. `many` has the same text as
  `other`. `one` keeps the count's placeholder, since it also serves 0.

## Terms

| English | Français | Note |
|---|---|---|
| Home (dock) | Accueil | |
| Recordings | Enregistrements | the section and its saved drives |
| Settings | Paramètres | Android's word |
| recording, a recording | enregistrement | |
| drive (a trip the comma recorded) | trajet | openpilot's (« stockage de trajets ») |
| replay | relecture | |
| live copy | copie en direct | |
| saved moment | moment enregistré | the rail's Save is « Garder » (« Enregistrer » is Record) |
| Record | Enregistrer | the rail's button |
| Go live / live streaming | Passer en direct / diffusion en direct | the button, and the feature named in a sentence: « En direct » |
| onroad screen | écran de conduite | |
| onroad / offroad (the comma's state) | en route / à l'arrêt | |
| design (an onroad screen's look) | style | |
| overlay pack | pack de superposition | « pack » alone where the context says it |
| fork | fork | openpilot's own jargon, masculine (« un fork ») |
| runtime (commaviewd) | runtime | masculine; « environnement d'exécution » is too long for the rows |
| update / install / uninstall | mettre à jour, mise à jour / installer / désinstaller | openpilot's |
| reboot | redémarrer | openpilot's |
| power off | éteindre | openpilot's |
| pair / pairing | associer / association | openpilot's |
| device (the comma) | appareil | openpilot's |
| this phone / this device (the device CommaView runs on) | ce téléphone / cet appareil | openpilot says téléphone and appareil; `common_this_phone` / `common_this_device` (and `_start`: Ce téléphone / Cet appareil), a sentence's placeholder (how-to-localize.md, "This phone or this device"). Both masculine and both start with c, so « de %1$s », « à %1$s », « que %1$s » never elide and adjectives agree either way. Keep the slot where English has it: at a sentence's start it gets the capitalised form, so « X de %1$s » can't open a sentence; make the slot the subject instead (« %1$s n'a pas pu… ») |
| your phone / your device (`common_your_*`) | votre téléphone / votre appareil | both masculine; Votre téléphone / Votre appareil at a sentence's start |
| connected / disconnected | connecté / déconnecté | |
| offline | hors ligne | openpilot's |
| engaged / disengaged | engagé / désengagé | openpilot's « désengager » |
| override | intervention | the driver's |
| experimental mode | mode expérimental | openpilot's |
| driver monitoring | surveillance du conducteur | openpilot's |
| driver camera | caméra conducteur | openpilot's |
| road camera / wide camera | caméra route / caméra grand angle | openpilot says « grand angle » |
| lead car | véhicule de tête | openpilot's |
| speed limit | limitation de vitesse | |
| set speed / MAX | vitesse réglée / MAX | openpilot's |
| lane change | changement de voie | |
| calibration | calibration | openpilot's |
| driver position (left/right-hand drive) | poste de conduite (à gauche / à droite) | |
| daylight contrast | contraste plein jour | |
| offline maps | cartes hors ligne | |
| navigation | navigation | |
| Home / Work (places) | Domicile / Travail | |
| vehicle location | position du véhicule | openpilot says véhicule |
| account / sign in / sign out | compte / se connecter / se déconnecter | button: Connexion / Déconnexion |
| leaderboard | classement | |
| achievement | succès | |
| privacy | confidentialité | |
| diagnostics | diagnostics | |
| report a problem | signaler un problème | |
| Details (Live View's pane) | Détails | |
| stream health | état du flux | |
| storage | stockage | openpilot's |
| hotspot | point d'accès | |
| Live / Delayed (Live View's state) | Direct / Différé | |
| frame pacing | cadence d'images | |
| inset (a picture in the picture) | incrustation | |
| framing: Fill / Exact / Extend / Auto | Remplir / Exact / Étendre / Auto | |
| camera framing | cadrage | |
| reduce motion | réduire les animations | Android's |
| screen edges | bords de l'écran | |
| View (Surround's) / chase / high / top-down | Vue / poursuite / haute / de dessus | |
| vehicle detection / detector / model | détection des véhicules / détecteur / modèle | |
| renderer | moteur de rendu | |
| key (an API key, an SSH key) | clé | openpilot's « clé SSH »; public / private: publique / privée |
| dashboard (a service's) | tableau de bord | |
| reroute | recalculer l'itinéraire | |
| Where to? | Où allez-vous ? | |
| map source | source de carte | |
| Powered by | Fourni par | |
| steering / speed active, manual (the HUD's control line) | direction active / vitesse active / manuel | review on a drive |
| steering only / speed only | direction seule / vitesse seule | |
| blind spot | angle mort | |
| green light / lead car moving | feu vert / véhicule de tête qui démarre | |
| safe update / install / repair | mise à jour sûre / installation sûre / réparation sûre | |
| overlays (drawn on video) | surimpressions | not overlay packs (pack de superposition) |
| telemetry | télémétrie | |
| patch | correctif | |
| in Park | en position P | |
| power harness | câble d'alimentation permanente | |
| guided / manual setup | configuration guidée / manuelle | openpilot's « configuration » |
| boot hook / runtime hook | hook de démarrage / hook du runtime | |
| vehicle security key | clé de sécurité du véhicule | |
| pair code / invitation | code d'association / invitation | |
| phones with a key | téléphones avec une clé | |
| shared token | jeton partagé | |
| development runtime | runtime de développement | |
| controller | contrôleur | |
| best effort | au mieux | |
| video only | vidéo seule | |
| widgets | widgets | Android's |
| backup / restore | sauvegarde / restauration | |
| read-only | lecture seule | |
| head unit | système multimédia | the car's screen |
| nearby devices | Appareils à proximité | Android's permission |
| display over other apps | Superposition sur d'autres applis | Android's permission |
| set aside (saved lists) | mis de côté | |
| Not now / Review | Plus tard / Consulter | openpilot's REVIEW is CONSULTER |
| queue | file d'attente | |
| Needs processing | À traiter | |
| pull drives | récupérer les trajets | |
| whole drive | trajet complet | |
| export | exporter | |
| pack studio | studio de packs | |
| clip | extrait | |
| log excerpt | extrait de journal | |
| support bundle | paquet d'assistance | |
| Driving insights | Statistiques de conduite | |
| Browser View | Browser View | the feature's name, kept as zh-TW and ja keep it |
| Driver cam (the rail's toggle) | Caméra cond. | short form of caméra conducteur |
| contribute | contribuer | |
| route / segment (openpilot's) | parcours / segment | |
| Privacy & sharing | Confidentialité et partage | the Settings page |
| stream key | clé de flux | YouTube's |
| destination (Go live's) | destination | |
| Go live | Passer en direct | the rail's button is « En direct »; YouTube Studio's own Go live is « Passer au direct », its Auto-start « démarrage automatique » |
| YouTube Studio | YouTube Studio | YouTube's French |
| Auto-start | Démarrage auto | |
| Public / Unlisted / Private | Public / Non répertorié / Privé | YouTube's |
| input (microphone) | entrée | |
| car hands-free | kit mains libres | |
| metered / monthly limit | limité / limite mensuelle | openpilot's « réseau non limité » |
| Your requests | Vos demandes | |
| Open / Closed (a request) | Ouverte / Fermée | |
| license | licence | |
| map library | bibliothèque de cartes | |
| map theme | thème de carte | |
| spoken guidance | guidage vocal | |
| dev build | version de développement | « version dev » where space is tight |
| access pass | pass d'accès | the account's |
| waitlist | liste d'attente | |
| beta member / admin | membre Beta / administrateur | |
| display name / public name | nom affiché / nom public | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | Cette semaine / Semaine dernière / Total | |
| finalized (a week) | finalisée | |
| badge / share card | badge / carte de partage | |
| Official / Community (packs) | Officiel / Communauté | |
| reviewed by CommaView / unreviewed | vérifié par CommaView / non vérifié | |
| Update ready | Mise à jour prête | |
| training collection | collecte d'entraînement | car detection's |
| recording metadata | métadonnées d'enregistrement | |
| SSH identity (a comma's host key) | identité SSH | |
| keystore | magasin de clés | Android's |
| repository (a fork's) | dépôt | |
| driving software | logiciel de conduite | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | remis dans son état d'origine | |
