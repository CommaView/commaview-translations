---
title: "Utiliser CommaView sur une tablette ou un écran de voiture"
description: "Le Live View de CommaView sur un plus grand écran : système multimédia Android, boîtier IA Android sur l'écran de la voiture ou tablette sur support. Installation, réseau, association, disposition."
topic: screens
order: 3
kind: walkthrough
lede: "Les écrans du comma 3X et du comma four sont petits. CommaView affiche le Live View de votre comma sur un plus grand : un système multimédia Android, un boîtier IA Android branché sur l'écran de la voiture, ou un téléphone ou une tablette sur un support. L'écran de voiture exécute sa propre copie de CommaView, associée à votre comma."
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 ou ultérieur"
    text: "Un système multimédia, un boîtier IA, un téléphone ou une tablette sous Android 8 ou ultérieur, qui vous laisse installer une application."
  - title: "Votre invitation"
    text: "L'adresse e-mail à laquelle votre invitation CommaView est arrivée, pour vous connecter sur my.commaview.com et dans l'application."
  - title: "CommaView sur votre téléphone"
    text: "Le plus simple : configurez d'abord votre comma depuis votre téléphone, puis associez l'écran de voiture. [Installer CommaView](/fr/guides/setup)."
howItWorks:
  - title: "Votre comma"
    text: "Envoie Live View par un réseau local, pas par Internet."
    edge: "point d'accès ou Wi‑Fi"
  - title: "L'écran de voiture"
    text: "Exécute son propre CommaView, associé à votre comma."
steps:
  - id: install
    title: "Installer CommaView sur l'écran de voiture"
    body: |
      Sur le système multimédia, le boîtier IA, le téléphone ou la tablette, ouvrez le navigateur web et connectez-vous sur [my.commaview.com](https://my.commaview.com) avec l'adresse e-mail à laquelle votre invitation est arrivée. Sous **Get the app**, touchez **Download CommaView**, ouvrez le téléchargement et autorisez les installations depuis le navigateur pour celle-ci, puis désactivez-les à nouveau, comme dans le [guide d'installation](/fr/guides/setup).

      Ouvrez CommaView et connectez-vous. Pendant la bêta, il a besoin d'Internet de temps en temps pour renouveler son pass d'accès : donnez-lui donc au moins de temps en temps un Wi‑Fi avec Internet.
    note: "Certains systèmes multimédias et boîtiers bloquent les installations depuis le navigateur. Téléchargez l'application sur un ordinateur, copiez-la avec une clé USB, et ouvrez-la depuis le gestionnaire de fichiers de l'appareil."
  - id: network
    title: "Le mettre sur le même réseau que le comma"
    body: |
      Live View va directement du comma à l'écran de voiture par un réseau local. Ils doivent seulement être sur le même, et en voiture, c'est généralement un point d'accès. Choisissez celui qui démarre tout seul avec la voiture : c'est généralement le plus simple.
    tabs:
      - label: "Point d'accès de l'écran de voiture"
        body: "Si le boîtier IA ou le système multimédia peut partager un point d'accès (beaucoup le peuvent avec une carte SIM), activez-le et connectez-y le comma dans **Paramètres › Réseau** sur le comma."
      - label: "Point d'accès de votre téléphone"
        body: "Connectez le comma et l'écran de voiture au point d'accès de votre téléphone. Ils y trouvent aussi Internet."
      - label: "Point d'accès du comma"
        body: "Activez le point d'accès du comma (openpilot parle de partage de connexion : sur un comma four, **Paramètres › Réseau › Activer le partage de connexion** ; sur un comma 3X, **Paramètres › Réseau › Avancé › Activer le partage de connexion**) et rejoignez-le depuis l'écran de voiture."
      - label: "Wi‑Fi domestique"
        body: "À la maison, les deux sur votre Wi‑Fi. Pratique pour la configuration, mais cela s'arrête dès que vous partez."
    note: "Désactivez tout VPN sur l'écran de voiture. Certains points d'accès isolent les appareils connectés : si l'écran de voiture ne trouve pas le comma sur l'un, essayez-en un autre. Plus d'infos dans [Se connecter en voiture](/fr/guides/connect-in-the-car)."
  - id: pair
    title: "L'associer à votre comma"
    body: |
      Si votre comma exécute déjà CommaView depuis votre téléphone, associez l'écran de voiture au lieu de tout reconfigurer. Il reçoit sa propre clé.
    tabs:
      - label: "Sur votre téléphone"
        body: |
          Ouvrez les **Paramètres de l'appareil** du comma, puis **Associer un autre téléphone**. Sous **Ajouter un autre téléphone**, touchez **Afficher l'invitation** : un code à taper, ou un code QR, valable 10 minutes et à usage unique.
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**Afficher l'invitation**."
          - target: this-phone
            text: "Les téléphones qui ont une clé, celui-ci marqué **Ce téléphone**. L'écran de voiture les rejoint."
      - label: "Sur l'écran de voiture"
        body: |
          Sur **Connectez votre comma**, touchez **Associer un comma qui exécute CommaView** (si un comma est déjà ajouté, ouvrez plutôt **Ajouter un comma**). Choisissez votre comma et touchez **Saisir son code d'association**, ou **Scanner le code QR**. S'il n'est pas listé, touchez **Saisir l'adresse et le code**. Tapez l'invitation dans **Code d'association ou invitation** et touchez **Associer le comma**.
        screen: add-comma
        pins:
          - target: found-comma
            text: "Votre comma, trouvé sur ce réseau."
          - target: scan-qr
            text: "**Scanner le code QR**."
          - target: enter-address
            text: "**Saisir l'adresse et le code**, s'il n'est pas listé."
    note: "Votre téléphone affiche alors **Un nouveau téléphone a une clé**. Touchez **C'est le mien**. Toutes les étapes : [Ajouter un autre téléphone ou une tablette](/fr/guides/another-phone)."
  - id: fit
    title: "L'adapter à votre écran"
    body: |
      Sur un écran large, CommaView se dispose en tableau de bord, avec la navigation dans un rail sur le côté. Gardez la taille de texte de l'appareil lisible d'un coup d'œil : CommaView se dispose selon la place qu'il a à cette taille.

      Les commandes de Live View sont du côté du conducteur. En **Auto**, CommaView suit le côté que signale votre comma ; pour le régler vous-même, choisissez **Paramètres › Affichage › Poste de conduite** : **Auto**, **Conduite à gauche** ou **Conduite à droite**. Cela inverse les commandes sur chaque écran.
    tabs:
      - label: "Tablette"
        body: "L'accueil affiche la voiture, votre semaine, la carte et vos trajets côte à côte, avec le rail sur le côté."
        screen: tablet-home
        pins:
          - target: home-tab
            text: "Le rail : **Accueil**, **Enregistrements**, **Paramètres**."
          - target: open-live-view
            text: "**Ouvrir Live View**."
      - label: "Système multimédia"
        body: "Le même tableau de bord, à la taille d'un écran intégré au tableau de bord."
        screen: car-home
        pins:
          - target: home-tab
            text: "Le rail : **Accueil**, **Enregistrements**, **Paramètres**."
          - target: open-live-view
            text: "**Ouvrir Live View**."
      - label: "Par un boîtier IA"
        body: |
          Certaines voitures coupent les bords de l'image qu'envoie un boîtier IA, sans qu'Android le sache. Ouvrez **Paramètres › Affichage › Bords de l'écran** et rentrez chaque bord jusqu'à voir la ligne sur tout le pourtour. Vérifiez ensuite que l'accueil, Live View et Paramètres tiennent à l'intérieur. **Thème**, au même endroit, peut suivre l'écran de voiture : **Comme cet appareil**.
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−** et **+** rentrent chaque bord ; **OK** le garde."
  - id: live-view
    title: "Ouvrir Live View et vérifier qu'il s'affiche"
    body: |
      Touchez **Ouvrir Live View**, voiture allumée. Ses commandes sont dans un rail à côté de la route, du côté du conducteur, compact sur un écran bas.
    tabs:
      - label: "Tablette"
        body: "**Détails** s'ouvre dans un panneau à côté de la vidéo."
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "Les Détails, à côté de la vidéo."
          - target: record-button
            text: "**Enregistrer**."
          - target: go-live-button
            text: "**En direct**."
      - label: "Système multimédia"
        body: "Le rail contient Enregistrer, le sélecteur d'écran de conduite, Caméra cond., Détails et Quitter."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Enregistrer**."
          - target: onroad-screen-button
            text: "Le sélecteur d'écran de conduite."
          - target: driver-cam-button
            text: "**Caméra cond.**"
          - target: details
            text: "**Détails**, sous Caméra cond."
          - target: exit
            text: "**Quitter**."
  - id: auto
    title: "Le laisser s'ouvrir tout seul"
    body: |
      Dans **Paramètres › Affichage**, sous **Ouverture de Live View** :

      - **Ouvrir Live View à la connexion** ouvre Live View tout seul quand votre comma se connecte avec la voiture allumée.
      - **Ouvrir CommaView au démarrage de cet appareil**, pour un système multimédia qui redémarre avec la voiture. Celui qui se met plutôt en veille a peut-être sa propre liste d'applications à lancer.
      - **Ouvrir CommaView à la connexion Bluetooth** : quand l'appareil que vous choisissez se connecte, votre voiture ou, sur un système multimédia, votre téléphone.

      Avec **Superposition sur d'autres applis** autorisé, CommaView s'ouvre tout seul. Sinon, une notification propose de l'ouvrir.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Ouvrir Live View à la connexion**."
check: "Voiture allumée, l'écran de voiture ouvre Live View, l'indicateur du flux affiche **Direct**, et chaque commande est à l'intérieur des bords de l'écran."
fixes:
  - q: "Puis-je utiliser CommaView par CarPlay ou Android Auto ?"
    a: "Pas depuis votre téléphone. CommaView n'est pas une application CarPlay ou Android Auto, et ces plateformes ne laissent pas les applications du téléphone afficher de la vidéo pendant que la voiture roule. Un boîtier IA Android contourne cela, car c'est un appareil Android à part entière : CommaView tourne sur le boîtier, et la voiture affiche l'écran du boîtier. Voyez [Faire tourner CommaView sur un boîtier IA Android](/fr/guides/ai-box)."
  - q: "Est-ce que ça marche avec l'Android Automotive intégré de ma voiture (Google intégré) ?"
    a: "Pas encore. Les voitures avec Google intégré n'installent des applications que depuis leur propre Play Store, où CommaView n'est pas. Si vous essayez autrement, dites-nous comment ça s'est passé."
  - q: "Puis-je utiliser un écran de voiture et mon téléphone avec le même comma ?"
    a: "Oui : associez chacun au comma. Un seul a Live View à la fois, alors quittez d'abord Live View sur l'autre. Live View indique **Live View est ouvert sur un autre appareil** et démarre tout seul dès que vous revenez à l'accueil sur l'autre."
  - q: "Ma voiture coupe les bords de l'image"
    a: "Certaines voitures rognent l'image qu'envoie un boîtier IA, sans qu'Android le sache. **Paramètres › Affichage › Bords de l'écran** garde l'application à l'écart de chaque bord que vous réglez."
  - q: "L'écran de voiture ne trouve pas le comma"
    a: "CommaView trouve le comma tout seul sur le même réseau, même si son adresse change. Sinon, saisissez l'adresse IP du comma : 192.168.43.1 sur son propre point d'accès (la même pour tous les comma), ou sur tout autre réseau, l'adresse IP que le comma affiche dans **Paramètres › Réseau** : sous le nom du réseau sur le bouton Wi‑Fi d'un comma four, ou sous **Avancé** sur un comma 3X."
  - q: "L'écran de voiture n'a plus de vidéo après une mise à jour du runtime"
    a: "Quand vous mettez à jour le runtime de votre comma, mettez d'abord à jour CommaView sur chaque appareil qui le regarde, écran de voiture compris. Un écran de voiture avec une ancienne version de CommaView continue de fonctionner 90 jours après que le premier téléphone du comma a reçu sa clé ; ensuite, il a besoin de CommaView 0.0.166 ou ultérieur et d'une invitation."
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## Ce qui fonctionne pendant la conduite

CommaView est une application Android : il lui faut donc un appareil Android devant vous. Chacun de ceux-ci peut la faire tourner pendant que vous roulez :

- **Un système multimédia Android.** Un système multimédia de seconde monte sous Android 8 ou ultérieur : CommaView s'y installe comme sur un téléphone, et tourne sur l'écran de la voiture pendant que vous roulez.
- **Un « boîtier IA » Android.** Un petit ordinateur Android qui se branche sur le port CarPlay ou Android Auto filaire de la voiture et y affiche son propre écran Android. CommaView tourne sur le boîtier, pas sur votre téléphone. Voyez [Faire tourner CommaView sur un boîtier IA Android](/fr/guides/ai-box).
- **Un téléphone ou une tablette sur un support.** N'importe quel téléphone ou tablette Android, sur un support de tableau de bord ou de grille d'aération qui ne gêne pas votre vue. La solution la plus simple, et celle que la plupart des gens utilisent.

Une voiture avec un navigateur web, comme une Tesla, peut plutôt y afficher Live View : voyez [Afficher Live View dans le navigateur de votre voiture](/fr/guides/browser-view).

## Ce qui ne fonctionne pas, et pourquoi

- **CarPlay et Android Auto depuis votre téléphone.** CommaView n'est pas une application CarPlay ou Android Auto. Ces plateformes ne laissent pas les applications du téléphone afficher de la vidéo pendant que la voiture roule.
- **La vidéo à l'arrêt dans CarPlay et Android Auto.** Apple et Google ajoutent la vidéo pour certaines voitures, mais seulement à l'arrêt : elle ne peut donc pas afficher Live View sur la route.
- **La recopie de votre téléphone vers la voiture.** Les adaptateurs qui recopient l'écran d'un téléphone par CarPlay ou Android Auto ne sont pas pris en charge. Utilisez plutôt un boîtier IA Android ou un système multimédia qui exécute CommaView lui-même.
- **Google intégré (Android Automotive).** Ces voitures n'installent des applications que depuis leur propre Play Store, où CommaView n'est pas.

## Matériel testé

Les écrans de voiture avec lesquels l'équipe CommaView a roulé. CommaView devrait tourner sur tout appareil sous Android 8 ou ultérieur, mais voici ceux que nous avons vérifiés :

| Appareil | Type | Ce que nous avons vérifié |
| --- | --- | --- |
| **Système multimédia Doro** (Qualcomm QCM6125, Android 13, 1280 × 720) | Système multimédia | Live View en trajets urbains (octobre 2026). |
| **Système multimédia Dasaita 10,2″** (1280 × 720, dans un Toyota RAV4) | Système multimédia | Live View en conduite ; envoi des enregistrements, garé. |

**Aidez-nous à tester.** Chaque écran de voiture est différent. Si vous utilisez CommaView sur un système multimédia ou un boîtier, [dites-nous comment ça s'est passé](#parlez-nous-de-votre-écran-de-voiture), et nous l'ajouterons ici une fois vérifié.

## Parlez-nous de votre écran de voiture

Envoyez-le-nous depuis l'écran de voiture lui-même, pour que le rapport contienne son modèle et la taille de son écran :

1. Dans CommaView sur le système multimédia ou le boîtier, ouvrez **Paramètres › Assistance et diagnostics** et touchez **Signaler un problème ou proposer une idée**.
2. Choisissez **Idée**, puis activez **Cet appareil : diagnostics** (une idée les laisse désactivés) : ils nous donnent sa marque, son modèle et la taille de son écran.
3. Dans la note, indiquez votre voiture, le système multimédia ou le boîtier (marque et modèle), comment il est connecté (quel point d'accès, ou quel Wi‑Fi), et ce qui a marché ou non. Touchez ensuite **Envoyer**.

Vous retrouverez ce que vous avez envoyé, et nos réponses, sous Your feedback sur [my.commaview.com](https://my.commaview.com/feedback). Pas encore dans la bêta, ou l'application ne démarre pas ? Dites-le-nous sur le [Discord de CommaView](https://discord.gg/UuMhz9K8ft).

## Sécurité

- Installez, associez et réglez la disposition à l'arrêt. Vérifiez que Live View s'affiche avant de rouler.
- Ne manipulez pas CommaView en conduisant. Gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande.
- Les alertes de votre comma et les instruments de votre voiture passent en premier. CommaView ne montre que ce que voit le comma.
- Fixez un téléphone ou une tablette là où il ne gêne ni votre vue ni un airbag, et respectez les règles locales sur les écrans en voiture.
