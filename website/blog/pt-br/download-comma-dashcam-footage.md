---
title: "Como baixar as imagens de dashcam de um comma"
description: "Um guia prático sobre os arquivos de vídeo do comma, as diferenças entre comma 3, 3X e four, e as formas mais seguras de exportar as imagens de uma rota."
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma device video
  - dashcam footage
  - openpilot tools
  - SSH
heroLabel: "Guia do comma"
draft: false
---

Precisa tirar vídeo de um comma? Os caminhos de sempre são o comma connect, o Openpilot Toolkit ou o acesso direto por SSH/SFTP.

O que confunde as pessoas é a organização dos arquivos. Os comma gravam as rotas do openpilot em segmentos curtos, e não num único clipe de dashcam gigante. Cada segmento pode incluir arquivos de câmera brutos, vídeo de prévia e logs da rota. Quando isso fica claro, exportar imagens deixa de ser um mistério.

Uma observação importante logo de cara: um comma pode ser útil para gravar a via, depurar e revisar rotas, mas não é um substituto direto de uma dashcam dedicada.

## Os comma são câmeras úteis, não dashcams perfeitas

Uma dashcam dedicada é feita para capturar provas: inicialização rápida, resistência a acidentes, modo estacionado, exportação simples de arquivos, opções de câmera traseira e armazenamento removível.

Um comma é feito para rodar o openpilot. Ele grava dados de rota porque eles são úteis para os modelos de condução, a depuração, as prévias do connect e o desenvolvimento. Essas imagens podem ser valiosas, mas vêm com concessões:

- recuperar as imagens pode ser mais difícil do que tirar um cartão SD
- um acidente ou uma queda repentina de energia pode fazer perder as imagens recentes
- gravar em modo estacionado não é o objetivo principal
- a cobertura de uma dashcam traseira não está incluída
- os dados locais antigos são apagados quando o dispositivo precisa de espaço

Se o objetivo são imagens confiáveis de um acidente, use uma dashcam de verdade. Se o objetivo são imagens de rotas do openpilot, revisão para desenvolvimento ou exportação local de vídeo, vale a pena aprender como o comma funciona.

## Que arquivos o openpilot grava?

A documentação oficial de registro do openpilot descreve as rotas como segmentos de um minuto. Para cada segmento, o openpilot atual grava estes tipos de arquivo:

| Arquivo | O que contém |
| --- | --- |
| `fcamera.hevc` | vídeo da câmera da via, H.265/HEVC |
| `ecamera.hevc` | vídeo da câmera grande-angular da via, H.265/HEVC |
| `dcamera.hevc` | vídeo da câmera do motorista/interior, H.265/HEVC |
| `qcamera.ts` | prévia H.264 em resolução menor da câmera da via |
| `rlog.zst` | logs completos da rota |
| `qlog.zst` | logs reduzidos da rota |

O vídeo mostrado no comma connect é o `qcamera.ts`, de resolução menor. As imagens de câmera em resolução total ficam nos arquivos HEVC e podem precisar ser enviadas manualmente pelo connect ou copiadas direto do dispositivo.

Rotas antigas, forks antigos ou documentação antiga podem mostrar `rlog`/`qlog` sem `.zst`, ou nomes de log `.bz2` mais antigos. Para o openpilot atual, use os nomes acima.

## comma 3, comma 3X e comma four: o que muda?

Há duas coisas diferentes que as pessoas misturam: o hardware das câmeras e a organização dos arquivos.

O hardware das câmeras muda conforme a geração:

| Dispositivo | Câmeras e armazenamento |
| --- | --- |
| comma 3 | Três câmeras de 1080p com HDR de 120 dB. A documentação da comunidade lista várias versões de armazenamento: 1 TB, 250 GB, 64 GB (tardia) e 32 GB (inicial). |
| comma 3X | A mesma disposição de três câmeras do comma 3, com sensores de imagem OX03C10 melhores, HDR de 140 dB e, segundo costuma ser informado, 128 GB de armazenamento. |
| comma four | A comma o descreve com o mesmo processamento, o mesmo conjunto de sensores e as mesmas funções do comma 3X, mas num formato físico muito menor. O sistema de três câmeras cabe na área da tela de 1,9 polegada, com duas câmeras voltadas para a via e uma câmera interna com visão noturna. A comma informa 128 GB de armazenamento e 10 horas de imagens. |

As observações sobre arquivos aqui valem para os três. O CommaView em si funciona só com o comma 3X e o comma four.

No openpilot atual, a organização prática dos arquivos é a mesma em todo o hardware da comma. Os arquivos de segmento atuais são `fcamera.hevc`, `ecamera.hevc`, `dcamera.hevc`, `qcamera.ts`, `rlog.zst` e `qlog.zst`.

Ou seja, as câmeras podem mudar fisicamente enquanto os nomes de exportação continuam os mesmos. `fcamera.hevc` é a câmera da via. `ecamera.hevc` é a câmera grande-angular da via. `dcamera.hevc` é a câmera do motorista/interior.

Se você usa um fork personalizado, confira no dispositivo antes de presumir que todos os arquivos estão lá. Os forks podem mudar as configurações de gravação, e a gravação do motorista/interior pode depender das configurações do dispositivo.

## Onde os arquivos ficam guardados localmente?

No hardware da comma, a raiz de logs atual do openpilot é:

```text
/data/media/0/realdata
```

Dentro dessa pasta, cada segmento de rota tem a própria pasta com data e hora, por exemplo:

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

É nessa pasta que você procura arquivos como:

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

Para trabalhar direto por SSH/SFTP, esta é a pasta por onde começar. A documentação oficial explica como se conectar a um comma 3X ou comma four por SSH, e o openpilot usa `/data/media/0/realdata` como raiz de logs no dispositivo.

## Opção 1: usar o comma connect

Para viagens recentes, o comma connect costuma ser o lugar mais fácil para começar.

Use o connect quando:

- a rota é recente
- o dispositivo enviou a rota com sucesso
- o vídeo de prévia basta
- você prefere uma interface web ao SSH
- você só precisa de alguns clipes ou arquivos

O connect também é onde muitos usuários identificam primeiro a rota e os números de segmento de que precisam. O problema é a retenção: o connect pode parar de mostrar uma rota antes de o dispositivo apagá-la. Se o connect não mostra mais uma rota mas os arquivos ainda existem no dispositivo, talvez o SSH/SFTP ainda consiga recuperá-los.

Lembre também que as prévias do connect se baseiam no `qcamera.ts`. Se você precisa das imagens de câmera em resolução total, garanta que os arquivos de vídeo completos sejam enviados ou tire direto os arquivos HEVC brutos.

## Opção 2: usar o Openpilot Toolkit

O Openpilot Toolkit é uma ferramenta da comunidade que pode deixar a exportação local menos sofrida. Ele inclui fluxos para configurar o SSH, navegar pelos arquivos, ver os vídeos das viagens e exportar os brutos.

Use o Openpilot Toolkit quando:

- você quer uma interface gráfica
- você não quer digitar os comandos SSH na mão
- você precisa de ajuda para configurar as chaves
- você usa Windows ou Android
- você quer navegar e exportar as imagens de uma rota de forma mais direta

Para muitos usuários, é o melhor meio-termo: mais controle que o connect e menos atrito que trabalhar à mão no terminal.

## Opção 3: usar SSH ou SFTP diretamente

O acesso direto por SSH/SFTP dá o máximo de controle e o mínimo de ajuda.

Em linhas gerais, o acesso por SSH costuma ser:

1. Criar ou usar uma conta do GitHub com chaves SSH.
2. Ativar o SSH nas configurações do comma.
3. Digitar o seu usuário do GitHub no comma para que ele busque as suas chaves públicas.
4. Conectar como usuário `comma` na porta `22`.

Depois de conectado, navegue ou copie a partir de:

```text
/data/media/0/realdata
```

Use o acesso direto quando:

- você precisa dos arquivos `fcamera.hevc`, `ecamera.hevc` ou `dcamera.hevc` brutos
- o connect não mostra o arquivo de que você precisa
- você quer arquivar uma rota inteira
- você se vira bem com clientes SFTP como FileZilla ou WinSCP
- você se vira bem com `ssh`, `scp` ou `rsync`

Os arquivos `.hevc` brutos costumam tocar no VLC. Se outro app precisar de MP4, faça o remux com o ffmpeg em vez de recodificar sempre que possível.

## Qual método usar?

Use o comma connect se a viagem é recente e uma revisão normal da rota basta.

Use o Openpilot Toolkit se você quer um fluxo local mais amigável sem fazer cada passo de SSH/SFTP à mão.

Use SSH ou SFTP se você precisa de arquivos brutos, arquivos locais mais antigos, arquivos completos de rotas ou controle direto sobre o que é copiado.

## Onde o CommaView entra

O CommaView é um app Android, local primeiro, para transmitir a câmera do comma, com sobreposições, configuração do runtime, gravações e reproduções.

Ele está no mesmo universo do acesso local à câmera, mas não é o comma connect, nem o Openpilot Toolkit, nem uma dashcam tradicional. Não deve ser usado como auxílio à direção nem como único sistema de captura de provas num veículo.

O CommaView funciona com o comma 3X e o comma four, com o openpilot ou um [fork compatível](/forks): sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 ou carrotpilot. O comma 3 não é compatível: a comma o passou para uma versão do openpilot congelada e de suporte de longo prazo, de cuja tela o CommaView não consegue tirar a sobreposição ([por quê](/pt-br#faq-comma-3)).

## Leia também

- Documentação oficial de registro do openpilot: [Logging](https://docs.comma.ai/concepts/logs/)
- Documentação oficial de SSH da comma: [conectar a um comma 3X ou comma four](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect: [comma.ai/connect](https://comma.ai/connect)
- Wiki do openpilot: [Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma: [Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit: [página do projeto](https://spektor56.github.io/OpenpilotToolkit/)
