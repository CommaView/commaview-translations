---
title: "멈춘 설정 해결하기"
description: "CommaView 설정 메시지가 뜻하는 것을 설정 순서(SSH, 설치, 페어링)대로 설명합니다. 보이는 메시지와 할 일을 찾아보세요."
topic: troubleshooting
order: 1
kind: fixes
lede: "설정은 순서대로 진행됩니다. SSH로 comma에 로그인하고, CommaView 런타임을 설치한 다음, 휴대폰과 페어링합니다. 멈추면 메시지에 어느 부분이 실패했는지 나오니 그 부분부터 해결하세요. SSH가 된다는 것은 첫 단계만 통과했다는 뜻입니다. 런타임이 시작되지 않았다면 페어링 코드는 작동하지 않습니다."
parked: true
updated: 2026-11-27
needs:
  - title: "P단"
    text: "openpilot을 해제하고 차를 P단에 둔 채 켜 두세요. 상시 전원 하네스가 없으면 차를 끌 때 comma도 꺼집니다."
  - title: "하나의 네트워크"
    text: "휴대폰이 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다. 노트북이 comma에 연결된다고 해서 휴대폰도 된다는 뜻은 아닙니다."
steps:
  - id: read
    title: "설정 메시지를 읽고 세부 정보 복사하기"
    body: |
      설치가 실패하면 설정이 무엇이 잘못됐는지, comma가 원래대로 되돌려졌는지, 무엇을 해야 하는지 알려 줍니다. 그 문장을 아래의 [잘 안 될 때](#fixes)에서 찾으세요.

      **세부 정보 복사**는 지원팀이 읽는 보고서(앱 버전, 릴리스, 설치 프로그램의 마지막 단계와 전체 출력)를 복사합니다. 메시지에서 안내하면 support@commaview.com으로 보내는 이메일에 붙여넣으세요.
    tabs:
      - label: "설치가 실패함"
        body: "설정이 실패한 내용을 알려 주고 **세부 정보 복사**를 제공합니다."
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**세부 정보 복사**."
          - target: install
            text: "원인을 해결했으면 **CommaView 설치**로 다시 시도합니다."
      - label: "SSH가 실패함"
        body: "아무것도 설치하기 전에, 설정이 comma에 들어갈 수 없었던 이유(**SSH 인증에 실패했습니다.** 등)와 확인할 것을 알려 줍니다."
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "무엇이 잘못됐는지, 무엇을 확인할지."
  - id: address
    title: "comma의 주소 확인하기"
    body: |
      설정은 휴대폰의 네트워크에서 comma를 찾습니다. 내 comma가 목록에 없으면 **내 comma가 목록에 없음**을 누르고 IP 주소를 입력하세요. comma의 **설정 → 네트워크**에 있습니다. comma four에서는 Wi‑Fi 버튼의 네트워크 이름 아래, comma 3X에서는 **고급 설정** 아래입니다.

      comma의 주소는 집 Wi‑Fi, 핫스팟, VPN 등 네트워크마다 다릅니다. 휴대폰이 지금 연결된 네트워크의 주소를 쓰세요.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "설정이 이 네트워크에서 찾은 comma."
      - text: "**내 comma가 목록에 없음**: 찾지 못했을 때 IP 주소를 입력합니다."
  - id: pair-code
    title: "새 코드로 페어링하기"
    body: |
      페어링 코드는 유효 기간이 짧고 한 번만 쓸 수 있습니다. 거부되면 같은 코드를 다시 입력하지 말고 새 코드를 받으세요. 수동 설치 후에는 설치 프로그램이 보여 주고, comma와 이미 페어링된 휴대폰에서는 **장치 설정 › 다른 휴대폰이나 태블릿 페어링**에서 볼 수 있습니다.
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**comma IP 주소**."
      - target: pair-code
        text: "**페어링 코드**. 하이픈은 생략해도 됩니다."
  - id: runs
    title: "이미 설치되어 있다면 페어링하기"
    body: |
      다른 휴대폰이나 이전 설정으로 comma에 이미 CommaView가 있다면 다시 설치할 필요가 없습니다. 홈에서 **comma 추가**를 누르고 **주소와 코드 입력**을 누른 다음, comma의 IP와 페어링 코드 또는 초대 코드로 페어링하세요.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "comma의 IP."
      - target: pair-code
        text: "**페어링 코드 또는 초대 코드**."
      - target: pair
        text: "**comma 페어링**."
  - id: no-video
    title: "설치와 페어링은 됐지만 영상이 없을 때"
    body: |
      페어링 이후에 화면이 나오지 않는 것은 SSH가 아니라 스트리밍 문제입니다. Live View가 **이 comma에 연결할 수 없음** 같은 상태를 알려 주고, comma가 응답하면 알아서 다시 연결합니다. [CommaView가 comma를 찾을 수 없을 때](/ko/guides/comma-not-found)를 보세요.
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**다시 시도**."
fixes:
  - q: "“SSH 인증에 실패했습니다.”"
    a: "CommaView 키가 GitHub에 있는지(제목은 자유), comma에서 SSH가 켜져 있는지 확인하세요. 키를 추가하기 전에 comma에 GitHub 사용자 이름을 입력했다면, 지우고 다시 입력해서 comma가 키를 다시 가져오게 하세요."
  - q: "“192.168.1.50:22에서 연결이 거부되었습니다. comma에서 SSH가 켜져 있는지 확인하세요.”"
    a: "comma에서 **설정 → 장치 → SSH**로 가서 SSH를 켜세요."
  - q: "“… 연결 시간이 초과되었습니다.” 또는 “…에 연결할 경로가 없습니다.”"
    a: "휴대폰이 그 주소에 연결할 수 없습니다. 휴대폰이 comma와 같은 Wi‑Fi나 comma의 핫스팟에 있는지, comma가 깨어 있는지(차가 켜져 있는지), IP 주소가 이 네트워크에서 comma의 주소인지 확인하세요."
  - q: "“…에서 comma를 찾을 수 없습니다. IP 주소를 확인하세요.”"
    a: "그 주소에서 아무것도 응답하지 않았습니다. comma의 **설정 → 네트워크**에서 IP를 확인하세요."
  - q: "“마지막 설정 이후 이 comma의 SSH 신원이 바뀌었습니다.”"
    a: "comma를 초기화했거나 다시 플래시했다면 설정을 다시 실행하세요."
  - q: "“CommaView가 이 휴대전화에서 SSH 키를 만들지 못했습니다. 다시 시도하거나 내 SSH 키를 사용하세요.”"
    a: "**다시 시도**를 누르거나, **내 SSH 키 사용**으로 GitHub에 이미 있는 키 쌍을 가져오세요."
  - q: "“설치가 대기 중입니다.”"
    a: "차가 주행 중이어서 comma가 주행을 중단하지 않고 설치를 대기시켰습니다. openpilot을 해제하고 차를 P단에 둔 뒤 차를 켠 채 1~2분 기다렸다가 **설정 완료**를 누르세요."
  - q: "“차량이 주행 중이어서 설치 작업을 실행하지 않았습니다.”"
    a: "openpilot을 해제하고 차를 P단에 둔 다음 다시 시도하세요."
  - q: "“comma에서 다른 CommaView 설치, 업데이트 또는 복구가 이미 진행 중입니다.”"
    a: "끝날 때까지 몇 분 기다린 다음 다시 시도하세요."
  - q: "“comma가 CommaView를 다운로드하지 못했습니다.”"
    a: "comma는 런타임을 직접 내려받습니다. Wi‑Fi나 comma 자체 SIM으로 인터넷에 연결되어 있는지 확인한 다음 다시 시도하세요. 모바일 데이터가 되는 휴대폰 핫스팟도 됩니다."
  - q: "“CommaView 다운로드가 불완전하거나 손상된 채로 comma에 도착했습니다.”"
    a: "다시 시도하세요. 또 그러면 세부 정보를 복사해 support@commaview.com으로 보내 주세요."
  - q: "“설치 작업 중 comma의 저장 공간이 부족해졌습니다.”"
    a: "나중에 다시 시도하세요. 또 그러면 세부 정보를 복사해 support@commaview.com으로 보내 주세요."
  - q: "“CommaView는 아직 comma의 주행 소프트웨어를 지원하지 않습니다.”"
    a: "comma가 CommaView를 설치할 수 없는 소프트웨어를 실행 중입니다. [어떤 포크를 지원하는지 확인하세요](/ko/guides/forks). 내 포크 지원을 요청하려면 세부 정보를 복사해 support@commaview.com으로 보내 주세요."
  - q: "“CommaView가 …에 화면을 안전하게 추가할 수 없습니다.”"
    a: "내 포크는 CommaView 목록에 없으며, 확인 결과 CommaView가 연결하는 부분에서 화면이 달랐습니다. comma에서 바뀐 것은 없습니다. 내 포크 지원을 요청하려면 세부 정보를 복사해 support@commaview.com으로 보내 주세요."
  - q: "“comma 3는 지원되지 않습니다”"
    a: "CommaView는 comma 3X와 comma four에서 작동합니다. comma 3의 openpilot 릴리스는 업스트림에서 업데이트가 멈췄고 화면을 다르게 그리기 때문에 CommaView가 오버레이를 표시할 수 없습니다."
  - q: "“설치 작업 후 comma에서 CommaView가 시작되지 않았습니다.”"
    a: "comma를 재시작한 다음 다시 시도하세요. 또 그러면 세부 정보를 복사해 support@commaview.com으로 보내 주세요."
  - q: "“확인 실패. 192.168.1.50:5002의 CommaView API에 연결하지 못했습니다.”"
    a: "설치는 끝났지만 휴대폰이 런타임에 연결할 수 없습니다. 휴대폰이 아직 comma의 네트워크에 있는지 확인한 다음 다시 시도하세요. 컴퓨터에서는 SSH가 되는데 이건 안 된다면, 컴퓨터가 휴대폰과 다른 네트워크에 있는 것입니다."
  - q: "“페어링 코드를 사용할 수 없습니다. 새 코드를 만들어 다시 시도하세요.”"
    a: "코드가 만료됐거나, 이미 사용됐거나, 잘못 입력했습니다. 새 코드를 받으세요([3단계](#step-pair-code))."
  - q: "“페어링 실패: CommaView 런타임 API에 연결할 수 없습니다”"
    a: "휴대폰이 그 주소의 comma에 연결할 수 없습니다. 핫스팟이나 네트워크를 확인한 다음 다시 시도하세요."
  - q: "“재부팅 후 CommaView가 자동으로 시작되지 않습니다”"
    a: "CommaView는 설치되어 있지만, comma가 부팅할 때 CommaView를 시작하는 것이 없습니다. comma의 `/data/continue.sh`에 `exec ./launch_openpilot.sh` 줄이 없습니다. 그 줄을 추가한 다음 CommaView를 다시 설치하세요."
related: [setup, comma-not-found, support-bundle]
---

## 설정이 거치는 단계

각 단계는 앞 단계가 필요하므로 이 순서대로 확인하세요.

1. **SSH**(포트 22): 설정이 설치를 위해 comma에 들어가는 방법입니다. GitHub 키, comma에 입력한 GitHub 사용자 이름, 켜진 SSH가 필요합니다.
2. **설치**: comma가 런타임을 내려받아 설치합니다. 그 뒤 단계를 보기 전에 이 결과부터 읽으세요.
3. **런타임**(comma의 포트 5002): 설정이 응답을 확인한 다음 페어링합니다.
4. **페어링**: 일회용 페어링 코드로 휴대폰에 comma용 자체 키를 줍니다.
5. **영상**(포트 8200~8202): Live View의 카메라.

검색으로 comma를 찾지 못해도 주소를 알면 입력하는 것만으로 똑같이 연결됩니다. 검색은 편의 기능일 뿐이고, 중요한 것은 comma에 연결되는 것입니다.

## 안전

설정, 설치, 문제 해결은 openpilot을 해제하고 차를 P단에 둔 상태에서 하세요. 운전 중에는 절대 설정하거나 앱을 조작하지 마세요.
