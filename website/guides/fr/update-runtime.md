---
title: "Mettre à jour le runtime de votre comma"
description: "Mettez à jour le runtime CommaView de votre comma depuis l'accueil ou Paramètres de l'appareil. La mise à jour sûre attend la position P, pour ne jamais interrompre un trajet."
topic: account
order: 1
kind: walkthrough
lede: "Le runtime CommaView de votre comma se met à jour depuis l'application, jamais tout seul. Mettez d'abord à jour CommaView, puis le runtime quand l'application le propose. Si la voiture roule, la **mise à jour sûre** met la mise à jour en attente sur le comma et l'installe dès que la voiture est en position P avec openpilot désengagé."
updated: 2026-11-27
needs:
  - title: "Le téléphone et le comma ensemble"
    text: "Sur le même Wi‑Fi que le comma, ou sur son point d'accès."
  - title: "La voiture allumée"
    text: "Laissez la voiture allumée, en position P. Sans câble d'alimentation permanente, l'éteindre éteint aussi le comma."
howItWorks:
  - title: "CommaView"
    text: "Chaque version de l'application nomme le runtime avec lequel elle a été testée, et propose exactement celui-là."
  - title: "Votre comma"
    text: "Le télécharge, le vérifie et l'installe, une fois la voiture en position P."
    edge: "redémarrage"
  - title: "Live View"
    text: "Reprend une fois le comma redémarré."
steps:
  - id: app-first
    title: "Mettre d'abord à jour CommaView"
    body: |
      L'application installe le runtime avec lequel elle a été testée : mettez donc à jour l'application avant le runtime. Quand une mise à jour est prête, **Mettre à jour** apparaît en haut de l'accueil et dans Paramètres › **À propos**. Touchez-le : **Mettre à jour CommaView** indique la version, son canal et sa taille. Touchez **Télécharger** ; CommaView la télécharge en arrière-plan et la vérifie, puis Android vous demande de confirmer l'installation.
    screen: app-update-offer
    pins:
      - target: download
        text: "**Télécharger**."
      - target: channel
        text: "Le canal de la version : **Bêta**, ou **Alpha** pour les testeurs."
    note: "Mettez à jour CommaView sur chaque téléphone, tablette et écran de voiture qui regarde ce comma avant de mettre à jour son runtime."
  - id: open
    title: "Ouvrir la mise à jour du runtime"
    tabs:
      - label: "Depuis l'accueil"
        body: "L'accueil affiche **Mise à jour du runtime prête** quand un nouveau runtime est prêt pour ce comma. Touchez **Consulter la mise à jour** : la carte **Mise à jour du runtime** affiche les versions **Installé** et **Disponible** et indique si la voiture est prête. Touchez **Mettre à jour le runtime**, ou **Mettre en attente** pendant que la voiture roule."
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**Mise à jour du runtime** : Installé, Disponible et l'état de la voiture."
          - target: update-runtime
            text: "**Mettre à jour le runtime** (**Mettre en attente** pendant que la voiture roule)."
      - label: "Depuis Paramètres de l'appareil"
        body: "Ouvrez les **Paramètres de l'appareil** du comma, puis **Runtime** (il affiche **Mettre à jour** quand une mise à jour est prête). La page affiche le runtime installé et le runtime disponible. Touchez **Mettre à jour**."
        screen: device-runtime
        pins:
          - target: update-now
            text: "**Mettre à jour**."
  - id: install
    title: "L'installer, ou laisser la mise à jour sûre la mettre en attente"
    body: |
      Depuis Paramètres de l'appareil, la boîte de dialogue **Mise à jour du runtime** indique si la voiture est prête.
    tabs:
      - label: "La voiture est en position P"
        body: "Elle indique « La voiture est en position P et openpilot n'est pas engagé. La mise à jour du runtime peut démarrer sans risque. » Touchez **Installer la mise à jour**."
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**Installer la mise à jour**."
          - target: close
            text: "**Fermer** la laisse pour plus tard."
      - label: "La voiture roule"
        body: "Elle indique « La voiture roule. La mise à jour sûre met la mise à jour en attente sur le comma et l'installe dès que la voiture est en position P avec openpilot désengagé. » Touchez **Mise à jour sûre…**, lisez la note, puis touchez **Lancer la mise à jour sûre** une fois son court compte à rebours terminé. Il se passe la même chose quand CommaView n'a pas pu confirmer si la voiture roule."
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**Mise à jour sûre…**, puis **Lancer la mise à jour sûre**."
    note: "CommaView n'arrête jamais openpilot ni votre fork : une mise à jour en attente attend la position P, et aucun trajet n'est interrompu."
  - id: progress
    title: "La laisser se faire"
    body: |
      Le comma télécharge la version, vérifie qu'elle est complète et intacte, l'installe et redémarre CommaView, et l'application affiche chaque étape. Vous pouvez changer d'application ou verrouiller votre téléphone : la mise à jour continue, et sa notification montre où elle en est.

      Tant que le comma n'a pas commencé l'installation, **Annuler la mise à jour** l'arrête, et rien ne change sur votre comma.
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "Les étapes : Téléchargement, Vérification, Installation, Redémarrage de CommaView, Reconnexion."
  - id: queued
    title: "Une mise à jour en attente attend la position P"
    body: |
      Une mise à jour en attente s'affiche sur la carte **Mise à jour du runtime** de l'accueil comme **En attente de la position P**. Elle s'installe une fois que la voiture est en position P depuis quelques secondes avec openpilot désengagé. Laissez la voiture allumée pendant l'installation.
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "**En attente de la position P**, avec son étape."
  - id: reboot
    title: "Redémarrer le comma pour terminer"
    body: |
      Après une mise à jour du runtime, le comma doit redémarrer avant que CommaView diffuse à nouveau depuis lui : openpilot ne charge le nouveau code d'écran de CommaView qu'au redémarrage du comma. L'application ne le redémarre jamais d'elle-même.

      Touchez **Redémarrer le comma** sur la carte de l'accueil, ou **Redémarrer le comma** dans la boîte de dialogue, avec la voiture éteinte ou en position P. openpilot s'arrête environ une minute. Vous pouvez aussi le redémarrer depuis le comma lui-même : **Paramètres → Appareil → Redémarrer**.
check: "La dernière étape de la mise à jour indique **Mis à jour**, et Paramètres de l'appareil affiche le nouveau runtime **À jour**. Après le redémarrage, Live View s'affiche avec ses surimpressions."
fixes:
  - q: "« Le runtime de ce comma est plus récent que celui de cette application »"
    a: "Mettez à jour CommaView, puis réessayez. Rien n'a été changé sur le comma."
  - q: "« Mise à jour nécessaire »"
    a: "Cette application et le runtime de ce comma ne sont pas assez récents l'un pour l'autre. Mettez d'abord à jour CommaView, puis le runtime."
  - q: "« Le comma n'a pas installé … : il exécute …, que CommaView ne liste pas »"
    a: "Le comma n'a rien changé et a gardé le runtime qu'il avait. Pour ajouter CommaView à ce fork au mieux, relancez la configuration de ce comma : elle vérifie le fork et vous demande d'abord votre accord."
  - q: "« La voiture a redémarré à chaque lancement, donc le comma a cessé d'essayer »"
    a: "Mettez la voiture en position P avec openpilot désengagé, puis réessayez."
  - q: "« Mise à jour du runtime annulée »"
    a: "Le comma a remis le runtime qu'il avait. Réessayez, et si cela échoue encore, [envoyez un paquet d'assistance](/fr/guides/support-bundle)."
  - q: "« CommaView met déjà à jour ou désinstalle un runtime »"
    a: "Une seule opération sur le runtime à la fois. Réessayez quand elle sera terminée."
  - q: "Pas de surimpressions ni de télémétrie après la mise à jour"
    a: "Le comma n'a pas encore redémarré. Redémarrez-le avec la voiture éteinte ou en position P."
related: [releases, uninstall, another-phone]
---

## Pourquoi les mises à jour attendent la position P

L'installation du runtime arrête CommaView sur le comma pendant le remplacement de ses fichiers et redémarre ses services : le comma ne le fait donc qu'avec la voiture en position P et openpilot désengagé. La mise à jour sûre ne demande pas à openpilot de passer à l'arrêt : elle met le travail en attente sur le comma, qui l'exécute dès que la voiture est en position P. Inutile d'éteindre la voiture ; laissez-la allumée, en position P.

Avant que quoi que ce soit change sur le comma, il télécharge la version et vérifie qu'elle est complète et intacte. Si une installation échoue ensuite, le comma remet le runtime qu'il avait.
