---
title: "CommaView 0.0.164: carrotpilot, SunnyPilot-TeslaHW1 e cópias ao vivo"
description: "O CommaView 0.0.164 adiciona carrotpilot e SunnyPilot-TeslaHW1, e cópias ao vivo que salvam o que o Live View mostra ao dirigir. E acesso antecipado à Navegação e ao Surround."
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot forks
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - recordings
heroLabel: "Notas de versão"
draft: false
---

O CommaView 0.0.164 já está disponível para todos no beta. Ele adiciona mais dois forks do openpilot, **carrotpilot** e **SunnyPilot-TeslaHW1**, e agora o CommaView funciona com sete: openpilot, sunnypilot, StarPilot, o openpilot da xnor-tech, AdventurePilot, SunnyPilot-TeslaHW1 e carrotpilot. Também traz as **cópias ao vivo**, que salvam o que o Live View mostra enquanto você dirige, prontas assim que você para.

Ele vem com o runtime `v0.0.60-beta`, que reconhece os dois forks novos. Atualize o runtime pelo app quando ele oferecer e reinicie o comma quando o app pedir.

## SunnyPilot-TeslaHW1

O SunnyPilot-TeslaHW1 é um fork do sunnypilot que adiciona os carros Tesla HW1 (Autopilot 1). A tela dele é a do sunnypilot, então o CommaView desenha a tela do sunnypilot com tudo o que o sunnypilot acrescenta e mostra o nome do fork no app.

Uma coisa a saber: o `op fork update` dele não consegue trocar o fork enquanto o hook do CommaView está instalado. Desinstale o CommaView antes, ou use o seletor de forks na tela do comma, que funciona normalmente.

## carrotpilot

O carrotpilot é um fork do openpilot para carros Hyundai, Kia e Genesis, instalado a partir de `i.carrotpilot.app`. O CommaView desenha a tela do openpilot para ele, com a sua velocidade, a trajetória, as faixas e o veículo à frente, e mostra o nome do fork no app.

Dois limites, por enquanto:

- **A tela própria do carrotpilot ainda não é desenhada.** O que ele acrescenta à tela do openpilot, como a navegação, os radares de velocidade e o HUD, não aparece no Live View.
- **As atualizações dele removem o hook do CommaView até o comma reiniciar.** A atualização automática do carrotpilot e as ferramentas de Git da página web dele redefinem os arquivos enquanto ele roda. Nada quebra: o app pede para reiniciar, e o Live View volta depois.

## Cópias ao vivo

Até agora, **Gravar** fazia uma reprodução: quando você estaciona, o app baixa o vídeo do próprio comma e desenha o HUD por cima. Continua sendo a melhor imagem, mas leva um tempo depois da viagem e para em 10 minutos por gravação.

Agora **Configurações › Gravações › Gravar no Live View** deixa você escolher o que **Gravar** faz:

| Opção | O que você recebe |
| --- | --- |
| **Reprodução** (o padrão) | O vídeo do próprio comma com o HUD desenhado por cima, feito depois que você estaciona. A melhor imagem, até 10 minutos por gravação. |
| **Cópia ao vivo** | O que o Live View mostra enquanto você dirige, salvo no seu celular e pronto em **Gravações** assim que você para, sem o limite de 10 minutos. |
| **Ambas** | Uma cópia ao vivo agora, e a reprodução depois da viagem. |

Uma cópia ao vivo é em 720p (cerca de 1,4 GB por hora) ou 1080p (cerca de 2,3 GB por hora), a 20 quadros por segundo. Ela continua enquanto você troca de app ou bloqueia o celular, com uma notificação pela qual você pode pará-la. Ela para sem problemas antes de o armazenamento do celular acabar e, se o app fechar durante a gravação, você fica com tudo menos o último minuto.

As cópias ao vivo ficam no seu celular e nunca são enviadas.

## Também no 0.0.164

- **Configurações que usam a tela toda.** **Gravações**, **Tela** e **Transmissão ao vivo** se organizam como **Mapas offline**, em duas colunas onde cabem, e ficam alinhadas em tablets, centrais multimídia e celulares na horizontal.
- **Por que uma instalação falhou.** Se a configuração, uma atualização do runtime ou uma desinstalação falhar, o app diz o que deu errado e o que fazer: um fork que o CommaView não suporta, o carro em movimento, o comma sem internet, um download corrompido. Ele diz se o seu comma ficou como estava, e **Copiar detalhes** copia o relatório de que o suporte precisa.
- **Reproduções mais rápidas.** Uma reprodução baixa só o vídeo que mostra, e a próxima viagem da fila é baixada enquanto outra é feita. Uma gravação interrompida porque o app fechou, pelo limite de 10 minutos ou porque o carro desligou agora também pode virar reprodução.
- **A qualidade da reprodução voltou a funcionar.** Balanced, High e Max voltam a fazer reproduções diferentes: todas estavam sendo feitas nos mesmos 40 Mbit/s. High, o padrão, agora faz arquivos com cerca de metade do tamanho a partir de um comma 3X.

## Acesso antecipado: Navegação e Surround

Alguns recursos estão no início do desenvolvimento: **Navegação**, **Surround**, **Transmitir** e **Enviar ao CommaView**. Estamos liberando esses recursos para um grupo limitado de testadores, ativados por conta, enquanto reunimos opiniões, então eles só aparecem nas contas em que estão ativados.

- **Navegação** é a orientação curva a curva do **Início** ao Live View: procure um lugar, escolha uma rota e siga o cartão de curva, as instruções faladas e, na tela do CommaView, as setas pintadas na sua faixa. Se você errar uma curva, ela encontra uma nova rota em segundos. É só para exibição: nada é enviado ao seu comma nem ao seu carro.
- **Surround** é uma visão 3D da via ao redor do seu carro: a via como a câmera a vê, com as linhas de faixa e os cruzamentos, e os carros, caminhões e semáforos ao seu redor.

Alguns deles rodam em serviços pagos, como o cálculo de rotas da Navegação, então estamos mantendo o grupo pequeno até saber quanto custa um uso normal. Se quiser ajudar a testar, fale com a gente no nosso [Discord](https://discord.gg/UuMhz9K8ft) e esteja pronto para contar como eles se saem nas suas viagens.

## Como conseguir

O CommaView está num beta só para convidados. Se você já participa, o app oferece a atualização 0.0.164 sozinho. Depois que ele atualizar, atualize o runtime no seu comma pelo app e reinicie o comma quando ele pedir. As atualizações do runtime esperam o carro estar em P com o openpilot desativado, então nunca interrompem uma viagem.

Novo no CommaView? O [guia de configuração](/pt-br/guides/setup) mostra como instalar o app e conectar o seu comma.

## Leia também

- [Quais forks do openpilot funcionam com o CommaView](/forks), incluindo [SunnyPilot-TeslaHW1](/forks#teslahw1) e [carrotpilot](/forks#carrotpilot)
- [Novidades](/whats-new) de cada versão
- [Como funcionam as versões do CommaView](/pt-br/guides/releases)

O CommaView não é oficial e não é afiliado à comma.ai, ao sunnypilot, ao carrotpilot nem ao SunnyPilot-TeslaHW1. É software beta e não é um sistema de segurança: nunca deixe que ele tire sua atenção da direção.
