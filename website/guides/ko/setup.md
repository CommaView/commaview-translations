---
title: "CommaView 설정하기"
description: "Android에 CommaView 앱을 설치하고, comma 3X나 comma four를 준비한 다음, 안내 설정으로 런타임을 설치하고 comma를 페어링합니다."
topic: start
order: 1
kind: walkthrough
lede: "CommaView는 두 부분으로 되어 있습니다. Android 휴대폰, 태블릿 또는 헤드 유닛의 앱과 comma에서 실행되는 작은 런타임입니다. 앱을 설치하면 앱의 안내 설정이 comma에 런타임을 설치하고, 확인하고, 페어링합니다. 몇 분이면 되며, P단에서 openpilot을 해제한 상태로 진행합니다."
parked: true
updated: 2026-11-27
needs:
  - title: "comma 3X 또는 comma four"
    text: "openpilot이나 [지원 포크](/ko/guides/forks)를 실행 중이어야 합니다. comma 3는 지원하지 않습니다. comma 3의 openpilot 릴리스는 업스트림에서 업데이트가 멈췄고 화면을 다르게 그리기 때문에 CommaView가 오버레이를 표시할 수 없습니다. [comma 3를 지원하지 않는 이유](/ko/#faq-comma-3)."
  - title: "Android 기기와 초대"
    text: "Android 8 이상, 그리고 초대를 받은 이메일 주소. CommaView는 베타 중이므로 초대받은 계정으로 로그인합니다."
  - title: "같은 네트워크"
    text: "휴대폰과 comma가 같은 로컬 네트워크에 있어야 합니다. 집 Wi‑Fi, 휴대폰의 핫스팟, comma 자체 핫스팟 등 둘 다 연결할 수 있는 네트워크면 됩니다. 차 안이라면 [집 Wi‑Fi 없이 연결하기](/ko/guides/connect-in-the-car)를 보세요."
  - title: "GitHub 계정"
    text: "comma는 입력한 GitHub 사용자 이름의 SSH 키를 받아들입니다. 키는 CommaView가 만들고, 설정 중에 직접 GitHub에 추가합니다."
howItWorks:
  - title: "휴대폰"
    text: "SSH 키를 만듭니다. 이 키를 GitHub에 추가합니다."
    edge: "SSH"
  - title: "comma"
    text: "GitHub 사용자 이름에서 키를 가져옵니다. CommaView는 포크 옆에 런타임을 설치합니다."
    edge: "로컬 네트워크"
  - title: "CommaView"
    text: "런타임이 응답하는지 확인하고 comma를 저장합니다. 그 후로는 알아서 다시 연결합니다."
steps:
  - id: get-the-app
    title: "앱 받고 로그인하기"
    body: |
      Android 기기에서 초대받은 이메일 주소로 [my.commaview.com](https://my.commaview.com)에 로그인합니다. **Get the app** 아래에서 **Download CommaView**를 누르세요. 파일을 확인하고 싶다면 옆에 SHA-256 체크섬이 표시됩니다.

      다운로드한 파일을 여세요. Android가 브라우저의 설치 허용을 요청하면 이번 설치에만 허용하고, 끝나면 다시 끄세요.

      CommaView를 여세요. 처음 한 번 **CommaView 개선에 참여**할지 묻습니다(**보내기** 또는 **보내지 않음**). 다음으로 로그인을 요청합니다. **로그인**을 누르고 초대받은 이메일 주소를 사용하세요. 그 후에는 이용권이 유효한 동안 오프라인으로도 작동합니다.
    tabs:
      - label: "CommaView 개선에 참여"
        body: "충돌 보고서와 comma가 실행하는 주행 소프트웨어의 종류입니다. 영상, 주행, 장소, 이름은 절대 보내지 않습니다. 설정 › **개인정보 및 공유**에서 언제든 바꿀 수 있습니다."
        screen: improve-commaview
        pins:
          - target: send
            text: "**보내기**: 문제 해결에 도움이 되는 충돌 보고서를 보냅니다."
          - target: dont-send
            text: "**보내지 않음**: 휴대폰에만 보관합니다."
      - label: "로그인"
        body: "베타 기간에는 CommaView에 초대받은 계정이 필요합니다. **로그인**을 누르면 브라우저가 열립니다."
        screen: sign-in
        pins:
          - target: sign-in
            text: "초대받은 이메일 주소로 **로그인**."
    note: "헤드 유닛이나 차량 화면의 AI 박스에 설치하나요? 네트워크와 comma 페어링은 [차량 화면](/ko/guides/car-screens)에서 다룹니다."
  - id: connect
    title: "comma 설정 시작하기"
    body: |
      안내문을 읽고, 비공식 소프트웨어이며 안전한 사용은 본인 책임임을 이해했다고 체크한 다음 **이해했습니다 — 계속**을 누르세요.

      **comma 연결**에서 **comma에 CommaView 설정**을 누르세요.
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**comma에 CommaView 설정**: 아직 CommaView가 없는 comma용."
      - target: pair-runs
        text: "다른 휴대폰에서 이미 CommaView를 실행 중인가요? 대신 **CommaView를 실행 중인 comma 페어링**: [다른 휴대폰이나 태블릿 추가하기](/ko/guides/another-phone)."
  - id: setup-path
    title: "설정 방법 고르기"
    tabs:
      - label: "안내 설정"
        body: "**안내 설정**(**권장** 표시가 있음)을 고르고 **안내 설정으로 계속**을 누르세요. CommaView가 SSH 키를 만들고, 연결을 안내하고, comma를 확인합니다. 다음 단계들은 이 흐름을 따릅니다."
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**권장** 표시가 있는 **안내 설정**."
          - target: continue
            text: "**안내 설정으로 계속**."
      - label: "수동 설정"
        body: "컴퓨터에서 comma에 사용자 `comma`로 SSH 접속이 이미 되는 경우에만 사용하세요. **수동 설정**을 고르고 **수동 설정으로 계속**을 누른 다음 터미널에서 명령을 실행합니다. 설치 프로그램이 일회용 페어링 코드를 보여 주면 **명령을 실행했습니다**를 누르고, comma의 IP와 코드를 입력한 뒤 **comma 추가**를 누르세요. 단계별 설명은 [터미널에서 수동 설정하기](#터미널에서-수동-설정하기)에 있습니다."
        screen: setup-manual-instructions
        pins:
          - text: "**눌러서 복사**로 명령을 복사합니다."
          - target: ran-command
            text: "설치 프로그램이 페어링 코드를 보여 주면 **명령을 실행했습니다**."
  - id: ssh-key
    title: "GitHub에 SSH 키 추가하기"
    body: |
      CommaView가 이 휴대폰용 SSH 키를 만듭니다. **키 복사 후 GitHub 열기**를 누르면 공개 키가 복사되고 GitHub의 새 SSH 키 페이지가 열립니다.

      GitHub에서 **Key** 칸에 키를 붙여넣고, 제목은 자유롭게 정한 다음(CommaView가 미리 채워 둡니다) **Add SSH key**로 저장하세요. CommaView로 돌아와 **계속**을 누르세요.
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**키 복사 후 GitHub 열기**. “SSH 키를 복사했습니다. GitHub를 여는 중…”이라고 표시됩니다."
      - target: own-key
        text: "**내 SSH 키 사용**: GitHub에 이미 등록한 키 쌍을 가져옵니다."
      - target: continue
        text: "GitHub에 키를 저장한 뒤 **계속**."
    note: "GitHub에 이미 키 쌍이 있나요? 대신 **내 SSH 키 사용**으로 가져올 수 있습니다. 개인 키는 휴대폰에만 남습니다."
  - id: comma-ssh
    title: "comma에서 SSH 켜기"
    body: |
      comma 화면에서 **설정 → 장치 → SSH**로 이동하세요.

      1. GitHub 사용자 이름을 입력합니다.
      2. comma가 GitHub 키를 가져올 때까지 기다립니다.
      3. SSH를 켭니다.

      그런 다음 CommaView로 돌아와 **계속**을 누르세요.
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "SSH를 켠 뒤 **계속**."
    note: "comma는 사용자 이름을 입력할 때 한 번만 키를 가져옵니다. 키를 추가하기 전에 사용자 이름을 입력했다면, 지운 뒤 다시 입력해서 comma가 키를 다시 가져오게 하세요."
  - id: choose-comma
    title: "comma 고르기"
    body: |
      CommaView는 이 Wi‑Fi 네트워크에서 이미 CommaView를 실행 중인 comma를 보여 줍니다. 그래서 처음 설정하는 comma는 보통 목록에 없습니다. **내 comma가 목록에 없음**을 누르고 IP 주소를 입력하세요. 그다음 **CommaView 설치**를 누르세요.

      IP는 comma의 **설정 → 네트워크**에 있습니다. comma four에서는 Wi‑Fi 버튼의 네트워크 이름 아래, comma 3X에서는 **고급 설정** 아래에 있습니다.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "이미 CommaView를 실행 중인 comma. 이 휴대폰에 저장된 comma에는 **이 휴대전화에 저장됨**이 표시됩니다."
      - text: "**내 comma가 목록에 없음**: IP 주소를 입력합니다."
      - target: install
        text: "**CommaView 설치**."
  - id: safe-install
    title: "안전 설치 시작하기"
    body: |
      **안전 설치** 대화 상자에 설치할 comma가 표시됩니다. 안내를 읽고, 짧은 카운트다운이 끝나면 **안전 설치 시작**을 누르세요.
    tabs:
      - label: "차량이 P단에 있음"
        body: "차량이 P단에 있고 openpilot이 작동 중이 아니면 CommaView가 바로 설치합니다."
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "카운트다운이 끝나면 **안전 설치 시작**."
      - label: "차량이 주행 중임"
        body: "comma가 설치를 대기시켰다가 openpilot이 해제된 상태로 차량이 P단에 있을 때 실행하므로 주행이 중단되지 않습니다. 설정에 **설치 대기 중**이 표시됩니다. openpilot을 해제하고 차를 P단에 둔 뒤 1~2분 기다렸다가 **설정 완료**를 누르세요."
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "차량이 P단에 있으면 **설정 완료**."
    note: "그다음 CommaView가 SSH로 comma에 연결해 어떤 comma인지 확인하고, 이 앱 버전에서 테스트한 런타임을 설치합니다. 설치가 응답하는지 확인한 뒤 이 휴대폰에 comma를 저장합니다. 끝날 때까지 휴대폰을 같은 네트워크에 두세요."
    warn: "차를 켠 채 P단에 두세요. 상시 전원 하네스가 없으면 차를 끌 때 comma도 꺼져 설치가 멈춥니다."
  - id: ready
    title: "CommaView 준비 완료"
    body: |
      comma에 설치와 페어링이 끝났으며, 다음에 comma가 켜지면 알아서 다시 연결합니다.
    tabs:
      - label: "CommaView 준비 완료"
        body: "**완료**를 누르세요."
        screen: setup-done
        pins:
          - target: finish
            text: "**완료**를 누르면 홈으로 갑니다."
      - label: "재시작하여 설정 완료"
        body: "설정에 **재시작하여 설정 완료**가 표시될 때가 있습니다. comma를 한 번 재시작하면 휴대폰으로 스트리밍합니다. 차를 끄거나 openpilot을 해제하고 P단에 둔 상태에서 **comma 재시작 후 완료**를 누르세요. 재시작하는 동안 약 1분간 openpilot이 멈춥니다."
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**comma 재시작 후 완료**."
check: "홈에 차량이 표시되고, comma가 **연결됨**이며, 런타임과 comma 주소가 보입니다. **Live View 열기**를 누르면 도로가 실시간으로 재생되고 경로와 앞차가 위에 그려집니다. 이제부터는 휴대폰과 comma가 같은 네트워크에 있으면 주소가 바뀌어도 앱이 알아서 comma를 찾습니다."
fixes:
  - q: "SSH로 연결할 수 없었습니다"
    a: "comma의 **설정 → 장치 → SSH**에서 SSH가 켜져 있는지, GitHub 사용자 이름이 본인 것인지, CommaView 키가 그 GitHub 계정에 있는지 확인하세요. 사용자 이름을 입력한 뒤에 키를 추가했다면 사용자 이름을 지우고 다시 입력해서 comma가 키를 가져오게 하세요."
  - q: "내 comma가 목록에 없습니다"
    a: "처음에는 정상입니다. 목록에는 이미 CommaView를 실행 중인 comma만 나옵니다. **내 comma가 목록에 없음**을 누르고 IP 주소를 입력하세요(comma의 **설정 → 네트워크**: comma four에서는 Wi‑Fi 버튼의 네트워크 이름 아래, comma 3X에서는 **고급 설정** 아래). 휴대폰이 comma와 같은 네트워크에 있고 VPN을 쓰고 있지 않은지도 확인하세요."
  - q: "설정에 “설치 대기 중”이 표시됩니다"
    a: "comma가 차량 주행을 감지해 기다리는 중입니다. openpilot을 해제하고 차를 P단에 둔 뒤 1분 정도 기다렸다가 **설정 완료**를 누르세요. 차는 켜 두세요. 상시 전원 하네스가 없으면 차를 끌 때 comma도 꺼집니다."
  - q: "설정에서 comma를 지원하지 않는다고 합니다"
    a: "comma 3에서는 설정이 멈추고 **comma 3X 또는 comma four에 CommaView 설정**을 안내합니다. CommaView가 화면을 추가할 수 없는 포크에서는 설정이 그렇게 알려 주고 아무것도 바꾸지 않습니다. [comma와 포크가 지원되는지 확인하기](/ko/guides/forks)."
  - q: "페어링 코드가 작동하지 않았습니다"
    a: "페어링 코드는 일회용이며 금방 만료됩니다. 설치 프로그램을 다시 실행해 새 코드를 받고, 표시된 대로 입력했는지 확인하세요(하이픈은 생략해도 됩니다)."
  - q: "연결됐는데 영상이 나오지 않습니다"
    a: "설정과 페어링은 끝났고, 이건 영상 스트림 문제입니다. comma가 켜져 있고 주행할 준비가 됐는지 확인하고, 휴대폰을 같은 네트워크에 둔 채 Live View를 다시 여세요. **이 comma에 연결할 수 없음**이 표시되면 [comma를 찾을 수 없을 때](/ko/guides/comma-not-found)를 보세요."
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## 터미널에서 수동 설정하기

컴퓨터에서 comma에 사용자 `comma`로 SSH 접속이 이미 되는 경우에만 사용하세요.

1. CommaView에서 **수동 설정**을 고르고 **수동 설정으로 계속**을 누르세요. **터미널에서 설치**에 이 앱의 런타임용 명령이 복사할 수 있게 표시됩니다(**눌러서 복사**). 현재 릴리스의 런타임을 설치하는 다음과 같은 명령입니다.

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. comma와 같은 Wi‑Fi 네트워크에 있는 컴퓨터에서 `COMMA_IP`를 comma의 IP 주소로 바꿔 실행하세요(comma의 **설정 → 네트워크**: comma four에서는 Wi‑Fi 버튼의 네트워크 이름 아래, comma 3X에서는 **고급 설정** 아래). 컴퓨터가 설치 프로그램을 내려받고, SSH가 comma에서 사용자 `comma`로 실행합니다.
3. 설치 프로그램이 끝나면 comma에서 CommaView가 시작되고 일회용 페어링 코드가 표시됩니다.
4. CommaView로 돌아와 **명령을 실행했습니다**를 누르세요. **comma 추가**에서 comma를 고르거나 IP를 입력하고, 페어링 코드를 입력한 뒤 **comma 추가**를 누르세요. 앱이 런타임을 확인하고 comma를 저장합니다.

## 첫 주행 전에

운전하기 전에 P단에서 먼저 확인하세요.

- 홈에 comma가 **연결됨**으로 표시됩니다.
- Live View가 재생되고 경로가 차와 함께 움직입니다.
- 앱에 경고가 나오거나 복구를 요청하면 운전하기 전에 해결하세요.
- 운전 중에 조작할 필요가 없도록 미리 설정해 두세요.

그래도 해결되지 않나요? [CommaView Discord](https://discord.gg/UuMhz9K8ft)에서 물어보거나 앱에서 피드백을 보내세요. 지원팀이 로그를 요청하면 [지원 번들을 보내세요](/ko/guides/support-bundle).
