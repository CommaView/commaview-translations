---
title: "Escolher a tela de condução e adicionar pacotes de sobreposição"
description: "Escolha como o Live View desenha a via: a tela do comma four, a do comma 3X ou a do próprio CommaView. Depois adicione um pacote de sobreposição com o que seu fork desenha na própria tela."
topic: screens
order: 6
kind: walkthrough
lede: "O Live View desenha uma tela de condução sobre a câmera da via: a do **comma four**, a do **comma 3X** ou a do próprio **CommaView**. As telas da comma são desenhadas no visual do seu fork. Os **pacotes de sobreposição** acrescentam o que a tela do seu fork desenha e o CommaView não, como os indicadores híbridos do BluePilot ou o caminho arco-íris do dragonpilot."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "O Live View funciona"
    text: "O CommaView em um celular Android, emparelhado com seu comma. Ainda não? [Configurar o CommaView](/pt-br/guides/setup)."
  - title: "Conta conectada, para a loja"
    text: "Membros navegam pelos pacotes do CommaView. Sem entrar na conta, você ainda pode adicionar um pacote a partir de um arquivo ou link."
steps:
  - id: switch
    title: "Troque de tela no Live View"
    body: |
      No Live View, toque no seletor de tela de condução. Ele tem o nome da tela que mostra, e cada toque passa para a próxima: **comma 4**, **comma 3X**, **CommaView**, e começa de novo. A que você deixar escolhida fica guardada para a próxima vez.
    screen: phone-live-view
    clip: onroad-screen
    pins:
      - target: onroad-screen-button
        text: "O seletor de tela de condução, com o nome da tela que mostra."
    note: "Onde não cabe ao lado dos outros controles, ele fica em **Mais**, como **Tela de condução**. Enquanto uma gravação está em andamento, ele fica esmaecido: uma gravação mantém a tela com que começou."
  - id: display
    title: "Ou escolha em Configurações › Tela"
    body: |
      Para ver todas as telas antes de escolher, abra **Configurações › Tela**. O cartão **Tela de condução** mostra uma prévia da tela escolhida sobre uma foto de via, enquadrada pelas câmeras do seu comma e desenhada no visual do seu fork. **Ativado**, **Intervenção** e **Desativado**, abaixo dela, mudam o momento mostrado; não salvam nada.
    screen: settings-display
    pins:
      - target: onroad-screen-card
        text: "A prévia da tela escolhida."
      - target: onroad-screen
        text: "**Tela de condução**: toque para ver a lista."
  - id: pick
    title: "Escolha uma tela"
    body: |
      Cada tela da lista tem uma pequena imagem e uma nota:

      - **comma four**: MÁX acima da via quando muda, o volante e a confiança ao lado.
      - **comma 3X**: uma borda de status, a caixa MÁX, uma velocidade grande e alertas embaixo.
      - **CommaView**: um caminho fluido, uma mira no veículo à frente e a velocidade, o status e os alertas do próprio CommaView.

      Escolher uma salva a escolha e muda a prévia, as opções e o Live View. Qualquer tela funciona nos dois commas.
    screen: settings-display-onroad-screens
    clip: display-pick
    pins:
      - target: comma-four-option
        text: "**comma four**."
      - target: comma-3x-option
        text: "**comma 3X**."
      - target: commaview-option
        text: "**CommaView**."
    note: "Alertas, avisos e o status do monitoramento do motorista sempre usam as cores do próprio comma, qualquer que seja a tela escolhida."
  - id: store
    title: "Abra a loja de pacotes de sobreposição"
    body: |
      Abra **Configurações › Pacotes de sobreposição**, ou toque no cartão **Pacotes de sobreposição** no Início.
    tabs:
      - label: "Conta conectada"
        body: |
          A loja lista primeiro os pacotes **Oficiais** do CommaView e depois os da **Comunidade**, todos revisados pelo CommaView. **Para seu comma** oferece o pacote oficial do fork que seu comma roda. Busque, ou filtre a lista com **Todos**, **Oficiais**, **Comunidade** e **Para meus commas**.
        screen: overlay-packs-store
        pins:
          - target: search
            text: "**Buscar pacotes**."
          - text: "**Para seu comma**: o pacote oficial para o fork do seu comma."
          - target: bluepilot-row
            text: "Os pacotes **Oficiais**, como o BluePilot HUD."
          - target: yours
            text: "**Seus pacotes**: o que está neste celular."
      - label: "De um arquivo ou link"
        body: |
          Alguém compartilhou um arquivo `.cvpack` ou um link (GitHub, um gist, um anexo do Discord)? Abra **Seus pacotes** e, em **Adicionar um pacote você mesmo**, toque em **Instalar de um arquivo** ou **Colar um link**. O CommaView não revisou um pacote adicionado assim, e a caixa de diálogo de instalação avisa isso.
  - id: install
    title: "Instale um pacote"
    body: |
      Toque em um pacote para ver a prévia, os forks em que ele funciona (**Funciona em**) e o que ele acrescenta ao Live View. Toque em **Instalar** e depois em **Instalar** de novo na caixa de diálogo. O pacote vai para este celular e para os seus commas emparelhados.
    screen: overlay-pack-detail
    pins:
      - text: "A prévia: o Live View com o pacote. Toque para ampliar."
      - target: install
        text: "**Instalar**."
    note: "Um pacote oficial só roda nos forks para os quais foi feito. Se nenhum dos seus commas emparelhados roda um deles, a caixa de diálogo avisa; ele instala mesmo assim, mas não aparece no Live View até algum rodar."
  - id: drive
    title: "Veja na próxima viagem"
    body: |
      Depois de instalado, a loja diz que o pacote vai para o seu comma quando este celular o alcançar, e começa a rodar lá quando o carro estiver desligado. Na próxima viagem, abra o Live View: o pacote desenha nas telas comma four, comma 3X e CommaView, abaixo dos alertas da própria tela de condução.

      Para desativar um pacote, abra **Seus pacotes**: cada pacote tem um único botão, para este celular e todos os commas emparelhados juntos.
check: "Nos **Detalhes** do Live View, a linha **Pacotes de sobreposição** mostra o nome do pacote e diz que ele está **rodando**."
fixes:
  - q: "O seletor de tela de condução está esmaecido"
    a: "Há uma gravação em andamento. Pare a gravação, ou espere terminar, e depois troque."
  - q: "Os Detalhes dizem que o pacote “não é para este fork”"
    a: "O pacote foi feito para a tela de outro fork e não desenha nada na sua. Os pacotes oficiais dizem para quais forks são em **Funciona em**."
  - q: "O pacote ainda não aparece no Live View"
    a: "Ele chega ao seu comma quando seu celular se conecta a ele, e começa a rodar lá quando o carro está desligado. Desligue e ligue o carro de novo com o celular na rede do comma e depois abra o Live View."
  - q: "“Entre para ver os pacotes do CommaView”"
    a: "A loja lista os pacotes do CommaView para membros com a conta conectada. Toque em **Entrar**. Os pacotes que já estão no celular continuam funcionando enquanto você está fora da conta."
  - q: "“Não é possível acessar my.commaview.com”"
    a: "Verifique a conexão com a internet deste celular e toque em **Tentar de novo**. **Seus pacotes** continua listando tudo o que está no celular."
related: [live-view, record, forks]
blogPost: commaview-0-0-166-languages-browser-view
---

## As opções de cada tela

Abaixo da prévia, **Configurações › Tela** mostra as opções da tela escolhida:

- **Opções de comma four**: **Enquadramento da prévia** (igualar exatamente o enquadramento do comma four, mostrar mais da câmera ou cortá-la para preencher esta tela) e **Painel de confiança compacto** (um painel e uma bola menores, para mais vídeo).
- **Opções de CommaView**: **Enquadramento da câmera** (**Preencher tela** corta a câmera para preencher uma tela na horizontal; **Câmera inteira** mostra tudo, com faixas pretas onde for preciso) e **Reduzir movimento**, que deixa parados o caminho, a velocidade e a mira do CommaView.
- **comma 3X**: nenhuma. Ela é desenhada como o comma a desenha.

Depois, **Em todas as telas**: **Posição do motorista**, que espelha os controles, **Tema**, **Contraste diurno** para sol e reflexos, e **Bordas da tela** para uma tela do carro que corta as bordas da imagem ([telas do carro](/pt-br/guides/car-screens)).

Uma reprodução que você gera em Gravações desenha o que o Live View desenhava enquanto você gravava, seja lá o que você escolher depois.

## De onde vem uma sobreposição

O CommaView não adivinha o que desenhar. O runtime no seu comma envia, ao lado do vídeo, os mesmos dados de condução que a própria tela do openpilot lê (o caminho, as faixas, o carro à frente, as velocidades, os alertas, o monitoramento do motorista), e o app os desenha no seu celular, alinhados com a câmera que está mostrando. Quando esses dados chegam atrasados, faltam ou são para outra câmera, o CommaView deixa essa parte de fora em vez de desenhar algo que pode estar errado.

## Segurança

Escolha a tela e instale pacotes estacionado. Não mexa no CommaView enquanto dirige: mantenha os olhos na via e as mãos no volante, como o openpilot pede. Uma sobreposição é algo para olhar, não uma ajuda à direção: os alertas do seu comma e os instrumentos do seu carro vêm primeiro. O ícone de monitoramento do motorista não prova atenção, e a sobreposição de uma reprodução serve para rever uma viagem, não como prova do que aconteceu exatamente.
