---
title: "CommaView 0.0.165: Transmitir para todos, Enviar ao CommaView e detecção de carros"
description: "O CommaView 0.0.165 libera Transmitir para todos e Enviar ao CommaView para os membros, permite contribuir viagens para a detecção de carros e adiciona mais forks, sem garantia."
date: 2026-11-01
updatedDate: 2026-11-13
slug: commaview-0-0-165-go-live-send-to-commaview
tags:
  - live streaming
  - YouTube
  - recordings
  - openpilot forks
  - privacy
heroLabel: "Notas de versão"
draft: false
---

O CommaView 0.0.165 já está disponível para todos no beta. **Transmitir** agora é para todos, e **Enviar ao CommaView** para cada membro, com uma viagem ou várias de uma vez. Com o novo runtime, os membros podem **contribuir viagens para a detecção de carros**, o CommaView agora instala em **mais forks do openpilot**, sem garantia, e as câmeras e os dados do seu comma vão **só para os celulares emparelhados com ele**.

Ele vem com o runtime `v0.0.61-beta`. **Atualize antes o CommaView em cada celular e central multimídia que assiste ao seu comma**, depois atualize o runtime pelo app quando ele oferecer e reinicie o comma quando o app pedir. Um celular ou central multimídia que ficar no 0.0.164 ou anterior não recebe vídeo de um comma com o runtime v0.0.61 ou mais recente.

## Transmitir

**Transmitir** estava em acesso antecipado no 0.0.164. Agora é para todos: **Transmitir**, no Live View, envia o que o Live View mostra, a via e a sobreposição do CommaView, para o seu canal do YouTube ou qualquer servidor RTMP, em 720p ou 1080p.

Configure uma vez em **Configurações › Transmissão ao vivo**: **Entrar com o YouTube**, que cria, inicia e encerra cada transmissão por você, ou salve uma chave de transmissão ou um servidor. Depois, **Transmitir** aparece no Live View, ou no menu **Mais** dele quando a tela não tem espaço.

- **Quem pode assistir** tem sua própria linha em **Configurações › Transmissão ao vivo** e começa em **Não listado**. Quem assiste vê por onde você dirige.
- O **Som** fica desligado, a menos que você escolha o microfone do seu comma ou do seu celular. Ele vai para a sua transmissão e as suas cópias ao vivo, nunca para o CommaView.
- Quando o Wi‑Fi do seu comma está sem internet, a transmissão usa os dados móveis do seu celular. As configurações mostram mais ou menos quanto por hora.
- Entrar com o YouTube e **Transmitir** agora funcionam quando uma VPN é a rede padrão do seu celular.

O mapa e o cartão de curva da Navegação nunca aparecem numa transmissão.

## Enviar ao CommaView

**Enviar ao CommaView** agora é para cada membro. Em **Gravações**, escolha uma viagem que o seu comma gravou, ou selecione várias, e depois **Enviar ao CommaView** com uma nota sobre o que aconteceu. Recebemos o vídeo da via e grande-angular de cada viagem e o log dela, para podermos ver o problema; nunca a câmera do motorista, o som nem o VIN do seu carro.

Cada viagem é baixada do seu comma antes de ser enviada, uma de cada vez e a mais antiga primeiro, então mantenha o comma ligado e estacionado até terminar. O CommaView aceita 20 envios por dia por conta; os demais esperam o dia seguinte.

A mesma tela **Enviar ao CommaView** agora leva tudo o que você nos envia: um **Problema** ou uma **Ideia**, a sua nota e cada anexo, que você pode abrir com **Ver** ou deixar de fora. Ela abre em **Configurações › Suporte e diagnóstico**, pelo **Relatar** de qualquer erro e pelo menu **Mais** de uma gravação.

## Contribuir para a detecção de carros

O Surround, ainda em acesso antecipado, roda o próprio detector de carros no seu celular. Agora os membros podem ajudar a treiná-lo com as suas viagens. Você precisa do novo runtime no seu comma.

- **Com um toque:** **Contribuir para a detecção de carros**, no menu **Mais** de uma viagem, ou para várias viagens selecionadas.
- **Automaticamente:** ative **Contribuir viagens automaticamente** em **Configurações › Privacidade e dados › Detecção de carros**. As viagens recentes do seu comma são enviadas, qualquer viagem que ele ainda tenha, quando o seu celular e o comma estão numa rede que você permite, até um limite diário. Não com a economia de bateria ligada, nem enquanto você usa o Live View ou grava.

**Enviar contribuições em** escolhe essas redes. **Redes que eu escolher**, o padrão, lista os dados móveis do seu celular e os Wi‑Fi que o seu comma tem salvos; marque os que quer usar, cada um com um limite mensal se quiser. As contribuições ocupam cerca de 110 MB por minuto de viagem. Quando o seu comma entra num Wi‑Fi que ainda não usou, o **Início** e uma notificação perguntam se você quer adicioná-lo. O seu comma diz em que rede está, então o CommaView não precisa da sua localização.

Saiba o que você está dando antes de dar:

- **Uma contribuição é a viagem inteira:** o vídeo da via e grande-angular e o log, incluindo por onde ela passou, do início ao fim.
- **É para sempre.** Ela passa a fazer parte da coleção de treinamento do CommaView e não pode ser removida depois. Nada a liga a você ou ao seu comma.
- **O comma connect espera.** Enquanto uma viagem está sendo enviada, o seu comma a guarda por até um dia para que o openpilot não a apague, e enquanto isso o envio do openpilot a pula.

O app explica isso uma vez antes da sua primeira contribuição, e contribuir fica desligado até você ativar.

## Mais forks do openpilot, sem garantia

O CommaView agora instala em mais forks do openpilot, sem garantia. Ele lista o openpilot e seis forks dele, e verifica cada um antes de cada versão. Em qualquer outro fork do openpilot, a configuração parava. Agora ela verifica o fork, sem mudar nada, e se o CommaView consegue adicionar a sua visualização, ela diz "O CommaView não verificou este fork": o que é desenhado (as câmeras, a trajetória, as faixas, o veículo à frente, os alertas e a velocidade) e o que não é. **Instalar mesmo assim** instala só nesse fork.

O Live View o desenha com o visual do openpilot, ou do sunnypilot quando o fork parte da tela do sunnypilot, e mostra o nome dele, como "BluePilotDev/bluepilot · best effort". **Desinstalar runtime**, em **Configurações do dispositivo**, devolve os arquivos do fork.

Verificados em novembro de 2026: dragonpilot, BluePilot, crwusiz, opgm, zoompilot, o Carrot do jixiexiaoge, NotAutopilot e outros passam na verificação de instalação; não foram testados num carro. [Os forks e os branches verificados](/forks#install-check) estão na página de forks compatíveis.

Dois limites:

- **Sem garantia.** As versões do CommaView não são verificadas com o seu fork. Se o fork se atualizar para algo que o CommaView não consegue acompanhar, a visualização do CommaView se desliga e o fork dirige normalmente.
- **A tela própria do fork não é desenhada.** Os botões, cores e widgets dele não aparecem no Live View, e forks baseados na antiga tela nativa do openpilot não são compatíveis.

## Só celulares emparelhados

Com o novo runtime, as câmeras e os dados do seu comma vão só para os celulares e centrais multimídia emparelhados com ele. Quando outro está com a câmera, o Live View diz "Outro dispositivo está usando a câmera deste comma" e tenta de novo sozinho.

As instalações do runtime agora também se recuperam. Uma queda de energia ou uma reinicialização no meio da instalação devolve a versão anterior, uma instalação continua quando o app para de escutar, e um download que trava continua de onde parou.

## Também no 0.0.165

- **Várias viagens de uma vez.** Selecione viagens em **Gravações** para compartilhá-las, fazer as reproduções, enviá-las ou excluí-las juntas.
- **O Live View cabe em qualquer tela.** Os controles não rolam mais nem cortam o **Sair**: o que não cabe vai para **Mais**, e um texto maior leva controles para **Mais** em vez de encolher qualquer coisa. O Live View também está mais leve para o celular, e se recupera sozinho em vez de travar.
- **Suas solicitações.** Quando você relata um problema ou envia uma ideia com a conta conectada, podemos responder. **Configurações › Suporte e diagnóstico › Suas solicitações** mostra as nossas respostas, você recebe um e-mail e a conversa continua em my.commaview.com.
- **Configurações reorganizadas.** **Privacidade e dados** diz o que sai do seu celular. **Ajude a melhorar o CommaView** pergunta uma vez se deve enviar relatórios de falhas e qual software de condução o seu comma roda.
- **O ranking, para cada membro.** Ele não depende mais de uma ativação por conta.
- **Modo experimental no openpilot mais recente.** No nightly do openpilot e no sunnypilot dev, onde o modo chill não existe mais, o Live View mostra o modo experimental como o openpilot faz.
- **Apoiar o CommaView.** **Configurações › Suporte e diagnóstico › Apoiar o CommaView** abre a nossa página no [Buy Me a Coffee](https://buymeacoffee.com/commaview), para ajudar a cobrir a hospedagem, os testes e o app para iOS. Não desbloqueia nada.
- **Correções.** Uma central multimídia com Android 16 não fecha mais o CommaView no Live View quando o decodificador de vídeo dela falha, e a tela do comma 3X do StarPilot desenha a câmera nas centrais multimídia que a mostravam preta.

## Acesso antecipado: Navegação e Surround

**Navegação**, **Surround**, **Surround V2** e **Ferramentas experimentais** continuam com um grupo limitado de testadores, ativados por conta, enquanto reunimos opiniões.

- A **Navegação** agora mostra um mapa no Live View durante um trajeto, ao lado do vídeo ou no canto dele, e **Para onde?** quando não há trajeto. No mapa do canto, encerrar e silenciar estão sempre à mão, encerrar pode ser desfeito por 8 segundos, e você pode dizer para onde ir.
- **O mapa da Navegação** agora tem os temas **Claro** e **Escuro**, que trocam ao nascer e ao pôr do sol onde o seu comma está, para ser lido no sol. Escolha **Auto**, **Igual ao celular**, **Claro** ou **Escuro** em **Configurações › Mapas e navegação › Tema do mapa**.
- O **Surround V2** é um segundo renderizador experimental para o Surround, em **Configurações › Ferramentas experimentais**.

Alguns deles rodam em serviços pagos, como o cálculo de rotas da Navegação, então por enquanto estamos mantendo o grupo pequeno. Se quiser ajudar a testar, fale com a gente no nosso [Discord](https://discord.gg/UuMhz9K8ft) e esteja pronto para contar como eles se saem nas suas viagens.

## Como atualizar

O CommaView está num beta só para convidados. Se você já participa, o app oferece o 0.0.165 sozinho.

1. Atualize o CommaView em **cada celular e central multimídia** que você usa com o seu comma.
2. Depois, atualize o runtime do seu comma pelo app.
3. Reinicie o comma quando o app pedir. As atualizações do runtime esperam o carro estar em P com o openpilot desativado, então nunca interrompem uma viagem.

Novo no CommaView? O [guia de configuração](/pt-br/guides/setup) mostra como instalar o app e conectar o seu comma.

## Leia também

- [Quais forks do openpilot funcionam com o CommaView](/forks), e [os forks que ele não lista](/forks#unlisted)
- [Novidades](/whats-new) de cada versão
- [Como funcionam as versões do CommaView](/pt-br/guides/releases)
- [Política de privacidade](/privacy) (em inglês), sobre o que Transmitir, Enviar ao CommaView e as contribuições compartilham

O CommaView não é oficial e não é afiliado à comma.ai, ao sunnypilot nem a nenhum fork do openpilot com que funciona. É software beta e não é um sistema de segurança: nunca deixe que ele tire sua atenção da direção.

## Correção, 13 de novembro de 2026

Em **Contribuir para a detecção de carros**, este post dizia que nada numa contribuição a liga a você ou ao seu comma. Isso foi longe demais. Uma contribuição não nomeia você nem o seu comma, mas a rota e o vídeo de uma viagem podem mostrar por onde você dirige. A partir da próxima versão do app, o app diz isso e pede que você concorde de novo antes da sua próxima contribuição; a [política de privacidade](/privacy) já dizia que uma contribuição inclui a rota da viagem. O resto do post continua como foi publicado.
