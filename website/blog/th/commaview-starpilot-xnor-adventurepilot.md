---
title: "CommaView ใช้ได้แล้วกับ StarPilot, xnor และ AdventurePilot"
description: "CommaView 0.0.163 เพิ่ม openpilot ของ xnor-tech และ AdventurePilot ต่อจาก StarPilot ใน 0.0.162 ฟอร์ก openpilot แต่ละตัวแสดงอะไรใน Live View บน comma 3X และ comma four"
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "บันทึกประจำรุ่น"
draft: false
---

ตอนนี้ CommaView ใช้ได้กับ openpilot ห้ารุ่น: **openpilot**, **sunnypilot**, **StarPilot**, **openpilot ของ xnor-tech** (รุ่น xnor และ rx) และ **AdventurePilot** StarPilot มาใน CommaView 0.0.162 และ Beta 0.0.163 เพิ่ม xnor และ AdventurePilot ในแต่ละตัว Live View จะวาดหน้าจอของฟอร์กนั้นเองบนโทรศัพท์ แท็บเล็ต หรือจอในรถที่ใช้ Android พร้อมสิ่งที่ฟอร์กนั้นเพิ่มเข้ามา

ก่อนหน้านี้ การตั้งค่าบนฟอร์กเหล่านี้จะหยุดพร้อมข้อความ “unsupported upstream remote” เมื่อใช้แอป 0.0.163 และรันไทม์ของมัน การตั้งค่าจะติดตั้งและจับคู่ได้เหมือนบน openpilot

## แต่ละฟอร์กแสดงอะไรใน Live View

CommaView ไม่ได้เดาจากชื่อฟอร์ก รันไทม์บน comma ของคุณบอกแอปว่าหน้าจอของฟอร์กเพิ่มอะไรเข้ามา แล้วแอปจะวาดลงบนหน้าจอแบบ comma four แบบ comma 3X หรือหน้าจอของ CommaView เอง

| ฟอร์ก | สิ่งที่ CommaView วาด |
| --- | --- |
| openpilot | หน้าจอแบบ comma four และ comma 3X หรือโอเวอร์เลย์ของ CommaView เอง |
| sunnypilot | หน้าจอของ sunnypilot: MADS ตัวช่วยความเร็วจำกัด เส้นทางสีรุ้ง ไฟเตือนจุดบอด และส่วนที่เพิ่มบน comma 3X |
| StarPilot | สี วิดเจ็ต คำเตือน และการเลือกกล้องของ StarPilot |
| xnor | หน้าจอของ openpilot บนรุ่น xnor หน้าจอของ sunnypilot บน rx และสีพวงมาลัย Rivian ของ rx |
| AdventurePilot | หน้าจอของ sunnypilot พร้อมตัวบอกการรักษากึ่งกลางเลน ชิป CURVE และสีโหมดบังคับเลี้ยว |

## StarPilot

StarPilot บอกโหมดการขับด้วยสี และ CommaView ใช้สีที่ StarPilot เลือก: ขอบจอ เส้นทาง และวิดเจ็ต คำเตือน และการเลือกกล้อง รวมถึงกล้องฝั่งคนขับ ปิดการตั้งค่า **Disable Logging** ของ StarPilot ก่อน: มันหยุดตัวเข้ารหัสวิดีโอที่ Live View ใช้สตรีม

## openpilot ของ xnor-tech: xnor และ rx

openpilot ของ xnor-tech มีสองรุ่นจากรีโพสิทอรีเดียว สาขา **xnor** ใช้หน้าจอของ openpilot และสาขา **rx** ใช้หน้าจอของ sunnypilot ทั้งคู่มีพอร์ตรถของ xnor-tech CommaView ตรวจว่า comma ของคุณใช้ตัวไหนแล้ววาดหน้าจอนั้น พร้อมคำเตือนตามที่ comma เขียน

บน Rivian ที่ใช้ rx พวงมาลัยจะบอกว่ารถกำลังบังคับเลี้ยวแบบไหน: สีเขียวเมื่อบังคับด้วยมุม สีน้ำเงินเมื่อบังคับด้วยแรงบิด CommaView วาดสีเดียวกันบนพวงมาลัยของ comma four และบนปุ่มโหมดทดลองของ comma 3X

## AdventurePilot

AdventurePilot เป็นฟอร์กของ sunnypilot ที่มีพอร์ตรถของตัวเอง CommaView วาดหน้าจอของ sunnypilot พร้อมสิ่งที่ AdventurePilot เพิ่ม:

- **ตัวบอกการรักษากึ่งกลางเลน** เป็นแถบมนที่แสดงแรงดันและระยะเยื้องบนหน้าจอ comma 3X และเป็นแถบขนาดเล็กบน comma four
- **ชิป CURVE** บนหน้าจอ comma 3X ที่กะพริบเมื่อระบบควบคุมความเร็วในโค้งทำงาน
- **สีโหมดบังคับเลี้ยว** บนพวงมาลัย และแถบแรงบิดที่แสดงความเร่งด้านข้างเมื่อ Rivian บังคับเลี้ยวผ่านช่องสัญญาณมุม

## วิธีอัปเดต

CommaView อยู่ในช่วง Beta แบบเชิญเท่านั้น ถ้าคุณอยู่ในกลุ่ม แอปจะเสนออัปเดต 0.0.163 ให้เอง หลังแอปอัปเดต ให้อัปเดตรันไทม์บน comma จากแอป แล้วรีบูต comma เมื่อแอปขอ การอัปเดตรันไทม์จะรอจนรถอยู่ในเกียร์ P และ openpilot ยกเลิกระบบช่วยขับ จึงไม่ขัดจังหวะการขับ

เพิ่งเริ่มใช้ CommaView? [คู่มือการตั้งค่า](/th/guides/setup) อธิบายการติดตั้งแอปและการเชื่อมต่อ comma ของคุณ

## สิ่งที่ไม่เปลี่ยน

- CommaView ใช้ได้กับ **comma 3X** และ **comma four** ยังไม่รองรับ comma 3 รวมถึงรุ่นสำหรับ comma 3 ของฟอร์กต่างๆ เช่น xnor-c3 ([ทำไม](/th/#faq-comma-3))
- CommaView ไม่เปลี่ยนวิธีที่ฟอร์กของคุณขับ มันเพิ่มรันไทม์ขนาดเล็กไว้ข้างๆ และฮุกเล็กๆ ใน UI บนหน้าจอ เพื่อวาดเส้นทาง เลน และคำเตือนแบบเดียวกันได้
- บนฟอร์กที่ CommaView ยังไม่รองรับ การตั้งค่าจะหยุดและปล่อย comma ไว้อย่างเดิม คุณขอให้รองรับฟอร์กของคุณได้ที่บอร์ดฟีเจอร์บน my.commaview.com

## อ่านเพิ่มเติม

- [ฟอร์ก openpilot ใดใช้ได้กับ CommaView](/th/forks) และแต่ละตัวแสดงอะไร
- [มีอะไรใหม่](/th/whats-new) ในทุกรุ่น
- [การออกรุ่นของ CommaView ทำงานอย่างไร](/th/guides/releases)

CommaView ไม่ใช่ซอฟต์แวร์ทางการ และไม่มีส่วนเกี่ยวข้องกับ comma.ai, sunnypilot, StarPilot, xnor-tech หรือ AdventurePilot เป็นซอฟต์แวร์ Beta และไม่ใช่ระบบความปลอดภัย: อย่าปล่อยให้มันดึงความสนใจไปจากการขับ
