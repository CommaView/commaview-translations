# Português do Brasil glossary

The words every Brazilian Portuguese string uses for CommaView's terms, so screens translated apart say the same
thing. Where openpilot already translates a term (`selfdrive/ui/translations/app_pt-BR.po`, taken from the `v0.10.1`
tag: master no longer has it), its word is used, so the app says what the car's screen says. Brazilian usage
throughout. Machine drafted; a native speaker's review is owed before release
(the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`). Gender follows the thing
a name stands for: *o* comma (o dispositivo), *o* app, *o* fork.

## Style

- Address the person as **você**, as openpilot's translation does ("Tem certeza de que deseja desligar?", "Emparelhe
  seu dispositivo"). Imperatives in the você form: Toque, Abra, Conecte, Digite.
- Brazilian words: **celular** (not telemóvel or telefone), **tela**, **arquivo**, **app**, **baixar**, **salvar**.
  openpilot writes "telefone" ("no seu telefone"); the app says celular, as Brazilians do.
- Names of settings, switches and files quoted in running text take “ ” (“Localização do veículo”, “Disable
  Logging”); nested quotes ‘ ’. Ellipsis stays ….
- Sentence case for titles and buttons (only the first word and names capitalised). openpilot's translation
  title-cases ("Modo Experimental", "Redefinir Calibração"); ours follow the English's sentence case: "Modo
  experimental", "Redefinir calibração". openpilot's ALL-CAPS buttons are its own style.
- Buttons are short infinitives: Cancelar, Concluído, Salvar, Excluir, Tentar de novo, Continuar, Abrir, Fechar,
  Ativar, Desativar.
- No full stop on titles, buttons, row titles or pills; whole sentences in body text end with one.
- Portuguese runs about 20–30 % longer than English: prefer the shorter common word, drop articles in pills and row
  subtitles, and drop a word the zh-TW drops in narrow places.
- Numbers keep the English digits and decimal point as the app formats them (the app formats, not the strings).
- Plurals: `one`, `many` and `other`; `many` (Android's CLDR form for large compact numbers) has the same text as
  `other`.

## This phone or this device

`strings_common.xml` words the device the app runs on: **este celular** / **este dispositivo** mid-sentence, and
**Este celular** / **Este dispositivo** at a sentence's start. Both nouns are masculine and both phrases start with
"este", so every sentence reads with either. Where a preposition contracts with "este", the sentence writes only the
preposition's first letter before the placeholder: `n%1$s` reads "neste celular" / "neste dispositivo" ("Salvo
n%1$s"), `d%1$s` reads "deste celular" / "deste dispositivo". Only the mid-sentence forms take this prefix. A
placeholder that gets the sentence-start form (English starts the sentence with it) stays at the start of the
Portuguese sentence ("%1$s não conseguiu ler o vídeo"). Every sentence that names the device takes the placeholder. "your phone" is `common_your_*` (seu celular / seu dispositivo), which doesn't contract: "no %1$s".

## Terms

| English | Português (Brasil) | Note |
|---|---|---|
| Home (dock) | Início | |
| Recordings | Gravações | the section and its saved drives |
| Settings | Configurações | "Ajustes" nowhere |
| recording, a recording | gravação | openpilot: "Gravar e Enviar" |
| drive (a trip the comma recorded) | viagem | |
| replay | reprodução | |
| live copy | cópia ao vivo | |
| saved moment | momento salvo | |
| Record | Gravar | the rail's button |
| Go live / live streaming | transmissão ao vivo | |
| onroad screen | tela de condução | |
| onroad / offroad (the comma's state) | em movimento / parado | |
| design (an onroad screen's look) | design | Brazilian usage keeps the English word |
| overlay pack | pacote de sobreposição | "pacote" alone where the context is clear |
| fork | fork | openpilot's own jargon; kept, masculine (o fork) |
| runtime (commaviewd) | runtime | developers' word, kept in Brazilian tech usage; masculine |
| update / install / uninstall | atualizar / instalar / desinstalar | openpilot's |
| reboot | reiniciar | openpilot's |
| power off | desligar | openpilot's |
| pair / pairing | emparelhar / emparelhamento | openpilot's |
| device (the comma) | dispositivo | openpilot's |
| this phone / this device | este celular / este dispositivo | `common_this_*`; openpilot says telefone |
| your phone / your device (`common_your_*`) | seu celular / seu dispositivo | both masculine; "seu" doesn't contract, so the sentence writes "no %1$s", "do %1$s"; Seu celular / Seu dispositivo at a sentence's start |
| connected / disconnected | conectado / desconectado | |
| offline | offline | openpilot's |
| engaged / disengaged | ativado / desativado | openpilot: "Desativar" for disengaging |
| override | intervenção do motorista | |
| experimental mode | modo experimental | openpilot's |
| driver monitoring | monitoramento do motorista | openpilot's ("Monitoramento de Motorista") |
| driver camera | câmera do motorista | openpilot's; Live View's short toggle is “Câm. int.” |
| road camera / wide camera | câmera da via / câmera grande-angular | |
| lead car | veículo à frente | |
| speed limit | limite de velocidade | |
| set speed / MAX | velocidade definida / MÁX | openpilot's MAX is MÁX |
| lane change | mudança de faixa | openpilot: "saída de faixa" |
| calibration | calibração | openpilot's |
| driver position (left/right-hand drive) | posição do motorista (volante à esquerda / à direita) | |
| daylight contrast | contraste diurno | |
| offline maps | mapas offline | |
| navigation | navegação | |
| Home / Work (places) | Casa / Trabalho | |
| vehicle location | localização do veículo | openpilot says veículo |
| account / sign in / sign out | conta / entrar / sair | |
| leaderboard | ranking | |
| achievement | conquista | |
| privacy | privacidade | |
| diagnostics | diagnóstico | |
| report a problem | relatar um problema | |
| Details (Live View's pane) | Detalhes | |
| stream health | saúde da transmissão | |
| storage | armazenamento | openpilot's |
| hotspot | ponto de acesso | openpilot's "Tethering" toggle is its own name |
| Live / Delayed (Live View's state) | Ao vivo / Com atraso | |
| frame pacing | ritmo de quadros | |
| inset (a picture in the picture) | miniatura | |
| framing: Fill / Exact / Extend / Auto | Preencher / Exato / Estender / Auto | |
| camera framing | enquadramento da câmera | |
| reduce motion | reduzir movimento | |
| screen edges | bordas da tela | |
| View (Surround's) / chase / high / top-down | Visão / perseguição / elevada / de cima | |
| vehicle detection / detector / model | detecção de veículos / detector / modelo | |
| renderer | renderizador | |
| key (an API key, an SSH key) | chave | openpilot's "chaves SSH"; public / private: chave pública / privada |
| dashboard (a service's) | painel | |
| reroute | recalcular rota | |
| Where to? | Para onde? | |
| map source | fonte do mapa | |
| Powered by | Com tecnologia | |
| steering / speed active, manual (the HUD's control line) | direção ativa / velocidade ativa / manual | review on a drive |
| steering only / speed only | só direção / só velocidade | |
| blind spot | ponto cego | |
| green light / lead car moving | sinal verde / veículo à frente andou | |
| safe update / install / repair | atualização / instalação / reparo seguro | |
| overlays (drawn on video) | sobreposições | not overlay packs |
| telemetry | telemetria | |
| patch | patch | |
| in Park | em P (estacionado) | "em P" in narrow places |
| power harness | chicote de alimentação | |
| guided / manual setup | configuração guiada / manual | openpilot's configuração |
| boot hook / runtime hook | hook de inicialização / hook do runtime | developers' jargon, kept |
| vehicle security key | chave de segurança do veículo | |
| pair code / invitation | código de emparelhamento / convite | |
| phones with a key | celulares com chave | |
| shared token | token compartilhado | |
| development runtime | runtime de desenvolvimento | |
| controller | controle | a game controller |
| best effort | sem garantia | |
| video only | só vídeo | |
| widgets | widgets | Android's Portuguese |
| backup / restore | backup / restaurar | |
| read-only | somente leitura | |
| head unit | central multimídia | |
| nearby devices | dispositivos por perto | Android's permission |
| display over other apps | sobrepor a outros apps | Android's permission |
| set aside (saved lists) | separado | |
| Not now / Review | Agora não / Revisar | openpilot's REVIEW is REVISAR |
| queue | fila | |
| Needs processing | Aguardando processamento | |
| pull drives | buscar viagens | |
| whole drive | viagem inteira | |
| export | exportar | |
| pack studio | estúdio de pacotes | |
| clip | clipe | |
| log excerpt | trecho do log | |
| support bundle | pacote de suporte | |
| Driving insights | Estatísticas de condução | |
| contribute | contribuir | |
| route / segment (openpilot's) | rota / segmento | |
| Privacy & sharing | Privacidade e dados | the Settings page; compartilhamento is too long for the hub row at 2× text |
| stream key | chave de transmissão | YouTube's |
| destination (Go live's) | destino | |
| Go live | Transmitir | |
| YouTube Studio | YouTube Studio | YouTube's own name in Portuguese |
| Auto-start | Início automático | |
| Public / Unlisted / Private | Público / Não listado / Privado | YouTube's |
| input (microphone) | entrada | |
| car hands-free | viva-voz do carro | |
| car | carro | openpilot's |
| metered / monthly limit | limitada / limite mensal | openpilot: "rede sem franquia" for unmetered |
| Your requests | Suas solicitações | |
| Open / Closed (a request) | Aberta / Encerrada | |
| license | licença | |
| map library | biblioteca de mapas | |
| map theme | tema do mapa | |
| spoken guidance | orientação por voz | |
| dev build | versão de desenvolvimento | |
| access pass | passe de acesso | the account's |
| waitlist | lista de espera | |
| beta member / admin | membro Beta / administrador | |
| display name / public name | nome de exibição / nome público | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | Esta semana / Semana passada / Total | |
| finalized (a week) | encerrada | |
| badge / share card | selo / cartão para compartilhar | |
| Official / Community (packs) | Oficial / Comunidade | |
| reviewed by CommaView / unreviewed | revisado pela CommaView / não revisado | |
| Update ready | Atualização pronta | |
| training collection | coleção de treinamento | car detection's; openpilot's "Guia de Treinamento" |
| recording metadata | metadados da gravação | |
| SSH identity (a comma's host key) | identidade SSH | |
| keystore | armazenamento de chaves | Android's |
| repository (a fork's) | repositório | |
| driving software | software de condução | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | deixar como estava | |
