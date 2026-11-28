---
title: "CommaView ne trouve pas votre comma"
description: "L'accueil indique Hors ligne ou Live View ne joint pas votre comma ? Vérifiez le réseau, l'adresse du comma et son association, dans cet ordre."
topic: troubleshooting
order: 2
kind: fixes
lede: "CommaView parle directement à votre comma sur votre réseau local, sans service cloud entre les deux. Quand il ne le trouve pas, c'est presque toujours que votre téléphone et le comma sont sur des réseaux différents, que le comma est en veille avec la voiture éteinte, ou que son adresse a changé. Vérifiez cela d'abord, puis son association."
parked: true
updated: 2026-11-27
needs:
  - title: "La voiture allumée"
    text: "Le comma se met en veille quand la voiture est éteinte. Allumez la voiture, en position P."
  - title: "Un seul réseau"
    text: "Votre téléphone sur le même Wi‑Fi que le comma, ou sur son point d'accès. En voiture : [se connecter en voiture](/fr/guides/connect-in-the-car)."
steps:
  - id: home
    title: "Voir ce que dit l'accueil"
    body: |
      Quand votre téléphone ne joint pas le comma, l'accueil l'affiche **Hors ligne**, avec **Reconnecter**, et une carte **Connexion impossible ?** : « Votre téléphone doit être sur le même Wi-Fi que le comma, ou sur son point d'accès. Le comma se met en veille quand la voiture est éteinte. »

      Vérifiez les deux, puis touchez **Reconnecter**.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Reconnecter**."
      - target: cant-connect
        text: "La carte **Connexion impossible ?**."
  - id: live-view
    title: "Dans Live View : attendre, ou réessayer"
    body: |
      Live View dit pourquoi il s'est arrêté. **Impossible de joindre ce comma** signifie que votre téléphone ne le joint pas sur le réseau. Il se reconnecte tout seul quand le comma répond ; **Réessayer** retente tout de suite.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**Impossible de joindre ce comma** : pourquoi Live View s'est arrêté."
      - target: retry
        text: "**Réessayer**."
  - id: network
    title: "Vérifier le réseau de votre téléphone"
    body: |
      Ouvrez les paramètres Wi‑Fi de votre téléphone et vérifiez qu'il est connecté au réseau du comma : le même Wi‑Fi domestique, le point d'accès de votre téléphone avec le comma connecté dessus, ou le point d'accès du comma.

      - Un téléphone qui a quitté un Wi‑Fi sans Internet pour les données mobiles ne joint pas le comma. Reconnectez-le.
      - Un VPN sur votre téléphone peut envoyer son trafic ailleurs. Désactivez-le et réessayez.
      - Certains points d'accès empêchent les appareils connectés de se joindre. Essayez un autre réseau, comme le point d'accès du comma.
    note: "Les paramètres Wi‑Fi et de point d'accès d'Android ne sont pas illustrés : ils diffèrent d'un téléphone à l'autre."
  - id: address
    title: "Vérifier l'adresse du comma"
    body: |
      Le comma reçoit une nouvelle adresse quand il rejoint un autre réseau, ou quand un routeur lui en donne une nouvelle. CommaView le retrouve tout seul quand il le voit sur le réseau ; sinon, enregistrez vous-même son adresse.

      Sur le comma, trouvez son adresse IP dans **Paramètres → Réseau**. Dans CommaView, ouvrez les **Paramètres de l'appareil** depuis l'accueil, touchez **Changer le nom ou l'adresse**, modifiez **Adresse IP**, tapez l'adresse du comma et touchez **Enregistrer**.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "L'adresse IP du comma."
      - target: save
        text: "**Enregistrer**."
  - id: add
    title: "Toujours introuvable ? L'ajouter à nouveau"
    body: |
      Sur l'accueil, touchez **Ajouter un comma**. **Sur ce réseau** liste les comma qui exécutent CommaView sur le réseau de votre téléphone : touchez le vôtre. S'il n'y est pas, touchez **Saisir l'adresse et le code**, ou **Scanner le code QR** sur un téléphone déjà associé.
    screen: add-comma
    pins:
      - target: found-comma
        text: "**Sur ce réseau** : un comma trouvé à proximité."
      - target: enter-address
        text: "**Saisir l'adresse et le code**."
      - target: scan-qr
        text: "**Scanner le code QR**."
  - id: pair
    title: "Associer avec son adresse et un nouveau code"
    body: |
      Tapez l'IP du comma et un code d'association ou une invitation, puis touchez **Associer le comma**. Les codes expirent vite : un téléphone déjà associé au comma en affiche un nouveau dans **Paramètres de l'appareil**, sous **Associer un autre téléphone ou une tablette**.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "L'IP du comma."
      - target: pair-code
        text: "**Code d'association ou invitation**."
      - target: pair
        text: "**Associer le comma**."
    note: "Si saisir son adresse fonctionne mais que le comma n'apparaît jamais tout seul, le réseau masque la détection de CommaView. Ce n'est pas grave : c'est l'adresse qui compte."
check: "L'accueil affiche votre comma **Connecté**, et **Ouvrir Live View** ouvre l'image."
fixes:
  - q: "« Impossible de joindre ce comma »"
    a: "Votre téléphone doit être sur le même Wi‑Fi que le comma, ou sur son point d'accès. Live View se reconnecte quand il répond. Vérifiez le réseau ([étape 3](#step-network)) et l'adresse du comma ([étape 4](#step-address))."
  - q: "« CommaView ne répond pas »"
    a: "Le comma répond, mais pas CommaView dessus. Il redémarre peut-être sur le comma : Live View se reconnecte dès qu'il revient. Si cela persiste, redémarrez le comma, garé."
  - q: "« Aucune vidéo de ce comma »"
    a: "Il répond, mais sa vidéo n'est pas revenue. Réessayez, ou revenez en arrière et vérifiez le comma : openpilot est peut-être encore en train de démarrer."
  - q: "« Live View est ouvert sur un autre appareil »"
    a: "Ce comma ne diffuse que vers un téléphone ou système multimédia à la fois. Revenez à l'accueil dans CommaView sur l'autre appareil, et Live View démarre ici tout seul."
  - q: "« Le comma n'a pas répondu à temps. »"
    a: "Une liaison faible ou chargée. Vérifiez que votre téléphone est sur le Wi‑Fi ou le point d'accès du comma, plus près si possible, puis réessayez."
  - q: "« Le comma a refusé la connexion. CommaView est peut-être en train de redémarrer dessus. »"
    a: "Attendez un instant qu'il revienne, puis réessayez."
  - q: "« Les données de la voiture n'arrivent pas »"
    a: "La vidéo arrive, mais pas la vitesse, les clignotants ni les alertes de la voiture. Redémarrez le comma pour corriger cela."
  - q: "« Échec de l'association : code d'association expiré. Générez un nouveau code et réessayez. »"
    a: "Obtenez un nouveau code sur un téléphone déjà associé au comma, dans **Paramètres de l'appareil › Associer un autre téléphone ou une tablette**, et associez de nouveau."
  - q: "« Échec de l'association : code d'association invalide. Vérifiez le code ou scannez le QR. »"
    a: "Vérifiez le code tapé (les tirets sont facultatifs), ou scannez plutôt son code QR."
  - q: "« Mettre à jour le runtime de ce comma » ou « Mettre à jour CommaView »"
    a: "Cette application et le runtime du comma sont trop éloignés pour communiquer. Mettez à jour celui qui est nommé : le runtime depuis Paramètres de l'appareil ([Mettre à jour le runtime](/fr/guides/update-runtime)), ou l'application."
  - q: "« Impossible de lire vos comma enregistrés »"
    a: "Les comma enregistrés sur ce téléphone n'ont pas pu être lus, donc aucun n'est affiché. Ils n'ont pas été supprimés. Réessayez, ou touchez **Repartir de zéro** et associez de nouveau chaque comma : l'ancienne liste est gardée au moins 90 jours."
related: [connect-in-the-car, setup-troubleshooting, another-phone]
---

## Comment CommaView trouve un comma

- **La détection** trouve les comma qui exécutent CommaView sur le réseau de votre téléphone, pour que vous n'ayez pas à taper d'adresse. Certains réseaux la bloquent.
- **L'adresse** est ce à quoi CommaView se connecte. La saisir fonctionne, que la détection marche ou non.
- **L'association** donne à votre téléphone sa propre clé pour le comma, avec un code temporaire. Détection et association sont distinctes : un comma que votre téléphone joint doit quand même être associé.
- **Un comma enregistré** est reconnu par son identité, pas seulement par son adresse : quand il apparaît à une nouvelle adresse, CommaView met à jour celle enregistrée.

## Sécurité

Vérifiez les réseaux et associez à l'arrêt. Ne manipulez pas CommaView en conduisant.
