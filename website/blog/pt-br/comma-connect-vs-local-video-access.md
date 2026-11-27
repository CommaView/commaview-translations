---
title: "comma connect ou vídeo local: qual faz o que você precisa?"
description: "comma connect, SSH e CommaView comparados após o openpilot 0.11.2: transmissão com o carro parado, clipes, retenção de viagens, qualidade, privacidade e para que serve cada um."
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - local video access
  - comma four
  - CommaView
heroLabel: "Comparação para decidir"
draft: false
---

O comma connect, o app web da própria comma, é onde a maioria dos donos olha as viagens primeiro, e para muitas tarefas é o lugar certo. Desde o openpilot 0.11.2 ele faz mais do que antes: pode transmitir ao vivo um carro estacionado e cortar clipes MP4 no dispositivo. O acesso local, por SSH ou com o CommaView, faz outro trabalho: tira o vídeo direto do comma pela sua própria rede.

A resposta curta:

- **Uma viagem recente, de qualquer lugar:** comma connect.
- **Dar uma olhada no carro enquanto ele está estacionado:** a transmissão ao vivo do comma connect.
- **Ver a via com a sobreposição de condução do seu fork enquanto dirige, numa tela maior:** o Live View do CommaView.
- **Os arquivos de câmera brutos, para desenvolvimento ou arquivo:** SSH.
- **Um clipe do que você acabou de ver, com a sobreposição, no seu celular, sem enviar nada:** o **Gravar** do CommaView.

## O que o comma connect faz

**Ele guarda as suas viagens na nuvem, por um tempo.** A [página do prime](https://comma.ai/prime) da comma diz que as gravações "são enviadas ao connect, onde ficam guardadas por 3 dias". Com o comma prime (US$ 24 por mês, só nos EUA, dados incluídos) ou o prime lite (US$ 14 por mês, com o seu próprio chip se quiser dados móveis), o connect as guarda por um ano.

**O que ele mostra por padrão é o vídeo pequeno.** A [documentação de logs](https://docs.comma.ai/concepts/logs/) da comma diz que o vídeo no connect vem dos arquivos qcamera, "versões de menor resolução do fcamera.hevc", feitas para serem enviadas rápido numa conexão lenta. Os arquivos HEVC em resolução total ficam no comma, a menos que você os envie também.

**Desde o 0.11.2, ele transmite ao vivo um carro estacionado.** O [post da versão 0.11.2](https://blog.comma.ai/0112release/) (23 de outubro de 2026) diz que, com conexão à internet, "o Wi‑Fi de casa ou o LTE do comma prime", e um comma power instalado, "você pode transmitir ao vivo as câmeras da via e do motorista para ver o que está acontecendo ao redor do veículo enquanto ele está estacionado". Você assiste no connect, de qualquer lugar.

**Ele também corta clipes.** A mesma versão adiciona um botão de clipes no connect: escolha parte de uma viagem e "o seu comma vai juntá-la e recodificá-la como um MP4 (H.264) amplamente compatível". Deixe o comma ligado enquanto ele trabalha e depois baixe o clipe pelo connect.

É um avanço real. Se você quer ver o seu carro estacionado da sua mesa, ou mandar para um amigo um clipe da viagem de ontem à noite, o connect agora faz as duas coisas.

## O que o comma connect não faz

- **Ele não transmite enquanto você dirige.** A transmissão ao vivo é para um carro estacionado.
- **Ele não desenha a sobreposição de condução do openpilot.** A transmissão e os clipes são vídeo de câmera, sem a trajetória, as faixas, os alertas ou a velocidade que você vê na tela do comma.
- **Ele precisa de internet.** A transmissão precisa do Wi‑Fi de casa ou do LTE do prime, e as viagens precisam ser enviadas antes que o connect possa mostrá-las.
- **Ele esquece depois de 3 dias sem o prime.** Depois disso, o connect não mostra mais a viagem, mesmo que o comma ainda a tenha.

Nada disso é um defeito. O connect é um serviço na nuvem para ver o seu carro e as suas viagens de onde você estiver.

## O que o acesso local faz

Acesso local significa pegar o vídeo do próprio comma, na mesma rede, em vez dos servidores da comma.

### SSH: os arquivos brutos

Cada viagem do openpilot é salva no comma em segmentos de um minuto, cada um com os próprios arquivos: `fcamera.hevc` (via), `ecamera.hevc` (via grande-angular), `dcamera.hevc` (motorista), `qcamera.ts` (a prévia pequena) e os logs. Por SSH você pode copiar qualquer um deles enquanto o comma ainda os tiver; ele apaga as viagens mais antigas quando fica sem espaço. É o jeito de conseguir vídeo em resolução total para desenvolvimento ou para o seu próprio arquivo, mas são arquivos HEVC de um minuto, não um clipe que dá para compartilhar. O nosso guia para [baixar as imagens do comma](/pt-br/blog/download-comma-dashcam-footage) mostra o passo a passo.

### CommaView: Live View e Gravações no Android

O CommaView é um app Android e um pequeno runtime no comma, o `commaviewd`, que envia a câmera e os dados de condução para o seu celular pela sua própria rede local: o seu Wi‑Fi, ou um ponto de acesso no carro, seja do celular, da central multimídia ou do comma.

- **Live View, enquanto você dirige.** A câmera da via com a tela do próprio fork desenhada por cima, como o comma four ou o comma 3X a desenha, ou com a tela própria do CommaView, num celular, num tablet no painel ou numa central multimídia Android. A tela do comma four tem 1,9 polegada; a do seu celular é bem maior.
- **Gravações no seu celular.** Toque em **Gravar** no Live View e, quando você estacionar, o CommaView baixa o vídeo do próprio comma desse trecho, até 10 minutos, e desenha a tela do seu fork por cima no celular. Ou salve uma cópia ao vivo do que o Live View mostra, em 720p ou 1080p, sem o limite de 10 minutos. Assista, compartilhe ou abra em outro app.
- **Transmitir.** Transmita o que o Live View mostra, a via e a sobreposição, para o seu canal do YouTube ou qualquer servidor RTMP, em 720p ou 1080p.
- **Sem assinatura, sem envio.** O Live View e as gravações vão do seu comma para o seu celular, e as gravações ficam lá até você excluí-las. As câmeras do seu comma vão só para os celulares e centrais multimídia emparelhados com ele.

Funciona com o comma 3X e o comma four, com openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 e carrotpilot, e com outros forks sem garantia. [Quais forks, e o que o Live View desenha em cada um](/forks).

## Lado a lado

| Recurso | comma connect | CommaView |
| --- | --- | --- |
| Vídeo ao vivo | Câmeras da via e do motorista, com o carro estacionado | Câmera da via, enquanto você dirige |
| Sobreposição de condução | Não | A tela do seu fork, ou a do CommaView |
| Por onde vai o vídeo | Pela internet, assistido no connect | Pela sua própria rede local (Wi‑Fi ou um ponto de acesso), para os seus celulares emparelhados |
| Precisa de | Internet, e um comma power para a transmissão | Um celular, tablet ou central multimídia Android na mesma rede |
| Clipes | Qualquer parte de uma viagem, como MP4 cortado no comma e baixado pelo connect | O que você gravou no Live View: uma reprodução de até 10 minutos, ou uma cópia ao vivo, com a sobreposição |
| Quanto tempo as viagens ficam | 3 dias, um ano com o prime | No seu celular até você excluí-las |
| Custo | Grátis, ou prime US$ 24 / lite US$ 14 por mês | Sem assinatura; o CommaView está num beta só para convidados |

## Use os dois

Eles não disputam a mesma tarefa. Fique com o connect para ver o carro de qualquer lugar e para as viagens que você quer na nuvem; use o CommaView para ver a via com a sobreposição do seu fork numa tela maior, gravar o que você viu e transmitir. Um passageiro pode assistir ao Live View enquanto você dirige; se você dirige sozinho, trate-o como a tela do próprio comma e mantenha os olhos na via.

## Leia também

- [comma prime](https://comma.ai/prime), sobre os planos do connect e por quanto tempo ele guarda as viagens
- [openpilot 0.11.2](https://blog.comma.ai/0112release/), sobre a transmissão ao vivo e os clipes
- [Como baixar as imagens do comma](/pt-br/blog/download-comma-dashcam-footage), por SSH
- [Configurar o CommaView](/pt-br/guides/setup)

O CommaView não é oficial e não é afiliado ao comma.ai, ao sunnypilot nem a nenhum fork do openpilot com que funciona, nem endossado por eles. É software beta e não é um sistema de segurança: nunca deixe que ele tire sua atenção da direção.
