---
title: "Atualizar o runtime do seu comma"
description: "Atualize o runtime do CommaView no seu comma pelo Início ou pelas Configurações do dispositivo. A Atualização segura espera o carro em P, então nunca interrompe uma viagem."
topic: account
order: 1
kind: walkthrough
lede: "O runtime do CommaView no seu comma é atualizado pelo app, nunca sozinho. Atualize primeiro o CommaView e depois o runtime quando o app oferecer. Se o carro estiver em movimento, a **Atualização segura** coloca a atualização na fila do comma e a instala quando o carro estiver em P com o openpilot desativado."
updated: 2026-11-27
needs:
  - title: "O celular e o comma juntos"
    text: "No mesmo Wi-Fi que o comma, ou no ponto de acesso dele."
  - title: "O carro ligado"
    text: "Mantenha o carro ligado, em P. Sem um chicote de alimentação, desligá-lo também desliga o comma."
howItWorks:
  - title: "CommaView"
    text: "Cada versão do app indica o runtime com que foi testada e oferece exatamente esse."
  - title: "Seu comma"
    text: "Baixa, verifica e instala o runtime quando o carro está em P."
    edge: "reinício"
  - title: "Live View"
    text: "Volta a funcionar depois que o comma reinicia."
steps:
  - id: app-first
    title: "Atualize primeiro o CommaView"
    body: |
      O app instala o runtime com que foi testado, então atualize o app antes do runtime. Quando há uma atualização pronta, **Atualizar** aparece no topo do Início e em Configurações › **Sobre**. Toque nele: **Atualize o CommaView** mostra a versão, o canal e o tamanho. Toque em **Baixar**; o CommaView baixa em segundo plano e verifica, e depois o Android pede para você confirmar a instalação.
    screen: app-update-offer
    pins:
      - target: download
        text: "**Baixar**."
      - target: channel
        text: "O canal da versão: **Beta**, ou **Alfa** para testadores."
    note: "Atualize o CommaView em todos os celulares, tablets e telas do carro que assistem a este comma antes de atualizar o runtime dele."
  - id: open
    title: "Abra a atualização do runtime"
    tabs:
      - label: "Pelo Início"
        body: "O Início mostra **Atualização do runtime pronta** quando há um novo runtime para este comma. Toque em **Revisar atualização**: o cartão **Atualização do runtime** mostra as versões **Instalado** e **Disponível** e se o carro está pronto. Toque em **Atualizar runtime**, ou em **Colocar na fila** enquanto o carro está em movimento."
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**Atualização do runtime**: Instalado, Disponível e se o carro está pronto."
          - target: update-runtime
            text: "**Atualizar runtime** (**Colocar na fila** com o carro em movimento)."
      - label: "Pelas Configurações do dispositivo"
        body: "Abra as **Configurações do dispositivo** do comma e depois **Runtime** (ele mostra **Atualizar** quando há uma pronta). A página mostra o runtime instalado e o disponível. Toque em **Atualizar agora**."
        screen: device-runtime
        pins:
          - target: update-now
            text: "**Atualizar agora**."
  - id: install
    title: "Instale, ou deixe a Atualização segura colocar na fila"
    body: |
      Pelas Configurações do dispositivo, a caixa de diálogo **Atualização do runtime** diz se o carro está pronto.
    tabs:
      - label: "O carro está em P"
        body: "Ela diz “O carro está em P e o openpilot não está ativado. É seguro iniciar a atualização do runtime.” Toque em **Instalar atualização**."
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**Instalar atualização**."
          - target: close
            text: "**Fechar** deixa para depois."
      - label: "O carro está em movimento"
        body: "Ela diz “O carro está em movimento. A Atualização segura coloca a atualização na fila do comma e a instala quando o carro estiver em P com o openpilot desativado.” Toque em **Atualização segura…**, leia a nota e toque em **Iniciar atualização segura** quando a contagem regressiva curta terminar. O mesmo acontece quando o CommaView não conseguiu confirmar se o carro está em movimento."
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**Atualização segura…** e depois **Iniciar atualização segura**."
    note: "O CommaView nunca para o openpilot nem o seu fork: uma atualização na fila espera o carro em P, e uma viagem nunca é interrompida."
  - id: progress
    title: "Deixe rodar"
    body: |
      O comma baixa a versão, verifica se ela está completa e inalterada, instala e reinicia o CommaView, e o app mostra cada passo. Você pode trocar de app ou bloquear o celular: a atualização continua, e a notificação mostra o progresso.

      Até o comma começar a instalar, **Cancelar atualização** a interrompe, e nada muda no seu comma.
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "Os passos: Baixando, Verificando, Instalando, Reiniciando o CommaView, Reconectando."
  - id: queued
    title: "Uma atualização na fila espera o carro em P"
    body: |
      Uma atualização na fila aparece no cartão **Atualização do runtime** do Início como **Aguardando o carro estar em P**. Ela é instalada quando o carro fica alguns segundos em P com o openpilot desativado. Deixe o carro ligado enquanto ela instala.
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "**Aguardando o carro estar em P**, com o passo."
  - id: reboot
    title: "Reinicie o comma para concluir"
    body: |
      Depois de uma atualização do runtime, o comma precisa reiniciar antes de o CommaView voltar a transmitir dele: o openpilot só carrega o novo código de tela do CommaView quando o comma reinicia. O app nunca o reinicia sozinho.

      Toque em **Reiniciar comma** no cartão do Início, ou em **Reiniciar comma agora** na caixa de diálogo, com o carro desligado ou em P. O openpilot para por cerca de um minuto. Você também pode reiniciar pelo próprio comma: **Configurações → Dispositivo → Reiniciar**.
check: "O último passo da atualização mostra **Atualizado**, e as Configurações do dispositivo mostram o novo runtime **Atualizado**. Depois do reinício, o Live View roda com a sobreposição."
fixes:
  - q: "“O runtime deste comma é mais novo do que este app instala”"
    a: "Atualize o CommaView e tente de novo. Nada foi alterado no comma."
  - q: "“Atualização necessária”"
    a: "Este app e o runtime deste comma não são novos o bastante um para o outro. Atualize primeiro o CommaView e depois o runtime."
  - q: "“O comma não instalou …: ele usa …, que o CommaView não lista”"
    a: "O comma não mudou nada e manteve o runtime que tinha. Para adicionar o CommaView a esse fork sem garantia, faça a configuração deste comma de novo: ela verifica o fork e pergunta antes."
  - q: "“O carro voltou a andar toda vez que começou, então o comma parou de tentar”"
    a: "Coloque o carro em P com o openpilot desativado e tente de novo."
  - q: "“Atualização do runtime revertida”"
    a: "O comma voltou ao runtime que tinha. Tente de novo e, se falhar outra vez, [envie um pacote de suporte](/pt-br/guides/support-bundle)."
  - q: "“O CommaView já está atualizando ou desinstalando um runtime”"
    a: "Só uma tarefa de runtime roda por vez. Tente de novo quando ela terminar."
  - q: "Sem sobreposições nem telemetria depois da atualização"
    a: "O comma ainda não reiniciou. Reinicie com o carro desligado ou em P."
related: [releases, uninstall, another-phone]
---

## Por que as atualizações esperam o carro em P

Instalar o runtime para o CommaView no comma enquanto os arquivos são substituídos e reinicia os serviços dele, então o comma só faz isso com o carro em P e o openpilot desativado. A Atualização segura não pede ao openpilot para parar: ela coloca o trabalho na fila do comma, que o executa quando o carro está em P. Você não precisa desligar o carro; mantenha-o ligado, em P.

Antes de mudar qualquer coisa no comma, ele baixa a versão e verifica se está completa e inalterada. Se uma instalação falhar depois disso, o comma volta ao runtime que tinha.
