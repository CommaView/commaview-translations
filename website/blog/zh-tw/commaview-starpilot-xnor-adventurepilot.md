---
title: "CommaView 現在支援 StarPilot、xnor 和 AdventurePilot"
description: "繼 0.0.162 支援 StarPilot 之後，CommaView 0.0.163 新增 xnor-tech 的 openpilot 和 AdventurePilot。各個 openpilot 分支版本在 comma 3X 和 comma four 的 Live View 中會顯示什麼。"
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot 分支版本
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "版本說明"
draft: false
---

CommaView 現在支援五種 openpilot 版本：**openpilot**、**sunnypilot**、**StarPilot**、**xnor-tech 的 openpilot**（它的 xnor 和 rx 版本）以及 **AdventurePilot**。StarPilot 在 CommaView 0.0.162 加入，0.0.163 Beta 再加入 xnor 和 AdventurePilot。在每一種上，Live View 都會在您的 Android 手機、平板或車機上繪製該分支版本自己的畫面，連同它新增的內容。

在這之前，在這些分支版本上設定時會停在「unsupported upstream remote」。有了 0.0.163 的 App 和搭配的執行環境，安裝和配對都跟在 openpilot 上一樣。

## 各分支版本在 Live View 中顯示什麼

CommaView 不會從分支版本的名稱去猜。您 comma 上的執行環境會告訴 App，這個分支版本在畫面上加了什麼，App 再把它畫在 comma four 的畫面、comma 3X 的畫面或 CommaView 自己的畫面上。

| 分支版本 | CommaView 繪製的內容 |
| --- | --- |
| openpilot | comma four 和 comma 3X 的畫面，或 CommaView 自己的疊加圖層 |
| sunnypilot | sunnypilot 的畫面：MADS、速限輔助、彩虹路徑、盲點指示，以及它在 comma 3X 上新增的內容 |
| StarPilot | StarPilot 的配色、小工具、警示和鏡頭選擇 |
| xnor | xnor 版本是 openpilot 的畫面，rx 是 sunnypilot 的畫面，以及 rx 的 Rivian 方向盤色調 |
| AdventurePilot | sunnypilot 的畫面，加上它的車道置中指示器、CURVE 標籤和轉向模式色調 |

## StarPilot

StarPilot 用顏色表示駕駛模式，CommaView 用的也是 StarPilot 選定的顏色：它的邊框、路徑和小工具、它的警示，以及它的鏡頭選擇，包括車內鏡頭。請先關閉 StarPilot 的 **Disable Logging** 設定：它會停掉 Live View 串流所需的影像編碼器。

## xnor-tech 的 openpilot：xnor 和 rx

xnor-tech 的 openpilot 在同一個儲存庫裡提供兩種版本。它的 **xnor** 分支執行 openpilot 的畫面，**rx** 分支執行 sunnypilot 的畫面，兩者都有 xnor-tech 的車型移植。CommaView 會判斷您的 comma 執行的是哪一種，並繪製對應的畫面，警示也和 comma 上顯示的一樣。

在執行 rx 的 Rivian 上，方向盤會顯示車子的轉向方式：以角度轉向時是綠色，以扭力轉向時是藍色。CommaView 會在 comma four 的方向盤和 comma 3X 的實驗模式按鈕上畫出同樣的顏色。

## AdventurePilot

AdventurePilot 是一個 sunnypilot 分支版本，有自己的車型移植。CommaView 繪製 sunnypilot 的畫面，再加上 AdventurePilot 新增的內容：

- 它的 **車道置中指示器**：在 comma 3X 畫面上是顯示推力和偏移的膠囊形標籤，在 comma four 畫面上是一條精簡的橫條；
- comma 3X 畫面上的 **CURVE 標籤**，在彎道速度控制作用時閃爍；
- 方向盤上的 **轉向模式色調**，以及 Rivian 透過角度通道轉向時顯示橫向加速度的扭力條。

## 如何取得

CommaView 目前是僅限邀請的 Beta。如果您已加入，App 會自動提供 0.0.163 更新。App 更新後，從 App 更新 comma 上的執行環境，再依提示重新啟動 comma。執行環境更新會等到車子打入 P 檔且 openpilot 未啟用時才進行，所以絕不會打斷行駛。

第一次使用 CommaView？[設定指南](/zh-tw/guides/setup) 會帶您完成 App 安裝和 comma 連線。

## 沒有改變的部分

- CommaView 支援 **comma 3X** 和 **comma four**。comma 3 仍不支援，包括各分支版本的 comma 3 版本，例如 xnor-c3（[原因](/zh-tw#faq-comma-3)）。
- CommaView 絕不會改變分支版本的駕駛方式。它只是在旁邊加上一個小型執行環境，並在螢幕介面加上一個小掛鉤，好畫出同樣的路徑、車道和警示。
- 在 CommaView 還不支援的分支版本上，設定會停止，並讓您的 comma 維持原狀。您可以在 my.commaview.com 的功能看板上提出支援您分支版本的請求。

## 延伸閱讀

- [哪些 openpilot 分支版本支援 CommaView](/forks)，以及各自顯示的內容
- 每個版本的[最新消息](/whats-new)
- [CommaView 的版本發布方式](/zh-tw/guides/releases)

CommaView 是非官方軟體，與 comma.ai、sunnypilot、StarPilot、xnor-tech 或 AdventurePilot 均無關聯。它是 Beta 軟體，不是安全系統：千萬別讓它分散您開車的注意力。
