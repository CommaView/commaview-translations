---
title: "다른 휴대폰이나 태블릿 추가하기"
description: "10분 동안 유효한 초대 코드로 다른 휴대폰, 태블릿, 차량 화면에 comma용 키를 따로 주고, 키가 있는 휴대폰을 확인하고 삭제합니다."
topic: start
order: 4
kind: walkthrough
lede: "comma를 보는 휴대폰마다 자체 키가 있습니다. 다른 휴대폰, 태블릿, 차량 화면을 추가하려면 이미 comma가 있는 휴대폰에서 초대 코드를 표시하고, 새 기기에서 입력하거나 스캔하세요. SSH도, 다시 설정할 필요도 없습니다."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "키가 있는 휴대폰"
    text: "comma와 페어링된 휴대폰 한 대가 CommaView 0.0.166 이상과 그 런타임을 쓰고 있어야 합니다. 아직이라면 [CommaView를 설정하세요](/ko/guides/setup)."
  - title: "새 기기의 CommaView"
    text: "0.0.166 이상을 설치하고 로그인해 두세요. [앱 받기](/ko/guides/setup#step-get-the-app)."
  - title: "같은 네트워크"
    text: "둘 다 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다."
howItWorks:
  - title: "휴대폰"
    text: "comma에 초대 코드를 요청합니다. 코드나 QR 코드로, 10분 동안 유효합니다."
  - title: "새 휴대폰"
    text: "초대 코드로 참여해 자체 키를 받습니다."
    edge: "로컬 네트워크"
  - title: "comma"
    text: "키가 있는 모든 휴대폰에 새 휴대폰이 키를 받았다고 알립니다."
steps:
  - id: device-settings
    title: "휴대폰에서 다른 휴대폰 페어링 열기"
    body: |
      이미 comma가 있는 휴대폰의 홈에서 comma의 **장치 설정**을 열고 **다른 휴대폰 페어링**을 여세요.
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**다른 휴대폰 페어링**: 다른 휴대폰이나 태블릿이 연결할 수 있는 짧은 유효 기간의 코드."
  - id: show-invitation
    title: "초대 코드 표시하기"
    body: |
      **키가 있는 휴대폰** 아래의 **다른 휴대폰 추가**에서, 아직 이 comma가 없는 휴대폰용 초대 코드를 표시합니다. **초대 코드 표시**를 누르세요.
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**초대 코드 표시**."
      - text: "이 comma의 키가 있는 휴대폰. 이 휴대폰이 맨 위에 있습니다."
  - id: invitation
    title: "초대 코드를 화면에 띄워 두기"
    body: |
      **다른 휴대폰 추가**에 세 묶음으로 된 코드, QR 코드, comma의 IP 주소가 표시됩니다. 10분 동안 유효하며 한 번만 쓸 수 있습니다. 만료되면 새 코드를 표시하세요.
    screen: invitation-dialog
    pins:
      - target: code
        text: "새 휴대폰에 입력할 코드."
      - target: qr
        text: "또는 스캔할 QR 코드."
      - text: "**… 후 만료**: 표시한 때부터 10분."
  - id: add-comma
    title: "새 휴대폰에서 comma 추가하기"
    body: |
      새 휴대폰의 **comma 연결**에서 **CommaView를 실행 중인 comma 페어링**을 누르세요. 이미 comma가 있다면 대신 홈에서 **comma 추가**를 누르세요.

      comma가 **이 네트워크에 있음**에 표시됩니다. 눌러서 선택하거나, **QR 코드 스캔**을 눌러 초대 코드를 스캔하세요. 목록에 없으면 **주소와 코드 입력**을 누르세요.
    screen: add-comma
    pins:
      - target: found-comma
        text: "이 네트워크에서 찾은 comma."
      - target: scan-qr
        text: "**QR 코드 스캔**으로 초대 코드를 스캔합니다."
      - target: enter-address
        text: "목록에 없으면 **주소와 코드 입력**."
  - id: pair
    title: "초대 코드를 입력하고 페어링하기"
    body: |
      **comma IP**를 확인하고, **페어링 코드 또는 초대 코드**에 초대 코드를 입력한 다음(또는 QR 버튼을 눌러 스캔하고) **comma 페어링**을 누르세요. 새 휴대폰이 자체 키를 받고 홈에 comma가 표시됩니다.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**comma IP**. 찾은 comma라면 미리 채워져 있습니다."
      - target: pair-code
        text: "**페어링 코드 또는 초대 코드**."
      - target: scan-qr
        text: "**페어링 QR 스캔**."
      - target: pair
        text: "**comma 페어링**."
  - id: new-key
    title: "다른 휴대폰에서 확인하기"
    body: |
      키가 있는 각 휴대폰에 **새 휴대폰에 키가 생겼습니다**라는 알림이 이름, 시간과 함께 표시됩니다. **내 휴대폰입니다**를 누르세요. 내 기기가 아니면 **삭제**를 누르세요. **휴대폰 확인**을 누르면 키가 있는 모든 휴대폰이 나열된 **다른 휴대폰 페어링**이 열립니다.
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "내 휴대폰이나 태블릿이면 **내 휴대폰입니다**."
      - target: review
        text: "**휴대폰 확인**: 키가 있는 모든 휴대폰을 보여 줍니다."
check: "새 휴대폰의 홈에 comma가 표시되고 Live View가 열립니다. 첫 휴대폰의 **다른 휴대폰 페어링**에서 **키가 있는 휴대폰** 아래에 새 휴대폰이 나옵니다."
fixes:
  - q: "“이 초대 코드로 참여하지 못했습니다”"
    a: "잘못 입력했거나, 만료되었거나, 이미 사용되었을 수 있습니다. 이 comma가 이미 있는 휴대폰(장치 설정의 **다른 휴대폰 페어링**, **다른 휴대폰 추가**)에서 새 코드를 표시하세요."
  - q: "“이 comma의 런타임은 휴대폰 키 도입 이전 버전입니다”"
    a: "먼저 comma의 런타임을 업데이트하세요: [comma 런타임 업데이트하기](/ko/guides/update-runtime). 그다음 초대 코드를 표시하세요."
  - q: "“이 comma에 연결할 수 없음”"
    a: "두 휴대폰 모두 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다. [차 안에서 연결하기](/ko/guides/connect-in-the-car)."
  - q: "“페어링 실패: 이 comma는 더 이상 코드로 페어링하지 않습니다”"
    a: "comma가 이전 공유 토큰을 더 이상 받지 않습니다. 이미 키가 있는 휴대폰(설정의 **다른 휴대폰 추가**)에서 휴대폰을 추가하거나, comma 설정을 다시 실행하세요."
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## 휴대폰 삭제하기

키가 있는 휴대폰에서 comma의 **장치 설정**을 열고 **다른 휴대폰 페어링**을 여세요. 목록에서 휴대폰 옆의 **삭제**를 누르세요. 그 휴대폰은 초대 코드나 comma 설정으로 다시 추가될 때까지 이 comma에 연결할 수 없습니다.

## 이전 CommaView를 쓰는 휴대폰

0.0.166 이전에는 모든 휴대폰이 comma에 같은 공유 토큰을 보냈습니다. 0.0.166을 쓰는 휴대폰은 다음에 연결할 때 다시 페어링하지 않아도 키를 받습니다.

- **다른 휴대폰 페어링**의 **이전 CommaView 앱**에는 이전 CommaView를 쓰는 휴대폰이 공유 토큰으로 이 comma를 며칠 더 쓸 수 있는지 표시됩니다. 첫 휴대폰이 키를 받은 뒤 90일입니다. 그때까지는 **이전 앱용 페어링 코드**로 이전 CommaView를 쓰는 휴대폰을 페어링할 수 있습니다.
- **지금 중지**는 공유 토큰을 쓰는 모든 휴대폰이 키를 받은 뒤, comma가 공유 토큰을 더 이상 받지 않게 합니다. 그러면 이전 CommaView를 쓰는 휴대폰은 이 comma에서 작동하지 않으며, 업데이트할 때까지 다시 페어링할 수 없습니다.
- 그 후에는 키가 없는 휴대폰에 CommaView 0.0.166 이상과 초대 코드가 필요합니다.

comma의 런타임을 업데이트할 때는 먼저 그 comma를 보는 모든 기기(차량 화면 포함)에서 CommaView를 업데이트하세요.
