---
title: "Afficher Live View dans le navigateur de votre voiture"
description: "Browser View affiche le Live View de CommaView dans le navigateur web de votre voiture, Tesla comprise, servi par votre téléphone via son point d'accès. Rien à installer dans la voiture."
topic: screens
order: 2
kind: walkthrough
lede: "**Browser View** affiche ce que montre Live View dans le navigateur web de votre voiture. Votre téléphone le sert à la voiture par son point d'accès ou son Wi‑Fi, donc rien n'est à installer dans la voiture. Il a été conçu pour des voitures comme les Tesla, qui ont un navigateur mais ni CarPlay ni Android Auto, et il fonctionne dans tout navigateur qui peut joindre votre téléphone."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View fonctionne"
    text: "CommaView sur un téléphone Android, associé à votre comma. Pas encore ? [Installer CommaView](/fr/guides/setup)."
  - title: "Un navigateur dans la voiture"
    text: "Une Tesla, une autre voiture avec un navigateur web, ou une tablette ou un ordinateur portable dans la voiture."
  - title: "Un seul réseau"
    text: "La voiture et votre comma sur le point d'accès de votre téléphone, ou sur tout réseau partagé par les trois."
howItWorks:
  - title: "Votre comma"
    text: "Envoie Live View à votre téléphone, comme d'habitude."
  - title: "Votre téléphone"
    text: "Sert l'image sous forme de page web, protégée par un code à huit chiffres."
    edge: "point d'accès"
  - title: "Le navigateur de la voiture"
    text: "Ouvre la page : 20 images par seconde, 720p ou 1080p, jusqu'à quatre navigateurs."
steps:
  - id: hotspot
    title: "Connecter la voiture au point d'accès de votre téléphone"
    body: |
      Activez le point d'accès de votre téléphone, puis connectez-y la voiture depuis ses paramètres Wi‑Fi. Vérifiez que la voiture a rejoint votre téléphone, et pas un Wi‑Fi qu'elle connaît déjà. Connectez aussi votre comma au point d'accès s'il n'y est pas déjà : votre téléphone a toujours besoin de votre comma, comme d'habitude.
    note: "**Dans une Tesla**, désactivez d'abord le Wi‑Fi de votre téléphone, pour que le point d'accès partage les données mobiles."
  - id: start
    title: "Démarrer Browser View depuis les Détails de Live View"
    body: |
      Ouvrez **Live View** sur le téléphone, puis **Détails**. Vers la fin, la carte **Browser View** dit ce qu'elle fait et ce qu'elle communique à CommaView. Touchez **Démarrer**.
    screen: live-view-browser-view
    clip: browser-view-start
    pins:
      - target: browser-view-card
        text: "La carte **Browser View**, vers la fin des **Détails**."
      - target: start-button
        text: "**Démarrer**. La première fois, laissez quelques secondes au téléphone pour obtenir son certificat."
      - target: privacy-policy
        text: "Ce que Browser View communique à CommaView pendant qu'il tourne, et la **Politique de confidentialité**."
  - id: vpn
    title: "Dans une Tesla, activer l'adresse VPN"
    tabs:
      - label: "Tesla"
        body: |
          Le navigateur d'une Tesla n'ouvre pas les adresses que distribue un point d'accès. Sur la carte, touchez **Activer l'adresse VPN**, et acceptez quand Android demande d'autoriser CommaView à configurer un VPN. Votre téléphone reçoit une adresse que la Tesla ouvrira, `169.254.99.1`. Elle ne transporte aucun trafic, et toute autre application VPN est désactivée tant qu'elle est active.
        screen: live-view-browser-view-vpn
        pins:
          - target: short-link
            text: "Le lien court, valable aussi pour la Tesla : **Dans le navigateur de la voiture, Tesla compris, ouvrez**."
          - target: vpn-address
            text: "Les adresses du téléphone sur l'adresse VPN, `169.254.99.1`."
        note: "La question d'Android sur le VPN n'est pas illustrée : elle vient d'Android, et diffère d'un téléphone à l'autre."
      - label: "Autre voiture"
        body: |
          Rien à faire ici : les navigateurs des autres voitures ouvrent l'adresse du point d'accès. Passez à l'étape suivante.
  - id: open
    title: "Taper le lien court dans le navigateur de la voiture"
    body: |
      La carte affiche un lien court avec votre code à huit chiffres, par exemple `commaview.app/48291374`. Tapez-le dans le navigateur de la voiture et touchez **Ouvrir**. Avec la voiture en ligne et CommaView connecté, la page trouve votre téléphone et ouvre Live View par une connexion sécurisée : un cadenas, aucun avertissement, et l'image la plus fluide.
    screen: live-view-browser-view-on
    pins:
      - target: short-link
        text: "Le lien court à taper dans la voiture, avec votre code."
      - target: show-addresses
        text: "**Pas d'Internet dans la voiture ? Afficher les adresses** : les adresses propres du téléphone."
      - target: quality
        text: "**Image de Browser View** : 720p ou 1080p."
      - target: stop-button
        text: "**Arrêter** met fin à Browser View."
    warn: "**Pas d'Internet dans la voiture ?** Le lien court en a besoin. Utilisez plutôt l'adresse propre du téléphone : voyez [Pas d'Internet dans la voiture](#pas-dinternet-dans-la-voiture)."
  - id: bookmark
    title: "Ajouter la page aux favoris"
    body: |
      L'adresse de la page ne change pas : la prochaine fois, avec la voiture en ligne, ouvrez le favori au lieu de taper le lien court.
check: "La carte sur le téléphone indique qui regarde et ce que dessine le navigateur de la voiture, par exemple **1 navigateur regarde** et `Tesla 2025.20.6 · H.264 over HTTPS via the VPN name · 20 fps`."
fixes:
  - q: "« En attente du navigateur de la voiture » et rien ne s'ouvre"
    a: "Vérifiez que la voiture a rejoint le point d'accès de votre téléphone, et pas un autre Wi‑Fi. Dans une Tesla, activez l'adresse VPN ([étape 3](#step-vpn))."
  - q: "« Activez le point d'accès de ce téléphone »"
    a: "Le téléphone n'est ni sur un Wi‑Fi ni sur un point d'accès que la voiture pourrait partager. L'adresse apparaît dans les 5 secondes après l'activation de l'un ou l'autre."
  - q: "Le lien court indique que l'adresse VPN est désactivée"
    a: "Activez-la sur la carte, puis rechargez la page."
  - q: "Un avertissement qu'on ne peut pas passer"
    a: "Utilisez le lien court avec la voiture en ligne, ou l'image simple ([Pas d'Internet dans la voiture](#pas-dinternet-dans-la-voiture))."
  - q: "L'image s'arrête en marche avant"
    a: "C'est le constructeur qui décide si le navigateur d'une voiture continue d'afficher pendant la conduite. La ligne de rapport de la carte dit ce que la voiture affiche (« 0 fps · Masqué » est une image que la voiture a arrêtée). Indiquez-nous votre voiture et sa version logicielle : activez **Conserver les diagnostics sur ce téléphone** avant de rouler, puis envoyez **Signaler un problème ou proposer une idée** depuis Paramètres ensuite."
related: [car-screens, ai-box, go-live]
blogPost: commaview-0-0-166-languages-browser-view
---

## Pas d'Internet dans la voiture

Le lien court a besoin que la voiture soit en ligne pour sa page, par les données mobiles du point d'accès ou la connexion propre de la voiture. Sans cela, ouvrez directement l'adresse du téléphone. Sur la carte, touchez **Pas d'Internet dans la voiture ? Afficher les adresses** :

- **Meilleure image**, une adresse HTTPS comme `https://192.168.43.1:8443/48291374`. Le navigateur avertit d'abord, car le téléphone signe lui-même cette adresse : acceptez l'avertissement pour continuer. Le navigateur d'une Tesla ne vous laisse pas passer.
- **Image simple**, la même adresse en HTTP, comme `192.168.43.1:8090/48291374`. Aucun avertissement dans aucun navigateur, Tesla compris, mais une image de moindre qualité, moins fluide.

Avec l'adresse VPN activée, la carte affiche plutôt ses adresses, `https://169.254.99.1:8443/<code>` et `169.254.99.1:8090/<code>`. Dans une Tesla sans Internet, utilisez l'adresse simple.

L'adresse du point d'accès de votre téléphone peut différer de l'exemple ; la carte affiche toujours la bonne, avec un bouton Copier à côté de chacune.

## Choix sur la carte

- **Image de Browser View : 720p ou 1080p.** Le 1080p est plus net, mais sollicite davantage le téléphone et le point d'accès. 720p tant que vous ne choisissez rien.
- **Démarrer avec Live View.** Browser View démarre à chaque ouverture de Live View, avec l'adresse VPN si elle est activée. Arrêtez-le et il reste arrêté jusqu'à la prochaine ouverture de Live View.
- **Nouveau code.** Crée un nouveau code à huit chiffres, pour qu'une adresse vue par quelqu'un d'autre cesse de fonctionner. Ouvrez la nouvelle adresse dans la voiture.
- **Commandes dans la voiture.** Enregistrer, Garder le moment et les autres commandes de Live View se placent sous l'image ou à côté, du côté du conducteur, jamais par-dessus. **Commandes dans la voiture** sur la carte les désactive.
- **La caméra conducteur** s'affiche aussi dans la voiture tant que **Caméra cond.** est activé dans Live View.

## Pendant qu'il tourne

- **Browser View continue avec le téléphone verrouillé** ou dans une autre application. Sa notification indique « Affichage de Live View dans Browser View », et son **Arrêter** y met fin.
- **Quitter Live View y met fin**, comme au direct et aux copies en direct.
- **Le direct à côté de Browser View** partage son image. Lancé pendant que Browser View tourne seul, un direct n'a pas de son : arrêtez d'abord Browser View pour avoir le son.

## Confidentialité et sécurité

- L'image ne va qu'aux navigateurs sur le point d'accès ou le Wi‑Fi de votre téléphone qui ont le code. Jamais par les données mobiles, et jamais par les serveurs de CommaView.
- Dix codes erronés en une minute depuis un appareil le bloquent pendant une minute, et un appareil qui regarde déjà continue.
- Pendant que Browser View tourne, votre téléphone envoie au service de compte de CommaView son code, ses ports, si l'adresse VPN est activée et l'adresse privée du point d'accès ou du Wi‑Fi, pour que le lien court trouve votre téléphone. Toute personne qui a le code peut les voir, ainsi que le nom `commaview.app` de votre téléphone, pendant que Browser View tourne et jusqu'à 2 heures après un arrêt inattendu ; aucun ne permet d'ouvrir quoi que ce soit sans le point d'accès ou le Wi‑Fi de votre téléphone. Ils sont supprimés 30 jours après la dernière utilisation de Browser View. Le nom `commaview.app` de votre téléphone et la date de son dernier certificat restent tant que votre compte existe. Les certificats sont publics, donc ce nom reste dans les journaux Certificate Transparency ; il ne dit rien de vous, de votre voiture ni de votre comma. [La politique de confidentialité](/privacy) donne les détails.
- L'adresse VPN est votre choix, ne s'active jamais toute seule, et ne transporte aucun trafic.

## Questions

**Ai-je besoin d'un boîtier IA ou d'un nouveau système multimédia ?** Non. Browser View utilise le navigateur que votre voiture a déjà. Si votre voiture a plutôt CarPlay ou Android Auto, un [boîtier IA Android](/blog/android-ai-box-commaview) peut faire tourner CommaView sur l'écran de la voiture lui-même.

**Est-ce que cela consomme mes données mobiles ?** L'image non : elle va du téléphone à la voiture par le point d'accès. La page du lien court et l'usage du point d'accès par la voiture elle-même, oui.

**Le point d'accès de mon comma peut-il remplacer celui de mon téléphone ?** Pour la plupart des navigateurs, oui : mettez le téléphone et la voiture sur le point d'accès du comma et ouvrez l'adresse affichée sur la carte. Une Tesla a besoin de l'adresse VPN, qui ne marche que pour une voiture sur le point d'accès du téléphone lui-même.

## Sécurité

Configurez Browser View garé, puis n'y touchez plus. Ne manipulez pas CommaView en conduisant : gardez les yeux sur la route et les mains sur le volant, comme openpilot le demande. Les alertes de votre comma et les instruments de votre voiture passent en premier. CommaView ne montre que ce que voit le comma.
