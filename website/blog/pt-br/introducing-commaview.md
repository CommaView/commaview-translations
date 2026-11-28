---
title: "Apresentando o CommaView: transmissão local da câmera para dispositivos comma"
description: "O CommaView é um app Android para ver a câmera do seu comma localmente, com sobreposições no estilo MICI, configuração do runtime, gravações e reprodução de viagens."
date: 2026-05-02
slug: introducing-commaview
tags:
  - CommaView
  - comma device camera streaming
  - Android app
  - openpilot tools
heroLabel: "Notas do produto"
draft: false
---

O CommaView existe porque acessar a câmera do seu comma localmente deveria parecer um produto de verdade, e não um monte de scripts grudados numa sessão SSH.

O objetivo é simples: emparelhar um dispositivo Android com o seu comma, transmitir a câmera da via localmente, mostrar sobreposições de condução úteis e deixar a configuração entediante, no melhor sentido.

## Por que local primeiro?

O CommaView não tenta ser um painel na nuvem. O app conversa com o seu comma pela sua conexão local e mantém o essencial perto do hardware.

Isso importa porque um app que transmite a câmera do comma localmente pode ser rápido, fácil de entender e cuidadoso com a privacidade. Não deveria ser preciso ter uma conta só para ver o que o seu próprio dispositivo está vendo.

## O que o CommaView faz

O alfa atual foca no que deixa os testes do dia a dia menos chatos:

- transmissão local da câmera da via para o Android
- sobreposições no estilo MICI de trajetória, faixas, status e monitoramento do motorista
- configuração guiada do runtime para o serviço `commaviewd` no comma
- gravações de viagens e exportação de reproduções
- versões do app e do runtime pareadas, para que os testadores instalem versões compatíveis

## Por que Android primeiro?

O CommaView é só para Android porque o Android é o alvo prático para esse uso: celulares, tablets, instalação manual de apps, redes locais e hardware feito para o carro se encaixam melhor ali.

Esse foco deixa o app afiado, em vez de diluído para todas as plataformas possíveis.

## O que vem por aí

O acesso antecipado dos testadores vai ajudar a deixar a instalação mais robusta, verificar a compatibilidade de dispositivos e melhorar o alinhamento das sobreposições ao vivo em mais carros e configurações de comma.

Se quiser participar, entre na lista de acesso antecipado na página inicial. Vamos usar o blog para notas de versão, novidades para testadores e notas técnicas à medida que o CommaView cresce.
