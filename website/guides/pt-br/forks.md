---
title: "Verifique se seu comma e seu fork são compatíveis"
description: "O CommaView funciona com openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot e OPGM, e sem garantia com outros forks."
topic: start
order: 2
kind: reference
lede: "O CommaView mostra a câmera da via do seu comma com a sobreposição de condução do software que ele roda. Funciona com o openpilot e nove forks dele, no comma 3X e no comma four, e, sem garantia, com outros forks do openpilot. A configuração verifica qual fork seu comma roda antes de mudar qualquer coisa."
updated: 2026-11-27
needs:
  - title: "Um comma 3X ou comma four"
    text: "O comma 3 não é compatível, nem as versões dos forks para comma 3, como xnor-c3. [Por que o comma 3 não é compatível](/pt-br#faq-comma-3)."
  - title: "Seu fork, como ele roda"
    text: "Instalado e rodando normalmente. O CommaView adiciona o runtime ao lado dele e nunca muda a forma como ele dirige."
steps:
  - id: unlisted
    title: "Em um fork que o CommaView não lista, a configuração pergunta antes"
    body: |
      A configuração guiada verifica de qual repositório o software do seu comma foi instalado e instala o hook do CommaView para esse fork. Em um fork que não está na lista, ela primeiro verifica o fork, sem mudar nada.
    tabs:
      - label: "Sem garantia"
        body: "Se o CommaView consegue adicionar sua visualização, a configuração mostra **O CommaView não verificou este fork**. Ela identifica o fork pelo repositório e diz o que é desenhado (as câmeras, o caminho, as faixas, o carro à frente, os alertas e a velocidade) e o que não é (os botões, cores e widgets do próprio fork). **Instalar mesmo assim** instala nesse fork, e só nele. **Voltar** retorna à escolha do comma; nada foi instalado."
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**Instalar mesmo assim** adiciona a visualização do CommaView a este fork, sem garantia."
      - label: "Só vídeo (acesso antecipado)"
        body: "Para FrogPilot e KisaPilot, cujas telas não aceitam a visualização do CommaView, testadores com a opção Só vídeo veem **Só vídeo neste fork**: o CommaView transmite as câmeras e desenha a própria visualização a partir dos dados de condução, sem mudar nada no fork. Isso ainda não foi testado em um comma. Sem a opção, a configuração diz que o fork não é compatível e não muda nada."
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**Instalar só vídeo**."
    note: "Quando a verificação recusa um fork, a configuração diz “O CommaView não consegue adicionar sua visualização a … com segurança” e “Nada foi alterado no seu comma.”"
  - id: details
    title: "Veja qual fork o Live View desenha"
    body: |
      No Live View, abra **Detalhes**. A linha **Software** mostra o fork do seu comma, e um fork que o CommaView não lista aparece pelo repositório, como “crwusiz/openpilot · best effort”.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**Detalhes**, abaixo da imagem."
      - text: "**Software**: o fork que seu comma roda."
related: [setup, overlays, uninstall]
---

## Forks compatíveis

| Fork | De onde vem | Compatível desde |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | A primeira beta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | A primeira beta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot, antes github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor** (versões xnor e rx) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot, instalado de i.carrotpilot.app | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

Em um fork que não está na lista, a configuração verifica se o CommaView consegue adicionar sua visualização e pergunta antes; se não consegue, ela para e deixa seu comma como estava.

## O que cada fork mostra

### openpilot

O software da própria comma.ai. O Live View desenha a tela do comma four, a do comma 3X ou a sobreposição do próprio CommaView, com sua velocidade, MÁX, o limite de velocidade, o carro à frente e as mudanças de faixa.

### sunnypilot

O CommaView desenha a tela do sunnypilot com o que o sunnypilot acrescenta: os estados só direção e só velocidade do MADS, a assistência de limite de velocidade, o caminho arco-íris e os indicadores de ponto cego, e na tela do comma 3X a placa de limite de velocidade, o controle de cruzeiro inteligente e a interface de desenvolvedor. Ele lê suas configurações do sunnypilot, então a tela fica igual à do comma.

### StarPilot

O StarPilot mostra seus modos de condução por cores, e o CommaView usa as cores que o StarPilot escolheu: a borda, o caminho e os widgets nas telas do comma four e do comma 3X, os alertas e a escolha de câmera, inclusive a câmera do motorista.

Desative a configuração **Disable Logging** do StarPilot. Ela para o codificador de vídeo do qual o Live View transmite.

### O openpilot da xnor-tech: xnor e rx

O openpilot da xnor-tech vem em duas versões. As branches **xnor** rodam a tela do openpilot e as branches **rx** a do sunnypilot, cada uma com os ports de carros da xnor-tech. O CommaView desenha a que seu comma rodar, com os alertas como o comma os escreve.

Em um Rivian com rx, o volante fica verde enquanto o carro esterça por ângulo e azul enquanto esterça por torque: o volante do comma four e, na tela do comma 3X, o do botão do modo experimental.

### AdventurePilot

O AdventurePilot é um fork do sunnypilot com ports de carros próprios. O CommaView desenha a tela do sunnypilot com o que o AdventurePilot acrescenta:

- o indicador de centralização na faixa: uma pílula com o empurrão e o deslocamento na tela do comma 3X, uma barra compacta na do comma four;
- o chip CURVE na tela do comma 3X, que pisca enquanto o controle de velocidade em curvas atua;
- a cor do volante conforme o modo de direção, e uma barra de torque que mostra a aceleração lateral enquanto um Rivian esterça pelo canal de ângulo.

### SunnyPilot-TeslaHW1

O SunnyPilot-TeslaHW1 é um fork do sunnypilot que adiciona os carros Tesla HW1 (Autopilot 1). A tela dele é a do sunnypilot, então o CommaView desenha a tela do sunnypilot com tudo o que o sunnypilot acrescenta e mostra o nome do fork no app.

O `op fork update` dele não consegue trocar o fork enquanto o hook do CommaView está instalado: primeiro [desinstale o runtime do CommaView](/pt-br/guides/uninstall), ou use o seletor de forks na tela do comma, que funciona normalmente.

### carrotpilot

O carrotpilot é um fork do openpilot para carros Hyundai, Kia e Genesis, instalado de `i.carrotpilot.app`. O CommaView desenha a tela do openpilot para ele, com sua velocidade, o caminho, as faixas e o carro à frente. O que o carrotpilot acrescenta à própria tela, como a navegação, os radares e o HUD, ainda não é desenhado.

A atualização automática do carrotpilot e as ferramentas de Git da página web dele removem o hook do CommaView até o comma reiniciar. O app pede o reinício, e o Live View volta depois.

### BluePilot, dragonpilot e OPGM

Na lista desde o CommaView 0.0.166 com seu runtime. O CommaView mostra o nome de cada um e o desenha no visual da base: o BluePilot como sunnypilot, o dragonpilot e o OPGM como openpilot, com o ALKA do dragonpilot mostrado como direção. Um comma que rodava um deles sem garantia passa para ele na inicialização após a atualização do runtime. Nenhum deles foi dirigido com o CommaView ainda. Os [pacotes de sobreposição](/pt-br/guides/overlays) oficiais do CommaView desenham mais das telas próprias do BluePilot e do dragonpilot.

## Forks que o CommaView não lista

A partir do CommaView 0.0.165, com o runtime dele no seu comma, a configuração pode adicionar a visualização do CommaView a um fork do openpilot que não está na lista, sem garantia. O Live View desenha o fork no visual do openpilot, ou no do sunnypilot quando o fork se baseia na tela do sunnypilot. Para desfazer, **Desinstalar runtime** nas Configurações do dispositivo devolve os arquivos do fork como estavam.

- **Sem garantia.** As versões do CommaView não são testadas com o seu fork. Se o fork se atualizar para algo que o CommaView não acompanha, a visualização do CommaView é desativada e seu fork dirige e mostra a própria tela normalmente, até uma versão do CommaView tratar a mudança.
- **Nem todo fork.** Forks baseados na antiga tela nativa do openpilot não são compatíveis (abaixo).
- **Seu sim vale para aquele fork.** Se seu comma mudar para outro fork que o CommaView não lista, o CommaView pergunta de novo na configuração antes de adicionar sua visualização lá.

### Forks que passam na verificação de instalação (sem garantia)

Cada um destes **passa na verificação de instalação do CommaView; sem garantia, não testado em um carro.** Verificado em novembro de 2026, para as branches indicadas, com o runtime que o CommaView 0.0.165 instala: o instalador oferece o fork, adiciona a visualização do CommaView quando você concorda e a verifica, como faria no seu comma. Nada aqui foi testado em um comma dentro de um carro, um fork pode não suportar todos os carros nos dois dispositivos, e a próxima atualização de um fork pode mudar a resposta.

| Fork | Branches verificadas | Dispositivos | Desenhado como |
| --- | --- | --- | --- |
| **crwusiz** (github.com/crwusiz/openpilot) | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **Carrot do jixiexiaoge** (github.com/jixiexiaoge/openpilot) | Carrot | comma four, comma 3X | openpilot |
| **MoreTore** (github.com/MoreTore/openpilot) | release-mici | comma four | openpilot |
| **zoompilot** (github.com/zoompilot/zoompilot) | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato** (github.com/AlexandreSato/openpilot) | master | comma four, comma 3X | openpilot |
| **lukasloetkolben** (github.com/lukasloetkolben/openpilot) | master | comma four, comma 3X | openpilot |
| **mvl-boston** (github.com/mvl-boston/openpilot) | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub** (github.com/mouxangithub/openpilot) | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro** (github.com/programanichiro/openpilot) | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2** (github.com/infiniteCable2/openpilot) | master | comma four, comma 3X | sunnypilot |
| **herizon1054** (github.com/herizon1054/openpilot) | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot** (github.com/NotAutopilot/openpilot) | nap-release, naponsp-alpha | comma four, comma 3X | openpilot (nap-release), sunnypilot (naponsp-alpha) |

Seu fork não está aqui? Ele ainda pode funcionar: a configuração o verifica antes de mudar qualquer coisa.

### Não compatíveis

As telas destes forks não aceitam a visualização do CommaView, então a configuração avisa e não muda nada no seu comma:

- **FrogPilot** (github.com/FrogAi/FrogPilot). Roda a antiga tela nativa (Qt) do openpilot, que não tem lugar para a visualização do CommaView. O Só vídeo está em acesso antecipado.
- **KisaPilot** (github.com/kisapilot/openpilot). A tela em Python dele está desativada: roda a antiga tela nativa (Qt) do openpilot. O Só vídeo está em acesso antecipado.
- **IQ.Pilot** (github.com/IQLvbs/iqpilot). Desde outubro de 2026 roda sobre o próprio IQ.OS; o suporte espera até o CommaView poder tratá-lo como um fork próprio.
- **hikee9123** (github.com/hikee9123/openpilot). Roda a antiga tela nativa (Qt) do openpilot.

**Acesso antecipado: só vídeo para FrogPilot e KisaPilot.** Com a opção Só vídeo, a configuração oferece mostrar as câmeras deles no Live View com a sobreposição do próprio CommaView no lugar das telas deles, sem mudar nada no fork. Isso ainda não foi testado em um comma. Sem a opção, a configuração continua dizendo que eles não são compatíveis e não muda nada.

## Quais dispositivos comma

O comma 3X e o comma four. O comma 3 não é compatível, nem as versões dos forks para comma 3, como xnor-c3: [por que o comma 3 não é compatível](/pt-br#faq-comma-3). O app roda em um celular, tablet ou central multimídia Android.

## Branches de lançamento e de desenvolvimento

Antes de cada versão, o runtime do CommaView é compilado e verificado com as versões de lançamento destes forks. A nightly do openpilot e a branch dev do sunnypilot são verificadas em cada dia em que mudam, como aviso antecipado. Uma branch de desenvolvimento pode mudar mais rápido que o CommaView: se uma mudança impedir o hook do CommaView de carregar, a tela e a condução do seu fork continuam normalmente.

## Seu fork não está na lista?

Teste sem garantia e peça para incluí-lo no quadro de recursos em [my.commaview.com](https://my.commaview.com), ou envie uma ideia pelo app (Configurações › **Suporte e diagnóstico**). Um fork da lista é verificado antes de cada versão. Veja as [novidades](/whats-new) de cada versão.

## Perguntas

**O CommaView muda a forma como meu fork dirige?** Não. Ele adiciona um pequeno runtime ao lado do seu fork e um pequeno hook na interface de tela dele, para que o CommaView possa desenhar o mesmo caminho, as faixas e os alertas. A forma como seu carro dirige não muda.

**O CommaView funciona com o StarPilot?** Sim, desde o CommaView 0.0.162. O Live View mostra as cores, os widgets e a escolha de câmera do próprio StarPilot. Desative a configuração **Disable Logging** do StarPilot, que para o codificador de vídeo do qual o CommaView transmite.

**O CommaView funciona com o carrotpilot?** Sim, desde o CommaView 0.0.164. O Live View desenha a tela do openpilot para ele; o que o carrotpilot acrescenta à própria tela, como a navegação e os radares, ainda não é desenhado. Depois que o carrotpilot se atualiza sozinho, o app pede um reinício que traz o Live View de volta.

**O CommaView funciona com o FrogPilot?** Ainda não: ele roda a antiga tela nativa (Qt) do openpilot, que não tem lugar para a visualização do CommaView, então a configuração diz que ele não é compatível e não muda nada. O Só vídeo está em acesso antecipado para FrogPilot e KisaPilot, para testadores.
