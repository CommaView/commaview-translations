---
title: "Vérifier que votre comma et votre fork sont pris en charge"
description: "CommaView fonctionne avec openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot et OPGM, et au mieux avec les autres forks."
topic: start
order: 2
kind: reference
lede: "CommaView affiche la caméra route de votre comma avec les surimpressions de conduite du logiciel qu'il exécute. Il fonctionne avec openpilot et neuf de ses forks, sur le comma 3X et le comma four, et, au mieux, avec d'autres forks d'openpilot. La configuration vérifie quel fork exécute votre comma avant de changer quoi que ce soit."
updated: 2026-11-27
needs:
  - title: "Un comma 3X ou comma four"
    text: "Le comma 3 n'est pas pris en charge, y compris les versions comma 3 des forks comme xnor-c3. [Pourquoi le comma 3 n'est pas pris en charge](/#faq-comma-3)."
  - title: "Votre fork, tel qu'il tourne"
    text: "Installé et en marche comme d'habitude. CommaView ajoute son runtime à côté et ne change jamais sa façon de conduire."
steps:
  - id: unlisted
    title: "Sur un fork que CommaView ne liste pas, la configuration vous demande d'abord"
    body: |
      La configuration guidée vérifie depuis quel dépôt le logiciel de votre comma a été installé, et installe le hook de CommaView pour ce fork. Sur un fork qu'elle ne liste pas, elle vérifie d'abord le fork, sans rien changer.
    tabs:
      - label: "Au mieux"
        body: "Si CommaView peut ajouter sa vue, la configuration affiche **CommaView n'a pas vérifié ce fork**. Elle nomme le fork par son dépôt et dit ce qui est dessiné (les caméras, la trajectoire, les voies, le véhicule de tête, les alertes et la vitesse) et ce qui ne l'est pas (les boutons, couleurs et widgets propres au fork). **Installer quand même** installe sur ce fork, et uniquement celui-là. **Retour** revient au choix du comma ; rien n'a été installé."
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**Installer quand même** ajoute la vue de CommaView à ce fork, au mieux."
      - label: "Vidéo seule (accès anticipé)"
        body: "Pour FrogPilot et KisaPilot, dont les écrans ne peuvent pas recevoir la vue de CommaView, les testeurs qui ont l'option Vidéo seule voient **Vidéo seule sur ce fork** : CommaView diffuse les caméras et dessine sa propre vue à partir des données de conduite, sans rien changer au fork. Cela n'a pas encore été essayé sur un comma. Sans l'option, la configuration indique que le fork n'est pas pris en charge et ne change rien."
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**Installer en vidéo seule**."
    note: "Quand la vérification refuse un fork, la configuration indique « CommaView ne peut pas ajouter sa vue de façon sûre dans … » et « Rien n'a été changé sur votre comma. »"
  - id: details
    title: "Voir quel fork dessine Live View"
    body: |
      Dans Live View, ouvrez **Détails**. La ligne **Logiciel** nomme le fork de votre comma, et un fork que CommaView ne liste pas est nommé par son dépôt, par exemple « crwusiz/openpilot · au mieux ».
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**Détails**, sous l'image."
      - text: "**Logiciel** : le fork qu'exécute votre comma."
related: [setup, overlays, uninstall]
---

## Forks pris en charge

| Fork | D'où il vient | Pris en charge depuis |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | La première bêta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | La première bêta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot, anciennement github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor** (versions xnor et rx) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot, installé depuis i.carrotpilot.app | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

Sur un fork qu'elle ne liste pas, la configuration vérifie si CommaView peut ajouter sa vue et vous demande d'abord ; quand ce n'est pas possible, elle s'arrête et laisse votre comma tel quel.

## Ce que chaque fork affiche

### openpilot

Le logiciel de comma.ai. Live View dessine l'écran du comma four, celui du comma 3X, ou les surimpressions de CommaView, avec votre vitesse, MAX, la limitation de vitesse, le véhicule de tête et les changements de voie.

### sunnypilot

CommaView dessine l'écran de sunnypilot avec ce que sunnypilot y ajoute : les états direction seule et vitesse seule de MADS, l'assistant de limitation de vitesse, la trajectoire arc-en-ciel et les indicateurs d'angle mort, et sur l'écran du comma 3X son panneau de limitation de vitesse, le régulateur intelligent et l'interface développeur. Il lit vos réglages sunnypilot, pour que l'écran corresponde à celui du comma.

### StarPilot

StarPilot montre ses modes de conduite par la couleur, et CommaView utilise les couleurs choisies par StarPilot : sa bordure, sa trajectoire et ses widgets sur les écrans comma four et comma 3X, ses alertes, et son choix de caméra, caméra conducteur comprise.

Désactivez le réglage **Disable Logging** de StarPilot. Il arrête l'encodeur vidéo à partir duquel Live View diffuse.

### L'openpilot de xnor-tech : xnor et rx

L'openpilot de xnor-tech existe en deux versions. Ses branches **xnor** utilisent l'écran d'openpilot et ses branches **rx** celui de sunnypilot, chacune avec les portages de voitures de xnor-tech. CommaView dessine celle qu'exécute votre comma, avec ses alertes telles que le comma les écrit.

Sur un Rivian avec rx, le volant devient vert quand la voiture braque par l'angle et bleu quand elle braque par le couple : le volant du comma four, et sur l'écran du comma 3X celui du bouton du mode expérimental.

### AdventurePilot

AdventurePilot est un fork de sunnypilot avec ses propres portages de voitures. CommaView dessine l'écran de sunnypilot avec ce qu'AdventurePilot y ajoute :

- son indicateur de centrage dans la voie : une pastille avec la poussée et le décalage sur l'écran du comma 3X, une barre compacte sur celui du comma four ;
- la puce CURVE sur l'écran du comma 3X, qui clignote quand le contrôle de vitesse en courbe agit ;
- la teinte du volant selon son mode de direction, et une barre de couple qui montre l'accélération latérale quand un Rivian braque sur son canal d'angle.

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 est un fork de sunnypilot qui ajoute les Tesla HW1 (Autopilot 1). Son écran est celui de sunnypilot : CommaView dessine donc l'écran de sunnypilot avec tout ce que sunnypilot ajoute, et nomme le fork dans l'application.

Son `op fork update` ne peut pas changer de fork tant que le hook de CommaView est installé : [désinstallez d'abord le runtime de CommaView](/fr/guides/uninstall), ou utilisez le sélecteur de fork sur l'écran du comma, qui fonctionne comme d'habitude.

### carrotpilot

carrotpilot est un fork d'openpilot pour les Hyundai, Kia et Genesis, installé depuis `i.carrotpilot.app`. CommaView dessine pour lui l'écran d'openpilot, avec votre vitesse, la trajectoire, les voies et le véhicule de tête. Ce que carrotpilot ajoute à son propre écran, comme sa navigation, ses radars et son HUD, n'est pas encore dessiné.

La mise à jour automatique de carrotpilot, et les outils Git de sa page web, retirent le hook de CommaView jusqu'au redémarrage du comma. L'application demande le redémarrage, et Live View revient ensuite.

### BluePilot, dragonpilot et OPGM

Listés depuis CommaView 0.0.166 avec son runtime. CommaView nomme chacun et le dessine dans le style de sa base : BluePilot comme sunnypilot, dragonpilot et OPGM comme openpilot, l'ALKA de dragonpilot étant affiché comme direction. Un comma qui en exécutait un au mieux passe à lui au démarrage qui suit la mise à jour du runtime. Aucun n'a encore roulé avec CommaView. Les [packs de superposition](/fr/guides/overlays) officiels de CommaView dessinent davantage des écrans propres à BluePilot et dragonpilot.

## Les forks que CommaView ne liste pas

Depuis CommaView 0.0.165, avec son runtime sur votre comma, la configuration peut ajouter la vue de CommaView, au mieux, à un fork d'openpilot qu'elle ne liste pas. Live View dessine le fork dans le style d'openpilot, ou de sunnypilot quand le fork s'appuie sur l'écran de sunnypilot. Pour l'annuler, **Désinstaller le runtime** dans Paramètres de l'appareil remet les fichiers du fork dans leur état d'origine.

- **Au mieux.** Les versions de CommaView ne sont pas vérifiées sur votre fork. Si le fork se met à jour vers quelque chose que CommaView ne peut pas suivre, la vue de CommaView se désactive, et votre fork conduit et affiche son propre écran comme d'habitude, jusqu'à ce qu'une version de CommaView gère le changement.
- **Pas tous les forks.** Les forks construits sur l'ancien écran natif d'openpilot ne sont pas pris en charge (voir plus bas).
- **Votre accord vaut pour ce fork.** Si votre comma passe à un autre fork que CommaView ne liste pas, CommaView redemande dans la configuration avant d'y ajouter sa vue.

### Les forks qui passent la vérification d'installation (au mieux)

Chacun de ceux-ci **passe la vérification d'installation de CommaView ; au mieux, non testé sur une voiture.** Vérifiés en novembre 2026, pour les branches indiquées, avec le runtime qu'installe CommaView 0.0.165 : l'installateur propose le fork, ajoute la vue de CommaView une fois votre accord donné, et la vérifie, comme il le ferait sur votre comma. Rien ici n'a été essayé sur un comma dans une voiture, un fork peut ne pas prendre en charge toutes les voitures sur les deux appareils, et la prochaine mise à jour d'un fork peut changer la réponse.

| Fork | Branches vérifiées | Appareils | Dessiné comme |
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

Votre fork n'est pas là ? Il peut quand même fonctionner : la configuration le vérifie avant de changer quoi que ce soit.

### Non pris en charge

Les écrans de ces forks ne peuvent pas recevoir la vue de CommaView : la configuration le dit et ne change rien sur votre comma.

- **FrogPilot** (github.com/FrogAi/FrogPilot). Il utilise l'ancien écran natif (Qt) d'openpilot, qui n'a pas de place pour la vue de CommaView. La vidéo seule est en accès anticipé.
- **KisaPilot** (github.com/kisapilot/openpilot). Son écran Python est désactivé : il utilise l'ancien écran natif (Qt) d'openpilot. La vidéo seule est en accès anticipé.
- **IQ.Pilot** (github.com/IQLvbs/iqpilot). Depuis octobre 2026, il tourne sur son propre IQ.OS ; sa prise en charge attend que CommaView puisse le prendre en charge comme un fork à part entière.
- **hikee9123** (github.com/hikee9123/openpilot). Il utilise l'ancien écran natif (Qt) d'openpilot.

**Accès anticipé : vidéo seule pour FrogPilot et KisaPilot.** Avec l'option Vidéo seule, la configuration propose d'afficher leurs caméras dans Live View avec les surimpressions de CommaView à la place de leurs propres écrans, sans rien changer au fork. Cela n'a pas encore été essayé sur un comma. Sans l'option, la configuration indique toujours qu'ils ne sont pas pris en charge et ne change rien.

## Quels appareils comma

Le comma 3X et le comma four. Le comma 3 n'est pas pris en charge, y compris les versions comma 3 des forks comme xnor-c3 : [pourquoi le comma 3 n'est pas pris en charge](/#faq-comma-3). L'application tourne sur un téléphone, une tablette ou un système multimédia Android.

## Branches de version et de développement

Avant chaque version, le runtime de CommaView est compilé et vérifié sur les versions publiées de ces forks. La branche nightly d'openpilot et la branche dev de sunnypilot sont vérifiées chaque jour où elles changent, comme alerte précoce. Une branche de développement peut changer plus vite que CommaView : si un changement empêche le hook de CommaView de se charger, l'écran et la conduite de votre fork continuent comme d'habitude.

## Votre fork n'est pas listé ?

Essayez-le au mieux, et demandez qu'il soit listé sur le tableau des fonctionnalités sur [my.commaview.com](https://my.commaview.com), ou envoyez une idée depuis l'application (Paramètres › **Assistance et diagnostics**). Un fork listé est vérifié avant chaque version. Voyez [les nouveautés](/whats-new) de chaque version.

## Questions

**CommaView change-t-il la façon dont mon fork conduit ?** Non. Il ajoute un petit runtime à côté de votre fork et un petit hook dans son interface à l'écran, pour que CommaView puisse dessiner la même trajectoire, les mêmes voies et les mêmes alertes. La façon dont votre voiture conduit ne change pas.

**CommaView fonctionne-t-il avec StarPilot ?** Oui, depuis CommaView 0.0.162. Live View affiche les couleurs, les widgets et le choix de caméra propres à StarPilot. Désactivez le réglage **Disable Logging** de StarPilot, qui arrête l'encodeur vidéo à partir duquel CommaView diffuse.

**CommaView fonctionne-t-il avec carrotpilot ?** Oui, depuis CommaView 0.0.164. Live View dessine pour lui l'écran d'openpilot ; ce que carrotpilot ajoute à son propre écran, comme sa navigation et ses radars, n'est pas encore dessiné. Après une mise à jour automatique de carrotpilot, l'application demande un redémarrage qui fait revenir Live View.

**CommaView fonctionne-t-il avec FrogPilot ?** Pas encore : il utilise l'ancien écran natif (Qt) d'openpilot, qui n'a pas de place pour la vue de CommaView, donc la configuration indique qu'il n'est pas pris en charge et ne change rien. La vidéo seule est en accès anticipé pour FrogPilot et KisaPilot, pour les testeurs.
