---
title: "태블릿이나 차량 화면에서 CommaView 사용하기"
description: "CommaView의 Live View를 더 큰 화면에서: Android 헤드 유닛, 차량 화면에 연결하는 Android AI 박스, 거치대의 태블릿. 설치, 네트워크, 페어링, 배치."
topic: screens
order: 3
kind: walkthrough
lede: "comma 3X와 comma four의 화면은 작습니다. CommaView는 comma의 Live View를 Android 헤드 유닛, 차량 화면에 연결하는 Android AI 박스, 거치대에 단 휴대폰이나 태블릿 같은 더 큰 화면에 보여 줍니다. 차량 화면에서는 CommaView가 따로 실행되며 comma와 페어링됩니다."
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 이상"
    text: "Android 8 이상에서 실행되고 앱을 설치할 수 있는 헤드 유닛, AI 박스, 휴대폰 또는 태블릿."
  - title: "초대"
    text: "CommaView 초대를 받은 이메일 주소. my.commaview.com과 앱에 로그인할 때 씁니다."
  - title: "휴대폰의 CommaView"
    text: "가장 쉬운 방법은 먼저 휴대폰으로 comma를 설정한 다음 차량 화면을 페어링하는 것입니다. [CommaView 설정하기](/ko/guides/setup)."
howItWorks:
  - title: "comma"
    text: "인터넷이 아니라 로컬 네트워크로 Live View를 보냅니다."
    edge: "핫스팟 또는 Wi‑Fi"
  - title: "차량 화면"
    text: "자체 CommaView를 실행하며 comma와 페어링됩니다."
steps:
  - id: install
    title: "차량 화면에 CommaView 설치하기"
    body: |
      헤드 유닛, AI 박스, 휴대폰 또는 태블릿에서 웹 브라우저를 열고 초대받은 이메일 주소로 [my.commaview.com](https://my.commaview.com)에 로그인하세요. **Get the app** 아래에서 **Download CommaView**를 누르고, 다운로드한 파일을 연 다음 이번 설치에만 브라우저의 설치를 허용하고 끝나면 다시 끄세요. [설정 가이드](/ko/guides/setup)와 같은 방법입니다.

      CommaView를 열고 로그인하세요. 베타 기간에는 이용권을 갱신하려고 가끔 인터넷이 필요하므로, 적어도 가끔은 인터넷이 되는 Wi‑Fi에 연결해 주세요.
    note: "일부 헤드 유닛과 박스는 브라우저에서의 설치를 막습니다. 컴퓨터에서 앱을 내려받아 USB 메모리로 옮긴 다음 기기의 파일 관리자에서 여세요."
  - id: network
    title: "comma와 같은 네트워크에 연결하기"
    body: |
      Live View는 로컬 네트워크를 통해 comma에서 차량 화면으로 바로 갑니다. 같은 네트워크에 있기만 하면 되며, 차 안에서는 보통 핫스팟입니다. 차를 켤 때 함께 켜지는 방법을 고르세요. 보통 가장 간편합니다.
    tabs:
      - label: "차량 화면의 핫스팟"
        body: "AI 박스나 헤드 유닛이 핫스팟을 공유할 수 있다면(SIM 카드가 있는 기기는 대부분 가능합니다) 켜고, comma의 **설정 › 네트워크**에서 comma를 연결하세요."
      - label: "휴대폰의 핫스팟"
        body: "comma와 차량 화면을 휴대폰의 핫스팟에 연결하세요. 둘 다 그 핫스팟으로 인터넷도 씁니다."
      - label: "comma의 핫스팟"
        body: "comma의 핫스팟을 켜고(openpilot에서는 테더링이라고 합니다. comma four에서는 **설정 › 네트워크 › 테더링 사용**, comma 3X에서는 **설정 › 네트워크 › 고급 설정 › 테더링 사용**) 차량 화면에서 연결하세요."
      - label: "집 Wi‑Fi"
        body: "집에서는 둘 다 집 Wi‑Fi에 연결합니다. 설정할 때는 편하지만 차를 몰고 나가면 끊깁니다."
    note: "차량 화면의 VPN은 끄세요. 일부 핫스팟은 연결된 기기끼리 서로 통신하지 못하게 막습니다. 한 핫스팟에서 차량 화면이 comma를 찾지 못하면 다른 핫스팟을 써 보세요. 자세한 내용은 [차 안에서 연결하기](/ko/guides/connect-in-the-car)에 있습니다."
  - id: pair
    title: "comma와 페어링하기"
    body: |
      휴대폰에서 이미 comma에 CommaView를 실행 중이라면, 다시 설정하지 말고 차량 화면을 페어링하세요. 차량 화면은 자체 키를 받습니다.
    tabs:
      - label: "휴대폰에서"
        body: |
          comma의 **장치 설정**을 열고 **다른 휴대폰 페어링**을 여세요. **다른 휴대폰 추가** 아래에서 **초대 코드 표시**를 누르세요. 입력할 코드나 QR 코드가 표시되며, 10분 동안 유효하고 한 번만 쓸 수 있습니다.
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**초대 코드 표시**."
          - target: this-phone
            text: "키가 있는 휴대폰. 이 휴대폰에는 **이 휴대전화**가 표시됩니다. 차량 화면도 여기에 추가됩니다."
      - label: "차량 화면에서"
        body: |
          **comma 연결**에서 **CommaView를 실행 중인 comma 페어링**을 누르세요(이미 comma를 추가했다면 대신 **comma 추가**를 여세요). comma를 고르고 **페어링 코드 입력** 또는 **QR 코드 스캔**을 누르세요. 목록에 없으면 **주소와 코드 입력**을 누르세요. **페어링 코드 또는 초대 코드**에 초대 코드를 입력하고 **comma 페어링**을 누르세요.
        screen: add-comma
        pins:
          - target: found-comma
            text: "이 네트워크에서 찾은 comma."
          - target: scan-qr
            text: "**QR 코드 스캔**."
          - target: enter-address
            text: "목록에 없으면 **주소와 코드 입력**."
    note: "그러면 휴대폰에 **새 휴대폰에 키가 생겼습니다**가 표시됩니다. **내 휴대폰입니다**를 누르세요. 모든 단계: [다른 휴대폰이나 태블릿 추가하기](/ko/guides/another-phone)."
  - id: fit
    title: "화면에 맞추기"
    body: |
      넓은 화면에서는 CommaView가 대시보드처럼 배치되며, 탐색 메뉴는 옆쪽 레일에 들어갑니다. 기기의 글자 크기는 한눈에 읽을 수 있는 크기로 두세요. CommaView는 그 크기에서 쓸 수 있는 공간에 맞춰 배치합니다.

      Live View의 조작 버튼은 운전석 쪽에 있습니다. **자동**에서는 comma가 알려 주는 쪽을 따릅니다. 직접 정하려면 **설정 › 디스플레이 › 운전석 위치**에서 **자동**, **왼쪽 운전석**, **오른쪽 운전석** 중에서 고르세요. 모든 화면에서 조작 버튼이 좌우로 바뀝니다.
    tabs:
      - label: "태블릿"
        body: "홈에 차량, 한 주의 기록, 지도, 주행이 나란히 표시되고 옆쪽에 레일이 있습니다."
        screen: tablet-home
        pins:
          - target: home-tab
            text: "레일: **홈**, **녹화**, **설정**."
          - target: open-live-view
            text: "**Live View 열기**."
      - label: "헤드 유닛"
        body: "같은 대시보드를 대시보드 매립형 화면에 맞는 크기로 보여 줍니다."
        screen: car-home
        pins:
          - target: home-tab
            text: "레일: **홈**, **녹화**, **설정**."
          - target: open-live-view
            text: "**Live View 열기**."
      - label: "AI 박스를 통해"
        body: |
          어떤 차는 AI 박스가 보내는 화면의 가장자리를 잘라 내는데, Android는 이를 알 수 없습니다. **설정 › 디스플레이 › 화면 가장자리**를 열고 선이 한 바퀴 모두 보일 때까지 각 가장자리를 안쪽으로 옮기세요. 그다음 홈, Live View, 설정이 안쪽에 들어오는지 확인하세요. 거기 있는 **테마**는 차량 화면을 따르게 할 수 있습니다: **이 기기와 동일**.
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−**와 **+**로 각 가장자리를 안쪽으로 옮기고, **완료**로 저장합니다."
  - id: live-view
    title: "Live View를 열고 재생되는지 확인하기"
    body: |
      차를 켠 상태에서 **Live View 열기**를 누르세요. 조작 버튼은 도로 옆, 운전석 쪽 레일에 있으며 세로가 짧은 화면에서는 작아집니다.
    tabs:
      - label: "태블릿"
        body: "**세부 정보**는 영상 옆 창에 열립니다."
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "영상 옆의 세부 정보."
          - target: record-button
            text: "**녹화**."
          - target: go-live-button
            text: "**라이브 시작**."
      - label: "헤드 유닛"
        body: "레일에는 녹화, 주행 화면 전환, 운전자 카메라, 세부 정보, 나가기가 있습니다."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**녹화**."
          - target: onroad-screen-button
            text: "주행 화면 전환."
          - target: driver-cam-button
            text: "**운전자 카메라**."
          - target: details
            text: "운전자 카메라 아래의 **세부 정보**."
          - target: exit
            text: "**나가기**."
  - id: auto
    title: "알아서 열리게 하기"
    body: |
      **설정 › 디스플레이**의 **Live View 여는 중**에서:

      - **연결되면 Live View 열기**: 차가 켜진 상태에서 comma가 연결되면 Live View를 알아서 엽니다.
      - **이 기기가 시작되면 CommaView 열기**: 차와 함께 다시 시작하는 헤드 유닛용입니다. 다시 시작하지 않고 절전 상태가 되는 기기에는 시작할 앱 목록이 따로 있을 수 있습니다.
      - **블루투스가 연결되면 CommaView 열기**: 고른 기기(차량, 헤드 유닛이라면 휴대폰)가 연결되면 엽니다.

      **다른 앱 위에 표시**를 허용하면 CommaView가 알아서 열립니다. 허용하지 않으면 알림으로 열지 묻습니다.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**연결되면 Live View 열기**."
check: "차를 켜면 차량 화면에서 Live View가 열리고, 스트림 표시에 **실시간**이 나오며, 모든 조작 버튼이 화면 가장자리 안쪽에 있습니다."
fixes:
  - q: "CarPlay나 Android Auto로 CommaView를 쓸 수 있나요?"
    a: "휴대폰에서는 안 됩니다. CommaView는 CarPlay나 Android Auto 앱이 아니며, 이 플랫폼들은 주행 중에 휴대폰 앱이 영상을 보여 주는 것을 허용하지 않습니다. Android AI 박스는 그 자체가 Android 기기이므로 이 문제를 피할 수 있습니다. CommaView가 박스에서 실행되고, 차는 박스의 화면을 보여 줍니다. [Android AI 박스에서 CommaView 실행하기](/ko/guides/ai-box)를 보세요."
  - q: "차량에 내장된 Android Automotive(Google 내장)에서 작동하나요?"
    a: "아직은 아닙니다. Google 내장 차량은 자체 Play 스토어에서만 앱을 설치할 수 있는데, 거기에는 CommaView가 없습니다. 다른 방법으로 시도해 보셨다면 결과를 알려 주세요."
  - q: "같은 comma로 차량 화면과 휴대폰을 함께 쓸 수 있나요?"
    a: "네. 각각을 comma와 페어링하세요. Live View는 한 번에 한 기기에서만 열리므로 먼저 다른 기기에서 Live View를 닫으세요. Live View에 **다른 기기에서 Live View가 열려 있음**이 표시되고, 다른 기기에서 홈으로 돌아가면 알아서 시작됩니다."
  - q: "차가 화면 가장자리를 잘라 냅니다"
    a: "어떤 차는 AI 박스가 보내는 화면을 잘라 내는데, Android는 이를 알 수 없습니다. **설정 › 디스플레이 › 화면 가장자리**에서 정한 각 가장자리 안쪽으로 앱을 표시합니다."
  - q: "차량 화면이 comma를 찾지 못합니다"
    a: "CommaView는 같은 네트워크에서 주소가 바뀌어도 comma를 알아서 찾습니다. 찾지 못하면 comma의 IP 주소를 입력하세요. comma 자체 핫스팟에서는 192.168.43.1(모든 comma가 같습니다), 다른 네트워크에서는 comma의 **설정 › 네트워크**에 표시되는 IP 주소입니다. comma four에서는 Wi‑Fi 버튼의 네트워크 이름 아래, comma 3X에서는 **고급 설정** 아래에 있습니다."
  - q: "런타임 업데이트 후 차량 화면에 영상이 오지 않습니다"
    a: "comma의 런타임을 업데이트할 때는 먼저 그 comma를 보는 모든 기기(차량 화면 포함)에서 CommaView를 업데이트하세요. 이전 CommaView를 쓰는 차량 화면은 comma의 첫 휴대폰이 키를 받은 뒤 90일 동안 계속 작동합니다. 그 후에는 CommaView 0.0.166 이상과 초대 코드가 필요합니다."
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## 주행 중에 쓸 수 있는 것

CommaView는 Android 앱이므로 눈앞에 Android 기기가 있어야 합니다. 다음 중 어느 것으로든 주행 중에 실행할 수 있습니다.

- **Android 헤드 유닛.** Android 8 이상에서 실행되는 애프터마켓 헤드 유닛. 휴대폰처럼 CommaView를 설치할 수 있고, 주행 중에도 차량 화면에서 실행됩니다.
- **Android “AI 박스”.** 차량의 유선 CarPlay나 Android Auto 포트에 꽂아 그곳에 자체 Android 화면을 띄우는 작은 Android 컴퓨터. CommaView는 휴대폰이 아니라 박스에서 실행됩니다. [Android AI 박스에서 CommaView 실행하기](/ko/guides/ai-box)를 보세요.
- **거치대의 휴대폰이나 태블릿.** 시야를 가리지 않는 대시보드나 송풍구 거치대에 단 Android 휴대폰이나 태블릿. 가장 간단하며 대부분의 사람이 쓰는 방법입니다.

Tesla처럼 웹 브라우저가 있는 차량은 대신 브라우저에서 Live View를 볼 수 있습니다: [차량 브라우저에 Live View 표시하기](/ko/guides/browser-view).

## 안 되는 것과 그 이유

- **휴대폰에서 CarPlay와 Android Auto.** CommaView는 CarPlay나 Android Auto 앱이 아닙니다. 이 플랫폼들은 주행 중에 휴대폰 앱이 영상을 보여 주는 것을 허용하지 않습니다.
- **CarPlay와 Android Auto의 주차 중 영상.** Apple과 Google이 일부 차량에 영상 기능을 추가하고 있지만 주차 중에만 되므로, 도로에서 Live View를 보여 줄 수 없습니다.
- **휴대폰 화면을 차량에 미러링.** CarPlay나 Android Auto로 휴대폰 화면을 미러링하는 어댑터는 지원하지 않습니다. 대신 CommaView를 직접 실행하는 Android AI 박스나 헤드 유닛을 쓰세요.
- **Google 내장(Android Automotive).** 이 차량들은 자체 Play 스토어에서만 앱을 설치할 수 있는데, 거기에는 CommaView가 없습니다.

## 테스트한 하드웨어

CommaView 팀이 직접 주행하며 써 본 차량 화면입니다. CommaView는 Android 8 이상의 모든 기기에서 실행되어야 하지만, 확인한 것은 다음과 같습니다.

| 기기 | 종류 | 확인한 내용 |
| --- | --- | --- |
| **Doro head unit** (Qualcomm QCM6125, Android 13, 1280 × 720) | 헤드 유닛 | 시내 주행에서 Live View(2026년 10월). |
| **Dasaita 10.2″ head unit** (1280 × 720, Toyota RAV4에 장착) | 헤드 유닛 | 주행 중 Live View, 주차 중 녹화 업로드. |

**테스트를 도와주세요.** 차량 화면은 저마다 다릅니다. 헤드 유닛이나 박스에서 CommaView를 쓰고 있다면 [결과를 알려 주세요](#차량-화면에-대해-알려-주세요). 확인한 뒤 여기에 추가하겠습니다.

## 차량 화면에 대해 알려 주세요

신고에 모델과 화면 크기가 담기도록 차량 화면에서 직접 보내 주세요.

1. 헤드 유닛이나 박스의 CommaView에서 **설정 › 지원 및 진단**을 열고 **문제 신고 또는 아이디어 보내기**를 누르세요.
2. **아이디어**를 고르고 **이 기기의 진단 정보**를 켜세요(아이디어에서는 꺼져 있습니다). 제조사, 모델, 화면 크기를 알 수 있습니다.
3. 메모에 차량, 헤드 유닛이나 박스(브랜드와 모델), 연결 방식(누구의 핫스팟인지, 또는 Wi‑Fi), 잘 된 것과 안 된 것을 적고 **보내기**를 누르세요.

보낸 내용과 답변은 [my.commaview.com](https://my.commaview.com/feedback)의 Your feedback에서 볼 수 있습니다. 아직 베타에 참여하지 않았거나 앱이 시작되지 않나요? [CommaView Discord](https://discord.gg/UuMhz9K8ft)에서 알려 주세요.

## 안전

- 설치, 페어링, 배치 설정은 주차 상태에서 하세요. 운전하기 전에 Live View가 재생되는지 확인하세요.
- 운전 중에는 CommaView를 조작하지 마세요. openpilot이 요구하는 대로 눈은 도로에, 손은 핸들에 두세요.
- comma 자체의 알림과 차량 계기판이 우선입니다. CommaView는 comma가 보는 것을 보여 줄 뿐입니다.
- 휴대폰이나 태블릿은 시야나 에어백을 가리지 않는 곳에 달고, 차 안 화면에 관한 지역 규정을 따르세요.
