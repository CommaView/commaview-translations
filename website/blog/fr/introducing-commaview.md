---
title: "Voici CommaView : la diffusion locale de la caméra des appareils comma"
description: "CommaView est une application Android pour diffuser en local la caméra d'un comma, avec des surimpressions façon MICI, l'installation du runtime, des enregistrements et relectures."
date: 2026-05-02
slug: introducing-commaview
tags:
  - CommaView
  - comma device camera streaming
  - Android app
  - openpilot tools
heroLabel: "Notes produit"
draft: false
---

CommaView existe parce qu'accéder en local à la caméra d'un comma devrait ressembler à un vrai produit, pas à une pile de scripts scotchés à une session SSH.

Le but est simple : associer un appareil Android à votre comma, diffuser la caméra route en local, afficher des surimpressions utiles pendant la conduite, et rendre l'installation ennuyeuse, dans le meilleur sens du terme.

## Pourquoi le local d'abord ?

CommaView ne cherche pas à être un tableau de bord dans le cloud. L'application parle à votre comma par votre connexion locale et garde l'essentiel du travail au plus près du matériel.

C'est important, parce qu'une application qui diffuse la caméra du comma en local peut rester rapide, compréhensible et respectueuse de la vie privée. Personne ne devrait avoir besoin d'un compte juste pour voir ce que voit son propre appareil.

## Ce que fait CommaView

L'alpha actuelle se concentre sur ce qui rend les essais de tous les jours moins pénibles :

- la diffusion locale de la caméra route vers Android
- des surimpressions façon MICI pour la trajectoire, les voies, l'état et la surveillance du conducteur
- une configuration guidée du runtime pour le service `commaviewd` côté comma
- l'enregistrement des trajets et l'export des relectures
- des versions d'application et de runtime assorties, pour que les testeurs installent des builds compatibles

## Pourquoi Android d'abord ?

CommaView n'existe que sur Android, parce qu'Android est la cible pratique pour cet usage : téléphones, tablettes, installation hors store, réseau local et matériel adapté à la voiture s'y accordent mieux.

Ce choix permet à l'application de rester affûtée au lieu de s'édulcorer pour toutes les plateformes possibles.

## La suite

Un accès anticipé pour les testeurs aidera à fiabiliser l'installation, vérifier la compatibilité des appareils et améliorer l'alignement des surimpressions en direct sur plus de voitures et de configurations comma.

Si vous voulez en être, inscrivez-vous à l'accès anticipé sur la page d'accueil. Nous utiliserons le blog pour les notes de version, les nouvelles pour les testeurs et les notes techniques, à mesure que CommaView grandit.
