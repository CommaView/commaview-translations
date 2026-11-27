---
title: "comma connect 還是本機影像：哪一個符合您的需求？"
description: "openpilot 0.11.2 之後，comma connect、SSH 和 CommaView 的比較：停車直播、片段影片、行程保留期限、畫質、隱私權，以及各自的用途。"
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - 本機影像存取
  - comma four
  - CommaView
heroLabel: "選擇指南"
draft: false
---

comma connect 是 comma 自己的網頁應用程式，大多數車主都會先在這裡看自己的行程，而且就很多事情來說，它就是該看的地方。從 openpilot 0.11.2 起，它能做的比以前更多：可以直播停放中的車子，也能在裝置上剪出 MP4 片段影片。本機存取，不論是透過 SSH 還是 CommaView，做的是另一件事：在您自己的網路上，直接從 comma 取得影像。

簡短的答案：

- **在任何地方查看最近的一段行程：** comma connect。
- **車子停放時查看狀況：** comma connect 的直播。
- **開車時在更大的螢幕上觀看帶有分支版本駕駛疊加圖層的道路畫面：** CommaView 的 Live View。
- **用於開發或封存的原始鏡頭檔案：** SSH。
- **在手機上取得一段您剛剛看到、帶疊加圖層的片段，不必上傳：** CommaView 的 **錄影**。

## comma connect 能做什麼

**它會把您的行程在雲端保留一段時間。** comma 的 [prime 頁面](https://comma.ai/prime) 說，錄影「會上傳到 connect，並在那裡保存 3 天」。訂閱 comma prime（每月 24 美元，僅限美國，含數據）或 prime lite（每月 14 美元，需要行動網路的話請自備 SIM 卡）後，connect 會保留一年。

**它預設顯示的是小尺寸影片。** comma 的[記錄文件](https://docs.comma.ai/concepts/logs/) 說，connect 中的影片來自 qcamera 檔案，也就是「fcamera.hevc 的低解析度版本」，這些檔案是為了在慢速網路上快速上傳而製作的。完整解析度的 HEVC 檔案會留在 comma 上，除非您也上傳它們。

**從 0.11.2 起，它可以直播停放中的車子。** [0.11.2 的發布文章](https://blog.comma.ai/0112release/)（2026 年 10 月 23 日）說，在有網際網路連線（「家裡的 Wi‑Fi 或 comma prime 的 LTE」）並安裝 comma power 的情況下，「您可以直播道路鏡頭和車內鏡頭，在車子停放時查看周圍發生的狀況。」您可以在任何地方透過 connect 觀看。

**它也能剪片段。** 同一版本在 connect 中加入了片段按鈕：選取行程的一部分，「您的 comma 會把它拼接並重新編碼成相容性廣泛的 MP4（H.264）。」處理期間讓 comma 保持開機，然後從 connect 下載片段。

這是真正的進步。如果您想在辦公桌前看看停著的車，或把昨晚行程的一段片段傳給朋友，現在 connect 兩件事都做得到。

## comma connect 不做什麼

- **它無法在您行駛時直播。** 直播是給停放中的車子用的。
- **它不會繪製 openpilot 的駕駛疊加圖層。** 直播和片段都是鏡頭影片，沒有您在 comma 螢幕上看到的路徑、車道、警示或車速。
- **它需要網際網路。** 直播需要家裡的 Wi‑Fi 或 prime 的 LTE，行程也必須先上傳，connect 才能顯示。
- **沒有 prime 時，3 天後就不再保留。** 之後 connect 不再顯示這段行程，即使 comma 上還有。

這些都不是缺點。connect 是一項雲端服務，讓您不論身在何處都能查看自己的車子和行程。

## 本機存取能做什麼

本機存取是指在同一個網路上，直接從 comma 本身取得影像，而不是從 comma 的伺服器取得。

### SSH：原始檔案

每段 openpilot 行程都以一分鐘為單位的片段存在 comma 上，每個片段有自己的檔案：`fcamera.hevc`（道路）、`ecamera.hevc`（廣角道路）、`dcamera.hevc`（駕駛）、`qcamera.ts`（小尺寸預覽）和記錄檔。透過 SSH，只要 comma 上還有，您就能複製其中任何一個；空間不足時，comma 會刪除最舊的行程。這是取得完整解析度影片用於開發或個人封存的方法，但拿到的是一分鐘長的 HEVC 檔案，不是可以直接分享的片段。我們的[下載 comma 錄影](/zh-tw/blog/download-comma-dashcam-footage)指南會一步步說明。

### CommaView：Android 上的 Live View 和錄影

CommaView 是一款 Android App，加上 comma 上的一個小型執行環境 `commaviewd`，它透過您自己的區域網路把鏡頭畫面和駕駛資料傳到您的手機：可以是您的 Wi‑Fi，也可以是車上的熱點，不論是手機、車機還是 comma 分享的熱點。

- **開車時的 Live View。** 道路鏡頭畫面上畫著您分支版本自己的畫面，跟 comma four 或 comma 3X 上畫的一樣，或是 CommaView 自己的樣式，顯示在手機、儀表板上的平板或 Android 車機上。comma four 的螢幕是 1.9 吋；您手機的螢幕大得多。
- **存在手機上的錄影。** 在 Live View 中輕觸 **錄影**，停車後，CommaView 會下載 comma 自己錄下的那一段影片（最長 10 分鐘），並在手機上把分支版本的畫面畫上去。或者保存 Live View 所顯示畫面的即時副本，720p 或 1080p，沒有 10 分鐘限制。您可以播放、分享，或在其他 App 中開啟。
- **直播。** 把 Live View 顯示的內容，也就是道路和疊加圖層，以 720p 或 1080p 串流到您的 YouTube 頻道或任何 RTMP 伺服器。
- **不用訂閱，不用上傳。** Live View 和錄影從您的 comma 傳到您的手機，錄影會一直留在那裡，直到您刪除。您 comma 的鏡頭只會傳到與它配對的手機和車機。

它支援 comma 3X 和 comma four，執行 openpilot、sunnypilot、StarPilot、xnor、AdventurePilot、SunnyPilot-TeslaHW1 或 carrotpilot，其他分支版本則以盡力支援的方式運作。[支援哪些分支版本，以及 Live View 在各分支版本上畫出什麼](/forks)。

## 並排比較

| 功能 | comma connect | CommaView |
| --- | --- | --- |
| 即時影像 | 道路和車內鏡頭，車子停放時 | 道路鏡頭，行駛時 |
| 駕駛疊加圖層 | 無 | 您分支版本的畫面，或 CommaView 的樣式 |
| 影像傳到哪裡 | 經由網際網路，在 connect 中觀看 | 您自己的區域網路（Wi‑Fi 或熱點），傳到已配對的手機 |
| 需要 | 網際網路；直播還需要 comma power | 同一網路上的 Android 手機、平板或車機 |
| 片段 | 行程的任何部分，在 comma 上剪成 MP4，從 connect 下載 | 您在 Live View 中錄下的內容：最長 10 分鐘的回放，或即時副本，帶疊加圖層 |
| 行程保留多久 | 3 天，訂閱 prime 後一年 | 在您的手機上，直到您刪除 |
| 費用 | 免費，或 prime 每月 24 美元／lite 每月 14 美元 | 不用訂閱；CommaView 目前是僅限邀請的 Beta |

## 兩者都用

它們並不是在搶同一份工作。用 connect 隨時隨地查看車子、把想要的行程存到雲端；用 CommaView 在更大的螢幕上觀看帶有分支版本疊加圖層的道路畫面、錄下您看到的內容並直播。您開車時，乘客可以看 Live View；如果您獨自開車，請像對待 comma 自己的螢幕一樣對待它，眼睛始終看著路面。

## 延伸閱讀

- [comma prime](https://comma.ai/prime)：connect 的方案和行程保留時間
- [openpilot 0.11.2](https://blog.comma.ai/0112release/)：直播和片段功能
- [如何下載 comma 錄影](/zh-tw/blog/download-comma-dashcam-footage)：透過 SSH
- [設定 CommaView](/zh-tw/guides/setup)

CommaView 是非官方軟體，與 comma.ai、sunnypilot 或它支援的任何 openpilot 分支版本均無關聯，也未獲得它們的背書。它是 Beta 軟體，不是安全系統：千萬別讓它分散您開車的注意力。
