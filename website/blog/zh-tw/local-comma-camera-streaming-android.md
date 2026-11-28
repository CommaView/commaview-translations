---
title: "在 Android 上本機串流 comma 鏡頭：CommaView 能做什麼"
description: "CommaView 透過您自己的網路，把 comma 的道路鏡頭畫面連同駕駛疊加圖層串流到 Android：Live View、錄影、直播，以及它不做的事。"
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma 鏡頭串流
  - comma four
  - Android App
  - CommaView
  - 本機串流
heroLabel: "產品定位"
draft: false
---

CommaView 透過您自己的網路，把 comma 的道路鏡頭畫面連同駕駛疊加圖層，串流到 Android 手機、平板或車機。comma 和手機之間沒有雲端，也不需要先上傳任何東西。

它由兩個部分組成：CommaView App，以及 comma 上的一個小型執行環境 `commaviewd`，後者把鏡頭畫面和駕駛資料提供給 App。引導設定會安裝並檢查這個執行環境。

## 為什麼要串流

comma four 的螢幕只有 1.9 吋。就它的用途來說，這塊螢幕很好，但它很小，車主們也這麼說。comma 提供的其他取得影像的方式，是為別的用途設計的：

- **comma connect** 會把上傳的行程保留 3 天，訂閱 comma prime 則保留一年（[comma.ai/prime](https://comma.ai/prime)）。從 [openpilot 0.11.2](https://blog.comma.ai/0112release/) 起，在安裝 comma power 的情況下，它可以在車子停放時透過網際網路直播道路鏡頭和車內鏡頭的畫面，並在 comma 上剪出 MP4 片段影片。
- **SSH** 可以從 comma 的儲存空間取出原始的一分鐘 HEVC 片段。

這兩種方式都無法在您行駛時，顯示帶有 openpilot 駕駛疊加圖層的道路畫面。CommaView 就是為此而做的。

## CommaView 能做什麼

### Live View

即時的道路鏡頭畫面，上面畫著您分支版本自己的畫面：comma four 的、comma 3X 的，或 CommaView 自己的樣式，把您的車速、最大設定速度（MAX）、速限、前車和變換車道集中在一個儀表區。Live View 會依每個分支版本新增的內容繪製它的畫面，從 sunnypilot 的 MADS 到 StarPilot 自己的 HUD。它最高能以 comma 的每秒 20 格執行，並能在子母畫面中繼續運作。

在平板或 Android 車機上，CommaView 會以儀表板的方式排版，Live View 的控制項位於駕駛座那一側。

### 錄影

在 Live View 中輕觸 **錄影**，停車後，CommaView 會下載 comma 自己錄下的那一段影片（最長 10 分鐘），並在您的手機上把分支版本的畫面畫上去：這就是回放。您可以播放、分享，或在其他 App 中開啟它。即時副本會在您行駛時保存 Live View 顯示的畫面，720p 或 1080p，停車那一刻就能看，沒有 10 分鐘限制。錄影會一直留在您的手機上，直到您刪除。

### 直播

直播會把 Live View 顯示的內容，也就是道路和 CommaView 的疊加圖層，以 720p 或 1080p 串流到您的 YouTube 頻道或任何 RTMP 伺服器。**使用 YouTube 登入** 一次後，它會為您建立、開始和結束每一場直播。直播一開始是 **不公開**；觀看的人都看得到您開車經過的地方。

### 僅限已配對的手機

您 comma 的鏡頭和資料只會傳到與它配對的手機和車機。影片、行程和地點只會從您的 comma 傳到您的手機，不會去別的地方，除非您主動傳送、直播或貢獻它們。

## 哪些功能需要網際網路

Live View 和錄影不需要：它們在同一個區域網路上，直接從 comma 傳到您的手機。這個網路可以是您的 Wi‑Fi，也可以是車上由手機、車機、AI 盒或 comma 分享的熱點。登入、App 和執行環境更新、**車輛位置** 中的地圖、排行榜、直播，以及您傳給 CommaView 的任何內容，則需要網際網路。

## 支援哪些裝置

comma 3X 和 comma four，執行 openpilot、sunnypilot、StarPilot、xnor-tech 的 openpilot、AdventurePilot、SunnyPilot-TeslaHW1 或 carrotpilot。其他 openpilot 分支版本以盡力支援的方式運作：設定會先檢查分支版本，並在安裝前詢問您。comma 3 不支援：它執行的是已凍結的 openpilot 版本，CommaView 無法從它的畫面繪製疊加圖層。[支援的分支版本](/forks)。

您需要一支執行 Android 8 以上版本的 Android 手機、平板或車機。

## CommaView 不是什麼

- **不是 comma connect。** 它不會把行程存在雲端，也不能讓您在城市另一頭查看自己的車。這些請用 connect。
- **不是行車記錄器。** 如果您需要可作為證據的碰撞或停車錄影，[請使用專門的行車記錄器](/zh-tw/blog/is-comma-a-dashcam)。
- **不是駕駛輔助或安全系統。** 它顯示的是 comma 看到的東西；一切以實際路況為準。

## 安全使用

請在停車時設定 CommaView。您開車時，乘客可以看 Live View；如果您獨自開車，請像對待 comma 自己的螢幕一樣對待它，眼睛始終看著路面。

CommaView 目前是僅限邀請的 Beta。[加入名單](https://my.commaview.com/join)，輪到您時我們會寄電子郵件通知您。

CommaView 是非官方軟體，與 comma.ai、sunnypilot 或它支援的任何 openpilot 分支版本均無關聯，也未獲得它們的背書。它是 Beta 軟體，不是安全系統：千萬別讓它分散您開車的注意力。
