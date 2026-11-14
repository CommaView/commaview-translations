# 한국어 (Korean) glossary

The words every Korean string uses for CommaView's terms, so screens translated apart say the same thing. Where
openpilot already translates a term (`openpilot/selfdrive/ui/translations/app_ko.po`), its word is used, so the app says
what the car's screen says. Machine drafted; a native speaker's review is owed before release
(the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`).

## Style

- Polite formal style, as openpilot's Korean: statements end in **-합니다 / -됩니다**, requests in **-하세요**,
  questions in **-하시겠습니까?** ("정말 재시작하시겠습니까?"). The person isn't addressed with a pronoun; where one
  can't be avoided, **내** in labels ("내 요청") and nothing in sentences (openpilot's 귀하의 reads stiff in an app).
- Western punctuation (. , : ? !) and normal Korean word spacing. Quotes are “ ” (nested ‘ ’), never straight quotes.
- Particles after a Latin name follow its Korean reading: openpilot**이**/**을**/**은** (‑t), comma**가**/**를**/**는**,
  CommaView**가**/**를**, YouTube**가**/**를**, Live View**가**/**를**. After a placeholder (`%1$s`) whose last sound
  isn't known, the sentence uses a particle that doesn't vary (의, 에, 에서, 에게, 도, 만) or puts a noun after
  the placeholder ("%1$s 파일을"), and only where that can't be done, 을(를) / 이(가). 와/과, 은/는, 로/으로 after a
  placeholder are avoided.
- Buttons are short nouns, as Korean UIs write them: 취소, 완료, 저장, 삭제, 다시 시도, 계속, 열기, 닫기, 확인.
- No full stop on titles, buttons, row titles or pills; whole sentences in body text end with a full stop.
- Numbers and units: a space before a unit word (`25.7 GB`), none before a counter (`3개`, `5분`, `2일`).

## Terms

| English | 한국어 | Note |
|---|---|---|
| Home (dock) | 홈 | |
| Recordings | 녹화 | the section and its saved drives |
| Settings | 설정 | |
| recording, a recording | 녹화 | 녹화 영상 where it means the video |
| drive (a trip the comma recorded) | 주행 | openpilot's 주행 데이터 |
| replay | 다시 보기 | |
| live copy | 실시간 사본 | |
| saved moment | 저장한 순간 | |
| Record | 녹화 | the rail's button |
| Go live / live streaming | 라이브 방송 | |
| onroad screen | 주행 화면 | |
| onroad / offroad (the comma's state) | 주행 중 / 정차 중 | |
| design (an onroad screen's look) | 디자인 | |
| overlay pack | 오버레이 팩 | |
| fork | 포크 | Korean openpilot users say 포크 |
| runtime (commaviewd) | 런타임 | |
| update / install / uninstall | 업데이트 / 설치 / 제거 | openpilot's |
| reboot | 재시작 | openpilot's |
| power off | 전원 끄기 | openpilot's |
| pair / pairing | 페어링 | openpilot's |
| device (the comma) | 장치 | openpilot's |
| this phone / this device (the device CommaView runs on) | 이 휴대전화 / 이 기기 | `common_this_phone` / `common_this_device`, a sentence's placeholder: both end in a vowel, so one particle (가, 를, 는, 와, 로) fits either (how-to-localize.md, "This phone or this device"). Elsewhere a phone is 휴대폰, openpilot's |
| your phone / your device (`common_your_*`) | 휴대전화 / 기기 | "your" left unsaid, as Korean does; both end in a vowel, as 이 휴대전화 / 이 기기 |
| connected / disconnected | 연결됨 / 연결 끊김 | |
| offline | 오프라인 | openpilot's |
| engaged / disengaged | 작동 중 / 해제됨 | openpilot's 작동 중, 해제 |
| override | 운전자 개입 | |
| experimental mode | 실험 모드 | openpilot's (older .po; the current one dropped the string) |
| driver monitoring | 운전자 모니터링 | openpilot's |
| driver camera | 운전자 카메라 | openpilot's (older .po; the current "Cabin Camera" is untranslated) |
| road camera / wide camera | 도로 카메라 / 광각 카메라 | |
| lead car | 앞차 | |
| speed limit | 제한 속도 | |
| set speed / MAX | 설정 속도 / 최대 | openpilot's MAX is 최대 |
| lane change | 차선 변경 | |
| calibration | 캘리브레이션 | openpilot's (it also says 보정 in sentences) |
| driver position (left/right-hand drive) | 운전석 위치 (왼쪽/오른쪽 운전석) | |
| daylight contrast | 주간 대비 | |
| offline maps | 오프라인 지도 | |
| navigation | 내비게이션 | |
| Home / Work (places) | 집 / 직장 | |
| vehicle location | 차량 위치 | |
| account / sign in / sign out | 계정 / 로그인 / 로그아웃 | |
| leaderboard | 리더보드 | |
| achievement | 업적 | |
| privacy | 개인정보 보호 | |
| diagnostics | 진단 정보 | |
| report a problem | 문제 신고 | |
| Details (Live View's pane) | 세부 정보 | |
| stream health | 스트림 상태 | |
| storage | 저장 공간 | |
| hotspot | 핫스팟 | openpilot says 테더링 for the setting; Android's Korean says 핫스팟 |
| Live / Delayed (Live View's state) | 실시간 / 지연 | |
| frame pacing | 프레임 페이싱 | |
| inset (a picture in the picture) | 작은 화면 | |
| framing: Fill / Exact / Extend / Auto | 채우기 / 원본 비율 / 확장 / 자동 | |
| camera framing | 카메라 구도 | |
| reduce motion | 동작 줄이기 | |
| screen edges | 화면 가장자리 | |
| View (Surround's) / chase / high / top-down | 시점 / 추적 / 높은 시점 / 위에서 보기 | |
| vehicle detection / detector / model | 차량 감지 / 감지기 / 감지 모델 | |
| renderer | 렌더러 | |
| key (an API key, an SSH key) | 키 | openpilot's SSH 키; public / private: 공개 키 / 개인 키 |
| dashboard (a service's) | 대시보드 | |
| reroute | 경로 재탐색 | |
| Where to? | 어디로 갈까요? | |
| map source | 지도 출처 | |
| Powered by | 제공: | |
| steering / speed active, manual (the HUD's control line) | 조향 작동 중 / 속도 작동 중 / 수동 | review on a drive |
| steering only / speed only | 조향만 / 속도만 | |
| blind spot | 사각지대 | |
| green light / lead car moving | 녹색 신호 / 앞차 출발 | |
| safe update / install / repair | 안전 업데이트 / 안전 설치 / 안전 복구 | |
| overlays (drawn on video) | 오버레이 | not overlay packs (오버레이 팩) |
| telemetry | 텔레메트리 | |
| patch | 패치 | |
| in Park | P단 | "P단에 두세요" |
| power harness | 상시 전원 하네스 | |
| guided / manual setup | 안내 설정 / 수동 설정 | |
| boot hook / runtime hook | 부팅 훅 / 런타임 훅 | |
| vehicle security key | 차량 보안 키 | |
| pair code / invitation | 페어링 코드 / 초대 코드 | |
| phones with a key | 키가 있는 휴대폰 | |
| shared token | 공유 토큰 | |
| development runtime | 개발용 런타임 | |
| controller | 컨트롤러 | |
| best effort | 제한 지원 | works, without a promise; review |
| video only | 영상 전용 | |
| widgets | 위젯 | |
| backup / restore | 백업 / 복원 | |
| read-only | 읽기 전용 | |
| head unit | 헤드 유닛 | |
| nearby devices | 근처 기기 | Android's permission |
| display over other apps | 다른 앱 위에 표시 | Android's permission |
| set aside (saved lists) | 따로 보관 | |
| Not now / Review | 나중에 / 검토 | openpilot's REVIEW is 검토 |
| queue | 대기열 | |
| Needs processing | 처리 필요 | |
| pull drives | 주행 가져오기 | |
| whole drive | 전체 주행 | |
| export | 내보내기 | |
| pack studio | 팩 스튜디오 | |
| clip | 클립 | |
| log excerpt | 로그 발췌 | |
| support bundle | 지원 번들 | |
| Driving insights | 주행 통계 | |
| contribute | 기여 | |
| route / segment (openpilot's) | 경로 / 세그먼트 | |
| Privacy & sharing | 개인정보 및 공유 | the Settings page |
| stream key | 스트림 키 | |
| destination (Go live's) | 방송 대상 | |
| Go live | 라이브 시작 | |
| YouTube Studio | YouTube 스튜디오 | YouTube's Korean |
| Auto-start | 자동 시작 | |
| Public / Unlisted / Private | 공개 / 일부 공개 / 비공개 | YouTube's |
| input (microphone) | 입력 | |
| car hands-free | 차량 핸즈프리 | |
| metered / monthly limit | 종량제 / 월 한도 | openpilot's 종량제 |
| Your requests | 내 요청 | |
| Open / Closed (a request) | 처리 중 / 종료됨 | |
| license | 라이선스 | |
| map library | 지도 보관함 | |
| map theme | 지도 테마 | |
| spoken guidance | 음성 안내 | |
| dev build | 개발 빌드 | |
| access pass | 이용권 | the account's |
| waitlist | 대기자 명단 | |
| beta member / admin | Beta 회원 / 관리자 | |
| display name / public name | 표시 이름 / 공개 이름 | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | 이번 주 / 지난주 / 누적 | |
| finalized (a week) | 확정됨 | |
| badge / share card | 배지 / 공유 카드 | |
| Official / Community (packs) | 공식 / 커뮤니티 | |
| reviewed by CommaView / unreviewed | CommaView 검토 완료 / 검토 전 | |
| Update ready | 업데이트 준비됨 | |
| training collection | 학습 데이터 모음 | openpilot's 학습 데이터 |
| recording metadata | 녹화 메타데이터 | |
| SSH identity (a comma's host key) | SSH 신원 | |
| keystore | 키 저장소 | Android's |
| repository (a fork's) | 저장소 | |
| driving software | 주행 소프트웨어 | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | 원래대로 되돌림 | |
