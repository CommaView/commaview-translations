---
title: "Gravar uma cópia ao vivo do que o Live View mostra"
description: "Uma cópia ao vivo salva no seu celular o que o Live View mostra enquanto você dirige, pronta em Gravações assim que você para, sem limite de 10 minutos. Nunca é enviada."
topic: recordings
order: 2
kind: walkthrough
lede: "Uma **cópia ao vivo** salva no seu celular, enquanto você dirige, o que o Live View mostra: a via e a tela de condução. Ela fica pronta em Gravações no momento em que você para: nenhuma reprodução para gerar e sem limite de 10 minutos. As cópias ao vivo ficam no seu celular e nunca são enviadas."
appVersion: "0.0.164"
parked: true
updated: 2026-11-27
needs:
  - title: "O Live View funciona"
    text: "O CommaView no seu celular, emparelhado com seu comma. Ainda não? [Configurar o CommaView](/pt-br/guides/setup)."
  - title: "Espaço no seu celular"
    text: "Cerca de 1,4 GB por hora em 720p, ou 2,3 GB por hora em 1080p. Uma cópia ao vivo sempre deixa 500 MB livres."
howItWorks:
  - title: "Live View"
    text: "Desenha a via e a tela de condução, como sempre."
    edge: "enquanto você dirige"
  - title: "Seu celular"
    text: "Codifica o que o Live View desenha em um MP4, a 20 quadros por segundo."
  - title: "Gravações"
    text: "A cópia fica pronta no momento em que você para."
steps:
  - id: choose
    title: "Escolha Cópia ao vivo ou Ambas"
    body: |
      Toque em **Configurações** e depois em **Gravações**. Em **Gravar no Live View**, escolha o que Gravar gera. A escolha é salva na hora.
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Gravar no Live View**: **Reprodução**, **Cópia ao vivo** ou **Ambas**."
    tabs:
      - label: "Cópia ao vivo"
        body: |
          “O que o Live View mostra, pronta no momento em que você para. Nenhuma reprodução para gerar e sem limite de tempo.”
      - label: "Ambas"
        body: |
          “Uma cópia ao vivo agora e a reprodução após a viagem. A reprodução mantém o limite de 10 minutos.” A reprodução é gerada depois que você estaciona, como mostra [Gravar uma viagem](/pt-br/guides/record).
  - id: quality
    title: "Escolha a qualidade e o som"
    body: |
      Com uma cópia ao vivo escolhida, a página acrescenta as linhas dela. **Qualidade da cópia ao vivo** é **720p** até você escolher **1080p**. **Som** fica desativado, a menos que você escolha um microfone: o do comma ou o deste celular. É o mesmo Som de Configurações › Transmissão ao vivo.
    screen: settings-recordings
    pins:
      - text: "**Qualidade da cópia ao vivo**: 720p (cerca de 1,4 GB por hora) ou 1080p (cerca de 2,3 GB por hora)."
      - text: "**Som**: desativado, o microfone do comma ou o deste celular."
    note: "Uma cópia ao vivo mostra o que o Live View mostra, inclusive a miniatura da câmera do motorista enquanto **Câm. int.** está ativada. Desative Câm. int. no Live View para deixar a câmera do motorista de fora."
  - id: record
    title: "Toque em Gravar no Live View"
    body: |
      Com o carro ligado e ainda em P, abra o **Live View** e toque em **Gravar**. O cronômetro corre, e **Detalhes** mostra **Gravando ·** e o tempo, como em qualquer gravação. Toque em Gravar de novo para parar.

      A gravação continua enquanto você troca de app ou bloqueia o celular, com uma notificação, **Gravando uma cópia ao vivo**, que tem o cronômetro e **Parar**. Fechar o Live View a encerra.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Gravar, com o cronômetro. Toque de novo para parar."
      - target: recording
        text: "**Gravando ·** o tempo, em **Detalhes**."
    warn: "Comece a gravar antes de sair, ou deixe um passageiro cuidar disso. Não mexa no CommaView enquanto dirige."
  - id: find
    title: "Encontre em Gravações"
    body: |
      Abra **Gravações**. A cópia aparece marcada como **Cópia ao vivo**, sob o dia, com a duração e o tamanho. Por um momento depois de parar, ela mostra **Salvando a cópia ao vivo…** com o progresso; depois ela roda.

      Com **Ambas**, a viagem tem duas linhas: a cópia ao vivo e a reprodução, que espera você gerá-la depois de estacionar.
    screen: phone-recordings
    pins:
      - target: live-copy-row
        text: "A linha marcada como **Cópia ao vivo**."
      - text: "Com **Ambas**, a reprodução da viagem, em uma linha própria."
  - id: watch
    title: "Assista, compartilhe ou exclua"
    body: |
      Toque na cópia para assistir. Os dados dela incluem **Versão** (**Cópia ao vivo**, ou **Cópia ao vivo · e uma reprodução** com Ambas), **Qualidade** e **Som**. **Ações da gravação** tem **Compartilhar**, **Abrir em outro app**, **Selecionar** e **Excluir**.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Ações da gravação**: Compartilhar, Abrir em outro app, Selecionar e Excluir."
      - text: "**Tela cheia**."
check: "A cópia roda em Gravações assim que é salva, e a **Versão** da tela de reprodução mostra **Cópia ao vivo**."
fixes:
  - q: "“Espaço insuficiente para uma cópia ao vivo: ela sempre deixa 500 MB livres neste celular. Exclua viagens de que não precisa mais em Gravações.”"
    a: "Exclua viagens de que não precisa mais, ou escolha outro armazenamento em **Configurações › Gravações › Armazenamento**. O cartão Armazenamento diz aproximadamente quantas horas de cópias ao vivo cabem."
  - q: "“Cópia ao vivo parada: este celular está quase cheio. Ela está salva em Gravações; sempre deixa 500 MB livres.”"
    a: "O que foi gravado fica guardado. Libere espaço antes da próxima viagem."
  - q: "“Cópia ao vivo parada: nenhum vídeo do comma por um minuto. O que foi gravado está salvo em Gravações.”"
    a: "O celular perdeu o comma por um minuto, então a cópia terminou. Confira se o celular continua no Wi-Fi ou ponto de acesso do comma. Veja [O CommaView não encontra seu comma](/pt-br/guides/comma-not-found)."
  - q: "“Esta cópia ao vivo atingiu 3,5 GB, o máximo de um arquivo: ela continua em uma nova em Gravações.”"
    a: "Nada se perde: a viagem continua em uma segunda cópia ao vivo, em uma linha própria em Gravações."
  - q: "“A reprodução parou no limite de 10 minutos. A cópia ao vivo continua gravando.”"
    a: "Com **Ambas**, só a reprodução para aos 10 minutos. A cópia ao vivo continua até você parar."
  - q: "“Gravando só uma cópia ao vivo. A reprodução não pôde iniciar: …”"
    a: "Com **Ambas**, a cópia grava mesmo quando a parte da reprodução não consegue, por exemplo enquanto o comma precisa reiniciar ou este celular não está emparelhado com ele. A mensagem diz o motivo."
  - q: "A linha mostra “Requer 1,2 GB livres para salvar”"
    a: "As partes da cópia ficam guardadas até haver espaço para juntá-las em um só vídeo. Exclua viagens de que não precisa mais, e ela salva sozinha."
  - q: "O dado **Salva** mostra “Recuperada depois que o app fechou: o último minuto pode estar faltando”"
    a: "O app fechou durante a gravação, então a cópia foi montada com o que foi gravado: tudo, menos até o último minuto."
  - q: "“O CommaView só consegue continuar transmitindo e gravando enquanto está na tela: o Android não permitiu que ele rodasse em segundo plano.”"
    a: "O Android impediu o CommaView de rodar em segundo plano. Mantenha o Live View na tela enquanto grava."
related: [record, export-share, go-live]
blogPost: commaview-0-0-164-carrotpilot-teslahw1-live-copies
---

## Cópia ao vivo ou reprodução

| | Cópia ao vivo | Reprodução |
| --- | --- | --- |
| O que mostra | O que o Live View mostrou, como mostrou | O próprio vídeo do comma, com a tela de condução desenhada por cima |
| Quando fica pronta | No momento em que você para | Depois de estacionar e tocar em **Gerar reprodução** |
| Duração | Sem limite além do armazenamento | Até 10 minutos por gravação |
| Imagem | 720p ou 1080p, 20 quadros por segundo | A melhor imagem: **Balanced**, **High** ou **Max** |

## Enquanto você está ao vivo

Uma cópia ao vivo e [Transmitir](/pt-br/guides/go-live) compartilham um mesmo codificador. Uma cópia iniciada durante a transmissão tem a qualidade da transmissão. **Salvar cada transmissão ao vivo**, em Configurações › Gravações, guarda um MP4 de cada transmissão, como foi enviada, sem Gravar.

## Privacidade

As cópias ao vivo ficam no seu celular. Elas nunca são enviadas nem compartilhadas com os outros celulares emparelhados com o comma. **Enviar ao CommaView** envia os dados do próprio comma de uma viagem, nunca uma cópia ao vivo. O som só entra em uma cópia quando você escolheu um microfone, e a câmera do motorista só enquanto Câm. int. está ativada.

## Segurança

Escolha as configurações e inicie Gravar estacionado. Não mexa no CommaView enquanto dirige: mantenha os olhos na via e as mãos no volante, como o openpilot pede.
