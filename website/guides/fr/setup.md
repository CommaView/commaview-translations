---
title: "Installer CommaView"
description: "Installez l'application CommaView sur Android, préparez votre comma 3X ou comma four, et laissez la configuration guidée installer le runtime et associer votre comma."
topic: start
order: 1
kind: walkthrough
lede: "CommaView a deux parties : l'application sur votre téléphone, tablette ou système multimédia Android, et son petit runtime sur votre comma. Installez l'application, puis la configuration guidée de l'application installe le runtime sur votre comma, le vérifie et l'associe. Cela prend quelques minutes, en position P avec openpilot désengagé."
parked: true
updated: 2026-11-27
needs:
  - title: "Un comma 3X ou comma four"
    text: "Avec openpilot ou un [fork pris en charge](/fr/guides/forks). Le comma 3 n'est pas pris en charge : sa version d'openpilot est figée en amont et dessine son écran autrement, donc CommaView ne peut pas afficher ses surimpressions. [Pourquoi le comma 3 n'est pas pris en charge](/#faq-comma-3)."
  - title: "Un appareil Android et votre invitation"
    text: "Android 8 ou ultérieur, et l'adresse e-mail à laquelle votre invitation est arrivée. CommaView est en bêta : vous vous connectez avec le compte invité."
  - title: "Le même réseau"
    text: "Votre téléphone et le comma sur un même réseau local : votre Wi‑Fi, le point d'accès de votre téléphone, celui du comma, ou tout autre réseau que les deux peuvent rejoindre. En voiture ? [Se connecter sans Wi‑Fi domestique](/fr/guides/connect-in-the-car)."
  - title: "Un compte GitHub"
    text: "Le comma accepte les clés SSH du nom d'utilisateur GitHub que vous lui donnez. CommaView crée la clé ; vous l'ajoutez à GitHub pendant la configuration."
howItWorks:
  - title: "Votre téléphone"
    text: "Crée une clé SSH, que vous ajoutez à GitHub."
    edge: "SSH"
  - title: "Votre comma"
    text: "Récupère la clé depuis votre nom d'utilisateur GitHub. CommaView installe son runtime à côté de votre fork."
    edge: "réseau local"
  - title: "CommaView"
    text: "Vérifie que le runtime répond et enregistre votre comma. Ensuite, il se reconnecte tout seul."
steps:
  - id: get-the-app
    title: "Obtenir l'application et se connecter"
    body: |
      Sur votre appareil Android, connectez-vous sur [my.commaview.com](https://my.commaview.com) avec l'adresse e-mail à laquelle votre invitation est arrivée. Sous **Get the app**, touchez **Download CommaView**. Sa somme de contrôle SHA-256 est affichée à côté si vous voulez vérifier le fichier.

      Ouvrez le téléchargement. Android vous demande d'autoriser les installations depuis votre navigateur : autorisez-les pour cette installation, puis désactivez-les à nouveau.

      Ouvrez CommaView. Il demande une fois si vous voulez **Aider à améliorer CommaView** : **Envoyer** ou **Ne pas envoyer**. Il vous demande ensuite de vous connecter : touchez **Se connecter** et utilisez l'adresse e-mail à laquelle votre invitation est arrivée. Ensuite, il fonctionne hors ligne tant que son pass d'accès est valide.
    tabs:
      - label: "Aider à améliorer CommaView"
        body: "Les rapports de plantage et le logiciel de conduite de votre comma, jamais de vidéo, de trajets, de lieux ni de noms. Vous pouvez le changer à tout moment dans Paramètres › **Confidentialité et partage**."
        screen: improve-commaview
        pins:
          - target: send
            text: "**Envoyer** les rapports de plantage pour aider à corriger les problèmes."
          - target: dont-send
            text: "**Ne pas envoyer** les garde sur le téléphone."
      - label: "Se connecter"
        body: "Pendant la bêta, CommaView a besoin de votre compte invité. **Se connecter** ouvre votre navigateur."
        screen: sign-in
        pins:
          - target: sign-in
            text: "**Se connecter** avec l'adresse e-mail à laquelle votre invitation est arrivée."
    note: "Vous installez sur un système multimédia ou un boîtier IA branché sur l'écran de votre voiture ? [Écrans de voiture](/fr/guides/car-screens) explique son réseau et son association avec votre comma."
  - id: connect
    title: "Commencer à configurer votre comma"
    body: |
      Lisez l'avertissement, cochez que vous comprenez qu'il s'agit d'un logiciel non officiel et que vous êtes responsable de son usage en toute sécurité, puis touchez **Je comprends — continuer**.

      Sur **Connectez votre comma**, touchez **Installer CommaView sur votre comma**.
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**Installer CommaView sur votre comma**, pour un comma qui n'exécute pas encore CommaView."
      - target: pair-runs
        text: "Il exécute déjà CommaView depuis un autre téléphone ? Utilisez plutôt **Associer un comma qui exécute CommaView** : [Ajouter un autre téléphone ou une tablette](/fr/guides/another-phone)."
  - id: setup-path
    title: "Choisir une méthode de configuration"
    tabs:
      - label: "Configuration guidée"
        body: "Choisissez **Configuration guidée** (marquée comme recommandée) et touchez **Continuer vers la configuration guidée**. CommaView crée une clé SSH, vous guide pour la connexion et vérifie votre comma. Les étapes suivantes la suivent."
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**Configuration guidée**, marquée comme recommandée."
          - target: continue
            text: "**Continuer vers la configuration guidée**."
      - label: "Configuration manuelle"
        body: "Seulement si SSH fonctionne déjà de votre ordinateur vers le comma avec l'utilisateur `comma`. Choisissez **Configuration manuelle**, puis **Continuer vers la configuration manuelle**, et lancez la commande depuis votre terminal. Quand l'installateur affiche un code d'association à usage unique, touchez **J'ai exécuté la commande**, saisissez l'IP de votre comma et le code, puis touchez **Ajouter un comma**. [Configuration manuelle depuis un terminal](#configuration-manuelle-depuis-un-terminal) détaille chaque étape."
        screen: setup-manual-instructions
        pins:
          - text: "**Toucher pour copier** copie la commande."
          - target: ran-command
            text: "**J'ai exécuté la commande**, une fois que l'installateur affiche son code d'association."
  - id: ssh-key
    title: "Ajouter la clé SSH à GitHub"
    body: |
      CommaView crée une clé SSH pour ce téléphone. Touchez **Copier la clé et ouvrir GitHub** : cela copie la clé publique et ouvre la page de nouvelle clé SSH de GitHub.

      Sur GitHub, collez la clé dans le champ **Key**, donnez-lui un titre quelconque (CommaView en propose un), puis enregistrez avec **Add SSH key**. Revenez dans CommaView et touchez **Continuer**.
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**Copier la clé et ouvrir GitHub**. Il indique « Clé SSH copiée. Ouverture de GitHub… »"
      - target: own-key
        text: "**Utiliser ma propre clé SSH** importe une paire de clés que vous avez déjà sur GitHub."
      - target: continue
        text: "**Continuer**, une fois la clé enregistrée sur GitHub."
    note: "Vous avez déjà une paire de clés sur GitHub ? **Utiliser ma propre clé SSH** l'importe à la place. La clé privée reste sur votre téléphone."
  - id: comma-ssh
    title: "Activer SSH sur votre comma"
    body: |
      Sur l'écran du comma, allez dans **Paramètres → Appareil → SSH** :

      1. Saisissez votre nom d'utilisateur GitHub.
      2. Attendez que le comma récupère vos clés GitHub.
      3. Activez SSH.

      Revenez ensuite dans CommaView et touchez **Continuer**.
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "**Continuer**, une fois SSH activé."
    note: "Le comma récupère vos clés une seule fois, quand vous saisissez le nom d'utilisateur. Vous l'avez saisi avant d'ajouter la clé ? Supprimez-le et saisissez-le à nouveau, pour que le comma récupère les clés de nouveau."
  - id: choose-comma
    title: "Choisir votre comma"
    body: |
      CommaView liste les comma de ce réseau Wi‑Fi qui exécutent déjà CommaView, donc un comma que vous configurez pour la première fois n'y figure généralement pas encore. Touchez **Mon comma n'est pas listé** et tapez son adresse IP. Touchez ensuite **Installer CommaView**.

      Vous trouverez l'IP sur le comma dans **Paramètres → Réseau** : sous le nom du réseau sur le bouton Wi‑Fi d'un comma four, ou sous **Avancé** sur un comma 3X.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Un comma qui exécute déjà CommaView. Celui enregistré sur ce téléphone est marqué **Enregistré sur ce téléphone**."
      - text: "**Mon comma n'est pas listé** : saisissez son adresse IP."
      - target: install
        text: "**Installer CommaView**."
  - id: safe-install
    title: "Lancer l'installation sûre"
    body: |
      La boîte de dialogue **Installation sûre** nomme le comma sur lequel elle installe. Lisez la note, puis touchez **Lancer l'installation sûre** une fois son court compte à rebours terminé.
    tabs:
      - label: "La voiture est en position P"
        body: "Si la voiture est en position P et qu'openpilot n'est pas engagé, CommaView installe tout de suite."
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "**Lancer l'installation sûre**, après son compte à rebours."
      - label: "La voiture roule"
        body: "Le comma met l'installation en attente et la lance une fois la voiture en position P avec openpilot désengagé, pour ne jamais interrompre un trajet. La configuration affiche **Installation en attente** : mettez la voiture en position P avec openpilot désengagé, attendez une minute ou deux, puis touchez **Terminer la configuration**."
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "**Terminer la configuration**, une fois la voiture en position P."
    note: "CommaView se connecte alors au comma en SSH, vérifie de quel comma il s'agit et installe le runtime avec lequel cette version de l'application a été testée. Il vérifie que l'installation répond et enregistre votre comma sur ce téléphone. Gardez le téléphone sur le même réseau jusqu'à la fin."
    warn: "Laissez la voiture allumée, en position P. Sans câble d'alimentation permanente, éteindre la voiture éteint aussi le comma, ce qui interrompt l'installation."
  - id: ready
    title: "CommaView est prêt"
    body: |
      Votre comma est installé, associé, et se reconnecte tout seul à son prochain démarrage.
    tabs:
      - label: "CommaView est prêt"
        body: "Touchez **OK**."
        screen: setup-done
        pins:
          - target: finish
            text: "**OK** vous amène à l'accueil."
      - label: "Redémarrer pour terminer"
        body: "Parfois, la configuration indique **Redémarrer pour terminer** : le comma diffuse vers votre téléphone après un redémarrage. Touchez **Redémarrer le comma et terminer** avec la voiture éteinte, ou en position P avec openpilot désengagé. openpilot s'arrête environ une minute pendant le redémarrage."
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**Redémarrer le comma et terminer**."
check: "L'accueil affiche votre voiture avec son comma **Connecté**, le runtime et l'adresse du comma. Touchez **Ouvrir Live View** : la route s'affiche en direct, avec la trajectoire et le véhicule de tête dessinés par-dessus. Désormais, l'application trouve votre comma toute seule quand votre téléphone et le comma sont sur le même réseau, même si son adresse change."
fixes:
  - q: "Connexion SSH impossible"
    a: "Vérifiez que SSH est activé dans **Paramètres → Appareil → SSH** sur le comma, que le nom d'utilisateur GitHub est bien le vôtre, et que la clé CommaView est sur ce compte GitHub. Si vous avez ajouté la clé après avoir saisi le nom d'utilisateur, supprimez le nom d'utilisateur et saisissez-le à nouveau pour que le comma récupère la clé."
  - q: "Mon comma n'est pas dans la liste"
    a: "C'est normal la première fois : la liste affiche les comma qui exécutent déjà CommaView. Touchez **Mon comma n'est pas listé** et saisissez son adresse IP (**Paramètres → Réseau** sur le comma : sous le nom du réseau sur le bouton Wi‑Fi d'un comma four, ou sous **Avancé** sur un comma 3X). Vérifiez que le téléphone est sur le même réseau que le comma et pas sur un VPN."
  - q: "La configuration indique « Installation en attente »"
    a: "Le comma a vu que la voiture roulait, donc il attend. Mettez la voiture en position P avec openpilot désengagé, attendez une minute, puis touchez **Terminer la configuration**. Laissez la voiture allumée : sans câble d'alimentation permanente, l'éteindre éteint aussi le comma."
  - q: "La configuration indique que mon comma n'est pas pris en charge"
    a: "Sur un comma 3, la configuration s'arrête et propose **Installer CommaView sur un comma 3X ou un comma four**. Sur un fork dont CommaView ne peut pas compléter l'écran avec sa vue, la configuration le dit et ne change rien. [Vérifiez que votre comma et votre fork sont pris en charge](/fr/guides/forks)."
  - q: "Le code d'association n'a pas marché"
    a: "Les codes d'association sont à usage unique et expirent vite. Relancez l'installateur pour obtenir un nouveau code, et vérifiez que vous l'avez tapé tel qu'il s'affiche (le tiret est facultatif)."
  - q: "Connecté, mais pas de vidéo"
    a: "La configuration et l'association sont faites ; il s'agit du flux vidéo. Vérifiez que le comma est allumé et prêt à rouler, gardez le téléphone sur le même réseau, et rouvrez Live View. S'il indique **Impossible de joindre ce comma**, voyez [CommaView ne trouve pas votre comma](/fr/guides/comma-not-found)."
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## Configuration manuelle depuis un terminal

Seulement si SSH fonctionne déjà de votre ordinateur vers le comma avec l'utilisateur `comma`.

1. Dans CommaView, choisissez **Configuration manuelle**, puis **Continuer vers la configuration manuelle**. L'application affiche la commande de son runtime sur **Installer depuis votre terminal**, prête à copier (**Toucher pour copier**). Elle ressemble à celle-ci, qui installe le runtime de la version actuelle :

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. Lancez-la depuis un ordinateur sur le même réseau Wi‑Fi que votre comma, en remplaçant `COMMA_IP` par l'adresse IP du comma (**Paramètres → Réseau** sur le comma : sous le nom du réseau sur le bouton Wi‑Fi d'un comma four, ou sous **Avancé** sur un comma 3X). Votre ordinateur télécharge l'installateur, et SSH l'exécute sur le comma avec l'utilisateur `comma`.
3. Quand l'installateur a terminé, CommaView démarre sur le comma et affiche un code d'association à usage unique.
4. De retour dans CommaView, touchez **J'ai exécuté la commande**. Sur **Ajoutez votre comma**, sélectionnez votre comma ou saisissez son IP, tapez le code d'association, puis touchez **Ajouter un comma**. L'application vérifie le runtime et enregistre le comma.

## Avant votre premier trajet

Essayez en position P avant de rouler.

- L'accueil affiche votre comma comme **Connecté**.
- Live View s'affiche et la trajectoire bouge avec la voiture.
- Si l'application affiche un avertissement ou demande une réparation, réglez-le avant de rouler.
- Configurez tout pour que rien ne demande votre attention pendant la conduite.

Toujours bloqué ? Demandez sur le [Discord de CommaView](https://discord.gg/UuMhz9K8ft), ou envoyez un commentaire depuis l'application. Si l'assistance demande des journaux, [envoyez un paquet d'assistance](/fr/guides/support-bundle).
