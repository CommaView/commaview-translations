---
title: "Regarder votre comma dans Live View"
description: "Ouvrez Live View pour voir la caméra route de votre comma et son écran de conduite sur votre téléphone, et découvrez ses commandes, ses Détails et ses messages en cas de problème."
topic: screens
order: 1
kind: walkthrough
lede: "**Live View** affiche la caméra route de votre comma, en direct, avec l'écran de conduite dessiné par-dessus : celui du comma four, celui du comma 3X ou celui de CommaView. L'image vient directement du comma par votre propre réseau, pas par Internet."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView est installé"
    text: "CommaView sur un téléphone Android, associé à votre comma. Pas encore ? [Installer CommaView](/fr/guides/setup)."
  - title: "La voiture est allumée"
    text: "openpilot n'envoie de la vidéo qu'en route. Voiture éteinte, Live View attend et démarre tout seul quand la voiture démarre."
  - title: "Un seul réseau"
    text: "Votre téléphone et votre comma sur le même Wi‑Fi ou point d'accès. En voiture, voyez [Se connecter en voiture](/fr/guides/connect-in-the-car)."
steps:
  - id: open
    title: "Ouvrir Live View depuis l'accueil"
    body: |
      Sur l'**Accueil**, avec votre comma connecté et la voiture allumée, touchez **Ouvrir Live View**. La route apparaît en quelques secondes, et l'indicateur du flux affiche **Direct**.
    screen: phone-home
    pins:
      - target: open-live-view
        text: "**Ouvrir Live View**, le bouton principal de l'accueil."
    note: "Voiture éteinte, Live View indique **Votre comma est en ligne mais ne roule pas**. Il démarre tout seul quand la voiture démarre, ou tout de suite avec **Actualiser**."
  - id: controls
    title: "Découvrir les commandes sous l'image"
    body: |
      En position verticale, les commandes sont sous la vidéo :

      - **Enregistrer** garde ce passage du trajet. Voyez [Enregistrer un trajet](/fr/guides/record).
      - **Garder** conserve les 3 dernières minutes et la minute suivante du trajet.
      - Le sélecteur d'écran de conduite, nommé d'après l'écran qu'il affiche (**CommaView**, **comma 4**, **comma 3X**), passe au suivant à chaque toucher. Voyez [Choisir l'écran de conduite](/fr/guides/overlays).
      - **En direct** diffuse ce que montre Live View, une fois configuré. Voyez [Passer en direct](/fr/guides/go-live).
      - **Caméra cond.** affiche la caméra conducteur dans un coin de l'image.
      - **Détails** ouvre les informations et les cartes de Live View.

      Ce qui ne tient pas à la largeur et à la taille de texte de votre téléphone va dans **Plus**. Rien n'est réduit ni coupé.
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**Enregistrer**."
      - target: onroad-screen-button
        text: "Le sélecteur d'écran de conduite."
      - target: driver-cam-button
        text: "**Caméra cond.**"
      - target: go-live-button
        text: "**En direct**, une fois la diffusion en direct configurée."
      - text: "**Plus** contient ce qui ne tient pas."
    note: "Pendant un enregistrement, le sélecteur d'écran de conduite et **Caméra cond.** sont grisés : choisissez-les avant de toucher **Enregistrer**."
  - id: details
    title: "Ouvrir les Détails"
    body: |
      Touchez **Détails**, ou remontez le volet en bas de l'écran. Il montre l'état du flux, la vidéo, le runtime, le logiciel et l'adresse de votre comma, si vous enregistrez ou diffusez, et la carte **Browser View**. Ses liens ouvrent **Enregistrements** et les **Paramètres de l'appareil** de votre comma.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "Le volet **Détails**."
      - text: "Le résumé : l'état du flux, la vidéo et le runtime."
      - target: recordings-link
        text: "**Enregistrements**."
      - target: device-settings-link
        text: "**Paramètres de l'appareil** pour ce comma."
  - id: turn
    title: "Tourner le téléphone, ou utiliser un plus grand écran"
    body: |
      Tournez le téléphone à l'horizontale : la vidéo occupe l'écran, avec les commandes dans un rail du côté du conducteur. **Détails** s'ouvre à côté de l'image, et **Quitter** ferme Live View.
    tabs:
      - label: "Téléphone à l'horizontale"
        body: "Le rail contient les mêmes commandes. Sur un écran bas, il devient compact."
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "**Enregistrer**, en haut du rail."
          - target: more
            text: "**Plus** contient **Caméra cond.** et **Détails**."
          - target: exit
            text: "**Quitter** ferme Live View."
      - label: "Tablette ou écran de voiture"
        body: "Sur un écran large, le rail reste du côté du conducteur. Voyez [Utiliser CommaView sur un écran de voiture](/fr/guides/car-screens)."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Enregistrer**."
          - target: onroad-screen-button
            text: "Le sélecteur d'écran de conduite."
          - target: driver-cam-button
            text: "**Caméra cond.**"
          - target: details
            text: "**Détails**."
          - target: exit
            text: "**Quitter**."
  - id: auto
    title: "Laisser Live View s'ouvrir tout seul"
    body: |
      Pour un téléphone ou un système multimédia qui ne sert qu'à afficher Live View, ouvrez **Paramètres › Affichage** et activez **Ouvrir Live View à la connexion**, sous **Ouverture de Live View**. Live View s'ouvre alors tout seul quand votre comma se connecte avec la voiture allumée. Si vous le quittez, il reste fermé jusqu'à la prochaine fois.

      **Garder la barre d'état**, juste en dessous, affiche l'horloge du système au-dessus de Live View au lieu d'utiliser tout l'écran.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Ouvrir Live View à la connexion**."
  - id: leave
    title: "Quitter Live View quand vous avez fini"
    body: |
      Touchez **Quitter**, ou retour, une fois garé. Quitter Live View met aussi fin au direct, à Browser View et aux copies en direct. Live View n'est ouvert que sur un téléphone ou système multimédia à la fois : quittez-le sur l'un avant de l'ouvrir sur un autre.
check: "L'indicateur du flux affiche **Direct**, la route défile, et l'état du flux dans les Détails indique **Bon**."
fixes:
  - q: "« Votre comma est en ligne mais ne roule pas »"
    a: "La voiture est éteinte, ou openpilot n'a pas démarré. Live View revient tout seul dans les 30 secondes après le démarrage de la voiture, ou touchez **Actualiser**."
  - q: "« Impossible de joindre ce comma »"
    a: "Votre téléphone doit être sur le même Wi‑Fi que le comma, ou sur son point d'accès. Live View se reconnecte quand le comma répond, ou touchez **Réessayer**. Toujours rien ? Voyez [CommaView ne trouve pas votre comma](/fr/guides/comma-not-found)."
  - q: "« Live View est ouvert sur un autre appareil »"
    a: "Votre comma ne diffuse que vers un téléphone ou système multimédia à la fois. Revenez à l'accueil dans CommaView sur l'autre appareil, et Live View démarre ici tout seul."
  - q: "« Les données de la voiture n'arrivent pas »"
    a: "La vidéo arrive, mais pas la vitesse, les clignotants ni les alertes de la voiture. Redémarrez le comma pour corriger cela."
  - q: "« Vidéo en différé »"
    a: "Aucune nouvelle image n'est arrivée depuis une seconde. Live View l'indique à côté de l'image, et se reconnecte tout seul si la vidéo ne revient pas."
  - q: "« Impossible de lire la vidéo de ce comma »"
    a: "Aucun des décodeurs vidéo du téléphone n'a pu la lire. CommaView continue d'essayer. Envoyez un rapport d'assistance depuis Paramètres pour que CommaView puisse s'y pencher : voyez [Envoyer un rapport d'assistance](/fr/guides/support-bundle)."
related: [overlays, record, browser-view, car-screens]
---

## Sécurité

Ouvrez Live View garé, puis n'y touchez plus. Ne manipulez pas CommaView en conduisant : gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande. Les alertes de votre comma et les instruments de votre voiture passent en premier. CommaView ne montre que ce que voit le comma.
