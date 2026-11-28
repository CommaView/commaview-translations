---
title: "Un comma est-il une dashcam ? Utile, mais pas un remplaçant"
description: "Les images du comma après openpilot 0.11.2, la sécurité d'abord : fichiers de parcours, conservation et extraits connect, stockage local, accidents, mode parking et dashcams."
date: 2026-11-06
slug: is-comma-a-dashcam
tags:
  - comma dashcam
  - comma device video
  - dashcam footage
  - openpilot
heroLabel: "Dashcam : la réalité"
draft: false
---

Un comma peut enregistrer des images utiles de la route et de l'habitacle. Cela n'en fait pas un remplaçant direct d'une vraie dashcam.

Les images peuvent servir à revoir un parcours, à déboguer, à exporter, et à donner du contexte à un incident. Mais une vraie dashcam repose sur d'autres principes : une capture de preuves qui résiste aux accidents, un stockage amovible simple, un mode parking, une caméra arrière, et une récupération aussi simple qu'un appareil électroménager.

Si des images fiables d'accident ou pour l'assurance comptent, utilisez une vraie dashcam à côté du comma. Réponse ennuyeuse, bonne réponse.

## Ce qu'enregistre un comma

openpilot enregistre des parcours tant que l'appareil tourne. La documentation actuelle sur la journalisation décrit les parcours comme découpés en segments, avec des fichiers de caméra et de journal comme :

- `fcamera.hevc` — vidéo de la caméra route
- `ecamera.hevc` — vidéo de la caméra route grand angle
- `dcamera.hevc` — vidéo de la caméra conducteur/habitacle
- `qcamera.ts` — vidéo d'aperçu en plus basse résolution
- `rlog.zst` — journal complet du parcours
- `qlog.zst` — journal réduit du parcours

Ce sont des données très utiles.

Mais ce n'est pas non plus un simple « extrait de dashcam ». C'est la journalisation des parcours d'openpilot : fichiers segmentés, identifiants de parcours, comportement d'envoi, conservation locale, codecs, journaux et outils.

## Où trouver les images

Il y a deux grands endroits où l'on regarde d'abord :

1. **comma connect** pour les trajets récents visibles dans le cloud.
2. **Le stockage local de l'appareil** pour les fichiers encore présents sur le comma.

La [page prime](https://comma.ai/prime) de comma indique que les trajets envoyés sont gardés 3 jours dans connect, ou 1 an avec comma prime. Par défaut, connect montre la vidéo `qcamera` en plus basse résolution ([documentation de comma sur les journaux](https://docs.comma.ai/concepts/logs/)).

Depuis [openpilot 0.11.2](https://blog.comma.ai/0112release/) (octobre 2026), connect peut aussi découper un extrait dans une partie d'un trajet : le comma le réencode en MP4 tant qu'il reste allumé, et vous le téléchargez depuis connect. Obtenir un extrait partageable est donc bien plus simple qu'avant.

Le stockage local d'openpilot, c'est autre chose. Sur le matériel comma actuel, les données de parcours se trouvent en pratique sous `/data/media/0/realdata/`. Mais le stockage local n'est pas infini. openpilot fait le ménage quand la place manque, les anciens parcours ne sont donc pas une archive permanente.

Si quelque chose compte, mettez-le de côté rapidement.

## Pourquoi on utilise quand même les images du comma

Les images du comma peuvent être vraiment utiles.

Bons usages :

- revoir ce qui s'est passé sur un parcours
- déboguer le comportement d'openpilot
- vérifier le contexte caméra/journal
- exporter des extraits ou des fichiers HEVC bruts
- partager des exemples pour le développement ou l'assistance
- alimenter des flux de relecture ou de test

Si vous avez déjà un comma, ignorer ces images serait dommage. Elles ont de la valeur.

L'erreur, c'est de croire que « de la valeur » veut dire « le même rôle qu'une vraie dashcam ».

## Pourquoi il ne remplace pas une vraie dashcam

Une vraie dashcam est d'abord conçue pour capturer des preuves.

Cela veut souvent dire : un stockage simple, une récupération rapide, des modes parking, des options de caméra arrière ou intérieure, un fonctionnement autonome, et un usage pensé pour mettre des extraits de côté après un événement.

Un comma est conçu pour faire tourner openpilot. Les données de caméra existent parce qu'openpilot a besoin de journalisation, de développement de modèles, de débogage, de revoir les parcours et des aperçus de connect.

Ces priorités recoupent les besoins d'une dashcam, mais elles ne sont pas identiques.

## Les points de risque

### Accidents et coupures de courant

Si l'appareil perd l'alimentation, est endommagé ou s'éteint au mauvais moment, les images récentes peuvent être plus difficiles à récupérer, ou incomplètes.

Cela ne veut pas dire que les images du comma sont inutiles à chaque incident. Cela veut dire qu'elles ne doivent pas être votre seul plan pour les preuves.

### Mode parking

Les vraies dashcams vendent souvent le mode parking avec kit de branchement permanent comme une fonction phare.

openpilot 0.11.2 vous permet de diffuser en direct dans connect les caméras route et conducteur d'une voiture garée, avec une connexion Internet et un comma power installé. L'article de comma le présente comme un moyen de voir ce qui se passe autour de la voiture ; il ne le présente pas comme un enregistreur d'événements en mode parking.

Considérez la surveillance en stationnement comme le domaine d'une vraie dashcam, sauf si vous avez une installation très précise, validée, et que vous en comprenez les risques.

### Couverture arrière

Les caméras route, route grand angle et conducteur/habitacle du comma ne valent pas une dashcam tournée vers l'arrière.

Si la vue arrière compte, utilisez du matériel qui filme l'arrière.

### Stockage et export laborieux

Une dashcam vise en général une récupération simple des extraits, par microSD, application ou écran.

Avec le comma, récupérer peut impliquer les fenêtres de visibilité de connect, l'envoi manuel, les identifiants de segment, SSH/SFTP, les fichiers HEVC, le ménage local, VLC/ffmpeg/remuxage ou des outils d'aide. Les nouveaux extraits de connect aident, mais le comma doit rester allumé pendant qu'il en produit un, et le trajet doit encore être là.

Pour des utilisateurs techniques, ça va. Ce n'est pas simple comme un appareil électroménager.

## Quand les images du comma peuvent suffire

Les images du comma peuvent suffire pour :

- garder une trace occasionnelle de la route
- revoir des parcours openpilot
- déboguer et tester
- le support au développement
- un export local tant que le parcours existe
- revoir un événement peu après qu'il s'est produit

C'est une liste solide.

Cela ne fait toujours pas du comma votre seul enregistreur de preuves sérieux.

## Quand ajouter une dashcam

Utilisez une vraie dashcam si vous tenez à :

- des images fiables d'accident ou pour l'assurance
- la surveillance en stationnement
- la couverture arrière
- la récupération la plus simple possible
- un stockage amovible
- un enregistrement indépendant si le comma perd l'alimentation
- un outil plus simple pour les conducteurs non techniques

Ce duo n'a rien de bizarre. Un comma peut être excellent pour openpilot pendant qu'une dashcam s'occupe de la capture de preuves, sans surprise.

## La place de CommaView

CommaView est une application Android et un petit runtime sur le comma. Il montre en direct la caméra route du comma, avec les surimpressions de votre fork, sur votre téléphone, votre tablette ou votre système multimédia Android, sur votre propre réseau, et il garde sur votre téléphone ce que vous enregistrez. Touchez Enregistrer dans Live View et, une fois garé, il télécharge la vidéo du comma pour ce passage, jusqu'à 10 minutes, et dessine les surimpressions par-dessus ; ou gardez une copie en direct de ce que montre Live View, sans limite de 10 minutes. Rien n'est envoyé en ligne, et les enregistrements restent sur votre téléphone jusqu'à ce que vous les supprimiez. Il enregistre quand vous touchez Enregistrer, pas tout seul : il n'aide donc pas pour un événement que vous n'avez pas vu venir.

Obtenir un extrait de ce que vous avez vu devient ainsi bien plus simple. Cela ne transforme pas un comma en dashcam critique pour la sécurité.

Il ne garantit pas la conservation des preuves.

Ce n'est pas une aide à la conduite.

Et il ne fonctionne qu'avec le comma 3X et le comma four, pas le comma 3. CommaView est non officiel, et n'est ni affilié à comma.ai ni approuvé par comma.ai.

## Liste pratique après un incident

Pas un conseil juridique, juste un tri pratique :

1. Arrêtez-vous et occupez-vous d'abord de la sécurité et des urgences.
2. Ne comptez pas uniquement sur la conservation de connect.
3. Mettez de côté et exportez les segments de parcours concernés dès que possible.
4. Si vous utilisez connect, repérez le parcours et la plage horaire dont vous avez besoin.
5. Si connect ne montre pas les fichiers mais que l'appareil les a encore, utilisez SSH/SFTP avec l'accord du propriétaire, ou un outil local de confiance.
6. Gardez les fichiers d'origine si possible.
7. Évitez toute modification destructive ou tout ménage tant que les images importantes ne sont pas copiées.
8. Pour les questions juridiques ou d'assurance, adressez-vous aux professionnels compétents.

L'essentiel : agir vite, copier avec soin, et ne pas croire que les images attendront indéfiniment.

## La réponse honnête

Un comma est une caméra et un enregistreur de données utiles pour les parcours openpilot. Il peut fournir un contexte vidéo précieux.

Mais si la question est « puis-je me passer d'une dashcam ? », la réponse prudente est non.

Utilisez les images du comma pour revoir les parcours, déboguer et travailler en local. Utilisez une vraie dashcam quand une capture de preuves fiable est l'exigence.
