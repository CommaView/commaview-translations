---
title: "CommaView fonctionne désormais avec StarPilot, xnor et AdventurePilot"
description: "CommaView 0.0.163 ajoute l'openpilot de xnor-tech et AdventurePilot, après StarPilot dans 0.0.162. Ce que chaque fork d'openpilot montre dans Live View sur comma 3X et comma four."
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "Notes de version"
draft: false
---

CommaView fonctionne désormais avec cinq builds d'openpilot : **openpilot**, **sunnypilot**, **StarPilot**, **l'openpilot de xnor-tech** (ses builds xnor et rx) et **AdventurePilot**. StarPilot est arrivé avec CommaView 0.0.162, et la bêta 0.0.163 ajoute xnor et AdventurePilot. Sur chacun, Live View dessine l'écran propre au fork sur votre téléphone Android, votre tablette ou votre système multimédia, avec ce que ce fork y ajoute.

Jusqu'ici, l'installation sur ces forks s'arrêtait sur « unsupported upstream remote ». Avec l'application 0.0.163 et son runtime, elle installe et associe comme sur openpilot.

## Ce que chaque fork montre dans Live View

CommaView ne devine rien d'après le nom du fork. Le runtime sur votre comma indique à l'application ce que l'écran du fork ajoute, et l'application le dessine sur l'écran du comma four, celui du comma 3X ou celui de CommaView.

| Fork | Ce que dessine CommaView |
| --- | --- |
| openpilot | Les écrans du comma four et du comma 3X, ou les surimpressions propres à CommaView |
| sunnypilot | L'écran de sunnypilot : MADS, l'assistant de limitation de vitesse, la trajectoire arc-en-ciel, les indicateurs d'angle mort et ses ajouts pour le comma 3X |
| StarPilot | Les couleurs, widgets, alertes et choix de caméra de StarPilot |
| xnor | L'écran d'openpilot sur les builds xnor, celui de sunnypilot sur rx, et la teinte du volant de rx pour Rivian |
| AdventurePilot | L'écran de sunnypilot avec son indicateur de centrage dans la voie, sa puce CURVE et la teinte du mode de direction |

## StarPilot

StarPilot montre ses modes de conduite par la couleur, et CommaView reprend les couleurs choisies par StarPilot : sa bordure, sa trajectoire et ses widgets, ses alertes et son choix de caméra, caméra conducteur comprise. Désactivez d'abord le réglage **Disable Logging** de StarPilot : il arrête l'encodeur vidéo dont Live View tire son flux.

## L'openpilot de xnor-tech : xnor et rx

L'openpilot de xnor-tech existe en deux builds issus d'un même dépôt. Ses branches **xnor** utilisent l'écran d'openpilot et ses branches **rx** celui de sunnypilot, chacune avec les portages de véhicules de xnor-tech. CommaView détecte celle que fait tourner votre comma et dessine cet écran, avec les alertes telles que le comma les écrit.

Sur un Rivian sous rx, le volant indique comment la voiture braque : vert quand elle braque par l'angle, bleu quand elle braque par le couple. CommaView dessine les mêmes couleurs sur le volant du comma four et sur le bouton du mode expérimental du comma 3X.

## AdventurePilot

AdventurePilot est un fork de sunnypilot avec ses propres portages de véhicules. CommaView dessine l'écran de sunnypilot avec ce qu'AdventurePilot y ajoute :

- son **indicateur de centrage dans la voie**, une pastille avec la poussée et le décalage sur l'écran du comma 3X, et une barre compacte sur celui du comma four ;
- la **puce CURVE** sur l'écran du comma 3X, qui clignote quand le contrôle de vitesse en virage agit ;
- la **teinte du mode de direction** sur le volant, et une barre de couple qui montre l'accélération latérale quand un Rivian braque par son canal d'angle.

## Comment l'obtenir

CommaView est en bêta sur invitation. Si vous en faites partie, l'application propose d'elle-même la mise à jour 0.0.163. Une fois l'application à jour, mettez à jour le runtime de votre comma depuis l'application, puis redémarrez le comma quand elle le demande. Les mises à jour du runtime attendent que la voiture soit en position P et openpilot désengagé, pour ne jamais interrompre un trajet.

Nouveau sur CommaView ? Le [guide d'installation](/fr/guides/setup) explique comment installer l'application et connecter votre comma.

## Ce qui n'a pas changé

- CommaView fonctionne sur le **comma 3X** et le **comma four**. Le comma 3 n'est toujours pas pris en charge, y compris les builds comma 3 des forks comme xnor-c3 ([pourquoi](/fr/#faq-comma-3)).
- CommaView ne change jamais la façon dont votre fork conduit. Il ajoute un petit runtime à côté et un petit hook dans son interface à l'écran, pour pouvoir dessiner la même trajectoire, les mêmes voies et les mêmes alertes.
- Sur un fork que CommaView ne prend pas encore en charge, l'installation s'arrête et laisse votre comma tel qu'il était. Vous pouvez demander votre fork sur le tableau des fonctionnalités de my.commaview.com.

## Pour aller plus loin

- [Quels forks d'openpilot fonctionnent avec CommaView](/fr/forks), et ce que chacun montre
- [Les nouveautés](/fr/whats-new) de chaque version
- [Comment se font les versions de CommaView](/fr/guides/releases)

CommaView est non officiel et n'est affilié ni à comma.ai, ni à sunnypilot, StarPilot, xnor-tech ou AdventurePilot. C'est un logiciel en bêta et non un système de sécurité : ne le laissez jamais vous distraire de la conduite.
