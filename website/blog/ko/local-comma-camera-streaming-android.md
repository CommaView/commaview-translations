---
title: "Android에서 comma 카메라 로컬 스트리밍: CommaView가 하는 일"
description: "CommaView는 comma의 도로 카메라를 주행 오버레이와 함께 내 네트워크로 Android에 스트리밍합니다. Live View, 녹화, 라이브 방송, 그리고 하지 않는 일."
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma camera streaming
  - comma four
  - Android app
  - CommaView
  - local streaming
heroLabel: "제품 적합성"
draft: false
---

CommaView는 comma의 도로 카메라를 주행 오버레이와 함께 내 네트워크를 통해 Android 휴대폰, 태블릿, 헤드 유닛으로 스트리밍합니다. comma와 휴대폰 사이에 클라우드가 끼지 않고, 먼저 업로드할 필요도 없습니다.

구성은 두 가지입니다. CommaView 앱, 그리고 comma에서 카메라와 주행 데이터를 앱에 보내는 작은 런타임 `commaviewd`입니다. 안내 설정이 런타임을 설치하고 점검합니다.

## 왜 스트리밍하나요

comma four의 화면은 1.9인치입니다. 제 역할은 잘하지만 작고, 사용자들도 그렇게 말합니다. comma에서 영상을 보는 다른 방법은 다른 용도에 맞춰져 있습니다.

- **comma connect**는 업로드한 주행을 3일 동안, comma prime이 있으면 1년 동안 보관합니다([comma.ai/prime](https://comma.ai/prime)). [openpilot 0.11.2](https://blog.comma.ai/0112release/)부터는 comma power가 설치되어 있으면 주차 중에 도로 카메라와 운전자 카메라를 인터넷으로 실시간 스트리밍할 수 있고, comma에서 MP4 클립을 잘라 낼 수 있습니다.
- **SSH**로는 comma 저장 공간에서 1분 단위의 원본 HEVC 세그먼트를 가져올 수 있습니다.

둘 다 운전하는 동안 openpilot의 주행 오버레이와 함께 도로를 보여 주지는 않습니다. CommaView가 바로 그 일을 합니다.

## CommaView가 하는 일

### Live View

도로 카메라의 실시간 영상 위에 사용하는 포크 고유의 화면을 그립니다. comma four 화면, comma 3X 화면, 또는 CommaView 고유 화면으로, 속도, MAX, 제한 속도, 앞차, 차선 변경을 하나의 클러스터에 모아 보여 줍니다. Live View는 sunnypilot의 MADS부터 StarPilot 고유의 HUD까지, 각 포크의 화면을 그 포크가 더한 요소까지 그립니다. comma의 최대 초당 20프레임으로 작동하고, 화면 속 화면에서도 계속 실행됩니다.

태블릿이나 Android 헤드 유닛에서는 CommaView가 대시보드처럼 배치되고, Live View 조작 버튼은 운전석 쪽에 놓입니다.

### 녹화

Live View에서 녹화를 탭하면, 주차한 뒤 CommaView가 그 구간의 comma 원본 영상을 최대 10분까지 내려받고 휴대폰에서 포크 화면을 그 위에 그립니다. 이것이 다시 보기입니다. 재생하거나, 공유하거나, 다른 앱에서 열 수 있습니다. 실시간 사본은 운전하는 동안 Live View가 보여 주는 것을 720p 또는 1080p로 저장하며, 멈추는 순간 바로 볼 수 있고 10분 제한도 없습니다. 녹화는 삭제할 때까지 휴대폰에 남습니다.

### 라이브 방송

라이브 방송은 Live View가 보여 주는 것, 즉 도로와 CommaView의 오버레이를 YouTube 채널이나 원하는 RTMP 서버로 720p 또는 1080p로 방송합니다. YouTube로 한 번 로그인하면 방송마다 만들고, 시작하고, 끝내는 일까지 해 줍니다. 방송은 일부 공개로 시작합니다. 시청자는 내가 어디를 달리는지 볼 수 있습니다.

### 페어링한 휴대폰에만

comma의 카메라와 데이터는 페어링한 휴대폰과 헤드 유닛에만 전달됩니다. 영상, 주행, 장소는 comma에서 휴대폰으로만 가고, 직접 보내거나, 방송하거나, 기여하지 않는 한 다른 곳으로 가지 않습니다.

## 인터넷이 필요한 것

Live View와 녹화에는 필요 없습니다. 같은 로컬 네트워크에서 comma에서 휴대폰으로 바로 전달됩니다. 그 네트워크는 Wi-Fi일 수도 있고, 휴대폰, 헤드 유닛, AI 박스, comma 중 하나가 차 안에서 만든 핫스팟일 수도 있습니다. 로그인, 앱과 런타임 업데이트, 차량 위치의 지도, 리더보드, 라이브 방송, CommaView로 보내는 모든 것에는 인터넷이 필요합니다.

## 함께 쓸 수 있는 것

comma 3X와 comma four에서 openpilot, sunnypilot, StarPilot, xnor-tech의 openpilot, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot을 지원합니다. 다른 openpilot 포크는 제한 지원으로 작동합니다. 설정이 포크를 점검하고 설치하기 전에 묻습니다. comma 3는 지원하지 않습니다. comma 3는 업데이트가 멈춘 openpilot 릴리스에서 실행되며, CommaView는 그 화면에서 오버레이를 그릴 수 없습니다. [지원하는 포크](/forks).

Android 8 이상의 Android 휴대폰, 태블릿, 헤드 유닛이 필요합니다.

## CommaView가 아닌 것

- **comma connect가 아닙니다.** 주행을 클라우드에 보관하거나 멀리서 차를 보여 주지 않습니다. 그런 용도라면 connect를 쓰세요.
- **블랙박스가 아닙니다.** 사고나 주차 중 증거가 될 영상이 필요하다면 [전용 블랙박스를 쓰세요](/ko/blog/is-comma-a-dashcam).
- **운전 보조 장치나 안전 시스템이 아닙니다.** comma가 보는 것을 보여 줄 뿐이며, 판단의 기준은 실제 도로입니다.

## 안전하게 사용하기

CommaView 설정은 주차한 상태에서 하세요. 운전 중에는 동승자가 Live View를 보는 것이 좋습니다. 혼자 운전할 때는 comma 자체 화면처럼 다루고 눈을 도로에서 떼지 마세요.

CommaView는 초대제 베타입니다. [명단에 등록](https://my.commaview.com/join)하시면 차례가 되었을 때 이메일로 알려 드립니다.

CommaView는 비공식 앱이며 comma.ai, sunnypilot 및 함께 작동하는 어떤 openpilot 포크와도 관련이 없고 승인을 받지도 않았습니다. 베타 소프트웨어이며 안전 시스템이 아닙니다. 운전에 방해가 되지 않도록 하세요.
