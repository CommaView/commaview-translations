---
title: "ตรวจว่ารองรับ comma และฟอร์กของคุณ"
description: "CommaView ใช้ได้กับ openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot และ OPGM และกับฟอร์กอื่นแบบเท่าที่ทำได้"
topic: start
order: 2
kind: reference
lede: "CommaView แสดงกล้องหน้าของ comma พร้อมโอเวอร์เลย์การขับของซอฟต์แวร์ที่ comma ใช้ ใช้ได้กับ openpilot และฟอร์กเก้าตัว บน comma 3X และ comma four และกับฟอร์ก openpilot อื่นแบบเท่าที่ทำได้ การตั้งค่าจะตรวจว่า comma ใช้ฟอร์กใดก่อนเปลี่ยนแปลงอะไร"
updated: 2026-11-27
needs:
  - title: "comma 3X หรือ comma four"
    text: "ไม่รองรับ comma 3 รวมถึงบิลด์สำหรับ comma 3 ของฟอร์กต่างๆ เช่น xnor-c3 [ทำไมไม่รองรับ comma 3](/#faq-comma-3)"
  - title: "ฟอร์กของคุณ ตามที่ใช้งานอยู่"
    text: "ติดตั้งและทำงานตามปกติ CommaView เพิ่มรันไทม์ไว้ข้างๆ และไม่เปลี่ยนวิธีที่ฟอร์กขับ"
steps:
  - id: unlisted
    title: "บนฟอร์กที่ CommaView ไม่ได้ระบุไว้ การตั้งค่าจะถามคุณก่อน"
    body: |
      การตั้งค่าแบบมีคำแนะนำจะตรวจว่าซอฟต์แวร์ของ comma ติดตั้งมาจากรีโพสิทอรีใด และติดตั้งฮุกของ CommaView สำหรับฟอร์กนั้น บนฟอร์กที่ไม่ได้ระบุไว้ การตั้งค่าจะตรวจฟอร์กก่อนโดยไม่เปลี่ยนแปลงอะไร
    tabs:
      - label: "เท่าที่ทำได้"
        body: "ถ้า CommaView เพิ่มมุมมองได้ การตั้งค่าจะแสดง **CommaView ยังไม่ได้ตรวจสอบฟอร์กนี้** โดยระบุฟอร์กตามรีโพสิทอรี และบอกว่าอะไรถูกวาด (กล้อง เส้นทาง เลน รถคันหน้า การแจ้งเตือน และความเร็ว) และอะไรไม่ถูกวาด (ปุ่ม สี และวิดเจ็ตของฟอร์กเอง) **ติดตั้งต่อไป** ติดตั้งบนฟอร์กนั้นเท่านั้น **ย้อนกลับ** กลับไปเลือก comma โดยไม่ได้ติดตั้งอะไร"
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**ติดตั้งต่อไป** เพิ่มมุมมองของ CommaView ลงในฟอร์กนี้แบบเท่าที่ทำได้"
      - label: "วิดีโอเท่านั้น (ทดลองใช้ก่อน)"
        body: "สำหรับ FrogPilot และ KisaPilot ซึ่งหน้าจอรับมุมมองของ CommaView ไม่ได้ ผู้ทดสอบที่มีแฟล็กวิดีโอเท่านั้นจะเห็น **วิดีโอเท่านั้นบนฟอร์กนี้**: CommaView สตรีมกล้องและวาดมุมมองของตัวเองจากข้อมูลการขับ โดยไม่เปลี่ยนอะไรในฟอร์ก ยังไม่เคยลองบน comma จริง ถ้าไม่มีแฟล็ก การตั้งค่าจะบอกว่าไม่รองรับฟอร์กนี้และไม่เปลี่ยนแปลงอะไร"
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**ติดตั้งแบบวิดีโอเท่านั้น**"
    note: "เมื่อการตรวจปฏิเสธฟอร์ก การตั้งค่าจะแสดง “CommaView เพิ่มมุมมองของตัวเองลงใน … อย่างปลอดภัยไม่ได้” และ “ไม่มีสิ่งใดบน comma ถูกเปลี่ยนแปลง”"
  - id: details
    title: "ดูว่า Live View วาดฟอร์กใด"
    body: |
      ใน Live View เปิด **รายละเอียด** บรรทัด **ซอฟต์แวร์** ระบุฟอร์กของ comma ส่วนฟอร์กที่ CommaView ไม่ได้ระบุไว้จะแสดงตามรีโพสิทอรี เช่น “crwusiz/openpilot · best effort”
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**รายละเอียด** ใต้ภาพ"
      - text: "**ซอฟต์แวร์**: ฟอร์กที่ comma ใช้"
related: [setup, overlays, uninstall]
---

## ฟอร์กที่รองรับ

| ฟอร์ก | ที่มา | รองรับตั้งแต่ |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | Beta แรก |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | Beta แรก |
| **StarPilot** | github.com/StarPilotHQ/StarPilot เดิมคือ github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor** (บิลด์ xnor และ rx) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot ติดตั้งจาก i.carrotpilot.app | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

บนฟอร์กที่ไม่ได้ระบุไว้ การตั้งค่าจะตรวจว่า CommaView เพิ่มมุมมองได้หรือไม่และถามคุณก่อน ถ้าทำไม่ได้ การตั้งค่าจะหยุดและปล่อย comma ไว้อย่างเดิม

## แต่ละฟอร์กแสดงอะไร

### openpilot

ซอฟต์แวร์ของ comma.ai เอง Live View วาดหน้าจอของ comma four ของ comma 3X หรือโอเวอร์เลย์ของ CommaView เอง พร้อมความเร็ว สูงสุด ความเร็วจำกัด รถคันหน้า และการเปลี่ยนเลน

### sunnypilot

CommaView วาดหน้าจอของ sunnypilot พร้อมสิ่งที่ sunnypilot เพิ่มเข้ามา: สถานะพวงมาลัยเท่านั้นและความเร็วเท่านั้นของ MADS ตัวช่วยความเร็วจำกัด เส้นทางสีรุ้งและไฟแสดงจุดบอด และบนหน้าจอ comma 3X ยังมีป้ายความเร็วจำกัด smart cruise และ UI สำหรับนักพัฒนา CommaView อ่านการตั้งค่า sunnypilot ของคุณ หน้าจอจึงตรงกับของ comma

### StarPilot

StarPilot แสดงโหมดการขับด้วยสี และ CommaView ใช้สีที่ StarPilot เลือก: ขอบ เส้นทาง และวิดเจ็ตบนหน้าจอ comma four และ comma 3X การแจ้งเตือน และการเลือกกล้อง รวมถึงกล้องฝั่งคนขับ

ปิดการตั้งค่า **Disable Logging** ของ StarPilot เพราะจะหยุดตัวเข้ารหัสวิดีโอที่ Live View ใช้สตรีม

### openpilot ของ xnor-tech: xnor และ rx

openpilot ของ xnor-tech มีสองบิลด์ สาขา **xnor** ใช้หน้าจอของ openpilot และสาขา **rx** ใช้หน้าจอของ sunnypilot ทั้งสองมีการรองรับรถของ xnor-tech CommaView วาดแบบที่ comma ของคุณใช้ พร้อมการแจ้งเตือนตามที่ comma เขียน

บน Rivian ที่ใช้ rx พวงมาลัยจะเป็นสีเขียวเมื่อรถบังคับเลี้ยวด้วยมุม และสีน้ำเงินเมื่อบังคับด้วยแรงบิด: พวงมาลัยของ comma four และบนหน้าจอ comma 3X คือปุ่มโหมดทดลอง

### AdventurePilot

AdventurePilot เป็นฟอร์กของ sunnypilot ที่รองรับรถของตัวเอง CommaView วาดหน้าจอของ sunnypilot พร้อมสิ่งที่ AdventurePilot เพิ่มเข้ามา:

- ตัวแสดงการรักษาตำแหน่งกลางเลน: แถบมนแสดงแรงดันและค่าเยื้องบนหน้าจอ comma 3X และแถบขนาดเล็กบนหน้าจอ comma four
- ชิป CURVE บนหน้าจอ comma 3X ซึ่งกะพริบขณะระบบควบคุมความเร็วในทางโค้งทำงาน
- สีพวงมาลัยตามโหมดบังคับเลี้ยว และแถบแรงบิดที่แสดงความเร่งด้านข้างขณะ Rivian บังคับเลี้ยวผ่านช่องสัญญาณมุม

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 เป็นฟอร์กของ sunnypilot ที่เพิ่มการรองรับรถ Tesla HW1 (Autopilot 1) หน้าจอเป็นของ sunnypilot CommaView จึงวาดหน้าจอของ sunnypilot พร้อมทุกอย่างที่ sunnypilot เพิ่ม และแสดงชื่อฟอร์กในแอป

คำสั่ง `op fork update` ของฟอร์กนี้ย้ายฟอร์กไม่ได้ขณะติดตั้งฮุกของ CommaView อยู่: [ถอนการติดตั้งรันไทม์ของ CommaView](/th/guides/uninstall) ก่อน หรือใช้ตัวสลับฟอร์กบนหน้าจอ comma ซึ่งทำงานตามปกติ

### carrotpilot

carrotpilot เป็นฟอร์กของ openpilot สำหรับรถ Hyundai, Kia และ Genesis ติดตั้งจาก `i.carrotpilot.app` CommaView วาดหน้าจอของ openpilot ให้ พร้อมความเร็ว เส้นทาง เลน และรถคันหน้า สิ่งที่ carrotpilot เพิ่มลงในหน้าจอของตัวเอง เช่น การนำทาง กล้องตรวจจับความเร็ว และ HUD ยังไม่ถูกวาด

การอัปเดตอัตโนมัติของ carrotpilot และเครื่องมือ Git บนหน้าเว็บของมัน จะนำฮุกของ CommaView ออกจนกว่า comma จะรีบูต แอปจะขอให้รีบูต และ Live View จะกลับมาหลังรีบูต

### BluePilot, dragonpilot และ OPGM

ระบุไว้ตั้งแต่ CommaView 0.0.166 พร้อมรันไทม์ของรุ่นนั้น CommaView แสดงชื่อแต่ละฟอร์กและวาดตามหน้าตาของฟอร์กต้นทาง: BluePilot แบบ sunnypilot ส่วน dragonpilot และ OPGM แบบ openpilot โดย ALKA ของ dragonpilot แสดงเป็นการคุมพวงมาลัย comma ที่เคยใช้ฟอร์กเหล่านี้แบบเท่าที่ทำได้จะย้ายมาใช้แบบระบุไว้เมื่อบูตหลังอัปเดตรันไทม์ ยังไม่มีฟอร์กใดในนี้ที่ขับกับ CommaView จริง [แพ็กโอเวอร์เลย์](/th/guides/overlays)ทางการของ CommaView วาดหน้าจอของ BluePilot และ dragonpilot ได้มากขึ้น

## ฟอร์กที่ CommaView ไม่ได้ระบุไว้

ตั้งแต่ CommaView 0.0.165 พร้อมรันไทม์ของรุ่นนั้นบน comma การตั้งค่าเพิ่มมุมมองของ CommaView ลงในฟอร์ก openpilot ที่ไม่ได้ระบุไว้ได้แบบเท่าที่ทำได้ Live View วาดฟอร์กตามหน้าตาของ openpilot หรือของ sunnypilot เมื่อฟอร์กสร้างบนหน้าจอของ sunnypilot หากต้องการยกเลิก **ถอนการติดตั้งรันไทม์** ในการตั้งค่าอุปกรณ์จะคืนไฟล์ของฟอร์กเป็นแบบเดิม

- **เท่าที่ทำได้** รุ่นต่างๆ ของ CommaView ไม่ได้ตรวจกับฟอร์กของคุณ ถ้าฟอร์กอัปเดตตัวเองจนเป็นแบบที่ CommaView ตามไม่ทัน มุมมองของ CommaView จะปิด และฟอร์กจะขับและแสดงหน้าจอของตัวเองตามปกติ จนกว่ารุ่นใหม่ของ CommaView จะรองรับการเปลี่ยนแปลงนั้น
- **ไม่ใช่ทุกฟอร์ก** ฟอร์กที่สร้างบนหน้าจอเนทีฟรุ่นเก่าของ openpilot ไม่รองรับ (ดูด้านล่าง)
- **การตกลงของคุณใช้กับฟอร์กนั้นเท่านั้น** ถ้า comma เปลี่ยนไปใช้ฟอร์กอื่นที่ CommaView ไม่ได้ระบุไว้ CommaView จะถามอีกครั้งในการตั้งค่าก่อนเพิ่มมุมมองลงไป

### ฟอร์กที่ผ่านการตรวจการติดตั้ง (เท่าที่ทำได้)

ฟอร์กเหล่านี้ทุกตัว **ผ่านการตรวจการติดตั้งของ CommaView เท่าที่ทำได้ ยังไม่ได้ทดสอบบนรถ** ตรวจเมื่อพฤศจิกายน 2026 สำหรับสาขาที่ระบุ กับรันไทม์ที่ CommaView 0.0.165 ติดตั้ง: ตัวติดตั้งเสนอฟอร์ก เพิ่มมุมมองของ CommaView เมื่อคุณตกลง และตรวจสอบ เหมือนที่ทำบน comma ของคุณ ไม่มีรายการใดที่ลองบน comma ในรถจริง ฟอร์กอาจไม่รองรับรถทุกรุ่นบนทั้งสองอุปกรณ์ และการอัปเดตครั้งถัดไปของฟอร์กอาจเปลี่ยนผลลัพธ์

| ฟอร์ก | สาขาที่ตรวจ | อุปกรณ์ | วาดแบบ |
| --- | --- | --- | --- |
| **crwusiz** (github.com/crwusiz/openpilot) | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **Carrot ของ jixiexiaoge** (github.com/jixiexiaoge/openpilot) | Carrot | comma four, comma 3X | openpilot |
| **MoreTore** (github.com/MoreTore/openpilot) | release-mici | comma four | openpilot |
| **zoompilot** (github.com/zoompilot/zoompilot) | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato** (github.com/AlexandreSato/openpilot) | master | comma four, comma 3X | openpilot |
| **lukasloetkolben** (github.com/lukasloetkolben/openpilot) | master | comma four, comma 3X | openpilot |
| **mvl-boston** (github.com/mvl-boston/openpilot) | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub** (github.com/mouxangithub/openpilot) | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro** (github.com/programanichiro/openpilot) | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2** (github.com/infiniteCable2/openpilot) | master | comma four, comma 3X | sunnypilot |
| **herizon1054** (github.com/herizon1054/openpilot) | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot** (github.com/NotAutopilot/openpilot) | nap-release, naponsp-alpha | comma four, comma 3X | openpilot (nap-release), sunnypilot (naponsp-alpha) |

ไม่มีฟอร์กของคุณใช่ไหม? อาจยังใช้ได้: การตั้งค่าจะตรวจก่อนเปลี่ยนแปลงอะไร

### ไม่รองรับ

หน้าจอของฟอร์กเหล่านี้รับมุมมองของ CommaView ไม่ได้ การตั้งค่าจึงแจ้งและไม่เปลี่ยนแปลงอะไรบน comma:

- **FrogPilot** (github.com/FrogAi/FrogPilot) ใช้หน้าจอเนทีฟ (Qt) รุ่นเก่าของ openpilot ซึ่งไม่มีที่สำหรับมุมมองของ CommaView วิดีโอเท่านั้นเปิดให้ทดลองใช้ก่อน
- **KisaPilot** (github.com/kisapilot/openpilot) หน้าจอ Python ถูกปิด: ใช้หน้าจอเนทีฟ (Qt) รุ่นเก่าของ openpilot วิดีโอเท่านั้นเปิดให้ทดลองใช้ก่อน
- **IQ.Pilot** (github.com/IQLvbs/iqpilot) ตั้งแต่ตุลาคม 2026 ทำงานบน IQ.OS ของตัวเอง การรองรับต้องรอจนกว่า CommaView จะรองรับเป็นฟอร์กแยกต่างหาก
- **hikee9123** (github.com/hikee9123/openpilot) ใช้หน้าจอเนทีฟ (Qt) รุ่นเก่าของ openpilot

**ทดลองใช้ก่อน: วิดีโอเท่านั้นสำหรับ FrogPilot และ KisaPilot** เมื่อมีแฟล็กวิดีโอเท่านั้น การตั้งค่าจะเสนอให้เล่นกล้องของฟอร์กเหล่านี้ใน Live View พร้อมโอเวอร์เลย์ของ CommaView แทนหน้าจอของฟอร์ก โดยไม่เปลี่ยนอะไรในฟอร์ก ยังไม่เคยลองบน comma จริง ถ้าไม่มีแฟล็ก การตั้งค่าจะยังบอกว่าไม่รองรับและไม่เปลี่ยนแปลงอะไร

## อุปกรณ์ comma รุ่นใดบ้าง

comma 3X และ comma four ไม่รองรับ comma 3 รวมถึงบิลด์สำหรับ comma 3 ของฟอร์กต่างๆ เช่น xnor-c3: [ทำไมไม่รองรับ comma 3](/#faq-comma-3) แอปทำงานบนโทรศัพท์ แท็บเล็ต หรือจอในรถที่ใช้ Android

## สาขารุ่นเผยแพร่และสาขาพัฒนา

ก่อนเผยแพร่แต่ละรุ่น รันไทม์ของ CommaView จะถูกบิลด์และตรวจกับบิลด์รุ่นเผยแพร่ของฟอร์กเหล่านี้ สาขา nightly ของ openpilot และสาขา dev ของ sunnypilot จะถูกตรวจทุกวันที่มีการเปลี่ยนแปลง เพื่อเตือนล่วงหน้า สาขาพัฒนาอาจเปลี่ยนเร็วกว่า CommaView: ถ้าการเปลี่ยนแปลงทำให้ฮุกของ CommaView โหลดไม่ได้ หน้าจอและการขับของฟอร์กจะทำงานต่อตามปกติ

## ไม่มีฟอร์กของคุณในรายการ?

ลองใช้แบบเท่าที่ทำได้ และขอให้เพิ่มในรายการได้ที่บอร์ดฟีเจอร์ใน [my.commaview.com](https://my.commaview.com) หรือส่งไอเดียจากแอป (การตั้งค่า › **การสนับสนุนและการวินิจฉัย**) ฟอร์กที่ระบุไว้จะถูกตรวจก่อนเผยแพร่ทุกรุ่น ดู[มีอะไรใหม่](/whats-new)ในแต่ละรุ่น

## คำถาม

**CommaView เปลี่ยนวิธีที่ฟอร์กของฉันขับหรือไม่?** ไม่ CommaView เพิ่มรันไทม์ขนาดเล็กไว้ข้างฟอร์กและฮุกขนาดเล็กใน UI บนหน้าจอ เพื่อให้วาดเส้นทาง เลน และการแจ้งเตือนแบบเดียวกันได้ วิธีที่รถของคุณขับไม่เปลี่ยน

**CommaView ใช้กับ StarPilot ได้ไหม?** ได้ ตั้งแต่ CommaView 0.0.162 Live View แสดงสี วิดเจ็ต และการเลือกกล้องของ StarPilot เอง ปิดการตั้งค่า **Disable Logging** ของ StarPilot ซึ่งหยุดตัวเข้ารหัสวิดีโอที่ CommaView ใช้สตรีม

**CommaView ใช้กับ carrotpilot ได้ไหม?** ได้ ตั้งแต่ CommaView 0.0.164 Live View วาดหน้าจอของ openpilot ให้ สิ่งที่ carrotpilot เพิ่มลงในหน้าจอของตัวเอง เช่น การนำทางและกล้องตรวจจับความเร็ว ยังไม่ถูกวาด หลัง carrotpilot อัปเดตตัวเอง แอปจะขอให้รีบูตเพื่อให้ Live View กลับมา

**CommaView ใช้กับ FrogPilot ได้ไหม?** ยังไม่ได้: FrogPilot ใช้หน้าจอเนทีฟ (Qt) รุ่นเก่าของ openpilot ซึ่งไม่มีที่สำหรับมุมมองของ CommaView การตั้งค่าจึงบอกว่าไม่รองรับและไม่เปลี่ยนแปลงอะไร วิดีโอเท่านั้นเปิดให้ผู้ทดสอบ FrogPilot และ KisaPilot ทดลองใช้ก่อน
