---
title: "CommaView 0.0.164 : carrotpilot, SunnyPilot-TeslaHW1 et copies en direct"
description: "CommaView 0.0.164 ajoute carrotpilot et SunnyPilot-TeslaHW1, et des copies en direct qui gardent ce que montre Live View en roulant. Plus Navigation et Surround en accès anticipé."
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot forks
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - recordings
heroLabel: "Notes de version"
draft: false
---

CommaView 0.0.164 est disponible pour tous les membres de la bêta. Il ajoute deux forks d'openpilot, **carrotpilot** et **SunnyPilot-TeslaHW1** : CommaView fonctionne désormais avec sept forks, openpilot, sunnypilot, StarPilot, l'openpilot de xnor-tech, AdventurePilot, SunnyPilot-TeslaHW1 et carrotpilot. Il apporte aussi les **copies en direct**, qui gardent ce que montre Live View pendant que vous roulez, prêtes dès que vous vous arrêtez.

Il est accompagné du runtime `v0.0.60-beta`, qui reconnaît les deux nouveaux forks. Mettez à jour le runtime depuis l'application quand elle le propose, et redémarrez le comma quand elle le demande.

## SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 est un fork de sunnypilot qui ajoute les Tesla HW1 (Autopilot 1). Son écran est celui de sunnypilot : CommaView dessine donc l'écran de sunnypilot avec tout ce que sunnypilot y ajoute, et nomme le fork dans l'application.

À savoir : son `op fork update` ne peut pas changer de fork tant que le hook de CommaView est installé. Désinstallez d'abord CommaView, ou utilisez le sélecteur de fork sur l'écran du comma, qui fonctionne normalement.

## carrotpilot

carrotpilot est un fork d'openpilot pour les Hyundai, Kia et Genesis, installé depuis `i.carrotpilot.app`. CommaView dessine pour lui l'écran d'openpilot, avec votre vitesse, la trajectoire, les voies et le véhicule de tête, et nomme le fork dans l'application.

Deux limites, pour l'instant :

- **L'écran propre à carrotpilot n'est pas encore dessiné.** Ce qu'il ajoute à l'écran d'openpilot, comme sa navigation, ses radars et son HUD, n'apparaît pas dans Live View.
- **Ses mises à jour retirent le hook de CommaView jusqu'au redémarrage du comma.** La mise à jour automatique de carrotpilot, et les outils Git de sa page web, réinitialisent ses fichiers pendant qu'il tourne. Rien ne casse : l'application demande un redémarrage, et Live View revient ensuite.

## Copies en direct

Jusqu'ici, Enregistrer produisait une relecture : une fois garé, l'application télécharge la vidéo du comma et dessine le HUD par-dessus. C'est toujours la meilleure image, mais cela prend un moment après le trajet et s'arrête à 10 minutes par enregistrement.

Paramètres › Enregistrements › **Enregistrer dans Live View** vous permet maintenant de choisir ce que produit Enregistrer :

| Choix | Ce que vous obtenez |
| --- | --- |
| Relecture (par défaut) | La vidéo du comma avec le HUD dessiné par-dessus, produite une fois garé. La meilleure image, jusqu'à 10 minutes par enregistrement. |
| Copie en direct | Ce que montre Live View pendant que vous roulez, gardé sur votre téléphone et prêt dans Enregistrements dès que vous vous arrêtez, sans limite de 10 minutes. |
| Les deux | Une copie en direct tout de suite, et la relecture après le trajet. |

Une copie en direct est en 720p (environ 1,4 Go par heure) ou en 1080p (environ 2,3 Go par heure), à 20 images par seconde. Elle continue quand vous changez d'application ou verrouillez le téléphone, avec une notification qui permet de l'arrêter. Elle s'arrête proprement avant que le stockage du téléphone soit plein, et si l'application se ferme pendant l'enregistrement, vous gardez tout sauf la dernière minute.

Les copies en direct restent sur votre téléphone et ne sont jamais envoyées en ligne.

## Aussi dans 0.0.164

- **Des paramètres qui occupent tout l'écran.** Enregistrements, Affichage et Diffusion en direct sont disposés comme Cartes hors ligne, sur deux colonnes quand elles tiennent, et s'alignent sur les tablettes, les systèmes multimédias et les téléphones tenus à l'horizontale.
- **Pourquoi une installation a échoué.** Si l'installation, une mise à jour du runtime ou une désinstallation échoue, l'application dit ce qui s'est passé et quoi faire : un fork que CommaView ne prend pas en charge, la voiture en train de rouler, pas d'Internet sur le comma, un téléchargement endommagé. Elle dit si votre comma a été remis dans son état d'origine, et **Copier les détails** copie le rapport dont l'assistance a besoin.
- **Des relectures plus rapides.** Une relecture ne télécharge que la vidéo qu'elle montre, et le trajet suivant dans la file d'attente se télécharge pendant qu'une autre est produite. Un enregistrement interrompu par la fermeture de l'application, la limite de 10 minutes ou l'arrêt de la voiture peut maintenant lui aussi devenir une relecture.
- **La qualité de relecture fonctionne de nouveau.** Balanced, High et Max produisent de nouveau des relectures différentes : toutes étaient produites au même débit de 40 Mbit/s. High, le réglage par défaut, produit maintenant des fichiers environ deux fois plus petits depuis un comma 3X.

## Accès anticipé : Navigation et Surround

Certaines fonctions sont en début de développement : **Navigation**, **Surround**, **Passer en direct** et **Envoyer à CommaView**. Nous les ouvrons à un groupe restreint de testeurs, derrière des options de fonctionnalité, le temps de recueillir des retours : elles n'apparaissent que sur les comptes où elles sont activées.

- **Navigation**, c'est le guidage virage par virage, de l'Accueil à Live View : cherchez un lieu, choisissez un itinéraire, puis suivez la carte de virage, les annonces vocales et, sur l'écran de CommaView, des chevrons peints dans votre voie. Après une erreur de direction, un nouvel itinéraire est trouvé en quelques secondes. C'est de l'affichage seulement : rien n'est envoyé à votre comma ni à votre voiture.
- **Surround** est une vue 3D de la route autour de votre voiture : la route telle que la caméra la voit, avec ses marquages et ses intersections, et les voitures, camions et feux autour de vous.

Certaines reposent sur des services payants, comme le calcul d'itinéraire de Navigation : nous gardons donc le groupe restreint tant que nous ne savons pas ce que coûte un usage normal. Si vous voulez aider à les tester, contactez-nous sur notre [Discord](https://discord.gg/UuMhz9K8ft) et préparez-vous à nous dire comment elles se comportent sur vos trajets.

## Comment l'obtenir

CommaView est en bêta sur invitation. Si vous en faites partie, l'application propose d'elle-même la mise à jour 0.0.164. Une fois à jour, mettez à jour le runtime de votre comma depuis l'application, puis redémarrez le comma quand elle le demande. Les mises à jour du runtime attendent que la voiture soit en position P et openpilot désengagé, pour ne jamais interrompre un trajet.

Nouveau sur CommaView ? Le [guide d'installation](/fr/guides/setup) explique comment installer l'application et connecter votre comma.

## Pour aller plus loin

- [Quels forks d'openpilot fonctionnent avec CommaView](/fr/forks), dont [SunnyPilot-TeslaHW1](/fr/forks#teslahw1) et [carrotpilot](/fr/forks#carrotpilot)
- [Les nouveautés](/fr/whats-new) de chaque version
- [Comment se font les versions de CommaView](/fr/guides/releases)

CommaView est non officiel et n'est affilié ni à comma.ai, ni à sunnypilot, carrotpilot ou SunnyPilot-TeslaHW1. C'est un logiciel en bêta et non un système de sécurité : ne le laissez jamais vous distraire de la conduite.
