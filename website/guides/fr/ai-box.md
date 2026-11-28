---
title: "Faire tourner CommaView sur un boîtier IA Android"
description: "Affichez Live View sur l'écran CarPlay ou Android Auto de votre voiture avec un boîtier IA Android : branchez-le, installez CommaView, mettez-le sur le réseau du comma, associez-le et ajustez-le."
topic: screens
order: 4
kind: walkthrough
lede: "Si votre voiture a d'origine CarPlay ou Android Auto **filaire**, un **boîtier IA Android** peut afficher le Live View de CommaView sur l'écran de la voiture, sans nouvel autoradio ni câblage. Le boîtier est un petit ordinateur Android qui se branche sur le port USB où vous brancheriez votre téléphone. CommaView tourne sur le boîtier, donc votre téléphone reste libre pour les appels et les cartes."
parked: true
updated: 2026-11-27
needs:
  - title: "CarPlay ou Android Auto filaire"
    text: "CarPlay ou Android Auto filaire d'origine, par un port USB qui transporte des données. Vérifiez que le boîtier prend en charge ce qu'a votre voiture."
  - title: "Un boîtier avec un vrai Android"
    text: "Android 8 ou ultérieur, qui vous laisse installer une application depuis un fichier. Les boîtiers « vidéo » fermés et les simples adaptateurs sans fil ne peuvent pas faire tourner CommaView. [Quel boîtier acheter](/blog/android-ai-box-commaview)."
  - title: "CommaView sur votre téléphone"
    text: "Configurez d'abord votre comma depuis votre téléphone, puis associez le boîtier. [Installer CommaView](/fr/guides/setup)."
howItWorks:
  - title: "Votre comma"
    text: "Envoie Live View au boîtier par un réseau local."
    edge: "Wi‑Fi"
  - title: "Boîtier IA"
    text: "Exécute CommaView, comme n'importe quel appareil Android."
    edge: "USB"
  - title: "Écran de la voiture"
    text: "Affiche l'écran du boîtier, comme il affiche CarPlay."
steps:
  - id: plug-in
    title: "Brancher le boîtier et installer CommaView"
    body: |
      Branchez le boîtier sur le port USB CarPlay ou Android Auto de la voiture et laissez-le démarrer. Connectez-le pour l'instant à un Wi‑Fi avec Internet.

      Dans le navigateur du boîtier, connectez-vous sur [my.commaview.com](https://my.commaview.com) avec l'adresse e-mail à laquelle votre invitation est arrivée, et touchez **Download CommaView** sous **Get the app**. Autorisez les installations depuis le navigateur pour cette seule installation, puis désactivez-les à nouveau. Ouvrez CommaView et connectez-vous.
    note: "Faites tourner CommaView dans le mode Android du boîtier, pas avec le CarPlay de votre téléphone relayé."
  - id: network
    title: "Mettre le boîtier et le comma sur le même réseau"
    body: |
      Live View va directement du comma au boîtier par un réseau local, pas par Internet, et n'importe quel réseau commun aux deux convient.
    tabs:
      - label: "Point d'accès du boîtier"
        body: "Les boîtiers avec une carte SIM peuvent généralement partager un point d'accès. Activez-le et connectez-y le comma dans **Paramètres › Réseau** sur le comma."
      - label: "Point d'accès de votre téléphone"
        body: "Connectez le boîtier et le comma au point d'accès de votre téléphone. Ils y trouvent aussi Internet."
      - label: "Point d'accès du comma"
        body: "Activez le point d'accès du comma (openpilot parle de partage de connexion) et rejoignez-le depuis le boîtier."
    note: "La plupart des boîtiers utilisent aussi le Wi‑Fi pour connecter votre téléphone en CarPlay sans fil, et certains perdent alors leur Internet par Wi‑Fi. Désactivez tout VPN sur le boîtier."
  - id: pair
    title: "Associer le boîtier à votre comma"
    body: |
      Sur votre téléphone, ouvrez les **Paramètres de l'appareil** du comma, touchez **Associer un autre téléphone**, puis, sous **Ajouter un autre téléphone**, **Afficher l'invitation**. Sur le boîtier, touchez **Associer un comma qui exécute CommaView**, choisissez votre comma, et tapez le code ou touchez **Scanner le code QR**. Toutes les étapes : [Utiliser CommaView sur une tablette ou un écran de voiture](/fr/guides/car-screens#step-pair).
  - id: edges
    title: "Éloigner l'application des bords que la voiture coupe"
    body: |
      Certaines voitures rognent les bords de ce qu'envoie le boîtier, sans qu'Android le sache. Ouvrez **Paramètres › Affichage › Bords de l'écran**. Une ligne marque la limite de l'application : rentrez chaque bord avec **−** et **+** jusqu'à voir la ligne sur tout le pourtour, puis touchez **OK**. **Réinitialiser** désactive le réglage.

      Vérifiez ensuite que l'accueil, Live View et Paramètres tiennent à l'intérieur.
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−** et **+** rentrent chaque bord ; **OK** le garde."
      - text: "**Thème**, aussi dans **Paramètres › Affichage** : **Comme cet appareil** suit le boîtier."
  - id: auto
    title: "Le laisser s'ouvrir tout seul"
    body: |
      Dans **Paramètres › Affichage**, sous **Ouverture de Live View** :

      - **Ouvrir CommaView au démarrage de cet appareil**, pour un boîtier qui redémarre avec la voiture.
      - **Ouvrir CommaView à la connexion Bluetooth**, en choisissant votre téléphone, pour un boîtier qui se met plutôt en veille.
      - **Ouvrir Live View à la connexion**, pour aller directement dans Live View dès que votre comma se connecte avec la voiture allumée.

      Autorisez **Superposition sur d'autres applis** pour que CommaView puisse s'ouvrir tout seul. Sans cela, une notification propose de l'ouvrir.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Ouvrir Live View à la connexion**."
  - id: check
    title: "Vérifier que Live View s'affiche, puis rouler"
    body: |
      Voiture allumée, ouvrez Live View sur le boîtier. Ses commandes sont dans un rail du côté du conducteur, compact sur un écran bas. Vérifiez que l'image s'affiche et que rien n'est coupé avant de rouler.
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "**Enregistrer**, en haut du rail."
      - target: details
        text: "**Détails**, plus bas dans le rail."
    note: "L'écran du boîtier arrive à la voiture sous forme de vidéo : Live View est donc encodé une fois de plus en route. Attendez-vous à une image un peu plus douce et un peu plus tardive que sur un téléphone en main."
check: "L'écran de la voiture affiche l'accueil de CommaView, puis Live View avec l'indicateur du flux sur **Direct**, et la ligne de **Bords de l'écran** est visible sur tout le pourtour."
fixes:
  - q: "Le boîtier ne peut pas installer CommaView"
    a: "Certains boîtiers bloquent les installations depuis le navigateur. Téléchargez l'application sur un ordinateur, copiez-la avec une clé USB, et ouvrez-la depuis le gestionnaire de fichiers du boîtier. Un boîtier au système fermé avec une liste d'applications fixe ne peut pas l'installer du tout."
  - q: "Le boîtier ne trouve pas le comma"
    a: "Vérifiez que les deux sont sur le même réseau, et que le boîtier n'a pas abandonné son Wi‑Fi pour le CarPlay sans fil. Saisissez l'adresse IP du comma si besoin : 192.168.43.1 sur le point d'accès du comma. Plus d'infos dans [Se connecter en voiture](/fr/guides/connect-in-the-car)."
  - q: "L'image saccade ou ne s'affiche pas"
    a: "Le comma envoie sa caméra route en HEVC (H.265) 1928 × 1208, et les décodeurs des boîtiers les moins chers peuvent ne pas suivre. Si un décodeur échoue, CommaView essaie tout seul les autres du boîtier. Live View indique **Impossible de lire la vidéo de ce comma** quand aucun n'y arrive : envoyez un rapport d'assistance depuis le boîtier."
  - q: "« Live View est ouvert sur un autre appareil »"
    a: "Votre comma ne diffuse que vers un téléphone ou système multimédia à la fois. Revenez à l'accueil dans CommaView sur votre téléphone, et Live View démarre tout seul sur le boîtier."
  - q: "Puis-je encore utiliser CarPlay depuis mon téléphone ?"
    a: "Oui. La plupart des boîtiers relaient sans fil le CarPlay ou l'Android Auto de votre téléphone, et vous passez de celui-ci à l'Android du boîtier. CommaView tourne dans le mode Android du boîtier."
  - q: "Le boîtier a-t-il besoin d'une carte SIM ?"
    a: "Pas pour Live View. Pendant la bêta, CommaView a besoin d'Internet de temps en temps pour renouveler son pass d'accès, ce que lui donnent le Wi‑Fi de la maison, le point d'accès de votre téléphone ou une carte SIM dans le boîtier."
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## Quatre sortes d'« adaptateur CarPlay »

Les magasins vendent quatre choses bien différentes sous le même nom. Une seule fait tourner CommaView.

| Type | Ce qu'il fait | Fait tourner CommaView ? |
| --- | --- | --- |
| **Boîtier IA Android** | Android complet sur l'écran de la voiture, applications installées comme sur un téléphone | **Oui** |
| **Boîtier « vidéo » fermé** | Quelques applications de streaming intégrées sur un système verrouillé | Non |
| **Adaptateur sans fil** | Rend sans fil le CarPlay ou l'Android Auto filaire. Pas d'Android à lui | Non |
| **Écran CarPlay portable** | Un écran séparé pour le CarPlay de votre téléphone, souvent sans Android à l'intérieur | Non |

[Les meilleurs boîtiers IA Android pour CommaView](/blog/android-ai-box-commaview) compare les boîtiers qui valent la peine. Une Tesla n'a ni CarPlay ni Android Auto : utilisez plutôt [Browser View](/fr/guides/browser-view).

Quand vous mettez à jour le runtime de votre comma, mettez d'abord à jour CommaView sur le boîtier, comme sur chaque appareil qui regarde votre comma.

## Sécurité

Configurez le boîtier garé, puis n'y touchez plus. Ne manipulez pas CommaView en conduisant : gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande. Les alertes de votre comma et les instruments de votre voiture passent en premier. CommaView ne montre que ce que voit le comma.
