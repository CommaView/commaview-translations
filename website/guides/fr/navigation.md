---
title: "Naviguer avec votre propre clé Stadia Maps"
description: "Ajoutez votre clé Stadia Maps, cherchez un lieu depuis l'accueil, choisissez un itinéraire et suivez sa carte de direction et ses annonces vocales dans Live View. Envoyez aussi le lieu à votre comma."
topic: navigation
order: 1
kind: walkthrough
lede: "La **navigation** vous guide vers un lieu dans Live View. Cherchez-le depuis l'accueil avec **Où allez-vous ?**, choisissez un itinéraire, touchez **Démarrer**, puis suivez la carte de direction et les annonces vocales. Les itinéraires viennent de Stadia Maps avec votre propre clé, qui reste chiffrée sur votre téléphone. Le guidage est uniquement affiché et ne contrôle jamais la voiture."
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "Connecté"
    text: "CommaView 0.0.167 ou ultérieur, connecté avec votre compte bêta. La navigation n'est pas proposée hors connexion."
  - title: "Une clé Stadia Maps"
    text: "Une clé API de votre propre compte Stadia Maps. Les itinéraires sont demandés sous votre compte et ses conditions."
  - title: "Position du véhicule activée"
    text: "Le guidage suit le GPS de votre comma. Activez **Position du véhicule** pour votre comma sur l'accueil."
  - title: "Internet sur votre téléphone"
    text: "Pour les recherches et les itinéraires. Ils passent par les données mobiles quand le Wi‑Fi du comma n'a pas Internet."
howItWorks:
  - title: "Où allez-vous ?"
    text: "Trouve des lieux près de votre comma, à partir des données d'OpenStreetMap (Photon)."
    edge: "votre clé"
  - title: "Stadia Maps"
    text: "Calcule les itinéraires, demandés par votre téléphone avec votre clé. Rien ne passe par CommaView."
  - title: "Live View"
    text: "Vous guide depuis la position de votre comma : la carte de direction, la carte et les annonces vocales."
steps:
  - id: open
    title: "Ouvrir Cartes et navigation"
    body: |
      Touchez **Paramètres**, puis **Cartes et navigation**. Une fois connecté, c'est la ligne où se trouvaient auparavant les Cartes hors ligne.
    screen: support-settings
    pins:
      - target: maps-row
        text: "**Cartes et navigation**."
  - id: get-key
    title: "Obtenir une clé auprès de Stadia Maps"
    body: |
      Sous **Votre clé Stadia Maps**, **Clé API** indique **Non ajoutée**. Touchez **Obtenir une clé Stadia Maps** : cela ouvre l'inscription de Stadia dans votre navigateur. Inscrivez-vous, puis copiez votre clé API depuis votre tableau de bord Stadia Maps.
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**Votre clé Stadia Maps** : « Les itinéraires demandent votre propre clé Stadia Maps… »"
      - target: get-key
        text: "**Obtenir une clé Stadia Maps** ouvre l'inscription de Stadia."
      - target: add-key
        text: "**Ajouter**, une fois votre clé copiée."
    note: "Le site de Stadia n'est pas illustré : c'est le leur. Son tableau de bord affiche l'usage, le forfait et les limites de votre clé."
  - id: add-key
    title: "La coller, puis Vérifier et enregistrer"
    body: |
      De retour dans CommaView, touchez **Ajouter**. Touchez **Coller** pour mettre votre clé dans le champ, puis **Vérifier et enregistrer**. Pour vérifier la clé, CommaView demande à Stadia Maps un court itinéraire entre deux points fixes, rien qui vous concerne : **Vérification auprès de Stadia Maps…**. Une fois acceptée, **Clé API** l'affiche masquée, par exemple **•••• e1f0**.
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "**Votre clé API Stadia Maps**, masquée."
      - target: paste
        text: "**Coller** depuis le presse-papiers."
      - target: check-and-save
        text: "**Vérifier et enregistrer**."
    note: "« Conservée sur ce téléphone uniquement, chiffrée. Vérifiée par un court itinéraire auprès de Stadia Maps avant d'être conservée. » Elle n'est jamais dans un paquet d'assistance ni dans un rapport de plantage."
  - id: where-to
    title: "Toucher Où allez-vous ? sur l'accueil"
    body: |
      Garé, touchez **Où allez-vous ?** sur l'accueil, sous la carte de votre comma. Tapez un lieu ou une adresse, ou touchez le micro pour le dire. Une fois enregistrés, **Domicile** et **Travail** sont à un toucher sur la carte.
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**Où allez-vous ?** ouvre la recherche."
      - target: voice
        text: "**Où allez-vous ? par la voix**."
      - target: home-chip
        text: "**Domicile**, une fois enregistré."
  - id: pick
    title: "Choisir le lieu"
    body: |
      Les résultats sont près de votre comma, chacun avec son adresse et sa distance, puis viennent vos lieux enregistrés et récents. Touchez celui que vous voulez.
    screen: navigation-search
    pins:
      - target: search-field
        text: "**Rechercher un lieu ou une adresse**."
      - target: first-result
        text: "Un résultat, avec son adresse et sa distance par rapport à votre comma."
    note: "La saisie est désactivée quand la voiture roule : « La saisie est désactivée quand la voiture roule. Utilisez la voix ou un lieu enregistré. »"
  - id: start
    title: "Choisir un itinéraire et toucher Démarrer"
    body: |
      L'aperçu de l'itinéraire affiche l'itinéraire sur une carte, la durée, la distance et l'heure d'arrivée. Chaque itinéraire a une puce : **Le plus rapide**, **Itinéraire 2**, etc. Touchez **Démarrer** : le guidage commence et Live View s'ouvre.

      **Enregistrer comme domicile** et **Enregistrer comme travail** gardent le lieu à un toucher sur l'accueil.
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "Les itinéraires : **Le plus rapide**, **Itinéraire 2**…"
      - target: start
        text: "**Démarrer**."
      - target: save-home
        text: "**Enregistrer comme domicile**, et **Enregistrer comme travail** à côté."
  - id: follow
    title: "Le suivre dans Live View"
    body: |
      La carte de direction affiche la prochaine manœuvre : sa flèche, la distance, l'instruction et l'étape suivante, ainsi que l'heure d'arrivée. Une annonce vocale arrive environ 20 secondes avant chaque manœuvre, une autre juste avant, et une à l'arrivée. Sur l'écran de conduite de CommaView, des chevrons sont peints dans votre voie et en travers de la sortie de la manœuvre.

      Ratez une sortie et un nouvel itinéraire arrive en quelques secondes. Le trajet se termine tout seul une fois arrivé et la voiture éteinte.
    tabs:
      - label: "Téléphone"
        body: |
          En position verticale, la carte de direction et la carte sont sous la vidéo.
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "La carte de direction."
          - target: end
            text: "**Arrêter la navigation**."
          - target: mute
            text: "**Couper la voix du guidage**."
          - target: map-button
            text: "**Carte** masque la carte pour le trajet, et la fait revenir."
      - label: "Écran de voiture"
        body: |
          Sur un système multimédia, quand il y a la place à côté de la vidéo, la carte et la carte de direction s'y placent dans leur propre panneau. Sinon, l'écran CommaView fond la carte dans le coin de la vidéo. Faites glisser le séparateur pour changer la largeur du panneau.
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "La carte de direction."
          - target: divider
            text: "Le séparateur, pour changer la largeur de la carte."
          - target: map-button
            text: "**Carte**."
    warn: "Préparez le trajet garé. Ne manipulez pas CommaView en conduisant : la carte de direction et la voix sont là pour que vous n'ayez pas à le faire, et les alertes d'openpilot et de votre voiture passent en premier."
  - id: send
    title: "Envoyer le lieu à votre comma, si votre fork en accepte un"
    body: |
      Sous **Démarrer**, l'aperçu de l'itinéraire propose **Envoyer au comma** pour les forks dont la navigation accepte une destination : StarPilot, carrotpilot, et la navigation (alpha) d'openpilot, avec celle de sunnypilot qui en découle. Les autres forks ne l'affichent pas.

      Touchez-le. CommaView demande d'abord et dit ce que le fork change à la conduite avec ses réglages actuels, comme ralentir dans les virages. Touchez **Envoyer** : « Envoyé à votre comma. StarPilot y planifie son propre itinéraire. » Le fork calcule l'itinéraire avec son propre service : son itinéraire peut donc différer de celui de CommaView. **Effacer du comma** le retire, et terminer le trajet le retire aussi.
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**Envoyer**."
    note: "**Envoyer chaque trajet à ce comma**, sous Envoyer au comma, envoie chaque trajet quand vous touchez Démarrer. Il se met en pause tout seul si les réglages de conduite du fork changent, jusqu'à ce que vous donniez à nouveau votre accord."
check: "Dans **Cartes et navigation**, **Clé API** affiche votre clé masquée, et l'aperçu de l'itinéraire indique **Itinéraires par Stadia Maps · Le guidage est uniquement affiché et ne contrôle jamais la voiture.**"
fixes:
  - q: "« Ajoutez votre propre clé Stadia Maps pour obtenir des itinéraires : Réglages › Cartes et navigation. »"
    a: "Aucune clé n'est encore gardée. Touchez **Ajouter votre clé** dans l'aperçu de l'itinéraire, ou suivez [les étapes 2 et 3](#step-get-key). Où allez-vous ?, la recherche et les lieux fonctionnent sans clé."
  - q: "« Stadia Maps n'a pas accepté cette clé (401). Vérifiez qu'elle est copiée en entier depuis votre tableau de bord. »"
    a: "Copiez à nouveau la clé en entier depuis votre tableau de bord Stadia Maps, et collez-la encore une fois."
  - q: "« Ce n'est pas une clé Stadia Maps. »"
    a: "Ce que vous avez collé n'a pas la forme d'une clé API, donc rien n'a été envoyé. Copiez la clé API depuis votre tableau de bord Stadia Maps : des lettres, des chiffres et des tirets."
  - q: "« Stadia Maps a refusé cette clé (403) : son forfait n'inclut peut-être pas les itinéraires. »"
    a: "Vérifiez votre forfait dans votre tableau de bord Stadia Maps."
  - q: "« Votre clé Stadia Maps a dépassé sa limite (429) »"
    a: "Ses crédits du mois sont épuisés, ou elle a fait trop de demandes à l'instant. Vérifiez-la dans votre tableau de bord Stadia Maps. L'application ne l'utilise plus pendant cinq minutes."
  - q: "« Impossible de joindre Stadia Maps pour vérifier la clé. Vérifiez la connexion Internet de ce téléphone et réessayez. »"
    a: "Votre téléphone n'a pas Internet pour l'instant. Réessayez avec les données mobiles ou un Wi‑Fi qui accède à Internet."
  - q: "Il n'y a pas de **Où allez-vous ?** sur l'accueil"
    a: "La navigation est réservée aux membres connectés depuis CommaView 0.0.167. Déconnecté, ou avec un pass qui ne se vérifie pas, elle n'est pas proposée. Elle est désactivée en Chine continentale."
  - q: "La carte de direction indique « Position du véhicule désactivée »"
    a: "Le guidage a besoin de la position de votre comma. Activez **Position du véhicule** pour ce comma sur l'accueil."
  - q: "La carte de direction indique « En attente du GPS »"
    a: "Le guidage démarre avec la première position de votre comma. Laissez-lui un instant sous un ciel dégagé."
  - q: "« C'est trop loin pour un seul trajet »"
    a: "La navigation calcule des itinéraires vers des lieux jusqu'à 1 500 km (930 miles). Choisissez une étape en chemin, puis repartez de là."
  - q: "**Envoyer au comma** n'est pas là"
    a: "Il n'apparaît que dans l'aperçu de l'itinéraire, et seulement pour un fork dont la navigation accepte une destination : StarPilot, carrotpilot, ou la navigation (alpha) d'openpilot ou de sunnypilot."
  - q: "« Impossible de joindre votre comma pour lui envoyer ce trajet. »"
    a: "Connectez ce téléphone au même réseau que votre comma, puis touchez **Réessayer**."
  - q: "« La navigation (alpha) d'openpilot est désactivée sur votre comma. »"
    a: "Touchez **Activer la navigation (alpha)**, garé. Sur les versions publiées qui la désactivent à chaque démarrage, elle ne peut pas encore rester activée."
related: [live-view, car-screens, overlays]
---

## La carte dans Live View

**Paramètres › Cartes et navigation › Carte de Live View** choisit où elle s'affiche :

- **Disposition** : **Automatique** (à côté de la vidéo quand il y a la place, sinon dans le coin), **À côté de la vidéo**, ou **Dans le coin**. Les écrans comma 3X, comma four, StarPilot et Surround affichent toujours la carte à côté de la vidéo.
- **Largeur à côté de la vidéo** se règle en faisant glisser le séparateur dans Live View. **Réinitialiser** la remet par défaut.
- **Thème de carte** : **Comme l'app** (par défaut : clair quand CommaView est clair, sombre quand il est sombre), **Auto** (clair du lever au coucher du soleil là où est votre comma), **Comme le téléphone**, **Clair** ou **Sombre**. Il s'applique à toutes les cartes : celle de Live View, la carte de position de l'accueil, **Position du véhicule** et l'aperçu de l'itinéraire.

## Guidage vocal et vos lieux

- **Guidage vocal** active et désactive les annonces. Le haut-parleur de la carte de direction, **Couper la voix du guidage**, est le même réglage.
- **Vos lieux** : **Domicile** et **Travail**, et **Lieux récents**, gardés sur ce téléphone. **Effacer** retire les lieux récents.

## Un lieu depuis une autre application

Dans Google Maps ou une autre application de cartes, partagez un lieu et choisissez **Naviguer avec CommaView**. Son aperçu d'itinéraire s'ouvre sur l'accueil, comme pour un lieu enregistré.

## Mapbox

Si votre compte le propose, Paramètres › Cartes et navigation peut calculer les itinéraires avec votre propre jeton Mapbox au lieu de Stadia Maps.

## Confidentialité

Votre clé Stadia Maps est gardée uniquement sur ce téléphone, chiffrée, et n'est jamais journalisée ni mise dans un paquet d'assistance. Les itinéraires vont de votre téléphone à Stadia Maps avec elle ; rien ne va au service de compte de CommaView. Les recherches vont à Photon, près de la position de votre comma. Effacer votre clé, ou vous déconnecter, la retire du téléphone.

## Sécurité

Préparez un trajet garé, et laissez la carte de direction et la voix vous guider. La navigation est uniquement affichée : elle ne dirige jamais, ne freine jamais et ne change rien à ce que fait openpilot. Ne manipulez pas CommaView en conduisant : gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande.
