---
title: "CommaView 0.0.164: carrotpilot, SunnyPilot-TeslaHW1, 실시간 사본"
description: "CommaView 0.0.164는 carrotpilot과 SunnyPilot-TeslaHW1을 지원하고, 운전 중 Live View 화면을 저장하는 실시간 사본을 더했습니다. 내비게이션과 Surround 얼리 액세스도 있습니다."
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot forks
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - recordings
heroLabel: "릴리스 노트"
draft: false
---

CommaView 0.0.164를 베타 참여자 모두에게 배포했습니다. openpilot 포크 두 개, **carrotpilot**과 **SunnyPilot-TeslaHW1**을 새로 지원해, 이제 CommaView는 openpilot, sunnypilot, StarPilot, xnor-tech의 openpilot, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot의 일곱 가지에서 작동합니다. 또한 운전하는 동안 Live View가 보여 주는 것을 저장해 멈추는 순간 바로 쓸 수 있는 **실시간 사본**도 추가되었습니다.

런타임 `v0.0.60-beta`가 함께 나오며, 새 포크 두 개를 인식합니다. 앱이 안내하면 앱에서 런타임을 업데이트하고, 앱이 요청하면 comma를 재시작하세요.

## SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1은 Tesla의 HW1(Autopilot 1) 차량을 지원하는 sunnypilot 포크입니다. 화면이 sunnypilot의 것이므로 CommaView는 sunnypilot이 더한 모든 요소와 함께 sunnypilot 화면을 그리고, 앱에 포크 이름을 표시합니다.

알아 둘 점이 하나 있습니다. CommaView의 훅이 설치된 동안에는 이 포크의 `op fork update`로 포크를 옮길 수 없습니다. 먼저 CommaView를 제거하거나, comma 화면의 포크 전환 기능을 쓰세요. 이쪽은 평소처럼 작동합니다.

## carrotpilot

carrotpilot은 Hyundai, Kia, Genesis 차량용 openpilot 포크로, `i.carrotpilot.app`에서 설치합니다. CommaView는 carrotpilot에 openpilot 화면을 그려 속도, 경로, 차선, 앞차를 보여 주고, 앱에 포크 이름을 표시합니다.

현재는 제한이 두 가지 있습니다.

- **carrotpilot 고유의 화면은 아직 그리지 않습니다.** carrotpilot이 openpilot 화면에 더하는 내비게이션, 과속 단속 카메라, HUD 등은 Live View에 나타나지 않습니다.
- **carrotpilot의 업데이트는 comma가 재시작할 때까지 CommaView의 훅을 없앱니다.** carrotpilot의 자동 업데이트와 웹 페이지의 Git 도구는 실행 중에 파일을 초기화합니다. 망가지는 것은 없습니다. 앱이 재시작을 요청하고, 재시작하면 Live View가 돌아옵니다.

## 실시간 사본

지금까지 녹화는 다시 보기를 만들었습니다. 주차하면 앱이 comma 원본 영상을 내려받아 그 위에 HUD를 그립니다. 화질은 여전히 이쪽이 가장 좋지만, 주행 후 시간이 걸리고 녹화 하나가 10분에서 멈춥니다.

이제 설정 › 녹화 › **Live View에서 녹화**에서 녹화가 무엇을 만들지 고를 수 있습니다.

| 선택 | 결과 |
| --- | --- |
| 다시 보기(기본값) | comma 원본 영상 위에 HUD를 그린 것으로, 주차 후 만들어집니다. 화질이 가장 좋고, 녹화 하나에 최대 10분입니다. |
| 실시간 사본 | 운전하는 동안 Live View가 보여 주는 것으로, 휴대폰에 저장되어 멈추는 순간 녹화에서 볼 수 있습니다. 10분 제한이 없습니다. |
| 둘 다 | 지금은 실시간 사본, 주행 후에는 다시 보기. |

실시간 사본은 720p(시간당 약 1.4 GB) 또는 1080p(시간당 약 2.3 GB), 초당 20프레임입니다. 다른 앱으로 전환하거나 휴대폰을 잠가도 계속되며, 알림에서 멈출 수 있습니다. 휴대폰 저장 공간이 바닥나기 전에 깔끔하게 멈추고, 녹화 중에 앱이 닫혀도 마지막 1분을 뺀 나머지는 모두 남습니다.

실시간 사본은 휴대폰에 남으며 절대 업로드되지 않습니다.

## 0.0.164의 다른 변경 사항

- **화면 전체를 쓰는 설정.** 녹화, 디스플레이, 라이브 방송 페이지가 오프라인 지도처럼 배치되어 공간이 되면 두 열로 표시되고, 태블릿, 헤드 유닛, 가로로 든 휴대폰에서도 가지런히 정렬됩니다.
- **설치가 실패한 이유.** 설정, 런타임 업데이트, 제거가 실패하면 앱이 무엇이 잘못되었고 어떻게 해야 하는지 알려 줍니다. CommaView가 지원하지 않는 포크, 주행 중인 차, comma의 인터넷 연결 없음, 손상된 다운로드 등입니다. comma가 원래대로 되돌려졌는지도 알려 주며, 세부 정보 복사로 지원팀에 필요한 보고서를 복사할 수 있습니다.
- **더 빨라진 다시 보기.** 다시 보기는 보여 줄 부분의 영상만 내려받고, 하나를 만드는 동안 대기열의 다음 주행을 내려받습니다. 앱 종료, 10분 제한, 차량 시동 꺼짐으로 중간에 끊긴 녹화도 이제 다시 보기로 만들 수 있습니다.
- **다시 보기 화질이 다시 작동.** Balanced, High, Max가 다시 서로 다른 다시 보기를 만듭니다. 그동안은 모든 다시 보기가 같은 40 Mbit/s로 만들어졌습니다. 기본값인 High는 이제 comma 3X에서 파일 크기가 약 절반입니다.

## 얼리 액세스: 내비게이션과 Surround

일부 기능은 초기 개발 단계에 있습니다. **내비게이션**, **Surround**, **라이브 시작**, **CommaView로 보내기**입니다. 의견을 모으는 동안 기능 플래그 뒤에 두고 제한된 테스터 그룹에게만 공개하므로, 기능이 켜진 계정에서만 보입니다.

- **내비게이션**은 홈에서 Live View까지 이어지는 턴바이턴 안내입니다. 장소를 검색하고 경로를 고른 다음, 회전 카드, 음성 안내, 그리고 CommaView 화면에서는 차선에 그려진 화살표를 따라가면 됩니다. 길을 잘못 들면 몇 초 안에 새 경로를 찾습니다. 표시 전용이며, comma나 차량에는 아무것도 보내지 않습니다.
- **Surround**는 차 주변 도로를 3D로 보여 줍니다. 카메라가 보는 도로를 차선과 교차로까지 그리고, 주변의 승용차, 트럭, 신호등도 보여 줍니다.

내비게이션의 경로 탐색처럼 일부는 유료 서비스로 작동하므로, 일반적인 사용에 비용이 얼마나 드는지 알 때까지 그룹을 작게 유지합니다. 테스트를 돕고 싶다면 [Discord](https://discord.gg/UuMhz9K8ft)로 연락해 주세요. 실제 주행에서 어땠는지 알려 주시면 큰 도움이 됩니다.

## 받는 방법

CommaView는 초대제 베타입니다. 참여 중이라면 앱이 0.0.164 업데이트를 알아서 안내합니다. 업데이트한 다음 앱에서 comma의 런타임을 업데이트하고, 요청하면 comma를 재시작하세요. 런타임 업데이트는 차가 P단에 있고 openpilot이 해제될 때까지 기다리므로 주행이 중단되지 않습니다.

CommaView가 처음이라면 [설정 가이드](/ko/guides/setup)에서 앱 설치부터 comma 연결까지 차례로 안내합니다.

## 더 읽어 보기

- [CommaView와 함께 쓸 수 있는 openpilot 포크](/forks)([SunnyPilot-TeslaHW1](/forks#teslahw1), [carrotpilot](/forks#carrotpilot) 포함)
- 모든 릴리스의 [새로운 기능](/whats-new)
- [CommaView 릴리스 방식](/ko/guides/releases)

CommaView는 비공식 앱이며 comma.ai, sunnypilot, carrotpilot, SunnyPilot-TeslaHW1과 관련이 없습니다. 베타 소프트웨어이며 안전 시스템이 아닙니다. 운전에 방해가 되지 않도록 하세요.
