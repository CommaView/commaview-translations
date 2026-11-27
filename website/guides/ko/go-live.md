---
title: "YouTube나 다른 서버로 라이브 방송하기"
description: "Live View에 보이는 도로와 주행 화면을 YouTube 채널이나 RTMP 서버로 720p 또는 1080p로 방송합니다. 한 번 설정하면 Live View에서 바로 라이브를 시작할 수 있습니다."
topic: screens
order: 5
kind: walkthrough
lede: "**라이브 시작**은 Live View에 보이는 도로와 주행 화면을 휴대폰에서 YouTube 채널이나 RTMP 서버로 720p 또는 1080p로 방송합니다. 설정에서 한 번 준비해 두면 Live View에서 시작할 수 있습니다."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View 작동"
    text: "Android 휴대폰의 CommaView가 comma와 페어링되어 있어야 합니다. 아직이라면 [CommaView를 설정하세요](/ko/guides/setup)."
  - title: "방송할 곳"
    text: "로그인할 YouTube 채널, 또는 YouTube 스튜디오나 다른 RTMP 서버의 스트림 키."
  - title: "휴대폰의 인터넷"
    text: "comma의 Wi‑Fi에 인터넷이 없으면 방송은 휴대폰의 모바일 데이터를 씁니다. 720p에서 시간당 약 1.4 GB입니다."
howItWorks:
  - title: "comma"
    text: "평소처럼 휴대폰에 Live View를 보냅니다."
  - title: "휴대폰"
    text: "Live View가 그리는 화면을 초당 20프레임, 720p 또는 1080p로 방송합니다."
    edge: "인터넷"
  - title: "YouTube 또는 내 서버"
    text: "시청을 허용한 사람에게 보여 줍니다."
steps:
  - id: settings
    title: "설정 › 라이브 방송 열기"
    body: |
      **설정**을 열고 **라이브 방송**을 누르세요. 설정하기 전까지는 그 항목에 **설정하기**가 표시됩니다.
    screen: support-settings
    pins:
      - target: live-streaming-row
        text: "**라이브 방송**."
  - id: destination
    title: "방송할 곳 고르기"
    tabs:
      - label: "YouTube로 로그인"
        body: |
          **YouTube로 로그인**을 누르세요. 브라우저에서 Google 로그인이 열리면 계정과 채널을 고르세요. 로그인하면 라이브를 시작할 때마다 채널에 방송이 만들어지고 YouTube가 알아서 시작합니다. 스트림 키도, YouTube 스튜디오에서 누를 것도 없습니다. 그러면 **방송 대상** 카드에 채널과 **로그인됨**이 표시됩니다.
        screen: settings-live-streaming
        pins:
          - target: destination-row
            text: "**방송 대상**: 로그인된 채널."
        note: "Google 자체의 로그인 페이지는 싣지 않았습니다."
      - label: "스트림 키 또는 서버"
        body: |
          **스트림 키 사용**(또는 **방송 대상 설정**)을 누르고, **플랫폼**에서 **YouTube**나 **기타 서버**를 고른 다음 스트림 키를 붙여넣으세요. YouTube라면 YouTube 스튜디오에서 만들기 › 라이브 스트리밍 시작 › 스트림으로 가서 스트림 키를 복사하고, 영상이 도착하면 방송이 시작되도록 거기서 자동 시작을 켜세요. 다른 서버라면 `rtmp://`나 `rtmps://` 주소도 붙여넣으세요. **방송 대상 저장**을 누르세요.
        screen: settings-live-streaming-destination
        pins:
          - target: platform
            text: "**플랫폼**."
          - target: stream-key
            text: "스트림 키. 이 휴대폰에만 보관되며, 해당 서버로만 보냅니다."
          - target: save
            text: "**방송 대상 저장**."
        note: "`rtmp://`는 스트림 키를 암호화하지 않고 보냅니다. 서버가 지원하면 `rtmps://`를 쓰세요."
  - id: choices
    title: "시청 대상, 화질, 소리 확인하기"
    body: |
      - **시청 가능 대상**(YouTube에 로그인한 경우): **공개**, **일부 공개**, **비공개**. 처음에는 **일부 공개**입니다. 스트림 키라면 YouTube 스튜디오에서 고르세요. 시청자는 내가 어디를 달리는지 볼 수 있습니다.
      - **제목 및 설명**(YouTube에 로그인한 경우): 방송마다 붙는 이름. 날짜, 차량 등을 넣는 칩이 있습니다.
      - **화질**: 720p 또는 1080p. 각각 시간당 모바일 데이터 사용량이 대략 표시됩니다.
      - **소리**: comma의 마이크나 이 휴대폰의 마이크를 고르지 않으면 꺼져 있습니다. 동승자를 포함해 차 안의 모든 사람의 소리가 들어갑니다. 소리는 방송과 실시간 사본에만 들어가며 CommaView로 보내지 않습니다.

      **라이브 방송 전에**에 데이터 사용량, 운전자 카메라, 방송이 멈추는 경우가 정리되어 있습니다.
    screen: settings-live-streaming
    pins:
      - text: "**제목 및 설명**."
      - target: sound-row
        text: "**소리**."
  - id: go
    title: "Live View에서 라이브 시작 누르기"
    body: |
      Live View를 열고 **라이브 시작**을 누르세요. **시작 중…**이 표시된 뒤 방송 시간이 나옵니다. 출발하기 전에 시작하고, 그다음에는 건드리지 마세요.
    screen: phone-live-view
    pins:
      - target: go-live-button
        text: "**라이브 시작**. 들어가지 않으면 **더 보기**에 있습니다."
    warn: "**운전자 카메라**가 켜져 있으면 방송에 운전자 카메라가 나오며, **운전자 카메라**에 **실시간**이 표시됩니다. 방송에 운전자 카메라를 넣지 않으려면 **운전자 카메라**를 끄세요."
  - id: share
    title: "시청 링크 공유하기"
    body: |
      **세부 정보**에서 방송 항목에 **방송 중**과 방송 시간, 전송 속도, 사용한 데이터, 네트워크가 표시됩니다. YouTube에 로그인했다면 그 아래의 **시청 링크 공유**로 방송의 `youtu.be` 링크를 공유할 수 있습니다.
    screen: phone-live-view-go-live
    pins:
      - target: stop-live
        text: "방송 중인 **라이브 시작**과 타이머."
      - target: streaming
        text: "**방송 중**과 방송 시간."
      - target: share-watch-link
        text: "**시청 링크 공유**."
  - id: stop
    title: "주차하면 방송 중지하기"
    body: |
      **라이브 시작**을 다시 누르면 멈춥니다. Live View를 나갈 때, 알림의 **중지**를 누를 때, 영상이 멈추고 1분이 지났을 때도 방송이 멈춥니다. 다른 앱으로 전환하거나 휴대폰을 잠가도 계속됩니다.
check: "Live View의 **라이브 시작**에 방송 색으로 타이머가 돌아가고, 세부 정보에 **방송 중**이 표시되며, YouTube나 서버에서 방송이 재생됩니다."
fixes:
  - q: "Live View에 라이브 시작이 없습니다"
    a: "아직 라이브 방송을 설정하지 않았습니다. 세부 정보에 **여기에서 라이브 방송을 하려면 설정에서 라이브 방송을 설정하세요**가 표시됩니다. 또는 조작 버튼이 다 들어가지 않아 **더 보기**에 있습니다."
  - q: "“설정 › 라이브 방송에서 스트림 키를 추가하세요”"
    a: "방송할 곳이 없습니다. **설정 › 라이브 방송**에서 YouTube로 로그인하거나 스트림 키를 추가하세요."
  - q: "스트림 키로는 YouTube 방송이 시작되지 않습니다"
    a: "스트림 키를 쓸 때는 YouTube 스튜디오의 라이브 스트리밍 시작으로 방송을 매번 시작하거나, 거기서 자동 시작을 켜세요. YouTube로 로그인했다면 알아서 시작됩니다."
  - q: "“키에 공백이 있습니다”"
    a: "스트리밍 서비스에서 키를 다시 복사해 붙여넣으세요."
  - q: "“소리 없음: Browser View가 소리 없이 실행 중입니다”"
    a: "라이브 방송은 Browser View의 화면을 공유하는데, Browser View에는 소리가 없습니다. 소리를 넣으려면 라이브 방송 전에 Browser View를 중지하세요. 소리 없이 시작한 녹화도 마찬가지입니다."
  - q: "방송이 저절로 멈춥니다"
    a: "Live View가 매번 메시지로 이유를 알려 줍니다. 방송은 영상이 멈추고 1분 뒤에, 그리고 Live View를 나갈 때도 멈춥니다."
related: [live-view, browser-view, live-copy]
blogPost: commaview-0-0-165-go-live-send-to-commaview
---

## 방송마다 사본 남기기

**설정 › 녹화 › 각 라이브 방송 저장**을 켜면 라이브 방송마다 보낸 그대로의 MP4를 방송 화질로 녹화에 저장합니다. 휴대폰에 보관됩니다. [실시간 사본 남기기](/ko/guides/live-copy)를 보세요.

## 방송에 들어가는 것과 들어가지 않는 것

- **들어가는 것:** 도로와 그 위에 그린 주행 화면, 그리고 **운전자 카메라**가 켜져 있는 동안의 운전자 카메라.
- **들어가지 않는 것:** Live View의 조작 버튼, 세부 정보, 메시지. 내비게이션 지도는 설정에서 고를 수 있을 때 **방송에 지도 표시**를 켠 경우에만, CommaView 모서리의 지도만 들어갑니다.
- 녹화와 라이브 방송은 따로 작동합니다. 주행을 녹화하면서 동시에 방송할 수 있습니다.

## 안전

라이브 방송 설정과 시작은 주차 상태에서 하고, 그다음에는 건드리지 마세요. 운전 중에는 CommaView를 조작하지 마세요. openpilot이 요구하는 대로 눈은 도로에, 손은 핸들에 두세요. 시청자는 내가 어디를 달리는지 볼 수 있습니다.
