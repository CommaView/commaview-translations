---
title: "Conectar no carro sem o Wi-Fi de casa"
description: "Coloque seu celular e seu comma em uma mesma rede no carro: o ponto de acesso do celular, o do comma ou o de uma tela do carro, e o que fazer quando o CommaView não alcança o comma."
topic: start
order: 3
kind: walkthrough
lede: "O Live View vai direto do comma para o seu celular por uma rede local, não pela internet. Para o CommaView tanto faz de quem é a rede: seu celular e o comma só precisam estar na mesma. No carro, normalmente é um ponto de acesso."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView configurado"
    text: "Seu comma emparelhado com este celular. Ainda não? [Configurar o CommaView](/pt-br/guides/setup)."
  - title: "Sem VPN"
    text: "Desative qualquer VPN no celular ou na tela do carro enquanto usa o CommaView."
howItWorks:
  - title: "Seu comma"
    text: "Oferece o Live View e as gravações na rede em que está."
    edge: "um ponto de acesso"
  - title: "Seu celular"
    text: "Encontra o comma sozinho nessa rede, mesmo que o endereço mude."
steps:
  - id: network
    title: "Coloque o celular e o comma em uma mesma rede"
    body: |
      Escolha a que combina com seu carro: a que liga sozinha quando o carro liga costuma dar menos trabalho. Você conecta o comma a uma rede pela própria tela dele, em **Configurações › Rede**.
    tabs:
      - label: "O ponto de acesso do seu celular"
        body: "Ative o ponto de acesso do seu celular e conecte o comma a ele. O CommaView no mesmo celular alcança o comma por ele, e o comma também recebe internet por ele."
      - label: "O ponto de acesso do comma"
        body: "Ative o ponto de acesso do comma (o openpilot chama de tethering: em um comma four, **Configurações › Rede › enable tethering**; em um comma 3X, **Configurações › Rede › Avançado › Enable Tethering**) e conecte-se a ele pelas configurações de Wi-Fi do celular. O ponto de acesso do comma não tem internet."
      - label: "O ponto de acesso de uma tela do carro"
        body: "Se uma AI box ou central multimídia pode compartilhar um ponto de acesso (muitas com chip SIM podem), ative-o e conecte o comma a ele, e seu celular, se você usar um. [Telas do carro](/pt-br/guides/car-screens) tem mais detalhes."
    note: "Alguns pontos de acesso isolam os dispositivos conectados. Se o CommaView não encontrar o comma em um, tente outro."
  - id: home
    title: "Abra o CommaView"
    body: |
      O Início mostra seu comma **Conectado** assim que ele responde na nova rede: o CommaView o encontra sozinho, mesmo em um endereço novo. O comma dorme quando o carro está desligado, então ligue o carro primeiro.

      Se o Início mostrar o comma offline com **Não conecta?**, verifique se o celular está no mesmo Wi-Fi que o comma, ou no ponto de acesso dele, e toque em **Reconectar**.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**Reconectar** tenta o comma de novo."
      - target: cant-connect
        text: "**Não conecta?** diz do que o celular precisa: o mesmo Wi-Fi que o comma, ou o ponto de acesso dele."
  - id: address
    title: "Se ainda não encontrar, digite o endereço"
    body: |
      Abra as **Configurações do dispositivo** do comma, depois **Nome e endereço**, e edite o endereço IP. No ponto de acesso do próprio comma é **192.168.43.1** (é o mesmo em todos os commas). Em qualquer outra rede, é o endereço que o comma mostra em **Configurações › Rede**: abaixo do nome da rede no botão de Wi-Fi em um comma four, ou em **Avançado** em um comma 3X. Toque em **Salvar**.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "O endereço IP do comma nesta rede."
      - target: save
        text: "**Salvar**."
  - id: live-view
    title: "Abra o Live View"
    body: |
      Toque em **Abrir o Live View** no Início. Se o celular perder o comma, o Live View diz o motivo e se reconecta sozinho quando o comma responde. **Não é possível alcançar este comma** significa que o celular não está na rede do comma: corrija isso e toque em **Tentar de novo**.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**Não é possível alcançar este comma**: por que o Live View parou."
      - target: retry
        text: "**Tentar de novo**, quando o celular voltar à rede do comma."
check: "O Início mostra seu comma **Conectado**, e o Live View mostra a via com o caminho desenhado por cima."
fixes:
  - q: "“Não é possível alcançar este comma”"
    a: "O celular precisa estar no mesmo Wi-Fi que o comma, ou no ponto de acesso dele. Veja em qual rede o celular entrou (ele pode ter voltado para um Wi-Fi conhecido), desative qualquer VPN e toque em **Tentar de novo**."
  - q: "“O Live View está aberto em outro dispositivo”"
    a: "Este comma transmite para um celular ou central multimídia por vez. Volte ao Início no CommaView do outro dispositivo, e o Live View começa aqui sozinho."
  - q: "“O CommaView não está respondendo”"
    a: "Ele pode estar reiniciando no comma. O Live View se reconecta quando ele voltar."
  - q: "O CommaView diz que precisa de internet para renovar"
    a: "Durante a beta, o CommaView renova o passe de acesso de vez em quando, e o ponto de acesso do comma não conta como internet. Dê ao celular dados móveis ou um Wi-Fi com internet por um momento."
  - q: "Funcionou em um ponto de acesso e não em outro"
    a: "Alguns pontos de acesso isolam os dispositivos conectados, então o celular não vê o comma. Tente outra das redes do passo 1."
related: [comma-not-found, car-screens, browser-view, setup-troubleshooting]
---

## Descoberta, emparelhamento e o endereço

Três coisas diferentes precisam funcionar, e saber qual falhou mostra o que corrigir:

- **Encontrar o comma.** O CommaView procura seu comma na rede em que o celular está e atualiza o endereço salvo quando encontra o mesmo comma em outro lugar. Algumas redes bloqueiam essa busca; digitar o endereço (passo 3) resolve.
- **Alcançá-lo.** O celular precisa alcançar o comma nessa rede. Um notebook que acessa o comma por SSH não prova que o celular consegue.
- **Emparelhamento.** Depois de alcançar o comma, o celular usa a chave que recebeu ao emparelhar. Trocar de rede não desfaz o emparelhamento: você não precisa emparelhar de novo.
