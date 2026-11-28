---
title: "Ajouter un autre téléphone ou une tablette"
description: "Donnez à un autre téléphone, une tablette ou un écran de voiture sa propre clé pour votre comma avec une invitation de 10 minutes, et voyez ou retirez les téléphones qui en ont une."
topic: start
order: 4
kind: walkthrough
lede: "Chaque téléphone qui regarde votre comma a sa propre clé. Pour ajouter un autre téléphone, une tablette ou un écran de voiture, affichez une invitation sur un téléphone qui a déjà votre comma, puis tapez-la ou scannez-la sur le nouveau. Pas de SSH, pas de nouvelle configuration."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Un téléphone avec une clé"
    text: "Un téléphone déjà associé à votre comma, avec CommaView 0.0.166 ou ultérieur et son runtime. Pas encore ? [Installer CommaView](/fr/guides/setup)."
  - title: "CommaView sur le nouvel appareil"
    text: "Installé et connecté, en version 0.0.166 ou ultérieure. [Obtenir l'application](/fr/guides/setup#step-get-the-app)."
  - title: "Le même réseau"
    text: "Les deux sur le même Wi‑Fi que le comma, ou sur son point d'accès."
howItWorks:
  - title: "Votre téléphone"
    text: "Demande une invitation au comma : un code ou un code QR, valable 10 minutes."
  - title: "Le nouveau téléphone"
    text: "Rejoint avec l'invitation et reçoit sa propre clé."
    edge: "réseau local"
  - title: "Votre comma"
    text: "Prévient chaque téléphone qui a une clé qu'un nouveau en a une."
steps:
  - id: device-settings
    title: "Sur votre téléphone, ouvrir Associer un autre téléphone"
    body: |
      Sur le téléphone qui a déjà votre comma, ouvrez les **Paramètres de l'appareil** du comma depuis l'accueil, puis **Associer un autre téléphone**.
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**Associer un autre téléphone** : un code temporaire pour connecter un autre téléphone ou une tablette."
  - id: show-invitation
    title: "Afficher une invitation"
    body: |
      Sous **Téléphones avec une clé**, **Ajouter un autre téléphone** affiche une invitation pour un téléphone qui n'a pas encore ce comma. Touchez **Afficher l'invitation**.
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**Afficher l'invitation**."
      - text: "Les téléphones qui ont une clé pour ce comma, celui-ci en premier."
  - id: invitation
    title: "Garder l'invitation à l'écran"
    body: |
      **Ajouter un autre téléphone** affiche un code en trois groupes, un code QR et l'adresse IP du comma. Il est valable 10 minutes et ne sert qu'une fois. Quand il expire, affichez-en un nouveau.
    screen: invitation-dialog
    pins:
      - target: code
        text: "Le code à taper sur le nouveau téléphone."
      - target: qr
        text: "Ou le code QR à scanner."
      - text: "**Expire dans …** : 10 minutes à partir de son affichage."
  - id: add-comma
    title: "Sur le nouveau téléphone, ajouter le comma"
    body: |
      Sur le nouveau téléphone, touchez **Associer un comma qui exécute CommaView** sur **Connectez votre comma**. S'il a déjà un comma, touchez plutôt **Ajouter un comma** sur l'accueil.

      Votre comma apparaît sous **Sur ce réseau**. Touchez-le, ou touchez **Scanner le code QR** et scannez l'invitation. S'il n'est pas listé, touchez **Saisir l'adresse et le code**.
    screen: add-comma
    pins:
      - target: found-comma
        text: "Votre comma, trouvé sur ce réseau."
      - target: scan-qr
        text: "**Scanner le code QR** pour scanner l'invitation."
      - target: enter-address
        text: "**Saisir l'adresse et le code** quand il n'est pas listé."
  - id: pair
    title: "Taper l'invitation et associer"
    body: |
      Vérifiez l'**IP du comma**, tapez l'invitation dans **Code d'association ou invitation** (ou touchez le bouton QR pour la scanner), puis touchez **Associer le comma**. Le nouveau téléphone reçoit sa propre clé et affiche votre comma sur l'accueil.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**IP du comma**, remplie pour un comma trouvé."
      - target: pair-code
        text: "**Code d'association ou invitation**."
      - target: scan-qr
        text: "**Scanner le QR d'association**."
      - target: pair
        text: "**Associer le comma**."
  - id: new-key
    title: "Confirmer sur vos autres téléphones"
    body: |
      Chaque téléphone qui a une clé est prévenu : **Un nouveau téléphone a une clé**, avec son nom et l'heure. Touchez **C'est le mien**. S'il n'est pas à vous, touchez **Supprimer** ; **Voir les téléphones** ouvre **Associer un autre téléphone**, où chaque téléphone avec une clé est listé.
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "**C'est le mien**, pour votre propre téléphone ou tablette."
      - target: review
        text: "**Voir les téléphones** liste chaque téléphone qui a une clé."
check: "Le nouveau téléphone affiche votre comma sur l'accueil et ouvre Live View. Sur votre premier téléphone, **Associer un autre téléphone** le liste sous **Téléphones avec une clé**."
fixes:
  - q: "« Impossible de rejoindre avec cette invitation »"
    a: "Elle est peut-être mal saisie, expirée ou déjà utilisée. Affichez-en une nouvelle sur le téléphone qui a déjà ce comma (dans ses Paramètres de l'appareil : **Associer un autre téléphone**, **Ajouter un autre téléphone**)."
  - q: "« Le runtime de ce comma est antérieur aux clés de téléphone »"
    a: "Mettez d'abord à jour le runtime du comma : [Mettre à jour le runtime de votre comma](/fr/guides/update-runtime). Affichez ensuite l'invitation."
  - q: "« Impossible de joindre ce comma »"
    a: "Les deux téléphones doivent être sur le même Wi‑Fi que le comma, ou sur son point d'accès. [Se connecter en voiture](/fr/guides/connect-in-the-car)."
  - q: "« Échec de l'association : ce comma ne s'associe plus par code »"
    a: "Le comma n'accepte plus l'ancien jeton partagé. Ajoutez le téléphone depuis un appareil qui a déjà une clé (dans ses paramètres : **Ajouter un autre téléphone**), ou relancez la configuration du comma."
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## Retirer un téléphone

Sur un téléphone qui a une clé, ouvrez les **Paramètres de l'appareil** du comma, puis **Associer un autre téléphone**. Touchez **Supprimer** à côté d'un téléphone de la liste. Il ne peut plus joindre ce comma tant qu'il n'est pas ajouté à nouveau, avec une invitation ou en reconfigurant le comma.

## Téléphones avec une ancienne version de CommaView

Avant la 0.0.166, chaque téléphone envoyait au comma le même jeton partagé. Un téléphone en 0.0.166 reçoit sa clé à sa prochaine connexion, sans nouvelle association.

- **Anciennes applications CommaView**, dans **Associer un autre téléphone**, indique combien de jours un téléphone avec une ancienne version de CommaView peut encore utiliser ce comma avec le jeton partagé : 90 jours après que son premier téléphone a reçu une clé. D'ici là, **Code d'association pour une ancienne app** associe un téléphone avec une ancienne version de CommaView.
- **Arrêter maintenant** fait que le comma n'accepte plus le jeton partagé, une fois que chaque téléphone qui l'utilise a une clé. Les téléphones avec une ancienne version de CommaView ne fonctionnent alors plus avec ce comma, et ne peuvent pas s'associer à nouveau avant d'être mis à jour.
- Ensuite, un téléphone sans clé a besoin de CommaView 0.0.166 ou ultérieur et d'une invitation.

Quand vous mettez à jour le runtime de votre comma, mettez d'abord à jour CommaView sur chaque appareil qui le regarde, écrans de voiture compris.
