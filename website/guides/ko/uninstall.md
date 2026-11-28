---
title: "comma에서 CommaView 제거하기"
description: "장치 설정에서 comma의 CommaView 런타임을 제거하고, 포크 파일을 원래대로 되돌리고, 휴대폰에서 comma를 삭제합니다."
topic: account
order: 3
kind: walkthrough
lede: "**런타임 제거**는 comma에서 CommaView를 제거합니다. CommaView의 훅을 되돌리고, 런타임을 멈추고, `/data/commaview`를 삭제합니다. 포크는 늘 하던 대로 주행합니다. CommaView를 제거하거나, 안내 설정을 처음부터 다시 실행할 때 쓰세요."
parked: true
updated: 2026-11-27
needs:
  - title: "휴대폰과 comma가 함께 있음"
    text: "comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다. 장치 설정에서 업데이트와 제거를 하려면 comma가 필요합니다."
  - title: "차가 켜져 있고 P단"
    text: "차가 주행 중이면 comma는 openpilot이 해제된 상태로 P단에 있을 때까지 제거를 대기시킵니다."
steps:
  - id: device-settings
    title: "comma의 장치 설정 열기"
    body: |
      홈에서 comma의 **장치 설정**을 열고 **런타임**(“업데이트 또는 제거”)을 여세요.
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**런타임**: CommaView 업데이트 또는 제거."
  - id: uninstall
    title: "런타임 제거 누르기"
    body: |
      런타임 업데이트 아래의 **런타임 제거**는 이 comma에서 CommaView를 제거합니다. 그다음 안내 설정을 처음부터 다시 실행할 수 있습니다.
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**런타임 제거**."
  - id: confirm
    title: "확인하기"
    body: |
      **CommaView가 제거됩니다**: CommaView가 런타임 훅을 되돌리고, 멈추고, 이 comma에서 `/data/commaview`를 삭제합니다. comma는 휴대폰에 저장된 상태로 남습니다. 짧은 카운트다운이 끝나면 **런타임 제거**를 누르세요.
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**CommaView가 제거됩니다**와 그 내용."
      - text: "카운트다운이 끝나면 **런타임 제거**. **취소**를 누르면 CommaView를 유지합니다."
    note: "차가 주행 중이면 comma가 제거를 대기시킵니다. openpilot이 해제된 상태로 차가 P단에 있으면 CommaView가 제거되며, 그때까지는 계속 실행됩니다."
  - id: forget
    title: "원하면 휴대폰에서 comma 삭제하기"
    body: |
      이제 장치 설정에 런타임이 제거되었다고 표시됩니다. 휴대폰에서도 comma를 빼려면 장치 설정 맨 끝의 **이 comma 삭제**를 누르세요. CommaView에 이 comma가 더 이상 나오지 않고 페어링 키가 삭제됩니다. 앱 자체를 지우려면 다른 앱처럼 Android 설정에서 CommaView를 제거하세요.
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**이 comma 삭제**."
check: "대화 상자에 **런타임 제거됨**이 표시되고, 장치 설정의 런타임에 **제거됨**이 나옵니다: “comma에서 CommaView가 제거되었습니다. 다시 설치하려면 안내 설정을 실행하세요.”"
fixes:
  - q: "“SSH 권한 오류로 제거에 실패했습니다.”"
    a: "comma가 이 휴대폰의 SSH 접속을 허용하지 않았습니다. comma의 **설정 → 장치 → SSH**에서 SSH가 켜져 있고 그 GitHub 사용자 이름에 이 휴대폰의 키가 있는지 확인한 다음 **다시 제거**를 누르세요."
  - q: "“comma가 CommaView를 제거하지 못해 그대로 두었습니다”"
    a: "아무것도 제거되지 않았습니다. 차를 P단에 두고 다시 시도하세요."
  - q: "“차량이 P단에 있을 때까지 제거가 대기 중입니다.”"
    a: "차가 주행 중입니다. openpilot을 해제하고 P단에 둔 채 차를 켜 두면 comma가 알아서 CommaView를 제거합니다."
  - q: "제거 버튼이 흐리게 표시됩니다"
    a: "CommaView가 이미 런타임을 업데이트하거나 제거하는 중입니다. 끝난 뒤 다시 시도하세요."
related: [setup, update-runtime, forks]
---

## 제거로 되돌아가는 것

- **목록에 있는 포크**에서는 CommaView가 포크의 화면 UI에 더한 작은 훅을 되돌립니다.
- **CommaView 목록에 없는 포크**(제한 지원)에서는 포크의 파일을 원래대로 되돌립니다.
- **영상 전용**은 포크의 파일을 전혀 바꾸지 않았으므로, 제거하면 런타임이 삭제됩니다.

SunnyPilot-TeslaHW1에서는 `op fork update` 전에 런타임을 제거하세요. CommaView 훅이 설치된 동안에는 포크를 바꿀 수 없습니다. 자세한 내용은 [comma와 포크가 지원되는지 확인하기](/ko/guides/forks)에 있습니다.

## CommaView 다시 설정하기

제거한 뒤에도 comma는 휴대폰에 저장된 상태로 남습니다. [안내 설정](/ko/guides/setup)을 실행하면 새로 설치하듯 다시 설치할 수 있습니다.
