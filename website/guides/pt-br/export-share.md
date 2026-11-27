---
title: "Compartilhar e exportar gravações"
description: "Compartilhe uma reprodução ou uma cópia ao vivo em Gravações, abra em outro app ou exporte uma viagem inteira do seu comma como um só MP4 no seu celular."
topic: recordings
order: 3
kind: walkthrough
lede: "Cada gravação no seu celular é um MP4 que você pode compartilhar, salvar nos seus arquivos ou abrir em outro app, pelo menu **Ações da gravação** em Gravações. **Exportar viagem inteira…** também copia do seu comma para o celular o vídeo da via de uma viagem inteira, como o comma gravou."
parked: true
updated: 2026-11-27
needs:
  - title: "Uma gravação no seu celular"
    text: "Uma reprodução ou uma cópia ao vivo em Gravações. Ainda não? [Gravar uma viagem](/pt-br/guides/record) ou [gravar uma cópia ao vivo](/pt-br/guides/live-copy)."
  - title: "Para uma viagem inteira"
    text: "O comma que a gravou, emparelhado com este celular, estacionado e ao alcance, e um runtime que liste as viagens."
steps:
  - id: open
    title: "Abra a gravação"
    body: |
      Abra **Gravações** pela barra de baixo (a barra lateral em uma tela maior) e toque na viagem. Ela abre na tela de reprodução, com o player e os dados.
    screen: phone-recordings
    pins:
      - text: "Uma reprodução. Toque em qualquer viagem para abrir."
      - target: live-copy-row
        text: "Uma cópia ao vivo, marcada como **Cópia ao vivo**."
      - target: filter
        text: "**Filtrar**: **Prontas** mostra só as viagens com um vídeo para compartilhar."
  - id: actions
    title: "Abra Ações da gravação"
    body: |
      Na tela de reprodução, toque em **Ações da gravação**, o botão Mais ao lado da hora e da data.
    screen: recordings-watch
    pins:
      - target: more
        text: "**Ações da gravação**."
      - text: "**Tela cheia** reproduz ocupando a tela."
  - id: share
    title: "Compartilhe ou abra em outro app"
    body: |
      **Compartilhar** entrega o vídeo ao menu de compartilhamento do Android, onde você pode enviá-lo ou salvá-lo nos seus arquivos. **Abrir em outro app** reproduz em outro player de vídeo.

      **Arquivos**, quando uma viagem tem vários, lista cada arquivo para compartilhar separadamente, como cada parte de uma viagem inteira longa.
    screen: recordings-watch-menu
    pins:
      - target: share
        text: "**Compartilhar**: o menu de compartilhamento do Android."
      - target: open-in
        text: "**Abrir em outro app**."
      - target: send
        text: "**Enviar ao CommaView…** envia ao CommaView um problema com esta viagem: [Enviar um pacote de suporte](/pt-br/guides/support-bundle)."
    note: "O menu de compartilhamento do Android não aparece na imagem: ele é do Android e muda de celular para celular."
    warn: "Um vídeo pode mostrar mais que a via: onde e quando você dirigiu, placas, rostos e lugares, e a câmera do motorista em uma cópia ao vivo feita com Câm. int. ativada. Confira antes de compartilhar."
  - id: export
    title: "Exporte uma viagem inteira"
    body: |
      Para uma viagem que seu comma gravou, **Ações da gravação** tem **Exportar viagem inteira…**. Ele copia a câmera da via do comma da viagem inteira para um só MP4 no seu celular, exatamente como o comma gravou. Não tem HUD: **Gerar reprodução** desenha a tela de condução sobre as partes que você gravou.
    screen: recordings-watch-menu
    pins:
      - target: export-drive
        text: "**Exportar viagem inteira…**"
  - id: export-sheet
    title: "Confira o tamanho e toque em Exportar"
    body: |
      A folha diz quanto da viagem o comma tem, como **23 min · cerca de 1,7 GB**, e o espaço livre no seu celular. Toque em **Exportar**: “Exportando a viagem inteira. Ela é salva em Gravações quando o comma estiver estacionado.”

      Nada é baixado até você tocar em Exportar. A partir daí o comma guarda a viagem enquanto ela é copiada; até lá, ele ainda pode excluí-la para abrir espaço, começando pelas viagens mais antigas.
    screen: recordings-export
    pins:
      - target: export
        text: "**Exportar**."
      - target: cancel
        text: "**Cancelar** desiste."
  - id: whole-drive
    title: "Encontre a viagem inteira em Gravações"
    body: |
      A exportação é uma linha própria, **Viagem inteira**, ao lado da gravação de onde você a pediu. Enquanto espera, ela diz o motivo, como **Aguardando você estacionar**, e depois **Salvando do comma** com o progresso. Depois de salva, ela roda e é compartilhada como qualquer gravação.
    screen: phone-recordings
    pins:
      - text: "A linha **Viagem inteira**, com o título de quando a viagem começou."
    note: "Uma viagem com mais de cerca de 45 minutos de vídeo da via é salva em partes de 3,5 GB: **Arquivos** lista cada uma."
check: "O menu de compartilhamento do Android abre com o vídeo. Para uma viagem inteira, a linha dela roda, e o dado **Salva** da tela de reprodução mostra **A viagem inteira · neste celular**."
fixes:
  - q: "**Exportar viagem inteira…** não está no menu"
    a: "Ele aparece para uma viagem que seu comma gravou, enquanto esse comma está emparelhado com este celular e o runtime dele lista as viagens. [Atualize o runtime do comma](/pt-br/guides/update-runtime) se ele for mais antigo. Uma cópia ao vivo não tem uma viagem do comma para exportar."
  - q: "**Exportar viagem inteira…** está acinzentado: “Já exportada”, “Sendo exportada” ou “A cópia parou: Tentar salvar de novo na linha dela”"
    a: "A viagem já foi exportada, ou a exportação está a caminho. Se ela parou, abra a linha **Viagem inteira** e escolha **Tentar salvar de novo** no menu dela."
  - q: "“O comma não tem esta viagem, então ela não pode ser exportada.”"
    a: "O comma a excluiu para abrir espaço para viagens mais novas. Nada pode trazê-la de volta."
  - q: "“Esta viagem é mais antiga que as 50 que o comma lista, então não pode ser encontrada para copiar.”"
    a: "Seu comma lista as 50 viagens mais recentes, e esta é mais antiga, então a exportação não a encontra."
  - q: "“Requer cerca de 2,2 GB livres. Libere espaço antes.”"
    a: "Exclua viagens de que não precisa mais, ou escolha outro armazenamento em **Configurações › Gravações**, e abra a folha de novo."
  - q: "A viagem inteira mostra “Aguardando você estacionar”, “Aguardando alcançar o comma” ou “Aguardando enquanto o Live View está aberto”"
    a: "Ela só é copiada enquanto o comma está estacionado, ao alcance do seu celular e sem mostrar o Live View. Continua sozinha assim que puder."
  - q: "“Nenhum player de vídeo encontrado”"
    a: "Não há outro app de vídeo neste dispositivo para **Abrir em outro app**. Reproduza em Gravações, ou use **Compartilhar** para salvar nos seus arquivos."
  - q: "“Esta reprodução não roda aqui. Tente outro app.”"
    a: "Use **Abrir em outro app**, ou compartilhe com um app que a reproduza."
related: [record, live-copy, support-bundle]
---

## Compartilhar várias de uma vez

Toque e segure uma viagem para selecioná-la, depois toque em outras para adicioná-las. A barra de baixo diz quantas estão selecionadas. O menu **Mais** dela tem **Compartilhar**, que entrega todos os vídeos selecionados juntos ao menu de compartilhamento do Android, e a barra tem **Excluir**. Uma viagem que ainda não tem vídeo no seu celular fica de fora, e a ação diz quantas inclui.

## Buscar viagens novas automaticamente

**Configurações › Gravações › Buscar viagens novas** traz para casa a câmera da via de cada viagem nova sem nenhum toque: mais ou menos a cada meia hora, enquanto seu celular e seu comma estão em um Wi-Fi que você escolhe em **Redes Wi-Fi** e o carro está estacionado. Cada viagem buscada é uma linha **Do comma** em Gravações, sem HUD, como uma viagem inteira. **Espaço para viagens buscadas** limita o espaço que elas ocupam: 10, 20 ou 50 GB, ou **Sem limite**. Elas nunca são excluídas para abrir espaço.

## Para onde vão

Os arquivos compartilhados vão só para onde você os envia. As gravações ficam no seu celular, e o backup do Android e a transferência para um celular novo as deixam de fora.
