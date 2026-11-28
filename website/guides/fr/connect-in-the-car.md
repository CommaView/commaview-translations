---
title: "Se connecter en voiture sans Wi‑Fi domestique"
description: "Mettez votre téléphone et votre comma sur un même réseau en voiture : point d'accès du téléphone, du comma ou d'un écran de voiture, et que faire quand CommaView ne joint pas le comma."
topic: start
order: 3
kind: walkthrough
lede: "Live View va directement du comma à votre téléphone par un réseau local, pas par Internet. Peu importe à qui appartient le réseau : votre téléphone et le comma doivent seulement être sur le même. En voiture, c'est généralement un point d'accès."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView installé"
    text: "Votre comma associé à ce téléphone. Pas encore ? [Installer CommaView](/fr/guides/setup)."
  - title: "Pas de VPN"
    text: "Désactivez tout VPN sur le téléphone ou l'écran de voiture pendant que vous utilisez CommaView."
howItWorks:
  - title: "Votre comma"
    text: "Sert Live View et les enregistrements sur le réseau où il se trouve."
    edge: "un point d'accès"
  - title: "Votre téléphone"
    text: "Trouve le comma tout seul sur ce réseau, même si son adresse change."
steps:
  - id: network
    title: "Mettre le téléphone et le comma sur un même réseau"
    body: |
      Choisissez ce qui convient à votre voiture : celui qui démarre tout seul avec la voiture est généralement le plus simple. Vous connectez le comma à un réseau sur son propre écran, dans **Paramètres › Réseau**.
    tabs:
      - label: "Point d'accès de votre téléphone"
        body: "Activez le point d'accès de votre téléphone et connectez-y le comma. CommaView sur ce même téléphone joint le comma par ce réseau, et le comma y trouve aussi Internet."
      - label: "Point d'accès du comma"
        body: "Activez le point d'accès du comma (openpilot parle de partage de connexion : sur un comma four, **Paramètres › Réseau › Activer le partage de connexion** ; sur un comma 3X, **Paramètres › Réseau › Avancé › Activer le partage de connexion**) et rejoignez-le depuis les paramètres Wi‑Fi de votre téléphone. Le point d'accès du comma ne donne pas Internet."
      - label: "Point d'accès d'un écran de voiture"
        body: "Si un boîtier IA ou un système multimédia peut partager un point d'accès (beaucoup le peuvent avec une carte SIM), activez-le et connectez-y le comma, et votre téléphone si vous en utilisez un. [Écrans de voiture](/fr/guides/car-screens) en dit plus."
    note: "Certains points d'accès isolent les appareils connectés les uns des autres. Si CommaView ne trouve pas le comma sur l'un, essayez-en un autre."
  - id: home
    title: "Ouvrir CommaView"
    body: |
      L'accueil affiche votre comma **Connecté** dès qu'il répond sur le nouveau réseau : CommaView le trouve tout seul, même à une nouvelle adresse. Le comma se met en veille quand la voiture est éteinte, alors démarrez d'abord la voiture.

      Si l'accueil affiche le comma hors ligne avec **Connexion impossible ?**, vérifiez que le téléphone est sur le même Wi‑Fi que le comma, ou sur son point d'accès, puis touchez **Reconnecter**.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Reconnecter** réessaie de joindre le comma."
      - target: cant-connect
        text: "**Connexion impossible ?** dit ce qu'il faut au téléphone : le même Wi‑Fi que le comma, ou son point d'accès."
  - id: address
    title: "S'il reste introuvable, saisir son adresse"
    body: |
      Ouvrez les **Paramètres de l'appareil** du comma, puis **Nom et adresse**, et modifiez son adresse IP. Sur le point d'accès du comma, c'est **192.168.43.1** (la même pour tous les comma). Sur tout autre réseau, c'est l'adresse que le comma affiche dans **Paramètres › Réseau** : sous le nom du réseau sur le bouton Wi‑Fi d'un comma four, ou sous **Avancé** sur un comma 3X. Touchez **Enregistrer**.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "L'adresse IP du comma sur ce réseau."
      - target: save
        text: "**Enregistrer**."
  - id: live-view
    title: "Ouvrir Live View"
    body: |
      Touchez **Ouvrir Live View** sur l'accueil. Si le téléphone perd le comma, Live View dit pourquoi et se reconnecte tout seul quand le comma répond. **Impossible de joindre ce comma** signifie que le téléphone n'est pas sur le réseau du comma : corrigez cela, puis touchez **Réessayer**.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**Impossible de joindre ce comma** : pourquoi Live View s'est arrêté."
      - target: retry
        text: "**Réessayer**, une fois le téléphone revenu sur le réseau du comma."
check: "L'accueil affiche votre comma **Connecté**, et Live View montre la route avec la trajectoire dessinée par-dessus."
fixes:
  - q: "« Impossible de joindre ce comma »"
    a: "Le téléphone doit être sur le même Wi‑Fi que le comma, ou sur son point d'accès. Vérifiez quel réseau le téléphone a rejoint (il est peut-être revenu sur un Wi‑Fi connu), désactivez tout VPN, et touchez **Réessayer**."
  - q: "« Live View est ouvert sur un autre appareil »"
    a: "Ce comma ne diffuse que vers un téléphone ou système multimédia à la fois. Revenez à l'accueil dans CommaView sur l'autre appareil, et Live View démarre ici tout seul."
  - q: "« CommaView ne répond pas »"
    a: "Il redémarre peut-être sur le comma. Live View se reconnecte dès qu'il revient."
  - q: "CommaView dit avoir besoin d'Internet pour se renouveler"
    a: "Pendant la bêta, CommaView renouvelle de temps en temps son pass d'accès, et le point d'accès du comma ne compte pas comme Internet. Donnez un instant au téléphone des données mobiles ou un Wi‑Fi avec Internet."
  - q: "Ça marchait sur un point d'accès et pas sur un autre"
    a: "Certains points d'accès isolent les appareils connectés, donc le téléphone ne voit pas le comma. Essayez un autre des réseaux de l'étape 1."
related: [comma-not-found, car-screens, browser-view, setup-troubleshooting]
---

## Détection, association et adresse

Trois choses distinctes doivent fonctionner, et savoir laquelle a échoué vous dit quoi corriger :

- **Trouver le comma.** CommaView cherche votre comma sur le réseau du téléphone, et met à jour l'adresse enregistrée quand il retrouve le même comma ailleurs. Certains réseaux bloquent cette recherche ; saisir l'adresse (étape 3) la contourne.
- **Le joindre.** Le téléphone doit joindre le comma sur ce réseau. Un ordinateur portable qui se connecte au comma en SSH ne prouve pas que le téléphone le peut.
- **L'association.** Une fois le comma joint, le téléphone utilise la clé reçue lors de l'association. Changer de réseau n'annule pas l'association : vous n'avez pas à associer de nouveau.
