---
title: "Navegar com sua própria chave do Stadia Maps"
description: "Adicione sua chave do Stadia Maps, busque um lugar no Início, escolha uma rota e siga o cartão de manobras e a orientação por voz no Live View. Envie o lugar ao seu comma também."
topic: navigation
order: 1
kind: walkthrough
lede: "A **Navegação** guia você até um lugar no Live View. Busque o lugar no Início com **Para onde?**, escolha uma rota, toque em **Iniciar** e siga o cartão de manobras e a orientação por voz. As rotas vêm do Stadia Maps com a sua própria chave, que fica protegida no seu celular. A orientação é só visual e nunca controla o carro."
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "Conta conectada"
    text: "CommaView 0.0.167 ou posterior, com a conta da beta conectada. A navegação não aparece fora da conta."
  - title: "Uma chave do Stadia Maps"
    text: "Uma chave de API da sua própria conta do Stadia Maps. As rotas são pedidas na sua conta e sob os termos dela."
  - title: "Localização do veículo ativada"
    text: "A orientação segue o GPS do seu comma. Ative **Localização do veículo** para o seu comma no Início."
  - title: "Internet no celular"
    text: "Para buscas e rotas. Elas usam os dados móveis quando o Wi-Fi do comma não tem internet."
howItWorks:
  - title: "Para onde?"
    text: "Encontra lugares perto do seu comma, com os dados do OpenStreetMap (Photon)."
    edge: "sua chave"
  - title: "Stadia Maps"
    text: "Planeja as rotas, pedidas pelo seu celular com a sua chave. Nada passa pelo CommaView."
  - title: "Live View"
    text: "Guia você a partir da posição do seu comma: o cartão de manobras, o mapa e a orientação por voz."
steps:
  - id: open
    title: "Abra Mapas e navegação"
    body: |
      Toque em **Configurações** e depois em **Mapas e navegação**. Com a conta conectada, é a linha onde antes ficavam os mapas offline.
    screen: support-settings
    pins:
      - target: maps-row
        text: "**Mapas e navegação**."
  - id: get-key
    title: "Obtenha uma chave no Stadia Maps"
    body: |
      Em **Sua chave do Stadia Maps**, **Chave de API** mostra **Não adicionada**. Toque em **Obter uma chave no Stadia Maps**: abre o cadastro do Stadia no navegador. Cadastre-se e copie sua chave de API do painel do Stadia Maps.
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**Sua chave do Stadia Maps**: “As rotas precisam da sua própria chave do Stadia Maps…”"
      - target: get-key
        text: "**Obter uma chave no Stadia Maps** abre o cadastro do Stadia."
      - target: add-key
        text: "**Adicionar**, depois de copiar sua chave."
    note: "O site do Stadia não aparece na imagem: é deles. O painel mostra o uso, o plano e os limites da sua chave."
  - id: add-key
    title: "Cole e toque em Verificar e salvar"
    body: |
      De volta ao CommaView, toque em **Adicionar**. Toque em **Colar** para pôr sua chave no campo e depois em **Verificar e salvar**. Para verificar a chave, o CommaView pede ao Stadia Maps uma rota curta entre dois pontos fixos, nada seu: **Verificando com o Stadia Maps…**. Depois de aceita, **Chave de API** a mostra mascarada, como **•••• e1f0**.
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "**Sua chave de API do Stadia Maps**, mascarada."
      - target: paste
        text: "**Colar** da área de transferência."
      - target: check-and-save
        text: "**Verificar e salvar**."
    note: "“Guardada só neste celular, protegida. Verificada com uma rota curta no Stadia Maps antes de ser guardada.” Ela nunca vai em um pacote de suporte nem em um relatório de falhas."
  - id: where-to
    title: "Toque em Para onde? no Início"
    body: |
      Estacionado, toque em **Para onde?** no Início, abaixo do cartão do seu comma. Digite um lugar ou endereço, ou toque no microfone para falar. Depois de salvos, **Casa** e **Trabalho** ficam a um toque no cartão.
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**Para onde?** abre a busca."
      - target: voice
        text: "**Para onde? por voz**."
      - target: home-chip
        text: "**Casa**, depois de salva."
  - id: pick
    title: "Escolha o lugar"
    body: |
      Os resultados ficam perto do seu comma, cada um com endereço e distância, e depois vêm seus lugares salvos e recentes. Toque no que quiser.
    screen: navigation-search
    pins:
      - target: search-field
        text: "**Buscar lugares ou endereços**."
      - target: first-result
        text: "Um resultado, com o endereço e a distância até o seu comma."
    note: "A digitação fica desativada com o carro em movimento: “A digitação fica desativada com o carro em movimento. Use a voz ou um lugar salvo.”"
  - id: start
    title: "Escolha uma rota e toque em Iniciar"
    body: |
      A prévia da rota mostra a rota em um mapa, o tempo, a distância e a hora de chegada. Cada rota tem um chip: **Mais rápida**, **Rota 2** e assim por diante. Toque em **Iniciar**: a orientação começa e o Live View abre.

      **Salvar como Casa** e **Salvar como Trabalho** deixam o lugar a um toque no Início.
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "As rotas: **Mais rápida**, **Rota 2**…"
      - target: start
        text: "**Iniciar**."
      - target: save-home
        text: "**Salvar como Casa**, e **Salvar como Trabalho** ao lado."
  - id: follow
    title: "Siga no Live View"
    body: |
      O cartão de manobras mostra a próxima manobra: a seta, a distância, a instrução e o passo seguinte, e quando você vai chegar. Um aviso por voz vem cerca de 20 segundos antes de cada manobra, outro logo antes, e um na chegada. Na tela de condução do próprio CommaView, setas são pintadas na sua faixa e na saída da manobra.

      Se você perder uma manobra, uma nova rota chega em segundos. A viagem termina sozinha quando você chega e desliga o carro.
    tabs:
      - label: "Celular"
        body: |
          Na vertical, o cartão de manobras e o mapa ficam abaixo do vídeo.
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "O cartão de manobras."
          - target: end
            text: "**Encerrar navegação**."
          - target: mute
            text: "**Silenciar voz da orientação**."
          - target: map-button
            text: "**Mapa** esconde o mapa durante a viagem e o traz de volta."
      - label: "Tela do carro"
        body: |
          Em uma central multimídia, onde há espaço ao lado do vídeo, o mapa e o cartão de manobras ficam ali, em um painel próprio. Onde não há, a tela do CommaView mescla o mapa no canto do vídeo. Arraste o divisor para mudar a largura do painel.
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "O cartão de manobras."
          - target: divider
            text: "O divisor, para mudar a largura do mapa."
          - target: map-button
            text: "**Mapa**."
    warn: "Prepare a viagem estacionado. Não mexa no CommaView enquanto dirige: o cartão de manobras e a voz estão lá para você não precisar, e os alertas do openpilot e do seu carro vêm primeiro."
  - id: send
    title: "Envie o lugar ao seu comma, se o seu fork aceitar"
    body: |
      Abaixo de **Iniciar**, a prévia da rota tem **Enviar ao comma** para os forks cuja própria navegação aceita um destino: StarPilot, carrotpilot e a navegação (alfa) do openpilot, com a do sunnypilot baseada nela. Outros forks não mostram essa opção.

      Toque nela. O CommaView pergunta antes e diz o que o fork faz na condução com as configurações atuais dele, como reduzir a velocidade nas curvas. Toque em **Enviar**: “Enviado ao seu comma. O StarPilot planeja a própria rota lá.” O fork calcula a rota com o próprio serviço, então ela pode ser diferente da do CommaView. **Apagar do comma** tira o destino de novo, e encerrar a viagem também o apaga.
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**Enviar**."
    note: "**Enviar cada viagem a este comma**, abaixo de Enviar ao comma, envia cada viagem quando você toca em Iniciar. Ele pausa sozinho se as configurações de condução do fork mudarem, até você concordar de novo."
check: "Em **Mapas e navegação**, **Chave de API** mostra sua chave mascarada, e a prévia da rota diz **Rotas por Stadia Maps · A orientação é só visual e nunca controla o carro.**"
fixes:
  - q: "“Adicione sua própria chave do Stadia Maps para obter rotas: Configurações › Mapas e navegação.”"
    a: "Ainda não há chave guardada. Toque em **Adicionar sua chave** na prévia da rota, ou siga [os passos 2 e 3](#step-get-key). Para onde?, a busca e os lugares funcionam sem ela."
  - q: "“O Stadia Maps não aceitou esta chave (401). Verifique se ela foi copiada inteira do seu painel.”"
    a: "Copie a chave de novo do painel do Stadia Maps, inteira, e cole mais uma vez."
  - q: "“Isso não é uma chave do Stadia Maps.”"
    a: "O que você colou não tem formato de chave de API, então nada foi enviado. Copie a chave de API do painel do Stadia Maps: letras, dígitos e hífens."
  - q: "“O Stadia Maps recusou esta chave (403): o plano dela pode não incluir rotas.”"
    a: "Confira seu plano no painel do Stadia Maps."
  - q: "“Sua chave do Stadia Maps está acima do limite (429)”"
    a: "Os créditos deste mês acabaram, ou ela fez pedidos demais agora há pouco. Verifique no painel do Stadia Maps. O app não a usa de novo por cinco minutos."
  - q: "“Não foi possível acessar o Stadia Maps para verificar a chave. Verifique a conexão com a internet deste celular e tente de novo.”"
    a: "Seu celular está sem internet agora. Tente de novo com dados móveis ou um Wi-Fi com internet."
  - q: "Não há **Para onde?** no Início"
    a: "A navegação é para membros com a conta conectada a partir do CommaView 0.0.167. Fora da conta, ou com um passe que não é validado, ela não aparece. Ela não está disponível na China continental."
  - q: "O cartão de manobras diz “Localização do veículo desativada”"
    a: "A orientação precisa da posição do seu comma. Ative **Localização do veículo** para este comma no Início."
  - q: "O cartão de manobras diz “Aguardando GPS”"
    a: "A orientação começa com a primeira posição do seu comma. Dê um tempo a céu aberto."
  - q: "“Longe demais para uma viagem”"
    a: "A navegação planeja rotas para lugares a até 1.500 km (930 milhas). Escolha uma parada no caminho e continue de lá."
  - q: "**Enviar ao comma** não aparece"
    a: "Ele só aparece na prévia da rota, e só para um fork cuja navegação aceita um destino: StarPilot, carrotpilot, ou a navegação (alfa) do openpilot ou do sunnypilot."
  - q: "“Não foi possível alcançar seu comma para enviar esta viagem.”"
    a: "Conecte este celular à mesma rede do seu comma e toque em **Tentar de novo**."
  - q: "“A navegação (alfa) do openpilot está desligada no seu comma.”"
    a: "Toque em **Ligar a navegação (alfa)**, estacionado. Nas versões de lançamento que a desligam toda vez que iniciam, ainda não dá para mantê-la ligada."
related: [live-view, car-screens, overlays]
---

## O mapa no Live View

**Configurações › Mapas e navegação › Mapa do Live View** escolhe onde ele fica:

- **Layout**: **Automático** (ao lado do vídeo onde há espaço, senão no canto), **Ao lado do vídeo** ou **No canto**. As telas comma 3X, comma four, StarPilot e Surround sempre mostram o mapa ao lado do vídeo.
- **Largura ao lado do vídeo** é ajustada arrastando o divisor no Live View. **Redefinir** volta ao padrão.
- **Tema do mapa**: **Igual ao app** (o padrão: claro enquanto o CommaView está claro, escuro enquanto está escuro), **Auto** (claro do nascer ao pôr do sol onde seu comma está), **Igual ao celular**, **Claro** ou **Escuro**. Vale para todos os mapas: o do Live View, o cartão de localização do Início, **Localização do veículo** e a prévia da rota.

## Orientação por voz e seus lugares

- **Orientação por voz** liga e desliga os avisos falados. O alto-falante do cartão de manobras, **Silenciar voz da orientação**, é a mesma configuração.
- **Seus lugares**: **Casa** e **Trabalho**, e **Lugares recentes**, guardados neste celular. **Limpar** apaga os recentes.

## Um lugar de outro app

No Google Maps ou em outro app de mapas, compartilhe um lugar e escolha **Navegar com o CommaView**. A prévia da rota abre no Início, como a de um lugar salvo.

## Mapbox

Se a sua conta oferecer, Configurações › Mapas e navegação pode calcular rotas com seu próprio token do Mapbox em vez do Stadia Maps.

## Privacidade

Sua chave do Stadia Maps fica só neste celular, protegida, e nunca é registrada em logs nem vai em um pacote de suporte. As rotas vão do seu celular ao Stadia Maps com ela; nada vai para o serviço de contas do CommaView. As buscas vão ao Photon, perto da posição do seu comma. Apagar sua chave, ou sair da conta, a remove do celular.

## Segurança

Prepare a viagem estacionado e deixe o cartão de manobras e a voz guiarem você. A navegação é só visual: ela nunca esterça, freia nem muda o que o openpilot faz. Não mexa no CommaView enquanto dirige: mantenha os olhos na via e as mãos no volante, como o openpilot pede.
