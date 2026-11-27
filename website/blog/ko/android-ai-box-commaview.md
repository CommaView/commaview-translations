---
title: "CommaView에 알맞은 Android AI 박스: 오디오를 바꾸지 않고"
description: "순정 CarPlay나 Android Auto 화면에서 CommaView의 Live View를 띄울 수 있는 Android AI 박스는 무엇인지, 오디오를 바꾸지 않고 고르는 법과 피해야 할 것."
date: 2026-11-16
slug: android-ai-box-commaview
tags:
  - CommaView
  - Android AI box
  - CarPlay
  - Android Auto
  - head unit
heroLabel: "구매 가이드"
draft: false
---

차에 순정 **유선** CarPlay나 Android Auto가 있다면, **Android AI 박스**로 CommaView의 Live View를 차량 자체 화면에 띄울 수 있습니다. 새 오디오도 배선 작업도 필요 없습니다. 박스는 작은 Android 컴퓨터로, 휴대폰을 꽂는 USB 포트에 꽂습니다. 차는 이것을 CarPlay나 Android Auto를 실행하는 휴대폰으로 여기고, 박스의 Android 화면 전체를 보여 줍니다. CommaView는 다른 Android 기기처럼 박스에 설치되고, comma와 페어링해 운전하는 동안 박스에서 실행됩니다.

간단히 말해 대부분의 사람에게는 RAM 8 GB의 **Carlinkit TBox Plus**나 **TBox Ambient**, 또는 **Ottocast P3 Pro**를 권합니다. 가장 빠른 박스는 **Carlinkit TBox Ultra**입니다. 예산이 빠듯하다면, 차에 유선 CarPlay가 있으면 **Ottocast P3 Lite**, Android Auto만 있으면 **Carlinkit TBox Mini S**입니다. 이미 애프터마켓 Android 오디오가 있나요? 그 자체로 CommaView를 실행할 수 있습니다. [Android 헤드 유닛](#이미-android-헤드-유닛이-있나요)을 참고하세요. 폐쇄형 시스템의 “동영상” 어댑터, 단순 무선 CarPlay 어댑터, 휴대용 CarPlay 화면은 피하세요. CommaView를 설치할 수 없습니다.

이 가이드는 2026년 11월 기준으로 CommaView가 박스에 요구하는 것을 다룹니다. CommaView 팀은 아직 AI 박스로 주행해 보지 않았으므로, 아래의 어느 것도 [테스트한 하드웨어](/ko/guides/car-screens#테스트한-하드웨어) 목록에 없습니다. 제조사가 공개한 정보를 CommaView가 실행되는 기기에 요구하는 조건과 맞춰 본 것입니다. 직접 CommaView를 실행해 보셨다면 [결과를 알려 주세요](/ko/guides/car-screens#차량-화면에-대해-알려-주세요).

## 휴대폰의 CarPlay나 Android Auto를 쓰면 안 되나요?

CommaView는 CarPlay나 Android Auto 앱이 아니며, 이 플랫폼들은 차가 움직이는 동안 휴대폰 앱이 영상을 보여 주지 못하게 합니다. Apple과 Google이 일부 차량에 동영상을 추가하고 있지만 주차 중에만 됩니다. CarPlay를 통해 휴대폰 화면을 미러링하는 어댑터도 지원하지 않습니다.

AI 박스는 휴대폰이 아니기 때문에 이 제한을 피해 갑니다. 박스는 그 자체로 Android 기기이고, 차는 CarPlay를 보여 주듯 박스의 화면을 보여 줍니다. CommaView가 박스에서 실행되므로 휴대폰은 통화와 지도에 쓸 수 있습니다.

<figure class="post-diagram">
<svg viewBox="0 0 600 196" role="img" aria-labelledby="ai-box-diagram-title" style="display:block;width:100%;height:auto;font-family:var(--font)"><title id="ai-box-diagram-title">comma가 Wi-Fi로 CommaView를 실행하는 AI 박스에 Live View를 보냅니다. 박스는 휴대폰이 CarPlay나 Android Auto로 하듯이 화면 전체를 차량의 USB 포트를 통해 차량 화면으로 보냅니다.</title><rect x="0" y="46" width="150" height="104" rx="18" style="fill:var(--card-top);stroke:var(--quiet-line);stroke-width:2"/><text x="75" y="94" text-anchor="middle" style="fill:var(--text);font-size:24px;font-weight:700">comma</text><text x="75" y="124" text-anchor="middle" style="fill:var(--text-secondary);font-size:18px;font-weight:500">3X 또는 four</text><line x1="158" y1="98" x2="212" y2="98" style="stroke:var(--brand);stroke-width:3"/><path d="M210 90 L222 98 L210 106 Z" style="fill:var(--brand)"/><text x="189" y="80" text-anchor="middle" style="fill:var(--live-text);font-size:18px;font-weight:600">Wi‑Fi</text><rect x="225" y="46" width="150" height="104" rx="18" style="fill:var(--card-top);stroke:var(--live-line);stroke-width:2"/><text x="300" y="94" text-anchor="middle" style="fill:var(--text);font-size:24px;font-weight:700">AI 박스</text><text x="300" y="124" text-anchor="middle" style="fill:var(--text-secondary);font-size:18px;font-weight:500">CommaView 실행</text><line x1="383" y1="98" x2="437" y2="98" style="stroke:var(--brand);stroke-width:3"/><path d="M435 90 L447 98 L435 106 Z" style="fill:var(--brand)"/><text x="414" y="80" text-anchor="middle" style="fill:var(--live-text);font-size:18px;font-weight:600">USB</text><rect x="450" y="46" width="150" height="104" rx="18" style="fill:var(--card-top);stroke:var(--quiet-line);stroke-width:2"/><text x="525" y="94" text-anchor="middle" style="fill:var(--text);font-size:24px;font-weight:700">차량 화면</text><text x="525" y="124" text-anchor="middle" style="fill:var(--text-secondary);font-size:18px;font-weight:500">박스 화면 표시</text><text x="300" y="186" text-anchor="middle" style="fill:var(--text-caption);font-size:17px;font-weight:500">휴대폰은 끼지 않으므로 통화와 지도에 쓸 수 있습니다.</text></svg>
<figcaption>Live View는 comma에서 Wi‑Fi로 박스에 전달됩니다. 박스는 휴대폰이 CarPlay를 보내듯 USB 포트를 통해 화면을 차로 보냅니다.</figcaption>
</figure>

## 네 가지 “CarPlay 어댑터”와 골라야 할 것

매장에서는 전혀 다른 네 가지 제품을 같은 이름으로 팝니다. CommaView가 실행되는 것은 하나뿐입니다.

| 종류 | 하는 일 | CommaView 실행? |
| --- | --- | --- |
| **Android AI 박스**(Carlinkit TBox, Ottocast P3) | 차량 화면에서 완전한 Android가 실행되며, 휴대폰처럼 앱을 설치 | **예** |
| **폐쇄형 “동영상” 박스**(Ottocast Play2Video) | 잠긴 시스템에 몇 가지 스트리밍 앱이 내장 | 아니요 |
| **무선 어댑터**(대부분의 저가 동글) | 유선 CarPlay나 Android Auto를 무선으로 바꿈. 자체 Android 없음 | 아니요 |
| **휴대용 CarPlay 화면** | 휴대폰 CarPlay용 별도 화면. 내부가 Android가 아닌 경우가 많음 | 아니요 |

## CommaView가 박스에 요구하는 것

사기 전에 아래 항목을 하나씩 확인하세요. 하나라도 빠지면 CommaView가 실행되지 않거나 잘 실행되지 않습니다.

1. **차량의 프로토콜.** 모든 AI 박스에는 데이터를 전달하는 USB 포트를 통한 순정 **유선** CarPlay나 유선 Android Auto가 필요합니다. 유선 CarPlay만 받는 박스도 있으니, 차에 있는 것을 박스가 지원하는지 확인하세요. 무선 CarPlay만 있는 차(일부 BMW)에는 전용 모델이 필요하고, Tesla에는 CarPlay가 아예 없습니다.
2. **직접 앱을 설치할 수 있는 진짜 Android.** CommaView에는 Android 8 이상이 필요하며, 여기 소개하는 박스는 모두 Android 12나 13에서 실행됩니다. 더 중요한 것은 앱을 설치할 수 있느냐입니다. Google Play에서든, 내려받은 파일에서든 상관없습니다. CommaView 베타는 Google Play가 아니라 my.commaview.com에서 설치하므로, 박스의 브라우저나 파일 관리자로 앱을 설치할 수 있어야 합니다. 폐쇄형 시스템에 정해진 앱만 있는 박스로는 할 수 없습니다.
3. **comma와 같은 네트워크의 Wi‑Fi.** Live View는 인터넷이 아니라 로컬 네트워크로 comma에서 박스로 바로 갑니다. 둘 다 연결된 네트워크라면 어느 것이든 됩니다. 박스 자체의 핫스팟에 comma를 연결하거나(SIM 카드가 있는 박스는 대개 공유할 수 있습니다), 휴대폰 핫스팟에 둘 다 연결하거나, comma의 핫스팟에 박스를 연결하면 됩니다. 대부분의 박스는 무선 CarPlay용으로 휴대폰을 연결할 때도 Wi‑Fi를 쓰며, 그동안 Wi‑Fi 인터넷이 끊기는 박스도 있습니다. CommaView는 휴대폰의 CarPlay를 중계하는 상태가 아니라 박스의 Android 모드에서 실행하세요.
4. **comma의 영상을 재생하는 영상 디코더.** comma는 도로 카메라를 1928 × 1208 HEVC(H.265)로 보냅니다. 최근 몇 년 사이의 휴대폰은 이를 하드웨어로 재생하며, 저희가 권하는 박스의 Qualcomm 칩(Snapdragon 662, 665/6125, 6225/680, 690급)은 휴대폰용 칩입니다. 가장 저렴한 박스는 이름을 밝히지 않는 칩을 쓰는데, 디코더가 부족하기 쉬운 곳이 바로 거기입니다. 디코더가 실패하면 CommaView가 박스의 다른 디코더를 알아서 시도합니다.
5. **충분한 메모리.** RAM은 최소 4 GB, 8 GB면 CommaView, 지도, 음악을 함께 돌릴 여유가 있습니다.

알아 두면 좋은 점이 두 가지 더 있습니다.

- **박스의 화면은 영상으로 차에 전달됩니다.** CarPlay와 Android Auto는 박스의 화면을 영상 스트림으로 차에 보내므로, Live View가 가는 길에 한 번 더 인코딩됩니다. 손에 든 휴대폰보다 약간 덜 선명하고 조금 늦다고 생각하세요. 해상도는 차가 정하며, 대개 차량 자체 화면 크기입니다.
- **일부 차량은 박스가 보내는 화면의 가장자리를 잘라 냅니다.** Android는 이를 알 수 없습니다. CommaView 0.0.166 베타에는 설정 › 디스플레이 › 화면 가장자리가 추가되어, 지정한 각 가장자리에 앱이 걸리지 않게 합니다.

## 추천 제품

### 최고의 선택: Carlinkit TBox Plus(8 GB)

**Android 13 · Qualcomm 8코어(6125 또는 6225급) · 4 GB + 64 GB 또는 8 GB + 128 GB · 유선 CarPlay와 유선 Android Auto · 4G SIM 슬롯 · 듀얼 밴드 Wi‑Fi 5**

가장 먼저 써 볼 박스는 TBox Plus입니다. 유선 CarPlay **또는** 유선 Android Auto가 있는 차에서 작동하고, Google Play가 들어 있으며, Qualcomm 칩은 휴대폰의 영상 디코더를 갖춘 휴대폰용 칩입니다. Carlinkit은 유선 CarPlay나 Android Auto를 지원하는 Alpine, Pioneer, Kenwood 애프터마켓 헤드 유닛도 호환 화면으로 꼽습니다.

- **8 GB + 128 GB 버전을 사세요.** 미국·캐나다용과 그 밖의 국가용 버전이 있습니다. 4G 모뎀이 내 통신망에서 작동하도록 운전하는 지역용을 사세요.
- **칩이 다를 수 있습니다.** Carlinkit 자체 페이지에 6125와 6225가 모두 나옵니다. 둘 다 CommaView에 충분하며, 6225가 더 새로운 칩입니다.
- **4G 슬롯은 CommaView에 필수가 아닙니다.** Live View에는 인터넷이 필요 없지만, CommaView 베타는 가끔 인터넷으로 이용권을 갱신하므로 SIM이 있으면 운전 중에도 갱신할 수 있습니다.

### 이것도 훌륭합니다: Carlinkit TBox Ambient

**Android 13 · Qualcomm QCM6225(Snapdragon 680급) · 4 + 64, 6 + 128, 8 + 128 GB · 유선 CarPlay와 유선 Android Auto · 4G SIM 슬롯 · 듀얼 밴드 Wi‑Fi 5**

Ambient는 TBox Plus에 더 새로운 칩과 LED 조명 링을 더하고 메모리 선택지를 늘린 제품입니다. CommaView에게는 같은 박스입니다. TBox Plus와 같은 가격에 찾았다면 이쪽을 고르고, 어느 쪽이든 8 GB 버전을 사세요. Carlinkit은 예전 6125와 660 칩 버전도 언급하므로, 판매 페이지에 6225라고 적혀 있는지 확인하세요.

### 가장 강력한 제품: Carlinkit TBox Ultra

**Android 15 · Qualcomm SM6350(Snapdragon 690급) · 8 GB + 128 또는 256 GB · 유선 CarPlay와 유선 Android Auto · 4G SIM 슬롯**

Ultra는 Carlinkit에서 가장 빠른 박스입니다. TBox Plus와 Ambient보다 빠른 칩을 쓰고, 여기 소개한 박스 중 가장 새로운 Android에서 실행됩니다. 리뷰에서는 1080p와 4K 스트리밍이 매끄럽다고 하므로, Live View 옆에 지도와 음악을 띄울 여유가 가장 많습니다. 가격은 가장 비싸서 정가 약 329달러이며, 할인으로 더 싸게 파는 경우가 많습니다. 이후 생산분은 같은 칩으로 Ultra 2, Ultra 3라는 이름으로 팝니다. Carlinkit은 BMW를 지원하지 않는다고 밝힙니다. 판매 페이지에는 앱 스토어가 있다고 하지만 Google Play라고는 하지 않으니, 믿고 쓰기 전에 받은 박스가 파일로 앱을 설치할 수 있는지 확인하세요.

### 최고의 Ottocast: Ottocast P3 Pro

**Android 13 · Snapdragon 6225 · 8 GB + 128 GB · 유선 CarPlay 또는 유선 Android Auto(스위치로 전환) · CloudSIM · HDMI 출력**

Ottocast의 플래그십으로, TBox Ambient와 같은 급의 칩과 메모리를 갖췄습니다. 뒷면에 CP/AA 스위치가 있어 유선 프로토콜을 하나만 지원하는 차에도 맞고, 두 번째 화면용 HDMI 출력도 있습니다. Ottocast는 Sony 애프터마켓 헤드 유닛을 지원하지 않는다고 밝힙니다. 제품 페이지에는 원하는 앱을 무엇이든 내려받을 수 있다고 하지만 방법은 적혀 있지 않으니, 믿고 쓰기 전에 받은 박스가 파일로 앱을 설치할 수 있는지 확인하세요.

### 저예산, 유선 CarPlay 전용: Ottocast P3 Lite

**Android 12 · Snapdragon 665 · 4 GB + 64 GB · 유선 CarPlay 전용 · Google Play**

CommaView를 올린다면 이것이 최소한입니다. Snapdragon 665는 예전 휴대폰용 칩이고, RAM 4 GB는 CommaView 하나만 돌리기에는 충분합니다. **순정 유선 CarPlay에서만** 작동합니다. Android Auto만 있는 차, BMW(Ottocast는 BMW용 버전을 팝니다), Sony 애프터마켓 헤드 유닛에서는 쓸 수 없습니다.

### 저예산, Android Auto 지원: Carlinkit TBox Mini S 또는 TBox S2C

**Android 13 · Qualcomm SM6115(Snapdragon 662) · 4 GB + 64 GB(일부 S2C는 8 GB) · 유선 CarPlay와 유선 Android Auto**

Carlinkit의 저렴한 박스는 Snapdragon 662를 씁니다. P3 Lite의 665보다 조금 오래되었지만 Android 13에서 실행되고 CarPlay뿐 아니라 유선 Android Auto도 받으므로, Android Auto만 있는 차에 어울립니다. Qualcomm은 662가 디코딩할 수 있는 최대 영상 크기를 공개하지 않으며, comma의 1928 × 1208은 1080p보다 조금 큽니다. 반품할 수 있는 곳에서 사고, 믿고 쓰기 전에 Live View가 재생되는지 확인하세요.

### 무선 CarPlay만 있는 BMW: Ottocast i3

iDrive 7 이후의 많은 BMW에는 무선 CarPlay만 있어 일반 AI 박스를 쓸 수 없습니다. Ottocast는 이런 차를 위해 Android 13 기반의 **i3**를 만듭니다. 다른 박스에 비해 무엇을 설치할 수 있는지는 잘 알지 못합니다. 이 박스에서 CommaView를 써 보셨다면 결과를 듣고 싶습니다.

### Rivian과 GM 전기차: EV Play Max

Rivian과 GM의 최신 전기차에는 CarPlay도 Android Auto도 없으므로 어떤 AI 박스도 작동하지 않습니다. Amprocity의 **EV Play Max**는 이런 차를 위해 만든 Android 컴퓨터로, 차량 자체 디스플레이에 화면을 보여 주고 Google Play도 있습니다. 꽂기만 하면 되는 제품은 아닙니다. Rivian에 장착하는 데 1시간쯤 걸리고, 제조사는 GM이 막을 수도 있다고 말합니다. 칩이 공개되지 않아 comma의 영상을 재생할 수 있는지 알 수 없고, 써 봤다는 사람도 아직 없습니다. 더 저렴한 **EV Play LT**는 휴대폰의 CarPlay나 Android Auto를 차로 가져올 뿐이며 CommaView를 실행할 수 없습니다. 먼저 openpilot이 내 차를 지원하는지 확인하세요.

### Tesla

Tesla에는 CarPlay도 Android Auto도 없으므로 어떤 AI 박스도 작동하지 않습니다. 하지만 웹 브라우저가 있고, 0.0.166 베타에 새로 생긴 CommaView의 **Browser View**가 휴대폰이 핫스팟으로 보내는 Live View를 그 브라우저에 띄웁니다. 설정 방법은 [Browser View 가이드](/ko/guides/browser-view)에 있습니다. 시야를 가리지 않는 거치대에 단 Android 휴대폰이나 태블릿도 괜찮습니다.

## 한눈에 보기

| 박스 | Android | 칩 | RAM | 유선 CarPlay | 유선 Android Auto | 앱 설치 |
| --- | --- | --- | --- | --- | --- | --- |
| Carlinkit TBox Plus | 13 | Qualcomm 6125 / 6225 | 4 또는 8 GB | 예 | 예 | Google Play |
| Carlinkit TBox Ambient | 13 | Qualcomm 6225 | 4, 6, 8 GB | 예 | 예 | 예, 버전 확인 |
| Carlinkit TBox Ultra | 15 | Qualcomm SM6350(690급) | 8 GB | 예 | 예 | 예, 방법 확인 |
| Ottocast P3 Pro | 13 | Snapdragon 6225 | 8 GB | 예 | 예(스위치) | 예, 방법 확인 |
| Ottocast P3 Lite | 12 | Snapdragon 665 | 4 GB | 예 | 아니요 | Google Play |
| Carlinkit TBox Mini S / S2C | 13 | Snapdragon 662 | 4 GB(일부 S2C 8 GB) | 예 | 예 | 예 |

2026년 11월에 제조사가 공개한 정보입니다. 제조사는 같은 이름으로 생산분마다 칩과 메모리를 바꾸므로, 사려는 제품의 판매 페이지를 확인하세요.

## 이미 Android 헤드 유닛이 있나요?

차에 애프터마켓 Android 오디오(헤드 유닛)가 있다면 그 자체로 CommaView를 실행합니다. 박스가 필요 없고, 영상이 CarPlay를 거쳐 화면에 가지도 않습니다. CommaView 팀은 두 대로 주행하며, [테스트한 하드웨어](/ko/guides/car-screens#테스트한-하드웨어) 목록에 있습니다. 회원들은 훨씬 많은 기종에서 CommaView를 씁니다. 박스와 마찬가지로 확인할 것은 칩이며, 헤드 유닛 설정의 기기 정보나 판매 페이지에서 알 수 있습니다.

<figure class="post-figure">
<img src="/product/app-car-live-view-433b29dde4.webp" width="2112" height="1080" loading="lazy" decoding="async" alt="실제 주행 중 넓은 차량 화면을 가득 채운 CommaView의 Live View: 운전석 쪽의 조작 버튼 레일, 차선 안에 청록색으로 그린 경로, 거리와 함께 상자로 표시한 앞차, 속도 클러스터.">
<figcaption>실제 주행 중 대시보드의 넓은 화면에 띄운 Live View. 헤드 유닛은 바로 보여 주고, AI 박스를 거치면 차량 화면에 같은 영상이 약간 덜 선명하게 나옵니다.</figcaption>
</figure>

흔히 보이는 칩을 안전한 순서로 꼽으면 다음과 같습니다.

- **Qualcomm**(Snapdragon 662, 665 또는 QCM6125, QCM6490): 휴대폰용 칩으로 가장 안전한 선택입니다. Joying, Dasaita, Teyes의 Qualcomm 제품과 특정 차종에 맞춰 만든 많은 화면이 이 칩을 씁니다. 1920 × 720 화면의 Qualcomm 제품에서 Live View가 comma의 최대 초당 20프레임으로 재생되었다는 보고가 있습니다.
- **Unisoc UIS7870**: Mekede M7 Plus와 Junsun V3 같은 2025~26년 제품의 빠른 칩입니다. 디코더 사양이 comma의 영상보다 훨씬 높습니다.
- **MediaTek MT8667**: Junsun V2 Plus와 특정 차종의 화면을 대체하는 10.25인치, 12.3인치 와이드 화면 등에 쓰입니다. 이 칩의 제품에서 Live View가 초당 20프레임으로 재생되었다는 보고가 있습니다.
- **Unisoc UIS7862**(TS10과 그 밖의 많은 FYT, TopWay 제품): 저렴한 헤드 유닛에서 가장 흔한 칩입니다. comma의 영상이 이 디코더의 사양 한계에 가까우니, 믿고 쓰기 전에 Live View가 재생되는지 확인하세요.

많은 헤드 유닛이 실제보다 새로운 Android를 쓴다고 표시합니다. CommaView에는 Android 8 이상이 필요하며, 위의 제품은 모두 충족합니다. comma와 같은 네트워크에 연결하는 방법은 [차량 화면](/ko/guides/car-screens) 가이드에서 설명합니다.

## 피해야 할 것

- Ottocast의 Play2Video Pro와 Ultra 같은 **폐쇄형 “동영상” 박스**. 잠긴 Android에서 짧은 앱 목록으로 Netflix와 YouTube를 재생할 뿐이며, CommaView를 설치할 방법이 없습니다.
- **단순 무선 CarPlay와 Android Auto 어댑터.** 휴대폰의 CarPlay를 무선으로 바꿀 뿐입니다. CommaView를 실행할 Android가 없습니다.
- 휴대폰 화면을 CarPlay로 복사하는 **화면 미러링 어댑터**. CommaView는 지원하지 않습니다.
- 대시보드에 붙이는 **휴대용 CarPlay 화면**. 내부가 Android가 아닌 경우가 많고, Android인 것도 휴대폰의 CarPlay를 실행할 뿐 자체 앱은 돌리지 않습니다. 거치대에 단 Android 태블릿이 더 낫습니다.
- Carlinkit의 초기 AI 박스나 그 복제품 같은 **Snapdragon 450을 쓰는 Android 9의 오래된 AI 박스**. 사용자들은 느리다고 하며, 디코더 사양이 1080p라 comma의 영상에 못 미칩니다. 지금도 재고품이 싸게 팔립니다.
- **RAM 2 GB의 박스, 또는 판매 페이지가 칩 이름을 밝히지 않는 박스.** Android는 돌아가도 comma의 영상을 매끄럽게 재생하지 못할 수 있습니다.

## 설정하기

모두 주차한 상태에서 하세요. 모든 단계는 [차량 화면](/ko/guides/car-screens) 가이드에 있습니다.

1. **차의 CarPlay나 Android Auto용 USB 포트에 박스를 꽂고** 부팅되기를 기다리세요. 우선 인터넷이 되는 Wi‑Fi에 연결하세요.
2. **CommaView를 설치하세요.** 박스의 브라우저에서 초대받은 이메일로 my.commaview.com에 로그인하고 Get the app에서 CommaView를 내려받으세요. 이번 설치에만 브라우저의 설치를 허용하고, 끝나면 다시 끄세요.
3. **박스와 comma를 같은 네트워크에 연결하세요.** 박스의 핫스팟을 켜고 comma를 연결하거나, 둘 다 휴대폰 핫스팟에 연결하거나, comma의 핫스팟(openpilot에서는 테더링이라고 합니다)을 켜고 박스에서 연결하세요.
4. **박스를 comma와 페어링하세요.** 휴대폰에서 이미 그 comma와 CommaView를 쓰고 있다면, 휴대폰에서 comma의 장치 설정을 열고 다른 휴대폰 페어링 › 다른 휴대폰 추가 › **초대 코드 표시**를 누른 다음, 박스에서 코드를 입력하거나 QR 코드를 스캔하세요.
5. **화면에 맞추세요.** CommaView 0.0.166 이상에서는 차가 화면을 잘라 내면 화면 가장자리를 설정하고, 운전하기 전에 Live View가 재생되는지 확인하세요. 설정 › 디스플레이 › Live View 여는 중에서 박스가 켜질 때 CommaView를 열고, comma가 연결되면 바로 Live View로 들어가게 할 수 있습니다.

comma의 런타임을 업데이트할 때는 comma를 보는 다른 모든 기기처럼 박스의 CommaView를 먼저 업데이트하세요.

## 안전

박스 설정은 주차한 상태에서 하고, 그다음에는 손대지 마세요. 운전 중에 CommaView를 조작하지 마세요. openpilot이 요구하듯 눈은 도로에, 손은 핸들에 두세요. comma 자체의 경고와 차량 계기판이 우선입니다. CommaView는 comma가 보는 것을 보여 줄 뿐입니다.

## 자주 묻는 질문

**AI 박스를 쓰면 차량 보증이 무효가 되나요?** 휴대폰을 꽂는 USB 포트에 꽂을 뿐 차에는 아무것도 바꾸지 않습니다. 뽑으면 차는 원래대로입니다.

**휴대폰의 CarPlay도 계속 쓸 수 있나요?** 네. 대부분의 박스는 휴대폰의 CarPlay나 Android Auto를 무선으로 중계하며, 그것과 박스의 Android 사이를 전환해 씁니다. CommaView는 박스의 Android 모드에서 실행됩니다.

**박스에 SIM 카드가 필요한가요?** Live View에는 필요 없습니다. Live View는 comma와 박스가 함께 쓰는 로컬 네트워크로 comma에서 박스로 갑니다. 베타 기간에 CommaView는 이용권을 갱신하려고 가끔 인터넷이 필요하며, 집 Wi‑Fi, 휴대폰 핫스팟, 박스의 SIM 중 어느 것이든 됩니다.

**휴대폰과 박스가 같은 comma를 함께 볼 수 있나요?** 네. 각각을 comma와 페어링하세요. Live View는 한 번에 한 대만 쓸 수 있습니다.

**차에 Google이 내장되어 있습니다. 그걸 써도 되나요?** 아직은 안 됩니다. Google 내장 차량은 자체 Play 스토어에서만 앱을 설치하며, 거기에는 CommaView가 없습니다.
