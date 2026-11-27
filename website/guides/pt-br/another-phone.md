---
title: "Adicionar outro celular ou tablet"
description: "Dê a outro celular, tablet ou tela do carro uma chave própria para o seu comma com um convite de 10 minutos, e veja e remova os celulares que têm uma."
topic: start
order: 4
kind: walkthrough
lede: "Cada celular que assiste ao seu comma tem uma chave própria. Para adicionar outro celular, tablet ou tela do carro, mostre um convite em um celular que já tem seu comma e digite ou escaneie no novo. Sem SSH e sem configurar tudo de novo."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Um celular com chave"
    text: "Um celular já emparelhado com seu comma, com o CommaView 0.0.166 ou posterior e o runtime dele. Ainda não? [Configurar o CommaView](/pt-br/guides/setup)."
  - title: "O CommaView no novo"
    text: "Instalado e com a conta conectada, na 0.0.166 ou posterior. [Baixe o app](/pt-br/guides/setup#step-get-the-app)."
  - title: "A mesma rede"
    text: "Os dois no mesmo Wi-Fi que o comma, ou no ponto de acesso dele."
howItWorks:
  - title: "Seu celular"
    text: "Pede um convite ao comma: um código ou um QR code, válido por 10 minutos."
  - title: "O celular novo"
    text: "Entra com o convite e recebe uma chave própria."
    edge: "rede local"
  - title: "Seu comma"
    text: "Avisa a cada celular com chave que um novo recebeu uma."
steps:
  - id: device-settings
    title: "No seu celular, abra Emparelhar outro celular"
    body: |
      No celular que já tem seu comma, abra as **Configurações do dispositivo** do comma pelo Início e depois **Emparelhar outro celular**.
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**Emparelhar outro celular**: um código de curta duração para outro celular ou tablet se conectar."
  - id: show-invitation
    title: "Mostre um convite"
    body: |
      Em **Celulares com chave**, **Adicionar outro celular** mostra um convite para um celular que ainda não tem este comma. Toque em **Mostrar convite**.
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**Mostrar convite**."
      - text: "Os celulares com chave para este comma, este primeiro."
  - id: invitation
    title: "Mantenha o convite na tela"
    body: |
      **Adicionar outro celular** mostra um código em três grupos, um QR code e o endereço IP do comma. Ele vale por 10 minutos e funciona uma vez. Quando expirar, mostre um novo.
    screen: invitation-dialog
    pins:
      - target: code
        text: "O código para digitar no celular novo."
      - target: qr
        text: "Ou o QR code para escanear."
      - text: "**Expira em …**: 10 minutos a partir de quando aparece."
  - id: add-comma
    title: "No celular novo, adicione o comma"
    body: |
      No celular novo, toque em **Emparelhar um comma que já roda o CommaView** em **Conecte seu comma**. Se ele já tiver um comma, toque em **Adicionar um comma** no Início.

      Seu comma aparece em **Nesta rede**. Toque nele, ou toque em **Escanear QR code** e escaneie o convite. Se ele não aparecer, toque em **Digitar endereço e código**.
    screen: add-comma
    pins:
      - target: found-comma
        text: "Seu comma, encontrado nesta rede."
      - target: scan-qr
        text: "**Escanear QR code** para escanear o convite."
      - target: enter-address
        text: "**Digitar endereço e código** quando ele não aparece."
  - id: pair
    title: "Digite o convite e emparelhe"
    body: |
      Confira o **IP do comma**, digite o convite em **Código ou convite** (ou toque no botão de QR para escaneá-lo) e toque em **Emparelhar comma**. O celular novo recebe uma chave própria e mostra seu comma no Início.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**IP do comma**, preenchido para um comma encontrado."
      - target: pair-code
        text: "**Código ou convite**."
      - target: scan-qr
        text: "**Escanear QR de emparelhamento**."
      - target: pair
        text: "**Emparelhar comma**."
  - id: new-key
    title: "Confirme nos seus outros celulares"
    body: |
      Cada celular com chave recebe o aviso **Um celular novo tem chave**, com o nome e quando. Toque em **É meu**. Se não for um dos seus, toque em **Remover**; **Ver celulares** abre **Emparelhar outro celular**, onde todos os celulares com chave aparecem.
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "**É meu**, para o seu próprio celular ou tablet."
      - target: review
        text: "**Ver celulares** lista todos os celulares com chave."
check: "O celular novo mostra seu comma no Início e abre o Live View. No primeiro celular, **Emparelhar outro celular** o lista em **Celulares com chave**."
fixes:
  - q: "“Não foi possível entrar com esse convite”"
    a: "Ele pode ter sido digitado errado, expirado ou já usado. Mostre um novo no celular que já tem este comma (Configurações do dispositivo, **Emparelhar outro celular**, **Adicionar outro celular**)."
  - q: "“O runtime deste comma é anterior às chaves de celular”"
    a: "Atualize primeiro o runtime do comma: [Atualizar o runtime do seu comma](/pt-br/guides/update-runtime). Depois mostre o convite."
  - q: "“Não é possível alcançar este comma”"
    a: "Os dois celulares precisam estar no mesmo Wi-Fi que o comma, ou no ponto de acesso dele. [Conectar no carro](/pt-br/guides/connect-in-the-car)."
  - q: "“Falha no emparelhamento: este comma não emparelha mais por código”"
    a: "O comma parou de aceitar o antigo token compartilhado. Adicione o celular a partir de um que já tenha chave (nas configurações dele, **Adicionar outro celular**) ou faça a configuração do comma de novo."
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## Remover um celular

Em um celular com chave, abra as **Configurações do dispositivo** do comma e depois **Emparelhar outro celular**. Toque em **Remover** ao lado de um celular da lista. Ele não consegue alcançar este comma de novo até ser adicionado outra vez, com um convite ou configurando o comma.

## Celulares com um CommaView mais antigo

Antes da 0.0.166, todos os celulares enviavam ao comma o mesmo token compartilhado. Um celular com a 0.0.166 recebe a chave na próxima vez que se conecta, sem emparelhar de novo.

- **Apps CommaView mais antigos**, em **Emparelhar outro celular**, diz por quantos dias ainda um celular com um CommaView mais antigo pode usar este comma com o token compartilhado: 90 dias depois que o primeiro celular dele recebe uma chave. Até lá, **Código de emparelhamento para um app mais antigo** emparelha um celular com um CommaView mais antigo.
- **Parar agora** faz o comma parar de aceitar o token compartilhado, quando todos os celulares que o usam tiverem chave. Os celulares com um CommaView mais antigo param de funcionar com este comma e não podem emparelhar de novo até serem atualizados.
- Depois disso, um celular sem chave precisa do CommaView 0.0.166 ou posterior e de um convite.

Quando atualizar o runtime do seu comma, atualize antes o CommaView em todos os dispositivos que o assistem, inclusive as telas do carro.
