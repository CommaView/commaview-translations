---
title: "Transmissão local da câmera do comma no Android: o que o CommaView faz"
description: "O CommaView transmite a câmera da via do seu comma com a sobreposição para o Android pela sua própria rede: Live View, Gravações, Transmitir e o que ele não faz."
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma camera streaming
  - comma four
  - Android app
  - CommaView
  - local streaming
heroLabel: "Para que serve"
draft: false
---

O CommaView transmite a câmera da via do seu comma, com a sobreposição de condução, para um celular, tablet ou central multimídia Android pela sua própria rede. Não há nuvem entre o comma e o seu celular, e nada precisa ser enviado antes.

São duas partes: o app CommaView e um pequeno runtime no comma, o `commaviewd`, que entrega a câmera e os dados de condução ao app. A configuração guiada instala o runtime e o verifica.

## Por que transmitir?

A tela do comma four tem 1,9 polegada. É uma boa tela para o que faz, mas é pequena, e os donos dizem isso. As outras formas de tirar vídeo do comma foram feitas para outras tarefas:

- O **comma connect** guarda as viagens enviadas por 3 dias, ou um ano com o comma prime ([comma.ai/prime](https://comma.ai/prime)). Desde o [openpilot 0.11.2](https://blog.comma.ai/0112release/), ele transmite ao vivo as câmeras da via e do motorista com o carro estacionado, pela internet, com um comma power instalado, e corta clipes MP4 no comma.
- O **SSH** dá acesso aos segmentos HEVC brutos de um minuto no armazenamento do comma.

Nenhum dos dois mostra a via com a sobreposição de condução do openpilot enquanto você dirige. É para isso que serve o CommaView.

## O que o CommaView faz

### Live View

A câmera da via, ao vivo, com a tela do próprio fork desenhada por cima: a do comma four, a do comma 3X ou a do próprio CommaView, com a sua velocidade, MÁX, o limite de velocidade, o veículo à frente e as mudanças de faixa num só bloco. O Live View desenha a tela de cada fork com o que esse fork acrescenta, do MADS do sunnypilot ao HUD próprio do StarPilot. Roda a até 20 quadros por segundo, o máximo do comma, e continua em picture-in-picture.

Num tablet ou numa central multimídia Android, o CommaView se organiza como um painel, com os controles do Live View do lado do motorista.

### Gravações

Toque em **Gravar** no Live View e, quando você estacionar, o CommaView baixa o vídeo do próprio comma desse trecho, até 10 minutos, e desenha a tela do seu fork por cima no seu celular: uma reprodução. Assista, compartilhe ou abra em outro app. Uma cópia ao vivo salva o que o Live View mostra enquanto você dirige, em 720p ou 1080p, pronta assim que você para, sem o limite de 10 minutos. As gravações ficam no seu celular até você excluí-las.

### Transmitir

**Transmitir** envia o que o Live View mostra, a via e a sobreposição do CommaView, para o seu canal do YouTube ou qualquer servidor RTMP, em 720p ou 1080p. Entre com o YouTube uma vez e o app cria, inicia e encerra cada transmissão. As transmissões começam como **Não listado**; quem assiste vê por onde você dirige.

### Só celulares emparelhados

As câmeras e os dados do seu comma vão só para os celulares e centrais multimídia emparelhados com ele. Vídeo, viagens e lugares vão do seu comma para o seu celular e para nenhum outro lugar, a menos que você os envie, transmita ou contribua com eles.

## O que precisa de internet

O Live View e as gravações, não: vão direto do comma para o seu celular, na mesma rede local: o seu Wi‑Fi, ou um ponto de acesso no carro a partir do celular, da central multimídia, de uma AI box ou do comma. Precisam de internet: entrar na conta, as atualizações do app e do runtime, o mapa em **Localização do veículo**, o ranking, Transmitir e tudo o que você envia ao CommaView.

## Com o que funciona

O comma 3X e o comma four, com openpilot, sunnypilot, StarPilot, o openpilot da xnor-tech, AdventurePilot, SunnyPilot-TeslaHW1 e carrotpilot. Outros forks do openpilot funcionam sem garantia: a configuração verifica o fork e pergunta a você antes de instalar. O comma 3 não é compatível: ele está numa versão congelada do openpilot, de cuja tela o CommaView não consegue tirar a sobreposição. [Forks compatíveis](/forks).

Você precisa de um celular, tablet ou central multimídia com Android 8 ou mais recente.

## O que o CommaView não é

- **Não é o comma connect.** Não guarda viagens na nuvem nem mostra o seu carro do outro lado da cidade. Para isso, use o connect.
- **Não é uma dashcam.** [Use uma dashcam dedicada](/pt-br/blog/is-comma-a-dashcam) se precisar de imagens de batida ou de estacionamento que sirvam como prova.
- **Não é um auxílio à direção nem um sistema de segurança.** Ele mostra o que o comma vê; a via é a fonte da verdade.

## Use com segurança

Configure o CommaView com o carro parado. Um passageiro pode assistir ao Live View enquanto você dirige; se você dirige sozinho, trate-o como a tela do próprio comma e mantenha os olhos na via.

O CommaView está num beta só para convidados. [Entre na lista](https://my.commaview.com/join) e mandaremos um e-mail quando chegar a sua vez.

O CommaView não é oficial e não é afiliado ao comma.ai, ao sunnypilot nem a nenhum fork do openpilot com que funciona, nem endossado por eles. É software beta e não é um sistema de segurança: nunca deixe que ele tire sua atenção da direção.
