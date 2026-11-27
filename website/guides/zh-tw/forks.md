---
title: "檢查您的 comma 和分支版本是否受支援"
description: "CommaView 支援 openpilot、sunnypilot、StarPilot、xnor、AdventurePilot、SunnyPilot-TeslaHW1、carrotpilot、BluePilot、dragonpilot 和 OPGM，並盡力支援其他分支版本。"
topic: start
order: 2
kind: reference
lede: "CommaView 會顯示您 comma 的道路鏡頭畫面，並疊上它所執行軟體的駕駛畫面。它支援 comma 3X 和 comma four 上的 openpilot 及其九個分支版本，並盡力支援其他 openpilot 分支版本。設定在變更任何東西之前，會先檢查您的 comma 執行的是哪個分支版本。"
updated: 2026-11-27
needs:
  - title: "一台 comma 3X 或 comma four"
    text: "不支援 comma 3，包括各分支版本的 comma 3 版本，例如 xnor-c3。[為什麼不支援 comma 3](/#faq-comma-3)。"
  - title: "照常執行的分支版本"
    text: "已安裝並照常執行。CommaView 會在它旁邊加上執行環境，絕不改變它的駕駛方式。"
steps:
  - id: unlisted
    title: "在 CommaView 未列出的分支版本上，設定會先詢問您"
    body: |
      引導設定會檢查您 comma 的軟體是從哪個儲存庫安裝的，並為那個分支版本安裝 CommaView 的掛鉤。在未列出的分支版本上，它會先檢查分支版本，不會變更任何東西。
    tabs:
      - label: "盡力支援"
        body: "如果 CommaView 可以加入它的畫面，設定會顯示 **CommaView 尚未驗證這個分支版本**。它會以儲存庫名稱標示分支版本，並說明會繪製什麼（鏡頭畫面、行駛路徑、車道線、前車、警示和車速），以及不會繪製什麼（分支版本自己的按鈕、顏色和小工具）。**仍要安裝** 會安裝到這個分支版本上，而且只限這一個。**返回** 會回到選擇 comma 的步驟；不會安裝任何東西。"
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**仍要安裝** 會以盡力支援的方式把 CommaView 的畫面加入這個分支版本。"
      - label: "僅影像模式（搶先體驗）"
        body: "FrogPilot 和 KisaPilot 的畫面無法加入 CommaView 的畫面，擁有「僅影像」標記的測試人員會看到 **這個分支版本僅影像模式**：CommaView 會串流鏡頭畫面，並依照駕駛資料繪製自己的畫面，不變動分支版本的任何內容。它還沒有在 comma 上實際試過。沒有這個標記時，設定會說明這個分支版本不受支援，而且不會變更任何東西。"
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**安裝僅影像模式**。"
    note: "檢查拒絕某個分支版本時，設定會顯示「CommaView 無法安全地將其畫面加入 …」和「您的 comma 上沒有任何變更。」"
  - id: details
    title: "查看 Live View 繪製的是哪個分支版本"
    body: |
      在 Live View 中開啟 **詳細資訊**。**軟體** 一列會顯示您 comma 的分支版本；CommaView 未列出的分支版本會以儲存庫名稱顯示，例如「crwusiz/openpilot · best effort」。
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**詳細資訊**，在畫面下方。"
      - text: "**軟體**：您的 comma 執行的分支版本。"
related: [setup, overlays, uninstall]
---

## 支援的分支版本

| 分支版本 | 來源 | 開始支援的版本 |
| --- | --- | --- |
| **openpilot** | comma.ai，github.com/commaai/openpilot | 第一個 Beta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | 第一個 Beta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot，原為 github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor**（xnor 和 rx 版本） | xnor-tech，github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot，從 i.carrotpilot.app 安裝 | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

在未列出的分支版本上，設定會檢查 CommaView 能否加入它的畫面，並先詢問您；如果不能，設定會停止，讓您的 comma 維持原狀。

## 每個分支版本顯示什麼

### openpilot

comma.ai 自己的軟體。Live View 會繪製 comma four 的畫面、comma 3X 的畫面或 CommaView 自己的疊加圖層，顯示您的車速、MAX、速限、前車和變換車道。

### sunnypilot

CommaView 會繪製 sunnypilot 的畫面和 sunnypilot 新增的內容：MADS 的僅轉向和僅速度狀態、速限輔助、彩虹路徑和盲點指示，在 comma 3X 畫面上還有它的速限標誌、智慧巡航和開發者介面。它會讀取您的 sunnypilot 設定，讓畫面和 comma 上的一致。

### StarPilot

StarPilot 用顏色表示駕駛模式，CommaView 會採用 StarPilot 選的顏色：comma four 和 comma 3X 畫面上的邊框、路徑和小工具，它的警示，以及它的鏡頭選擇，包括車內鏡頭。

請關閉 StarPilot 的 **Disable Logging** 設定。它會停止 Live View 串流所用的影像編碼器。

### xnor-tech 的 openpilot：xnor 和 rx

xnor-tech 的 openpilot 有兩種版本。**xnor** 分支執行 openpilot 的畫面，**rx** 分支執行 sunnypilot 的畫面，兩者都附有 xnor-tech 的車型適配。CommaView 會繪製您的 comma 執行的那一種，警示文字和 comma 上的一致。

在執行 rx 的 Rivian 上，車輛以角度轉向時方向盤會變成綠色，以扭力轉向時則是藍色：comma four 上是方向盤圖示，comma 3X 畫面上則是實驗模式按鈕的方向盤。

### AdventurePilot

AdventurePilot 是有自己車型適配的 sunnypilot 分支版本。CommaView 會繪製 sunnypilot 的畫面和 AdventurePilot 新增的內容：

- 它的車道置中指示器：comma 3X 畫面上是顯示推力和偏移的標籤，comma four 畫面上是精簡的長條；
- comma 3X 畫面上的 CURVE 標記，彎道速度控制作用時會閃爍；
- 它轉向模式的方向盤色調，以及 Rivian 透過角度通道轉向時顯示橫向加速度的扭力條。

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 是 sunnypilot 的分支版本，加入了 Tesla HW1（Autopilot 1）車輛的支援。它的畫面就是 sunnypilot 的，所以 CommaView 會繪製 sunnypilot 的畫面和它新增的所有內容，並在 App 中顯示這個分支版本的名稱。

安裝了 CommaView 的掛鉤時，它的 `op fork update` 無法切換分支版本：請先[解除安裝 CommaView 的執行環境](/zh-tw/guides/uninstall)，或使用 comma 螢幕上的分支版本切換器，它可以照常使用。

### carrotpilot

carrotpilot 是針對 Hyundai、Kia 和 Genesis 車輛的 openpilot 分支版本，從 `i.carrotpilot.app` 安裝。CommaView 會為它繪製 openpilot 的畫面，顯示您的車速、行駛路徑、車道線和前車。carrotpilot 在自己畫面上新增的內容，例如導航、測速照相和 HUD，目前還不會繪製。

carrotpilot 的自動更新以及它網頁上的 Git 工具會移除 CommaView 的掛鉤，直到 comma 重新啟動為止。App 會請您重新啟動，重新啟動後 Live View 就會恢復。

### BluePilot、dragonpilot 和 OPGM

從 CommaView 0.0.166 及其執行環境起列為支援。CommaView 會顯示它們各自的名稱，並以其基礎版本的樣式繪製：BluePilot 依照 sunnypilot，dragonpilot 和 OPGM 依照 openpilot，dragonpilot 的 ALKA 會顯示為轉向。之前以盡力支援方式執行其中一個的 comma，會在執行環境更新後的下次開機時切換過來。它們都還沒有搭配 CommaView 實際開過車。CommaView 的官方[疊加套件](/zh-tw/guides/overlays)可以繪製更多 BluePilot 和 dragonpilot 自己畫面上的內容。

## CommaView 未列出的分支版本

從 CommaView 0.0.165 起，只要您的 comma 上裝有它的執行環境，設定就能以盡力支援的方式，把 CommaView 的畫面加入它未列出的 openpilot 分支版本。Live View 會以 openpilot 的樣式繪製這個分支版本；如果分支版本建立在 sunnypilot 的畫面上，則以 sunnypilot 的樣式繪製。要復原時，裝置設定中的 **解除安裝執行環境** 會把分支版本的檔案還原為原本的狀態。

- **盡力支援。** CommaView 的版本沒有針對您的分支版本檢查過。如果分支版本自行更新成 CommaView 跟不上的樣子，CommaView 的畫面會關閉，您的分支版本則照常駕駛並顯示自己的畫面，直到有 CommaView 版本處理了這項變化。
- **不是每個分支版本都可以。** 建立在 openpilot 舊版原生畫面上的分支版本不受支援（見下文）。
- **您的同意只適用於那個分支版本。** 如果您的 comma 換成另一個 CommaView 未列出的分支版本，CommaView 會在設定中再詢問您一次，才會把畫面加到那裡。

### 通過安裝檢查的分支版本（盡力支援）

以下每一個都**通過了 CommaView 的安裝檢查；盡力支援，未在車上測試。** 檢查於 2026 年 11 月進行，針對列出的分支，使用 CommaView 0.0.165 安裝的執行環境：安裝程式會提供這個分支版本，在您同意後加入 CommaView 的畫面並加以檢查，就像在您的 comma 上一樣。這裡沒有任何一項在車上的 comma 實際試過，分支版本也不一定在兩種裝置上都支援所有車款，而且分支版本的下一次更新可能改變結果。

| 分支版本 | 檢查的分支 | 裝置 | 繪製樣式 |
| --- | --- | --- | --- |
| **crwusiz**（github.com/crwusiz/openpilot） | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **jixiexiaoge’s Carrot**（github.com/jixiexiaoge/openpilot） | Carrot | comma four, comma 3X | openpilot |
| **MoreTore**（github.com/MoreTore/openpilot） | release-mici | comma four | openpilot |
| **zoompilot**（github.com/zoompilot/zoompilot） | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato**（github.com/AlexandreSato/openpilot） | master | comma four, comma 3X | openpilot |
| **lukasloetkolben**（github.com/lukasloetkolben/openpilot） | master | comma four, comma 3X | openpilot |
| **mvl-boston**（github.com/mvl-boston/openpilot） | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub**（github.com/mouxangithub/openpilot） | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro**（github.com/programanichiro/openpilot） | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2**（github.com/infiniteCable2/openpilot） | master | comma four, comma 3X | sunnypilot |
| **herizon1054**（github.com/herizon1054/openpilot） | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot**（github.com/NotAutopilot/openpilot） | nap-release, naponsp-alpha | comma four, comma 3X | openpilot（nap-release），sunnypilot（naponsp-alpha） |

您的分支版本不在這裡？它仍然可能可以使用：設定在變更任何東西之前都會先檢查它。

### 不受支援

這些分支版本的畫面無法加入 CommaView 的畫面，所以設定會如實告知，而且不會變更您 comma 上的任何東西：

- **FrogPilot**（github.com/FrogAi/FrogPilot）。它執行 openpilot 舊版的原生（Qt）畫面，沒有地方可以加入 CommaView 的畫面。僅影像模式正在搶先體驗中。
- **KisaPilot**（github.com/kisapilot/openpilot）。它的 Python 畫面已關閉：執行的是 openpilot 舊版的原生（Qt）畫面。僅影像模式正在搶先體驗中。
- **IQ.Pilot**（github.com/IQLvbs/iqpilot）。從 2026 年 10 月起，它執行在自己的 IQ.OS 上；要等 CommaView 能把它當成獨立的分支版本來支援。
- **hikee9123**（github.com/hikee9123/openpilot）。它執行 openpilot 舊版的原生（Qt）畫面。

**搶先體驗：FrogPilot 和 KisaPilot 的僅影像模式。** 擁有「僅影像」標記時，設定會提供在 Live View 中播放它們的鏡頭畫面，並以 CommaView 自己的疊加圖層取代它們的畫面，不變動分支版本的任何內容。它還沒有在 comma 上實際試過。沒有這個標記時，設定仍會說明它們不受支援，而且不會變更任何東西。

## 支援哪些 comma 裝置

comma 3X 和 comma four。不支援 comma 3，包括各分支版本的 comma 3 版本，例如 xnor-c3：[為什麼不支援 comma 3](/#faq-comma-3)。App 可以在 Android 手機、平板或車機上執行。

## 正式版和開發分支

每次發布前，CommaView 的執行環境都會針對這些分支版本的正式版建置來建置和檢查。openpilot 的 nightly 和 sunnypilot 的 dev 分支在每次有變動的當天都會檢查，作為預警。開發分支的變化可能比 CommaView 更快：如果某項變動讓 CommaView 的掛鉤無法載入，您分支版本的畫面和駕駛都會照常運作。

## 您的分支版本沒有列出？

可以先以盡力支援的方式試用，並在 [my.commaview.com](https://my.commaview.com) 的功能許願板上要求列入，或從 App 提出建議（設定 › **支援與診斷**）。列出的分支版本在每次發布前都會經過檢查。每個版本的變化請看[最新消息](/whats-new)。

## 常見問題

**CommaView 會改變我分支版本的駕駛方式嗎？** 不會。它只是在您的分支版本旁加上一個小型執行環境，並在它的螢幕介面中加一個小掛鉤，讓 CommaView 能繪製同樣的路徑、車道線和警示。您車輛的駕駛方式不會改變。

**CommaView 支援 StarPilot 嗎？** 支援，從 CommaView 0.0.162 起。Live View 會顯示 StarPilot 自己的顏色、小工具和鏡頭選擇。請關閉 StarPilot 的 **Disable Logging** 設定，它會停止 CommaView 串流所用的影像編碼器。

**CommaView 支援 carrotpilot 嗎？** 支援，從 CommaView 0.0.164 起。Live View 會為它繪製 openpilot 的畫面；carrotpilot 在自己畫面上新增的內容，例如導航和測速照相，目前還不會繪製。carrotpilot 自行更新後，App 會請您重新啟動，重新啟動後 Live View 就會恢復。

**CommaView 支援 FrogPilot 嗎？** 目前還不支援：它執行 openpilot 舊版的原生（Qt）畫面，沒有地方可以加入 CommaView 的畫面，所以設定會說明它不受支援，而且不會變更任何東西。FrogPilot 和 KisaPilot 的僅影像模式正開放測試人員搶先體驗。
