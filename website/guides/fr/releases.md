---
title: "Comment se font les versions de CommaView"
description: "Comment l'application CommaView et le runtime de votre comma sont publiés : des alphas, puis une bêta, des téléchargements signés, des runtimes assortis et des mises à jour qui attendent P."
topic: account
order: 2
kind: reference
lede: "CommaView a deux parties qui se mettent à jour ensemble : l'application Android et le petit runtime sur votre comma. Voici comment une version vous parvient, et comment les mises à jour restent sûres."
updated: 2026-11-27
steps:
  - id: version
    title: "Voir quelle version vous avez"
    body: |
      Paramètres › **À propos** affiche la version de l'application, et si elle est **À jour** ou si une mise à jour est disponible, avec sa version. CommaView vérifie votre compte pour une nouvelle version et vous prévient quand elle est prête.
    screen: support-about
    pins:
      - target: version
        text: "La version de l'application."
      - target: up-to-date
        text: "**À jour**, ou la version prête pour vous."
  - id: app-update
    title: "Mettre à jour l'application depuis l'application"
    body: |
      Quand une version est prête, **Mettre à jour** apparaît en haut de l'accueil et dans **À propos**. **Mettre à jour CommaView** indique la version et son canal : **Bêta** pour toutes les personnes invitées, ou **Alpha**, « Une version précoce pour les testeurs. Elle peut avoir plus de problèmes que la bêta. » Touchez **Télécharger** : CommaView la télécharge en arrière-plan, la vérifie, puis Android vous demande de confirmer l'installation.
    screen: app-update-offer
    pins:
      - target: channel
        text: "Le canal : **Bêta** ou **Alpha**."
      - target: download
        text: "**Télécharger**. **Plus tard** la laisse pour plus tard."
  - id: runtime
    title: "Puis mettre à jour le runtime de votre comma"
    body: |
      Chaque version de l'application nomme le runtime avec lequel elle a été testée. Une fois l'application à jour, l'accueil propose ce runtime avec **Mise à jour du runtime prête**. Les mises à jour du runtime partent toujours de l'application, jamais d'elles-mêmes. [Mettre à jour le runtime de votre comma](/fr/guides/update-runtime) détaille chaque étape.
    screen: home-runtime-update
    pins:
      - target: update-card
        text: "**Mise à jour du runtime** : le runtime installé et le runtime disponible."
related: [update-runtime, uninstall, setup]
---

## D'abord l'alpha, puis la bêta

- Chaque version sort d'abord sous forme d'une série d'alphas pour quelques testeurs.
- Quand une alpha tient la route, elle devient la bêta de cette version et va à toutes les personnes invitées.
- Votre compte sur [my.commaview.com](https://my.commaview.com) propose toujours la version qui vous convient.

## Signée et assortie

- Chaque téléchargement de l'application est une version signée, jamais une version de débogage, avec sa somme de contrôle SHA-256 affichée à côté sur my.commaview.com. L'application vérifie la taille et la somme de contrôle d'une mise à jour téléchargée avant de proposer de l'installer : « Le téléchargement ne correspondait pas à sa somme de contrôle, il n'a donc pas été installé. »
- Chaque version de l'application nomme le runtime avec lequel elle a été testée, et l'application installe exactement celui-là sur votre comma.
- Une application plus ancienne ne se voit jamais proposer un runtime avec lequel elle n'a pas été testée. Si le runtime d'un comma est plus récent que celui que l'application installe, elle le dit : mettez à jour CommaView, puis réessayez.

## Mettre à jour votre comma en toute sécurité

- Les mises à jour du runtime partent de l'accueil ou de Paramètres de l'appareil, jamais d'elles-mêmes.
- Les mises à jour n'interrompent jamais un trajet. Si la voiture roule, la mise à jour sûre met la mise à jour en attente et le comma l'installe dès que la voiture est en position P avec openpilot désengagé. Inutile d'éteindre la voiture.
- Après une mise à jour du runtime, le comma doit redémarrer avant que CommaView diffuse à nouveau. L'application vous le demande.
- Vous pouvez retirer le runtime depuis Paramètres de l'appareil à tout moment : [Retirer CommaView](/fr/guides/uninstall).

## Où vous en entendez parler

- L'application vous prévient quand une nouvelle version est prête.
- [Nouveautés](/whats-new) liste chaque changement.
- Nous vous écrivons pour les changements importants, et vous pouvez envoyer un commentaire depuis l'application à tout moment (Paramètres › **Assistance et diagnostics**).
