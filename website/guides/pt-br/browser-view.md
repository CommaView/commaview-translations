---
title: "Mostre o Live View no navegador do seu carro"
description: "O Browser View mostra o Live View do CommaView no próprio navegador do seu carro, inclusive de um Tesla, servido pelo celular via ponto de acesso. Nada para instalar no carro."
topic: screens
order: 2
kind: walkthrough
lede: "O **Browser View** mostra o que o Live View mostra no próprio navegador do seu carro. Seu celular serve a imagem ao carro pelo ponto de acesso ou pelo Wi-Fi, então não há nada para instalar no carro. Ele foi feito para carros como um Tesla, que têm navegador mas não têm CarPlay nem Android Auto, e funciona em qualquer navegador que alcance seu celular."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "O Live View funciona"
    text: "O CommaView em um celular Android, emparelhado com seu comma. Ainda não? [Configurar o CommaView](/pt-br/guides/setup)."
  - title: "Um navegador no carro"
    text: "Um Tesla, outro carro com navegador, ou um tablet ou notebook no carro."
  - title: "Uma só rede"
    text: "O carro e seu comma no ponto de acesso do seu celular, ou em qualquer rede que os três compartilhem."
howItWorks:
  - title: "Seu comma"
    text: "Envia o Live View para o seu celular, como sempre."
  - title: "Seu celular"
    text: "Serve a imagem como uma página web, protegida por um código de oito dígitos."
    edge: "ponto de acesso"
  - title: "O navegador do carro"
    text: "Abre a página: 20 quadros por segundo, 720p ou 1080p, até quatro navegadores."
steps:
  - id: hotspot
    title: "Conecte o carro ao ponto de acesso do seu celular"
    body: |
      Ative o ponto de acesso do seu celular e conecte o carro a ele pelas configurações de Wi-Fi do carro. Confira se o carro entrou no seu celular e não em um Wi-Fi que já conhecia. Conecte também seu comma ao ponto de acesso se ele ainda não estiver: seu celular continua precisando do seu comma, como sempre.
    note: "**Em um Tesla**, desative primeiro o Wi-Fi do seu celular, para que o ponto de acesso compartilhe os dados móveis."
  - id: start
    title: "Inicie o Browser View pelos Detalhes do Live View"
    body: |
      Abra o **Live View** no celular e depois **Detalhes**. Perto do fim, o cartão **Browser View** explica o que ele faz e o que informa ao CommaView. Toque em **Iniciar**.
    screen: live-view-browser-view
    clip: browser-view-start
    pins:
      - target: browser-view-card
        text: "O cartão **Browser View**, perto do fim de **Detalhes**."
      - target: start-button
        text: "**Iniciar**. Na primeira vez, dê ao celular alguns segundos para obter o certificado."
      - target: privacy-policy
        text: "O que o Browser View informa ao CommaView enquanto roda, e a **Política de privacidade**."
  - id: vpn
    title: "Em um Tesla, ative o endereço VPN"
    tabs:
      - label: "Tesla"
        body: |
          O navegador de um Tesla não abre os endereços que um ponto de acesso distribui. No cartão, toque em **Ativar endereço VPN** e permita quando o Android pedir para o CommaView configurar uma VPN. Seu celular recebe um endereço que o Tesla abre, `169.254.99.1`. Ele não carrega tráfego, e qualquer outro app de VPN fica desligado enquanto ele está ativo.
        screen: live-view-browser-view-vpn
        pins:
          - target: short-link
            text: "O link curto, também para o Tesla: **No navegador do carro, inclusive de um Tesla, abra**."
          - target: vpn-address
            text: "Os endereços do celular no endereço VPN, `169.254.99.1`."
        note: "A pergunta do próprio Android sobre a VPN não aparece na imagem: ela é do Android e muda de celular para celular."
      - label: "Outro carro"
        body: |
          Nada a fazer aqui: os navegadores de outros carros abrem o endereço do ponto de acesso. Siga para o próximo passo.
  - id: open
    title: "Digite o link curto no navegador do carro"
    body: |
      O cartão mostra um link curto com seu código de oito dígitos, como `commaview.app/48291374`. Digite-o no navegador do carro e toque em **Abrir**. Com o carro online e o CommaView com a conta conectada, a página encontra seu celular e abre o Live View por uma conexão segura: um cadeado, nenhum aviso e a imagem mais fluida.
    screen: live-view-browser-view-on
    pins:
      - target: short-link
        text: "O link curto para digitar no carro, com seu código."
      - target: show-addresses
        text: "**Sem internet no carro? Mostrar endereços**: os endereços do próprio celular."
      - target: quality
        text: "**Imagem do Browser View**: 720p ou 1080p."
      - target: stop-button
        text: "**Parar** encerra o Browser View."
    warn: "**Sem internet no carro?** O link curto precisa dela. Use o endereço do próprio celular: veja [Sem internet no carro](#sem-internet-no-carro)."
  - id: bookmark
    title: "Salve a página nos favoritos"
    body: |
      O endereço da página não muda, então na próxima vez, com o carro online, abra o favorito em vez de digitar o link curto.
check: "O cartão no celular diz quem está assistindo e o que o navegador do carro desenha, como **1 navegador assistindo** e `Tesla 2025.20.6 · H.264 over HTTPS via the VPN name · 20 fps`."
fixes:
  - q: "“Aguardando o navegador do carro” e nada abre"
    a: "Confira se o carro entrou no ponto de acesso do seu celular, e não em outro Wi-Fi. Em um Tesla, ative o endereço VPN ([passo 3](#step-vpn))."
  - q: "“Ative o ponto de acesso deste celular”"
    a: "O celular não está nem em um Wi-Fi nem em um ponto de acesso que o carro possa compartilhar. O endereço aparece até 5 segundos depois de um dos dois ser ativado."
  - q: "O link curto diz que o endereço VPN está desativado"
    a: "Ative-o no cartão e recarregue a página."
  - q: "Um aviso que não deixa passar"
    a: "Use o link curto com o carro online, ou a imagem básica ([Sem internet no carro](#sem-internet-no-carro))."
  - q: "A imagem para em D"
    a: "Se o navegador de um carro continua desenhando enquanto você dirige depende da montadora. A linha de relatório do cartão diz o que o carro desenha (“0 fps · hidden” é uma imagem que o carro parou). Conte para nós qual é o seu carro e a versão do software dele: ative **Guardar diagnóstico neste celular** antes de dirigir e depois envie **Relatar um problema ou enviar uma ideia** pelas Configurações."
related: [car-screens, ai-box, go-live]
blogPost: commaview-0-0-166-languages-browser-view
---

## Sem internet no carro

O link curto precisa que o carro esteja online para abrir a página, pelos dados móveis do ponto de acesso ou pela própria conexão do carro. Sem isso, abra diretamente o endereço do celular. No cartão, toque em **Sem internet no carro? Mostrar endereços**:

- **Melhor imagem**, um endereço HTTPS como `https://192.168.43.1:8443/48291374`. O navegador avisa primeiro, porque o celular assina esse endereço por conta própria: aceite o aviso para continuar. O navegador de um Tesla não deixa passar.
- **Imagem básica**, o mesmo endereço por HTTP, como `192.168.43.1:8090/48291374`. Nenhum aviso em nenhum navegador, inclusive o de um Tesla, mas uma imagem de qualidade menor e menos fluida.

Com o endereço VPN ativado, o cartão mostra os endereços dele, `https://169.254.99.1:8443/<code>` e `169.254.99.1:8090/<code>`. Em um Tesla sem internet, use o básico.

O endereço do ponto de acesso do seu celular pode ser diferente do exemplo; o cartão sempre mostra o certo, com um botão Copiar ao lado de cada um.

## Opções do cartão

- **Imagem do Browser View: 720p ou 1080p.** 1080p é mais nítida e exige mais do celular e do ponto de acesso. 720p até você escolher.
- **Iniciar com o Live View.** O Browser View inicia toda vez que o Live View abre, com o endereço VPN se estiver ativado. Se você parar, ele fica parado até o Live View abrir de novo.
- **Novo código.** Cria um novo código de oito dígitos, para que um endereço que outra pessoa viu pare de funcionar. Abra o novo endereço no carro.
- **Controles no carro.** Gravar, Salvar momento e os outros controles do Live View ficam abaixo da imagem ou ao lado dela, do lado do motorista, nunca por cima. **Controles no carro** no cartão os desativa.
- **A câmera do motorista** também aparece no carro enquanto **Câm. int.** está ativada no Live View.

## Enquanto roda

- **O Browser View continua com o celular bloqueado** ou em outro app. A notificação diz “Mostrando o Live View no Browser View”, e o **Parar** dela o encerra.
- **Sair do Live View o encerra**, como encerra Transmitir e as cópias ao vivo.
- **Transmitir junto com o Browser View** compartilha a imagem dele. Iniciada enquanto o Browser View roda sozinho, a transmissão fica sem som: pare o Browser View antes para ter som.

## Privacidade e segurança

- A imagem vai só para navegadores no ponto de acesso ou no Wi-Fi do seu celular que tenham o código. Nunca pelos dados móveis, e nunca pelos servidores do CommaView.
- Dez códigos errados em um minuto de um mesmo dispositivo o bloqueiam por um minuto, e um dispositivo que já está assistindo continua.
- Enquanto o Browser View roda, seu celular envia ao serviço de contas do CommaView o código, as portas, se o endereço VPN está ativado e o endereço privado do ponto de acesso ou do Wi-Fi, para que o link curto encontre seu celular. Quem tiver o código pode vê-los, junto com o nome `commaview.app` do seu celular, enquanto o Browser View roda e por até 2 horas depois de ele parar inesperadamente; nenhum deles abre nada sem o ponto de acesso ou o Wi-Fi do seu celular. Eles são excluídos 30 dias depois da última vez que o Browser View rodou. O nome `commaview.app` do seu celular e a data do último certificado dele ficam enquanto sua conta existir. Certificados são públicos, então esse nome fica nos registros de Certificate Transparency; ele não diz nada sobre você, seu carro ou seu comma. [A política de privacidade](/privacy) tem os detalhes.
- O endereço VPN é escolha sua, nunca é ativado sozinho e não carrega tráfego.

## Perguntas

**Preciso de uma AI box ou de uma central multimídia nova?** Não. O Browser View usa o navegador que seu carro já tem. Se o seu carro tem CarPlay ou Android Auto, uma [AI box Android](/blog/android-ai-box-commaview) pode rodar o CommaView na própria tela do carro.

**Ele usa meus dados móveis?** A imagem não: ela vai do celular para o carro pelo ponto de acesso. A página do link curto e o uso que o próprio carro faz do ponto de acesso, sim.

**O ponto de acesso do meu comma pode fazer isso no lugar do celular?** Para a maioria dos navegadores, sim: coloque o celular e o carro no ponto de acesso do comma e abra o endereço que o cartão mostra. Um Tesla precisa do endereço VPN, que só funciona para um carro no ponto de acesso do próprio celular.

## Segurança

Configure o Browser View estacionado e depois deixe-o em paz. Não mexa no CommaView enquanto dirige: mantenha os olhos na via e as mãos no volante, como o openpilot pede. Os alertas do seu comma e os instrumentos do seu carro vêm primeiro. O CommaView só mostra o que o comma vê.
