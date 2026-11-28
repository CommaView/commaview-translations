---
title: "Gravar uma viagem pelo Live View"
description: "Toque em Gravar no Live View e gere a reprodução da viagem ao estacionar: o próprio vídeo do comma com a tela do seu fork desenhada por cima, salvo no seu celular."
topic: recordings
order: 1
kind: walkthrough
lede: "**Gravar** no Live View salva uma viagem. A menos que você escolha outra coisa, ele gera uma **reprodução**: quando você estaciona, o CommaView baixa o próprio vídeo do comma do que você gravou, até 10 minutos, e desenha a tela de condução por cima no seu celular. Nada é enviado: as gravações ficam no seu celular até você excluí-las."
parked: true
updated: 2026-11-27
needs:
  - title: "O Live View funciona"
    text: "O CommaView no seu celular, emparelhado com seu comma. Ainda não? [Configurar o CommaView](/pt-br/guides/setup) e depois [abrir o Live View](/pt-br/guides/live-view)."
  - title: "O carro ligado"
    text: "Gravar começa quando o comma inicia uma viagem, então ligue o carro primeiro. Comece a gravar em P, antes de sair."
  - title: "Espaço no seu celular"
    text: "A reprodução é gerada no seu celular, a partir do vídeo do comma. Configurações › Gravações mostra o armazenamento usado e o espaço livre."
howItWorks:
  - title: "Gravar no Live View"
    text: "Abre a janela de captura do comma: ela guarda os dados da tela de condução enquanto você grava."
    edge: "depois de estacionar"
  - title: "Gerar reprodução"
    text: "O celular baixa o vídeo do comma daquele trecho, uma viagem por vez."
  - title: "Gravações"
    text: "A reprodução roda no seu celular, com a tela desenhada sobre o vídeo."
steps:
  - id: choose
    title: "Escolha o que Gravar gera"
    body: |
      Toque em **Configurações** e depois em **Gravações**. Em **Gravar no Live View**, **Reprodução** fica escolhida até você mudar: “A melhor imagem: o próprio vídeo do comma com o HUD desenhado por cima, gerada depois que você estaciona. Até 10 minutos por gravação.”

      **Cópia ao vivo** salva o que o Live View mostra, sem limite de tempo, e **Ambas** gera as duas. Elas têm [um guia próprio](/pt-br/guides/live-copy).
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Gravar no Live View**: **Reprodução**, **Cópia ao vivo** ou **Ambas**."
      - text: "**Reprodução** abre a qualidade: **Balanced**, **High** ou **Max**. Qualidade maior demora mais para gerar e cria arquivos maiores."
  - id: start
    title: "Toque em Gravar no Live View"
    body: |
      Com o carro ligado e ainda em P, abra o **Live View** e toque em **Gravar**. Por um momento aparece **Iniciando…** enquanto o CommaView sincroniza com a viagem, e depois o cronômetro corre.
    screen: phone-live-view
    clip: record
    pins:
      - target: record-button
        text: "**Gravar**. Em um tablet, uma central multimídia ou um celular de lado, ele fica na barra."
    warn: "Comece a gravar antes de sair, ou deixe um passageiro cuidar disso. Não mexa no CommaView enquanto dirige."
  - id: recording
    title: "Deixe gravar"
    body: |
      Enquanto grava, Gravar mostra o tempo e **Detalhes** mostra **Gravando ·** e o tempo. Toque em Gravar de novo para parar. Uma reprodução também para sozinha aos 10 minutos e quando o Live View fecha.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Gravar, com o cronômetro. Toque de novo para parar."
      - target: recording
        text: "**Gravando ·** o tempo, em **Detalhes**."
      - text: "**Salvar** guarda os últimos 3 minutos e o próximo minuto, sem Gravar. É copiado para o seu celular quando você estaciona."
    note: "**Salvar** só aparece onde o runtime do seu comma lista as viagens. Um toque dentro desse próximo minuto guarda mais um minuto, até 10 minutos. Deixe isso com um passageiro enquanto você dirige."
  - id: make-replay
    title: "Estacione e gere a reprodução"
    body: |
      Depois de estacionar, abra **Gravações** pela barra de baixo (a barra lateral em uma tela maior). A viagem que você gravou mostra **Aguardando processamento**. Abra e toque em **Gerar reprodução**: o app diz “Reprodução na fila. Acompanhe em Fila.”

      O comma só compartilha uma viagem enquanto o carro está em P com o openpilot desativado, então mantenha o carro ligado e o celular na rede do comma até a reprodução ficar pronta. Sem um chicote de alimentação, desligar o carro também desliga o comma.
    screen: recordings-make-replay
    pins:
      - text: "**Gerar reprodução**."
      - target: queue
        text: "**Fila** mostra cada reprodução sendo gerada, uma por vez, com Pausar, Tentar de novo e Remover."
    note: "**Gerar reprodução** pode levar até um minuto para aparecer depois de estacionar: um comma que disse estar em movimento é consultado de novo um minuto depois."
  - id: watch
    title: "Assista em Gravações"
    body: |
      Quando fica pronta, o app diz **Reprodução gerada** com o número de quadros, e a viagem roda em Gravações. Toque para assistir, em tela cheia se quiser.
    screen: phone-recordings
    pins:
      - text: "A reprodução da viagem, agrupada sob o dia."
      - target: filter
        text: "**Filtrar**: **Todas as viagens**, **Prontas** ou **Aguardando processamento**, e qual comma."
check: "A linha da viagem não mostra mais **Aguardando processamento**, e ela roda quando você toca. Para compartilhar ou salvar em outro lugar, veja [Compartilhar e exportar gravações](/pt-br/guides/export-share)."
fixes:
  - q: "“A gravação pode começar depois que o comma iniciar uma viagem.”"
    a: "O comma está parado. Ligue o carro, espere o openpilot iniciar e toque em Gravar de novo."
  - q: "“O CommaView ainda está sincronizando com esta viagem. Tente Gravar de novo em instantes.”"
    a: "Gravar precisa dos tempos de quadro do comma, que chegam com os dados de condução. Eles não chegaram em 5 segundos. Espere um momento e toque em Gravar de novo."
  - q: "“O CommaView não está recebendo dados de condução do comma. Verifique a conexão e tente Gravar de novo.”"
    a: "O vídeo pode continuar rodando, mas os dados de condução pararam. Confira se o celular continua no Wi-Fi ou ponto de acesso do comma e tente de novo. Se o Live View disser **Os dados do carro não estão chegando**, reinicie o comma."
  - q: "“Reinicie o comma antes: o CommaView foi instalado, atualizado ou reparado e volta a gravar após reiniciar.”"
    a: "Reinicie o comma com o carro em P e grave de novo."
  - q: "“O armazenamento de gravação está cheio. Libere espaço e tente Gravar de novo.”"
    a: "Exclua em Gravações as viagens de que não precisa mais, ou escolha outro armazenamento em **Configurações › Gravações › Armazenamento** com **Alterar**."
  - q: "“O comma não tem mais espaço para os dados do HUD desta viagem (cerca de 55 minutos de gravações). Grave de novo na próxima viagem.”"
    a: "O comma guarda até cerca de 55 minutos de dados do HUD de gravações por viagem. Gere as reproduções do que você gravou e grave de novo na próxima viagem."
  - q: "“Coloque em P para gerar esta reprodução”, ou a viagem mostra “Aguardando você estacionar”"
    a: "O comma só compartilha uma viagem estacionado, com o openpilot desativado. Coloque o carro em P e mantenha-o ligado. A reprodução espera e pergunta de novo a cada 15 segundos; depois de 30 minutos de condução ela para com “O carro ainda estava em movimento, então o comma não pôde compartilhar esta viagem. Tente de novo depois de estacionar.” Toque em **Tentar de novo** na Fila depois de estacionar."
  - q: "“Conecte-se a Comma Chameleon para gerar esta reprodução”"
    a: "Seu celular não conseguiu alcançar o comma que gravou a viagem (aparece o nome do seu). Conecte o celular ao Wi-Fi ou ao ponto de acesso do comma e toque em **Tentar de novo** na Fila. Veja [O CommaView não encontra seu comma](/pt-br/guides/comma-not-found)."
  - q: "“Viagem excluída do comma”"
    a: "O comma excluiu esta viagem para abrir espaço para outras mais novas antes de a reprodução ser gerada, então ela não pode mais ser gerada. Você pode excluir a gravação. Uma viagem que mostra **Gere a reprodução logo** está perto disso: gere enquanto pode."
  - q: "A reprodução mostra “HUD ausente por 2 min”"
    a: "O comma não salvou os dados da tela de condução em parte da gravação. A reprodução mostra **Dados do HUD indisponíveis** nesse trecho, e o dado **Dados do HUD** da tela de reprodução diz por quanto tempo."
  - q: "“Reprodução gerada: 4.860 quadros. Ela termina antes, onde o comma perdeu energia.”"
    a: "O comma perdeu energia quando a viagem terminou, então os últimos momentos não foram salvos. Gravações pode mostrar **Seu comma pode ter perdido energia no fim de uma viagem**; o **Como corrigir** dele explica a alimentação do comma e a configuração do tempo parado."
related: [live-copy, export-share, live-view]
---

## Reprodução, cópia ao vivo ou ambas

| Gravar gera | O que você recebe |
| --- | --- |
| **Reprodução** (o padrão) | O próprio vídeo do comma com a tela de condução desenhada por cima, gerado depois que você estaciona. A melhor imagem, até 10 minutos por gravação, enquanto o comma ainda tem a viagem. Só as câmeras da via e grande-angular: uma reprodução não tem câmera do motorista. |
| **Cópia ao vivo** | O que o Live View mostra, salvo no seu celular enquanto você dirige e pronto no momento em que você para. Nenhuma reprodução para gerar e sem limite de tempo. [Gravar uma cópia ao vivo](/pt-br/guides/live-copy). |
| **Ambas** | Uma cópia ao vivo agora e a reprodução após a viagem. A reprodução mantém o limite de 10 minutos. |

## Onde as gravações ficam

As gravações ficam no seu celular. **Configurações › Gravações › Armazenamento** mostra o armazenamento usado e o espaço livre, e **Alterar** escolhe outro quando o celular tem. O backup do Android e a transferência para um celular novo as deixam de fora. **Enviar ao CommaView** envia só os dados do próprio comma de uma viagem, e só quando você envia.

## Segurança

Inicie Gravar antes de sair e gere as reproduções depois de estacionar. Não mexa no CommaView enquanto dirige: mantenha os olhos na via e as mãos no volante, como o openpilot pede. O CommaView não é uma câmera veicular nem um sistema de segurança, e uma gravação pode falhar.
