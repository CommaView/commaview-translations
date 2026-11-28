---
title: "CommaView 0.0.165 : le direct pour tous, Envoyer à CommaView et la détection des véhicules"
description: "CommaView 0.0.165 ouvre le direct à tous et Envoyer à CommaView à chaque membre, permet de contribuer des trajets à la détection des véhicules et s'installe sur plus de forks."
date: 2026-11-01
updatedDate: 2026-11-13
slug: commaview-0-0-165-go-live-send-to-commaview
tags:
  - live streaming
  - YouTube
  - recordings
  - openpilot forks
  - privacy
heroLabel: "Notes de version"
draft: false
---

CommaView 0.0.165 est disponible pour tous les membres de la bêta. **Passer en direct** est désormais ouvert à tous, et **Envoyer à CommaView** à chaque membre, pour un trajet ou plusieurs à la fois. Avec le nouveau runtime, les membres peuvent **contribuer des trajets à la détection des véhicules**, CommaView s'installe maintenant sur **plus de forks d'openpilot**, au mieux, et les caméras et données de votre comma ne vont **qu'aux téléphones associés**.

Il est accompagné du runtime `v0.0.61-beta`. **Mettez d'abord à jour CommaView sur chaque téléphone et système multimédia qui regarde votre comma**, puis mettez à jour le runtime depuis l'application quand elle le propose, et redémarrez le comma quand elle le demande. Un téléphone ou un système multimédia resté en 0.0.164 ou avant ne reçoit plus de vidéo d'un comma en runtime v0.0.61 ou plus récent.

## Passer en direct

Le direct était en accès anticipé dans 0.0.164. Il est maintenant ouvert à tous : **En direct**, dans Live View, diffuse ce que montre Live View, la route et les surimpressions de CommaView, sur votre chaîne YouTube ou sur n'importe quel serveur RTMP, en 720p ou 1080p.

Configurez-le une fois dans Paramètres › Diffusion en direct : **Se connecter avec YouTube**, qui crée, lance et termine chaque diffusion pour vous, ou enregistrez une clé de flux ou un serveur. Le direct apparaît ensuite dans Live View, ou dans son menu **Plus** quand l'écran manque de place.

- **Qui peut regarder** a sa propre ligne dans Paramètres › Diffusion en direct, et commence sur Non répertoriée. Qui regarde voit où vous roulez.
- **Son** est désactivé, sauf si vous choisissez le micro de votre comma ou celui de votre téléphone. Il va dans votre diffusion et vos copies en direct, jamais à CommaView.
- Quand le Wi‑Fi de votre comma n'a pas Internet, la diffusion passe par les données mobiles de votre téléphone. Les paramètres indiquent à peu près combien par heure.
- La connexion à YouTube et le direct fonctionnent maintenant quand un VPN est le réseau par défaut de votre téléphone.

La carte et la carte de virage de la navigation ne sont jamais dans une diffusion.

## Envoyer à CommaView

Envoyer à CommaView est maintenant ouvert à chaque membre. Dans Enregistrements, choisissez un trajet enregistré par votre comma, ou sélectionnez-en plusieurs, puis **Envoyer à CommaView** avec une note sur ce qui s'est passé. Nous recevons la vidéo route et grand angle de chaque trajet et son journal, pour voir le problème ; jamais la caméra conducteur, le son ni le numéro VIN de votre voiture.

Chaque trajet est téléchargé depuis votre comma avant d'être envoyé, un à la fois et le plus ancien d'abord : gardez donc le comma allumé et garé jusqu'à la fin. CommaView accepte 20 envois par jour et par compte ; les suivants attendent le lendemain.

La même fenêtre **Envoyer à CommaView** porte maintenant tout ce que vous nous envoyez : un **Problème** ou une **Idée**, votre note, et chaque pièce jointe, que vous pouvez ouvrir avec **Voir** ou laisser de côté. Elle s'ouvre depuis Paramètres › Assistance et diagnostics, depuis **Signaler** sur n'importe quelle erreur, et depuis le menu Plus d'un enregistrement.

## Contribuer à la détection des véhicules

Surround, toujours en accès anticipé, fait tourner son propre détecteur de véhicules sur votre téléphone. Les membres peuvent maintenant aider à l'entraîner avec leurs trajets. Il vous faut le nouveau runtime sur votre comma.

- **D'un geste :** **Contribuer à la détection des véhicules**, dans le menu Plus d'un trajet, ou pour plusieurs trajets sélectionnés.
- **Automatiquement :** activez **Contribuer les trajets automatiquement** dans Paramètres › Confidentialité et partage › Détection des véhicules. Les trajets récents de votre comma sont envoyés, tous ceux qu'il a encore, quand votre téléphone et le comma sont sur un réseau que vous autorisez, jusqu'à une limite quotidienne. Pas en mode économie de batterie, ni pendant que vous utilisez Live View ou enregistrez.

**Envoyer les contributions sur** choisit ces réseaux. **Réseaux que je choisis**, le réglage par défaut, liste les données mobiles de votre téléphone et les Wi‑Fi enregistrés par votre comma ; cochez ceux à utiliser, chacun avec une limite mensuelle si vous le souhaitez. Une contribution représente environ 110 Mo par minute de trajet. Quand votre comma rejoint un Wi‑Fi qu'il n'a jamais utilisé, l'Accueil et une notification demandent s'il faut l'ajouter. Votre comma indique sur quel réseau il est, CommaView n'a donc pas besoin de votre position.

Sachez ce que vous donnez avant de le donner :

- **Une contribution, c'est le trajet entier :** sa vidéo route et grand angle et son journal, y compris son parcours, du début à la fin.
- **C'est définitif.** Elle rejoint la collecte d'entraînement de CommaView et ne peut pas être retirée ensuite. Rien ne la relie à vous ni à votre comma.
- **comma connect attend.** Pendant l'envoi d'un trajet, votre comma le garde jusqu'à un jour pour qu'openpilot ne le supprime pas, et l'outil d'envoi d'openpilot le saute en attendant.

L'application l'explique une fois avant votre première contribution, et la contribution reste désactivée tant que vous ne l'activez pas.

## Plus de forks d'openpilot, au mieux

CommaView s'installe maintenant sur plus de forks d'openpilot, au mieux. Il liste openpilot et six de ses forks, et vérifie chacun avant chaque version. Sur tout autre fork d'openpilot, l'installation s'arrêtait. Maintenant elle vérifie le fork, sans rien changer, et si CommaView peut y ajouter sa vue, elle affiche « CommaView n'a pas vérifié ce fork » : ce qui est dessiné (les caméras, la trajectoire, les voies, le véhicule de tête, les alertes et la vitesse) et ce qui ne l'est pas. **Installer quand même** installe sur ce fork seulement.

Live View le dessine avec le style d'openpilot, ou celui de sunnypilot quand le fork s'appuie sur l'écran de sunnypilot, et le nomme, par exemple « BluePilotDev/bluepilot · best effort ». **Désinstaller le runtime**, dans Paramètres de l'appareil, remet les fichiers du fork en place.

Vérifiés en novembre 2026, dragonpilot, BluePilot, crwusiz, opgm, zoompilot, le Carrot de jixiexiaoge, NotAutopilot et d'autres passent sa vérification d'installation ; non testés en voiture. [Les forks et les branches vérifiées](/fr/forks#install-check) sont sur la page des forks pris en charge.

Deux limites :

- **Au mieux.** Les versions de CommaView ne sont pas vérifiées sur votre fork. Si le fork se met à jour vers quelque chose que CommaView ne sait pas suivre, la vue de CommaView se désactive et le fork conduit comme d'habitude.
- **L'écran propre au fork n'est pas dessiné.** Ses boutons, couleurs et widgets n'apparaissent pas dans Live View, et les forks bâtis sur l'ancien écran natif d'openpilot ne sont pas pris en charge du tout.

## Téléphones associés seulement

Avec le nouveau runtime, les caméras et données de votre comma ne vont qu'aux téléphones et systèmes multimédias qui lui sont associés. Quand un autre appareil a la caméra, Live View affiche « Un autre appareil utilise la caméra de ce comma » et réessaie de lui-même.

Les installations du runtime se rétablissent aussi maintenant. Une coupure de courant ou un redémarrage en pleine installation remet la version précédente, une installation continue quand l'application cesse d'écouter, et un téléchargement bloqué reprend là où il s'était arrêté.

## Aussi dans 0.0.165

- **Plusieurs trajets à la fois.** Sélectionnez des trajets dans Enregistrements pour les partager, produire leurs relectures, les envoyer ou les supprimer ensemble.
- **Live View tient sur tous les écrans.** Ses commandes ne défilent plus et ne coupent plus **Quitter** : ce qui ne tient pas va dans **Plus**, et un texte plus grand déplace des commandes dans Plus au lieu de rien rétrécir. Live View est aussi plus léger pour le téléphone, et repart de lui-même au lieu de se figer.
- **Vos demandes.** Quand vous signalez un problème ou envoyez une idée en étant connecté, nous pouvons répondre. Paramètres › Assistance et diagnostics › **Vos demandes** montre nos réponses, vous recevez un e-mail, et la conversation continue sur my.commaview.com.
- **Des paramètres réorganisés.** Confidentialité et partage dit ce qui quitte votre téléphone. **Aider à améliorer CommaView** demande une fois s'il faut envoyer les rapports de plantage et quel logiciel de conduite tourne sur votre comma.
- **Le classement, pour chaque membre.** Il ne dépend plus d'une option de fonctionnalité.
- **Le mode expérimental sur les openpilot récents.** Sur la nightly d'openpilot et sunnypilot dev, où le mode chill a disparu, Live View affiche le mode expérimental comme le fait openpilot.
- **Soutenir CommaView.** Paramètres › Assistance et diagnostics › **Soutenir CommaView** ouvre notre page [Buy Me a Coffee](https://buymeacoffee.com/commaview), pour aider à couvrir l'hébergement, les tests et l'application iOS. Elle ne débloque rien.
- **Corrections.** Un système multimédia sous Android 16 ne ferme plus CommaView dans Live View quand son décodeur vidéo échoue, et l'écran comma 3X de StarPilot dessine sa caméra sur les systèmes multimédias qui l'affichaient en noir.

## Accès anticipé : Navigation et Surround

**Navigation**, **Surround**, **Surround V2** et les **Outils expérimentaux** restent réservés à un groupe restreint de testeurs, derrière des options de fonctionnalité, le temps de recueillir des retours.

- **Navigation** affiche maintenant une carte dans Live View pendant un trajet, à côté de la vidéo ou dans son coin, et **Où allez-vous ?** sans trajet. Sur la carte en coin, Terminer et Couper la voix sont toujours là, Terminer peut être annulé pendant 8 secondes, et vous pouvez dire où aller.
- **La carte de Navigation** a maintenant un thème clair et un thème sombre, qui basculent au lever et au coucher du soleil là où se trouve votre comma, pour rester lisible au soleil. Choisissez Auto, Comme le téléphone, Clair ou Sombre dans Paramètres › Cartes et navigation › Thème de carte.
- **Surround V2** est un second moteur de rendu expérimental pour Surround, dans Paramètres › Outils expérimentaux.

Certaines reposent sur des services payants, comme le calcul d'itinéraire de Navigation : nous gardons donc le groupe restreint pour l'instant. Si vous voulez aider à les tester, contactez-nous sur notre [Discord](https://discord.gg/UuMhz9K8ft) et préparez-vous à nous dire comment elles se comportent sur vos trajets.

## Comment mettre à jour

CommaView est en bêta sur invitation. Si vous en faites partie, l'application propose d'elle-même la 0.0.165.

1. Mettez à jour CommaView sur **chaque téléphone et système multimédia** que vous utilisez avec votre comma.
2. Puis mettez à jour le runtime de votre comma depuis l'application.
3. Redémarrez le comma quand l'application le demande. Les mises à jour du runtime attendent que la voiture soit en position P et openpilot désengagé, pour ne jamais interrompre un trajet.

Nouveau sur CommaView ? Le [guide d'installation](/fr/guides/setup) explique comment installer l'application et connecter votre comma.

## Pour aller plus loin

- [Quels forks d'openpilot fonctionnent avec CommaView](/fr/forks), et [les forks qu'il ne liste pas](/fr/forks#unlisted)
- [Les nouveautés](/fr/whats-new) de chaque version
- [Comment se font les versions de CommaView](/fr/guides/releases)
- [Politique de confidentialité](/privacy) (en anglais) : ce que partagent le direct, Envoyer à CommaView et les contributions

CommaView est non officiel et n'est affilié ni à comma.ai, ni à sunnypilot, ni à aucun des forks d'openpilot avec lesquels il fonctionne. C'est un logiciel en bêta et non un système de sécurité : ne le laissez jamais vous distraire de la conduite.

## Correction du 13 novembre 2026

Dans **Contribuer à la détection des véhicules**, cet article disait que rien ne relie une contribution à vous ou à votre comma. C'était aller trop loin. Une contribution ne nomme ni vous ni votre comma, mais le parcours et la vidéo d'un trajet peuvent montrer où vous roulez. À partir de la prochaine version de l'application, celle-ci le dit et vous redemande votre accord avant votre prochaine contribution ; la [politique de confidentialité](/privacy) disait déjà qu'une contribution comprend le parcours du trajet. Le reste de l'article est tel qu'il a été publié.
