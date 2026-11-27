---
title: "내 Stadia Maps 키로 길 안내 받기"
description: "Stadia Maps 키를 추가하고, 홈에서 장소를 검색해 경로를 고른 다음, Live View에서 회전 카드와 음성 안내를 따르세요. 장소를 comma로 보낼 수도 있습니다."
topic: navigation
order: 1
kind: walkthrough
lede: "**내비게이션**은 Live View에서 목적지까지 안내합니다. 홈의 **어디로 갈까요?**로 검색하고, 경로를 고르고, **시작**을 누른 다음 회전 카드와 음성 안내를 따르세요. 경로는 내 키로 Stadia Maps에서 받으며, 키는 휴대폰에 암호화해 보관됩니다. 안내는 표시만 하며 차량을 제어하지 않습니다."
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "로그인"
    text: "CommaView 0.0.167 이상에서 베타 계정으로 로그인해야 합니다. 로그아웃 상태에서는 내비게이션을 쓸 수 없습니다."
  - title: "Stadia Maps 키"
    text: "내 Stadia Maps 계정의 API 키. 경로는 내 계정과 그 약관에 따라 요청됩니다."
  - title: "차량 위치 켜기"
    text: "안내는 comma의 GPS를 따릅니다. 홈에서 comma의 **차량 위치**를 켜세요."
  - title: "휴대폰의 인터넷"
    text: "검색과 경로에 씁니다. comma의 Wi‑Fi에 인터넷이 없으면 모바일 데이터를 씁니다."
howItWorks:
  - title: "어디로 갈까요?"
    text: "OpenStreetMap 데이터(Photon)로 comma 근처의 장소를 찾습니다."
    edge: "내 키"
  - title: "Stadia Maps"
    text: "휴대폰이 내 키로 요청한 경로를 계획합니다. CommaView를 거치는 것은 없습니다."
  - title: "Live View"
    text: "comma의 위치에서 회전 카드, 지도, 음성 안내로 안내합니다."
steps:
  - id: open
    title: "지도 및 내비게이션 열기"
    body: |
      **설정**을 누르고 **지도 및 내비게이션**을 누르세요. 로그인한 상태에서는 예전에 오프라인 지도가 있던 항목입니다.
    screen: support-settings
    pins:
      - target: maps-row
        text: "**지도 및 내비게이션**."
  - id: get-key
    title: "Stadia Maps에서 키 받기"
    body: |
      **내 Stadia Maps 키** 아래의 **API 키**에 **추가 안 됨**이 표시되어 있습니다. **Stadia Maps에서 키 받기**를 누르면 브라우저에서 Stadia 가입 페이지가 열립니다. 가입한 다음 Stadia Maps 대시보드에서 API 키를 복사하세요.
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**내 Stadia Maps 키**: “경로에는 내 Stadia Maps 키가 필요합니다…”"
      - target: get-key
        text: "**Stadia Maps에서 키 받기**로 Stadia 가입 페이지가 열립니다."
      - target: add-key
        text: "키를 복사했으면 **추가**."
    note: "Stadia의 사이트는 Stadia의 것이므로 싣지 않았습니다. 대시보드에서 키의 사용량, 요금제, 한도를 볼 수 있습니다."
  - id: add-key
    title: "붙여넣고 확인 후 저장"
    body: |
      CommaView로 돌아와 **추가**를 누르세요. **붙여넣기**를 눌러 키를 입력란에 넣고 **확인 후 저장**을 누르세요. CommaView는 키를 확인하려고 정해진 두 지점 사이의 짧은 경로 하나만 Stadia Maps에 요청하며, 내 정보는 보내지 않습니다: **Stadia Maps로 확인하는 중…**. 받아들여지면 **API 키**에 **•••• e1f0**처럼 가려서 표시됩니다.
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "가려서 표시되는 **내 Stadia Maps API 키**."
      - target: paste
        text: "클립보드에서 **붙여넣기**."
      - target: check-and-save
        text: "**확인 후 저장**."
    note: "“이 휴대전화에만 암호화해 보관합니다. 보관하기 전에 Stadia Maps에 짧은 경로를 하나 요청해 확인합니다.” 지원 번들이나 충돌 보고서에는 절대 들어가지 않습니다."
  - id: where-to
    title: "홈에서 어디로 갈까요? 누르기"
    body: |
      주차 상태에서 홈의 comma 카드 아래에 있는 **어디로 갈까요?**를 누르세요. 장소나 주소를 입력하거나, 마이크를 눌러 말하세요. 저장해 두면 **집**과 **직장**을 카드에서 한 번에 고를 수 있습니다.
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**어디로 갈까요?**로 검색이 열립니다."
      - target: voice
        text: "**음성으로 ‘어디로 갈까요?’**."
      - target: home-chip
        text: "저장했다면 **집**."
  - id: pick
    title: "장소 고르기"
    body: |
      comma 근처의 결과가 주소와 거리와 함께 나오고, 이어서 저장한 장소와 최근 장소가 나옵니다. 원하는 곳을 누르세요.
    screen: navigation-search
    pins:
      - target: search-field
        text: "**장소 또는 주소 검색**."
      - target: first-result
        text: "주소와 comma로부터의 거리가 있는 결과."
    note: "차가 움직이는 동안에는 입력할 수 없습니다: “차량이 움직이는 동안에는 입력할 수 없습니다. 음성이나 저장된 장소를 사용하세요.”"
  - id: start
    title: "경로를 고르고 시작 누르기"
    body: |
      경로 미리보기에 지도 위의 경로, 소요 시간, 거리, 도착 예정 시각이 나옵니다. 경로마다 **최단 시간**, **경로 2** 같은 칩이 있습니다. **시작**을 누르면 안내가 시작되고 Live View가 열립니다.

      **집으로 저장**과 **직장으로 저장**으로 장소를 저장해 홈에서 한 번에 고를 수 있습니다.
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "경로: **최단 시간**, **경로 2**…"
      - target: start
        text: "**시작**."
      - target: save-home
        text: "**집으로 저장**, 그리고 옆의 **직장으로 저장**."
  - id: follow
    title: "Live View에서 안내 따르기"
    body: |
      회전 카드에 다음 회전이 표시됩니다. 화살표, 거리, 안내, 그다음 안내, 도착 예정 시각입니다. 음성 안내는 회전마다 약 20초 전, 바로 직전, 그리고 도착할 때 나옵니다. CommaView 자체 주행 화면에서는 차선과 회전 출구에 화살표가 그려집니다.

      회전을 놓치면 몇 초 안에 새 경로가 나옵니다. 도착해서 차를 끄면 안내가 알아서 끝납니다.
    tabs:
      - label: "휴대폰"
        body: |
          세로로 들면 회전 카드와 지도가 영상 아래에 있습니다.
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "회전 카드."
          - target: end
            text: "**내비게이션 종료**."
          - target: mute
            text: "**안내 음성 끄기**."
          - target: map-button
            text: "**지도**로 이번 안내 동안 지도를 숨기거나 다시 보여 줍니다."
      - label: "차량 화면"
        body: |
          헤드 유닛에서 영상 옆에 공간이 있으면 지도와 회전 카드가 별도 패널에 나옵니다. 공간이 없으면 CommaView 화면이 영상 모서리에 지도를 자연스럽게 겹칩니다. 구분선을 끌어 패널 너비를 바꾸세요.
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "회전 카드."
          - target: divider
            text: "지도 너비를 바꾸는 구분선."
          - target: map-button
            text: "**지도**."
    warn: "안내 설정은 주차 상태에서 하세요. 운전 중에는 CommaView를 조작하지 마세요. 그러라고 회전 카드와 음성이 있습니다. openpilot과 차량 자체의 알림이 우선입니다."
  - id: send
    title: "포크가 받는다면 장소를 comma로 보내기"
    body: |
      경로 미리보기의 **시작** 아래에, 자체 내비게이션이 목적지를 받는 포크를 위한 **comma로 보내기**가 있습니다. StarPilot, carrotpilot, openpilot 내비게이션(알파), 그리고 이를 이어받은 sunnypilot의 내비게이션입니다. 다른 포크에서는 나오지 않습니다.

      누르면 CommaView가 먼저 묻고, 회전 시 감속처럼 현재 설정에서 포크가 주행에 어떤 영향을 주는지 알려 줍니다. **보내기**를 누르세요: “comma로 보냈습니다. StarPilot이(가) 그곳에서 자체 경로를 계획합니다.” 포크는 자체 서비스로 경로를 계획하므로 CommaView의 경로와 다를 수 있습니다. **comma에서 지우기**로 다시 지울 수 있으며, 안내를 끝내도 지워집니다.
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**보내기**."
    note: "comma로 보내기 아래의 **모든 경로를 이 comma로 보내기**를 켜면 시작을 누를 때마다 경로를 보냅니다. 포크의 주행 설정이 바뀌면 다시 동의할 때까지 알아서 일시 중지됩니다."
check: "**지도 및 내비게이션**의 **API 키**에 키가 가려서 표시되고, 경로 미리보기에 **경로 제공: Stadia Maps · 안내는 표시만 하며 차량을 제어하지 않습니다.**가 표시됩니다."
fixes:
  - q: "“경로를 받으려면 내 Stadia Maps 키를 추가하세요: 설정 › 지도 및 내비게이션.”"
    a: "아직 보관된 키가 없습니다. 경로 미리보기에서 **키 추가**를 누르거나 [2단계와 3단계](#step-get-key)를 따르세요. 어디로 갈까요?, 검색, 장소는 키 없이도 됩니다."
  - q: "“Stadia Maps가 이 키를 받아들이지 않았습니다(401). 대시보드에서 키 전체를 복사했는지 확인하세요.”"
    a: "Stadia Maps 대시보드에서 키 전체를 다시 복사해 한 번 더 붙여넣으세요."
  - q: "“Stadia Maps 키가 아닙니다.”"
    a: "붙여넣은 것이 API 키 형식이 아니라서 아무것도 보내지 않았습니다. Stadia Maps 대시보드에서 API 키(문자, 숫자, 하이픈)를 복사하세요."
  - q: "“Stadia Maps가 이 키를 거부했습니다(403). 요금제에 경로 기능이 포함되지 않았을 수 있습니다.”"
    a: "Stadia Maps 대시보드에서 요금제를 확인하세요."
  - q: "“내 Stadia Maps 키가 한도를 초과했습니다(429)”"
    a: "이번 달 크레딧을 다 썼거나 방금 요청이 너무 많았습니다. Stadia Maps 대시보드에서 확인하세요. 앱은 5분 동안 그 키로 요청하지 않습니다."
  - q: "“키를 확인하려고 Stadia Maps에 연결하지 못했습니다. 이 휴대전화의 인터넷 연결을 확인하고 다시 시도하세요.”"
    a: "지금 휴대폰에 인터넷이 없습니다. 모바일 데이터나 인터넷이 되는 Wi‑Fi로 다시 시도하세요."
  - q: "홈에 **어디로 갈까요?**가 없습니다"
    a: "내비게이션은 CommaView 0.0.167부터 로그인한 회원용입니다. 로그아웃 상태이거나 이용권을 확인할 수 없으면 나오지 않습니다. 중국 본토에서는 꺼져 있습니다."
  - q: "회전 카드에 “차량 위치가 꺼져 있음”이 표시됩니다"
    a: "안내에는 comma의 위치가 필요합니다. 홈에서 이 comma의 **차량 위치**를 켜세요."
  - q: "회전 카드에 “GPS 대기 중”이 표시됩니다"
    a: "안내는 comma가 처음 위치를 잡으면 시작됩니다. 하늘이 트인 곳에서 잠시 기다리세요."
  - q: "“한 번에 가기에는 너무 멉니다”"
    a: "내비게이션은 최대 1,500 km(930마일) 떨어진 곳까지 경로를 계획합니다. 중간 경유지를 고른 다음 그곳에서 이어 가세요."
  - q: "**comma로 보내기**가 없습니다"
    a: "경로 미리보기에서만, 그리고 내비게이션이 목적지를 받는 포크(StarPilot, carrotpilot, 또는 openpilot이나 sunnypilot의 내비게이션(알파))에서만 나옵니다."
  - q: "“이 경로를 보낼 comma에 연결할 수 없습니다.”"
    a: "이 휴대폰을 comma와 같은 네트워크에 연결한 다음 **다시 시도**를 누르세요."
  - q: "“comma에서 openpilot 내비게이션(알파)이 꺼져 있습니다.”"
    a: "주차 상태에서 **내비게이션(알파) 켜기**를 누르세요. 시작할 때마다 이를 끄는 릴리스 빌드에서는 아직 켜 둘 수 없습니다."
related: [live-view, car-screens, overlays]
---

## Live View의 지도

**설정 › 지도 및 내비게이션 › Live View 지도**에서 지도가 나올 곳을 고릅니다.

- **배치**: **자동**(공간이 있으면 영상 옆, 없으면 모서리), **영상 옆**, **모서리**. comma 3X, comma four, StarPilot, Surround 화면에서는 지도가 항상 영상 옆에 나옵니다.
- **영상 옆 너비**는 Live View에서 구분선을 끌어 정합니다. **재설정**으로 되돌립니다.
- **지도 테마**: **앱과 동일**(기본값: CommaView가 밝으면 밝게, 어두우면 어둡게), **자동**(comma가 있는 곳의 일출부터 일몰까지 밝게), **휴대폰과 동일**, **밝게**, **어둡게**. 모든 지도에 적용됩니다: Live View의 지도, 홈의 위치 카드, **차량 위치**, 경로 미리보기.

## 음성 안내와 내 장소

- **음성 안내**로 음성을 끄고 켭니다. 회전 카드의 스피커, **안내 음성 끄기**도 같은 설정입니다.
- **내 장소**: **집**, **직장**, **최근 장소**. 이 휴대폰에 보관됩니다. **지우기**로 최근 장소를 지웁니다.

## 다른 앱의 장소

Google 지도 등 지도 앱에서 장소를 공유하고 **CommaView로 길 안내**를 고르세요. 저장한 장소처럼 홈에서 경로 미리보기가 열립니다.

## Mapbox

계정에서 제공되면, 설정 › 지도 및 내비게이션에서 Stadia Maps 대신 내 Mapbox 토큰으로 경로를 받을 수 있습니다.

## 개인정보 보호

Stadia Maps 키는 이 휴대폰에만 암호화해 보관되며, 로그나 지원 번들에 절대 들어가지 않습니다. 경로는 그 키로 휴대폰에서 Stadia Maps로 요청되며, CommaView 계정 서비스로는 아무것도 가지 않습니다. 검색은 comma 위치 근처로 Photon에 보냅니다. 키를 지우거나 로그아웃하면 휴대폰에서 삭제됩니다.

## 안전

안내 설정은 주차 상태에서 하고, 회전 카드와 음성에 맡기세요. 내비게이션은 표시만 하며, 조향, 제동, openpilot의 동작을 바꾸지 않습니다. 운전 중에는 CommaView를 조작하지 마세요. openpilot이 요구하는 대로 눈은 도로에, 손은 핸들에 두세요.
