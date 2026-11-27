---
title: "Comment télécharger les images de dashcam d'un comma"
description: "Un guide pratique sur les fichiers vidéo du comma, les différences entre comma 3, 3X et four, et les façons les plus sûres d'exporter les images d'un parcours."
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma device video
  - dashcam footage
  - openpilot tools
  - SSH
heroLabel: "Guide comma"
draft: false
---

Besoin de récupérer la vidéo d'un comma ? Les chemins habituels sont comma connect, Openpilot Toolkit, ou un accès direct par SSH/SFTP.

Ce qui piège souvent, c'est l'organisation des fichiers. Les appareils comma enregistrent les parcours openpilot en courts segments, pas en un seul énorme extrait de dashcam. Chaque segment peut contenir des fichiers de caméra bruts, une vidéo d'aperçu et des journaux de parcours. Une fois que c'est compris, l'export devient beaucoup moins mystérieux.

Une remarque importante d'emblée : un comma peut être utile pour filmer la route, déboguer et revoir des parcours, mais ce n'est pas un remplaçant direct d'une vraie dashcam.

## Les appareils comma sont de bonnes caméras, pas des dashcams parfaites

Une vraie dashcam est conçue pour capturer des preuves : démarrage rapide, résistance aux accidents, mode parking, export de fichiers simple, options de caméra arrière et stockage amovible.

Un comma est conçu pour faire tourner openpilot. Il enregistre des données de parcours parce qu'elles servent aux modèles de conduite, au débogage, aux aperçus de connect et au développement. Ces images peuvent avoir de la valeur, mais avec des compromis :

- les images peuvent être plus difficiles à récupérer que de retirer une carte SD
- un accident ou une coupure de courant soudaine peut faire perdre les images récentes
- l'enregistrement en mode parking n'est pas l'objectif principal de la conception
- aucune dashcam tournée vers l'arrière n'est incluse
- les anciennes données locales sont supprimées quand l'appareil manque de place

Si le but est d'avoir des images d'accident fiables, utilisez une vraie dashcam. Si le but est d'obtenir les images d'un parcours openpilot, de revoir pour le développement ou d'exporter de la vidéo en local, la méthode comma vaut la peine d'être apprise.

## Quels fichiers openpilot enregistre-t-il ?

La documentation officielle d'openpilot sur la journalisation décrit les parcours comme des segments d'une minute. Pour chaque segment, un openpilot récent enregistre ces types de fichiers :

| Fichier | Contenu |
| --- | --- |
| `fcamera.hevc` | vidéo de la caméra route, H.265/HEVC |
| `ecamera.hevc` | vidéo de la caméra route grand angle, H.265/HEVC |
| `dcamera.hevc` | vidéo de la caméra conducteur/habitacle, H.265/HEVC |
| `qcamera.ts` | aperçu H.264 en plus basse résolution de la caméra route |
| `rlog.zst` | journaux complets du parcours |
| `qlog.zst` | journaux du parcours réduits/décimés |

La vidéo affichée dans comma connect est le `qcamera.ts` en plus basse résolution. Les images en pleine résolution sont dans les fichiers HEVC, et il peut falloir les envoyer manuellement via connect ou les copier directement depuis l'appareil.

Des parcours plus anciens, des forks plus anciens ou une documentation plus ancienne peuvent montrer `rlog`/`qlog` sans `.zst`, ou d'anciens noms de journaux en `.bz2`. Pour un openpilot récent, utilisez les noms ci-dessus.

## comma 3, comma 3X et comma four : qu'est-ce qui change ?

On mélange souvent deux choses distinctes : le matériel de caméra et l'organisation des fichiers.

Le matériel de caméra diffère selon la génération :

| Appareil | Caméras et stockage |
| --- | --- |
| comma 3 | Trois caméras 1080p avec HDR 120 dB. La documentation de la communauté cite plusieurs variantes de stockage : 1 To, 250 Go, 64 Go (tardif) et 32 Go (premiers modèles). |
| comma 3X | La même disposition à trois caméras que le comma 3, des capteurs d'image OX03C10 améliorés, HDR 140 dB, et en général 128 Go de stockage. |
| comma four | Selon comma, il a la même puissance de calcul, les mêmes capteurs et les mêmes fonctions que le comma 3X, dans un boîtier bien plus petit. Le système à trois caméras tient dans l'encombrement de l'écran de 1,9 pouce, avec deux caméras tournées vers la route et une caméra d'habitacle à vision nocturne. comma annonce 128 Go de stockage et 10 heures d'images. |

Les remarques sur les fichiers s'appliquent aux trois. CommaView lui-même ne fonctionne qu'avec le comma 3X et le comma four.

Pour un openpilot récent, l'organisation pratique des fichiers est la même sur tout le matériel comma. Les fichiers de segment actuels sont `fcamera.hevc`, `ecamera.hevc`, `dcamera.hevc`, `qcamera.ts`, `rlog.zst` et `qlog.zst`.

Les caméras peuvent donc changer physiquement tandis que les noms à l'export restent familiers. `fcamera.hevc` est la caméra route. `ecamera.hevc` est la caméra route grand angle. `dcamera.hevc` est la caméra conducteur/habitacle.

Si vous utilisez un fork personnalisé, vérifiez sur l'appareil avant de supposer que chaque fichier est présent. Les forks peuvent changer les réglages d'enregistrement, et l'enregistrement de la caméra conducteur/habitacle peut dépendre des réglages de l'appareil.

## Où sont stockés les fichiers en local ?

Sur le matériel comma, la racine actuelle des journaux d'openpilot est :

```text
/data/media/0/realdata
```

Dans ce dossier, chaque segment de parcours a son propre dossier horodaté, par exemple :

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

C'est dans ce dossier que vous trouverez des fichiers comme :

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

Pour un accès direct par SSH/SFTP, c'est le dossier par lequel commencer. La documentation officielle explique comment se connecter en SSH à un comma 3X ou un comma four, et openpilot utilise `/data/media/0/realdata` comme racine des journaux sur l'appareil.

## Option 1 : utiliser comma connect

Pour les trajets récents, comma connect est en général le point de départ le plus simple.

Utilisez connect quand :

- le parcours est récent
- l'appareil a bien envoyé le parcours
- la vidéo d'aperçu suffit
- vous voulez une interface web plutôt que SSH
- vous n'avez besoin que de quelques extraits ou fichiers

C'est aussi dans connect que beaucoup repèrent d'abord le parcours et les numéros de segment dont ils ont besoin. Le piège, c'est la conservation : connect peut cesser de montrer un parcours avant que l'appareil l'ait supprimé en local. Si connect ne montre plus un parcours mais que les fichiers existent encore sur l'appareil, SSH/SFTP peut encore les récupérer.

N'oubliez pas non plus que les aperçus de connect reposent sur `qcamera.ts`. S'il vous faut les images en pleine résolution, vérifiez que les fichiers vidéo complets sont envoyés, ou récupérez directement les fichiers HEVC bruts.

## Option 2 : utiliser Openpilot Toolkit

Openpilot Toolkit est un outil de la communauté qui peut rendre l'export local moins pénible. Il aide à configurer SSH, à parcourir les fichiers, à prévisualiser la vidéo des trajets et à faire un export brut.

Utilisez Openpilot Toolkit quand :

- vous voulez une interface graphique
- vous ne voulez pas écrire vous-même les commandes SSH
- vous avez besoin d'aide pour configurer les clés
- vous êtes sous Windows ou Android
- vous voulez parcourir et exporter les images des parcours plus directement

Pour beaucoup, c'est le meilleur compromis : plus de contrôle que connect, moins d'effort que le travail manuel au terminal.

## Option 3 : utiliser SSH ou SFTP directement

L'accès direct par SSH/SFTP donne le plus de contrôle et le moins d'accompagnement.

Dans les grandes lignes, l'accès SSH consiste en général à :

1. Créer ou utiliser un compte GitHub avec des clés SSH.
2. Activer SSH dans les paramètres de l'appareil comma.
3. Saisir votre nom d'utilisateur GitHub sur le comma pour qu'il récupère vos clés publiques.
4. Se connecter en tant qu'utilisateur `comma` sur le port `22`.

Une fois connecté, parcourez ou copiez depuis :

```text
/data/media/0/realdata
```

Utilisez l'accès direct quand :

- il vous faut les fichiers bruts `fcamera.hevc`, `ecamera.hevc` ou `dcamera.hevc`
- connect ne montre pas le fichier dont vous avez besoin
- vous voulez archiver un parcours entier
- vous êtes à l'aise avec des clients SFTP comme FileZilla ou WinSCP
- vous êtes à l'aise avec `ssh`, `scp` ou `rsync`

Les fichiers `.hevc` bruts se lisent souvent dans VLC. Si une autre application a besoin de MP4, remuxez avec ffmpeg plutôt que de réencoder, quand c'est possible.

## Quelle méthode choisir ?

Choisissez comma connect si le trajet est récent et qu'une revue normale du parcours suffit.

Choisissez Openpilot Toolkit si vous voulez une méthode locale plus accueillante, sans faire chaque étape SSH/SFTP à la main.

Choisissez SSH ou SFTP s'il vous faut des fichiers bruts, d'anciens fichiers locaux, des archives de parcours complètes, ou un contrôle direct sur ce qui est copié.

## La place de CommaView

CommaView est une application Android pensée d'abord pour le local : diffusion de la caméra du comma, surimpressions, installation du runtime, enregistrements et relectures.

Il touche au même monde de l'accès local à la caméra, mais ce n'est ni comma connect, ni Openpilot Toolkit, ni une dashcam classique. Il ne doit servir ni d'aide à la conduite, ni de seul système de capture de preuves dans un véhicule.

CommaView fonctionne avec le comma 3X et le comma four, sous openpilot ou un [fork pris en charge](/fr/forks) : sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 ou carrotpilot. Le comma 3 n'est pas pris en charge : comma l'a placé sur une version d'openpilot figée, maintenue à long terme, dont CommaView ne peut pas tirer ses surimpressions ([pourquoi](/fr/#faq-comma-3)).

## Pour aller plus loin

- Documentation officielle d'openpilot sur la journalisation (en anglais) : [Logging](https://docs.comma.ai/concepts/logs/)
- Documentation SSH officielle de comma (en anglais) : [se connecter à un comma 3X ou un comma four](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect : [comma.ai/connect](https://comma.ai/connect)
- Wiki d'openpilot : [Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma : [Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit : [page du projet](https://spektor56.github.io/OpenpilotToolkit/)
