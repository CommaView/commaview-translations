---
title: "O CommaView agora funciona com StarPilot, xnor e AdventurePilot"
description: "O CommaView 0.0.163 adiciona o openpilot da xnor-tech e o AdventurePilot, após o StarPilot no 0.0.162. O que cada fork do openpilot mostra no Live View no comma 3X e no comma four."
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "Notas de versão"
draft: false
---

O CommaView agora funciona com cinco versões do openpilot: **openpilot**, **sunnypilot**, **StarPilot**, **o openpilot da xnor-tech** (suas versões xnor e rx) e **AdventurePilot**. O StarPilot chegou no CommaView 0.0.162, e o beta 0.0.163 adiciona o xnor e o AdventurePilot. Em cada um, o Live View desenha a tela do próprio fork no seu celular, tablet ou central multimídia Android, com o que esse fork acrescenta.

Até agora, a configuração nesses forks parava com "unsupported upstream remote". Com o app 0.0.163 e o seu runtime, ela instala e emparelha como no openpilot.

## O que cada fork mostra no Live View

O CommaView não adivinha pelo nome do fork. O runtime no seu comma diz ao app o que a tela do fork acrescenta, e o app desenha isso na tela do comma four, na do comma 3X ou na tela própria do CommaView.

| Fork | O que o CommaView desenha |
| --- | --- |
| openpilot | As telas do comma four e do comma 3X, ou a sobreposição própria do CommaView |
| sunnypilot | A tela do sunnypilot: MADS, a assistência de limite de velocidade, a trajetória arco-íris, os indicadores de ponto cego e seus acréscimos no comma 3X |
| StarPilot | As cores, widgets, alertas e escolha de câmera do StarPilot |
| xnor | A tela do openpilot nas versões xnor, a do sunnypilot no rx, e a cor do volante do Rivian no rx |
| AdventurePilot | A tela do sunnypilot com seu indicador de centralização na faixa, o chip CURVE e a cor do modo de direção |

## StarPilot

O StarPilot mostra seus modos de condução com cores, e o CommaView usa as cores que o StarPilot escolheu: a borda, a trajetória e os widgets, os alertas e a escolha de câmera, incluindo a câmera do motorista. Desative antes a configuração **Disable Logging** do StarPilot: ela para o codificador de vídeo de onde o Live View transmite.

## O openpilot da xnor-tech: xnor e rx

O openpilot da xnor-tech vem em duas versões de um mesmo repositório. Os branches **xnor** usam a tela do openpilot e os branches **rx** a do sunnypilot, cada um com os ports de carros da xnor-tech. O CommaView descobre qual deles o seu comma roda e desenha essa tela, com os alertas como o comma os escreve.

Num Rivian com rx, o volante mostra como o carro está esterçando: verde quando esterça por ângulo, azul quando esterça por torque. O CommaView desenha as mesmas cores no volante do comma four e no botão de modo experimental do comma 3X.

## AdventurePilot

O AdventurePilot é um fork do sunnypilot com seus próprios ports de carros. O CommaView desenha a tela do sunnypilot com o que o AdventurePilot acrescenta:

- o **indicador de centralização na faixa**, uma pílula com o empurrão e o deslocamento na tela do comma 3X e uma barra compacta na do comma four;
- o **chip CURVE** na tela do comma 3X, que pisca enquanto o controle de velocidade em curvas atua;
- a **cor do modo de direção** no volante, e uma barra de torque que mostra a aceleração lateral enquanto um Rivian esterça pelo canal de ângulo.

## Como conseguir

O CommaView está num beta só para convidados. Se você já participa, o app oferece a atualização 0.0.163 sozinho. Depois que o app atualizar, atualize o runtime no seu comma pelo app e reinicie o comma quando ele pedir. As atualizações do runtime esperam o carro estar em P com o openpilot desativado, então nunca interrompem uma viagem.

Novo no CommaView? O [guia de configuração](/pt-br/guides/setup) mostra como instalar o app e conectar o seu comma.

## O que não mudou

- O CommaView funciona no **comma 3X** e no **comma four**. O comma 3 continua sem suporte, assim como as versões dos forks para comma 3, como xnor-c3 ([por quê](/pt-br#faq-comma-3)).
- O CommaView nunca muda como o seu fork dirige. Ele adiciona um pequeno runtime ao lado e um pequeno hook na interface da tela, para poder desenhar a mesma trajetória, as mesmas faixas e os mesmos alertas.
- Num fork que o CommaView ainda não suporta, a configuração para e deixa o seu comma como estava. Você pode pedir o seu fork no quadro de sugestões em my.commaview.com.

## Leia também

- [Quais forks do openpilot funcionam com o CommaView](/forks), com o que cada um mostra
- [Novidades](/whats-new) de cada versão
- [Como funcionam as versões do CommaView](/pt-br/guides/releases)

O CommaView não é oficial e não é afiliado à comma.ai, ao sunnypilot, ao StarPilot, à xnor-tech nem ao AdventurePilot. É software beta e não é um sistema de segurança: nunca deixe que ele tire sua atenção da direção.
