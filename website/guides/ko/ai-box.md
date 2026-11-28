---
title: "Android AI 박스에서 CommaView 실행하기"
description: "Android AI 박스로 차량의 CarPlay나 Android Auto 화면에 Live View를 띄우세요. 꽂고, CommaView를 설치하고, comma의 네트워크에 연결하고, 페어링하고, 화면에 맞춥니다."
topic: screens
order: 4
kind: walkthrough
lede: "차량에 순정 **유선** CarPlay나 Android Auto가 있다면, **Android AI 박스**로 CommaView의 Live View를 차량 자체 화면에 띄울 수 있습니다. 새 오디오도 배선도 필요 없습니다. 박스는 휴대폰을 꽂는 USB 포트에 꽂는 작은 Android 컴퓨터입니다. CommaView가 박스에서 실행되므로 휴대폰은 통화와 지도에 그대로 쓸 수 있습니다."
parked: true
updated: 2026-11-27
needs:
  - title: "유선 CarPlay 또는 Android Auto"
    text: "데이터를 전달하는 USB 포트를 통한 순정 유선 CarPlay나 유선 Android Auto. 박스가 차량의 방식을 지원하는지 확인하세요."
  - title: "진짜 Android가 실행되는 박스"
    text: "Android 8 이상이며 파일로 앱을 설치할 수 있어야 합니다. 폐쇄형 “동영상” 박스와 단순 무선 어댑터에서는 CommaView를 실행할 수 없습니다. [어떤 박스를 살까](/ko/blog/android-ai-box-commaview)."
  - title: "휴대폰의 CommaView"
    text: "먼저 휴대폰으로 comma를 설정한 다음 박스를 페어링하세요. [CommaView 설정하기](/ko/guides/setup)."
howItWorks:
  - title: "comma"
    text: "로컬 네트워크로 박스에 Live View를 보냅니다."
    edge: "Wi‑Fi"
  - title: "AI 박스"
    text: "다른 Android 기기처럼 CommaView를 실행합니다."
    edge: "USB"
  - title: "차량 화면"
    text: "CarPlay를 보여 주듯이 박스의 화면을 보여 줍니다."
steps:
  - id: plug-in
    title: "박스를 꽂고 CommaView 설치하기"
    body: |
      박스를 차량의 CarPlay나 Android Auto USB 포트에 꽂고 켜질 때까지 기다리세요. 우선 인터넷이 되는 Wi‑Fi에 연결하세요.

      박스의 브라우저에서 초대받은 이메일 주소로 [my.commaview.com](https://my.commaview.com)에 로그인하고, **Get the app** 아래의 **Download CommaView**를 누르세요. 이번 설치에만 브라우저의 설치를 허용하고 끝나면 다시 끄세요. CommaView를 열고 로그인하세요.
    note: "CommaView는 휴대폰의 CarPlay를 전달하는 모드가 아니라 박스의 Android 모드에서 실행하세요."
  - id: network
    title: "박스와 comma를 같은 네트워크에 연결하기"
    body: |
      Live View는 인터넷이 아니라 로컬 네트워크를 통해 comma에서 박스로 바로 가며, 둘 다 연결된 네트워크라면 무엇이든 됩니다.
    tabs:
      - label: "박스의 핫스팟"
        body: "SIM 카드가 있는 박스는 보통 핫스팟을 공유할 수 있습니다. 켜고 comma의 **설정 › 네트워크**에서 comma를 연결하세요."
      - label: "휴대폰의 핫스팟"
        body: "박스와 comma를 휴대폰의 핫스팟에 연결하세요. 둘 다 그 핫스팟으로 인터넷도 씁니다."
      - label: "comma의 핫스팟"
        body: "comma의 핫스팟을 켜고(openpilot에서는 테더링이라고 합니다) 박스에서 연결하세요."
    note: "대부분의 박스는 무선 CarPlay를 위해 휴대폰 연결에도 Wi‑Fi를 쓰며, 그동안 Wi‑Fi 인터넷이 끊기는 박스도 있습니다. 박스의 VPN은 끄세요."
  - id: pair
    title: "박스를 comma와 페어링하기"
    body: |
      휴대폰에서 comma의 **장치 설정**을 열고 **다른 휴대폰 페어링**을 누른 다음, **다른 휴대폰 추가** 아래의 **초대 코드 표시**를 누르세요. 박스에서 **CommaView를 실행 중인 comma 페어링**을 누르고, comma를 고른 다음 코드를 입력하거나 **QR 코드 스캔**을 누르세요. 모든 단계: [태블릿이나 차량 화면에서 CommaView 사용하기](/ko/guides/car-screens#step-pair).
  - id: edges
    title: "차가 잘라 내는 가장자리에서 앱을 안쪽으로 옮기기"
    body: |
      어떤 차는 박스가 보내는 화면의 가장자리를 잘라 내는데, Android는 이를 알 수 없습니다. **설정 › 디스플레이 › 화면 가장자리**를 여세요. 앱이 끝나는 곳에 선이 표시됩니다. 선이 한 바퀴 모두 보일 때까지 **−**와 **+**로 각 가장자리를 안쪽으로 옮긴 다음 **완료**를 누르세요. **재설정**을 누르면 끕니다.

      그다음 홈, Live View, 설정이 안쪽에 들어오는지 확인하세요.
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−**와 **+**로 각 가장자리를 안쪽으로 옮기고, **완료**로 저장합니다."
      - text: "역시 **설정 › 디스플레이**에 있는 **테마**: **이 기기와 동일**은 박스를 따릅니다."
  - id: auto
    title: "알아서 열리게 하기"
    body: |
      **설정 › 디스플레이**의 **Live View 여는 중**에서:

      - **이 기기가 시작되면 CommaView 열기**: 차와 함께 다시 시작하는 박스용.
      - **블루투스가 연결되면 CommaView 열기**: 휴대폰을 골라, 다시 시작하지 않고 절전 상태가 되는 박스용.
      - **연결되면 Live View 열기**: 차가 켜진 상태에서 comma가 연결되면 바로 Live View로 들어갑니다.

      CommaView가 알아서 열리도록 **다른 앱 위에 표시**를 허용하세요. 허용하지 않으면 알림으로 열지 묻습니다.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**연결되면 Live View 열기**."
  - id: check
    title: "Live View가 재생되는지 확인하고 출발하기"
    body: |
      차를 켠 상태에서 박스의 Live View를 여세요. 조작 버튼은 운전석 쪽 레일에 있으며 세로가 짧은 화면에서는 작아집니다. 운전하기 전에 영상이 재생되고 잘린 부분이 없는지 확인하세요.
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "레일 맨 위의 **녹화**."
      - target: details
        text: "레일 아래쪽의 **세부 정보**."
    note: "박스의 화면은 영상으로 차량에 전달되므로 Live View가 중간에 한 번 더 인코딩됩니다. 손에 든 휴대폰보다 조금 흐리고 조금 늦을 수 있습니다."
check: "차량 화면에 CommaView 홈이, 이어서 Live View가 표시되고 스트림 표시에 **실시간**이 나오며, **화면 가장자리**의 선이 한 바퀴 모두 보입니다."
fixes:
  - q: "박스에 CommaView를 설치할 수 없습니다"
    a: "일부 박스는 브라우저에서의 설치를 막습니다. 컴퓨터에서 앱을 내려받아 USB 메모리로 옮긴 다음 박스의 파일 관리자에서 여세요. 시스템이 폐쇄되어 앱 목록이 고정된 박스에는 아예 설치할 수 없습니다."
  - q: "박스가 comma를 찾지 못합니다"
    a: "둘 다 같은 네트워크에 있는지, 박스가 무선 CarPlay 때문에 Wi‑Fi를 끊지 않았는지 확인하세요. 필요하면 comma의 IP 주소를 입력하세요. comma 자체 핫스팟에서는 192.168.43.1입니다. 자세한 내용은 [차 안에서 연결하기](/ko/guides/connect-in-the-car)에 있습니다."
  - q: "화면이 끊기거나 재생되지 않습니다"
    a: "comma는 도로 카메라를 1928 × 1208 HEVC(H.265)로 보내는데, 가장 저렴한 박스의 디코더로는 부족할 수 있습니다. 디코더가 실패하면 CommaView가 박스의 다른 디코더를 알아서 시도합니다. 아무것도 안 되면 Live View에 **이 comma의 영상을 재생할 수 없습니다**가 표시됩니다. 박스에서 지원 신고를 보내 주세요."
  - q: "“다른 기기에서 Live View가 열려 있음”"
    a: "comma는 한 번에 휴대폰이나 헤드 유닛 한 대로만 스트리밍합니다. 휴대폰의 CommaView에서 홈으로 돌아가면 박스에서 Live View가 알아서 시작됩니다."
  - q: "휴대폰의 CarPlay도 계속 쓸 수 있나요?"
    a: "네. 대부분의 박스는 휴대폰의 CarPlay나 Android Auto를 무선으로 전달하며, 그것과 박스의 Android를 오가며 쓸 수 있습니다. CommaView는 박스의 Android 모드에서 실행됩니다."
  - q: "박스에 SIM 카드가 필요한가요?"
    a: "Live View에는 필요 없습니다. 베타 기간에는 CommaView가 이용권을 갱신하려고 가끔 인터넷이 필요한데, 집 Wi‑Fi, 휴대폰의 핫스팟, 박스의 SIM 중 무엇이든 됩니다."
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## 네 종류의 “CarPlay 어댑터”

매장에서는 서로 아주 다른 네 가지 제품을 같은 이름으로 팝니다. CommaView가 실행되는 것은 하나뿐입니다.

| 종류 | 하는 일 | CommaView 실행 |
| --- | --- | --- |
| **Android AI 박스** | 차량 화면에서 완전한 Android가 실행되고 휴대폰처럼 앱을 설치 | **가능** |
| **폐쇄형 “동영상” 박스** | 잠긴 시스템에 몇 가지 스트리밍 앱이 내장 | 불가 |
| **무선 어댑터** | 유선 CarPlay나 Android Auto를 무선으로 바꿈. 자체 Android 없음 | 불가 |
| **휴대용 CarPlay 화면** | 휴대폰의 CarPlay용 별도 화면. 내부가 Android가 아닌 경우가 많음 | 불가 |

[CommaView에 가장 좋은 Android AI 박스](/ko/blog/android-ai-box-commaview)에서 살 만한 박스를 비교합니다. Tesla에는 CarPlay도 Android Auto도 없으니 대신 [Browser View](/ko/guides/browser-view)를 쓰세요.

comma의 런타임을 업데이트할 때는 comma를 보는 다른 기기와 마찬가지로 먼저 박스의 CommaView를 업데이트하세요.

## 안전

박스 설정은 주차 상태에서 하고, 그다음에는 건드리지 마세요. 운전 중에는 CommaView를 조작하지 마세요. openpilot이 요구하는 대로 눈은 도로에, 손은 핸들에 두세요. comma 자체의 알림과 차량 계기판이 우선입니다. CommaView는 comma가 보는 것을 보여 줄 뿐입니다.
