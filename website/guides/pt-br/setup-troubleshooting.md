---
title: "Resolver uma configuração que para"
description: "O que significam as mensagens da configuração do CommaView, na ordem em que ela avança: SSH, a instalação e o emparelhamento. Encontre a mensagem que você vê e o que fazer."
topic: troubleshooting
order: 1
kind: fixes
lede: "A configuração segue uma ordem: entra no seu comma por SSH, instala o runtime do CommaView e depois emparelha seu celular com ele. Quando ela para, a mensagem diz qual parte falhou, então corrija essa parte primeiro. O SSH funcionar só prova a primeira: um código de emparelhamento não funciona se o runtime nunca iniciou."
parked: true
updated: 2026-11-27
needs:
  - title: "Em P"
    text: "O carro em P com o openpilot desativado, e ligado: sem um chicote de alimentação, desligá-lo também desliga o comma."
  - title: "Uma só rede"
    text: "Seu celular no mesmo Wi-Fi que o comma, ou no ponto de acesso dele. Um notebook alcançar o comma não prova que o celular consegue."
steps:
  - id: read
    title: "Leia o que a configuração diz e copie os detalhes"
    body: |
      Quando a instalação falha, a configuração diz o que deu errado, se seu comma voltou a ficar como estava e o que fazer. Encontre essa frase em [Se não funcionar](#fixes), abaixo.

      **Copiar detalhes** copia o relatório que o suporte lê: a versão do app, a versão lançada, a última etapa do instalador e toda a saída dele. Cole em um e-mail para support@commaview.com quando a mensagem pedir.
    tabs:
      - label: "A instalação falhou"
        body: "A configuração diz o que falhou e oferece **Copiar detalhes**."
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**Copiar detalhes**."
          - target: install
            text: "**Instalar o CommaView** tenta de novo depois que você corrigir a causa."
      - label: "O SSH falhou"
        body: "Antes de instalar qualquer coisa, a configuração diz por que não conseguiu entrar no comma, como **Falha na autenticação SSH**, e o que verificar."
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "O que deu errado e o que verificar."
  - id: address
    title: "Verifique o endereço do comma"
    body: |
      A configuração procura commas na rede do seu celular. Se o seu não aparecer, toque em **Meu comma não aparece** e digite o endereço IP dele. No seu comma, ele fica em **Configurações → Rede**: abaixo do nome da rede no botão de Wi-Fi em um comma four, ou em **Avançado** em um comma 3X.

      O comma tem um endereço diferente em cada rede: o Wi-Fi de casa, um ponto de acesso, uma VPN. Use o da rede em que seu celular está agora.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "Um comma que a configuração encontrou nesta rede."
      - text: "**Meu comma não aparece**: digite o endereço IP quando ele não é encontrado."
  - id: pair-code
    title: "Emparelhe com um código novo"
    body: |
      Os códigos de emparelhamento duram pouco e funcionam uma vez. Se um for recusado, não digite de novo: pegue um novo. Depois de uma instalação manual, o instalador mostra um; um celular já emparelhado com o comma mostra um em **Configurações do dispositivo › Emparelhar outro celular ou tablet**.
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**Endereço IP do comma**."
      - target: pair-code
        text: "**Código de emparelhamento**. Hífen opcional."
  - id: runs
    title: "Já instalado? Emparelhe em vez disso"
    body: |
      Se o comma já roda o CommaView, por outro celular ou por uma configuração anterior, você não precisa instalar de novo. No Início, toque em **Adicionar um comma**, depois em **Digitar endereço e código**, e emparelhe com o IP do comma e um código de emparelhamento ou um convite.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "O IP do comma."
      - target: pair-code
        text: "**Código ou convite**."
      - target: pair
        text: "**Emparelhar comma**."
  - id: no-video
    title: "Instalado e emparelhado, mas sem vídeo"
    body: |
      Depois do emparelhamento, uma imagem faltando é um problema de transmissão, não de SSH. O Live View diz o que vê, como **Não é possível alcançar este comma**, e se reconecta sozinho quando o comma responde. Veja [O CommaView não encontra seu comma](/pt-br/guides/comma-not-found).
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**Tentar de novo**."
fixes:
  - q: "“Falha na autenticação SSH.”"
    a: "Verifique se a chave do CommaView está no GitHub (qualquer título) e se o SSH está ativado no comma. Se você digitou seu usuário do GitHub no comma antes de adicionar a chave, remova e digite de novo, para o comma buscar suas chaves outra vez."
  - q: "“Conexão recusada em 192.168.1.50:22. Verifique se o SSH está ativado no seu comma.”"
    a: "No comma, vá em **Configurações → Dispositivo → SSH** e ative o SSH."
  - q: "“Tempo de conexão esgotado com …” ou “Sem rota para …”"
    a: "Seu celular não alcança esse endereço. Confira se o celular está no mesmo Wi-Fi que o comma, ou no ponto de acesso dele, se o comma está acordado (carro ligado) e se o endereço IP é o do comma nesta rede."
  - q: "“Nenhum comma encontrado em … Verifique o endereço IP.”"
    a: "Nada respondeu nesse endereço. Confira o IP em **Configurações → Rede** no comma."
  - q: "“A identidade SSH deste comma mudou desde a última configuração.”"
    a: "Se você redefiniu ou regravou o comma, faça a configuração de novo."
  - q: "“O CommaView não conseguiu criar a chave SSH neste celular. Tente de novo ou use sua própria chave SSH.”"
    a: "Toque em **Tentar de novo**, ou em **Usar minha própria chave SSH** para importar um par de chaves que você já tem no GitHub."
  - q: "“Instalação na fila.”"
    a: "O carro estava em movimento, então o comma colocou a instalação na fila em vez de interromper a viagem. Coloque o carro em P com o openpilot desativado, deixe um ou dois minutos com o carro ligado e toque em **Concluir configuração**."
  - q: "“O carro está em movimento, então a instalação não foi executada.”"
    a: "Coloque o carro em P com o openpilot desativado e tente de novo."
  - q: "“Outra instalação, atualização ou reparo do CommaView já está em andamento no seu comma.”"
    a: "Espere alguns minutos até terminar e tente de novo."
  - q: "“Seu comma não conseguiu baixar o CommaView.”"
    a: "O comma baixa o runtime por conta própria. Confira se ele está conectado à internet, por Wi-Fi ou pelo próprio chip, e tente de novo. O ponto de acesso de um celular com dados móveis funciona."
  - q: "“O download do CommaView chegou ao seu comma incompleto ou corrompido.”"
    a: "Tente de novo. Se acontecer outra vez, copie os detalhes e envie para support@commaview.com."
  - q: "“Seu comma ficou sem espaço de armazenamento durante a instalação.”"
    a: "Tente de novo mais tarde. Se acontecer outra vez, copie os detalhes e envie para support@commaview.com."
  - q: "“O CommaView ainda não é compatível com o software de condução do seu comma.”"
    a: "Seu comma roda um software em que o CommaView não consegue instalar. [Veja com quais forks ele funciona](/pt-br/guides/forks). Para pedir o seu, copie os detalhes e envie para support@commaview.com."
  - q: "“O CommaView não consegue adicionar sua visualização a … com segurança”"
    a: "Seu fork é um que o CommaView não lista, e a verificação viu que a tela dele é diferente no ponto em que o CommaView se conecta. Nada foi alterado no seu comma. Para pedir seu fork, copie os detalhes e envie para support@commaview.com."
  - q: "“O comma 3 não é compatível”"
    a: "O CommaView funciona com o comma 3X e o comma four. A versão do openpilot do comma 3 está congelada e desenha a tela de outro jeito, então o CommaView não consegue mostrar a sobreposição."
  - q: "“O CommaView não iniciou no seu comma após a instalação.”"
    a: "Reinicie seu comma e tente de novo. Se acontecer outra vez, copie os detalhes e envie para support@commaview.com."
  - q: "“Falha na verificação. Não foi possível acessar a API do CommaView em 192.168.1.50:5002.”"
    a: "A instalação terminou, mas seu celular não alcança o runtime. Confira se o celular continua na rede do comma e tente de novo. Se o SSH funciona de um computador mas isto não, o computador está em uma rede em que seu celular não está."
  - q: "“Não foi possível usar o código de emparelhamento. Gere um código novo e tente de novo.”"
    a: "O código expirou, já foi usado ou foi digitado errado. Pegue um novo ([passo 3](#step-pair-code))."
  - q: "“Falha no emparelhamento: a API do runtime do CommaView não estava acessível”"
    a: "Seu celular não alcança o comma nesse endereço. Verifique o ponto de acesso ou a rede e tente de novo."
  - q: "“O CommaView não vai iniciar sozinho após reiniciar”"
    a: "O CommaView está instalado, mas nada o inicia quando seu comma liga: o `/data/continue.sh` do seu comma não tem a linha `exec ./launch_openpilot.sh`. Quando tiver, instale o CommaView de novo."
related: [setup, comma-not-found, support-bundle]
---

## As partes por que a configuração passa

Cada parte precisa da anterior, então verifique nesta ordem:

1. **SSH**, porta 22: como a configuração entra no comma para instalar. Precisa da sua chave no GitHub, do seu usuário do GitHub no comma e do SSH ativado.
2. **A instalação**: o comma baixa o runtime e o instala. Leia o resultado antes de qualquer coisa posterior.
3. **O runtime**, porta 5002 no comma: a configuração verifica se ele responde e depois emparelha com ele.
4. **O emparelhamento**: um código de emparelhamento de uso único dá ao seu celular uma chave própria para o comma.
5. **O vídeo**, portas 8200 a 8202: as câmeras do Live View.

Se a descoberta não encontra o comma mas você sabe o endereço, digitá-lo funciona igualmente: a descoberta é uma conveniência, e o que importa é alcançar o comma.

## Segurança

Faça a configuração, as instalações e a solução de problemas com o carro em P e o openpilot desativado. Nunca configure nem mexa no app enquanto dirige.
