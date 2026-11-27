---
title: "Um comma é uma dashcam? Útil, mas não substitui"
description: "Um olhar cuidadoso sobre as imagens do comma após o openpilot 0.11.2: arquivos de rota, retenção e clipes do connect, armazenamento local, acidentes, modo estacionado e dashcams."
date: 2026-11-06
slug: is-comma-a-dashcam
tags:
  - comma dashcam
  - comma device video
  - dashcam footage
  - openpilot
heroLabel: "A verdade sobre a dashcam"
draft: false
---

Um comma pode gravar imagens úteis da via e do interior do carro. Isso não faz dele um substituto direto de uma dashcam dedicada.

As imagens podem ajudar a revisar rotas, depurar, exportar e dar contexto a um incidente. Mas uma dashcam dedicada parte de outras premissas: capturar provas que resistam a um acidente, armazenamento removível simples, modo estacionado, câmera traseira e uma recuperação tão simples quanto a de um eletrodoméstico.

Se imagens confiáveis de um acidente ou para o seguro importam para você, use uma dashcam dedicada junto com o comma. Resposta chata, resposta certa.

## O que um comma grava

O openpilot grava rotas enquanto o dispositivo está ligado. A documentação atual de registro descreve as rotas em segmentos, com arquivos de câmera e de log como:

- `fcamera.hevc`: vídeo da câmera da via
- `ecamera.hevc`: vídeo da câmera grande-angular da via
- `dcamera.hevc`: vídeo da câmera do motorista/interior
- `qcamera.ts`: vídeo de prévia em resolução menor
- `rlog.zst`: log completo da rota
- `qlog.zst`: log reduzido da rota

São dados muito úteis.

Mas também não são um simples "clipe de dashcam". É o registro de rotas do openpilot: arquivos segmentados, IDs de rota, comportamento de envio, retenção local, codecs, logs e ferramentas.

## Onde as imagens podem estar

Há dois lugares onde as pessoas costumam olhar primeiro:

1. **comma connect**, para viagens recentes visíveis na nuvem.
2. **o armazenamento local do dispositivo**, para arquivos que ainda existem no comma.

A [página do prime](https://comma.ai/prime) da comma diz que as viagens enviadas ficam no connect por 3 dias, ou 1 ano com o comma prime. Por padrão, o connect mostra o vídeo `qcamera`, de resolução menor ([a documentação de logs da comma](https://docs.comma.ai/concepts/logs/)).

Desde o [openpilot 0.11.2](https://blog.comma.ai/0112release/) (outubro de 2026), o connect também pode cortar um clipe de parte de uma viagem: o comma o recodifica como MP4 enquanto continua ligado, e você o baixa pelo connect. Isso deixa muito mais fácil do que antes conseguir um clipe para compartilhar.

O armazenamento local do openpilot é outra coisa. No hardware atual da comma, a área prática de dados de rota fica em `/data/media/0/realdata/`. Mas o armazenamento local não é infinito. O openpilot faz limpeza quando falta espaço, então as rotas antigas não são um arquivo permanente.

Se algo importa, guarde logo.

## Por que as pessoas ainda usam as imagens do comma

As imagens do comma podem ser realmente úteis.

Bons usos:

- revisar o que aconteceu numa rota
- depurar o comportamento do openpilot
- verificar o contexto de câmera e logs
- exportar clipes ou arquivos HEVC brutos
- compartilhar exemplos para desenvolvimento ou suporte
- alimentar fluxos de reprodução e testes

Se você já tem um comma, ignorar essas imagens seria bobagem. Elas têm valor.

O erro é achar que "valioso" significa "o mesmo trabalho de uma dashcam dedicada".

## Por que ele não substitui uma dashcam dedicada

Uma dashcam dedicada costuma ser feita, antes de tudo, para capturar provas.

Isso geralmente significa armazenamento simples, recuperação rápida, modos de estacionamento, opções de câmera traseira ou interna, funcionamento independente e fluxos pensados para guardar clipes depois de um incidente.

Um comma é feito para rodar o openpilot. Os dados de câmera existem porque o openpilot precisa de registro, desenvolvimento de modelos, depuração, revisão de rotas e das prévias do connect.

Essas prioridades se sobrepõem às de uma dashcam, mas não são idênticas.

## Os pontos de risco

### Resistência a acidentes e quedas de energia

Se o dispositivo perde energia, é danificado ou desliga na hora errada, as imagens recentes podem ser mais difíceis de recuperar ou podem não estar completas.

Isso não significa que as imagens do comma sejam inúteis em qualquer incidente. Significa que elas não deveriam ser o seu único plano para ter provas.

### Modo estacionado

As dashcams dedicadas costumam vender o modo estacionado com kit de instalação fixa como recurso principal.

O openpilot 0.11.2 permite transmitir ao vivo no connect as câmeras da via e do motorista de um carro estacionado, com conexão à internet e um comma power instalado. O post da comma descreve isso como uma forma de ver o que está acontecendo ao redor do carro; não o apresenta como um gravador de eventos em modo estacionado.

Considere a vigilância do carro estacionado território das dashcams dedicadas, a menos que você tenha uma configuração bem específica e validada e entenda os riscos.

### Cobertura traseira

As câmeras da via, grande-angular e do motorista/interior do comma não equivalem a uma dashcam traseira.

Se a cobertura traseira importa, use um hardware que grave para trás.

### Atrito para armazenar e exportar

Uma dashcam geralmente busca uma recuperação de clipes simples pelo microSD, por um app ou por uma tela.

Recuperar imagens do comma pode envolver janelas de visibilidade do connect, envio manual, IDs de segmento, SSH/SFTP, arquivos HEVC, limpeza local, VLC/ffmpeg/remuxing ou ferramentas auxiliares. Os novos clipes do connect ajudam, mas o comma precisa continuar ligado enquanto faz um, e a viagem ainda precisa estar lá.

Isso é ok para usuários técnicos. Não é tão simples quanto um eletrodoméstico.

## Quando as imagens do comma podem bastar

As imagens do comma podem bastar para:

- ter uma referência informal da via
- revisar rotas do openpilot
- depurar e testar
- apoiar o desenvolvimento
- exportar localmente quando a rota ainda existe
- revisar um incidente pouco depois de ele acontecer

É uma lista forte.

Mesmo assim, isso não faz do comma o seu único gravador sério de provas.

## Quando adicionar uma dashcam

Use uma dashcam dedicada se você se importa com:

- imagens confiáveis de um acidente ou para o seguro
- vigilância do carro estacionado
- cobertura traseira
- a recuperação mais fácil possível
- armazenamento removível
- gravação independente se o comma perder energia
- uma ferramenta mais simples para motoristas não técnicos

A combinação não tem nada de estranha. Um comma pode ser ótimo para o openpilot enquanto uma dashcam cuida da tarefa chata de capturar provas.

## Onde o CommaView entra

O CommaView é um app Android e um pequeno runtime no comma. Ele mostra ao vivo a câmera da via do comma com a sobreposição de condução do seu fork no seu celular, tablet ou central multimídia Android, pela sua própria rede, e salva no seu celular o que você grava. Toque em **Gravar** no Live View e, quando você estacionar, ele baixa o vídeo do próprio comma desse trecho, até 10 minutos, e desenha a sobreposição por cima; ou salve uma cópia ao vivo do que o Live View mostra, sem o limite de 10 minutos. Nada é enviado, e as gravações ficam no seu celular até você excluí-las. Ele grava quando você toca em **Gravar**, não sozinho, então não ajuda num incidente que você não viu chegando.

Isso deixa muito mais fácil conseguir um clipe do que você viu. Não transforma um comma numa dashcam crítica para a segurança.

Não garante que as provas sejam preservadas.

Não é um auxílio à direção.

E funciona só com o comma 3X e o comma four, não com o comma 3. O CommaView não é oficial e não é afiliado à comma.ai nem endossado por ela.

## Lista prática depois de um incidente

Não é orientação jurídica, só uma triagem prática:

1. Pare de dirigir e cuide primeiro da segurança e das emergências.
2. Não confie só na retenção do connect.
3. Guarde ou exporte os segmentos de rota relevantes assim que puder.
4. Se usar o connect, identifique a rota e o intervalo de tempo de que precisa.
5. Se o connect não mostrar os arquivos mas o dispositivo ainda os tiver, use SSH/SFTP autorizado pelo dono ou uma ferramenta local confiável.
6. Guarde os arquivos originais sempre que possível.
7. Evite edições destrutivas ou limpezas até copiar as imagens importantes.
8. Para questões jurídicas ou de seguro, fale com os profissionais adequados.

O principal: aja rápido, copie com cuidado e não presuma que as imagens vão esperar por você para sempre.

## A resposta honesta

Um comma é uma câmera e um gravador de dados útil para as rotas do openpilot. Ele pode dar um contexto em vídeo valioso.

Mas se a pergunta é "posso dispensar a dashcam?", a resposta segura é não.

Use as imagens do comma para revisar rotas, depurar e trabalhar localmente. Use uma dashcam dedicada quando o requisito é capturar provas de forma confiável.
