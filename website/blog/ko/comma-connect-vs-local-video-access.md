---
title: "comma connect와 로컬 영상: 필요한 일을 해 주는 쪽은?"
description: "openpilot 0.11.2 이후의 comma connect, SSH, CommaView 비교: 주차 중 실시간 스트리밍, 클립, 주행 보관 기간, 화질, 개인정보, 그리고 각각의 용도."
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - local video access
  - comma four
  - CommaView
heroLabel: "선택 가이드"
draft: false
---

comma의 자체 웹 앱인 comma connect는 대부분의 사용자가 주행을 처음 보는 곳이며, 많은 경우 그게 맞는 선택입니다. openpilot 0.11.2부터는 할 수 있는 일이 늘어, 주차한 차를 실시간으로 스트리밍하고 장치에서 MP4 클립을 잘라 낼 수 있습니다. SSH나 CommaView를 통한 로컬 접근은 다른 일을 합니다. 내 네트워크에서 comma로부터 영상을 바로 가져옵니다.

간단히 정리하면 이렇습니다.

- **최근 주행을 어디서나:** comma connect.
- **주차한 차 상태 확인:** comma connect의 실시간 스트리밍.
- **운전하면서 포크의 주행 오버레이와 함께 도로를 더 큰 화면으로 보기:** CommaView의 Live View.
- **개발이나 보관용 원본 카메라 파일:** SSH.
- **방금 본 장면을 오버레이와 함께 업로드 없이 휴대폰에 클립으로:** CommaView의 녹화.

## comma connect가 하는 일

**주행을 일정 기간 클라우드에 보관합니다.** comma의 [prime 페이지](https://comma.ai/prime)에 따르면 녹화는 “connect에 업로드되어 3일 동안 보관”됩니다. comma prime(월 24달러, 미국 전용, 데이터 포함)이나 prime lite(월 14달러, 셀룰러를 쓰려면 SIM은 직접 준비)를 쓰면 connect가 1년 동안 보관합니다.

**기본으로 보여 주는 것은 작은 영상입니다.** comma의 [로그 문서](https://docs.comma.ai/concepts/logs/)에 따르면 connect의 영상은 qcamera 파일, 즉 “fcamera.hevc의 저해상도 버전”에서 나오며, 느린 연결에서도 빨리 업로드되도록 만들어졌습니다. 원본 해상도의 HEVC 파일은 따로 업로드하지 않는 한 comma에 남습니다.

**0.11.2부터 주차한 차를 실시간으로 스트리밍할 수 있습니다.** [0.11.2 릴리스 글](https://blog.comma.ai/0112release/)(2026년 10월 23일)에 따르면 인터넷 연결(“집 Wi-Fi 또는 comma prime LTE”)이 있고 comma power가 설치되어 있으면 “주차 중에 도로 카메라와 운전자 카메라를 실시간으로 스트리밍해 차 주변에서 무슨 일이 일어나는지 볼 수 있습니다”. connect에서 어디서나 볼 수 있습니다.

**클립도 잘라 냅니다.** 같은 릴리스에서 connect에 클립 버튼이 생겼습니다. 주행의 일부를 고르면 “comma가 이를 이어 붙여 널리 지원되는 MP4(H.264)로 다시 인코딩”합니다. 작업하는 동안 comma를 켜 두었다가 connect에서 클립을 내려받으면 됩니다.

이는 분명한 발전입니다. 책상에서 주차한 차를 보고 싶거나 어젯밤 주행의 클립을 친구에게 보내고 싶다면, 이제 connect로 둘 다 할 수 있습니다.

## comma connect가 하지 않는 일

- **운전 중에는 스트리밍하지 않습니다.** 실시간 스트리밍은 주차한 차를 위한 것입니다.
- **openpilot의 주행 오버레이를 그리지 않습니다.** 실시간 스트리밍과 클립은 카메라 영상일 뿐이며, comma 화면에 보이는 경로, 차선, 경고, 속도가 없습니다.
- **인터넷이 필요합니다.** 실시간 스트리밍에는 집 Wi-Fi나 prime의 LTE가 필요하고, 주행은 connect에 보이기 전에 업로드되어야 합니다.
- **prime이 없으면 3일 뒤에 사라집니다.** 그 뒤에는 comma에 주행이 남아 있어도 connect에 더 이상 나오지 않습니다.

이것들은 결함이 아닙니다. connect는 어디에 있든 차와 주행을 보기 위한 클라우드 서비스입니다.

## 로컬 접근이 하는 일

로컬 접근이란 comma의 서버가 아니라 같은 네트워크에서 comma 자체로부터 영상을 가져오는 것입니다.

### SSH: 원본 파일

openpilot의 모든 주행은 comma에 1분 단위 세그먼트로 저장되며, 세그먼트마다 파일이 따로 있습니다. `fcamera.hevc`(도로), `ecamera.hevc`(광각 도로), `dcamera.hevc`(운전자), `qcamera.ts`(작은 미리 보기), 그리고 로그입니다. SSH로는 comma에 남아 있는 동안 무엇이든 복사할 수 있습니다. comma는 공간이 부족하면 가장 오래된 주행부터 지웁니다. 개발이나 개인 보관용으로 원본 해상도 영상을 얻는 방법이지만, 받는 것은 1분 단위 HEVC 파일이지 바로 공유할 수 있는 클립이 아닙니다. [comma 영상 다운로드](/ko/blog/download-comma-dashcam-footage) 가이드에서 방법을 설명합니다.

### CommaView: Android에서 Live View와 녹화

CommaView는 Android 앱과 comma의 작은 런타임 `commaviewd`로 이루어지며, 카메라와 주행 데이터를 내 로컬 네트워크를 통해 휴대폰으로 보냅니다. 그 네트워크는 Wi-Fi일 수도, 차 안의 핫스팟(휴대폰, 헤드 유닛, comma 중 어느 것이든)일 수도 있습니다.

- **운전 중 Live View.** 도로 카메라 위에 사용하는 포크 고유의 화면을 comma four나 comma 3X가 그리는 대로, 또는 CommaView 고유 화면을 그려 휴대폰, 대시보드의 태블릿, Android 헤드 유닛에 보여 줍니다. comma four의 화면은 1.9인치이고, 휴대폰 화면은 훨씬 큽니다.
- **휴대폰에 녹화.** Live View에서 녹화를 탭하면, 주차한 뒤 CommaView가 그 구간의 comma 원본 영상을 최대 10분까지 내려받고 휴대폰에서 포크 화면을 그 위에 그립니다. 또는 Live View가 보여 주는 것을 720p나 1080p로, 10분 제한 없이 실시간 사본으로 저장할 수 있습니다. 재생하거나, 공유하거나, 다른 앱에서 열 수 있습니다.
- **라이브 방송.** Live View가 보여 주는 것, 즉 도로와 오버레이를 YouTube 채널이나 원하는 RTMP 서버로 720p 또는 1080p로 방송합니다.
- **구독도 업로드도 없습니다.** Live View와 녹화는 comma에서 휴대폰으로 가며, 녹화는 삭제할 때까지 휴대폰에 남습니다. comma의 카메라는 페어링한 휴대폰과 헤드 유닛에만 전달됩니다.

comma 3X와 comma four에서 openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot을 지원하고, 다른 포크도 제한 지원합니다. [지원 포크와 각각에서 Live View가 그리는 것](/forks).

## 나란히 비교

| 기능 | comma connect | CommaView |
| --- | --- | --- |
| 실시간 영상 | 도로 카메라와 운전자 카메라, 주차 중 | 도로 카메라, 운전 중 |
| 주행 오버레이 | 없음 | 포크의 화면 또는 CommaView의 화면 |
| 영상이 가는 곳 | 인터넷을 통해 connect에서 시청 | 내 로컬 네트워크(Wi-Fi 또는 핫스팟)를 통해 페어링한 휴대폰으로 |
| 필요한 것 | 인터넷, 실시간 스트리밍에는 comma power | 같은 네트워크의 Android 휴대폰, 태블릿, 헤드 유닛 |
| 클립 | 주행의 원하는 부분을 comma에서 MP4로 잘라 connect에서 내려받기 | Live View에서 녹화한 것: 최대 10분의 다시 보기 또는 실시간 사본, 오버레이 포함 |
| 주행 보관 기간 | 3일, prime이 있으면 1년 | 삭제할 때까지 휴대폰에 |
| 비용 | 무료, 또는 prime 월 24달러 / lite 월 14달러 | 구독 없음. CommaView는 초대제 베타 |

## 둘 다 쓰세요

둘은 같은 일을 두고 경쟁하지 않습니다. 어디서나 차를 보거나 클라우드에 두고 싶은 주행에는 connect를, 포크의 오버레이와 함께 도로를 더 큰 화면으로 보고, 본 것을 녹화하고, 방송하는 데는 CommaView를 쓰세요. 운전 중에는 동승자가 Live View를 보는 것이 좋습니다. 혼자 운전할 때는 comma 자체 화면처럼 다루고 눈을 도로에서 떼지 마세요.

## 더 읽어 보기

- [comma prime](https://comma.ai/prime): connect의 요금제와 주행 보관 기간
- [openpilot 0.11.2](https://blog.comma.ai/0112release/): 실시간 스트리밍과 클립
- [comma 영상 다운로드 방법](/ko/blog/download-comma-dashcam-footage)(SSH)
- [CommaView 설정](/ko/guides/setup)

CommaView는 비공식 앱이며 comma.ai, sunnypilot 및 함께 작동하는 어떤 openpilot 포크와도 관련이 없고 승인을 받지도 않았습니다. 베타 소프트웨어이며 안전 시스템이 아닙니다. 운전에 방해가 되지 않도록 하세요.
