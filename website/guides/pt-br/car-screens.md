---
title: "Usar o CommaView em um tablet ou tela do carro"
description: "Leve o Live View a uma tela maior: uma central multimídia Android, uma AI box Android na tela do carro ou um tablet em um suporte. Instalação, rede, emparelhamento e layout."
topic: screens
order: 3
kind: walkthrough
lede: "As telas do comma 3X e do comma four são pequenas. O CommaView mostra o Live View do seu comma em uma maior: uma central multimídia Android, uma AI box Android na própria tela do carro, ou um celular ou tablet em um suporte. A tela do carro roda a própria cópia do CommaView, emparelhada com seu comma."
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 ou posterior"
    text: "Uma central multimídia, AI box, celular ou tablet com Android 8 ou posterior que permita instalar um app."
  - title: "Seu convite"
    text: "O e-mail que recebeu seu convite do CommaView, para entrar em my.commaview.com e no app."
  - title: "O CommaView no seu celular"
    text: "O mais fácil: configure seu comma pelo celular primeiro e depois emparelhe a tela do carro. [Configurar o CommaView](/pt-br/guides/setup)."
howItWorks:
  - title: "Seu comma"
    text: "Envia o Live View por uma rede local, não pela internet."
    edge: "ponto de acesso ou Wi-Fi"
  - title: "A tela do carro"
    text: "Roda o próprio CommaView, emparelhado com seu comma."
steps:
  - id: install
    title: "Instale o CommaView na tela do carro"
    body: |
      Na central multimídia, AI box, celular ou tablet, abra o navegador e entre em [my.commaview.com](https://my.commaview.com) com o e-mail que recebeu seu convite. Em **Get the app**, toque em **Download CommaView**, abra o download e permita instalações pelo navegador para este, depois desative de novo, como no [guia de configuração](/pt-br/guides/setup).

      Abra o CommaView e entre na conta. Durante a beta ele precisa de internet de vez em quando para renovar o passe de acesso, então dê a ele um Wi-Fi com internet pelo menos de vez em quando.
    note: "Algumas centrais multimídia e AI boxes bloqueiam instalações pelo navegador. Baixe o app em um computador, copie para um pendrive e abra pelo gerenciador de arquivos do aparelho."
  - id: network
    title: "Coloque-a na mesma rede que o comma"
    body: |
      O Live View vai direto do comma para a tela do carro por uma rede local. Eles só precisam estar na mesma, e no carro normalmente é um ponto de acesso. Escolha a que liga sozinha quando o carro liga: costuma dar menos trabalho.
    tabs:
      - label: "O ponto de acesso da tela do carro"
        body: "Se a AI box ou a central multimídia pode compartilhar um ponto de acesso (muitas com chip SIM podem), ative-o e conecte o comma a ele em **Configurações › Rede** no comma."
      - label: "O ponto de acesso do seu celular"
        body: "Conecte o comma e a tela do carro ao ponto de acesso do seu celular. Eles também recebem internet por ele."
      - label: "O ponto de acesso do comma"
        body: "Ative o ponto de acesso do comma (o openpilot chama de tethering: em um comma four, **Configurações › Rede › enable tethering**; em um comma 3X, **Configurações › Rede › Avançado › Enable Tethering**) e conecte-se a ele pela tela do carro."
      - label: "Wi-Fi de casa"
        body: "Em casa, os dois no seu Wi-Fi. Prático para configurar, mas acaba quando você sai com o carro."
    note: "Desative qualquer VPN na tela do carro. Alguns pontos de acesso isolam os dispositivos conectados: se a tela do carro não encontrar o comma em um, tente outro. Mais em [Conectar no carro](/pt-br/guides/connect-in-the-car)."
  - id: pair
    title: "Emparelhe com seu comma"
    body: |
      Se seu comma já roda o CommaView a partir do seu celular, emparelhe a tela do carro em vez de configurar de novo. Ela recebe uma chave própria.
    tabs:
      - label: "No seu celular"
        body: |
          Abra as **Configurações do dispositivo** do comma e depois **Emparelhar outro celular**. Em **Adicionar outro celular**, toque em **Mostrar convite**: um código para digitar, ou um QR code, válido por 10 minutos e de uso único.
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**Mostrar convite**."
          - target: this-phone
            text: "Os celulares com chave, este marcado como **Este celular**. A tela do carro se junta a eles."
      - label: "Na tela do carro"
        body: |
          Em **Conecte seu comma**, toque em **Emparelhar um comma que já roda o CommaView** (com um comma já adicionado, abra **Adicionar um comma**). Escolha seu comma e toque em **Digitar o código**, ou em **Escanear QR code**. Se ele não aparecer, toque em **Digitar endereço e código**. Digite o convite em **Código ou convite** e toque em **Emparelhar comma**.
        screen: add-comma
        pins:
          - target: found-comma
            text: "Seu comma, encontrado nesta rede."
          - target: scan-qr
            text: "**Escanear QR code**."
          - target: enter-address
            text: "**Digitar endereço e código**, se ele não aparecer."
    note: "Seu celular então diz **Um celular novo tem chave**. Toque em **É meu**. Todos os passos: [Adicionar outro celular ou tablet](/pt-br/guides/another-phone)."
  - id: fit
    title: "Ajuste à sua tela"
    body: |
      Em uma tela larga, o CommaView se organiza como um painel, com a navegação em uma barra lateral. Deixe o tamanho de texto do aparelho em um que você leia num relance: o CommaView se organiza conforme o espaço que tem nesse tamanho.

      Os controles do Live View ficam do lado do motorista. Em **Auto**, o CommaView segue o lado que seu comma informa; para escolher você mesmo, vá em **Configurações › Tela › Posição do motorista**: **Auto**, **Volante à esquerda** ou **Volante à direita**. Isso espelha os controles em todas as telas.
    tabs:
      - label: "Tablet"
        body: "O Início mostra o carro, sua semana, o mapa e suas viagens lado a lado, com a barra na lateral."
        screen: tablet-home
        pins:
          - target: home-tab
            text: "A barra: **Início**, **Gravações**, **Configurações**."
          - target: open-live-view
            text: "**Abrir o Live View**."
      - label: "Central multimídia"
        body: "O mesmo painel, no tamanho de uma tela de painel do carro."
        screen: car-home
        pins:
          - target: home-tab
            text: "A barra: **Início**, **Gravações**, **Configurações**."
          - target: open-live-view
            text: "**Abrir o Live View**."
      - label: "Por uma AI box"
        body: |
          Alguns carros cortam as bordas da imagem que uma AI box envia, e o Android não tem como saber. Abra **Configurações › Tela › Bordas da tela** e mova cada borda para dentro até ver a linha em toda a volta. Depois confira se o Início, o Live View e as Configurações cabem dentro. **Tema** pode seguir a tela do carro ali: **Igual a este dispositivo**.
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−** e **+** movem cada borda para dentro; **Concluído** salva."
  - id: live-view
    title: "Abra o Live View e confira se ele roda"
    body: |
      Toque em **Abrir o Live View**, com o carro ligado. Os controles ficam em uma barra ao lado da via, do lado do motorista, compacta em uma tela baixa.
    tabs:
      - label: "Tablet"
        body: "**Detalhes** abre em um painel ao lado do vídeo."
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "Detalhes, ao lado do vídeo."
          - target: record-button
            text: "**Gravar**."
          - target: go-live-button
            text: "**Transmitir**."
      - label: "Central multimídia"
        body: "A barra tem Gravar, o seletor de tela de condução, Câm. int., Detalhes e Sair."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Gravar**."
          - target: onroad-screen-button
            text: "O seletor de tela de condução."
          - target: driver-cam-button
            text: "**Câm. int.**"
          - target: details
            text: "**Detalhes**, abaixo de Câm. int."
          - target: exit
            text: "**Sair**."
  - id: auto
    title: "Deixe abrir sozinho"
    body: |
      Em **Configurações › Tela**, em **Abrindo o Live View**:

      - **Abrir o Live View ao conectar** abre o Live View sozinho quando seu comma se conecta com o carro ligado.
      - **Abrir o CommaView quando este dispositivo iniciar**, para uma central multimídia que reinicia com o carro. Uma que entra em suspensão pode ter a própria lista de apps para iniciar.
      - **Abrir o CommaView quando o Bluetooth conectar**: quando o dispositivo que você escolher se conectar, seu carro ou, em uma central multimídia, seu celular.

      Com **Sobrepor a outros apps** permitido, o CommaView abre sozinho. Sem isso, uma notificação oferece abri-lo.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Abrir o Live View ao conectar**."
check: "Com o carro ligado, a tela do carro abre o Live View, a pílula da transmissão mostra **Ao vivo** e todos os controles ficam dentro das bordas da tela."
fixes:
  - q: "Posso usar o CommaView pelo CarPlay ou Android Auto?"
    a: "Não pelo seu celular. O CommaView não é um app de CarPlay nem de Android Auto, e essas plataformas não deixam apps do celular mostrar vídeo com o carro em movimento. Uma AI box Android contorna isso, porque é um dispositivo Android próprio: o CommaView roda na AI box, e o carro mostra a tela dela. Veja [Rodar o CommaView em uma AI box Android](/pt-br/guides/ai-box)."
  - q: "Funciona no Android Automotive de fábrica do meu carro (Google integrado)?"
    a: "Ainda não. Carros com Google integrado só instalam apps da própria Play Store, onde o CommaView não está. Se você tentar de outro jeito, conte como foi."
  - q: "Posso usar uma tela do carro e meu celular com o mesmo comma?"
    a: "Sim: emparelhe cada um com o comma. Só um deles tem o Live View por vez, então feche o Live View no outro primeiro. O Live View diz **O Live View está aberto em outro dispositivo** e começa sozinho quando você volta ao Início no outro."
  - q: "Meu carro corta as bordas da imagem"
    a: "Alguns carros cortam a imagem que uma AI box envia, e o Android não tem como saber. **Configurações › Tela › Bordas da tela** afasta o app de cada borda que você definir."
  - q: "A tela do carro não encontra o comma"
    a: "O CommaView encontra o comma sozinho na mesma rede, mesmo que o endereço mude. Se não encontrar, digite o endereço IP do comma: 192.168.43.1 no ponto de acesso do próprio comma (é o mesmo em todos os commas) ou, em qualquer outra rede, o endereço IP que o comma mostra em **Configurações › Rede**: abaixo do nome da rede no botão de Wi-Fi em um comma four, ou em **Avançado** em um comma 3X."
  - q: "A tela do carro parou de receber vídeo depois de uma atualização do runtime"
    a: "Quando atualizar o runtime do seu comma, atualize antes o CommaView em todos os dispositivos que o assistem, inclusive a tela do carro. Uma tela do carro com um CommaView mais antigo continua funcionando por 90 dias depois que o primeiro celular do comma recebe a chave; depois disso, ela precisa do CommaView 0.0.166 ou posterior e de um convite."
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## O que funciona enquanto você dirige

O CommaView é um app Android, então precisa de um dispositivo Android na sua frente. Qualquer um destes pode rodá-lo enquanto você dirige:

- **Uma central multimídia Android.** Uma central multimídia de reposição com Android 8 ou posterior: o CommaView instala nela como em um celular e roda na tela do carro enquanto você dirige.
- **Uma “AI box” Android.** Um pequeno computador Android que se conecta à porta de CarPlay ou Android Auto com fio do carro e desenha ali a própria tela Android. O CommaView roda na AI box, não no seu celular. Veja [Rodar o CommaView em uma AI box Android](/pt-br/guides/ai-box).
- **Um celular ou tablet em um suporte.** Qualquer celular ou tablet Android, em um suporte de painel ou de saída de ar que não atrapalhe a visão. O caminho mais simples, e o que a maioria das pessoas usa.

Um carro com navegador, como um Tesla, pode mostrar o Live View nele: veja [Mostrar o Live View no navegador do seu carro](/pt-br/guides/browser-view).

## O que não funciona, e por quê

- **CarPlay e Android Auto pelo seu celular.** O CommaView não é um app de CarPlay nem de Android Auto. Essas plataformas não deixam apps do celular mostrar vídeo com o carro em movimento.
- **Vídeo com o carro parado no CarPlay e Android Auto.** A Apple e o Google estão adicionando vídeo para alguns carros, mas só com o carro estacionado, então não dá para mostrar o Live View na estrada.
- **Espelhar o celular no carro.** Adaptadores que espelham a tela de um celular pelo CarPlay ou Android Auto não são compatíveis. Use uma AI box ou central multimídia Android que rode o próprio CommaView.
- **Google integrado (Android Automotive).** Esses carros só instalam apps da própria Play Store, onde o CommaView não está.

## Hardware testado

Telas do carro com que a equipe do CommaView já dirigiu. O CommaView deve rodar em qualquer dispositivo com Android 8 ou posterior, mas estes são os que verificamos:

| Dispositivo | Tipo | O que verificamos |
| --- | --- | --- |
| **Central multimídia Doro** (Qualcomm QCM6125, Android 13, 1280 × 720) | Central multimídia | Live View em trajetos urbanos (outubro de 2026). |
| **Central multimídia Dasaita de 10,2″** (1280 × 720, em um Toyota RAV4) | Central multimídia | Live View dirigindo; envio de gravações, estacionado. |

**Ajude a testar.** Cada tela do carro é diferente. Se você roda o CommaView em uma central multimídia ou AI box, [conte como foi](#conte-sobre-a-sua-tela-do-carro), e vamos incluí-la aqui depois de verificar.

## Conte sobre a sua tela do carro

Envie pela própria tela do carro, para que o relatório leve o modelo e o tamanho da tela:

1. No CommaView da central multimídia ou da AI box, abra **Configurações › Suporte e diagnóstico** e toque em **Relatar um problema ou enviar uma ideia**.
2. Escolha **Ideia** e ative **Este dispositivo: diagnóstico** (uma ideia deixa desativado): ele nos diz a marca, o modelo e o tamanho da tela.
3. Na nota, diga qual é o seu carro, a central multimídia ou AI box (marca e modelo), como está conectada (o ponto de acesso de quem, ou Wi-Fi) e o que funcionou e o que não funcionou. Depois toque em **Enviar**.

Você encontra o que enviou, e nossas respostas, em Your feedback em [my.commaview.com](https://my.commaview.com/feedback). Ainda não está na beta, ou o app não abre? Conte no [Discord do CommaView](https://discord.gg/UuMhz9K8ft).

## Segurança

- Instale, emparelhe e ajuste o layout estacionado. Confira se o Live View roda antes de dirigir.
- Não mexa no CommaView enquanto dirige. Mantenha os olhos na via e as mãos no volante, como o openpilot pede.
- Os alertas do seu comma e os instrumentos do seu carro vêm primeiro. O CommaView só mostra o que o comma vê.
- Instale o celular ou tablet onde ele não atrapalhe a visão nem um airbag, e siga as regras locais sobre telas em carros.
