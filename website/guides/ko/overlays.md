---
title: "주행 화면 고르고 오버레이 팩 추가하기"
description: "Live View가 도로를 그리는 방식을 고르세요: comma four 화면, comma 3X 화면 또는 CommaView 자체 화면. 그다음 포크가 자체 화면에 그리는 것을 위해 오버레이 팩을 추가하세요."
topic: screens
order: 6
kind: walkthrough
lede: "Live View는 도로 카메라 위에 주행 화면을 그립니다: **comma four** 화면, **comma 3X** 화면 또는 **CommaView** 자체 화면입니다. comma 화면은 포크의 모습으로 그려집니다. **오버레이 팩**은 BluePilot의 하이브리드 게이지나 dragonpilot의 무지개 경로처럼, 포크 자체 화면에는 있지만 CommaView가 그리지 않는 것을 더합니다."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View 작동"
    text: "Android 휴대폰의 CommaView가 comma와 페어링되어 있어야 합니다. 아직이라면 [CommaView를 설정하세요](/ko/guides/setup)."
  - title: "스토어는 로그인 필요"
    text: "CommaView의 팩은 회원만 둘러볼 수 있습니다. 로그아웃 상태에서도 파일이나 링크로 팩을 추가할 수 있습니다."
steps:
  - id: switch
    title: "Live View에서 화면 전환하기"
    body: |
      Live View에서 주행 화면 전환 버튼을 누르세요. 버튼에는 보여 주는 화면의 이름이 붙어 있으며, 누를 때마다 **comma 4**, **comma 3X**, **CommaView** 순으로 바뀌고 다시 처음으로 돌아옵니다. 마지막으로 둔 화면이 다음에도 쓰입니다.
    screen: phone-live-view
    clip: onroad-screen
    pins:
      - target: onroad-screen-button
        text: "보여 주는 화면의 이름이 붙은 주행 화면 전환 버튼."
    note: "다른 조작 버튼 옆에 들어가지 않으면 **더 보기**에 **주행 화면**으로 있습니다. 녹화 중에는 흐리게 표시됩니다. 녹화는 시작할 때의 화면을 유지합니다."
  - id: display
    title: "또는 설정 › 디스플레이에서 고르기"
    body: |
      고르기 전에 모든 화면을 보려면 **설정 › 디스플레이**를 여세요. **주행 화면** 카드에 고른 화면의 미리보기가 도로 사진 위에 표시되며, comma의 카메라에 맞춘 구도로 포크의 모습으로 그려집니다. 그 아래의 **작동 중**, **운전자 개입**, **해제됨**으로 보여 줄 순간을 바꿀 수 있으며, 아무것도 저장하지 않습니다.
    screen: settings-display
    pins:
      - target: onroad-screen-card
        text: "고른 화면의 미리보기."
      - target: onroad-screen
        text: "**주행 화면**: 누르면 목록이 나옵니다."
  - id: pick
    title: "화면 고르기"
    body: |
      목록의 각 화면에는 작은 그림과 설명이 있습니다.

      - **comma four**: 도로 위에 바뀔 때마다 표시되는 최대, 그 옆의 핸들과 신뢰도.
      - **comma 3X**: 상태 테두리, 최대 상자, 큰 속도 표시, 아래쪽을 따라 나오는 알림.
      - **CommaView**: 흐르는 듯한 경로, 앞차 잠금 표시, CommaView 자체의 속도, 상태, 알림.

      고르면 저장되고 미리보기, 옵션, Live View가 바뀝니다. 어느 comma에서든 모든 화면을 쓸 수 있습니다.
    screen: settings-display-onroad-screens
    clip: display-pick
    pins:
      - target: comma-four-option
        text: "**comma four**."
      - target: comma-3x-option
        text: "**comma 3X**."
      - target: commaview-option
        text: "**CommaView**."
    note: "알림, 경고, 운전자 모니터링 상태는 어떤 화면을 고르든 항상 comma 자체의 색을 씁니다."
  - id: store
    title: "오버레이 팩 스토어 열기"
    body: |
      **설정 › 오버레이 팩**을 열거나 홈의 **오버레이 팩** 카드를 누르세요.
    tabs:
      - label: "로그인한 경우"
        body: |
          스토어에는 CommaView의 **공식** 팩이 먼저, 이어서 **커뮤니티** 팩이 나오며, 모두 CommaView가 검토했습니다. **내 comma용**에 comma가 실행하는 포크용 공식 팩이 나옵니다. 검색하거나 **전체**, **공식**, **커뮤니티**, **내 comma용**으로 목록을 좁히세요.
        screen: overlay-packs-store
        pins:
          - target: search
            text: "**팩 검색**."
          - text: "**내 comma용**: comma의 포크용 공식 팩."
          - target: bluepilot-row
            text: "BluePilot HUD 같은 **공식** 팩."
          - target: yours
            text: "**내 팩**: 이 휴대폰에 있는 것."
      - label: "파일이나 링크로"
        body: |
          누군가 `.cvpack` 파일이나 링크(GitHub, gist, Discord 첨부 파일)를 공유했나요? **내 팩**을 열고 **직접 팩 추가** 아래의 **파일로 설치** 또는 **링크 붙여넣기**를 누르세요. 이렇게 추가한 팩은 CommaView가 검토하지 않았으며, 설치 대화 상자에도 그렇게 표시됩니다.
  - id: install
    title: "팩 설치하기"
    body: |
      팩을 누르면 미리보기, 작동하는 포크(**지원: …**), Live View에 더해지는 것이 나옵니다. **설치**를 누르고 대화 상자에서 다시 **설치**를 누르세요. 팩이 이 휴대폰과 페어링된 comma에 들어갑니다.
    screen: overlay-pack-detail
    pins:
      - text: "미리보기: 팩을 적용한 Live View. 누르면 확대됩니다."
      - target: install
        text: "**설치**."
    note: "공식 팩은 대상 포크에서만 작동합니다. 페어링된 comma 중 대상 포크를 실행하는 것이 없으면 대화 상자에 그렇게 표시됩니다. 설치는 되지만 대상 포크가 실행될 때까지 Live View에는 나오지 않습니다."
  - id: drive
    title: "다음 주행에서 확인하기"
    body: |
      설치하면 스토어에, 이 휴대폰이 comma에 연결될 때 팩이 comma로 가고 차가 꺼질 때 거기서 시작된다고 표시됩니다. 다음 주행에서 Live View를 열면 팩이 comma four, comma 3X, CommaView 화면에 주행 화면 자체의 알림 아래로 그려집니다.

      팩을 끄려면 **내 팩**을 여세요. 팩마다 스위치가 하나 있으며, 이 휴대폰과 페어링된 모든 comma에 함께 적용됩니다.
check: "Live View의 **세부 정보**에서 **오버레이 팩** 줄에 팩 이름과 **실행 중**이 표시됩니다."
fixes:
  - q: "주행 화면 전환 버튼이 흐리게 표시됩니다"
    a: "녹화 중입니다. 녹화를 멈추거나 끝날 때까지 기다린 다음 전환하세요."
  - q: "세부 정보에 팩이 “이 포크용 아님”으로 나옵니다"
    a: "팩은 다른 포크의 화면용이라 내 포크에는 아무것도 그리지 않습니다. 공식 팩의 대상 포크는 **지원: …**에 나옵니다."
  - q: "Live View에 아직 팩이 나오지 않습니다"
    a: "팩은 휴대폰이 comma에 연결될 때 comma로 가고, 차가 꺼질 때 거기서 시작됩니다. 휴대폰을 comma의 네트워크에 둔 채 차를 껐다가 다시 켜고 Live View를 여세요."
  - q: "“CommaView의 팩을 보려면 로그인하세요”"
    a: "스토어는 로그인한 회원에게 CommaView의 팩을 보여 줍니다. **로그인**을 누르세요. 휴대폰에 이미 있는 팩은 로그아웃 상태에서도 계속 작동합니다."
  - q: "“my.commaview.com에 연결할 수 없습니다”"
    a: "이 휴대폰의 인터넷 연결을 확인한 다음 **다시 시도**를 누르세요. **내 팩**에는 휴대폰에 있는 모든 것이 그대로 나옵니다."
related: [live-view, record, forks]
blogPost: commaview-0-0-166-languages-browser-view
---

## 화면별 옵션

미리보기 아래, **설정 › 디스플레이**에 고른 화면의 옵션이 나옵니다.

- **comma four 옵션**: **미리보기 구도**(comma four의 화면 틀에 정확히 맞추기, 카메라를 더 넓게 보여 주기, 또는 이 화면을 채우도록 자르기)와 **작은 신뢰도 패널**(영상을 더 넓게 보도록 패널과 공을 작게).
- **CommaView 옵션**: **카메라 구도**(**화면 채우기**는 가로 화면을 채우도록 카메라를 자르고, **카메라 전체**는 필요하면 검은 띠를 넣어 전부 보여 줍니다)와, CommaView의 경로, 속도, 잠금 표시를 고정하는 **동작 줄이기**.
- **comma 3X**: 없음. comma가 그리는 그대로 그립니다.

그다음 **모든 화면 공통**: 조작 버튼을 좌우로 바꾸는 **운전석 위치**, **테마**, 햇빛과 눈부심에 대응하는 **주간 대비**, 그리고 화면 가장자리를 잘라 내는 차량 화면을 위한 **화면 가장자리**([차량 화면](/ko/guides/car-screens))입니다.

녹화에서 만드는 다시 보기는 나중에 무엇을 고르든, 녹화할 때 Live View가 그린 것을 그립니다.

## 오버레이는 어디서 오나

CommaView는 무엇을 그릴지 추측하지 않습니다. comma의 런타임이 openpilot 자체 화면이 읽는 것과 같은 주행 데이터(경로, 차선, 앞차, 속도, 알림, 운전자 모니터링)를 영상과 함께 보내고, 앱이 보여 주는 카메라에 맞춰 휴대폰에서 그립니다. 그 데이터가 늦거나, 없거나, 다른 카메라용이면 CommaView는 틀릴 수 있는 것을 그리기보다 그 부분을 빼 둡니다.

## 안전

화면 선택과 팩 설치는 주차 상태에서 하세요. 운전 중에는 CommaView를 조작하지 마세요. openpilot이 요구하는 대로 눈은 도로에, 손은 핸들에 두세요. 오버레이는 보기 위한 것이지 운전 보조가 아닙니다. comma 자체의 알림과 차량 계기판이 우선입니다. 운전자 모니터링 아이콘은 주의하고 있다는 증거가 아니며, 다시 보기의 오버레이는 주행을 돌아보기 위한 것이지 무슨 일이 있었는지 정확히 보여 주는 증거가 아닙니다.
