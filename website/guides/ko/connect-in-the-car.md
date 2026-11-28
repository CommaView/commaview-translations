---
title: "집 Wi‑Fi 없이 차 안에서 연결하기"
description: "차 안에서 휴대폰과 comma를 한 네트워크에 연결하는 방법(휴대폰 핫스팟, comma 핫스팟, 차량 화면의 핫스팟)과 CommaView가 comma에 연결할 수 없을 때 할 일."
topic: start
order: 3
kind: walkthrough
lede: "Live View는 인터넷이 아니라 로컬 네트워크를 통해 comma에서 휴대폰으로 바로 옵니다. CommaView는 누구의 네트워크인지 상관하지 않습니다. 휴대폰과 comma가 같은 네트워크에 있기만 하면 됩니다. 차 안에서는 보통 핫스팟입니다."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView 설정 완료"
    text: "comma가 이 휴대폰과 페어링되어 있어야 합니다. 아직이라면 [CommaView를 설정하세요](/ko/guides/setup)."
  - title: "VPN 끄기"
    text: "CommaView를 쓰는 동안에는 휴대폰이나 차량 화면의 VPN을 끄세요."
howItWorks:
  - title: "comma"
    text: "연결된 네트워크에서 Live View와 녹화를 제공합니다."
    edge: "하나의 핫스팟"
  - title: "휴대폰"
    text: "주소가 바뀌어도 그 네트워크에서 comma를 알아서 찾습니다."
steps:
  - id: network
    title: "휴대폰과 comma를 한 네트워크에 연결하기"
    body: |
      차에 맞는 방법을 고르세요. 차를 켤 때 함께 켜지는 방법이 보통 가장 간편합니다. comma를 네트워크에 연결하려면 comma 화면의 **설정 › 네트워크**를 사용합니다.
    tabs:
      - label: "휴대폰의 핫스팟"
        body: "휴대폰의 핫스팟을 켜고 comma를 연결하세요. 같은 휴대폰의 CommaView가 그 핫스팟으로 comma에 연결하고, comma도 그 핫스팟으로 인터넷을 씁니다."
      - label: "comma의 핫스팟"
        body: "comma의 핫스팟을 켜고(openpilot에서는 테더링이라고 합니다. comma four에서는 **설정 › 네트워크 › 테더링 사용**, comma 3X에서는 **설정 › 네트워크 › 고급 설정 › 테더링 사용**) 휴대폰의 Wi‑Fi 설정에서 연결하세요. comma의 핫스팟으로는 인터넷을 쓸 수 없습니다."
      - label: "차량 화면의 핫스팟"
        body: "AI 박스나 헤드 유닛이 핫스팟을 공유할 수 있다면(SIM 카드가 있는 기기는 대부분 가능합니다) 켜고 comma와, 휴대폰을 쓴다면 휴대폰도 연결하세요. 자세한 내용은 [차량 화면](/ko/guides/car-screens)에 있습니다."
    note: "일부 핫스팟은 연결된 기기끼리 서로 통신하지 못하게 막습니다. 한 핫스팟에서 CommaView가 comma를 찾지 못하면 다른 핫스팟을 써 보세요."
  - id: home
    title: "CommaView 열기"
    body: |
      comma가 새 네트워크에서 응답하면 홈에 **연결됨**이 표시됩니다. 주소가 바뀌어도 CommaView가 알아서 찾습니다. 차가 꺼져 있으면 comma는 절전 상태이므로 먼저 차를 켜세요.

      홈에서 comma가 오프라인이고 **연결할 수 없나요?**가 표시되면, 휴대폰이 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있는지 확인한 다음 **다시 연결**을 누르세요.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**다시 연결**: comma에 다시 연결을 시도합니다."
      - target: cant-connect
        text: "**연결할 수 없나요?**: 휴대폰에 필요한 것을 알려 줍니다. comma와 같은 Wi‑Fi나 comma의 핫스팟입니다."
  - id: address
    title: "그래도 찾지 못하면 주소 입력하기"
    body: |
      comma의 **장치 설정**을 열고 **이름 및 주소**에서 IP 주소를 수정하세요. comma 자체 핫스팟에서는 **192.168.43.1**입니다(모든 comma가 같습니다). 다른 네트워크에서는 comma의 **설정 › 네트워크**에 표시되는 주소입니다. comma four에서는 Wi‑Fi 버튼의 네트워크 이름 아래, comma 3X에서는 **고급 설정** 아래에 있습니다. **저장**을 누르세요.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "이 네트워크에서 comma의 IP 주소."
      - target: save
        text: "**저장**."
  - id: live-view
    title: "Live View 열기"
    body: |
      홈에서 **Live View 열기**를 누르세요. 휴대폰이 comma와 연결이 끊기면 Live View가 이유를 알려 주고, comma가 응답하면 알아서 다시 연결합니다. **이 comma에 연결할 수 없음**은 휴대폰이 comma의 네트워크에 있지 않다는 뜻입니다. 해결한 다음 **다시 시도**를 누르세요.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**이 comma에 연결할 수 없음**: Live View가 멈춘 이유."
      - target: retry
        text: "휴대폰이 comma의 네트워크로 돌아오면 **다시 시도**."
check: "홈에 comma가 **연결됨**으로 표시되고, Live View에서 도로가 재생되며 경로가 위에 그려집니다."
fixes:
  - q: "“이 comma에 연결할 수 없음”"
    a: "휴대폰이 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다. 휴대폰이 어느 네트워크에 연결됐는지 확인하고(알고 있는 Wi‑Fi로 돌아갔을 수 있습니다), VPN을 끈 뒤 **다시 시도**를 누르세요."
  - q: "“다른 기기에서 Live View가 열려 있음”"
    a: "이 comma는 한 번에 휴대폰이나 헤드 유닛 한 대로만 스트리밍합니다. 다른 기기의 CommaView에서 홈으로 돌아가면 여기서 Live View가 알아서 시작됩니다."
  - q: "“CommaView가 응답하지 않음”"
    a: "comma에서 재시작 중일 수 있습니다. 돌아오면 Live View가 다시 연결합니다."
  - q: "CommaView가 갱신하려면 인터넷이 필요하다고 합니다"
    a: "베타 기간에는 CommaView가 가끔 이용권을 갱신하는데, comma의 핫스팟은 인터넷으로 치지 않습니다. 잠시 휴대폰을 모바일 데이터나 인터넷이 되는 Wi‑Fi에 연결하세요."
  - q: "한 핫스팟에서는 됐는데 다른 핫스팟에서는 안 됩니다"
    a: "일부 핫스팟은 연결된 기기끼리 서로 통신하지 못하게 막아 휴대폰이 comma를 볼 수 없습니다. 1단계의 다른 네트워크를 써 보세요."
related: [comma-not-found, car-screens, browser-view, setup-troubleshooting]
---

## 검색, 페어링, 주소

세 가지가 따로따로 작동해야 하며, 어느 것이 실패했는지 알면 무엇을 고칠지 알 수 있습니다.

- **comma 찾기.** CommaView는 휴대폰이 연결된 네트워크에서 comma를 찾고, 같은 comma를 새 위치에서 찾으면 저장된 주소를 업데이트합니다. 이 검색을 막는 네트워크도 있는데, 주소를 입력하면(3단계) 해결됩니다.
- **연결하기.** 휴대폰이 그 네트워크에서 comma에 연결할 수 있어야 합니다. 노트북에서 comma에 SSH로 접속된다고 해서 휴대폰도 된다는 뜻은 아닙니다.
- **페어링.** 연결되면 휴대폰은 페어링할 때 받은 키를 사용합니다. 네트워크를 바꿔도 페어링은 풀리지 않으므로 다시 페어링할 필요가 없습니다.
