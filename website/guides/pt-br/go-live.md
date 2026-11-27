---
title: "Transmitir ao vivo no YouTube ou em outro servidor"
description: "Transmita o que o Live View mostra, a via e a tela de condução, para seu canal do YouTube ou qualquer servidor RTMP, em 720p ou 1080p. Configure uma vez e transmita pelo Live View."
topic: screens
order: 5
kind: walkthrough
lede: "**Transmitir** envia o que o Live View mostra, a via e a tela de condução, do seu celular para o seu canal do YouTube ou qualquer servidor RTMP, em 720p ou 1080p. Configure uma vez nas Configurações e depois inicie pelo Live View."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "O Live View funciona"
    text: "O CommaView em um celular Android, emparelhado com seu comma. Ainda não? [Configurar o CommaView](/pt-br/guides/setup)."
  - title: "Um lugar para transmitir"
    text: "Um canal do YouTube para entrar, ou uma chave de transmissão do YouTube Studio ou de outro servidor RTMP."
  - title: "Internet no celular"
    text: "Quando o Wi-Fi do comma não tem internet, a transmissão usa os dados móveis do celular: cerca de 1,4 GB por hora em 720p."
howItWorks:
  - title: "Seu comma"
    text: "Envia o Live View para o seu celular, como sempre."
  - title: "Seu celular"
    text: "Transmite o que o Live View desenha: 20 quadros por segundo, 720p ou 1080p."
    edge: "internet"
  - title: "YouTube ou seu servidor"
    text: "Mostra para quem você deixar assistir."
steps:
  - id: settings
    title: "Abra Configurações › Transmissão ao vivo"
    body: |
      Abra **Configurações** e toque em **Transmissão ao vivo**. Até você configurar, a linha dela mostra **Configurar**.
    screen: support-settings
    pins:
      - target: live-streaming-row
        text: "**Transmissão ao vivo**."
  - id: destination
    title: "Escolha para onde transmitir"
    tabs:
      - label: "Entrar com o YouTube"
        body: |
          Toque em **Entrar com o YouTube**. O login do Google abre no navegador, onde você escolhe a conta e o canal. Com a conta conectada, Transmitir cria cada transmissão no seu canal e o YouTube a inicia sozinho: sem chave de transmissão, sem apertar nada no YouTube Studio. O cartão **Destino** então mostra seu canal, **Conectado**.
        screen: settings-live-streaming
        pins:
          - target: destination-row
            text: "**Destino**: seu canal, conectado."
        note: "As páginas de login do próprio Google não aparecem na imagem."
      - label: "Uma chave de transmissão ou servidor"
        body: |
          Toque em **Usar uma chave de transmissão** (ou **Configurar destino**), escolha a **Plataforma**, **YouTube** ou **Outro servidor**, e cole a chave de transmissão. Para o YouTube: no YouTube Studio, Criar › Transmitir ao vivo › Stream, copie a chave de transmissão e ative ali o início automático, para cada transmissão começar quando o vídeo chegar. Para outro servidor, cole também o endereço `rtmp://` ou `rtmps://`. Toque em **Salvar destino**.
        screen: settings-live-streaming-destination
        pins:
          - target: platform
            text: "**Plataforma**."
          - target: stream-key
            text: "A chave de transmissão. Ela fica só neste celular e só é enviada ao servidor a que pertence."
          - target: save
            text: "**Salvar destino**."
        note: "`rtmp://` envia sua chave de transmissão sem criptografia. Use `rtmps://` se o seu servidor oferecer."
  - id: choices
    title: "Confira quem pode assistir, a qualidade e o som"
    body: |
      - **Quem pode assistir** (com a conta do YouTube conectada): **Público**, **Não listado** ou **Privado**. Começa em **Não listado**. Com uma chave de transmissão, escolha no YouTube Studio. Quem assiste vê por onde você dirige.
      - **Título e descrição** (com a conta do YouTube conectada): o nome de cada transmissão, com chips para a data, o carro e mais.
      - **Qualidade**: 720p ou 1080p, com quantos dados móveis cada uma usa por hora, aproximadamente.
      - **Som**: desativado, a menos que você escolha o microfone do seu comma ou o deste celular. Todos no carro são ouvidos, inclusive passageiros. Ele só vai para a sua transmissão e as suas cópias ao vivo, nunca para o CommaView.

      **Antes de transmitir** resume tudo: uso de dados, a câmera do motorista e quando a transmissão para.
    screen: settings-live-streaming
    pins:
      - text: "**Título e descrição**."
      - target: sound-row
        text: "**Som**."
  - id: go
    title: "Toque em Transmitir no Live View"
    body: |
      Abra o Live View e toque em **Transmitir**. Aparece **Iniciando…** e depois há quanto tempo você está ao vivo. Inicie antes de sair e depois deixe em paz.
    screen: phone-live-view
    pins:
      - target: go-live-button
        text: "**Transmitir**. Onde não cabe, fica em **Mais**."
    warn: "A transmissão mostra a câmera do motorista sempre que **Câm. int.** está ativada, e **Câm. int.** então mostra **Ao vivo**. Desative **Câm. int.** para deixar a câmera do motorista fora da transmissão."
  - id: share
    title: "Compartilhe o link para assistir"
    body: |
      Nos **Detalhes**, a linha da transmissão mostra **Transmitindo** e há quanto tempo, com a taxa enviada, os dados usados e a rede. Com a conta do YouTube conectada, **Compartilhar link**, logo abaixo, compartilha o link `youtu.be` da sua transmissão.
    screen: phone-live-view-go-live
    pins:
      - target: stop-live
        text: "**Transmitir**, ao vivo, com o cronômetro."
      - target: streaming
        text: "**Transmitindo** e há quanto tempo."
      - target: share-watch-link
        text: "**Compartilhar link**."
  - id: stop
    title: "Pare a transmissão depois de estacionar"
    body: |
      Toque em **Transmitir** de novo para parar. A transmissão também para quando você sai do Live View, pelo **Parar** da notificação, e sozinha um minuto depois de o vídeo parar. Ela continua quando você troca de app ou bloqueia o celular.
check: "O **Transmitir** do Live View mostra um cronômetro correndo nas cores de ao vivo, os Detalhes dizem **Transmitindo** e sua transmissão aparece no YouTube ou no seu servidor."
fixes:
  - q: "Não há Transmitir no Live View"
    a: "A transmissão ao vivo ainda não está configurada: os Detalhes dizem **Configure a transmissão ao vivo nas Configurações para transmitir daqui**. Ou ele está em **Mais**, onde nem todos os controles cabem."
  - q: "“Adicione sua chave de transmissão em Configurações › Transmissão ao vivo”"
    a: "Transmitir não tem para onde enviar. Entre com o YouTube, ou adicione uma chave de transmissão, em **Configurações › Transmissão ao vivo**."
  - q: "A transmissão do YouTube não começa com uma chave de transmissão"
    a: "Com uma chave de transmissão, inicie cada transmissão em Transmitir ao vivo no YouTube Studio, ou ative ali o início automático. Com a conta do YouTube conectada, ela começa sozinha."
  - q: "“Essa chave tem um espaço”"
    a: "Copie a chave de novo do seu serviço de transmissão e cole."
  - q: "“Sem som: o Browser View está rodando sem som”"
    a: "Transmitir compartilha a imagem do Browser View, que não tem som. Pare o Browser View antes de transmitir para ter som. O mesmo vale para uma gravação que começou sem som."
  - q: "A transmissão para sozinha"
    a: "O Live View sempre diz o motivo em uma mensagem. Uma transmissão também para um minuto depois de o vídeo parar, e quando você sai do Live View."
related: [live-view, browser-view, live-copy]
blogPost: commaview-0-0-165-go-live-send-to-commaview
---

## Guarde uma cópia de cada transmissão

**Configurações › Gravações › Salvar cada transmissão ao vivo** salva em Gravações um MP4 de cada transmissão, como foi enviada, na qualidade da transmissão. Ele fica no seu celular. Veja [Guardar uma cópia ao vivo](/pt-br/guides/live-copy).

## O que está na transmissão, e o que não está

- **Está:** a via e a tela de condução desenhada por cima, e a câmera do motorista enquanto **Câm. int.** está ativada.
- **Não está:** os controles do Live View, os Detalhes e as mensagens. O mapa da navegação só com **Mapa na transmissão** ativado, onde as Configurações oferecem, e só o mapa do canto do CommaView.
- Gravar e Transmitir são independentes: você pode gravar e transmitir uma viagem ao mesmo tempo.

## Segurança

Configure e inicie Transmitir estacionado e depois deixe em paz. Não mexa no CommaView enquanto dirige: mantenha os olhos na via e as mãos no volante, como o openpilot pede. Quem assiste vê por onde você dirige.
