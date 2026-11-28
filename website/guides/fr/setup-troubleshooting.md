---
title: "Débloquer une configuration qui s'arrête"
description: "Ce que signifient les messages de configuration de CommaView, dans l'ordre de la configuration : SSH, l'installation, puis l'association. Trouvez votre message et quoi faire."
topic: troubleshooting
order: 1
kind: fixes
lede: "La configuration avance dans l'ordre : elle se connecte à votre comma en SSH, installe le runtime de CommaView, puis associe votre téléphone. Quand elle s'arrête, son message dit quelle partie a échoué : corrigez d'abord celle-là. Que SSH fonctionne ne prouve que la première : un code d'association ne peut pas marcher tant que le runtime n'a jamais démarré."
parked: true
updated: 2026-11-27
needs:
  - title: "En position P"
    text: "La voiture en position P avec openpilot désengagé, et allumée : sans câble d'alimentation permanente, l'éteindre éteint aussi le comma."
  - title: "Un seul réseau"
    text: "Votre téléphone sur le même Wi‑Fi que le comma, ou sur son point d'accès. Un ordinateur portable qui joint le comma ne prouve pas que votre téléphone le peut."
steps:
  - id: read
    title: "Lire ce que dit la configuration, et copier les détails"
    body: |
      Quand l'installation échoue, la configuration dit ce qui n'a pas marché, si votre comma a été remis dans son état d'origine, et quoi faire. Trouvez cette phrase plus bas, sous [Si ça ne marche pas](#fixes).

      **Copier les détails** copie le rapport que lit l'assistance : la version de l'application, la version publiée, la dernière étape de l'installateur et toute sa sortie. Collez-le dans un e-mail à support@commaview.com quand le message le demande.
    tabs:
      - label: "L'installation a échoué"
        body: "La configuration dit ce qui a échoué et propose **Copier les détails**."
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**Copier les détails**."
          - target: install
            text: "**Installer CommaView** réessaie une fois la cause corrigée."
      - label: "SSH a échoué"
        body: "Avant toute installation, la configuration dit pourquoi elle n'a pas pu accéder au comma, par exemple **Échec de l'authentification SSH**, et quoi vérifier."
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "Ce qui n'a pas marché, et quoi vérifier."
  - id: address
    title: "Vérifier l'adresse du comma"
    body: |
      La configuration cherche les comma sur le réseau de votre téléphone. Si le vôtre n'est pas listé, touchez **Mon comma n'est pas listé** et tapez son adresse IP. Sur votre comma, elle se trouve dans **Paramètres → Réseau** : sous le nom du réseau sur le bouton Wi‑Fi d'un comma four, ou sous **Avancé** sur un comma 3X.

      Le comma a une adresse différente sur chaque réseau : votre Wi‑Fi domestique, un point d'accès, un VPN. Utilisez celle du réseau où se trouve votre téléphone en ce moment.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Un comma que la configuration a trouvé sur ce réseau."
      - text: "**Mon comma n'est pas listé** : tapez l'adresse IP quand il n'est pas trouvé."
  - id: pair-code
    title: "Associer avec un nouveau code"
    body: |
      Les codes d'association sont temporaires et à usage unique. Si l'un est refusé, ne le retapez pas : obtenez-en un nouveau. Après une installation manuelle, l'installateur en affiche un ; un téléphone déjà associé au comma en affiche un dans **Paramètres de l'appareil › Associer un autre téléphone ou une tablette**.
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**Adresse IP du comma**."
      - target: pair-code
        text: "**Code d'association**. Tiret facultatif."
  - id: runs
    title: "Déjà installé ? Associez plutôt"
    body: |
      Si le comma exécute déjà CommaView, depuis un autre téléphone ou une configuration précédente, inutile de réinstaller. Sur l'accueil, touchez **Ajouter un comma**, puis **Saisir l'adresse et le code**, et associez avec l'IP du comma et un code d'association ou une invitation.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "L'IP du comma."
      - target: pair-code
        text: "**Code d'association ou invitation**."
      - target: pair
        text: "**Associer le comma**."
  - id: no-video
    title: "Installé et associé, mais pas de vidéo"
    body: |
      Après l'association, une image absente est un problème de diffusion, pas de SSH. Live View dit ce qu'il constate, par exemple **Impossible de joindre ce comma**, et se reconnecte tout seul quand le comma répond. Voyez [CommaView ne trouve pas votre comma](/fr/guides/comma-not-found).
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**Réessayer**."
fixes:
  - q: "« Échec de l'authentification SSH. »"
    a: "Vérifiez que la clé CommaView est sur GitHub (titre quelconque) et que SSH est activé sur le comma. Si vous avez saisi votre nom d'utilisateur GitHub sur le comma avant d'ajouter la clé, supprimez-le et saisissez-le à nouveau, pour que le comma récupère de nouveau vos clés."
  - q: "« Connexion refusée à 192.168.1.50:22. Vérifiez que SSH est activé sur votre comma. »"
    a: "Sur le comma, allez dans **Paramètres → Appareil → SSH** et activez SSH."
  - q: "« Délai de connexion dépassé vers … » ou « Aucune route vers … »"
    a: "Votre téléphone ne joint pas cette adresse. Vérifiez que votre téléphone est sur le même Wi‑Fi que le comma, ou sur son point d'accès, que le comma est réveillé (voiture allumée), et que l'adresse IP est celle du comma sur ce réseau."
  - q: "« Aucun comma trouvé à … Vérifiez l'adresse IP. »"
    a: "Rien n'a répondu à cette adresse. Vérifiez l'IP dans **Paramètres → Réseau** sur le comma."
  - q: "« L'identité SSH de ce comma a changé depuis sa dernière configuration. »"
    a: "Si vous avez réinitialisé ou reflashé le comma, relancez la configuration."
  - q: "« CommaView n'a pas pu créer sa clé SSH sur ce téléphone. Réessayez, ou utilisez votre propre clé SSH. »"
    a: "Touchez **Réessayer**, ou **Utiliser ma propre clé SSH** pour importer une paire de clés que vous avez déjà sur GitHub."
  - q: "« Installation en attente. »"
    a: "La voiture roulait, donc le comma a mis l'installation en attente au lieu d'interrompre le trajet. Mettez la voiture en position P avec openpilot désengagé, laissez-la allumée une minute ou deux, puis touchez **Terminer la configuration**."
  - q: "« La voiture roule, donc l'installation n'a pas eu lieu. »"
    a: "Mettez la voiture en position P avec openpilot désengagé, puis réessayez."
  - q: "« Une autre installation, mise à jour ou réparation de CommaView est déjà en cours sur votre comma. »"
    a: "Attendez quelques minutes qu'elle se termine, puis réessayez."
  - q: "« Votre comma n'a pas pu télécharger CommaView. »"
    a: "Le comma télécharge lui-même le runtime. Vérifiez qu'il est connecté à Internet, par Wi‑Fi ou par sa propre carte SIM, puis réessayez. Un point d'accès de téléphone avec des données mobiles fonctionne."
  - q: "« Le téléchargement de CommaView est arrivé incomplet ou endommagé sur votre comma. »"
    a: "Réessayez. Si cela se reproduit, copiez les détails et envoyez-les à support@commaview.com."
  - q: "« Votre comma a manqué d'espace de stockage pendant l'installation. »"
    a: "Réessayez plus tard. Si cela se reproduit, copiez les détails et envoyez-les à support@commaview.com."
  - q: "« CommaView ne prend pas encore en charge le logiciel de conduite de votre comma. »"
    a: "Votre comma exécute un logiciel sur lequel CommaView ne peut pas s'installer. [Vérifiez avec quels forks il fonctionne](/fr/guides/forks). Pour demander le vôtre, copiez les détails et envoyez-les à support@commaview.com."
  - q: "« CommaView ne peut pas ajouter sa vue de façon sûre dans … »"
    a: "Votre fork fait partie de ceux que CommaView ne liste pas, et sa vérification a trouvé que son écran diffère là où CommaView s'y branche. Rien n'a été changé sur votre comma. Pour demander votre fork, copiez les détails et envoyez-les à support@commaview.com."
  - q: "« Le comma 3 n'est pas pris en charge »"
    a: "CommaView fonctionne avec le comma 3X et le comma four. La version d'openpilot du comma 3 est figée en amont et dessine son écran autrement, donc CommaView ne peut pas afficher ses surimpressions."
  - q: "« CommaView n'a pas démarré sur votre comma après l'installation. »"
    a: "Redémarrez votre comma, puis réessayez. Si cela se reproduit, copiez les détails et envoyez-les à support@commaview.com."
  - q: "« Échec de la vérification. Impossible de joindre l'API CommaView à 192.168.1.50:5002. »"
    a: "L'installation est terminée, mais votre téléphone ne joint pas le runtime. Vérifiez que votre téléphone est toujours sur le réseau du comma, puis réessayez. Si SSH fonctionne depuis un ordinateur mais pas ceci, l'ordinateur est sur un réseau où votre téléphone n'est pas."
  - q: "« Le code d'association n'a pas pu être utilisé. »"
    a: "Le code a expiré, a déjà servi ou a été mal tapé. Obtenez-en un nouveau ([étape 3](#step-pair-code))."
  - q: "« Échec de l'association : l'API du runtime CommaView était injoignable »"
    a: "Votre téléphone ne joint pas le comma à cette adresse. Vérifiez le point d'accès ou le réseau, puis réessayez."
  - q: "« CommaView ne démarrera pas tout seul après un redémarrage »"
    a: "CommaView est installé, mais rien ne le lance au démarrage de votre comma : le fichier `/data/continue.sh` de votre comma n'a pas de ligne `exec ./launch_openpilot.sh`. Une fois qu'il en a une, réinstallez CommaView."
related: [setup, comma-not-found, support-bundle]
---

## Les étapes de la configuration

Chaque étape a besoin de la précédente, alors vérifiez-les dans cet ordre :

1. **SSH**, port 22 : la façon dont la configuration accède au comma pour installer. Il faut votre clé GitHub, votre nom d'utilisateur GitHub sur le comma, et SSH activé.
2. **L'installation** : le comma télécharge le runtime et l'installe. Lisez son résultat avant tout le reste.
3. **Le runtime**, port 5002 sur le comma : la configuration vérifie qu'il répond, puis s'associe à lui.
4. **L'association** : un code d'association à usage unique donne à votre téléphone sa propre clé pour le comma.
5. **La vidéo**, ports 8200 à 8202 : les caméras de Live View.

Si la détection ne trouve pas le comma mais que vous connaissez son adresse, la taper marche tout aussi bien : la détection est un confort, et c'est joindre le comma qui compte.

## Sécurité

Faites la configuration, les installations et le dépannage avec la voiture en position P et openpilot désengagé. Ne configurez jamais et ne manipulez jamais l'application en conduisant.
