---
title: "Enregistrer un trajet depuis Live View"
description: "Touchez Enregistrer dans Live View, puis créez la relecture du trajet une fois garé : la vidéo propre du comma avec l'écran de votre fork dessiné par-dessus, gardée sur votre téléphone."
topic: recordings
order: 1
kind: walkthrough
lede: "**Enregistrer** dans Live View garde un trajet. Sauf si vous choisissez autrement, il crée une **relecture** : une fois garé, CommaView télécharge la vidéo propre du comma pour ce que vous avez enregistré, jusqu'à 10 minutes, et dessine l'écran de conduite par-dessus sur votre téléphone. Rien n'est envoyé en ligne : les enregistrements restent sur votre téléphone jusqu'à ce que vous les supprimiez."
parked: true
updated: 2026-11-27
needs:
  - title: "Live View fonctionne"
    text: "CommaView sur votre téléphone, associé à votre comma. Pas encore ? [Installer CommaView](/fr/guides/setup), puis [ouvrir Live View](/fr/guides/live-view)."
  - title: "La voiture allumée"
    text: "Enregistrer démarre une fois que le comma a commencé un trajet : allumez donc d'abord la voiture. Lancez l'enregistrement en position P, avant de partir."
  - title: "De la place sur votre téléphone"
    text: "Une relecture est créée sur votre téléphone, à partir de la vidéo du comma. Paramètres › Enregistrements affiche le stockage utilisé et l'espace libre."
howItWorks:
  - title: "Enregistrer dans Live View"
    text: "Ouvre la fenêtre de capture du comma : il garde les données de l'écran de conduite pendant que vous enregistrez."
    edge: "une fois garé"
  - title: "Créer la relecture"
    text: "Le téléphone télécharge la vidéo du comma pour ce passage, un trajet à la fois."
  - title: "Enregistrements"
    text: "La relecture se lit sur votre téléphone, avec l'écran dessiné par-dessus la vidéo."
steps:
  - id: choose
    title: "Choisir ce que crée Enregistrer"
    body: |
      Touchez **Paramètres**, puis **Enregistrements**. Sous **Enregistrer dans Live View**, **Relecture** est choisi tant que vous ne le changez pas : « La meilleure image : la vidéo propre du comma avec le HUD dessiné par-dessus, créée une fois garé. Jusqu'à 10 minutes par enregistrement. »

      **Copie en direct** garde plutôt ce que montre Live View, sans limite de durée, et **Les deux** crée les deux. Elles ont [leur propre guide](/fr/guides/live-copy).
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Enregistrer dans Live View** : **Relecture**, **Copie en direct** ou **Les deux**."
      - text: "**Relecture** ouvre sa qualité : **Balanced**, **High** ou **Max**. Une qualité plus élevée prend plus de temps et crée des fichiers plus gros."
  - id: start
    title: "Toucher Enregistrer dans Live View"
    body: |
      Voiture allumée et toujours en position P, ouvrez **Live View** et touchez **Enregistrer**. Il affiche un instant **Démarrage de l'enregistrement** pendant que CommaView se synchronise avec le trajet, puis son minuteur défile.
    screen: phone-live-view
    clip: record
    pins:
      - target: record-button
        text: "**Enregistrer**. Sur une tablette, un système multimédia ou un téléphone à l'horizontale, il est dans le rail."
    warn: "Lancez l'enregistrement avant de partir, ou laissez un passager s'en charger. Ne manipulez pas CommaView en conduisant."
  - id: recording
    title: "Le laisser enregistrer"
    body: |
      Pendant l'enregistrement, Enregistrer affiche la durée et **Détails** indique **Enregistrement ·** et la durée. Touchez à nouveau Enregistrer pour arrêter. Une relecture s'arrête aussi toute seule à 10 minutes, et quand Live View se ferme.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Enregistrer, avec son minuteur. Touchez-le à nouveau pour arrêter."
      - target: recording
        text: "**Enregistrement ·** la durée, dans **Détails**."
      - text: "**Garder** conserve les 3 dernières minutes et la minute suivante, sans Enregistrer. C'est copié sur votre téléphone une fois garé."
    note: "**Garder** n'apparaît que là où le runtime de votre comma liste ses trajets. Un toucher pendant cette minute suivante garde une minute de plus, jusqu'à 10 minutes. Laissez faire un passager pendant que vous conduisez."
  - id: make-replay
    title: "Se garer, puis créer la relecture"
    body: |
      Une fois garé, ouvrez **Enregistrements** depuis la barre du bas (le rail sur un plus grand écran). Le trajet enregistré indique **À traiter**. Ouvrez-le et touchez **Créer la relecture** : l'application indique « Relecture en file. Suivez-la dans File. »

      Le comma ne partage un trajet que pendant que la voiture est en position P avec openpilot désengagé : laissez donc la voiture allumée et votre téléphone sur le réseau du comma jusqu'à ce que la relecture soit créée. Sans câble d'alimentation permanente, éteindre la voiture éteint aussi le comma.
    screen: recordings-make-replay
    pins:
      - text: "**Créer la relecture**."
      - target: queue
        text: "**File** affiche chaque relecture en cours de création, une à la fois, avec Pause, Réessayer et Supprimer."
    note: "**Créer la relecture** peut mettre jusqu'à une minute à apparaître une fois garé : un comma qui indiquait rouler est interrogé à nouveau une minute plus tard."
  - id: watch
    title: "La regarder dans Enregistrements"
    body: |
      Une fois créée, l'application indique **Relecture créée** avec son nombre d'images, et le trajet se lit dans Enregistrements. Touchez-le pour le regarder, en plein écran si vous voulez.
    screen: phone-recordings
    pins:
      - text: "La relecture du trajet, regroupée sous le jour."
      - target: filter
        text: "**Filtrer** : **Tous les trajets**, **Prêts** ou **À traiter**, et quel comma."
check: "La ligne du trajet n'indique plus **À traiter**, et il se lit quand vous le touchez. Pour le partager ou l'enregistrer ailleurs, voyez [Partager et exporter des enregistrements](/fr/guides/export-share)."
fixes:
  - q: "« L'enregistrement peut démarrer une fois que le comma a commencé un trajet. »"
    a: "Le comma est à l'arrêt. Allumez la voiture et attendez qu'openpilot démarre, puis touchez à nouveau Enregistrer."
  - q: "« CommaView se synchronise encore avec ce trajet. Réessayez Enregistrer dans un instant. »"
    a: "Enregistrer a besoin des horodatages d'images du comma, qui arrivent avec ses données de conduite. Ils n'étaient pas arrivés en 5 secondes. Attendez un instant et touchez à nouveau Enregistrer."
  - q: "« CommaView ne reçoit pas les données de conduite du comma. Vérifiez la connexion, puis réessayez Enregistrer. »"
    a: "La vidéo s'affiche peut-être encore, mais les données de conduite se sont arrêtées. Vérifiez que votre téléphone est toujours sur le Wi‑Fi ou le point d'accès du comma, puis réessayez. Si Live View indique **Les données de la voiture n'arrivent pas**, redémarrez le comma."
  - q: "« Redémarrez d'abord le comma : CommaView a été installé, mis à jour ou réparé, et enregistre à nouveau après un redémarrage. »"
    a: "Redémarrez le comma quand la voiture est en position P, puis enregistrez à nouveau."
  - q: "« Le stockage d'enregistrement est plein. Libérez de l'espace, puis réessayez Enregistrer. »"
    a: "Supprimez dans Enregistrements les trajets dont vous n'avez plus besoin, ou choisissez un autre stockage dans **Paramètres › Enregistrements › Stockage** avec **Modifier**."
  - q: "« Le comma n'a plus de place pour les données du HUD de ce trajet (environ 55 minutes d'enregistrements). Enregistrez à nouveau lors de votre prochain trajet. »"
    a: "Le comma garde les données du HUD d'environ 55 minutes d'enregistrements par trajet. Créez les relectures de ce que vous avez enregistré, et enregistrez à nouveau au prochain trajet."
  - q: "« Passez en position P pour créer cette relecture », ou le trajet indique « En attente de votre arrêt »"
    a: "Le comma ne partage un trajet qu'à l'arrêt, avec openpilot désengagé. Mettez la voiture en position P et laissez-la allumée. La relecture attend et redemande toutes les 15 secondes ; après 30 minutes de conduite, elle s'arrête avec « La voiture roulait encore, donc le comma n'a pas pu partager ce trajet. Réessayez une fois garé. » Touchez **Réessayer** dans File une fois garé."
  - q: "« Connectez-vous à Comma Chameleon pour créer cette relecture »"
    a: "Votre téléphone n'a pas pu joindre le comma qui a enregistré le trajet (le message nomme le vôtre). Connectez votre téléphone au Wi‑Fi ou au point d'accès du comma, puis touchez **Réessayer** dans File. Voyez [CommaView ne trouve pas votre comma](/fr/guides/comma-not-found)."
  - q: "« Trajet supprimé du comma »"
    a: "Le comma a supprimé ce trajet pour faire de la place aux plus récents avant que sa relecture soit créée : elle ne peut donc plus l'être. Vous pouvez supprimer l'enregistrement. Un trajet qui indique **Créez la relecture vite** en est proche : créez-la tant que c'est possible."
  - q: "La relecture indique « HUD manquant sur 2 min »"
    a: "Le comma n'a pas gardé les données de l'écran de conduite pour une partie de l'enregistrement. La relecture affiche **Données du HUD indisponibles** sur ce passage, et l'information **Données du HUD** du lecteur indique sur quelle durée."
  - q: "« Relecture créée : 4 860 images. Elle s'arrête tôt, là où le comma a perdu l'alimentation. »"
    a: "Le comma a perdu l'alimentation à la fin du trajet, donc ses derniers instants n'ont pas été gardés. Enregistrements peut afficher **Votre comma a peut-être perdu l'alimentation à la fin d'un trajet** ; son **Comment corriger** explique l'alimentation du comma et le réglage du temps à l'arrêt."
related: [live-copy, export-share, live-view]
---

## Relecture, copie en direct ou les deux

| Enregistrer crée | Ce que vous obtenez |
| --- | --- |
| **Relecture** (par défaut) | La vidéo propre du comma avec l'écran de conduite dessiné par-dessus, créée une fois garé. La meilleure image, jusqu'à 10 minutes par enregistrement, tant que le comma a encore le trajet. Les caméras route et grand angle seulement : il n'y a pas de caméra conducteur dans une relecture. |
| **Copie en direct** | Ce que montre Live View, gardé sur votre téléphone pendant que vous roulez et prêt dès que vous vous arrêtez. Aucune relecture à créer et aucune limite de durée. [Enregistrer une copie en direct](/fr/guides/live-copy). |
| **Les deux** | Une copie en direct immédiate, et la relecture après le trajet. La relecture garde sa limite de 10 minutes. |

## Où sont gardés les enregistrements

Les enregistrements restent sur votre téléphone. **Paramètres › Enregistrements › Stockage** affiche le stockage utilisé et l'espace libre, et **Modifier** en choisit un autre quand votre téléphone en a un. La sauvegarde d'Android et le transfert vers un nouveau téléphone les laissent de côté. **Envoyer à CommaView** n'envoie que les données propres du comma pour un trajet, et seulement quand vous l'envoyez.

## Sécurité

Lancez Enregistrer avant de partir, et créez les relectures une fois garé. Ne manipulez pas CommaView en conduisant : gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande. CommaView n'est ni une dashcam ni un système de sécurité, et un enregistrement peut échouer.
