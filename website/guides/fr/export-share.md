---
title: "Partager et exporter des enregistrements"
description: "Partagez une relecture ou une copie en direct depuis Enregistrements, ouvrez-la dans une autre application, ou exportez un trajet complet de votre comma en un seul MP4 sur votre téléphone."
topic: recordings
order: 3
kind: walkthrough
lede: "Chaque enregistrement sur votre téléphone est un MP4 que vous pouvez partager, enregistrer dans vos fichiers ou ouvrir dans une autre application, depuis son menu **Actions de l'enregistrement** dans Enregistrements. **Exporter le trajet complet…** copie aussi la vidéo route d'un trajet complet de votre comma vers votre téléphone, telle que le comma l'a enregistrée."
parked: true
updated: 2026-11-27
needs:
  - title: "Un enregistrement sur votre téléphone"
    text: "Une relecture ou une copie en direct dans Enregistrements. Pas encore ? [Enregistrer un trajet](/fr/guides/record) ou [enregistrer une copie en direct](/fr/guides/live-copy)."
  - title: "Pour un trajet complet"
    text: "Le comma qui l'a enregistré, associé à ce téléphone, garé et à portée, et un runtime qui liste ses trajets."
steps:
  - id: open
    title: "Ouvrir l'enregistrement"
    body: |
      Ouvrez **Enregistrements** depuis la barre du bas (le rail sur un plus grand écran) et touchez le trajet. Il s'ouvre dans le lecteur, avec ses informations.
    screen: phone-recordings
    pins:
      - text: "Une relecture. Touchez n'importe quel trajet pour l'ouvrir."
      - target: live-copy-row
        text: "Une copie en direct, marquée **Copie en direct**."
      - target: filter
        text: "**Filtrer** : **Prêts** n'affiche que les trajets qui ont une vidéo à partager."
  - id: actions
    title: "Ouvrir Actions de l'enregistrement"
    body: |
      Dans le lecteur, touchez **Actions de l'enregistrement**, le bouton Plus à côté de l'heure et de la date.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Actions de l'enregistrement**."
      - text: "**Plein écran** l'affiche sur tout l'écran."
  - id: share
    title: "Le partager, ou l'ouvrir dans une autre application"
    body: |
      **Partager** confie la vidéo au menu de partage d'Android, où vous pouvez l'envoyer ou l'enregistrer dans vos fichiers. **Ouvrir dans une autre application** la lit dans un autre lecteur vidéo.

      **Fichiers**, quand un trajet en a plusieurs, liste chaque fichier à partager séparément, comme chaque partie d'un long trajet complet.
    screen: recordings-watch-menu
    pins:
      - target: share
        text: "**Partager** : le menu de partage d'Android."
      - target: open-in
        text: "**Ouvrir dans une autre application**."
      - target: send
        text: "**Envoyer à CommaView…** envoie plutôt un problème avec ce trajet à CommaView : [Envoyer un paquet d'assistance](/fr/guides/support-bundle)."
    note: "Le menu de partage d'Android n'est pas illustré : il vient d'Android, et diffère d'un téléphone à l'autre."
    warn: "Une vidéo peut montrer plus que la route : où et quand vous avez roulé, des plaques d'immatriculation, des visages et des lieux, et la caméra conducteur dans une copie en direct faite avec Caméra cond. activé. Vérifiez-la avant de la partager."
  - id: export
    title: "Exporter un trajet complet"
    body: |
      Pour un trajet enregistré par votre comma, **Actions de l'enregistrement** propose **Exporter le trajet complet…**. Cela copie la caméra route du comma pour tout le trajet dans un seul MP4 sur votre téléphone, exactement tel que le comma l'a enregistré. Il n'a pas de HUD : **Créer la relecture** dessine l'écran de conduite sur les parties enregistrées.
    screen: recordings-watch-menu
    pins:
      - target: export-drive
        text: "**Exporter le trajet complet…**"
  - id: export-sheet
    title: "Vérifier la taille, puis toucher Exporter"
    body: |
      La fenêtre indique quelle part du trajet le comma possède, par exemple **23 min · environ 1,7 GB**, et l'espace libre sur votre téléphone. Touchez **Exporter** : « Export du trajet complet. Il sera sauvegardé dans Enregistrements une fois le comma garé. »

      Rien n'est téléchargé avant que vous touchiez Exporter. À partir de là, le comma garde le trajet pendant la copie ; avant, il peut encore le supprimer pour faire de la place, les plus anciens trajets d'abord.
    screen: recordings-export
    pins:
      - target: export
        text: "**Exporter**."
      - target: cancel
        text: "**Annuler** le laisse."
  - id: whole-drive
    title: "Trouver le trajet complet dans Enregistrements"
    body: |
      L'export a sa propre ligne, **Trajet complet**, à côté de l'enregistrement depuis lequel vous l'avez demandé. Pendant qu'il attend, il dit pourquoi, par exemple **En attente de votre arrêt**, puis **Sauvegarde depuis le comma** avec sa progression. Une fois sauvegardé, il se lit et se partage comme n'importe quel enregistrement.
    screen: phone-recordings
    pins:
      - text: "La ligne **Trajet complet**, intitulée selon l'heure de début du trajet."
    note: "Un trajet de plus de 45 minutes environ de vidéo route est sauvegardé en parties de 3,5 GB : **Fichiers** les liste."
check: "Le menu de partage d'Android s'ouvre avec la vidéo. Pour un trajet complet, sa ligne se lit, et l'information **Sauvegarde** du lecteur indique **Le trajet complet · sur ce téléphone**."
fixes:
  - q: "**Exporter le trajet complet…** n'est pas dans le menu"
    a: "Il est proposé pour un trajet enregistré par votre comma, tant que ce comma est associé à ce téléphone et que son runtime liste ses trajets. [Mettez à jour le runtime du comma](/fr/guides/update-runtime) s'il est plus ancien. Une copie en direct n'a pas de trajet du comma à exporter."
  - q: "**Exporter le trajet complet…** est grisé : « Déjà exporté », « Export en cours » ou « Sa copie s'est arrêtée : Réessayer la sauvegarde sur sa ligne »"
    a: "Le trajet a déjà été exporté, ou son export est en route. S'il s'est arrêté, ouvrez la ligne **Trajet complet** et choisissez **Réessayer la sauvegarde** dans son menu."
  - q: "« Le comma n'a pas ce trajet, il ne peut donc pas être exporté. »"
    a: "Le comma l'a supprimé pour faire de la place aux trajets plus récents. Rien ne peut le récupérer."
  - q: "« Ce trajet est plus ancien que les 50 que liste le comma, il est donc introuvable pour la copie. »"
    a: "Votre comma liste ses 50 trajets les plus récents, et celui-ci est plus ancien : l'export ne peut donc pas le trouver."
  - q: "« Environ 2,2 GB libres requis. Libérez d'abord de l'espace. »"
    a: "Supprimez les trajets dont vous n'avez plus besoin, ou choisissez un autre stockage dans **Paramètres › Enregistrements**, puis rouvrez la fenêtre."
  - q: "Le trajet complet indique « En attente de votre arrêt », « En attente du comma » ou « En attente pendant que Live View est ouvert »"
    a: "Il n'est copié que pendant que le comma est garé, à portée de votre téléphone, et n'affiche pas Live View. Il reprend tout seul dès que c'est possible."
  - q: "« Aucun lecteur vidéo trouvé »"
    a: "Il n'y a pas d'autre application vidéo sur cet appareil pour **Ouvrir dans une autre application**. Lisez-la dans Enregistrements, ou utilisez **Partager** pour l'enregistrer dans vos fichiers."
  - q: "« Cette relecture ne peut pas être lue ici. Essayez une autre application. »"
    a: "Utilisez **Ouvrir dans une autre application**, ou partagez-la vers une application qui la lit."
related: [record, live-copy, support-bundle]
---

## En partager plusieurs à la fois

Appuyez longuement sur un trajet pour le sélectionner, puis touchez-en d'autres pour les ajouter. La barre du bas indique combien sont sélectionnés. Son menu **Plus** propose **Partager**, qui confie toutes les vidéos sélectionnées ensemble au menu de partage d'Android, et la barre propose **Supprimer**. Un trajet qui n'a pas encore de vidéo sur votre téléphone est laissé de côté, et l'action indique combien elle en prend.

## Récupérer les nouveaux trajets automatiquement

**Paramètres › Enregistrements › Récupérer les nouveaux trajets** rapatrie la caméra route de chaque nouveau trajet sans rien toucher : environ toutes les demi-heures, tant que votre téléphone et votre comma sont sur un Wi‑Fi que vous choisissez sous **Réseaux Wi-Fi** et que la voiture est garée. Chaque trajet récupéré est une ligne **Depuis le comma** dans Enregistrements, sans HUD, comme un trajet complet. **Espace pour les trajets récupérés** plafonne la place qu'ils prennent : 10, 20 ou 50 GB, ou **Aucune limite**. Ils ne sont jamais supprimés pour faire de la place.

## Où ils vont

Les fichiers partagés ne vont que là où vous les envoyez. Les enregistrements restent sur votre téléphone, et la sauvegarde d'Android et le transfert vers un nouveau téléphone les laissent de côté.
