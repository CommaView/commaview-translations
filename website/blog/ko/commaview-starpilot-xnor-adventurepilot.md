---
title: "CommaView가 StarPilot, xnor, AdventurePilot을 지원합니다"
description: "CommaView 0.0.163은 0.0.162의 StarPilot에 이어 xnor-tech의 openpilot과 AdventurePilot을 지원합니다. 각 openpilot 포크가 comma 3X와 comma four의 Live View에서 보여 주는 것."
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "릴리스 노트"
draft: false
---

이제 CommaView는 다섯 가지 openpilot 빌드에서 작동합니다. **openpilot**, **sunnypilot**, **StarPilot**, **xnor-tech의 openpilot**(xnor와 rx 빌드), 그리고 **AdventurePilot**입니다. StarPilot은 CommaView 0.0.162에서 추가되었고, 0.0.163 베타에서 xnor와 AdventurePilot이 추가되었습니다. 어느 포크에서든 Live View는 그 포크 고유의 화면을, 포크가 더한 요소까지 Android 휴대폰, 태블릿, 헤드 유닛에 그립니다.

지금까지 이 포크들에서는 설정이 “unsupported upstream remote”에서 멈췄습니다. 0.0.163 앱과 그 런타임이라면 openpilot에서와 똑같이 설치하고 페어링할 수 있습니다.

## 각 포크가 Live View에서 보여 주는 것

CommaView는 포크 이름으로 짐작하지 않습니다. comma의 런타임이 포크 화면에 무엇이 더해졌는지 앱에 알려 주고, 앱은 그것을 comma four 화면, comma 3X 화면, 또는 CommaView 고유 화면에 그립니다.

| 포크 | CommaView가 그리는 것 |
| --- | --- |
| openpilot | comma four와 comma 3X 화면, 또는 CommaView 고유 오버레이 |
| sunnypilot | sunnypilot 화면: MADS, 제한 속도 보조, 무지개 경로, 사각지대 표시, comma 3X용 추가 요소 |
| StarPilot | StarPilot의 색상, 위젯, 경고, 카메라 선택 |
| xnor | xnor 빌드에서는 openpilot 화면, rx에서는 sunnypilot 화면, 그리고 rx의 Rivian 핸들 색상 |
| AdventurePilot | sunnypilot 화면에 차선 중앙 유지 표시, CURVE 칩, 조향 모드 색상을 더한 것 |

## StarPilot

StarPilot은 주행 모드를 색으로 보여 주며, CommaView는 StarPilot이 고른 색을 그대로 씁니다. 테두리, 경로, 위젯, 경고, 그리고 운전자 카메라를 포함한 카메라 선택까지입니다. 먼저 StarPilot의 **Disable Logging** 설정을 끄세요. 이 설정은 Live View가 스트리밍하는 영상 인코더를 멈춥니다.

## xnor-tech의 openpilot: xnor와 rx

xnor-tech의 openpilot은 하나의 저장소에서 두 가지 빌드로 나옵니다. **xnor** 브랜치는 openpilot 화면을, **rx** 브랜치는 sunnypilot 화면을 쓰며, 둘 다 xnor-tech의 차량 지원을 포함합니다. CommaView는 comma가 어느 쪽을 실행하는지 알아내 그 화면을 그리고, 경고도 comma가 표시하는 그대로 보여 줍니다.

rx를 실행하는 Rivian에서는 핸들 색이 차의 조향 방식을 보여 줍니다. 각도로 조향할 때는 초록색, 토크로 조향할 때는 파란색입니다. CommaView는 같은 색을 comma four의 핸들과 comma 3X의 실험 모드 버튼에 그립니다.

## AdventurePilot

AdventurePilot은 자체 차량 지원을 갖춘 sunnypilot 포크입니다. CommaView는 sunnypilot 화면에 AdventurePilot이 더한 요소를 그립니다.

- **차선 중앙 유지 표시**: comma 3X 화면에서는 밀어내기와 오프셋을 보여 주는 알약 모양, comma four 화면에서는 작은 막대
- comma 3X 화면의 **CURVE 칩**: 커브 속도 제어가 작동하는 동안 깜빡입니다
- 핸들의 **조향 모드 색상**, 그리고 Rivian이 각도 채널로 조향하는 동안 횡가속도를 보여 주는 토크 막대

## 받는 방법

CommaView는 초대제 베타입니다. 참여 중이라면 앱이 0.0.163 업데이트를 알아서 안내합니다. 앱을 업데이트한 다음 앱에서 comma의 런타임을 업데이트하고, 요청하면 comma를 재시작하세요. 런타임 업데이트는 차가 P단에 있고 openpilot이 해제될 때까지 기다리므로 주행이 중단되지 않습니다.

CommaView가 처음이라면 [설정 가이드](/ko/guides/setup)에서 앱 설치부터 comma 연결까지 차례로 안내합니다.

## 바뀌지 않은 것

- CommaView는 **comma 3X**와 **comma four**에서 작동합니다. comma 3는 여전히 지원하지 않으며, xnor-c3 같은 포크의 comma 3용 빌드도 마찬가지입니다([이유](/ko/#faq-comma-3)).
- CommaView는 포크의 주행 방식을 바꾸지 않습니다. 작은 런타임을 옆에 두고 화면 UI에 작은 훅을 넣어 같은 경로, 차선, 경고를 그릴 수 있게 할 뿐입니다.
- CommaView가 아직 지원하지 않는 포크에서는 설정이 멈추고 comma는 원래대로 남습니다. my.commaview.com의 기능 요청 보드에서 사용하는 포크의 지원을 요청할 수 있습니다.

## 더 읽어 보기

- [CommaView와 함께 쓸 수 있는 openpilot 포크](/forks)와 각각이 보여 주는 것
- 모든 릴리스의 [새로운 기능](/whats-new)
- [CommaView 릴리스 방식](/ko/guides/releases)

CommaView는 비공식 앱이며 comma.ai, sunnypilot, StarPilot, xnor-tech, AdventurePilot과 관련이 없습니다. 베타 소프트웨어이며 안전 시스템이 아닙니다. 운전에 방해가 되지 않도록 하세요.
