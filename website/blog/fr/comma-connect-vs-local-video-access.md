---
title: "comma connect ou vidéo en local : lequel fait ce dont vous avez besoin ?"
description: "comma connect, SSH et CommaView comparés après openpilot 0.11.2 : direct à l'arrêt, extraits, conservation, qualité vidéo, vie privée, et à quoi sert chacun."
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - local video access
  - comma four
  - CommaView
heroLabel: "Guide de choix"
draft: false
---

comma connect, l'application web de comma, est l'endroit où la plupart des propriétaires regardent d'abord leurs trajets, et pour beaucoup d'usages, c'est le bon endroit. Depuis openpilot 0.11.2, il en fait plus qu'avant : il peut diffuser en direct une voiture garée et découper des extraits MP4 sur l'appareil. L'accès local, par SSH ou avec CommaView, fait un autre travail : il récupère la vidéo directement sur le comma, sur votre propre réseau.

La réponse courte :

- **Un trajet récent, de n'importe où :** comma connect.
- **Jeter un œil à la voiture garée :** le direct de comma connect.
- **Regarder la route avec les surimpressions de votre fork pendant que vous roulez, sur un plus grand écran :** le Live View de CommaView.
- **Les fichiers bruts de la caméra, pour le développement ou l'archivage :** SSH.
- **Un extrait de ce que vous venez de voir, avec les surimpressions, sur votre téléphone, sans envoi en ligne :** Enregistrer, dans CommaView.

## Ce que fait comma connect

**Il garde vos trajets dans le cloud, un certain temps.** La [page prime](https://comma.ai/prime) de comma indique que les enregistrements « seront envoyés sur connect, où ils seront stockés 3 jours ». Avec comma prime (24 $ par mois, États-Unis seulement, données comprises) ou prime lite (14 $ par mois, avec votre propre SIM si vous voulez du cellulaire), connect les garde un an.

**Ce qu'il montre par défaut, c'est la petite vidéo.** La [documentation des journaux](https://docs.comma.ai/concepts/logs/) de comma indique que la vidéo de connect vient des fichiers qcamera, des « versions basse résolution de fcamera.hevc », faites pour s'envoyer vite sur une connexion lente. Les fichiers HEVC en pleine résolution restent sur le comma, sauf si vous les envoyez aussi.

**Depuis 0.11.2, il peut diffuser en direct une voiture garée.** L'[article sur la 0.11.2](https://blog.comma.ai/0112release/) (23 octobre 2026) indique qu'avec une connexion Internet, « le Wi‑Fi de la maison ou la LTE de comma prime », et un comma power installé, « vous pouvez diffuser en direct vos caméras route et conducteur pour voir ce qui se passe autour de votre véhicule pendant qu'il est garé ». Vous le regardez dans connect, de n'importe où.

**Il découpe aussi des extraits.** La même version ajoute un bouton d'extraits dans connect : choisissez une partie d'un trajet et « votre comma l'assemble et le réencode dans un MP4 (H.264) largement compatible ». Laissez le comma allumé pendant qu'il travaille, puis téléchargez l'extrait depuis connect.

C'est un vrai progrès. Si vous voulez voir votre voiture garée depuis votre bureau, ou envoyer à un ami un extrait du trajet d'hier soir, connect fait maintenant les deux.

## Ce que ne fait pas comma connect

- **Il ne diffuse pas pendant que vous roulez.** Le direct est pour une voiture garée.
- **Il ne dessine pas les surimpressions d'openpilot.** Le direct et les extraits sont de la vidéo de caméra, sans la trajectoire, les voies, les alertes ni la vitesse que vous voyez sur l'écran du comma.
- **Il a besoin d'Internet.** Le direct a besoin du Wi‑Fi de la maison ou de la LTE de prime, et les trajets doivent être envoyés avant que connect puisse les montrer.
- **Sans prime, il oublie au bout de 3 jours.** Ensuite, connect ne montre plus le trajet, même si le comma l'a encore.

Rien de tout cela n'est un défaut. connect est un service cloud pour voir votre voiture et vos trajets d'où que vous soyez.

## Ce que fait l'accès local

L'accès local, c'est récupérer la vidéo sur le comma lui-même, sur le même réseau, plutôt que sur les serveurs de comma.

### SSH : les fichiers bruts

Chaque trajet openpilot est enregistré sur le comma en segments d'une minute, chacun avec ses propres fichiers : `fcamera.hevc` (route), `ecamera.hevc` (route grand angle), `dcamera.hevc` (conducteur), `qcamera.ts` (le petit aperçu) et les journaux. Par SSH, vous pouvez copier n'importe lequel tant que le comma l'a encore ; il supprime les trajets les plus anciens quand la place manque. C'est la façon d'obtenir de la vidéo en pleine résolution pour le développement ou vos propres archives, mais ce sont des fichiers HEVC d'une minute, pas un extrait à partager. Notre guide pour [télécharger les images du comma](/fr/blog/download-comma-dashcam-footage) vous accompagne pas à pas.

### CommaView : Live View et Enregistrements sur Android

CommaView est une application Android et un petit runtime sur le comma, `commaviewd`, qui envoie la caméra et les données de conduite à votre téléphone sur votre propre réseau local : votre Wi‑Fi, ou un point d'accès dans la voiture, celui de votre téléphone, de votre système multimédia ou du comma.

- **Live View, pendant que vous roulez.** La caméra route avec l'écran propre à votre fork dessiné dessus, comme le dessine le comma four ou le comma 3X, ou l'écran de CommaView, sur un téléphone, une tablette sur le tableau de bord ou un système multimédia Android. L'écran du comma four mesure 1,9 pouce ; celui de votre téléphone est bien plus grand.
- **Des enregistrements sur votre téléphone.** Touchez Enregistrer dans Live View et, une fois garé, CommaView télécharge la vidéo du comma pour ce passage, jusqu'à 10 minutes, et dessine par-dessus l'écran de votre fork sur le téléphone. Ou gardez une copie en direct de ce que montre Live View, en 720p ou 1080p, sans limite de 10 minutes. Lisez-la, partagez-la ou ouvrez-la dans une autre application.
- **Passer en direct.** Diffusez ce que montre Live View, la route et les surimpressions, sur votre chaîne YouTube ou n'importe quel serveur RTMP, en 720p ou 1080p.
- **Pas d'abonnement, pas d'envoi en ligne.** Live View et les enregistrements vont de votre comma à votre téléphone, et les enregistrements y restent jusqu'à ce que vous les supprimiez. Les caméras de votre comma ne vont qu'aux téléphones et systèmes multimédias qui lui sont associés.

Il fonctionne avec le comma 3X et le comma four, sous openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 et carrotpilot, et sur d'autres forks au mieux. [Quels forks, et ce que Live View dessine sur chacun](/fr/forks).

## Côte à côte

| Fonction | comma connect | CommaView |
| --- | --- | --- |
| Vidéo en direct | Caméras route et conducteur, à l'arrêt | Caméra route, pendant que vous roulez |
| Surimpressions de conduite | Non | L'écran de votre fork, ou celui de CommaView |
| Où va la vidéo | Par Internet, regardée dans connect | Votre propre réseau local (Wi‑Fi ou point d'accès), vers vos téléphones associés |
| Il faut | Internet, un comma power pour le direct | Un téléphone, une tablette ou un système multimédia Android sur le même réseau |
| Extraits | N'importe quelle partie d'un trajet, en MP4 découpé sur le comma et téléchargé depuis connect | Ce que vous avez enregistré dans Live View : une relecture jusqu'à 10 minutes, ou une copie en direct, avec les surimpressions |
| Durée de conservation | 3 jours, un an avec prime | Sur votre téléphone jusqu'à ce que vous les supprimiez |
| Coût | Gratuit, ou prime 24 $ / lite 14 $ par mois | Pas d'abonnement ; CommaView est en bêta sur invitation |

## Utilisez les deux

Ils ne se disputent pas le même rôle. Gardez connect pour voir la voiture de n'importe où et pour les trajets que vous voulez dans le cloud ; utilisez CommaView pour regarder la route avec les surimpressions de votre fork sur un plus grand écran, enregistrer ce que vous avez vu et le diffuser. Un passager peut regarder Live View pendant que vous roulez ; si vous conduisez seul, traitez-le comme l'écran du comma lui-même et gardez les yeux sur la route.

## Pour aller plus loin

- [comma prime](https://comma.ai/prime), pour les offres de connect et la durée de conservation des trajets
- [openpilot 0.11.2](https://blog.comma.ai/0112release/), pour le direct et les extraits
- [Comment télécharger les images du comma](/fr/blog/download-comma-dashcam-footage), par SSH
- [Installer CommaView](/fr/guides/setup)

CommaView est non officiel, et n'est ni affilié à comma.ai, sunnypilot ou aucun des forks d'openpilot avec lesquels il fonctionne, ni approuvé par eux. C'est un logiciel en bêta et non un système de sécurité : ne le laissez jamais vous distraire de la conduite.
