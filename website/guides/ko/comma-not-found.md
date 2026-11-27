---
title: "CommaView가 comma를 찾을 수 없을 때"
description: "홈에 오프라인이 표시되거나 Live View가 comma에 연결할 수 없나요? 네트워크, comma의 주소, 페어링을 이 순서대로 확인하세요."
topic: troubleshooting
order: 2
kind: fixes
lede: "CommaView는 클라우드 서비스 없이 로컬 네트워크로 comma와 직접 통신합니다. comma를 찾지 못할 때는 거의 항상 휴대폰과 comma가 서로 다른 네트워크에 있거나, 차가 꺼져 comma가 절전 상태이거나, comma의 주소가 바뀐 경우입니다. 이것들을 먼저 확인한 다음 페어링을 확인하세요."
parked: true
updated: 2026-11-27
needs:
  - title: "차가 켜져 있음"
    text: "차가 꺼져 있으면 comma는 절전 상태입니다. 차를 켜고 P단에 두세요."
  - title: "하나의 네트워크"
    text: "휴대폰이 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다. 차 안에서는: [차 안에서 연결하기](/ko/guides/connect-in-the-car)."
steps:
  - id: home
    title: "홈에 표시되는 내용 보기"
    body: |
      휴대폰이 comma에 연결할 수 없으면 홈에 **오프라인**과 **다시 연결**, 그리고 **연결할 수 없나요?** 카드가 표시됩니다: “휴대전화가 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다. 차량이 꺼져 있으면 comma는 절전 상태입니다.”

      둘 다 확인한 다음 **다시 연결**을 누르세요.
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**다시 연결**."
      - target: cant-connect
        text: "**연결할 수 없나요?** 카드."
  - id: live-view
    title: "Live View에서는 기다리거나 다시 시도하기"
    body: |
      Live View는 멈춘 이유를 알려 줍니다. **이 comma에 연결할 수 없음**은 휴대폰이 네트워크에서 comma에 연결할 수 없다는 뜻입니다. comma가 응답하면 알아서 다시 연결하며, **다시 시도**를 누르면 지금 다시 시도합니다.
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**이 comma에 연결할 수 없음**: Live View가 멈춘 이유."
      - target: retry
        text: "**다시 시도**."
  - id: network
    title: "휴대폰의 네트워크 확인하기"
    body: |
      휴대폰의 Wi‑Fi 설정을 열고 comma가 있는 네트워크(같은 집 Wi‑Fi, comma를 연결한 휴대폰의 핫스팟, 또는 comma 자체 핫스팟)에 연결되어 있는지 확인하세요.

      - 인터넷이 없는 Wi‑Fi에서 모바일 데이터로 넘어간 휴대폰은 comma에 연결할 수 없습니다. 다시 연결하세요.
      - 휴대폰의 VPN이 트래픽을 다른 곳으로 보낼 수 있습니다. 끄고 다시 시도하세요.
      - 일부 핫스팟은 연결된 기기끼리 서로 통신하지 못하게 막습니다. comma 자체 핫스팟 같은 다른 네트워크를 써 보세요.
    note: "Android의 Wi‑Fi와 핫스팟 설정 화면은 휴대폰마다 모양이 달라 싣지 않았습니다."
  - id: address
    title: "comma의 주소 확인하기"
    body: |
      comma는 다른 네트워크에 연결하거나 공유기가 새 주소를 줄 때 주소가 바뀝니다. CommaView는 네트워크에서 comma를 발견하면 알아서 다시 찾지만, 찾지 못하면 주소를 직접 저장하세요.

      comma의 **설정 → 네트워크**에서 IP 주소를 확인하세요. CommaView의 홈에서 **장치 설정**을 열고 **이름 또는 주소 변경**을 누른 다음 **IP 주소**를 수정해 comma의 주소를 입력하고 **저장**을 누르세요.
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "comma의 IP 주소."
      - target: save
        text: "**저장**."
  - id: add
    title: "그래도 찾지 못하면 다시 추가하기"
    body: |
      홈에서 **comma 추가**를 누르세요. **이 네트워크에 있음**에 휴대폰의 네트워크에서 CommaView를 실행 중인 comma가 나오면 내 comma를 누르세요. 없으면 **주소와 코드 입력**을 누르거나, comma와 이미 페어링된 휴대폰의 초대 코드를 **QR 코드 스캔**으로 읽으세요.
    screen: add-comma
    pins:
      - target: found-comma
        text: "**이 네트워크에 있음**: 근처에서 찾은 comma."
      - target: enter-address
        text: "**주소와 코드 입력**."
      - target: scan-qr
        text: "**QR 코드 스캔**."
  - id: pair
    title: "주소와 새 코드로 페어링하기"
    body: |
      comma의 IP와 페어링 코드 또는 초대 코드를 입력하고 **comma 페어링**을 누르세요. 코드는 금방 만료됩니다. comma와 이미 페어링된 휴대폰의 **장치 설정**에 있는 **다른 휴대폰이나 태블릿 페어링**에서 새 코드를 볼 수 있습니다.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "comma의 IP."
      - target: pair-code
        text: "**페어링 코드 또는 초대 코드**."
      - target: pair
        text: "**comma 페어링**."
    note: "주소를 입력하면 연결되는데 comma가 알아서 나타나지 않는다면, 네트워크가 CommaView의 검색을 가리고 있는 것입니다. 괜찮습니다. 중요한 것은 주소입니다."
check: "홈에 comma가 **연결됨**으로 표시되고, **Live View 열기**로 화면이 열립니다."
fixes:
  - q: "“이 comma에 연결할 수 없음”"
    a: "휴대폰이 comma와 같은 Wi‑Fi나 comma의 핫스팟에 연결되어 있어야 합니다. comma가 응답하면 Live View가 다시 연결합니다. 네트워크([3단계](#step-network))와 comma의 주소([4단계](#step-address))를 확인하세요."
  - q: "“CommaView가 응답하지 않음”"
    a: "comma는 응답하지만 그 위의 CommaView가 응답하지 않습니다. comma에서 재시작 중일 수 있으며, 돌아오면 Live View가 다시 연결합니다. 계속되면 주차 상태에서 comma를 재시작하세요."
  - q: "“이 comma에서 영상이 없음”"
    a: "응답은 하지만 영상이 돌아오지 않았습니다. 다시 시도하거나, 뒤로 가서 comma를 확인하세요. openpilot이 아직 시작 중일 수 있습니다."
  - q: "“다른 기기에서 Live View가 열려 있음”"
    a: "이 comma는 한 번에 휴대폰이나 헤드 유닛 한 대로만 스트리밍합니다. 다른 기기의 CommaView에서 홈으로 돌아가면 여기서 Live View가 알아서 시작됩니다."
  - q: "“comma가 제때 응답하지 않았습니다.”"
    a: "연결이 약하거나 혼잡합니다. 휴대폰이 comma의 Wi‑Fi나 핫스팟에 연결되어 있는지 확인하고, 가능하면 comma에 더 가까이 가서 다시 시도하세요."
  - q: "“comma가 연결을 거부했습니다. comma에서 CommaView가 재시작 중일 수 있습니다.”"
    a: "돌아올 때까지 잠시 기다린 다음 다시 시도하세요."
  - q: "“차량 데이터가 들어오지 않습니다”"
    a: "영상은 오지만 차량의 속도, 방향 지시등, 알림이 오지 않습니다. comma를 재시작하면 해결됩니다."
  - q: "“페어링 실패: 페어링 코드가 만료되었습니다. 새 코드를 만들어 다시 시도하세요.”"
    a: "comma와 이미 페어링된 휴대폰의 **장치 설정 › 다른 휴대폰이나 태블릿 페어링**에서 새 코드를 받아 다시 페어링하세요."
  - q: "“페어링 실패: 잘못된 페어링 코드입니다. 코드를 확인하거나 QR을 스캔하세요.”"
    a: "입력한 코드를 확인하거나(하이픈은 생략해도 됩니다), 대신 QR 코드를 스캔하세요."
  - q: "“이 comma의 런타임 업데이트” 또는 “CommaView 업데이트”"
    a: "이 앱과 comma의 런타임 버전 차이가 너무 커서 통신할 수 없습니다. 표시된 쪽을 업데이트하세요. 런타임은 장치 설정에서([런타임 업데이트하기](/ko/guides/update-runtime)), 앱은 앱에서 업데이트합니다."
  - q: "“저장된 comma를 읽을 수 없습니다”"
    a: "이 휴대폰에 저장된 comma를 읽을 수 없어 아무것도 표시되지 않습니다. 삭제된 것은 아닙니다. 다시 시도하거나, **새로 시작**으로 각 comma를 다시 페어링하세요. 이전 목록은 최소 90일 동안 보관됩니다."
related: [connect-in-the-car, setup-troubleshooting, another-phone]
---

## CommaView가 comma를 찾는 방법

- **검색**은 휴대폰의 네트워크에서 CommaView를 실행 중인 comma를 찾아 주므로 주소를 입력할 필요가 없습니다. 이를 막는 네트워크도 있습니다.
- **주소**는 CommaView가 연결하는 곳입니다. 검색이 되든 안 되든 주소를 입력하면 연결됩니다.
- **페어링**은 짧은 유효 기간의 코드로 휴대폰에 comma용 자체 키를 줍니다. 검색과 페어링은 별개입니다. 휴대폰이 연결할 수 있는 comma라도 페어링은 해야 합니다.
- **저장된 comma**는 주소만이 아니라 고유한 신원으로 알아봅니다. 그래서 새 주소에서 나타나면 CommaView가 저장된 주소를 업데이트합니다.

## 안전

네트워크 확인과 페어링은 주차 상태에서 하세요. 운전 중에는 CommaView를 조작하지 마세요.
