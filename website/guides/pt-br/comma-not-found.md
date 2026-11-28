---
title: "O CommaView não encontra seu comma"
description: "O Início mostra Offline ou o Live View não alcança seu comma? Verifique a rede, o endereço do comma e o emparelhamento, nessa ordem."
topic: troubleshooting
order: 2
kind: fixes
lede: "O CommaView fala com seu comma diretamente pela sua rede local, sem nenhum serviço de nuvem no meio. Quando ele não o encontra, quase sempre o celular e o comma estão em redes diferentes, o comma está dormindo com o carro desligado ou o endereço dele mudou. Verifique isso primeiro e depois o emparelhamento."
parked: true
updated: 2026-11-27
needs:
  - title: "O carro ligado"
    text: "O comma dorme quando o carro está desligado. Ligue o carro, em P."
  - title: "Uma só rede"
    text: "Seu celular no mesmo Wi-Fi que o comma, ou no ponto de acesso dele. No carro: [conectar no carro](/pt-br/guides/connect-in-the-car)."
steps:
  - id: home
    title: "Veja o que o Início diz"
    body: |
      Quando seu celular não alcança o comma, o Início o mostra **Offline**, com **Reconectar**, e um cartão **Não conecta?**: “Seu celular precisa estar no mesmo Wi-Fi que o comma ou no ponto de acesso dele. O comma dorme quando o carro está desligado.”

      Verifique as duas coisas e toque em **Reconectar**.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Reconectar**."
      - target: cant-connect
        text: "O cartão **Não conecta?**."
  - id: live-view
    title: "No Live View: espere ou tente de novo"
    body: |
      O Live View diz por que parou. **Não é possível alcançar este comma** significa que seu celular não o alcança na rede. Ele se reconecta sozinho quando o comma responde; **Tentar de novo** tenta agora.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**Não é possível alcançar este comma**: por que o Live View parou."
      - target: retry
        text: "**Tentar de novo**."
  - id: network
    title: "Verifique a rede do seu celular"
    body: |
      Abra as configurações de Wi-Fi do celular e confira se ele está na rede em que o comma está: o mesmo Wi-Fi de casa, o ponto de acesso do seu celular com o comma conectado, ou o ponto de acesso do próprio comma.

      - Um celular que saiu de um Wi-Fi sem internet para usar dados móveis não alcança o comma. Conecte de novo.
      - Uma VPN no celular pode mandar o tráfego para outro lugar. Desative e tente de novo.
      - Alguns pontos de acesso impedem que os dispositivos conectados se alcancem. Tente outra rede, como o ponto de acesso do próprio comma.
    note: "As configurações de Wi-Fi e de ponto de acesso do Android não aparecem na imagem: elas mudam de celular para celular."
  - id: address
    title: "Verifique o endereço do comma"
    body: |
      O comma recebe um endereço novo quando entra em outra rede, ou quando um roteador lhe dá outro. O CommaView o encontra de novo sozinho quando o vê na rede; se não encontrar, salve o endereço você mesmo.

      No comma, encontre o endereço IP em **Configurações → Rede**. No CommaView, abra as **Configurações do dispositivo** pelo Início, toque em **Alterar o nome ou o endereço**, edite **Endereço IP**, digite o endereço do comma e toque em **Salvar**.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "O endereço IP do comma."
      - target: save
        text: "**Salvar**."
  - id: add
    title: "Ainda não encontrou? Adicione de novo"
    body: |
      No Início, toque em **Adicionar um comma**. **Nesta rede** lista os commas que rodam o CommaView na rede do seu celular: toque no seu. Se ele não estiver lá, toque em **Digitar endereço e código**, ou em **Escanear QR code** em um celular já emparelhado com ele.
    screen: add-comma
    pins:
      - target: found-comma
        text: "**Nesta rede**: um comma encontrado por perto."
      - target: enter-address
        text: "**Digitar endereço e código**."
      - target: scan-qr
        text: "**Escanear QR code**."
  - id: pair
    title: "Emparelhe com o endereço e um código novo"
    body: |
      Digite o IP do comma e um código de emparelhamento ou um convite, e toque em **Emparelhar comma**. Os códigos expiram rápido: um celular já emparelhado com o comma mostra um novo nas **Configurações do dispositivo**, em **Emparelhar outro celular ou tablet**.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "O IP do comma."
      - target: pair-code
        text: "**Código ou convite**."
      - target: pair
        text: "**Emparelhar comma**."
    note: "Se digitar o endereço funciona mas o comma nunca aparece sozinho, a rede está escondendo a descoberta do CommaView. Tudo bem: o que importa é o endereço."
check: "O Início mostra seu comma **Conectado**, e **Abrir o Live View** abre a imagem."
fixes:
  - q: "“Não é possível alcançar este comma”"
    a: "Seu celular precisa estar no mesmo Wi-Fi que o comma, ou no ponto de acesso dele. O Live View se reconecta quando ele responde. Verifique a rede ([passo 3](#step-network)) e o endereço do comma ([passo 4](#step-address))."
  - q: "“O CommaView não está respondendo”"
    a: "O comma responde, mas o CommaView nele não. Ele pode estar reiniciando no comma: o Live View se reconecta quando ele voltar. Se continuar assim, reinicie o comma, estacionado."
  - q: "“Sem vídeo deste comma”"
    a: "Ele responde, mas o vídeo não voltou. Tente de novo, ou volte e verifique o comma: o openpilot pode ainda estar iniciando."
  - q: "“O Live View está aberto em outro dispositivo”"
    a: "Este comma transmite para um celular ou central multimídia por vez. Volte ao Início no CommaView do outro dispositivo, e o Live View começa aqui sozinho."
  - q: "“O comma não respondeu a tempo.”"
    a: "Uma conexão fraca ou congestionada. Confira se o celular está no Wi-Fi ou ponto de acesso do comma, mais perto dele se puder, e tente de novo."
  - q: "“O comma recusou a conexão. O CommaView pode estar reiniciando nele.”"
    a: "Espere um momento até ele voltar e tente de novo."
  - q: "“Os dados do carro não estão chegando”"
    a: "O vídeo chega, mas a velocidade, as setas e os alertas do carro não. Reinicie o comma para resolver."
  - q: "“Falha no emparelhamento: o código expirou. Gere um código novo e tente de novo.”"
    a: "Pegue um código novo em um celular já emparelhado com o comma, em **Configurações do dispositivo › Emparelhar outro celular ou tablet**, e emparelhe de novo."
  - q: "“Falha no emparelhamento: código inválido. Verifique o código ou escaneie o QR.”"
    a: "Confira o código que digitou (os hífens são opcionais), ou escaneie o QR code dele."
  - q: "“Atualize o runtime deste comma” ou “Atualize o CommaView”"
    a: "Este app e o runtime do comma estão distantes demais para conversar. Atualize o que a mensagem indicar: o runtime pelas Configurações do dispositivo ([Atualizar o runtime](/pt-br/guides/update-runtime)), ou o app."
  - q: "“Não é possível ler seus commas salvos”"
    a: "Os commas salvos neste celular não puderam ser lidos, então nenhum é mostrado. Eles não foram excluídos. Tente de novo, ou toque em **Recomeçar** e emparelhe cada comma de novo: a lista antiga fica guardada por pelo menos 90 dias."
related: [connect-in-the-car, setup-troubleshooting, another-phone]
---

## Como o CommaView encontra um comma

- **A descoberta** encontra os commas que rodam o CommaView na rede do seu celular, para você não precisar digitar endereços. Algumas redes a bloqueiam.
- **O endereço** é aquilo a que o CommaView se conecta. Digitá-lo funciona com ou sem a descoberta.
- **O emparelhamento** dá ao seu celular uma chave própria para o comma, com um código de curta duração. Descoberta e emparelhamento são coisas separadas: um comma que seu celular alcança ainda precisa ser emparelhado.
- **Um comma salvo** é reconhecido pela identidade, não só pelo endereço, então quando ele aparece em um endereço novo o CommaView atualiza o salvo.

## Segurança

Verifique as redes e emparelhe estacionado. Não mexa no CommaView enquanto dirige.
