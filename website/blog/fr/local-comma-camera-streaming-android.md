---
title: "Diffuser la caméra du comma en local sur Android : ce que fait CommaView"
description: "CommaView diffuse la caméra route de votre comma et ses surimpressions vers Android, sur votre propre réseau : Live View, Enregistrements, le direct, et ce qu'il ne fait pas."
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma camera streaming
  - comma four
  - Android app
  - CommaView
  - local streaming
heroLabel: "Ce qu'il fait"
draft: false
---

CommaView diffuse la caméra route de votre comma, avec ses surimpressions de conduite, vers un téléphone, une tablette ou un système multimédia Android, sur votre propre réseau. Aucun cloud ne se place entre le comma et votre téléphone, et rien n'a besoin d'être envoyé en ligne d'abord.

Il se compose de deux parties : l'application CommaView, et un petit runtime sur le comma, `commaviewd`, qui fournit la caméra et les données de conduite à l'application. La configuration guidée installe le runtime et le vérifie.

## Pourquoi diffuser, au fond

L'écran du comma four mesure 1,9 pouce. C'est un bon écran pour ce qu'il fait, mais il est petit, et les propriétaires le disent. Les autres moyens d'obtenir la vidéo du comma sont faits pour d'autres usages :

- **comma connect** garde les trajets envoyés 3 jours, ou un an avec comma prime ([comma.ai/prime](https://comma.ai/prime)). Depuis [openpilot 0.11.2](https://blog.comma.ai/0112release/), il peut diffuser en direct les caméras route et conducteur pendant que la voiture est garée, par Internet, avec un comma power installé, et découper des extraits MP4 sur le comma.
- **SSH** vous donne les segments HEVC bruts d'une minute depuis le stockage du comma.

Aucun des deux ne montre la route avec les surimpressions d'openpilot pendant que vous roulez. C'est à cela que sert CommaView.

## Ce que fait CommaView

### Live View

La caméra route, en direct, avec l'écran propre à votre fork dessiné dessus : celui du comma four, celui du comma 3X ou celui de CommaView, avec votre vitesse, MAX, la limitation de vitesse, le véhicule de tête et les changements de voie dans un même bloc. Live View dessine l'écran de chaque fork avec ce que ce fork y ajoute, du MADS de sunnypilot au HUD propre à StarPilot. Il tourne jusqu'aux 20 images par seconde du comma, et continue en mode image dans l'image.

Sur une tablette ou un système multimédia Android, CommaView se dispose comme un tableau de bord, avec les commandes de Live View du côté du conducteur.

### Enregistrements

Touchez Enregistrer dans Live View et, une fois garé, CommaView télécharge la vidéo du comma pour ce passage, jusqu'à 10 minutes, et dessine par-dessus l'écran de votre fork sur votre téléphone : une relecture. Lisez-la, partagez-la ou ouvrez-la dans une autre application. Une copie en direct garde ce que montre Live View pendant que vous roulez, en 720p ou 1080p, prête dès que vous vous arrêtez, sans limite de 10 minutes. Les enregistrements restent sur votre téléphone jusqu'à ce que vous les supprimiez.

### Passer en direct

Le direct diffuse ce que montre Live View, la route et les surimpressions de CommaView, sur votre chaîne YouTube ou sur n'importe quel serveur RTMP, en 720p ou 1080p. Connectez-vous une fois avec YouTube, et il crée, lance et termine chaque diffusion. Les diffusions commencent en Non répertoriée ; qui regarde voit où vous roulez.

### Téléphones associés seulement

Les caméras et données de votre comma ne vont qu'aux téléphones et systèmes multimédias qui lui sont associés. Vidéo, trajets et lieux vont de votre comma à votre téléphone et nulle part ailleurs, sauf si vous les envoyez, les diffusez ou les contribuez.

## Ce qui a besoin d'Internet

Live View et les enregistrements, non : ils vont directement du comma à votre téléphone, sur le même réseau local, votre Wi‑Fi ou un point d'accès dans la voiture, depuis votre téléphone, votre système multimédia, votre boîtier IA ou le comma. La connexion au compte, les mises à jour de l'application et du runtime, la carte de Position du véhicule, le classement, le direct et tout ce que vous envoyez à CommaView, oui.

## Avec quoi il fonctionne

Le comma 3X et le comma four, sous openpilot, sunnypilot, StarPilot, l'openpilot de xnor-tech, AdventurePilot, SunnyPilot-TeslaHW1 et carrotpilot. Les autres forks d'openpilot fonctionnent au mieux : l'installation vérifie le fork et vous demande avant d'installer. Le comma 3 n'est pas pris en charge : il est sur une version figée d'openpilot dont CommaView ne peut pas tirer ses surimpressions. [Forks pris en charge](/fr/forks).

Il vous faut un téléphone, une tablette ou un système multimédia sous Android 8 ou plus récent.

## Ce que CommaView n'est pas

- **Pas comma connect.** Il ne garde pas les trajets dans un cloud et ne montre pas votre voiture depuis l'autre bout de la ville. Utilisez connect pour cela.
- **Pas une dashcam.** [Prenez une vraie dashcam](/fr/blog/is-comma-a-dashcam) s'il vous faut des images d'accident ou de stationnement qui fassent foi.
- **Ni une aide à la conduite, ni un système de sécurité.** Il montre ce que voit le comma ; c'est la route qui fait foi.

## L'utiliser en sécurité

Configurez CommaView à l'arrêt. Un passager peut regarder Live View pendant que vous roulez ; si vous conduisez seul, traitez-le comme l'écran du comma lui-même et gardez les yeux sur la route.

CommaView est en bêta sur invitation. [Inscrivez-vous sur la liste](https://my.commaview.com/join) et nous vous écrirons quand ce sera votre tour.

CommaView est non officiel, et n'est ni affilié à comma.ai, sunnypilot ou aucun des forks d'openpilot avec lesquels il fonctionne, ni approuvé par eux. C'est un logiciel en bêta et non un système de sécurité : ne le laissez jamais vous distraire de la conduite.
