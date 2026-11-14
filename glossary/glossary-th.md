# ไทย (Thai) glossary

The words every Thai string uses for CommaView's terms, so screens translated apart say the same thing. Where
openpilot already translates a term, its word is used, so the app says what the car's screen says. openpilot's
`selfdrive/ui/translations/app_th.po` has no Thai yet (every `msgstr` is empty, master's file is gone and the release
tags carry it empty), so the words come from its older Qt translation, `main_th.ts` (v0.9.9). Machine drafted; a
native speaker's review is owed before release (the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`). openpilot's Thai writes
km/h as กม./ชม.; CommaView keeps the Latin units, as its other languages do, since they come from shared code.

## Style

- Polite, neutral UI Thai, as openpilot's Thai and Android's Thai write it. No ครับ / ค่ะ. Requests start with
  กรุณา only where openpilot would ("กรุณาเชื่อมต่อ Wi‑Fi"); most instructions are a plain verb ("แตะ…", "เปิด…").
  The person is addressed as คุณ only where a sentence needs it ("บัญชีของคุณ"), otherwise left out.
- Questions are asked as openpilot does: "คุณแน่ใจหรือไม่ว่าต้องการ…?" for confirmations, with a `?`.
- Spacing: Thai has no spaces between words. A space goes only between phrases and sentences (where English would
  put a comma or full stop), and around Latin words, names, numbers and placeholders ("เชื่อมต่อ comma แล้ว",
  "เหลือ 25.7 GB", "%1$s นาที"). Android breaks Thai lines with a dictionary, so names stay separated by spaces.
- No full stop: Thai doesn't end sentences with one. Sentences in body text are separated by a single space;
  titles, buttons and pills have no end punctuation either. `:` after a label as the English has it, `?` and `!`
  kept, `…` kept as the English has it. Quotes are “ ”.
- Buttons are short verbs, as Android's Thai writes them: ยกเลิก, เสร็จสิ้น, บันทึก, ลบ, ลองอีกครั้ง,
  ดำเนินการต่อ, เปิด, ปิด, ตกลง, ยืนยัน.
- Loanwords follow openpilot and the Royal Institute's spelling where they agree: อัปเดต, ดาวน์โหลด, อัปโหลด,
  แอป, ออนไลน์ / ออฟไลน์; openpilot's คาลิเบรท and รีบูต are kept.
- Counts take Thai's word order: noun, number, classifier ("การขับขี่ 3 ครั้ง", "3 รายการ", "5 นาที"); plurals
  have only `other`.

## Terms

| English | ไทย | Note |
|---|---|---|
| Home (dock) | หน้าแรก | |
| Recordings | การบันทึก | the section and its saved drives |
| Settings | การตั้งค่า | openpilot's |
| recording, a recording | การบันทึก | counted as รายการ |
| drive (a trip the comma recorded) | การขับขี่ | openpilot's (ข้อมูลการขับขี่); counted as ครั้ง |
| replay | เล่นซ้ำ | |
| live copy | สำเนาสด | |
| saved moment | ช่วงที่บันทึกไว้ | |
| Record | บันทึก | the rail's button; Save is บันทึก too, as on Android |
| Go live / live streaming | ถ่ายทอดสด | YouTube's Thai |
| onroad screen | หน้าจอขณะขับ | |
| onroad / offroad (the comma's state) | กำลังขับ / จอดอยู่ | |
| design (an onroad screen's look) | ดีไซน์ | |
| overlay pack | แพ็กโอเวอร์เลย์ | |
| fork | ฟอร์ก | openpilot's own jargon, transliterated |
| runtime (commaviewd) | รันไทม์ | |
| update / install / uninstall | อัปเดต / ติดตั้ง / ถอนการติดตั้ง | openpilot's |
| reboot | รีบูต | openpilot's |
| power off | ปิดเครื่อง | openpilot's |
| pair / pairing | จับคู่ / การจับคู่ | openpilot's |
| device (the comma) | อุปกรณ์ | openpilot's |
| this phone / this device (the device CommaView runs on) | โทรศัพท์เครื่องนี้ / อุปกรณ์เครื่องนี้ | openpilot says โทรศัพท์; `common_this_phone` / `common_this_device`, a sentence's placeholder (how-to-localize.md, "This phone or this device"); both take the classifier เครื่อง, so either reads in any sentence. The placeholder holds Thai words, so no space around it ("บันทึกไว้ใน%1$s") |
| your phone / your device (`common_your_*`) | โทรศัพท์ของคุณ / อุปกรณ์ของคุณ | no space around the placeholder |
| connected / disconnected | เชื่อมต่อแล้ว / ไม่ได้เชื่อมต่อ | |
| offline | ออฟไลน์ | openpilot's |
| engaged / disengaged | เข้าควบคุม / ยกเลิกระบบช่วยขับ | openpilot's (เข้าควบคุมอยู่, ยกเลิกระบบช่วยขับ) |
| override | ผู้ขับควบคุมเอง | |
| experimental mode | โหมดทดลอง | openpilot's |
| driver monitoring | การเฝ้าระวังผู้ขับขี่ | openpilot's |
| driver camera | กล้องฝั่งคนขับ | openpilot's |
| road camera / wide camera | กล้องหน้า / กล้องมุมกว้าง | openpilot's กล้องมุมกว้าง |
| lead car | รถคันหน้า | openpilot's |
| speed limit | ความเร็วจำกัด | |
| set speed / MAX | ความเร็วที่ตั้งไว้ / สูงสุด | openpilot's MAX is สูงสุด |
| lane change | เปลี่ยนเลน | |
| calibration | การคาลิเบรท | openpilot's |
| driver position (left/right-hand drive) | ตำแหน่งคนขับ (พวงมาลัยซ้าย / พวงมาลัยขวา) | |
| daylight contrast | คอนทราสต์กลางวัน | |
| offline maps | แผนที่ออฟไลน์ | |
| navigation | การนำทาง | |
| Home / Work (places) | บ้าน / ที่ทำงาน | |
| vehicle location | ตำแหน่งรถ | openpilot says รถยนต์ |
| account / sign in / sign out | บัญชี / ลงชื่อเข้าใช้ / ออกจากระบบ | openpilot's บัญชี |
| leaderboard | ตารางอันดับ | |
| achievement | ความสำเร็จ | |
| privacy | ความเป็นส่วนตัว | |
| diagnostics | ข้อมูลวินิจฉัย | |
| report a problem | รายงานปัญหา | |
| Details (Live View's pane) | รายละเอียด | |
| stream health | สถานะสตรีม | |
| storage | พื้นที่เก็บข้อมูล | Android's |
| hotspot | ฮอตสปอต | openpilot's |
| Live / Delayed (Live View's state) | สด / ล่าช้า | |
| frame pacing | จังหวะเฟรม | |
| inset (a picture in the picture) | ภาพซ้อน | |
| framing: Fill / Exact / Extend / Auto | เต็มจอ / ตามจริง / ขยาย / อัตโนมัติ | |
| camera framing | การจัดเฟรมกล้อง | |
| reduce motion | ลดการเคลื่อนไหว | |
| screen edges | ขอบจอ | |
| View (Surround's) / chase / high / top-down | มุมมอง / ตามหลัง / มุมสูง / มุมบน | |
| vehicle detection / detector / model | การตรวจจับรถ / ตัวตรวจจับ / โมเดลตรวจจับ | |
| renderer | ตัวเรนเดอร์ | |
| key (an API key, an SSH key) | คีย์ | openpilot's คีย์ SSH; public / private: คีย์สาธารณะ / คีย์ส่วนตัว |
| dashboard (a service's) | แดชบอร์ด | |
| reroute | คำนวณเส้นทางใหม่ | |
| Where to? | ไปที่ไหน? | |
| map source | แหล่งแผนที่ | |
| Powered by | ให้บริการโดย | |
| steering / speed active, manual (the HUD's control line) | คุมพวงมาลัย / คุมความเร็ว / ขับเอง | review on a drive |
| steering only / speed only | พวงมาลัยเท่านั้น / ความเร็วเท่านั้น | |
| blind spot | จุดบอด | |
| green light / lead car moving | ไฟเขียว / รถคันหน้าออกตัว | |
| safe update / install / repair | อัปเดตอย่างปลอดภัย / ติดตั้งอย่างปลอดภัย / ซ่อมแซมอย่างปลอดภัย | |
| overlays (drawn on video) | โอเวอร์เลย์ | not overlay packs (แพ็กโอเวอร์เลย์) |
| telemetry | เทเลเมทรี | |
| patch | แพตช์ | |
| in Park | อยู่ในเกียร์ P | |
| power harness | สายไฟเลี้ยงตลอดเวลา | openpilot calls the comma's harness สายควบคุม |
| guided / manual setup | ตั้งค่าแบบมีคำแนะนำ / ตั้งค่าเอง | |
| boot hook / runtime hook | ฮุกตอนบูต / ฮุกรันไทม์ | |
| vehicle security key | คีย์ความปลอดภัยของรถ | |
| pair code / invitation | รหัสจับคู่ / คำเชิญ | |
| phones with a key | โทรศัพท์ที่มีคีย์ | |
| shared token | โทเค็นที่ใช้ร่วมกัน | |
| development runtime | รันไทม์รุ่นพัฒนา | |
| controller | คอนโทรลเลอร์ | |
| best effort | เท่าที่ทำได้ | |
| video only | วิดีโอเท่านั้น | |
| widgets | วิดเจ็ต | Android's |
| backup / restore | สำรองข้อมูล / กู้คืน | Android's |
| read-only | อ่านอย่างเดียว | |
| head unit | จอในรถ | the car's own screen |
| nearby devices | อุปกรณ์ที่อยู่ใกล้เคียง | Android's permission |
| display over other apps | แสดงทับแอปอื่น | Android's permission |
| set aside (saved lists) | พักไว้ | |
| Not now / Review | ไว้ทีหลัง / ตรวจสอบ | openpilot's REVIEW (the training guide) is ทบทวน, which reads as "study again" here |
| queue | คิว | |
| Needs processing | รอประมวลผล | |
| pull drives | ดึงการขับขี่ | |
| whole drive | ทั้งการขับขี่ | |
| export | ส่งออก | |
| pack studio | สตูดิโอแพ็ก | |
| clip | คลิป | |
| log excerpt | ส่วนของล็อก | |
| support bundle | ชุดข้อมูลสำหรับฝ่ายสนับสนุน | |
| Driving insights | ข้อมูลการขับขี่ | |
| contribute | ร่วมพัฒนา | |
| route / segment (openpilot's) | เส้นทาง / เซกเมนต์ | openpilot's เซกเมนต์ |
| Privacy & sharing | ความเป็นส่วนตัวและการแชร์ | the Settings page |
| stream key | คีย์สตรีม | YouTube's |
| destination (Go live's) | ปลายทาง | |
| Go live | เริ่มถ่ายทอดสด | |
| YouTube Studio | YouTube Studio | |
| Auto-start | เริ่มอัตโนมัติ | |
| Public / Unlisted / Private | สาธารณะ / ไม่เป็นสาธารณะ / ส่วนตัว | YouTube's |
| input (microphone) | อินพุต | |
| car hands-free | แฮนด์ฟรีในรถ | |
| metered / monthly limit | แบบจำกัดปริมาณ / ขีดจำกัดรายเดือน | openpilot's "Cellular Metered" is a sentence, not a term |
| Your requests | คำขอของคุณ | |
| Open / Closed (a request) | เปิดอยู่ / ปิดแล้ว | |
| license | สัญญาอนุญาต | |
| map library | ไลบรารีแผนที่ | |
| map theme | ธีมแผนที่ | |
| spoken guidance | คำแนะนำด้วยเสียง | |
| dev build | รุ่นพัฒนา | |
| access pass | บัตรผ่าน | the account's |
| waitlist | รายชื่อรอ | |
| beta member / admin | สมาชิก Beta / ผู้ดูแลระบบ | |
| display name / public name | ชื่อที่แสดง / ชื่อสาธารณะ | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | สัปดาห์นี้ / สัปดาห์ที่แล้ว / ตลอดกาล | |
| finalized (a week) | สรุปผลแล้ว | |
| badge / share card | เหรียญ / การ์ดแชร์ | |
| Official / Community (packs) | ทางการ / ชุมชน | |
| reviewed by CommaView / unreviewed | ตรวจสอบโดย CommaView แล้ว / ยังไม่ตรวจสอบ | |
| Update ready | พร้อมอัปเดต | |
| training collection | ชุดข้อมูลการฝึกฝน | car detection's; openpilot's ข้อมูลการฝึกฝน |
| recording metadata | เมทาดาทาของการบันทึก | |
| SSH identity (a comma's host key) | ข้อมูลระบุตัวตน SSH | |
| keystore | คีย์สโตร์ | Android's |
| repository (a fork's) | รีโพสิทอรี | |
| driving software | ซอฟต์แวร์ช่วยขับ | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | คืนค่าเดิม | |
