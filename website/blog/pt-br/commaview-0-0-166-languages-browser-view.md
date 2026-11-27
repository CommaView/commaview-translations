---
title: "CommaView 0.0.166: uma chave para cada celular, mais 11 idiomas e Browser View"
description: "O CommaView 0.0.166 dá uma chave a cada celular, fala mais 11 idiomas, mostra o Live View no navegador do carro, guarda viagens no celular e abre a loja de pacotes."
date: 2026-11-16
slug: commaview-0-0-166-languages-browser-view
tags:
  - security
  - languages
  - browser view
  - recordings
  - overlay packs
heroLabel: "Notas de versão"
draft: false
---

O CommaView 0.0.166 já está disponível para todos no beta. Com o novo runtime, **cada celular recebe uma chave própria** para o seu comma, e ninguém precisa emparelhar de novo. O CommaView fala **mais 11 idiomas**, mostra o Live View no navegador do seu carro com o **Browser View**, guarda as suas viagens no celular com **Salvar este momento**, **Exportar viagem inteira…** e **Buscar viagens automaticamente**, e abre a **loja de pacotes de sobreposição**.

Ele vem com o runtime `v0.0.62-beta`. **Atualize antes o CommaView**, depois o runtime pelo app quando ele oferecer, e reinicie o comma quando o app pedir. Um celular ainda no 0.0.165 continua funcionando por 90 dias depois que o primeiro celular do seu comma recebe a chave. Não configure o seu comma de novo a partir de um celular no 0.0.165: a configuração feita nele recoloca o runtime antigo, e os celulares com chave não conseguem acessar o comma com ele.

## Uma chave para cada celular

Com o novo runtime, cada celular recebe uma chave própria para o seu comma, no lugar do token compartilhado que todos os celulares enviavam. A chave nunca atravessa a rede, e ninguém precisa emparelhar de novo: um celular no 0.0.166 recebe a chave na próxima vez que se conecta.

- **Um celular novo tem chave.** Cada celular com chave é avisado quando outro recebe uma, com **É meu**, **Remover** e **Ver celulares**, que abre **Configurações do dispositivo › Emparelhar outro celular**, onde aparecem todos os celulares com chave.
- **Adicionar um celular.** **Mostrar convite** num celular com chave dá um código ou um QR code, válido por 10 minutos.
- **Apps mais antigos.** O seu comma aceita o antigo token compartilhado por 90 dias depois que o primeiro celular recebe uma chave, ou até alguém tocar em **Parar agora**. Até lá, **Código de emparelhamento para um app mais antigo** emparelha um celular com uma versão anterior do CommaView. Depois disso, um celular sem chave precisa do 0.0.166 e de um convite.

## O CommaView no seu idioma

**Configurações › Idioma** agora oferece Deutsch, Español, Français, 日本語, 한국어, Português (Brasil), ไทย, Türkçe, Українська, 简体中文 e 繁體中文 além do inglês. **Idioma do celular**, o padrão, usa o primeiro idioma da lista do seu celular que o CommaView tem, ou o inglês, e a linha diz qual está usando. No Android 13 e mais recentes, a configuração de idioma por app do Android também funciona.

Todos os idiomas, menos o inglês, são **traduzidos automaticamente**, e nenhum falante nativo revisou nenhum deles ainda, então espere palavras erradas e frases estranhas. Um cartão no topo das Configurações avisa isso, e **Ajude a melhorar** abre as traduções do CommaView, onde qualquer pessoa pode sugerir uma palavra melhor. Você também pode nos contar no [Discord](https://discord.gg/UuMhz9K8ft) ou em **Relatar um problema ou enviar uma ideia**: diga a tela e o que ela diz agora.

- **As telas do seu comma ficam no idioma do seu comma.** Os rótulos de um fork e os alertas do seu comma são desenhados como o seu carro os mostra, agora na fonte do próprio fork quando o seu comma está em chinês, japonês, coreano ou tailandês.
- **Vale o texto em inglês** para o consentimento do ranking, e **Ver em inglês** o mostra. A política de privacidade e os termos estão em inglês.
- **As datas** seguem a ordem do seu idioma, e o título e a descrição do YouTube em Transmitir, até você mudá-los, ficam no idioma do app.
- **O coreano** mantém as palavras inteiras no fim da linha. No Android 13 e anteriores, um nome em coreano que você deu a um comma ou a um lugar ainda pode quebrar.

## Browser View

O Browser View mostra o que o Live View mostra no navegador do seu carro, servido pelo seu celular pelo ponto de acesso ou pelo Wi‑Fi. Inicie em **Live View › Detalhes › Browser View**, digite o link curto, `commaview.app/<code>`, no navegador do carro e toque em **Abrir**. Num Tesla, primeiro **Ativar endereço VPN**.

A imagem vai do seu celular para o carro, nunca pela internet; só a página do link curto vai. Com a conta conectada, o seu celular recebe um nome próprio e um certificado confiável, então um Tesla mostra um cadeado e a imagem H.264, mais fluida. Sem conta conectada, um Tesla recebe a imagem básica.

- **Controles no carro**: **Gravar**, **Salvar**, **Mapa**, a tela de condução, **Transmitir** e **Câm. int.**, ao lado da imagem ou embaixo dela, nunca por cima.
- **Sem internet no carro?** **Mostrar endereços** lista os endereços do próprio celular.
- 720p ou 1080p, códigos de oito dígitos, e **Iniciar com o Live View** para iniciar sempre que o Live View abrir.

Cada passo, inclusive o de um Tesla: [Browser View](/pt-br/guides/browser-view).

Enquanto ele roda, o seu celular envia ao serviço de contas do CommaView o código, as portas e o endereço privado dele, para que o link curto consiga encontrá-lo. Qualquer pessoa com o código pode vê-los, e o nome `commaview.app` do seu celular, enquanto o Browser View roda e por até 2 horas depois se ele parar inesperadamente, mas nenhum deles abre nada sem o ponto de acesso ou o Wi‑Fi do seu celular. Eles são excluídos 30 dias depois da última vez que o Browser View rodou. O nome `commaview.app` do seu celular e a data do último certificado ficam enquanto a sua conta existir, e o nome aparece em registros públicos de certificados. [A política de privacidade](/privacy) (em inglês) tem os detalhes.

## As suas viagens no seu celular

- **Salvar este momento.** **Salvar**, no Live View, guarda os últimos 3 minutos e o minuto seguinte de uma viagem; outro toque dentro desse minuto acrescenta um minuto, até 10 minutos. Nada é baixado enquanto você dirige: quando você estaciona, tudo é copiado num MP4 no seu celular.
- **Exportar viagem inteira…** No menu **Mais** de uma viagem: a câmera da via num só MP4, em partes acima de 3,5 GB. A tela diz o tamanho e se cabe antes de baixar qualquer coisa.
- **Buscar viagens automaticamente.** **Configurações › Gravações**: as viagens novas são copiadas em casa mais ou menos a cada meia hora nas redes Wi‑Fi que você escolher, só por Wi‑Fi, até o espaço que você der a elas. Uma hora de direção dá cerca de 4,5 GB.
- **Ficou sem energia?** **Gravações** avisa quando o seu comma perdeu energia no fim de uma viagem e diz como resolver.

Tudo é a câmera da via sem HUD, e fica no seu celular mesmo depois que o seu comma descarta a viagem.

## Pacotes de sobreposição

**Configurações › Pacotes de sobreposição**, ou o cartão no **Início**, abre a loja. Os pacotes adicionam ao Live View o que o seu fork desenha na própria tela, como os medidores híbridos do BluePilot ou a trajetória arco-íris do dragonpilot. Os membros navegam pelos pacotes **Oficiais** do CommaView, os da **Comunidade** e **Para seu comma**, cada um com uma prévia para o design que o Live View desenha. **Seus pacotes** tem um botão para o seu celular e cada comma emparelhado. Sem assinatura, você pode adicionar um pacote a partir de um arquivo ou de um link.

## Também no 0.0.166

- **Navegação com a sua própria chave do Stadia Maps**, para membros: **Configurações › Mapas e navegação › Sua chave do Stadia Maps**.
- **BluePilot, dragonpilot e OPGM** passam a ser forks listados, com o novo runtime. Nenhum foi dirigido com o CommaView ainda.
- **Live View em mais centrais multimídia**: quando o decodificador de vídeo do celular não consegue tocar o vídeo do comma, ele tenta outro.
- **Abrir o CommaView sozinho** quando uma central multimídia liga ou o Bluetooth conecta, e **Abrir o Live View ao conectar**, em **Configurações › Tela**. Para rodar o CommaView na tela do próprio carro: [as melhores AI boxes Android](/pt-br/blog/android-ai-box-commaview).
- **Compartilhar com o desenvolvedor do meu fork…**: um clipe, um resumo e o log do CommaView, para você mesmo compartilhar.
- **O Live View diz o que está acontecendo**: uma reinicialização que ele está esperando, dados do carro que pararam, uma imagem com atraso, por que está reconectando, outro dispositivo que está com ele aberto.
- **Atualizar o CommaView**, para membros, a partir do 0.0.166: a versão primeiro, **Cancelar download**, e o download continua em segundo plano.
- **Bordas da tela**, destinos de Transmitir para cada plataforma, e nada cortado com texto grande.

## Acesso antecipado

Transmitir para X, Twitch, Kick e Facebook, **Só vídeo** para FrogPilot e KisaPilot, as configurações do fork, a criação de pacotes de sobreposição e o Surround continuam ativados por conta, para um grupo limitado de testadores. Se quiser ajudar a testar, fale com a gente no nosso [Discord](https://discord.gg/UuMhz9K8ft) e esteja pronto para contar como eles se saem nas suas viagens.

## Como atualizar

O CommaView está num beta só para convidados. Se você já participa, o app oferece o 0.0.166 sozinho. Atualize o CommaView, depois o runtime do seu comma pelo app, e reinicie o comma quando ele pedir. Atualize cada celular e central multimídia que assiste ao seu comma em até 90 dias depois que o primeiro receber a chave.

## Leia também

- [Quais forks do openpilot funcionam com o CommaView](/forks)
- [Novidades](/whats-new) de cada versão
- [Como funcionam as versões do CommaView](/pt-br/guides/releases)

O CommaView não é oficial e não é afiliado à comma.ai, ao BluePilot, ao dragonpilot, ao OPGM nem aos outros forks citados. É software beta e não é um sistema de segurança: nunca deixe que ele tire sua atenção da direção.
