---
title: "Assista ao seu comma no Live View"
description: "Abra o Live View para ver no celular a câmera da via do seu comma e a tela de condução dele, e conheça os controles, os Detalhes e o que ele diz quando algo dá errado."
topic: screens
order: 1
kind: walkthrough
lede: "O **Live View** mostra ao vivo a câmera da via do seu comma, com a tela de condução desenhada por cima: a do comma four, a do comma 3X ou a do próprio CommaView. Ela vem direto do comma pela sua própria rede, não pela internet."
parked: true
updated: 2026-11-27
needs:
  - title: "O CommaView está configurado"
    text: "O CommaView em um celular Android, emparelhado com seu comma. Ainda não? [Configurar o CommaView](/pt-br/guides/setup)."
  - title: "O carro está ligado"
    text: "O openpilot só envia vídeo em movimento. Com o carro desligado, o Live View espera e começa sozinho quando o carro liga."
  - title: "Uma só rede"
    text: "Seu celular e seu comma no mesmo Wi-Fi ou ponto de acesso. No carro, veja [Conectar no carro](/pt-br/guides/connect-in-the-car)."
steps:
  - id: open
    title: "Abra o Live View pelo Início"
    body: |
      No **Início**, com seu comma conectado e o carro ligado, toque em **Abrir o Live View**. A via aparece em poucos segundos, com a pílula da transmissão mostrando **Ao vivo**.
    screen: phone-home
    pins:
      - target: open-live-view
        text: "**Abrir o Live View**, o botão principal do Início."
    note: "Com o carro desligado, o Live View diz **Seu comma está online, mas parado**. Ele começa sozinho quando o carro liga, ou na hora com **Atualizar**."
  - id: controls
    title: "Conheça os controles abaixo da imagem"
    body: |
      Com o celular na vertical, os controles ficam abaixo do vídeo:

      - **Gravar** salva este trecho da viagem. Veja [Gravar uma viagem](/pt-br/guides/record).
      - **Salvar** guarda os últimos 3 minutos e o próximo minuto da viagem.
      - O seletor de tela de condução, com o nome da tela que mostra (**CommaView**, **comma 4**, **comma 3X**), passa para a próxima a cada toque. Veja [Escolher a tela de condução](/pt-br/guides/overlays).
      - **Transmitir** transmite o que o Live View mostra, depois de configurado. Veja [Transmitir ao vivo](/pt-br/guides/go-live).
      - **Câm. int.** mostra a câmera do motorista em um canto da imagem.
      - **Detalhes** abre os dados e os cartões do Live View.

      O que não couber na largura e no tamanho de texto do seu celular vai para **Mais**. Nada é encolhido ou cortado.
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**Gravar**."
      - target: onroad-screen-button
        text: "O seletor de tela de condução."
      - target: driver-cam-button
        text: "**Câm. int.**"
      - target: go-live-button
        text: "**Transmitir**, depois que a transmissão ao vivo estiver configurada."
      - text: "**Mais** guarda o que não cabe."
    note: "Enquanto uma gravação está em andamento, o seletor de tela de condução e **Câm. int.** ficam esmaecidos: escolha antes de tocar em **Gravar**."
  - id: details
    title: "Abra os Detalhes"
    body: |
      Toque em **Detalhes**, ou puxe a folha da parte de baixo da tela. Ela mostra como está a transmissão, o vídeo, o runtime, o software do seu comma e o endereço dele, se você está gravando ou transmitindo, e o cartão **Browser View**. Os links abrem **Gravações** e as **Configurações do dispositivo** do seu comma.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "A folha **Detalhes**."
      - text: "O resumo: a saúde da transmissão, o vídeo e o runtime."
      - target: recordings-link
        text: "**Gravações**."
      - target: device-settings-link
        text: "**Configurações do dispositivo** deste comma."
  - id: turn
    title: "Gire o celular ou use uma tela maior"
    body: |
      Vire o celular de lado e o vídeo ocupa a tela, com os controles em uma barra do lado do motorista. **Detalhes** abre ao lado da imagem, e **Sair** fecha o Live View.
    tabs:
      - label: "Celular de lado"
        body: "A barra tem os mesmos controles. Em uma tela baixa, ela fica compacta."
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "**Gravar**, no topo da barra."
          - target: more
            text: "**Mais** contém **Câm. int.** e **Detalhes**."
          - target: exit
            text: "**Sair** fecha o Live View."
      - label: "Tablet ou tela do carro"
        body: "Em uma tela larga, a barra fica do lado do motorista. Veja [Usar o CommaView em uma tela do carro](/pt-br/guides/car-screens)."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Gravar**."
          - target: onroad-screen-button
            text: "O seletor de tela de condução."
          - target: driver-cam-button
            text: "**Câm. int.**"
          - target: details
            text: "**Detalhes**."
          - target: exit
            text: "**Sair**."
  - id: auto
    title: "Deixe o Live View abrir sozinho"
    body: |
      Para um celular ou central multimídia que só está ali para mostrar o Live View, abra **Configurações › Tela** e ative **Abrir o Live View ao conectar**, em **Abrindo o Live View**. O Live View então abre sozinho quando seu comma se conecta com o carro ligado. Se você o fechar, ele fica fechado até a próxima vez.

      **Manter a barra de status**, logo abaixo, mostra o relógio do sistema acima do Live View em vez de usar a tela inteira.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Abrir o Live View ao conectar**."
  - id: leave
    title: "Saia do Live View quando terminar"
    body: |
      Toque em **Sair**, ou em voltar, depois de estacionar. Sair do Live View também encerra Transmitir, o Browser View e as cópias ao vivo. O Live View fica aberto em um celular ou central multimídia por vez, então feche em um antes de abrir em outro.
check: "A pílula da transmissão mostra **Ao vivo**, a via se move e a saúde da transmissão nos Detalhes diz **Boa**."
fixes:
  - q: "“Seu comma está online, mas parado”"
    a: "O carro está desligado ou o openpilot não iniciou. O Live View volta sozinho até 30 segundos depois de o carro ligar, ou toque em **Atualizar**."
  - q: "“Não é possível alcançar este comma”"
    a: "Seu celular precisa estar no mesmo Wi-Fi que o comma, ou no ponto de acesso dele. O Live View se reconecta quando o comma responde, ou toque em **Tentar de novo**. Ainda nada? Veja [O CommaView não encontra seu comma](/pt-br/guides/comma-not-found)."
  - q: "“O Live View está aberto em outro dispositivo”"
    a: "Seu comma transmite para um celular ou central multimídia por vez. Volte ao Início no CommaView do outro dispositivo, e o Live View começa aqui sozinho."
  - q: "“Os dados do carro não estão chegando”"
    a: "O vídeo chega, mas a velocidade, as setas e os alertas do carro não. Reinicie o comma para resolver."
  - q: "“Vídeo com atraso”"
    a: "Nenhum quadro novo chegou em um segundo. O Live View avisa ao lado da imagem e se reconecta sozinho se o vídeo não voltar."
  - q: "“Não é possível reproduzir o vídeo deste comma”"
    a: "Nenhum dos decodificadores de vídeo do celular conseguiu reproduzi-lo. O CommaView continua tentando. Envie um relatório de suporte pelas Configurações para o CommaView investigar: veja [Enviar um relatório de suporte](/pt-br/guides/support-bundle)."
related: [overlays, record, browser-view, car-screens]
---

## Segurança

Abra o Live View estacionado e depois deixe-o em paz. Não mexa no CommaView enquanto dirige: mantenha os olhos na via e as mãos no volante, como o openpilot pede. Os alertas do seu comma e os instrumentos do seu carro vêm primeiro. O CommaView só mostra o que o comma vê.
