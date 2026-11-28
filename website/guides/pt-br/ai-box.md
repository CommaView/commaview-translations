---
title: "Rodar o CommaView em uma AI box Android"
description: "Leve o Live View à tela de CarPlay ou Android Auto do seu carro com uma AI box Android: conecte, instale o CommaView, coloque na rede do comma, emparelhe e ajuste."
topic: screens
order: 4
kind: walkthrough
lede: "Se o seu carro tem CarPlay ou Android Auto **com fio** de fábrica, uma **AI box Android** pode levar o Live View do CommaView à própria tela do carro, sem trocar o som e sem fiação. A AI box é um pequeno computador Android que se conecta à porta USB onde você conectaria o celular. O CommaView roda na AI box, então seu celular fica livre para ligações e mapas."
parked: true
updated: 2026-11-27
needs:
  - title: "CarPlay ou Android Auto com fio"
    text: "CarPlay com fio ou Android Auto com fio de fábrica, por uma porta USB que transmita dados. Confira se a AI box aceita o que seu carro tem."
  - title: "Uma AI box com Android de verdade"
    text: "Android 8 ou posterior que permita instalar um app a partir de um arquivo. Caixas fechadas “de vídeo” e simples adaptadores sem fio não rodam o CommaView. [Qual AI box comprar](/blog/android-ai-box-commaview)."
  - title: "O CommaView no seu celular"
    text: "Configure seu comma pelo celular primeiro e depois emparelhe a AI box. [Configurar o CommaView](/pt-br/guides/setup)."
howItWorks:
  - title: "Seu comma"
    text: "Envia o Live View para a AI box por uma rede local."
    edge: "Wi-Fi"
  - title: "AI box"
    text: "Roda o CommaView, como qualquer dispositivo Android."
    edge: "USB"
  - title: "Tela do carro"
    text: "Mostra a tela da AI box, do mesmo jeito que mostra o CarPlay."
steps:
  - id: plug-in
    title: "Conecte a AI box e instale o CommaView"
    body: |
      Conecte a AI box à porta USB de CarPlay ou Android Auto do carro e deixe-a iniciar. Por enquanto, conecte-a a um Wi-Fi com internet.

      No navegador da AI box, entre em [my.commaview.com](https://my.commaview.com) com o e-mail que recebeu seu convite e toque em **Download CommaView** em **Get the app**. Permita instalações pelo navegador só para esta instalação e depois desative de novo. Abra o CommaView e entre na conta.
    note: "Rode o CommaView no modo Android da AI box, não com o CarPlay do seu celular passando por ela."
  - id: network
    title: "Coloque a AI box e o comma na mesma rede"
    body: |
      O Live View vai direto do comma para a AI box por uma rede local, não pela internet, e qualquer rede em que os dois estejam serve.
    tabs:
      - label: "O ponto de acesso da AI box"
        body: "AI boxes com chip SIM normalmente podem compartilhar um ponto de acesso. Ative-o e conecte o comma a ele em **Configurações › Rede** no comma."
      - label: "O ponto de acesso do seu celular"
        body: "Conecte a AI box e o comma ao ponto de acesso do seu celular. Eles também recebem internet por ele."
      - label: "O ponto de acesso do comma"
        body: "Ative o ponto de acesso do comma (o openpilot chama de tethering) e conecte-se a ele pela AI box."
    note: "A maioria das AI boxes também usa o Wi-Fi para conectar seu celular ao CarPlay sem fio, e algumas perdem a internet do Wi-Fi enquanto fazem isso. Desative qualquer VPN na AI box."
  - id: pair
    title: "Emparelhe a AI box com seu comma"
    body: |
      No seu celular, abra as **Configurações do dispositivo** do comma, toque em **Emparelhar outro celular** e, em **Adicionar outro celular**, **Mostrar convite**. Na AI box, toque em **Emparelhar um comma que já roda o CommaView**, escolha seu comma e digite o código ou toque em **Escanear QR code**. Todos os passos: [Usar o CommaView em um tablet ou tela do carro](/pt-br/guides/car-screens#step-pair).
  - id: edges
    title: "Afaste o app das bordas que o carro corta"
    body: |
      Alguns carros cortam as bordas do que a AI box envia, e o Android não tem como saber. Abra **Configurações › Tela › Bordas da tela**. Uma linha marca onde o app termina: mova cada borda para dentro com **−** e **+** até ver a linha em toda a volta, e toque em **Concluído**. **Redefinir** desativa.

      Depois confira se o Início, o Live View e as Configurações cabem dentro.
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−** e **+** movem cada borda para dentro; **Concluído** salva."
      - text: "**Tema**, também em **Configurações › Tela**: **Igual a este dispositivo** segue a AI box."
  - id: auto
    title: "Deixe abrir sozinho"
    body: |
      Em **Configurações › Tela**, em **Abrindo o Live View**:

      - **Abrir o CommaView quando este dispositivo iniciar**, para uma AI box que reinicia com o carro.
      - **Abrir o CommaView quando o Bluetooth conectar**, escolhendo seu celular, para uma AI box que entra em suspensão.
      - **Abrir o Live View ao conectar**, para ir direto ao Live View quando seu comma se conecta com o carro ligado.

      Permita **Sobrepor a outros apps** para o CommaView poder abrir sozinho. Sem isso, uma notificação oferece abri-lo.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Abrir o Live View ao conectar**."
  - id: check
    title: "Confira se o Live View roda e dirija"
    body: |
      Com o carro ligado, abra o Live View na AI box. Os controles ficam em uma barra do lado do motorista, compacta em uma tela baixa. Confira se a imagem roda e se nada está cortado antes de dirigir.
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "**Gravar**, no topo da barra."
      - target: details
        text: "**Detalhes**, mais abaixo na barra."
    note: "A tela da AI box chega ao carro como vídeo, então o Live View é codificado mais uma vez no caminho. Espere uma imagem um pouco mais suave e um pouco mais atrasada do que em um celular na mão."
check: "A tela do carro mostra o Início do CommaView e depois o Live View com a pílula da transmissão mostrando **Ao vivo**, e a linha de **Bordas da tela** aparece em toda a volta."
fixes:
  - q: "A AI box não consegue instalar o CommaView"
    a: "Algumas AI boxes bloqueiam instalações pelo navegador. Baixe o app em um computador, copie para um pendrive e abra pelo gerenciador de arquivos da AI box. Uma AI box com sistema fechado e lista fixa de apps não consegue instalá-lo de jeito nenhum."
  - q: "A AI box não encontra o comma"
    a: "Confira se os dois estão na mesma rede e se a AI box não largou o Wi-Fi por causa do CarPlay sem fio. Digite o endereço IP do comma se precisar: 192.168.43.1 no ponto de acesso do próprio comma. Mais em [Conectar no carro](/pt-br/guides/connect-in-the-car)."
  - q: "A imagem trava ou não roda"
    a: "O comma envia a câmera da via em HEVC (H.265) de 1928 × 1208, e os decodificadores das AI boxes mais baratas podem não dar conta. Se um decodificador falha, o CommaView tenta os outros da AI box sozinho. O Live View diz **Não é possível reproduzir o vídeo deste comma** quando nenhum consegue: envie um relatório de suporte pela AI box."
  - q: "“O Live View está aberto em outro dispositivo”"
    a: "Seu comma transmite para um celular ou central multimídia por vez. Volte ao Início no CommaView do seu celular, e o Live View começa sozinho na AI box."
  - q: "Ainda posso usar o CarPlay do meu celular?"
    a: "Sim. A maioria das AI boxes passa o CarPlay ou Android Auto do seu celular sem fio, e você alterna entre isso e o Android da AI box. O CommaView roda no modo Android da AI box."
  - q: "A AI box precisa de chip SIM?"
    a: "Não para o Live View. Durante a beta, o CommaView precisa de internet de vez em quando para renovar o passe de acesso, o que o Wi-Fi de casa, o ponto de acesso do seu celular ou um chip na AI box fornece."
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## Quatro tipos de “adaptador de CarPlay”

As lojas vendem quatro coisas bem diferentes com o mesmo nome. Só uma roda o CommaView.

| Tipo | O que faz | Roda o CommaView? |
| --- | --- | --- |
| **AI box Android** | Android completo na tela do carro, com apps instalados como em um celular | **Sim** |
| **Caixa fechada “de vídeo”** | Alguns apps de streaming integrados em um sistema bloqueado | Não |
| **Adaptador sem fio** | Deixa o CarPlay ou Android Auto com fio sem fio. Sem Android próprio | Não |
| **Tela portátil de CarPlay** | Uma tela separada para o CarPlay do seu celular, muitas vezes sem Android dentro | Não |

[As melhores AI boxes Android para o CommaView](/blog/android-ai-box-commaview) compara as que valem a compra. Um Tesla não tem CarPlay nem Android Auto: use o [Browser View](/pt-br/guides/browser-view).

Quando atualizar o runtime do seu comma, atualize antes o CommaView na AI box, como em todos os dispositivos que assistem ao seu comma.

## Segurança

Configure a AI box estacionado e depois deixe-a em paz. Não mexa no CommaView enquanto dirige: mantenha os olhos na via e as mãos no volante, como o openpilot pede. Os alertas do seu comma e os instrumentos do seu carro vêm primeiro. O CommaView só mostra o que o comma vê.
