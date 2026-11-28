---
title: "Envoyer un paquet d'assistance"
description: "Gardez les diagnostics activés, reproduisez le problème, puis envoyez un rapport avec les journaux de votre téléphone et de votre comma depuis Paramètres › Assistance et diagnostics."
topic: troubleshooting
order: 3
kind: walkthrough
lede: "Un paquet d'assistance est un petit zip de ce que l'application CommaView a vu sur votre téléphone, et de ce que son runtime a vu sur votre comma. Il nous permet de trouver un problème sans être dans votre voiture. Il ne contient que des journaux : pas de vidéo, pas de position."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Diagnostics activés"
    text: "**Conserver les diagnostics sur ce téléphone**, activé sauf si quelqu'un l'a désactivé. Vérifiez-le avant que le problème se reproduise."
  - title: "Connecté à votre comma"
    text: "Pour les journaux de votre comma, l'accueil affiche votre comma **Connecté** quand vous envoyez."
  - title: "Connecté pour envoyer"
    text: "L'envoi demande votre compte bêta. Déconnecté, **Enregistrer dans un fichier** fonctionne quand même."
howItWorks:
  - title: "Votre téléphone"
    text: "Garde ses journaux et compteurs de vos 10 derniers trajets."
  - title: "Votre comma"
    text: "Ajoute les journaux de son runtime quand vous touchez Envoyer, sans position, VIN, identifiants, noms de Wi‑Fi ni jetons."
    edge: "quand vous touchez Envoyer"
  - title: "L'équipe CommaView"
    text: "Le lit dans un stockage privé, et répond par e-mail."
steps:
  - id: open
    title: "Ouvrir Assistance et diagnostics"
    body: |
      Dans CommaView, touchez **Paramètres** dans la barre du bas. Sur une tablette ou un système multimédia, il est dans le rail sur le côté. Touchez **Assistance et diagnostics**, vers la fin, avant À propos.
    screen: support-settings
    pins:
      - text: "**Assistance et diagnostics**."
  - id: keep-diagnostics
    title: "Conserver les diagnostics sur ce téléphone"
    body: |
      **Conserver les diagnostics sur ce téléphone** est activé sauf si quelqu'un l'a désactivé : l'application garde ses journaux et compteurs de vos 10 derniers trajets, pour qu'un rapport puisse dire ce qui s'est passé. S'il est désactivé, activez-le, puis reproduisez le problème.
    screen: support-diagnostics
    pins:
      - target: keep-diagnostics
        text: "**Conserver les diagnostics sur ce téléphone**."
    note: "Les diagnostics restent sur ce téléphone jusqu'à ce que vous envoyiez un rapport : ils ne sont jamais envoyés automatiquement."
  - id: happen-again
    title: "Reproduire le problème, garé"
    body: |
      Connectez-vous à votre comma comme d'habitude : votre téléphone sur le Wi‑Fi ou le point d'accès du comma, et l'accueil qui affiche votre comma **Connecté**. Refaites ce qui n'a pas marché ; par exemple, ouvrez Live View, passez à l'écran de conduite qui pose problème, et laissez-le 10 à 20 secondes. Notez à peu près quand c'est arrivé et ce que vous avez fait. Un enregistrement d'écran aide aussi.
    warn: "Reproduisez-le en position P. Si cela n'arrive que sur la route, laissez faire et envoyez le rapport une fois garé : l'historique vous attend. Ne manipulez jamais l'application en conduisant."
  - id: open-send
    title: "Ouvrir Envoyer à CommaView"
    body: |
      Dans **Assistance et diagnostics**, touchez **Signaler un problème ou proposer une idée**.

      Ou partez du problème : là où l'application affiche un échec, touchez son **Signaler** ; pour un enregistrement, choisissez **Envoyer à CommaView…** dans ses **Actions de l'enregistrement**. Chacun ouvre la même fenêtre, avec ce qui est pertinent déjà rempli.
    screen: support-diagnostics
    pins:
      - target: report
        text: "**Signaler un problème ou proposer une idée**."
  - id: send
    title: "Choisir ce qui part, et envoyer"
    body: |
      Choisissez **Problème** et dites ce qui s'est passé. Sous **Pièces jointes**, laissez **Ce téléphone : diagnostics** et les journaux de votre comma activés. **Voir** montre exactement ce que chacun contient. Sous les lignes, la fenêtre liste ce qui accompagne chaque rapport : la version de l'application, le modèle et la version d'Android de votre téléphone, et le logiciel de conduite et la configuration de votre comma.

      Touchez **Envoyer** : « Envoi en cours. Il se fait en arrière-plan et attend une connexion. »
    screen: support-send-feedback
    pins:
      - target: problem
        text: "**Problème** ou **Idée**."
      - text: "**Pièces jointes** : chaque ligne a un interrupteur et **Voir**."
      - target: send
        text: "**Envoyer**."
    note: "Envoyez pendant que l'application est connectée à votre comma : elle lui demande ses journaux quand vous touchez Envoyer. Si le comma est éteint ou hors de portée, le paquet dit pourquoi et contient quand même les journaux de l'application."
  - id: save-file
    title: "Ou l'enregistrer dans un fichier"
    body: |
      L'assistance a demandé le fichier lui-même, ou vous n'êtes pas connecté ? Touchez **Enregistrer dans un fichier** au lieu d'Envoyer. L'application crée le même paquet, un petit `.zip`, et ouvre le menu de partage d'Android. Envoyez-le là où l'assistance l'a demandé : un message privé sur Discord, un e-mail, ou un lien vers un stockage en ligne.
    screen: support-share-bug-report
    pins:
      - target: save-file
        text: "**Enregistrer dans un fichier**."
  - id: afterwards
    title: "Lire notre réponse"
    body: |
      Quand nous répondons, la réponse arrive par e-mail, et elle figure sur [Your feedback](https://my.commaview.com/feedback) sur my.commaview.com avec votre rapport. Répondez-nous là jusqu'à ce que nous le fermions ; vous pouvez le rouvrir pendant 30 jours ensuite. **Vos demandes**, dans **Assistance et diagnostics**, les liste aussi.
    screen: support-diagnostics
    pins:
      - target: your-requests
        text: "**Vos demandes** : les réponses et vos échanges avec CommaView."
check: "La fenêtre se ferme avec « Envoi en cours. Il se fait en arrière-plan et attend une connexion. », et le rapport apparaît sous **Vos demandes** une fois envoyé."
fixes:
  - q: "Le paquet n'a pas de journaux du comma"
    a: "L'application n'a pas pu joindre votre comma quand vous avez touché Envoyer, ou sa ligne sous **Pièces jointes** était désactivée. Vérifiez que l'accueil affiche votre comma **Connecté** avant d'ouvrir Envoyer à CommaView, et laissez la ligne de votre comma activée. Si l'application vous demande d'associer à nouveau votre comma, associez-le d'abord, puis renvoyez."
  - q: "Le bouton d'envoi indique **Se connecter pour envoyer**"
    a: "Vous êtes déconnecté. Touchez-le pour vous connecter avec votre compte bêta, ou utilisez **Enregistrer dans un fichier**."
  - q: "« Les pièces jointes dépassent les 25 MB qu'un rapport peut contenir. Désactivez-en une, ou enregistrez dans un fichier. »"
    a: "Désactivez une pièce jointe dont vous n'avez pas besoin, ou touchez **Enregistrer dans un fichier** et envoyez le fichier là où l'assistance le demande."
  - q: "Rien ne se passe quand je touche Enregistrer dans un fichier"
    a: "Android n'a aucune application sur cet appareil qui puisse recevoir un fichier. C'est courant sur les systèmes multimédias. [Envoyez-le](#step-send) plutôt à CommaView, ou enregistrez-le depuis un téléphone avec CommaView."
  - q: "« Impossible de préparer le rapport. Vérifiez le stockage local et réessayez. »"
    a: "L'application n'a pas pu écrire le paquet, généralement parce que l'appareil manque d'espace. Libérez de l'espace et réessayez."
related: [setup-troubleshooting, comma-not-found, releases]
---

## Ce que contient un paquet d'assistance

- **Ce téléphone : diagnostics.** Les journaux de diagnostic et compteurs de CommaView sur ce téléphone : erreurs de flux vidéo, d'affichage, de connexion et d'enregistrement, avec la version de l'application, le modèle du téléphone et sa version d'Android. Avec la navigation, aussi combien de recherches de lieux de chaque type ont réussi ou échoué, jamais ce que vous avez cherché.
- **Les journaux de votre comma.** Avec la ligne de votre comma activée : les journaux, compteurs et réglages du runtime CommaView, quels processus d'openpilot se sont arrêtés et pourquoi, et les lignes de manque de mémoire du noyau du comma.
- **Jamais dans un paquet.** Pas de vidéo, pas de position GPS, pas de VIN et pas de télémétrie brute des trajets : un enregistrement que vous envoyez part à côté du paquet, pas dedans. Un runtime de comma à jour retire les coordonnées GPS, les VIN, les noms de Wi‑Fi, les adresses IP publiques, les jetons et l'identifiant complet du dongle avant d'envoyer ses journaux.
- **Seulement quand vous envoyez.** Un paquet ne quitte votre téléphone que quand vous touchez Envoyer ou Enregistrer dans un fichier. Un fichier que vous enregistrez ne va que là où vous l'envoyez. Les adresses IP locales, les identifiants de session et les détails de version peuvent rester, alors ne partagez un paquet qu'avec des personnes de confiance.

## Où il va, et pour combien de temps

Un paquet envoyé va dans le stockage privé de CommaView, où seule l'équipe CommaView l'ouvre. Il est supprimé 180 jours après l'envoi, ou plus tôt, immédiatement, si vous nous le demandez ou supprimez votre compte ([Confidentialité](/privacy)). Pour le demander, écrivez à support@commaview.com.

Pour effacer ce que l'application garde sur ce téléphone, touchez **Effacer les données de diagnostic locales** dans **Assistance et diagnostics**. Cela ne supprime jamais vos enregistrements. Pour ne garder désormais que l'historique des erreurs d'enregistrement, désactivez **Conserver les diagnostics sur ce téléphone** sur la même page.

Vous ne savez pas où l'envoyer ? Demandez sur le [Discord de CommaView](https://discord.gg/UuMhz9K8ft).
