---
title: "comma와 포크가 지원되는지 확인하기"
description: "CommaView는 openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot, OPGM을 지원하며, 다른 포크는 제한 지원합니다."
topic: start
order: 2
kind: reference
lede: "CommaView는 comma의 도로 카메라를 comma가 실행하는 소프트웨어의 주행 오버레이와 함께 보여 줍니다. comma 3X와 comma four에서 openpilot과 9개 포크를 지원하며, 다른 openpilot 포크도 제한 지원합니다. 설정은 무언가를 바꾸기 전에 comma가 어떤 포크를 실행하는지 확인합니다."
updated: 2026-11-27
needs:
  - title: "comma 3X 또는 comma four"
    text: "comma 3는 지원하지 않으며, xnor-c3 같은 포크의 comma 3용 빌드도 마찬가지입니다. [comma 3를 지원하지 않는 이유](/ko/#faq-comma-3)."
  - title: "평소대로 실행되는 포크"
    text: "평소처럼 설치되어 실행 중이어야 합니다. CommaView는 그 옆에 런타임을 추가할 뿐, 주행 방식은 절대 바꾸지 않습니다."
steps:
  - id: unlisted
    title: "CommaView 목록에 없는 포크라면 설정이 먼저 묻습니다"
    body: |
      안내 설정은 comma의 소프트웨어가 어느 저장소에서 설치되었는지 확인하고, 그 포크용 CommaView 훅을 설치합니다. 목록에 없는 포크라면 아무것도 바꾸지 않고 먼저 포크를 확인합니다.
    tabs:
      - label: "제한 지원"
        body: "CommaView가 화면을 추가할 수 있으면 설정에 **CommaView가 확인하지 않은 포크입니다**가 표시됩니다. 저장소 이름으로 포크를 알려 주고, 그려지는 것(카메라, 경로, 차선, 앞차, 알림, 속도)과 그려지지 않는 것(포크 고유의 버튼, 색상, 위젯)을 설명합니다. **그래도 설치**를 누르면 그 포크에만 설치합니다. **뒤로**를 누르면 comma 선택으로 돌아가며, 아무것도 설치되지 않았습니다."
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**그래도 설치**: 이 포크에 CommaView 화면을 제한 지원으로 추가합니다."
      - label: "영상 전용(얼리 액세스)"
        body: "화면에 CommaView를 추가할 수 없는 FrogPilot과 KisaPilot에서는 영상 전용 플래그가 있는 테스터에게 **이 포크에서 영상 전용**이 표시됩니다. CommaView는 카메라를 스트리밍하고 주행 데이터로 자체 화면을 그리며, 포크는 전혀 바꾸지 않습니다. 아직 comma에서 시험해 보지 않았습니다. 플래그가 없으면 설정은 포크를 지원하지 않는다고 알리고 아무것도 바꾸지 않습니다."
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**영상 전용으로 설치**."
    note: "확인에서 포크가 거부되면 설정에 “CommaView가 …에 화면을 안전하게 추가할 수 없습니다.”와 “comma에서 바뀐 것은 없습니다.”가 표시됩니다."
  - id: details
    title: "Live View가 그리는 포크 확인하기"
    body: |
      Live View에서 **세부 정보**를 여세요. **소프트웨어** 줄에 comma의 포크가 표시됩니다. CommaView 목록에 없는 포크는 “crwusiz/openpilot · best effort”처럼 저장소 이름으로 표시됩니다.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "화면 아래의 **세부 정보**."
      - text: "**소프트웨어**: comma가 실행하는 포크."
related: [setup, overlays, uninstall]
---

## 지원 포크

| 포크 | 출처 | 지원 시작 |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | 첫 베타 |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | 첫 베타 |
| **StarPilot** | github.com/StarPilotHQ/StarPilot (이전 github.com/firestar5683/StarPilot) | 0.0.162 |
| **xnor** (xnor 및 rx 빌드) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot, i.carrotpilot.app에서 설치 | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

목록에 없는 포크라면 설정이 CommaView 화면을 추가할 수 있는지 확인하고 먼저 묻습니다. 추가할 수 없으면 설정이 멈추고 comma는 그대로 둡니다.

## 포크별 표시 내용

### openpilot

comma.ai의 자체 소프트웨어입니다. Live View는 comma four 화면, comma 3X 화면 또는 CommaView 자체 오버레이를 그리며, 속도, 최대, 제한 속도, 앞차, 차선 변경을 보여 줍니다.

### sunnypilot

CommaView는 sunnypilot이 더한 요소와 함께 sunnypilot 화면을 그립니다. MADS의 조향만·속도만 상태, 제한 속도 보조, 무지개 경로와 사각지대 표시, 그리고 comma 3X 화면에서는 제한 속도 표지, 스마트 크루즈, 개발자 UI입니다. sunnypilot 설정을 읽으므로 화면이 comma와 일치합니다.

### StarPilot

StarPilot은 주행 모드를 색으로 보여 주며, CommaView는 StarPilot이 고른 색을 사용합니다. comma four와 comma 3X 화면의 테두리, 경로, 위젯, 알림, 그리고 운전자 카메라를 포함한 카메라 선택입니다.

StarPilot의 **Disable Logging** 설정은 끄세요. Live View가 스트리밍하는 비디오 인코더가 멈춥니다.

### xnor-tech의 openpilot: xnor와 rx

xnor-tech의 openpilot에는 두 가지 빌드가 있습니다. **xnor** 브랜치는 openpilot 화면을, **rx** 브랜치는 sunnypilot 화면을 실행하며, 둘 다 xnor-tech의 차량 지원을 포함합니다. CommaView는 comma에서 실행 중인 쪽을 그리고, 알림은 comma가 쓰는 그대로 보여 줍니다.

rx를 실행하는 Rivian에서는 차가 각도로 조향하는 동안 핸들이 녹색, 토크로 조향하는 동안 파란색이 됩니다. comma four에서는 핸들, comma 3X 화면에서는 실험 모드 버튼의 핸들입니다.

### AdventurePilot

AdventurePilot은 자체 차량 지원을 가진 sunnypilot 포크입니다. CommaView는 AdventurePilot이 더한 요소와 함께 sunnypilot 화면을 그립니다.

- 차선 중앙 유지 표시: comma 3X 화면에서는 밀어내는 정도와 오프셋을 보여 주는 알약 모양, comma four 화면에서는 작은 막대.
- comma 3X 화면의 CURVE 칩. 커브 속도 제어가 작동하는 동안 깜박입니다.
- 조향 모드에 따른 핸들 색, 그리고 Rivian이 각도 채널로 조향하는 동안 횡가속도를 보여 주는 토크 막대.

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1은 Tesla의 HW1(Autopilot 1) 차량을 지원하는 sunnypilot 포크입니다. 화면이 sunnypilot의 것이므로, CommaView는 sunnypilot이 더한 모든 요소와 함께 sunnypilot 화면을 그리고 앱에서 포크 이름을 표시합니다.

CommaView 훅이 설치된 동안에는 이 포크의 `op fork update`로 포크를 바꿀 수 없습니다. 먼저 [CommaView 런타임을 제거](/ko/guides/uninstall)하거나, 평소처럼 작동하는 comma 화면의 포크 전환 기능을 사용하세요.

### carrotpilot

carrotpilot은 현대, 기아, 제네시스 차량용 openpilot 포크로, `i.carrotpilot.app`에서 설치합니다. CommaView는 이 포크에 openpilot 화면을 그리며 속도, 경로, 차선, 앞차를 보여 줍니다. carrotpilot이 자체 화면에 더하는 내비게이션, 과속 단속 카메라, HUD 등은 아직 그리지 않습니다.

carrotpilot의 자동 업데이트와 웹 페이지의 Git 도구는 comma가 재시작할 때까지 CommaView 훅을 제거합니다. 앱이 재시작을 요청하며, 재시작하면 Live View가 돌아옵니다.

### BluePilot, dragonpilot, OPGM

CommaView 0.0.166과 그 런타임부터 목록에 올랐습니다. CommaView는 각각의 이름을 표시하고 기반 소프트웨어의 모습으로 그립니다. BluePilot은 sunnypilot으로, dragonpilot과 OPGM은 openpilot으로 그리며, dragonpilot의 ALKA는 조향으로 표시합니다. 이 중 하나를 제한 지원으로 실행하던 comma는 런타임 업데이트 후 부팅할 때 목록의 포크로 전환됩니다. 아직 CommaView로 주행해 본 포크는 없습니다. CommaView 공식 [오버레이 팩](/ko/guides/overlays)을 쓰면 BluePilot과 dragonpilot 고유의 화면을 더 많이 그릴 수 있습니다.

## CommaView 목록에 없는 포크

CommaView 0.0.165부터는 comma에 그 런타임이 있으면, 설정이 목록에 없는 openpilot 포크에도 CommaView 화면을 제한 지원으로 추가할 수 있습니다. Live View는 포크를 openpilot의 모습으로 그리며, sunnypilot 화면을 기반으로 한 포크라면 sunnypilot의 모습으로 그립니다. 되돌리려면 장치 설정의 **런타임 제거**로 포크의 파일을 원래대로 되돌리세요.

- **제한 지원.** CommaView 릴리스는 사용 중인 포크에서 확인되지 않습니다. 포크가 CommaView가 따라갈 수 없는 방식으로 자동 업데이트되면, CommaView 릴리스가 그 변화를 처리할 때까지 CommaView 화면은 꺼지고 포크는 평소처럼 주행하며 자체 화면을 보여 줍니다.
- **모든 포크는 아닙니다.** openpilot의 이전 네이티브 화면을 기반으로 한 포크는 지원하지 않습니다(아래 참고).
- **동의는 그 포크에만 적용됩니다.** comma가 목록에 없는 다른 포크로 바뀌면, CommaView는 그곳에 화면을 추가하기 전에 설정에서 다시 묻습니다.

### 설치 확인을 통과한 포크(제한 지원)

다음 포크는 모두 **CommaView 설치 확인을 통과했지만 제한 지원이며, 차량에서 테스트하지 않았습니다.** 2026년 11월에 표시된 브랜치를 CommaView 0.0.165가 설치하는 런타임으로 확인했습니다. 설치 프로그램이 포크를 제시하고, 동의하면 CommaView 화면을 추가해 확인하는 과정을 comma에서와 같이 진행했습니다. 차 안의 comma에서는 시험하지 않았고, 포크가 두 장치에서 모든 차량을 지원하지 않을 수 있으며, 포크의 다음 업데이트로 결과가 바뀔 수 있습니다.

| 포크 | 확인한 브랜치 | 장치 | 표시 방식 |
| --- | --- | --- | --- |
| **crwusiz** (github.com/crwusiz/openpilot) | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **jixiexiaoge’s Carrot** (github.com/jixiexiaoge/openpilot) | Carrot | comma four, comma 3X | openpilot |
| **MoreTore** (github.com/MoreTore/openpilot) | release-mici | comma four | openpilot |
| **zoompilot** (github.com/zoompilot/zoompilot) | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato** (github.com/AlexandreSato/openpilot) | master | comma four, comma 3X | openpilot |
| **lukasloetkolben** (github.com/lukasloetkolben/openpilot) | master | comma four, comma 3X | openpilot |
| **mvl-boston** (github.com/mvl-boston/openpilot) | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub** (github.com/mouxangithub/openpilot) | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro** (github.com/programanichiro/openpilot) | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2** (github.com/infiniteCable2/openpilot) | master | comma four, comma 3X | sunnypilot |
| **herizon1054** (github.com/herizon1054/openpilot) | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot** (github.com/NotAutopilot/openpilot) | nap-release, naponsp-alpha | comma four, comma 3X | openpilot(nap-release), sunnypilot(naponsp-alpha) |

내 포크가 없나요? 그래도 작동할 수 있습니다. 설정은 무언가를 바꾸기 전에 포크를 확인합니다.

### 지원하지 않는 포크

다음 포크는 화면에 CommaView를 추가할 수 없으므로, 설정이 그렇게 알리고 comma에서 아무것도 바꾸지 않습니다.

- **FrogPilot** (github.com/FrogAi/FrogPilot). openpilot의 이전 네이티브(Qt) 화면을 실행해 CommaView 화면이 들어갈 자리가 없습니다. 영상 전용은 얼리 액세스 중입니다.
- **KisaPilot** (github.com/kisapilot/openpilot). Python 화면이 꺼져 있고 openpilot의 이전 네이티브(Qt) 화면을 실행합니다. 영상 전용은 얼리 액세스 중입니다.
- **IQ.Pilot** (github.com/IQLvbs/iqpilot). 2026년 10월부터 자체 IQ.OS에서 실행됩니다. CommaView가 별도의 포크로 지원할 수 있을 때까지 지원을 보류합니다.
- **hikee9123** (github.com/hikee9123/openpilot). openpilot의 이전 네이티브(Qt) 화면을 실행합니다.

**얼리 액세스: FrogPilot과 KisaPilot용 영상 전용.** 영상 전용 플래그가 있으면, 설정이 이 포크들의 카메라를 포크 고유 화면 대신 CommaView 자체 오버레이와 함께 Live View에서 재생하도록 제안하며, 포크는 전혀 바꾸지 않습니다. 아직 comma에서 시험해 보지 않았습니다. 플래그가 없으면 설정은 여전히 지원하지 않는다고 알리고 아무것도 바꾸지 않습니다.

## 지원하는 comma 장치

comma 3X와 comma four입니다. comma 3는 지원하지 않으며, xnor-c3 같은 포크의 comma 3용 빌드도 마찬가지입니다: [comma 3를 지원하지 않는 이유](/ko/#faq-comma-3). 앱은 Android 휴대폰, 태블릿, 헤드 유닛에서 실행됩니다.

## 릴리스 브랜치와 개발 브랜치

릴리스마다 CommaView 런타임을 이 포크들의 릴리스 빌드에 맞춰 빌드하고 확인합니다. openpilot의 nightly와 sunnypilot의 dev 브랜치는 조기 경고를 위해 바뀌는 날마다 확인합니다. 개발 브랜치는 CommaView보다 빨리 바뀔 수 있습니다. 변경으로 CommaView 훅이 로드되지 않더라도 포크의 화면과 주행은 평소처럼 계속됩니다.

## 내 포크가 목록에 없나요?

제한 지원으로 사용해 보고, [my.commaview.com](https://my.commaview.com)의 기능 요청 게시판에서 목록에 추가해 달라고 요청하거나 앱에서 아이디어를 보내세요(설정 › **지원 및 진단**). 목록에 있는 포크는 릴리스마다 확인합니다. 릴리스마다 [새로운 기능](/whats-new)도 확인하세요.

## 자주 묻는 질문

**CommaView가 포크의 주행 방식을 바꾸나요?** 아니요. 포크 옆에 작은 런타임을, 화면 UI에 작은 훅을 추가해 CommaView가 같은 경로, 차선, 알림을 그릴 수 있게 할 뿐입니다. 차량의 주행 방식은 바뀌지 않습니다.

**CommaView는 StarPilot에서 작동하나요?** 네, CommaView 0.0.162부터 작동합니다. Live View에 StarPilot 고유의 색, 위젯, 카메라 선택이 표시됩니다. StarPilot의 **Disable Logging** 설정은 끄세요. CommaView가 스트리밍하는 비디오 인코더가 멈춥니다.

**CommaView는 carrotpilot에서 작동하나요?** 네, CommaView 0.0.164부터 작동합니다. Live View는 openpilot 화면을 그립니다. carrotpilot이 자체 화면에 더하는 내비게이션이나 과속 단속 카메라 등은 아직 그리지 않습니다. carrotpilot이 자동 업데이트하면 앱이 재시작을 요청하고, 재시작하면 Live View가 돌아옵니다.

**CommaView는 FrogPilot에서 작동하나요?** 아직은 아닙니다. openpilot의 이전 네이티브(Qt) 화면을 실행해 CommaView 화면이 들어갈 자리가 없으므로, 설정은 지원하지 않는다고 알리고 아무것도 바꾸지 않습니다. FrogPilot과 KisaPilot용 영상 전용은 테스터를 위한 얼리 액세스 중입니다.
