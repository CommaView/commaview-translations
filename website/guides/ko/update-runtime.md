---
title: "comma 런타임 업데이트하기"
description: "홈이나 장치 설정에서 comma의 CommaView 런타임을 업데이트하세요. 안전 업데이트는 P단을 기다리므로 업데이트가 주행을 중단하지 않습니다."
topic: account
order: 1
kind: walkthrough
lede: "comma의 CommaView 런타임은 앱에서 업데이트하며, 절대 알아서 업데이트되지 않습니다. 먼저 CommaView를 업데이트하고, 앱이 제안하면 런타임을 업데이트하세요. 차가 주행 중이면 **안전 업데이트**가 comma에 업데이트를 대기시키고, openpilot이 해제된 상태로 차가 P단에 있으면 설치합니다."
updated: 2026-11-27
needs:
  - title: "휴대폰과 comma가 함께 있음"
    text: "comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다."
  - title: "차가 켜져 있음"
    text: "차를 켠 채 P단에 두세요. 상시 전원 하네스가 없으면 차를 끌 때 comma도 꺼집니다."
howItWorks:
  - title: "CommaView"
    text: "앱 릴리스마다 테스트한 런타임이 정해져 있으며, 정확히 그 런타임을 제안합니다."
  - title: "comma"
    text: "차가 P단에 있으면 내려받고, 확인하고, 설치합니다."
    edge: "재시작"
  - title: "Live View"
    text: "comma가 재시작하면 다시 시작합니다."
steps:
  - id: app-first
    title: "먼저 CommaView 업데이트하기"
    body: |
      앱은 테스트한 런타임을 설치하므로 런타임보다 앱을 먼저 업데이트하세요. 업데이트가 준비되면 홈 맨 위와 설정 › **정보**에 **업데이트**가 표시됩니다. 누르면 **CommaView 업데이트**에 버전, 채널, 크기가 나옵니다. **다운로드**를 누르면 CommaView가 백그라운드에서 내려받아 확인한 다음 Android가 설치 확인을 요청합니다.
    screen: app-update-offer
    pins:
      - target: download
        text: "**다운로드**."
      - target: channel
        text: "릴리스 채널: **베타**, 또는 테스터용 **알파**."
    note: "런타임을 업데이트하기 전에 이 comma를 보는 모든 휴대폰, 태블릿, 차량 화면에서 CommaView를 업데이트하세요."
  - id: open
    title: "런타임 업데이트 열기"
    tabs:
      - label: "홈에서"
        body: "이 comma용 새 런타임이 준비되면 홈에 **런타임 업데이트 준비됨**이 표시됩니다. **업데이트 검토**를 누르면 **런타임 업데이트** 카드에 **설치됨**과 **사용 가능** 버전, 차량이 준비됐는지가 나옵니다. **런타임 업데이트**를 누르세요. 차가 주행 중이면 **업데이트 대기열에 추가**입니다."
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**런타임 업데이트**: 설치됨, 사용 가능, 차량이 준비됐는지."
          - target: update-runtime
            text: "**런타임 업데이트**(주행 중에는 **업데이트 대기열에 추가**)."
      - label: "장치 설정에서"
        body: "comma의 **장치 설정**을 열고 **런타임**을 여세요(준비된 것이 있으면 **업데이트**가 표시됩니다). 페이지에 설치된 런타임과 사용 가능한 런타임이 나옵니다. **지금 업데이트**를 누르세요."
        screen: device-runtime
        pins:
          - target: update-now
            text: "**지금 업데이트**."
  - id: install
    title: "설치하거나 안전 업데이트로 대기시키기"
    body: |
      장치 설정에서는 **런타임 업데이트** 대화 상자에 차량이 준비됐는지가 표시됩니다.
    tabs:
      - label: "차량이 P단에 있음"
        body: "“차량이 P단에 있고 openpilot이 작동 중이 아닙니다. 런타임 업데이트를 안전하게 시작할 수 있습니다.”라고 표시됩니다. **업데이트 설치**를 누르세요."
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**업데이트 설치**."
          - target: close
            text: "**닫기**를 누르면 미뤄 둡니다."
      - label: "차량이 주행 중임"
        body: "“차량이 주행 중입니다. 안전 업데이트는 comma에 업데이트를 대기시킨 뒤 openpilot이 해제된 상태로 차량이 P단에 있으면 설치합니다.”라고 표시됩니다. **안전 업데이트…**를 누르고, 안내를 읽은 다음 짧은 카운트다운이 끝나면 **안전 업데이트 시작**을 누르세요. CommaView가 차량이 주행 중인지 확인하지 못했을 때도 마찬가지입니다."
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**안전 업데이트…**, 그다음 **안전 업데이트 시작**."
    note: "CommaView는 openpilot이나 포크를 절대 멈추지 않습니다. 대기 중인 업데이트는 P단을 기다리며, 주행이 중단되지 않습니다."
  - id: progress
    title: "진행되게 두기"
    body: |
      comma가 릴리스를 내려받고, 완전하고 변조되지 않았는지 확인하고, 설치한 다음 CommaView를 재시작하며, 앱에 각 단계가 표시됩니다. 다른 앱으로 전환하거나 휴대폰을 잠가도 업데이트가 계속되며, 알림에 진행 정도가 나옵니다.

      comma가 설치를 시작하기 전까지는 **업데이트 취소**로 멈출 수 있으며, comma에서는 아무것도 바뀌지 않습니다.
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "단계: 다운로드 중, 확인 중, 설치 중, CommaView 재시작 중, 다시 연결 중."
  - id: queued
    title: "대기 중인 업데이트는 P단을 기다립니다"
    body: |
      대기 중인 업데이트는 홈의 **런타임 업데이트** 카드에 **차량이 P단에 들어가기를 기다리는 중**으로 표시됩니다. openpilot이 해제된 상태로 차가 몇 초 동안 P단에 있으면 설치됩니다. 설치하는 동안 차를 켜 두세요.
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "단계와 함께 **차량이 P단에 들어가기를 기다리는 중**."
  - id: reboot
    title: "comma를 재시작해 마무리하기"
    body: |
      런타임 업데이트 후 CommaView가 다시 스트리밍하려면 comma를 재시작해야 합니다. openpilot은 comma가 재시작할 때만 CommaView의 새 화면 코드를 불러옵니다. 앱은 절대 알아서 재시작하지 않습니다.

      차를 끄거나 P단에 둔 상태에서 홈 카드의 **comma 재시작** 또는 대화 상자의 **지금 comma 재시작**을 누르세요. openpilot이 약 1분간 멈춥니다. comma 자체의 **설정 → 장치 → 재시작**에서 재시작할 수도 있습니다.
check: "업데이트의 마지막 단계에 **업데이트됨**이 표시되고, 장치 설정에 새 런타임이 **최신 버전**으로 나옵니다. 재시작 후 Live View가 오버레이와 함께 재생됩니다."
fixes:
  - q: "“이 comma의 런타임이 이 앱이 설치하는 것보다 최신입니다”"
    a: "CommaView를 업데이트한 다음 다시 시도하세요. comma에서 바뀐 것은 없습니다."
  - q: "“업데이트 필요”"
    a: "이 앱과 이 comma의 런타임이 서로에게 충분히 최신이 아닙니다. 먼저 CommaView를, 그다음 런타임을 업데이트하세요."
  - q: "“comma가 … 버전을 설치하지 않았습니다. CommaView 목록에 없는 … 포크를 실행 중이므로”"
    a: "comma는 아무것도 바꾸지 않고 기존 런타임을 유지했습니다. 그 포크에 CommaView를 제한 지원으로 추가하려면 이 comma의 설정을 다시 실행하세요. 포크를 확인하고 먼저 묻습니다."
  - q: "“시작할 때마다 차량이 다시 켜져서 comma가 시도를 멈췄습니다”"
    a: "openpilot을 해제하고 차를 P단에 둔 다음 다시 시도하세요."
  - q: "“런타임 업데이트 되돌림”"
    a: "comma가 이전 런타임으로 되돌렸습니다. 다시 시도하고, 또 실패하면 [지원 번들을 보내세요](/ko/guides/support-bundle)."
  - q: "“CommaView가 이미 런타임을 업데이트하거나 제거하는 중입니다”"
    a: "런타임 작업은 한 번에 하나만 실행됩니다. 끝난 뒤 다시 시도하세요."
  - q: "업데이트 후 오버레이나 텔레메트리가 없습니다"
    a: "comma가 아직 재시작하지 않았습니다. 차를 끄거나 P단에 둔 상태에서 재시작하세요."
related: [releases, uninstall, another-phone]
---

## 업데이트가 P단을 기다리는 이유

런타임을 설치하는 동안에는 파일을 바꾸는 사이 comma의 CommaView가 멈추고 서비스가 재시작되므로, comma는 차가 P단에 있고 openpilot이 해제되었을 때만 설치합니다. 안전 업데이트는 openpilot에 정차 중 상태로 바꾸라고 요청하지 않습니다. comma에 작업을 대기시키고, 차가 P단에 있으면 comma가 실행합니다. 차를 끌 필요는 없습니다. 켠 채 P단에 두세요.

comma는 무언가를 바꾸기 전에 릴리스를 내려받아 완전하고 변조되지 않았는지 확인합니다. 그 후 설치가 실패하면 이전 런타임으로 되돌립니다.
