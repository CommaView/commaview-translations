---
title: "Enregistrer une copie en direct de ce que montre Live View"
description: "Une copie en direct garde sur votre téléphone ce que montre Live View pendant que vous roulez, prête dans Enregistrements dès l'arrêt, sans limite de 10 minutes. Jamais envoyée en ligne."
topic: recordings
order: 2
kind: walkthrough
lede: "Une **copie en direct** garde ce que montre Live View, la route et son écran de conduite, sur votre téléphone pendant que vous roulez. Elle est prête dans Enregistrements dès que vous vous arrêtez : aucune relecture à créer et aucune limite de 10 minutes. Les copies en direct restent sur votre téléphone et ne sont jamais envoyées en ligne."
appVersion: "0.0.164"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View fonctionne"
    text: "CommaView sur votre téléphone, associé à votre comma. Pas encore ? [Installer CommaView](/fr/guides/setup)."
  - title: "De la place sur votre téléphone"
    text: "Environ 1,4 GB par heure en 720p, ou 2,3 GB par heure en 1080p. Une copie en direct laisse toujours 500 MB libres."
howItWorks:
  - title: "Live View"
    text: "Dessine la route et l'écran de conduite, comme toujours."
    edge: "pendant que vous roulez"
  - title: "Votre téléphone"
    text: "Encode ce que dessine Live View dans un MP4, à 20 images par seconde."
  - title: "Enregistrements"
    text: "La copie est prête dès que vous vous arrêtez."
steps:
  - id: choose
    title: "Choisir Copie en direct ou Les deux"
    body: |
      Touchez **Paramètres**, puis **Enregistrements**. Sous **Enregistrer dans Live View**, choisissez ce que crée Enregistrer. Le choix est gardé dès que vous le faites.
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Enregistrer dans Live View** : **Relecture**, **Copie en direct** ou **Les deux**."
    tabs:
      - label: "Copie en direct"
        body: |
          « Ce que montre Live View, prêt dès l'arrêt. Aucune relecture à créer et aucune limite de durée. »
      - label: "Les deux"
        body: |
          « Une copie en direct immédiate, et la relecture après le trajet. La relecture garde sa limite de 10 minutes. » La relecture est créée une fois garé, comme le montre [Enregistrer un trajet](/fr/guides/record).
  - id: quality
    title: "Choisir sa qualité et son son"
    body: |
      Avec une copie en direct choisie, la page ajoute ses lignes. **Qualité de la copie en direct** est en **720p** tant que vous ne choisissez pas **1080p**. **Son** est désactivé sauf si vous choisissez un micro : celui du comma, ou celui de ce téléphone. C'est le même Son que dans Paramètres › Diffusion en direct.
    screen: settings-recordings
    pins:
      - text: "**Qualité de la copie en direct** : 720p (environ 1,4 GB par heure) ou 1080p (environ 2,3 GB par heure)."
      - text: "**Son** : désactivé, le micro du comma ou celui de ce téléphone."
    note: "Une copie en direct montre ce que montre Live View, y compris l'incrustation de la caméra conducteur tant que **Caméra cond.** est activé. Désactivez Caméra cond. dans Live View pour laisser la caméra conducteur de côté."
  - id: record
    title: "Toucher Enregistrer dans Live View"
    body: |
      Voiture allumée et toujours en position P, ouvrez **Live View** et touchez **Enregistrer**. Son minuteur défile, et **Détails** indique **Enregistrement ·** et la durée, comme pour tout enregistrement. Touchez à nouveau Enregistrer pour arrêter.

      L'enregistrement continue quand vous changez d'application ou verrouillez le téléphone, avec une notification, **Enregistrement d'une copie en direct**, qui affiche son minuteur et **Arrêter**. Fermer Live View y met fin.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Enregistrer, avec son minuteur. Touchez-le à nouveau pour arrêter."
      - target: recording
        text: "**Enregistrement ·** la durée, dans **Détails**."
    warn: "Lancez l'enregistrement avant de partir, ou laissez un passager s'en charger. Ne manipulez pas CommaView en conduisant."
  - id: find
    title: "La trouver dans Enregistrements"
    body: |
      Ouvrez **Enregistrements**. La copie est marquée **Copie en direct**, sous le jour, avec sa durée et sa taille. Juste après l'arrêt, elle indique **Sauvegarde de la copie en direct…** avec sa progression ; ensuite, elle se lit.

      Avec **Les deux**, le trajet a deux lignes : la copie en direct, et la relecture, qui attend que vous la créiez une fois garé.
    screen: phone-recordings
    pins:
      - target: live-copy-row
        text: "La ligne marquée **Copie en direct**."
      - text: "Avec **Les deux**, la relecture du trajet, sur sa propre ligne."
  - id: watch
    title: "La regarder, la partager ou la supprimer"
    body: |
      Touchez la copie pour la regarder. Ses informations ajoutent **Version** (**Copie en direct**, ou **Copie en direct · avec relecture** avec Les deux), **Qualité** et **Son**. **Actions de l'enregistrement** propose **Partager**, **Ouvrir dans une autre application**, **Sélectionner** et **Supprimer**.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Actions de l'enregistrement** : Partager, Ouvrir dans une autre application, Sélectionner et Supprimer."
      - text: "**Plein écran**."
check: "La copie se lit dans Enregistrements dès qu'elle est sauvegardée, et la **Version** du lecteur indique **Copie en direct**."
fixes:
  - q: "« Pas assez d'espace pour une copie en direct : elle laisse toujours 500 MB libres sur ce téléphone. Supprimez dans Enregistrements les trajets dont vous n'avez plus besoin. »"
    a: "Supprimez les trajets dont vous n'avez plus besoin, ou choisissez un autre stockage dans **Paramètres › Enregistrements › Stockage**. La carte Stockage indique à peu près combien d'heures de copies en direct tiennent."
  - q: "« Copie en direct arrêtée : ce téléphone est presque plein. Elle est sauvegardée dans Enregistrements ; elle laisse toujours 500 MB libres. »"
    a: "Ce qui a été enregistré est gardé. Libérez de l'espace avant le prochain trajet."
  - q: "« Copie en direct arrêtée : aucune vidéo du comma depuis une minute. Ce qui a été enregistré est dans Enregistrements. »"
    a: "Le téléphone a perdu le comma pendant une minute, donc la copie s'est terminée. Vérifiez que votre téléphone reste sur le Wi‑Fi ou le point d'accès du comma. Voyez [CommaView ne trouve pas votre comma](/fr/guides/comma-not-found)."
  - q: "« Cette copie en direct a atteint 3,5 GB, le maximum d'un fichier : elle continue dans une nouvelle dans Enregistrements. »"
    a: "Rien n'est perdu : le trajet continue dans une deuxième copie en direct, sur sa propre ligne dans Enregistrements."
  - q: "« La relecture s'est arrêtée à sa limite de 10 minutes. La copie en direct continue d'enregistrer. »"
    a: "Avec **Les deux**, seule la relecture s'arrête à 10 minutes. La copie en direct continue jusqu'à ce que vous l'arrêtiez."
  - q: "« Enregistrement d'une copie en direct seulement. La relecture n'a pas pu démarrer : … »"
    a: "Avec **Les deux**, la copie enregistre même quand la partie relecture ne le peut pas, par exemple quand le comma doit redémarrer ou que ce téléphone ne lui est pas associé. Le message dit pourquoi."
  - q: "La ligne indique « 1,2 GB libres requis pour sauvegarder »"
    a: "Les morceaux de la copie sont gardés jusqu'à ce qu'il y ait la place de les assembler en une vidéo. Supprimez les trajets dont vous n'avez plus besoin, et elle se sauvegarde toute seule."
  - q: "Son information **Sauvegarde** indique « Récupérée après la fermeture de l'application : sa dernière minute peut manquer »"
    a: "L'application s'est fermée pendant l'enregistrement, donc la copie a été reconstituée à partir de ce qui avait été écrit : tout sauf, au plus, la dernière minute."
  - q: "« CommaView ne peut diffuser et enregistrer que lorsqu'il est à l'écran : Android ne l'a pas laissé fonctionner en arrière-plan. »"
    a: "Android a empêché CommaView de fonctionner en arrière-plan. Gardez Live View à l'écran pendant l'enregistrement."
related: [record, export-share, go-live]
blogPost: commaview-0-0-164-carrotpilot-teslahw1-live-copies
---

## Copie en direct ou relecture

| | Copie en direct | Relecture |
| --- | --- | --- |
| Ce qu'elle montre | Ce que montrait Live View, tel qu'il le montrait | La vidéo propre du comma, avec l'écran de conduite dessiné par-dessus |
| Quand elle est prête | Dès que vous vous arrêtez | Une fois garé et après avoir touché **Créer la relecture** |
| Durée | Pas de limite, à part le stockage | Jusqu'à 10 minutes par enregistrement |
| Image | 720p ou 1080p, 20 images par seconde | La meilleure image : **Balanced**, **High** ou **Max** |

## Pendant un direct

Une copie en direct et le [direct](/fr/guides/go-live) partagent un même encodeur. Une copie lancée pendant que vous diffusez a la qualité de la diffusion. **Garder chaque diffusion en direct**, dans Paramètres › Enregistrements, garde un MP4 de chaque direct, tel qu'il a été envoyé, sans Enregistrer.

## Confidentialité

Les copies en direct restent sur votre téléphone. Elles ne sont jamais envoyées en ligne, ni partagées avec les autres téléphones associés au comma. **Envoyer à CommaView** envoie les données propres du comma pour un trajet, jamais une copie en direct. Le son n'est dans une copie que si vous avez choisi un micro, et la caméra conducteur seulement tant que Caméra cond. est activé.

## Sécurité

Choisissez vos réglages et lancez Enregistrer garé. Ne manipulez pas CommaView en conduisant : gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande.
