---
title: "Live View로 comma 보기"
description: "Live View를 열어 comma의 도로 카메라와 주행 화면을 휴대폰에서 보고, 조작 버튼, 세부 정보, 문제가 있을 때의 메시지를 알아봅니다."
topic: screens
order: 1
kind: walkthrough
lede: "**Live View**는 comma의 도로 카메라를 실시간으로, 주행 화면(comma four, comma 3X 또는 CommaView 자체 화면)을 겹쳐서 보여 줍니다. 영상은 인터넷이 아니라 내 네트워크를 통해 comma에서 바로 옵니다."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView 설정 완료"
    text: "Android 휴대폰의 CommaView가 comma와 페어링되어 있어야 합니다. 아직이라면 [CommaView를 설정하세요](/ko/guides/setup)."
  - title: "차가 켜져 있음"
    text: "openpilot은 주행 중에만 영상을 보냅니다. 차가 꺼져 있으면 Live View는 기다렸다가 차가 켜지면 알아서 시작합니다."
  - title: "하나의 네트워크"
    text: "휴대폰과 comma가 같은 Wi‑Fi나 핫스팟에 있어야 합니다. 차 안에서는 [차 안에서 연결하기](/ko/guides/connect-in-the-car)를 보세요."
steps:
  - id: open
    title: "홈에서 Live View 열기"
    body: |
      comma가 연결되고 차가 켜진 상태에서 **홈**의 **Live View 열기**를 누르세요. 몇 초 안에 도로가 나오고 스트림 표시에 **실시간**이 표시됩니다.
    screen: phone-home
    pins:
      - target: open-live-view
        text: "홈의 주 버튼인 **Live View 열기**."
    note: "차가 꺼져 있으면 Live View에 **comma가 온라인이지만 주행 중이 아닙니다**가 표시됩니다. 차가 켜지면 알아서 시작하며, **새로고침**으로 바로 시작할 수도 있습니다."
  - id: controls
    title: "화면 아래의 조작 버튼 알아보기"
    body: |
      세로로 들면 조작 버튼이 영상 아래에 있습니다.

      - **녹화**는 주행의 이 구간을 저장합니다. [주행 녹화하기](/ko/guides/record)를 보세요.
      - **저장**은 주행의 직전 3분과 다음 1분을 남깁니다.
      - 주행 화면 전환 버튼에는 보여 주는 화면의 이름(**CommaView**, **comma 4**, **comma 3X**)이 붙어 있으며, 누를 때마다 다음 화면으로 바뀝니다. [주행 화면 고르기](/ko/guides/overlays)를 보세요.
      - **라이브 시작**은 설정해 두면 Live View에 보이는 화면을 방송합니다. [라이브 방송하기](/ko/guides/go-live)를 보세요.
      - **운전자 카메라**는 화면 모서리에 운전자 카메라를 보여 줍니다.
      - **세부 정보**는 Live View의 정보와 카드를 엽니다.

      휴대폰의 너비와 글자 크기에 들어가지 않는 것은 **더 보기**에 들어갑니다. 줄어들거나 잘리는 것은 없습니다.
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**녹화**."
      - target: onroad-screen-button
        text: "주행 화면 전환."
      - target: driver-cam-button
        text: "**운전자 카메라**."
      - target: go-live-button
        text: "라이브 방송을 설정했다면 **라이브 시작**."
      - text: "**더 보기**에 들어가지 않는 것이 있습니다."
    note: "녹화 중에는 주행 화면 전환과 **운전자 카메라**가 흐리게 표시됩니다. **녹화**를 누르기 전에 고르세요."
  - id: details
    title: "세부 정보 열기"
    body: |
      **세부 정보**를 누르거나 화면 아래쪽의 시트를 끌어 올리세요. 스트림 상태, 영상, 런타임, comma의 소프트웨어와 주소, 녹화나 방송 중인지, 그리고 **Browser View** 카드가 표시됩니다. 링크로 **녹화**와 comma의 **장치 설정**을 열 수 있습니다.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**세부 정보** 시트."
      - text: "요약: 스트림 상태, 영상, 런타임."
      - target: recordings-link
        text: "**녹화**."
      - target: device-settings-link
        text: "이 comma의 **장치 설정**."
  - id: turn
    title: "휴대폰을 가로로 돌리거나 더 큰 화면 쓰기"
    body: |
      휴대폰을 가로로 돌리면 영상이 화면을 채우고, 조작 버튼은 운전석 쪽 레일로 갑니다. **세부 정보**는 화면 옆에 열리고, **나가기**로 Live View를 나갑니다.
    tabs:
      - label: "가로로 든 휴대폰"
        body: "레일에 같은 조작 버튼이 있습니다. 세로가 짧은 화면에서는 작아집니다."
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "레일 맨 위의 **녹화**."
          - target: more
            text: "**더 보기**에 **운전자 카메라**와 **세부 정보**가 있습니다."
          - target: exit
            text: "**나가기**로 Live View를 나갑니다."
      - label: "태블릿이나 차량 화면"
        body: "넓은 화면에서는 레일이 운전석 쪽에 있습니다. [차량 화면에서 CommaView 사용하기](/ko/guides/car-screens)를 보세요."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**녹화**."
          - target: onroad-screen-button
            text: "주행 화면 전환."
          - target: driver-cam-button
            text: "**운전자 카메라**."
          - target: details
            text: "**세부 정보**."
          - target: exit
            text: "**나가기**."
  - id: auto
    title: "Live View가 알아서 열리게 하기"
    body: |
      Live View만 보여 주려고 둔 휴대폰이나 헤드 유닛이라면, **설정 › 디스플레이**를 열고 **Live View 여는 중**의 **연결되면 Live View 열기**를 켜세요. 그러면 차가 켜진 상태에서 comma가 연결될 때 Live View가 알아서 열립니다. 나가면 다음 연결 때까지 닫힌 채로 있습니다.

      바로 아래의 **상태 표시줄 유지**를 켜면 화면 전체를 쓰지 않고 Live View 위에 시스템 시계를 보여 줍니다.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**연결되면 Live View 열기**."
  - id: leave
    title: "다 쓰면 Live View 나가기"
    body: |
      주차한 뒤 **나가기**나 뒤로를 누르세요. Live View를 나가면 라이브 방송, Browser View, 실시간 사본도 끝납니다. Live View는 한 번에 휴대폰이나 헤드 유닛 한 대에서만 열리므로, 다른 기기에서 열기 전에 지금 기기에서 나가세요.
check: "스트림 표시에 **실시간**이 나오고, 도로가 움직이며, 세부 정보의 스트림 상태가 **양호**입니다."
fixes:
  - q: "“comma가 온라인이지만 주행 중이 아닙니다”"
    a: "차가 꺼져 있거나 openpilot이 시작되지 않았습니다. 차가 켜지고 30초 안에 Live View가 알아서 돌아오며, **새로고침**을 눌러도 됩니다."
  - q: "“이 comma에 연결할 수 없음”"
    a: "휴대폰이 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다. comma가 응답하면 Live View가 다시 연결하며, **다시 시도**를 눌러도 됩니다. 그래도 안 되면 [CommaView가 comma를 찾을 수 없을 때](/ko/guides/comma-not-found)를 보세요."
  - q: "“다른 기기에서 Live View가 열려 있음”"
    a: "comma는 한 번에 휴대폰이나 헤드 유닛 한 대로만 스트리밍합니다. 다른 기기의 CommaView에서 홈으로 돌아가면 여기서 Live View가 알아서 시작됩니다."
  - q: "“차량 데이터가 들어오지 않습니다”"
    a: "영상은 오지만 차량의 속도, 방향 지시등, 알림이 오지 않습니다. comma를 재시작하면 해결됩니다."
  - q: "“영상 지연”"
    a: "1초 동안 새 프레임이 오지 않았습니다. Live View가 화면 옆에 이를 표시하고, 영상이 돌아오지 않으면 알아서 다시 연결합니다."
  - q: "“이 comma의 영상을 재생할 수 없습니다”"
    a: "휴대폰의 어떤 비디오 디코더로도 재생할 수 없었습니다. CommaView는 계속 시도합니다. CommaView가 살펴볼 수 있도록 설정에서 지원 신고를 보내 주세요: [지원 신고 보내기](/ko/guides/support-bundle)를 보세요."
related: [overlays, record, browser-view, car-screens]
---

## 안전

Live View는 주차 상태에서 열고, 그다음에는 건드리지 마세요. 운전 중에는 CommaView를 조작하지 마세요. openpilot이 요구하는 대로 눈은 도로에, 손은 핸들에 두세요. comma 자체의 알림과 차량 계기판이 우선입니다. CommaView는 comma가 보는 것을 보여 줄 뿐입니다.
