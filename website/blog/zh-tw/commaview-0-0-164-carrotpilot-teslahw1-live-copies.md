---
title: "CommaView 0.0.164：carrotpilot、SunnyPilot-TeslaHW1 和即時副本"
description: "CommaView 0.0.164 新增 carrotpilot 和 SunnyPilot-TeslaHW1，以及在行駛中保存 Live View 畫面的即時副本。另外，導航和 Surround 開放搶先體驗。"
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot 分支版本
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - 錄影
heroLabel: "版本說明"
draft: false
---

CommaView 0.0.164 已向 Beta 的所有成員推出。它新增兩個 openpilot 分支版本 **carrotpilot** 和 **SunnyPilot-TeslaHW1**，所以 CommaView 現在支援七種：openpilot、sunnypilot、StarPilot、xnor-tech 的 openpilot、AdventurePilot、SunnyPilot-TeslaHW1 和 carrotpilot。它也帶來了 **即時副本**：在您行駛時保存 Live View 顯示的畫面，停車的那一刻就能看。

它搭配執行環境 `v0.0.60-beta`，可以辨識這兩個新的分支版本。App 提示時，請從 App 更新執行環境，並在 App 要求時重新啟動 comma。

## SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 是一個 sunnypilot 分支版本，加入了 Tesla HW1（Autopilot 1）車款。它的畫面就是 sunnypilot 的畫面，所以 CommaView 會繪製 sunnypilot 的畫面和 sunnypilot 新增的所有內容，並在 App 中顯示這個分支版本的名稱。

有一點要注意：安裝了 CommaView 的掛鉤時，它的 `op fork update` 無法切換分支版本。請先解除安裝 CommaView，或使用 comma 螢幕上的分支版本切換功能，它照常可以用。

## carrotpilot

carrotpilot 是一個針對現代、起亞和 Genesis 車款的 openpilot 分支版本，從 `i.carrotpilot.app` 安裝。CommaView 為它繪製 openpilot 的畫面，包括您的車速、路徑、車道和前車，並在 App 中顯示這個分支版本的名稱。

目前有兩項限制：

- **carrotpilot 自己的畫面還不會繪製。** 它在 openpilot 畫面上新增的內容，例如導航、測速照相和 HUD，不會顯示在 Live View 中。
- **它的更新會移除 CommaView 的掛鉤，直到 comma 重新啟動。** carrotpilot 的自動更新和它網頁上的 Git 工具，會在執行中重設它的檔案。不會有東西壞掉：App 會要求重新啟動，重新啟動後 Live View 就會回來。

## 即時副本

在這之前，**錄影** 產生的是回放：停車後，App 下載 comma 自己的影片，再把 HUD 畫上去。這仍然是畫質最好的方式，但行程結束後要等一陣子，而且每段錄影最長 10 分鐘。

現在可以在 設定 › 錄影 › **在 Live View 中錄影** 選擇 **錄影** 要產生什麼：

| 選項 | 您會得到 |
| --- | --- |
| **回放**（預設） | comma 自己的影片，上面畫著 HUD，停車後產生。畫質最好，每段錄影最長 10 分鐘。 |
| **即時副本** | 您行駛時 Live View 顯示的畫面，存在手機上，停車那一刻就出現在「錄影」中，沒有 10 分鐘限制。 |
| **兩者** | 現在先得到即時副本，行程結束後再得到回放。 |

即時副本是 720p（每小時約 1.4 GB）或 1080p（每小時約 2.3 GB），每秒 20 格。切換 App 或鎖定手機時會繼續錄，並顯示一則通知，可以從通知停止。手機儲存空間用完前，它會正常停止；如果錄影時 App 關閉，除了最後一分鐘，其他內容都會保留。

即時副本存在您的手機上，絕不會上傳。

## 0.0.164 的其他改進

- **設定頁面用滿整個螢幕。** **錄影**、**顯示** 和 **直播** 的版面和 **離線地圖** 一致，空間夠時分成兩欄，在平板、車機和橫拿的手機上都排列整齊。
- **安裝失敗的原因。** 如果設定、執行環境更新或解除安裝失敗，App 會說明哪裡出了問題、該怎麼做：CommaView 不支援的分支版本、車子正在行駛、comma 沒有網路、下載的檔案損毀。它會告訴您 comma 是否已還原為原本的狀態，**複製詳細資料** 會複製支援人員需要的報告。
- **回放更快。** 回放只下載它要顯示的影片，而且在製作一段回放時，佇列中的下一段行程會同時下載。因 App 關閉、10 分鐘限制或車子熄火而中斷的錄影，現在也能做成回放。
- **回放畫質設定恢復正常。** Balanced、High 和 Max 又會產生不同的回放了：先前每段回放都以相同的 40 Mbit/s 產生。預設的 High 現在在 comma 3X 上產生的檔案大約只有原本的一半。

## 搶先體驗：導航和 Surround

有些功能還在早期開發階段：**導航**、**Surround**、**直播** 和 **傳送給 CommaView**。我們透過功能開關開放給一小群測試者，同時收集意見，所以只有開啟這些功能的帳號才看得到。

- **導航** 提供從首頁到 Live View 的逐向導引：搜尋地點、選擇路線，然後跟著轉向卡片、語音提示，以及在 CommaView 畫面上畫在您車道裡的箭頭走。轉錯彎後，幾秒內就會找到新路線。它只負責顯示：不會傳送任何內容到您的 comma 或車子。
- **Surround** 是車子周圍道路的 3D 視圖：鏡頭看到的道路和它的車道線與路口，以及您周圍的汽車、卡車和紅綠燈。

其中一些功能使用付費服務，例如導航的路線規劃，所以在了解正常使用的成本之前，我們會維持小規模測試。如果您願意幫忙測試，請到我們的 [Discord](https://discord.gg/UuMhz9K8ft) 聯絡我們，並準備好告訴我們它們在您的行程中表現如何。

## 如何取得

CommaView 目前是僅限邀請的 Beta。如果您已加入，App 會自動提供 0.0.164 更新。更新後，從 App 更新 comma 上的執行環境，再依提示重新啟動 comma。執行環境更新會等到車子打入 P 檔且 openpilot 未啟用時才進行，所以絕不會打斷行駛。

第一次使用 CommaView？[設定指南](/zh-tw/guides/setup) 會帶您完成 App 安裝和 comma 連線。

## 延伸閱讀

- [哪些 openpilot 分支版本支援 CommaView](/forks)，包括 [SunnyPilot-TeslaHW1](/forks#teslahw1) 和 [carrotpilot](/forks#carrotpilot)
- 每個版本的[最新消息](/whats-new)
- [CommaView 的版本發布方式](/zh-tw/guides/releases)

CommaView 是非官方軟體，與 comma.ai、sunnypilot、carrotpilot 或 SunnyPilot-TeslaHW1 均無關聯。它是 Beta 軟體，不是安全系統：千萬別讓它分散您開車的注意力。
