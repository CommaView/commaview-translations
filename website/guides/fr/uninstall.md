---
title: "Retirer CommaView de votre comma"
description: "Désinstallez le runtime CommaView de votre comma dans Paramètres de l'appareil, remettez les fichiers de votre fork dans leur état d'origine et oubliez le comma sur votre téléphone."
topic: account
order: 3
kind: walkthrough
lede: "**Désinstaller le runtime** retire CommaView de votre comma : il annule les hooks de CommaView, arrête son runtime et supprime `/data/commaview`. Votre fork continue de conduire comme toujours. Utilisez-le pour retirer CommaView, ou pour relancer la configuration guidée depuis le début."
parked: true
updated: 2026-11-27
needs:
  - title: "Le téléphone et le comma ensemble"
    text: "Sur le même Wi‑Fi que le comma, ou sur son point d'accès. Paramètres de l'appareil a besoin du comma pour gérer les mises à jour et la suppression."
  - title: "La voiture allumée, en position P"
    text: "Si la voiture roule, le comma met la désinstallation en attente jusqu'à ce qu'elle soit en position P avec openpilot désengagé."
steps:
  - id: device-settings
    title: "Ouvrir les Paramètres de l'appareil du comma"
    body: |
      Depuis l'accueil, ouvrez les **Paramètres de l'appareil** de votre comma, puis **Runtime** (« Mettre à jour ou supprimer »).
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**Runtime** : mettre à jour ou supprimer CommaView."
  - id: uninstall
    title: "Toucher Désinstaller le runtime"
    body: |
      Sous la mise à jour du runtime, **Désinstaller le runtime** retire CommaView de ce comma. La configuration guidée peut ensuite repartir du début.
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**Désinstaller le runtime**."
  - id: confirm
    title: "Confirmer"
    body: |
      **CommaView sera supprimé** : CommaView annule ses hooks de runtime, s'arrête et supprime `/data/commaview` de ce comma. Le comma reste enregistré sur votre téléphone. Touchez **Désinstaller le runtime** une fois son court compte à rebours terminé.
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**CommaView sera supprimé**, et ce que cela fait."
      - text: "**Désinstaller le runtime**, après son compte à rebours. **Annuler** garde CommaView."
    note: "Si la voiture roule, le comma met la désinstallation en attente : CommaView est supprimé dès que la voiture est en position P avec openpilot désengagé, et fonctionne jusque-là."
  - id: forget
    title: "Oublier le comma sur votre téléphone, si vous le souhaitez"
    body: |
      Paramètres de l'appareil indique maintenant que le runtime a été supprimé. Pour retirer aussi le comma de votre téléphone, touchez **Oublier ce comma** à la fin de Paramètres de l'appareil : CommaView n'affiche plus ce comma et supprime sa clé d'association. Pour supprimer l'application elle-même, désinstallez CommaView depuis les paramètres d'Android comme n'importe quelle application.
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**Oublier ce comma**."
check: "La boîte de dialogue indique **Runtime désinstallé**, et Paramètres de l'appareil affiche le runtime **Supprimé** : « CommaView a été désinstallé de votre comma. Lancez la configuration guidée pour le réinstaller. »"
fixes:
  - q: "« Échec de la désinstallation : erreur d'autorisation SSH »"
    a: "Le comma n'a pas laissé entrer ce téléphone en SSH. Vérifiez que SSH est activé dans **Paramètres → Appareil → SSH** sur le comma et que son nom d'utilisateur GitHub a la clé de ce téléphone, puis touchez **Désinstaller à nouveau**."
  - q: "« Le comma n'a pas pu désinstaller CommaView et l'a laissé tel quel »"
    a: "Rien n'a été supprimé. Réessayez avec la voiture en position P."
  - q: "« Désinstallation en attente de la position P »"
    a: "La voiture roule. Mettez-la en position P avec openpilot désengagé, laissez-la allumée, et le comma retire CommaView tout seul."
  - q: "Le bouton de désinstallation est grisé"
    a: "CommaView est déjà en train de mettre à jour ou de désinstaller un runtime. Réessayez quand ce sera terminé."
related: [setup, update-runtime, forks]
---

## Ce que la désinstallation remet en place

- **Sur un fork listé**, elle annule le petit hook que CommaView ajoute à l'interface à l'écran du fork.
- **Sur un fork que CommaView ne liste pas** (au mieux), elle remet les fichiers du fork dans leur état d'origine.
- **Vidéo seule** n'a rien changé aux fichiers du fork, et la désinstallation retire le runtime.

Sur SunnyPilot-TeslaHW1, désinstallez le runtime avant `op fork update`, qui ne peut pas changer de fork tant que le hook de CommaView est installé. [Vérifiez que votre comma et votre fork sont pris en charge](/fr/guides/forks) en dit plus.

## Réinstaller CommaView

Après une désinstallation, le comma reste enregistré sur votre téléphone. Lancez la [configuration guidée](/fr/guides/setup) pour le réinstaller comme une nouvelle installation.
