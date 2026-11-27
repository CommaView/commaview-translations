---
title: "Remover o CommaView do seu comma"
description: "Desinstale o runtime do CommaView do seu comma nas Configurações do dispositivo, devolva os arquivos do seu fork como estavam e esqueça o comma no seu celular."
topic: account
order: 3
kind: walkthrough
lede: "**Desinstalar runtime** remove o CommaView do seu comma: ele desfaz os hooks do CommaView, para o runtime e remove `/data/commaview`. Seu fork continua dirigindo como sempre. Use para remover o CommaView ou para refazer a configuração guiada desde o início."
parked: true
updated: 2026-11-27
needs:
  - title: "O celular e o comma juntos"
    text: "No mesmo Wi-Fi que o comma, ou no ponto de acesso dele. As Configurações do dispositivo precisam do comma para gerenciar atualizações e remoção."
  - title: "O carro ligado, em P"
    text: "Se o carro estiver em movimento, o comma coloca a desinstalação na fila até ele estar em P com o openpilot desativado."
steps:
  - id: device-settings
    title: "Abra as Configurações do dispositivo do comma"
    body: |
      Pelo Início, abra as **Configurações do dispositivo** do seu comma e depois **Runtime** (“Atualizar ou remover”).
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**Runtime**: atualizar ou remover o CommaView."
  - id: uninstall
    title: "Toque em Desinstalar runtime"
    body: |
      Abaixo da atualização do runtime, **Desinstalar runtime** remove o CommaView deste comma. Depois, a configuração guiada pode ser feita de novo desde o início.
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**Desinstalar runtime**."
  - id: confirm
    title: "Confirme"
    body: |
      **O CommaView será removido**: o CommaView desfaz os hooks do runtime, para e remove `/data/commaview` deste comma. O comma continua salvo no seu celular. Toque em **Desinstalar runtime** quando a contagem regressiva curta terminar.
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**O CommaView será removido**, e o que isso faz."
      - text: "**Desinstalar runtime**, depois da contagem regressiva. **Cancelar** mantém o CommaView."
    note: "Se o carro estiver em movimento, o comma coloca a desinstalação na fila: o CommaView é removido quando o carro estiver em P com o openpilot desativado, e continua rodando até lá."
  - id: forget
    title: "Esqueça o comma no seu celular, se quiser"
    body: |
      As Configurações do dispositivo agora dizem que o runtime foi removido. Para tirar o comma do seu celular também, toque em **Esquecer este comma** no fim das Configurações do dispositivo: o CommaView deixa de mostrar este comma e exclui a chave de emparelhamento dele. Para remover o próprio app, desinstale o CommaView pelas configurações do Android, como qualquer app.
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**Esquecer este comma**."
check: "A caixa de diálogo diz **Runtime desinstalado**, e as Configurações do dispositivo mostram o runtime como **Removido**: “O CommaView foi desinstalado do seu comma. Faça a configuração guiada para instalá-lo de novo.”"
fixes:
  - q: "“A desinstalação falhou por erro de permissão SSH”"
    a: "O comma não deixou este celular entrar por SSH. Verifique se o SSH está ativado em **Configurações → Dispositivo → SSH** no comma e se o usuário do GitHub dele tem a chave deste celular, e toque em **Desinstalar de novo**."
  - q: "“O comma não conseguiu desinstalar o CommaView, então o deixou como estava”"
    a: "Nada foi removido. Tente de novo com o carro em P."
  - q: "“Desinstalação na fila até o carro estar em P”"
    a: "O carro está em movimento. Coloque-o em P com o openpilot desativado, mantenha-o ligado, e o comma remove o CommaView sozinho."
  - q: "O botão de desinstalar está acinzentado"
    a: "O CommaView já está atualizando ou desinstalando um runtime. Tente de novo quando terminar."
related: [setup, update-runtime, forks]
---

## O que a desinstalação devolve

- **Em um fork da lista**, ela desfaz o pequeno hook que o CommaView adiciona à interface de tela do fork.
- **Em um fork que o CommaView não lista** (sem garantia), ela devolve os arquivos do fork como estavam.
- **Só vídeo** não mudou nada nos arquivos do fork, e a desinstalação remove o runtime.

No SunnyPilot-TeslaHW1, desinstale o runtime antes do `op fork update`, que não consegue trocar o fork enquanto o hook do CommaView está instalado. [Verifique se seu comma e seu fork são compatíveis](/pt-br/guides/forks) tem mais detalhes.

## Configurar o CommaView de novo

Depois de uma desinstalação, o comma continua salvo no seu celular. Faça a [configuração guiada](/pt-br/guides/setup) para instalá-lo de novo como uma instalação nova.
