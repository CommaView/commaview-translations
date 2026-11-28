---
title: "Enviar um pacote de suporte"
description: "Deixe o diagnóstico ativado, faça o problema acontecer de novo e envie um relatório com os logs do seu celular e do seu comma em Configurações › Suporte e diagnóstico."
topic: troubleshooting
order: 3
kind: walkthrough
lede: "Um pacote de suporte é um pequeno zip com o que o app CommaView viu no seu celular e o que o runtime dele viu no seu comma. Ele nos permite encontrar um problema sem estar no seu carro. Contém só logs: nada de vídeo, nada de localização."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Diagnóstico ativado"
    text: "**Guardar diagnóstico neste celular**, ativado a menos que alguém tenha desativado. Confira antes de o problema acontecer de novo."
  - title: "Conectado ao seu comma"
    text: "Para os logs do seu comma, o Início mostra seu comma **Conectado** quando você envia."
  - title: "Conta conectada para enviar"
    text: "Enviar precisa da sua conta da beta. Fora da conta, **Salvar como arquivo** continua funcionando."
howItWorks:
  - title: "Seu celular"
    text: "Guarda os logs e contadores das suas últimas 10 viagens."
  - title: "Seu comma"
    text: "Acrescenta os logs do runtime quando você toca em Enviar, sem localização, VIN, IDs, nomes de Wi-Fi e tokens."
    edge: "quando você toca em Enviar"
  - title: "A equipe do CommaView"
    text: "Lê em um armazenamento privado e responde por e-mail."
steps:
  - id: open
    title: "Abra Suporte e diagnóstico"
    body: |
      No CommaView, toque em **Configurações** na barra de baixo. Em um tablet ou central multimídia, fica na barra lateral. Toque em **Suporte e diagnóstico**, perto do fim, antes de Sobre.
    screen: support-settings
    pins:
      - text: "**Suporte e diagnóstico**."
  - id: keep-diagnostics
    title: "Guarde o diagnóstico neste celular"
    body: |
      **Guardar diagnóstico neste celular** fica ativado a menos que alguém tenha desativado: o app guarda os logs e contadores das suas últimas 10 viagens, para que um relatório possa dizer o que aconteceu. Se estiver desativado, ative e faça o problema acontecer de novo.
    screen: support-diagnostics
    pins:
      - target: keep-diagnostics
        text: "**Guardar diagnóstico neste celular**."
    note: "O diagnóstico fica neste celular até você enviar um relatório: ele nunca é enviado automaticamente."
  - id: happen-again
    title: "Faça acontecer de novo, estacionado"
    body: |
      Conecte-se ao seu comma como de costume: o celular no Wi-Fi ou ponto de acesso do comma, e o Início mostrando seu comma **Conectado**. Faça o que deu errado; por exemplo, abra o Live View, mude para a tela de condução que apresenta o problema e deixe-a ali por 10 a 20 segundos. Anote mais ou menos quando aconteceu e o que você fez. Uma gravação de tela também ajuda.
    warn: "Faça acontecer em P. Se só acontece na estrada, deixe acontecer e envie o relatório depois de estacionar: o registro espera você. Nunca mexa no app enquanto dirige."
  - id: open-send
    title: "Abra Enviar ao CommaView"
    body: |
      Em **Suporte e diagnóstico**, toque em **Relatar um problema ou enviar uma ideia**.

      Ou comece pelo problema: onde o app mostra uma falha, toque no **Relatar** dela; para uma gravação, escolha **Enviar ao CommaView…** em **Ações da gravação**. Cada um abre a mesma folha, com o que é relevante já preenchido.
    screen: support-diagnostics
    pins:
      - target: report
        text: "**Relatar um problema ou enviar uma ideia**."
  - id: send
    title: "Escolha o que vai e envie"
    body: |
      Escolha **Problema** e conte o que aconteceu. Em **Anexos**, deixe ativados **Este celular: diagnóstico** e os logs do seu comma. **Ver** mostra exatamente o que cada um contém. Abaixo das linhas, a folha lista o que vai com todo relatório: a versão do app, o modelo do seu celular e a versão do Android, e o software de condução e a configuração do seu comma.

      Toque em **Enviar**: “Enviando. Vai em segundo plano e aguarda uma conexão.”
    screen: support-send-feedback
    pins:
      - target: problem
        text: "**Problema** ou **Ideia**."
      - text: "**Anexos**: cada linha tem um botão e **Ver**."
      - target: send
        text: "**Enviar**."
    note: "Envie enquanto o app está conectado ao seu comma: ele pede os logs ao comma quando você toca em Enviar. Se o comma estiver desligado ou fora de alcance, o pacote diz o motivo e ainda contém os logs do próprio app."
  - id: save-file
    title: "Ou salve como arquivo"
    body: |
      O suporte pediu o arquivo em si, ou você não está com a conta conectada? Toque em **Salvar como arquivo** em vez de Enviar. O app monta o mesmo pacote, um pequeno `.zip`, e abre o menu de compartilhamento do Android. Envie para onde o suporte pediu: uma mensagem direta no Discord, um e-mail ou um link de armazenamento em nuvem.
    screen: support-share-bug-report
    pins:
      - target: save-file
        text: "**Salvar como arquivo**."
  - id: afterwards
    title: "Leia nossa resposta"
    body: |
      Quando respondemos, a resposta chega por e-mail e fica em [Your feedback](https://my.commaview.com/feedback) em my.commaview.com, com seu relatório. Responda por lá até fecharmos; você pode reabrir por 30 dias depois. **Suas solicitações**, em **Suporte e diagnóstico**, também as lista.
    screen: support-diagnostics
    pins:
      - target: your-requests
        text: "**Suas solicitações**: as respostas e suas conversas com o CommaView."
check: "A folha fecha com “Enviando. Vai em segundo plano e aguarda uma conexão.”, e o relatório aparece em **Suas solicitações** depois de enviado."
fixes:
  - q: "O pacote não tem logs do comma"
    a: "O app não conseguiu alcançar seu comma quando você tocou em Enviar, ou a linha dele em **Anexos** estava desativada. Confira se o Início mostra seu comma **Conectado** antes de abrir Enviar ao CommaView, e deixe a linha do seu comma ativada. Se o app pedir para emparelhar seu comma de novo, emparelhe primeiro e envie de novo."
  - q: "Enviar mostra **Entre para enviar**"
    a: "Você está fora da conta. Toque para entrar com sua conta da beta, ou use **Salvar como arquivo**."
  - q: "“Os anexos passam dos 25 MB que um relatório comporta. Desative um ou use Salvar como arquivo.”"
    a: "Desative um anexo de que não precisa, ou toque em **Salvar como arquivo** e envie o arquivo para onde o suporte pedir."
  - q: "Nada acontece quando toco em Salvar como arquivo"
    a: "O Android não tem neste dispositivo nenhum app que aceite um arquivo. Isso é comum em centrais multimídia. [Envie](#step-send) ao CommaView em vez disso, ou salve a partir de um celular com o CommaView."
  - q: "“Não foi possível preparar o relatório. Verifique o armazenamento local e tente de novo.”"
    a: "O app não conseguiu gravar o pacote, normalmente porque falta armazenamento no dispositivo. Libere espaço e tente de novo."
related: [setup-troubleshooting, comma-not-found, releases]
---

## O que há em um pacote de suporte

- **O diagnóstico deste celular.** Os logs e contadores de diagnóstico do CommaView neste celular: a transmissão de vídeo, o desenho, a conexão e os erros de gravação, com a versão do app e o modelo do celular e a versão do Android. Com a Navegação, também quantas buscas de lugares de cada tipo funcionaram ou falharam, nunca o que você buscou.
- **Os logs do seu comma.** Com a linha do seu comma ativada: os logs, contadores e configurações do runtime do CommaView, quais processos do openpilot pararam e por quê, e as linhas de falta de memória do kernel do comma.
- **Nunca em um pacote.** Nada de vídeo, localização GPS, VIN ou telemetria bruta de condução: uma gravação que você envia vai ao lado do pacote, não dentro dele. Um runtime do comma atualizado remove coordenadas GPS, VINs, nomes de Wi-Fi, endereços IP públicos, tokens e o ID completo do dongle antes de enviar os logs.
- **Só quando você envia.** Um pacote só sai do seu celular quando você toca em Enviar ou Salvar como arquivo. Um arquivo que você salva só vai para onde você o enviar. Endereços IP locais, IDs de sessão e detalhes de versão podem permanecer, então compartilhe um pacote só com pessoas de confiança.

## Para onde vai e por quanto tempo

Um pacote que você envia vai para o armazenamento privado do CommaView, onde só a equipe do CommaView o abre. Ele é excluído 180 dias depois do envio, ou antes, na hora, quando você pede ou exclui sua conta ([Privacidade](/privacy)). Para pedir, mande um e-mail para support@commaview.com.

Para remover o que o app guarda neste celular, toque em **Limpar dados de diagnóstico locais** em **Suporte e diagnóstico**. Isso nunca exclui suas gravações. Para guardar daí em diante só o histórico de erros de gravação, desative **Guardar diagnóstico neste celular** na mesma página.

Não sabe para onde enviar? Pergunte no [Discord do CommaView](https://discord.gg/UuMhz9K8ft).
