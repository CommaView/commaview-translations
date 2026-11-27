---
title: "Configurar o CommaView"
description: "Instale o app CommaView no Android, prepare seu comma 3X ou comma four e deixe a configuração guiada instalar o runtime e emparelhar seu comma."
topic: start
order: 1
kind: walkthrough
lede: "O CommaView tem duas partes: o app no seu celular, tablet ou central multimídia Android, e o pequeno runtime dele no seu comma. Instale o app, e a configuração guiada coloca o runtime no seu comma, verifica e emparelha. Leva alguns minutos, com o carro em P e o openpilot desativado."
parked: true
updated: 2026-11-27
needs:
  - title: "Um comma 3X ou comma four"
    text: "Com openpilot ou um [fork compatível](/pt-br/guides/forks). O comma 3 não é compatível: a versão do openpilot dele está congelada e desenha a tela de outro jeito, então o CommaView não consegue mostrar a sobreposição. [Por que o comma 3 não é compatível](/pt-br#faq-comma-3)."
  - title: "Um dispositivo Android e seu convite"
    text: "Android 8 ou posterior, e o e-mail que recebeu seu convite. O CommaView está em beta: você entra com a conta convidada."
  - title: "A mesma rede"
    text: "Seu celular e o comma em uma mesma rede local: seu Wi-Fi, o ponto de acesso do seu celular, o do próprio comma ou qualquer outra em que os dois possam entrar. No carro? [Conectar sem o Wi-Fi de casa](/pt-br/guides/connect-in-the-car)."
  - title: "Uma conta no GitHub"
    text: "O comma aceita as chaves SSH do usuário do GitHub que você informar. O CommaView cria a chave; você a adiciona ao GitHub durante a configuração."
howItWorks:
  - title: "Seu celular"
    text: "Cria uma chave SSH, que você adiciona ao GitHub."
    edge: "SSH"
  - title: "Seu comma"
    text: "Pega a chave do seu usuário do GitHub. O CommaView instala o runtime ao lado do seu fork."
    edge: "rede local"
  - title: "CommaView"
    text: "Verifica se o runtime responde e salva seu comma. Daí em diante ele se reconecta sozinho."
steps:
  - id: get-the-app
    title: "Baixe o app e entre na conta"
    body: |
      No seu dispositivo Android, entre em [my.commaview.com](https://my.commaview.com) com o e-mail que recebeu seu convite. Em **Get the app**, toque em **Download CommaView**. A soma de verificação SHA-256 aparece ao lado, se você quiser conferir o arquivo.

      Abra o download. O Android pede para permitir instalações pelo seu navegador: permita para esta instalação e depois desative de novo.

      Abra o CommaView. Ele pergunta uma vez se você quer **Ajude a melhorar o CommaView**: **Enviar** ou **Não enviar**. Depois pede para você entrar: toque em **Entrar** e use o e-mail que recebeu seu convite. A partir daí ele funciona offline enquanto o passe de acesso for válido.
    tabs:
      - label: "Ajude a melhorar o CommaView"
        body: "Relatórios de falhas e qual software de condução seu comma usa, nunca vídeo, viagens, lugares ou nomes. Você pode mudar isso quando quiser em Configurações › **Privacidade e dados**."
        screen: improve-commaview
        pins:
          - target: send
            text: "**Enviar** relatórios de falhas para ajudar a corrigir problemas."
          - target: dont-send
            text: "**Não enviar** os mantém no celular."
      - label: "Entrar"
        body: "Durante a beta, o CommaView precisa da sua conta convidada. **Entrar** abre seu navegador."
        screen: sign-in
        pins:
          - target: sign-in
            text: "**Entrar** com o e-mail que recebeu seu convite."
    note: "Vai instalar em uma central multimídia ou em uma AI box na tela do carro? [Telas do carro](/pt-br/guides/car-screens) explica a rede dela e como emparelhá-la com seu comma."
  - id: connect
    title: "Comece a configurar seu comma"
    body: |
      Leia o aviso, marque que você entende que é um software não oficial e que é responsável pelo uso seguro, e toque em **Entendo — continuar**.

      Em **Conecte seu comma**, toque em **Configurar o CommaView no seu comma**.
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**Configurar o CommaView no seu comma**, para um comma que ainda não roda o CommaView."
      - target: pair-runs
        text: "Já roda o CommaView a partir de outro celular? Use **Emparelhar um comma que já roda o CommaView**: [Adicionar outro celular ou tablet](/pt-br/guides/another-phone)."
  - id: setup-path
    title: "Escolha um caminho de configuração"
    tabs:
      - label: "Configuração guiada"
        body: "Escolha **Configuração guiada** (marcada como Recomendado) e toque em **Continuar para a configuração guiada**. O CommaView cria uma chave SSH, guia a conexão e verifica seu comma. Os próximos passos acompanham essa configuração."
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**Configuração guiada**, marcada como Recomendado."
          - target: continue
            text: "**Continuar para a configuração guiada**."
      - label: "Configuração manual"
        body: "Só se o SSH já funcionar do seu computador para o comma como usuário `comma`. Escolha **Configuração manual**, depois **Continuar para a configuração manual**, e rode o comando no seu terminal. Quando o instalador mostrar um código de emparelhamento de uso único, toque em **Executei o comando**, digite o IP do seu comma e o código, e toque em **Adicionar um comma**. [Configuração manual pelo terminal](#configuração-manual-pelo-terminal) tem cada passo."
        screen: setup-manual-instructions
        pins:
          - text: "**Toque para copiar** copia o comando."
          - target: ran-command
            text: "**Executei o comando**, quando o instalador mostrar o código de emparelhamento."
  - id: ssh-key
    title: "Adicione a chave SSH ao GitHub"
    body: |
      O CommaView cria uma chave SSH para este celular. Toque em **Copiar chave e abrir o GitHub**: ele copia a chave pública e abre a página de nova chave SSH do GitHub.

      No GitHub, cole a chave no campo **Key**, dê qualquer título (o CommaView preenche um) e salve com **Add SSH key**. Volte ao CommaView e toque em **Continuar**.
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**Copiar chave e abrir o GitHub**. Aparece “Chave SSH copiada. Abrindo o GitHub…”"
      - target: own-key
        text: "**Usar minha própria chave SSH** importa um par de chaves que você já tem no GitHub."
      - target: continue
        text: "**Continuar**, depois que a chave estiver salva no GitHub."
    note: "Já tem um par de chaves no GitHub? **Usar minha própria chave SSH** importa esse par. A chave privada fica no seu celular."
  - id: comma-ssh
    title: "Ative o SSH no seu comma"
    body: |
      Na tela do comma, vá em **Configurações → Dispositivo → SSH**:

      1. Digite seu usuário do GitHub.
      2. Espere o comma buscar suas chaves do GitHub.
      3. Ative o SSH.

      Depois volte ao CommaView e toque em **Continuar**.
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "**Continuar**, depois que o SSH estiver ativado."
    note: "O comma busca suas chaves uma vez só, quando você digita o usuário. Digitou antes de adicionar a chave? Remova e digite de novo, para o comma buscar as chaves outra vez."
  - id: choose-comma
    title: "Escolha seu comma"
    body: |
      O CommaView lista os commas desta rede Wi-Fi que já rodam o CommaView, então um comma que você está configurando pela primeira vez normalmente ainda não aparece. Toque em **Meu comma não aparece** e digite o endereço IP dele. Depois toque em **Instalar o CommaView**.

      Você encontra o IP no comma em **Configurações → Rede**: abaixo do nome da rede no botão de Wi-Fi em um comma four, ou em **Avançado** em um comma 3X.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Um comma que já roda o CommaView. Um salvo neste celular aparece marcado como **Salvo neste celular**."
      - text: "**Meu comma não aparece**: digite o endereço IP dele."
      - target: install
        text: "**Instalar o CommaView**."
  - id: safe-install
    title: "Inicie a Instalação segura"
    body: |
      A caixa de diálogo **Instalação segura** mostra em qual comma vai instalar. Leia a nota e toque em **Iniciar instalação segura** quando a contagem regressiva curta terminar.
    tabs:
      - label: "O carro está em P"
        body: "Se o carro está em P e o openpilot não está ativado, o CommaView instala na hora."
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "**Iniciar instalação segura**, depois da contagem regressiva."
      - label: "O carro está em movimento"
        body: "O comma coloca a instalação na fila e a executa quando o carro estiver em P com o openpilot desativado, então uma viagem nunca é interrompida. A configuração mostra **Instalação na fila**: coloque o carro em P com o openpilot desativado, espere um ou dois minutos e toque em **Concluir configuração**."
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "**Concluir configuração**, quando o carro estiver em P."
    note: "Depois o CommaView se conecta ao comma por SSH, verifica qual comma é e instala o runtime com que esta versão do app foi testada. Ele confere se a instalação responde e salva seu comma neste celular. Mantenha o celular na mesma rede até terminar."
    warn: "Mantenha o carro ligado, em P. Sem um chicote de alimentação, desligar o carro também desliga o comma, o que interrompe a instalação."
  - id: ready
    title: "O CommaView está pronto"
    body: |
      Seu comma está instalado, emparelhado, e se reconecta sozinho na próxima vez que ligar.
    tabs:
      - label: "O CommaView está pronto"
        body: "Toque em **Pronto**."
        screen: setup-done
        pins:
          - target: finish
            text: "**Pronto** leva você ao Início."
      - label: "Reinicie para concluir"
        body: "Às vezes a configuração diz **Reinicie para concluir**: o comma transmite para o seu celular depois de reiniciar uma vez. Toque em **Reiniciar comma e concluir** com o carro desligado ou em P com o openpilot desativado. O openpilot para por cerca de um minuto enquanto reinicia."
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**Reiniciar comma e concluir**."
check: "O Início mostra seu carro com o comma **Conectado**, o runtime e o endereço do comma. Toque em **Abrir o Live View**: a via aparece ao vivo, com o caminho e o carro à frente desenhados por cima. Daqui em diante o app encontra seu comma sozinho quando o celular e o comma estão na mesma rede, mesmo que o endereço mude."
fixes:
  - q: "Não foi possível conectar por SSH"
    a: "Verifique se o SSH está ativado em **Configurações → Dispositivo → SSH** no comma, se o usuário do GitHub é o seu e se a chave do CommaView está nessa conta do GitHub. Se você adicionou a chave depois de digitar o usuário, remova o usuário e digite de novo para o comma buscar a chave."
  - q: "Meu comma não está na lista"
    a: "É normal na primeira vez: a lista mostra commas que já rodam o CommaView. Toque em **Meu comma não aparece** e digite o endereço IP dele (**Configurações → Rede** no comma: abaixo do nome da rede no botão de Wi-Fi em um comma four, ou em **Avançado** em um comma 3X). Verifique se o celular está na mesma rede que o comma e sem VPN."
  - q: "A configuração diz “Instalação na fila”"
    a: "O comma viu o carro em movimento, então espera. Coloque o carro em P com o openpilot desativado, espere um minuto e toque em **Concluir configuração**. Deixe o carro ligado: sem um chicote de alimentação, desligá-lo também desliga o comma."
  - q: "A configuração diz que meu comma não é compatível"
    a: "Em um comma 3, a configuração para e oferece **Configure o CommaView em um comma 3X ou comma four**. Em um fork em cuja tela o CommaView não consegue adicionar sua visualização, a configuração avisa e não muda nada. [Verifique se seu comma e seu fork são compatíveis](/pt-br/guides/forks)."
  - q: "O código de emparelhamento não funcionou"
    a: "Os códigos de emparelhamento são de uso único e expiram rápido. Rode o instalador de novo para obter um código novo e confira se digitou como aparece (o hífen é opcional)."
  - q: "Conectado, mas sem vídeo"
    a: "A configuração e o emparelhamento estão feitos; o problema é a transmissão de vídeo. Verifique se o comma está ligado e pronto para rodar, mantenha o celular na mesma rede e abra o Live View de novo. Se aparecer **Não é possível alcançar este comma**, veja [O CommaView não encontra seu comma](/pt-br/guides/comma-not-found)."
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## Configuração manual pelo terminal

Só se o SSH já funcionar do seu computador para o comma como usuário `comma`.

1. No CommaView, escolha **Configuração manual** e depois **Continuar para a configuração manual**. O app mostra o comando do runtime dele em **Instalar pelo terminal**, pronto para copiar (**Toque para copiar**). Ele é parecido com este, que instala o runtime da versão atual:

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. Rode o comando em um computador na mesma rede Wi-Fi que o seu comma, trocando `COMMA_IP` pelo endereço IP do comma (**Configurações → Rede** no comma: abaixo do nome da rede no botão de Wi-Fi em um comma four, ou em **Avançado** em um comma 3X). Seu computador baixa o instalador, e o SSH o executa no comma como usuário `comma`.
3. Quando o instalador termina, o CommaView inicia no comma e mostra um código de emparelhamento de uso único.
4. De volta ao CommaView, toque em **Executei o comando**. Em **Adicionar seu comma**, selecione seu comma ou digite o IP dele, digite o código de emparelhamento e toque em **Adicionar um comma**. O app verifica o runtime e salva o comma.

## Antes da primeira viagem

Teste em P antes de dirigir.

- O Início mostra seu comma como **Conectado**.
- O Live View roda e o caminho se move com o carro.
- Se o app mostrar um aviso ou pedir um reparo, resolva antes de dirigir.
- Deixe tudo configurado para que ele nunca precise da sua atenção enquanto você dirige.

Ainda com problemas? Pergunte no [Discord do CommaView](https://discord.gg/UuMhz9K8ft) ou envie um comentário pelo app. Se o suporte pedir logs, [envie um pacote de suporte](/pt-br/guides/support-bundle).
