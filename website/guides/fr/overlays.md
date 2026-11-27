---
title: "Choisir l'écran de conduite et ajouter des packs de superposition"
description: "Choisissez comment Live View dessine la route : l'écran du comma four, celui du comma 3X ou celui de CommaView. Ajoutez ensuite un pack de superposition pour ce que votre fork dessine sur son écran."
topic: screens
order: 6
kind: walkthrough
lede: "Live View dessine un écran de conduite par-dessus la caméra route : celui du **comma four**, celui du **comma 3X**, ou celui de **CommaView**. Les écrans comma sont dessinés dans le style de votre fork. Les **packs de superposition** ajoutent ce que l'écran de votre fork dessine et que CommaView ne dessine pas, comme les jauges hybrides de BluePilot ou la trajectoire arc-en-ciel de dragonpilot."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View fonctionne"
    text: "CommaView sur un téléphone Android, associé à votre comma. Pas encore ? [Installer CommaView](/fr/guides/setup)."
  - title: "Connecté, pour la boutique"
    text: "Les membres parcourent les packs de CommaView. Déconnecté, vous pouvez quand même ajouter un pack depuis un fichier ou un lien."
steps:
  - id: switch
    title: "Changer d'écran dans Live View"
    body: |
      Dans Live View, touchez le sélecteur d'écran de conduite. Il est nommé d'après l'écran qu'il affiche, et chaque toucher passe au suivant : **comma 4**, **comma 3X**, **CommaView**, puis on recommence. Celui sur lequel vous le laissez est gardé pour la prochaine fois.
    screen: phone-live-view
    clip: onroad-screen
    pins:
      - target: onroad-screen-button
        text: "Le sélecteur d'écran de conduite, nommé d'après l'écran qu'il affiche."
    note: "Quand il ne tient pas à côté des autres commandes, il est dans **Plus**, sous le nom **Écran de conduite**. Pendant un enregistrement, il est grisé : un enregistrement garde l'écran avec lequel il a commencé."
  - id: display
    title: "Ou le choisir dans Paramètres › Affichage"
    body: |
      Pour voir chaque écran avant de choisir, ouvrez **Paramètres › Affichage**. La carte **Écran de conduite** affiche un aperçu de l'écran choisi sur une photo de route, cadré selon les caméras de votre comma et dessiné dans le style de votre fork. **Engagé**, **Intervention** et **Désengagé** en dessous changent le moment affiché ; ils n'enregistrent rien.
    screen: settings-display
    pins:
      - target: onroad-screen-card
        text: "L'aperçu de l'écran choisi."
      - target: onroad-screen
        text: "**Écran de conduite** : touchez-le pour voir la liste."
  - id: pick
    title: "Choisir un écran"
    body: |
      Chaque écran de la liste a une petite image et une note :

      - **comma four** : MAX au-dessus de la route quand il change, le volant et la confiance à côté.
      - **comma 3X** : une bordure d'état, le cadre MAX, une grande vitesse et les alertes en bas.
      - **CommaView** : une trajectoire fluide, un verrouillage sur le véhicule de tête et la vitesse, l'état et les alertes propres à CommaView.

      En choisir un l'enregistre et change l'aperçu, ses options et Live View. Chaque écran fonctionne sur les deux comma.
    screen: settings-display-onroad-screens
    clip: display-pick
    pins:
      - target: comma-four-option
        text: "**comma four**."
      - target: comma-3x-option
        text: "**comma 3X**."
      - target: commaview-option
        text: "**CommaView**."
    note: "Les alertes, les avertissements et l'état de la surveillance du conducteur utilisent toujours les couleurs de votre comma, quel que soit l'écran choisi."
  - id: store
    title: "Ouvrir la boutique de packs de superposition"
    body: |
      Ouvrez **Paramètres › Packs de superposition**, ou touchez la carte **Packs de superposition** sur l'accueil.
    tabs:
      - label: "Connecté"
        body: |
          La boutique liste d'abord les packs **Officiels** de CommaView, puis ceux de la **Communauté**, chacun vérifié par CommaView. **Pour votre comma** propose le pack officiel du fork qu'exécute votre comma. Cherchez, ou filtrez la liste avec **Tous**, **Officiels**, **Communauté** et **Pour mes comma**.
        screen: overlay-packs-store
        pins:
          - target: search
            text: "**Rechercher des packs**."
          - text: "**Pour votre comma** : le pack officiel du fork de votre comma."
          - target: bluepilot-row
            text: "Les packs **Officiels**, comme BluePilot HUD."
          - target: yours
            text: "**Vos packs** : ce qui est sur ce téléphone."
      - label: "Depuis un fichier ou un lien"
        body: |
          Quelqu'un a partagé un fichier `.cvpack` ou un lien (GitHub, un gist, une pièce jointe Discord) ? Ouvrez **Vos packs** et, sous **Ajouter un pack vous-même**, touchez **Installer depuis un fichier** ou **Coller un lien**. CommaView n'a pas vérifié un pack ajouté ainsi, et la boîte de dialogue d'installation le dit.
  - id: install
    title: "Installer un pack"
    body: |
      Touchez un pack pour voir son aperçu, les forks sur lesquels il **Fonctionne** et ce qu'il ajoute à Live View. Touchez **Installer**, puis à nouveau **Installer** dans la boîte de dialogue. Le pack va sur ce téléphone et sur vos comma associés.
    screen: overlay-pack-detail
    pins:
      - text: "L'aperçu : Live View avec le pack. Touchez-le pour l'agrandir."
      - target: install
        text: "**Installer**."
    note: "Un pack officiel ne fonctionne que sur les forks pour lesquels il est fait. Si aucun de vos comma associés n'en exécute un, la boîte de dialogue le dit ; il s'installe quand même, mais n'apparaît dans Live View que quand l'un d'eux en exécute un."
  - id: drive
    title: "Le voir lors de votre prochain trajet"
    body: |
      Une fois installé, la boutique indique que le pack ira sur votre comma quand ce téléphone le joindra, et qu'il y démarrera quand la voiture sera éteinte. Lors de votre prochain trajet, ouvrez Live View : le pack dessine sur les écrans comma four, comma 3X et CommaView, sous les alertes propres à l'écran de conduite.

      Pour désactiver un pack, ouvrez **Vos packs** : chaque pack a un seul interrupteur, pour ce téléphone et chaque comma associé ensemble.
check: "Dans les **Détails** de Live View, la ligne **Packs de superposition** nomme le pack et indique qu'il est **en cours**."
fixes:
  - q: "Le sélecteur d'écran de conduite est grisé"
    a: "Un enregistrement est en cours. Arrêtez-le, ou attendez qu'il se termine, puis changez d'écran."
  - q: "Les Détails indiquent que le pack n'est « pas pour ce fork »"
    a: "Le pack est fait pour l'écran d'un autre fork et ne dessine rien sur le vôtre. Les packs officiels indiquent pour quels forks ils sont faits sous **Fonctionne sur**."
  - q: "Le pack n'est pas encore dans Live View"
    a: "Il arrive sur votre comma quand votre téléphone s'y connecte, et y démarre quand la voiture est éteinte. Éteignez puis rallumez la voiture avec votre téléphone sur le réseau du comma, puis ouvrez Live View."
  - q: "« Connectez-vous pour voir les packs de CommaView »"
    a: "La boutique liste les packs de CommaView pour les membres connectés. Touchez **Se connecter**. Les packs déjà sur le téléphone continuent de fonctionner pendant que vous êtes déconnecté."
  - q: "« Impossible de joindre my.commaview.com »"
    a: "Vérifiez la connexion Internet de ce téléphone, puis touchez **Réessayer**. **Vos packs** liste toujours tout ce qui est sur le téléphone."
related: [live-view, record, forks]
blogPost: commaview-0-0-166-languages-browser-view
---

## Les options de chaque écran

Sous l'aperçu, **Paramètres › Affichage** affiche les options propres à l'écran choisi :

- **Options de comma four** : **Cadrage de l'aperçu** (reproduire exactement le cadre du comma four, montrer davantage de la caméra, ou la rogner pour remplir cet écran) et **Panneau de confiance compact** (un panneau et une bille plus petits, pour plus de vidéo).
- **Options de CommaView** : **Cadrage** (**Remplir l'écran** rogne la caméra pour remplir un écran horizontal ; **Caméra entière** la montre en entier, avec des bandes noires si besoin) et **Réduire les animations**, qui garde immobiles la trajectoire, la vitesse et le verrouillage de CommaView.
- **comma 3X** : aucune. Il est dessiné comme le comma le dessine.

Ensuite, **Sur chaque écran** : **Poste de conduite**, qui inverse les commandes, **Thème**, **Contraste plein jour** pour le soleil et l'éblouissement, et **Bords de l'écran** pour un écran de voiture qui coupe les bords de l'image ([écrans de voiture](/fr/guides/car-screens)).

Une relecture créée dans Enregistrements dessine ce que Live View dessinait pendant l'enregistrement, quoi que vous choisissiez ensuite.

## D'où vient une surimpression

CommaView ne devine pas quoi dessiner. Le runtime de votre comma envoie, à côté de la vidéo, les mêmes données de conduite que lit l'écran d'openpilot (la trajectoire, les voies, le véhicule de tête, les vitesses, les alertes, la surveillance du conducteur), et l'application les dessine sur votre téléphone, alignées avec la caméra affichée. Quand ces données sont en retard, manquantes ou destinées à une autre caméra, CommaView laisse cette partie de côté plutôt que de dessiner quelque chose qui pourrait être faux.

## Sécurité

Choisissez l'écran et installez les packs garé. Ne manipulez pas CommaView en conduisant : gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande. Une surimpression est faite pour être regardée, pas pour aider à conduire : les alertes de votre comma et les instruments de votre voiture passent en premier. L'icône de surveillance du conducteur n'est pas une preuve d'attention, et la surimpression d'une relecture sert à revoir un trajet, pas à prouver exactement ce qui s'est passé.
