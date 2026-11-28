---
title: "Como funcionam as versões do CommaView"
description: "Como o app CommaView e o runtime do seu comma são lançados: versões alfa, depois uma beta, downloads assinados, runtimes compatíveis e atualizações que esperam o carro em P."
topic: account
order: 2
kind: reference
lede: "O CommaView tem duas partes que se atualizam juntas: o app Android e o pequeno runtime no seu comma. Veja como uma versão chega até você e como as atualizações continuam seguras."
updated: 2026-11-27
steps:
  - id: version
    title: "Veja qual versão você tem"
    body: |
      Configurações › **Sobre** mostra a versão do app e se ele está **Atualizado** ou se há uma atualização disponível, com a versão dela. O CommaView consulta sua conta em busca de uma nova versão e avisa quando ela estiver pronta.
    screen: support-about
    pins:
      - target: version
        text: "A versão do app."
      - target: up-to-date
        text: "**Atualizado**, ou a versão pronta para você."
  - id: app-update
    title: "Atualize o app por dentro dele"
    body: |
      Quando uma versão está pronta, **Atualizar** aparece no topo do Início e em **Sobre**. **Atualize o CommaView** mostra a versão e o canal: **Beta** para todos os convidados, ou **Alfa**, “Uma versão inicial para testadores. Pode ter mais problemas que a beta.” Toque em **Baixar**: o CommaView baixa em segundo plano, verifica e depois o Android pede para você confirmar a instalação.
    screen: app-update-offer
    pins:
      - target: channel
        text: "O canal: **Beta** ou **Alfa**."
      - target: download
        text: "**Baixar**. **Agora não** deixa para depois."
  - id: runtime
    title: "Depois atualize o runtime do seu comma"
    body: |
      Cada versão do app indica o runtime com que foi testada. Depois que o app é atualizado, o Início oferece esse runtime com **Atualização do runtime pronta**. As atualizações do runtime começam pelo app, nunca sozinhas. [Atualizar o runtime do seu comma](/pt-br/guides/update-runtime) tem cada passo.
    screen: home-runtime-update
    pins:
      - target: update-card
        text: "**Atualização do runtime**: o runtime instalado e o disponível."
related: [update-runtime, uninstall, setup]
---

## Alfa, depois beta

- Cada versão sai primeiro como uma série de alfas para alguns testadores.
- Quando uma alfa se mostra estável, ela vira a beta dessa versão e vai para todos os convidados.
- Sua conta em [my.commaview.com](https://my.commaview.com) sempre oferece a versão certa para você.

## Assinadas e compatíveis

- Cada download do app é uma versão de lançamento assinada, nunca uma versão de depuração, com a soma de verificação SHA-256 ao lado em my.commaview.com. O app confere o tamanho e a soma de verificação de uma atualização baixada antes de oferecer a instalação: “O download não correspondeu à soma de verificação, então não foi instalado.”
- Cada versão do app indica o runtime com que foi testada, e o app instala exatamente esse no seu comma.
- Um app mais antigo nunca recebe a oferta de um runtime com que não foi testado. Um comma cujo runtime é mais novo do que o app instala avisa: atualize o CommaView e tente de novo.

## Atualizar seu comma com segurança

- As atualizações do runtime começam pelo Início ou pelas Configurações do dispositivo, nunca sozinhas.
- As atualizações nunca interrompem uma viagem. Se o carro estiver em movimento, a Atualização segura coloca a atualização na fila e o comma a instala quando o carro estiver em P com o openpilot desativado. Você não precisa desligar o carro.
- Depois de uma atualização do runtime, o comma precisa reiniciar antes de o CommaView voltar a transmitir. O app pede isso.
- Você pode remover o runtime pelas Configurações do dispositivo a qualquer momento: [Remover o CommaView](/pt-br/guides/uninstall).

## Onde você fica sabendo

- O app avisa quando uma nova versão está pronta.
- [Novidades](/whats-new) lista cada mudança.
- Mandamos e-mail sobre mudanças importantes, e você pode enviar comentários pelo app a qualquer momento (Configurações › **Suporte e diagnóstico**).
