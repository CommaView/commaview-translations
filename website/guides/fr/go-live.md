---
title: "Passer en direct sur YouTube ou un autre serveur"
description: "Diffusez ce que montre Live View, la route et son écran de conduite, sur votre chaîne YouTube ou tout serveur RTMP, en 720p ou 1080p. Configurez une fois, puis passez en direct depuis Live View."
topic: screens
order: 5
kind: walkthrough
lede: "**Passer en direct** diffuse ce que montre Live View, la route et son écran de conduite, de votre téléphone vers votre chaîne YouTube ou tout serveur RTMP, en 720p ou 1080p. Configurez-le une fois dans Paramètres, puis lancez-le depuis Live View."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View fonctionne"
    text: "CommaView sur un téléphone Android, associé à votre comma. Pas encore ? [Installer CommaView](/fr/guides/setup)."
  - title: "Une destination"
    text: "Une chaîne YouTube avec laquelle se connecter, ou une clé de flux de YouTube Studio ou d'un autre serveur RTMP."
  - title: "Internet sur le téléphone"
    text: "Quand le Wi‑Fi du comma n'a pas Internet, la diffusion utilise les données mobiles de votre téléphone : environ 1,4 GB par heure en 720p."
howItWorks:
  - title: "Votre comma"
    text: "Envoie Live View à votre téléphone, comme d'habitude."
  - title: "Votre téléphone"
    text: "Diffuse ce que dessine Live View : 20 images par seconde, 720p ou 1080p."
    edge: "Internet"
  - title: "YouTube ou votre serveur"
    text: "Le montre à qui vous laissez regarder."
steps:
  - id: settings
    title: "Ouvrir Paramètres › Diffusion en direct"
    body: |
      Ouvrez **Paramètres** et touchez **Diffusion en direct**. Tant que vous ne l'avez pas configurée, sa ligne indique **Configurer**.
    screen: support-settings
    pins:
      - target: live-streaming-row
        text: "**Diffusion en direct**."
  - id: destination
    title: "Choisir où diffuser"
    tabs:
      - label: "Se connecter avec YouTube"
        body: |
          Touchez **Se connecter avec YouTube**. La connexion Google s'ouvre dans votre navigateur, où vous choisissez le compte et la chaîne. Une fois connecté, le direct crée chaque diffusion sur votre chaîne et YouTube la démarre tout seul : pas de clé de flux, rien à appuyer dans YouTube Studio. La carte **Destination** affiche alors votre chaîne, **Connecté**.
        screen: settings-live-streaming
        pins:
          - target: destination-row
            text: "**Destination** : votre chaîne, connectée."
        note: "Les pages de connexion de Google ne sont pas illustrées."
      - label: "Une clé de flux ou un serveur"
        body: |
          Touchez **Utiliser une clé de flux** (ou **Configurer la destination**), choisissez la **Plateforme**, **YouTube** ou **Autre serveur**, et collez la clé de flux. Pour YouTube : dans YouTube Studio, Créer › Passer au direct › Diffusion, copiez la clé de flux, et activez-y le démarrage automatique pour que chaque diffusion démarre à l'arrivée de la vidéo. Pour un autre serveur, collez aussi son adresse `rtmp://` ou `rtmps://`. Touchez **Enregistrer la destination**.
        screen: settings-live-streaming-destination
        pins:
          - target: platform
            text: "**Plateforme**."
          - target: stream-key
            text: "La clé de flux. Elle reste uniquement sur ce téléphone, et n'est envoyée qu'au serveur auquel elle est destinée."
          - target: save
            text: "**Enregistrer la destination**."
        note: "`rtmp://` envoie votre clé de flux sans chiffrement. Utilisez `rtmps://` si votre serveur le propose."
  - id: choices
    title: "Vérifier qui peut regarder, la qualité et le son"
    body: |
      - **Qui peut regarder** (connecté à YouTube) : **Publique**, **Non répertoriée** ou **Privée**. Par défaut **Non répertoriée**. Avec une clé de flux, choisissez-le dans YouTube Studio. Toute personne qui regarde voit où vous roulez.
      - **Titre et description** (connecté à YouTube) : le nom de chaque diffusion, avec des puces pour la date, la voiture et plus.
      - **Qualité** : 720p ou 1080p, avec à peu près les données mobiles consommées par heure pour chacune.
      - **Son** : désactivé sauf si vous choisissez le micro de votre comma ou celui de ce téléphone. Tout le monde dans la voiture est entendu, passagers compris. Il ne va que dans votre diffusion et vos copies en direct, jamais à CommaView.

      **Avant de passer en direct** résume tout : la consommation de données, la caméra conducteur et quand la diffusion s'arrête.
    screen: settings-live-streaming
    pins:
      - text: "**Titre et description**."
      - target: sound-row
        text: "**Son**."
  - id: go
    title: "Toucher En direct dans Live View"
    body: |
      Ouvrez Live View et touchez **En direct**. Il indique d'abord le démarrage, puis depuis combien de temps vous êtes en direct. Lancez-le avant de partir, puis n'y touchez plus.
    screen: phone-live-view
    pins:
      - target: go-live-button
        text: "**En direct**. Quand il ne tient pas, il est dans **Plus**."
    warn: "La diffusion montre la caméra conducteur dès que **Caméra cond.** est activé, et **Caméra cond.** affiche alors **Direct**. Désactivez **Caméra cond.** pour garder la caméra conducteur hors de la diffusion."
  - id: share
    title: "Partager le lien pour regarder"
    body: |
      Dans **Détails**, la ligne de la diffusion indique **Diffusion** et depuis combien de temps, avec le débit envoyé, les données utilisées et le réseau. Connecté à YouTube, **Partager le lien** en dessous partage le lien `youtu.be` de votre diffusion.
    screen: phone-live-view-go-live
    pins:
      - target: stop-live
        text: "**En direct**, en cours, avec son minuteur."
      - target: streaming
        text: "**Diffusion** et depuis combien de temps."
      - target: share-watch-link
        text: "**Partager le lien**."
  - id: stop
    title: "Arrêter la diffusion une fois garé"
    body: |
      Touchez à nouveau **En direct** pour arrêter. La diffusion s'arrête aussi quand vous quittez Live View, avec **Arrêter** dans sa notification, et toute seule une minute après l'arrêt de sa vidéo. Elle continue quand vous changez d'application ou verrouillez le téléphone.
check: "**En direct** dans Live View affiche un minuteur qui défile dans les couleurs du direct, les Détails indiquent **Diffusion**, et votre diffusion se lit sur YouTube ou votre serveur."
fixes:
  - q: "Il n'y a pas d'En direct dans Live View"
    a: "La diffusion en direct n'est pas encore configurée : les Détails indiquent **Configurez la diffusion en direct dans Paramètres pour passer en direct d'ici**. Ou il est dans **Plus**, quand les commandes ne tiennent pas toutes."
  - q: "« Ajoutez votre clé de flux dans Paramètres › Diffusion en direct »"
    a: "Le direct n'a nulle part où diffuser. Connectez-vous avec YouTube, ou ajoutez une clé de flux, dans **Paramètres › Diffusion en direct**."
  - q: "La diffusion YouTube ne démarre pas avec une clé de flux"
    a: "Avec une clé de flux, démarrez chaque diffusion avec Passer au direct dans YouTube Studio, ou activez-y le démarrage automatique. Connecté avec YouTube, elle démarre toute seule."
  - q: "« Cette clé contient un espace »"
    a: "Copiez à nouveau la clé depuis votre service de diffusion et collez-la."
  - q: "« Pas de son : Browser View tourne sans »"
    a: "Le direct partage l'image de Browser View, qui n'a pas de son. Arrêtez Browser View avant de passer en direct pour avoir le son. Il en va de même pour un enregistrement lancé sans son."
  - q: "La diffusion s'arrête toute seule"
    a: "Live View dit pourquoi dans un message à chaque fois. Une diffusion s'arrête aussi une minute après l'arrêt de sa vidéo, et quand vous quittez Live View."
related: [live-view, browser-view, live-copy]
blogPost: commaview-0-0-165-go-live-send-to-commaview
---

## Garder une copie de chaque diffusion

**Paramètres › Enregistrements › Garder chaque diffusion en direct** garde un MP4 de chaque direct dans Enregistrements, tel qu'il a été envoyé, à la qualité de la diffusion. Il reste sur votre téléphone. Voyez [Garder une copie en direct](/fr/guides/live-copy).

## Ce qui est dans la diffusion, et ce qui n'y est pas

- **Dedans :** la route et l'écran de conduite dessiné par-dessus, et la caméra conducteur tant que **Caméra cond.** est activé.
- **Pas dedans :** les commandes, les Détails et les messages de Live View. La carte de la navigation seulement avec **Carte dans la diffusion** activé, là où Paramètres le propose, et seulement la carte dans le coin de l'écran CommaView.
- Enregistrer et le direct sont indépendants : vous pouvez enregistrer et diffuser un trajet en même temps.

## Sécurité

Configurez et lancez le direct garé, puis n'y touchez plus. Ne manipulez pas CommaView en conduisant : gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande. Toute personne qui regarde voit où vous roulez.
