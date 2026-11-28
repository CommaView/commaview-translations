---
title: "CommaView 0.0.166 : une clé par téléphone, 11 langues de plus et Browser View"
description: "CommaView 0.0.166 donne une clé à chaque téléphone, parle 11 langues de plus, affiche Live View dans le navigateur de la voiture, garde vos trajets et ouvre la boutique de packs."
date: 2026-11-16
slug: commaview-0-0-166-languages-browser-view
tags:
  - security
  - languages
  - browser view
  - recordings
  - overlay packs
heroLabel: "Notes de version"
draft: false
---

CommaView 0.0.166 est disponible pour tous les membres de la bêta. Avec le nouveau runtime, **chaque téléphone reçoit sa propre clé** pour votre comma, et personne n'a à refaire l'association. CommaView parle **11 langues de plus**, affiche Live View dans le navigateur web de votre voiture avec **Browser View**, garde vos trajets sur votre téléphone avec **Garder ce moment**, **Exporter le trajet complet…** et **Récupérer les trajets automatiquement**, et ouvre la **boutique de packs de superposition**.

Il est accompagné du runtime `v0.0.62-beta`. **Mettez d'abord à jour CommaView**, puis le runtime depuis l'application quand elle le propose, et redémarrez le comma quand elle le demande. Un téléphone encore en 0.0.165 continue de fonctionner pendant 90 jours après que le premier téléphone de votre comma a reçu sa clé. Ne réinstallez pas votre comma depuis un téléphone en 0.0.165 : l'installation depuis celui-ci remet l'ancien runtime, et les téléphones avec une clé ne peuvent plus joindre le comma.

## Une clé par téléphone

Avec le nouveau runtime, chaque téléphone reçoit sa propre clé pour votre comma, à la place du jeton partagé que chaque téléphone envoyait jusqu'ici. La clé ne passe jamais sur le réseau, et personne n'a à refaire l'association : un téléphone en 0.0.166 reçoit sa clé à sa prochaine connexion.

- **Un nouveau téléphone a une clé.** Chaque téléphone avec une clé est prévenu quand un autre en reçoit une, avec **C'est le mien**, **Supprimer** et **Voir les téléphones**, qui ouvre Paramètres de l'appareil › Associer un autre téléphone, où chaque téléphone avec une clé est listé.
- **Ajouter un téléphone.** **Afficher l'invitation** sur un téléphone avec une clé donne un code ou un QR code, valable 10 minutes.
- **Anciennes applications.** Votre comma accepte l'ancien jeton partagé pendant 90 jours après que son premier téléphone a reçu une clé, ou jusqu'à ce que quelqu'un touche **Arrêter maintenant**. D'ici là, **Code d'association pour une ancienne app** associe un téléphone sous une ancienne version de CommaView. Ensuite, un téléphone sans clé a besoin de la 0.0.166 et d'une invitation.

## CommaView dans votre langue

Paramètres › **Langue** propose maintenant Deutsch, Español, Français, 日本語, 한국어, Português (Brasil), ไทย, Türkçe, Українська, 简体中文 et 繁體中文 à côté de l'English. **Langue du téléphone**, le réglage par défaut, prend la première langue de la liste de votre téléphone que CommaView connaît, sinon l'anglais, et la ligne indique laquelle elle utilise. Sur Android 13 et plus récent, le réglage de langue par application d'Android fonctionne aussi.

Toutes les langues sauf l'anglais sont **traduites automatiquement**, et aucun locuteur natif n'en a encore relu une : attendez-vous à des mots faux et à des phrases maladroites. Une carte en haut des Paramètres le dit, et **Aidez à l'améliorer** ouvre les traductions de CommaView, où chacun peut proposer un meilleur mot. Vous pouvez aussi nous le dire sur [Discord](https://discord.gg/UuMhz9K8ft) ou depuis **Signaler un problème ou proposer une idée** : nommez l'écran et ce qu'il dit actuellement.

- **Les écrans de votre comma restent dans la langue de votre comma.** Les libellés d'un fork et les alertes de votre comma sont dessinés comme votre voiture les montre, désormais dans la police propre au fork quand votre comma est en chinois, japonais, coréen ou thaï.
- **Le texte anglais fait foi** pour le consentement au classement, et **Afficher en anglais** l'affiche. La politique de confidentialité et les conditions d'utilisation sont en anglais.
- **Les dates** suivent l'ordre de votre langue, et le titre et la description YouTube du direct, tant que vous ne les changez pas, sont dans la langue de l'application.
- **Le coréen** garde les mots entiers en fin de ligne. Sur Android 13 et antérieur, un nom coréen donné à un comma ou à un lieu peut encore être coupé.

## Browser View

Browser View affiche ce que montre Live View dans le navigateur web de votre voiture, servi par votre téléphone via son point d'accès ou son Wi‑Fi. Lancez-le depuis Live View › Détails › Browser View, tapez le lien court, `commaview.app/<code>`, dans le navigateur de la voiture et touchez **Ouvrir**. Dans une Tesla, touchez d'abord **Activer l'adresse VPN**.

L'image va de votre téléphone à la voiture, jamais par Internet ; seule la page du lien court y passe. Connecté, votre téléphone reçoit son propre nom et un certificat de confiance : une Tesla affiche alors un cadenas et l'image H.264, plus fluide. Déconnecté, une Tesla reçoit l'**Image simple**.

- **Commandes dans la voiture** : Enregistrer, Garder, Carte, l'écran de conduite, En direct et Caméra cond., à côté ou en dessous de l'image, jamais par-dessus.
- **Pas d'Internet dans la voiture ?** **Afficher les adresses** liste les adresses propres du téléphone.
- 720p ou 1080p, des codes à huit chiffres, et **Démarrer avec Live View** pour le lancer chaque fois que Live View s'ouvre.

Chaque étape, Tesla comprise : [Browser View](/fr/guides/browser-view).

Pendant qu'il tourne, votre téléphone envoie au service de compte de CommaView son code, ses ports et son adresse privée, pour que le lien court puisse le trouver. Toute personne qui a le code peut les voir, ainsi que le nom `commaview.app` de votre téléphone, tant que Browser View tourne et jusqu'à 2 heures après un arrêt inattendu, mais rien de tout cela n'ouvre quoi que ce soit sans le point d'accès ou le Wi‑Fi de votre téléphone. Ils sont supprimés 30 jours après la dernière utilisation de Browser View. Le nom `commaview.app` de votre téléphone et la date de son dernier certificat restent tant que votre compte existe, et le nom figure dans les journaux publics de certificats. [La politique de confidentialité](/privacy) (en anglais) donne les détails.

## Vos trajets sur votre téléphone

- **Garder ce moment.** **Garder**, dans Live View, conserve les 3 dernières minutes et la minute suivante d'un trajet ; un autre appui pendant cette minute ajoute une minute, jusqu'à 10 minutes. Rien n'est téléchargé pendant que vous roulez : une fois garé, c'est copié dans un MP4 sur votre téléphone.
- **Exporter le trajet complet…** Dans le menu Plus d'un trajet : la caméra route en un seul MP4, en plusieurs parties au-delà de 3,5 Go. La fenêtre indique sa taille et s'il tient, avant tout téléchargement.
- **Récupérer les trajets automatiquement.** Paramètres › Enregistrements : les nouveaux trajets sont rapatriés environ toutes les demi-heures sur les Wi‑Fi que vous choisissez, en Wi‑Fi seulement, dans la limite de la place que vous leur donnez. Une heure de conduite représente environ 4,5 Go.
- **Coupure de courant ?** Enregistrements prévient quand votre comma a perdu l'alimentation à la fin d'un trajet, et dit comment y remédier.

Tout cela, c'est la caméra route sans HUD, et cela reste sur votre téléphone même après que votre comma a effacé le trajet.

## Packs de superposition

Paramètres › **Packs de superposition**, ou la carte sur l'Accueil, ouvre la boutique. Les packs ajoutent à Live View ce que votre fork dessine sur son propre écran, comme les jauges hybrides de BluePilot ou la trajectoire arc-en-ciel de dragonpilot. Les membres parcourent les packs **Officiels** de CommaView, ceux de la **Communauté** et **Pour votre comma**, chacun avec un aperçu pour le style que dessine Live View. **Vos packs** a un seul interrupteur pour votre téléphone et chaque comma associé. Sans abonnement, vous pouvez ajouter un pack depuis un fichier ou un lien.

## Aussi dans 0.0.166

- **La navigation avec votre propre clé Stadia Maps**, pour les membres : Paramètres › Cartes et navigation › Votre clé Stadia Maps.
- **BluePilot, dragonpilot et OPGM** sont des forks listés, avec le nouveau runtime. Aucun n'a encore été conduit avec CommaView.
- **Live View sur plus de systèmes multimédias** : quand le décodeur vidéo du téléphone ne sait pas lire la vidéo du comma, il en essaie un autre.
- **Ouvrir CommaView tout seul** au démarrage d'un système multimédia ou à la connexion Bluetooth, et **Ouvrir Live View à la connexion**, dans Paramètres › Affichage. Pour faire tourner CommaView sur l'écran de votre voiture : [les meilleurs boîtiers IA Android](/fr/blog/android-ai-box-commaview).
- **Partager avec le développeur de mon fork…** : un extrait, un résumé et le journal de CommaView, à partager vous-même.
- **Live View dit ce qui se passe** : un redémarrage qu'il attend, des données de la voiture qui se sont arrêtées, une image en différé, pourquoi il se reconnecte, un autre appareil où il est ouvert.
- **Mettre à jour CommaView**, pour les membres, à partir de la 0.0.166 : la version d'abord, **Annuler le téléchargement**, et le téléchargement continue en arrière-plan.
- **Bords de l'écran**, des destinations du direct pour chaque plateforme, et plus rien de coupé en grand texte.

## Accès anticipé

Le direct vers X, Twitch, Kick et Facebook, Vidéo seule pour FrogPilot et KisaPilot, les réglages du fork, la création de packs de superposition et Surround restent derrière des options de fonctionnalité, pour un groupe restreint de testeurs. Si vous voulez aider à les tester, contactez-nous sur notre [Discord](https://discord.gg/UuMhz9K8ft) et préparez-vous à nous dire comment elles se comportent sur vos trajets.

## Comment mettre à jour

CommaView est en bêta sur invitation. Si vous en faites partie, l'application propose d'elle-même la 0.0.166. Mettez à jour CommaView, puis le runtime de votre comma depuis l'application, et redémarrez le comma quand elle le demande. Mettez à jour chaque téléphone et système multimédia qui regarde votre comma dans les 90 jours qui suivent la première clé.

## Pour aller plus loin

- [Quels forks d'openpilot fonctionnent avec CommaView](/fr/forks)
- [Les nouveautés](/fr/whats-new) de chaque version
- [Comment se font les versions de CommaView](/fr/guides/releases)

CommaView est non officiel et n'est affilié ni à comma.ai, ni à BluePilot, dragonpilot, OPGM ou aux autres forks cités. C'est un logiciel en bêta et non un système de sécurité : ne le laissez jamais vous distraire de la conduite.
