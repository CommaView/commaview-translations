---
title: "comma 장치에서 블랙박스 영상을 내려받는 방법"
description: "comma 영상 파일, comma 3 / 3X / four의 차이, 그리고 경로 영상을 가장 안전하게 내보내는 방법을 다룬 실용 가이드."
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma device video
  - dashcam footage
  - openpilot tools
  - SSH
heroLabel: "comma 장치 가이드"
draft: false
---

comma 장치에서 영상을 꺼내야 하나요? 흔히 쓰는 방법은 comma connect, Openpilot Toolkit, 또는 SSH/SFTP 직접 접근입니다.

사람들이 헷갈리는 부분은 파일 구조입니다. comma 장치는 openpilot 경로를 하나의 긴 블랙박스 영상이 아니라 짧은 세그먼트로 나누어 기록합니다. 각 세그먼트에는 원본 카메라 파일, 미리 보기 영상, 경로 로그가 들어 있을 수 있습니다. 이것만 이해하면 영상 내보내기가 훨씬 쉬워집니다.

먼저 중요한 점 하나. comma 장치는 도로 영상, 디버깅, 경로 검토에 유용하지만, 전용 블랙박스를 그대로 대신할 수는 없습니다.

## comma 장치는 유용한 카메라지만 완벽한 블랙박스는 아닙니다

전용 블랙박스는 증거를 남기는 데 맞춰 만들어집니다. 빠른 부팅, 사고에 견디는 구조, 주차 모드, 간단한 파일 내보내기, 후방 카메라 옵션, 분리할 수 있는 저장 장치입니다.

comma 장치는 openpilot을 실행하려고 만들어졌습니다. 경로 데이터를 기록하는 이유는 주행 모델, 디버깅, connect 미리 보기, 개발에 유용하기 때문입니다. 그 영상은 가치가 있지만 대가도 따릅니다.

- SD 카드를 빼는 것보다 영상을 꺼내기 어려울 수 있습니다
- 사고나 갑작스러운 전원 차단으로 최근 영상을 잃을 수 있습니다
- 주차 중 녹화는 주된 설계 목표가 아닙니다
- 후방 블랙박스 영상은 포함되지 않습니다
- 장치에 공간이 필요하면 오래된 로컬 데이터가 삭제됩니다

믿을 수 있는 사고 영상이 목적이라면 진짜 블랙박스를 쓰세요. openpilot 경로 영상, 개발용 검토, 로컬 영상 내보내기가 목적이라면 comma의 작업 방식을 익혀 둘 만합니다.

## openpilot은 어떤 파일을 기록하나요?

openpilot의 공식 로그 문서는 경로를 1분 단위 세그먼트로 설명합니다. 최신 openpilot은 세그먼트마다 다음 종류의 파일을 기록합니다.

| 파일 | 내용 |
| --- | --- |
| `fcamera.hevc` | 도로 카메라 영상, H.265/HEVC |
| `ecamera.hevc` | 광각 도로 카메라 영상, H.265/HEVC |
| `dcamera.hevc` | 운전자/실내 카메라 영상, H.265/HEVC |
| `qcamera.ts` | 도로 카메라의 저해상도 H.264 미리 보기 |
| `rlog.zst` | 전체 경로 로그 |
| `qlog.zst` | 작게 솎아 낸 경로 로그 |

comma connect에 표시되는 영상은 저해상도 `qcamera.ts`입니다. 원본 해상도의 카메라 영상은 HEVC 파일에 있으며, connect에서 직접 업로드하거나 장치에서 바로 복사해야 할 수 있습니다.

오래된 경로, 오래된 포크, 오래된 문서에는 `.zst`가 없는 `rlog`/`qlog`나 예전의 `.bz2` 로그 이름이 나올 수 있습니다. 최신 openpilot에서는 위의 이름을 쓰세요.

## comma 3, comma 3X, comma four: 무엇이 다른가요?

사람들이 섞어서 이야기하는 별개의 두 가지가 있습니다. 카메라 하드웨어와 파일 구조입니다.

카메라 하드웨어는 세대마다 다릅니다.

| 장치 | 카메라/저장 공간 |
| --- | --- |
| comma 3 | 120 dB HDR의 1080p 카메라 3개. 커뮤니티 문서에는 1TB, 250GB, 후기 64GB, 초기 32GB 등 여러 저장 용량이 나옵니다. |
| comma 3X | comma 3와 같은 3카메라 구성에 이미지 센서를 OX03C10으로 업그레이드했고, 140 dB HDR. 저장 공간은 보통 128GB로 알려져 있습니다. |
| comma four | comma에 따르면 comma 3X와 같은 연산 성능, 센서 구성, 기능을 훨씬 작은 본체에 담았습니다. 3카메라 시스템이 1.9인치 화면 크기 안에 들어가며, 도로를 향한 카메라 2개와 야간 투시 실내 카메라를 갖췄습니다. comma는 128GB 저장 공간과 10시간 분량의 영상이라고 밝힙니다. |

여기의 파일 설명은 세 기종 모두에 해당합니다. CommaView 자체는 comma 3X와 comma four에서만 작동합니다.

최신 openpilot에서는 실제 파일 구조가 comma 하드웨어 사이에 공통입니다. 최신 세그먼트 파일은 `fcamera.hevc`, `ecamera.hevc`, `dcamera.hevc`, `qcamera.ts`, `rlog.zst`, `qlog.zst`입니다.

즉 카메라가 물리적으로 바뀌어도 내보낼 파일 이름은 그대로입니다. `fcamera.hevc`는 도로 카메라, `ecamera.hevc`는 광각 도로 카메라, `dcamera.hevc`는 운전자/실내 카메라입니다.

커스텀 포크를 쓴다면 모든 파일이 있다고 가정하기 전에 장치에서 확인하세요. 포크는 녹화 설정을 바꿀 수 있고, 운전자/실내 카메라 녹화는 장치 설정에 따라 달라질 수 있습니다.

## 파일은 로컬 어디에 저장되나요?

comma 하드웨어에서 현재 openpilot의 로그 루트는 다음과 같습니다.

```text
/data/media/0/realdata
```

이 폴더 안에 경로 세그먼트마다 타임스탬프가 붙은 폴더가 생깁니다. 예를 들면 다음과 같습니다.

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

이 폴더에서 다음과 같은 파일을 찾으면 됩니다.

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

SSH/SFTP로 직접 작업한다면 이 폴더에서 시작하세요. 공식 문서는 SSH로 comma 3X나 comma four에 연결하는 방법을 설명하며, openpilot은 장치의 로그 루트로 `/data/media/0/realdata`를 씁니다.

## 방법 1: comma connect 사용

최근 주행이라면 보통 comma connect에서 시작하는 것이 가장 쉽습니다.

이럴 때 connect를 쓰세요.

- 경로가 최근 것일 때
- 장치가 경로를 제대로 업로드했을 때
- 미리 보기 영상으로 충분할 때
- SSH 대신 웹 화면을 쓰고 싶을 때
- 클립이나 파일 몇 개만 필요할 때

connect는 많은 사용자가 필요한 경로와 세그먼트 번호를 처음 확인하는 곳이기도 합니다. 문제는 보관 기간입니다. 로컬 장치가 아직 지우지 않은 경로도 connect에서는 더 이상 보이지 않을 수 있습니다. connect에 경로가 더 이상 나오지 않아도 장치에 파일이 남아 있다면 SSH/SFTP로 되찾을 수 있습니다.

또한 connect 미리 보기는 `qcamera.ts`를 바탕으로 한다는 점을 기억하세요. 원본 해상도의 카메라 영상이 필요하다면 전체 영상 파일이 업로드되었는지 확인하거나 원본 HEVC 파일을 직접 가져오세요.

## 방법 2: Openpilot Toolkit 사용

Openpilot Toolkit은 로컬 내보내기를 덜 번거롭게 해 주는 커뮤니티 도구입니다. SSH 설정, 파일 탐색, 주행 영상 미리 보기, 원본 내보내기 기능이 있습니다.

이럴 때 Openpilot Toolkit을 쓰세요.

- GUI를 원할 때
- SSH 명령을 직접 짜고 싶지 않을 때
- 키 설정에 도움이 필요할 때
- Windows나 Android를 쓸 때
- 경로 영상을 더 직접 탐색하고 내보내고 싶을 때

많은 사용자에게는 이것이 가장 좋은 절충안입니다. connect보다 자유롭고, 터미널 수작업보다 덜 번거롭습니다.

## 방법 3: SSH나 SFTP 직접 사용

SSH/SFTP를 직접 쓰면 가장 자유롭지만, 도와주는 것도 가장 적습니다.

대략적으로 SSH 접근은 보통 다음과 같습니다.

1. SSH 키가 등록된 GitHub 계정을 만들거나 기존 계정을 씁니다.
2. comma 장치 설정에서 SSH를 켭니다.
3. comma 장치에 GitHub 사용자 이름을 입력해 공개 키를 가져올 수 있게 합니다.
4. 사용자 `comma`, 포트 `22`로 연결합니다.

연결되면 다음 위치를 탐색하거나 복사합니다.

```text
/data/media/0/realdata
```

이럴 때 직접 접근을 쓰세요.

- 원본 `fcamera.hevc`, `ecamera.hevc`, `dcamera.hevc` 파일이 필요할 때
- 필요한 파일이 connect에 나오지 않을 때
- 경로 전체를 보관하고 싶을 때
- FileZilla나 WinSCP 같은 SFTP 클라이언트에 익숙할 때
- `ssh`, `scp`, `rsync`에 익숙할 때

원본 `.hevc` 파일은 대개 VLC에서 재생됩니다. 다른 앱에 MP4가 필요하다면 가능한 한 다시 인코딩하지 말고 ffmpeg로 리먹싱하세요.

## 어떤 방법을 써야 하나요?

주행이 최근 것이고 일반적인 경로 검토로 충분하다면 comma connect를 쓰세요.

SSH/SFTP 단계를 모두 손으로 하지 않고 더 편한 로컬 작업 방식을 원한다면 Openpilot Toolkit을 쓰세요.

원본 파일, 오래된 로컬 파일, 경로 전체 보관이 필요하거나 무엇을 복사할지 직접 정하고 싶다면 SSH나 SFTP를 쓰세요.

## CommaView의 자리

CommaView는 comma 장치의 카메라 스트리밍, 오버레이, 런타임 설정, 녹화, 다시 보기를 위한 로컬 우선 Android 앱입니다.

로컬 카메라 접근이라는 같은 영역에 겹치지만, comma connect도 Openpilot Toolkit도 일반적인 블랙박스도 아닙니다. 운전 보조 장치나 차량의 유일한 증거 기록 시스템으로 써서는 안 됩니다.

CommaView는 openpilot이나 [지원하는 포크](/forks)(sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot)를 실행하는 comma 3X와 comma four에서 작동합니다. comma 3는 지원하지 않습니다. comma가 comma 3를 업데이트가 멈춘 장기 지원 openpilot 릴리스로 옮겼고, CommaView는 그 화면에서 오버레이를 그릴 수 없기 때문입니다([이유](/ko/#faq-comma-3)).

## 더 읽어 보기

- openpilot 공식 로그 문서: [Logging](https://docs.comma.ai/concepts/logs/)
- comma 공식 SSH 문서: [comma 3X나 comma four에 연결하기](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect: [comma.ai/connect](https://comma.ai/connect)
- openpilot 위키: [Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma: [Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit: [프로젝트 페이지](https://spektor56.github.io/OpenpilotToolkit/)
