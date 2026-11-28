---
title: "在 Android AI 盒上執行 CommaView"
description: "用 Android AI 盒把 Live View 放到車輛原廠的 CarPlay 或 Android Auto 螢幕上：插上盒子、安裝 CommaView、連上 comma 的網路、完成配對並調整畫面。"
topic: screens
order: 4
kind: walkthrough
lede: "如果您的車輛原廠配備**有線** CarPlay 或 Android Auto，**Android AI 盒**可以把 CommaView 的 Live View 放到車輛自己的螢幕上，不必換音響，也不必拉線。這種盒子是一台小型 Android 電腦，插在您平常接手機的 USB 孔上。CommaView 在盒子上執行，您的手機就能空出來講電話、看地圖。"
parked: true
updated: 2026-11-27
needs:
  - title: "有線 CarPlay 或 Android Auto"
    text: "原廠有線 CarPlay 或有線 Android Auto，而且 USB 孔能傳輸資料。請確認盒子支援您車上的系統。"
  - title: "執行真正 Android 的盒子"
    text: "Android 8 以上版本，而且允許從檔案安裝 App。封閉式「影音」盒和單純的無線轉接器無法執行 CommaView。[該買哪一款盒子](/blog/android-ai-box-commaview)。"
  - title: "手機上的 CommaView"
    text: "先用手機設定好您的 comma，再配對盒子。[設定 CommaView](/zh-tw/guides/setup)。"
howItWorks:
  - title: "您的 comma"
    text: "透過區域網路把 Live View 傳到盒子。"
    edge: "Wi‑Fi"
  - title: "AI 盒"
    text: "像任何 Android 裝置一樣執行 CommaView。"
    edge: "USB"
  - title: "車上的螢幕"
    text: "像顯示 CarPlay 一樣顯示盒子的畫面。"
steps:
  - id: plug-in
    title: "插上盒子並安裝 CommaView"
    body: |
      把盒子插到車上的 CarPlay 或 Android Auto USB 孔，等它開機。先讓它連上可以上網的 Wi‑Fi。

      在盒子的瀏覽器中，用收到邀請的電子郵件地址登入 [my.commaview.com](https://my.commaview.com)，並在 **Get the app** 底下輕觸 **Download CommaView**。只為這次安裝允許從瀏覽器安裝 App，裝好後再關閉。開啟 CommaView 並登入。
    note: "請在盒子的 Android 模式下執行 CommaView，而不是透過手機的 CarPlay 轉接。"
  - id: network
    title: "讓盒子和 comma 連上同一個網路"
    body: |
      Live View 透過區域網路直接從 comma 傳到盒子，不經過網際網路，兩者共同連上的任何網路都可以。
    tabs:
      - label: "盒子的熱點"
        body: "有 SIM 卡的盒子通常可以分享熱點。開啟熱點，然後在 comma 的 **設定 › 網路** 中讓 comma 連上。"
      - label: "手機的熱點"
        body: "讓盒子和 comma 都連上您的手機熱點，它們也會透過熱點上網。"
      - label: "comma 的熱點"
        body: "開啟 comma 的熱點（openpilot 稱為網路分享），再讓盒子連上。"
    note: "大多數盒子也會用 Wi‑Fi 連接手機來使用無線 CarPlay，有些盒子這時會斷開 Wi‑Fi 的網際網路連線。請關閉盒子上的任何 VPN。"
  - id: pair
    title: "將盒子與您的 comma 配對"
    body: |
      在手機上開啟 comma 的 **裝置設定**，輕觸 **配對其他手機**，再於 **新增另一支手機** 底下輕觸 **顯示邀請碼**。在盒子上輕觸 **配對已執行 CommaView 的 comma**，選擇您的 comma，輸入代碼或輕觸 **掃描 QR 碼**。每個步驟的說明：[在平板或車用螢幕上使用 CommaView](/zh-tw/guides/car-screens#step-pair)。
  - id: edges
    title: "讓 App 避開車輛裁掉的邊緣"
    body: |
      有些車輛會裁掉盒子輸出畫面的邊緣，而 Android 無從得知。開啟 **設定 › 顯示 › 螢幕邊緣**。一條線標出 App 的邊界：用 **−** 和 **+** 把每一邊往內移，直到整圈線都看得到，再輕觸 **完成**。**重設** 會關閉這項功能。

      接著確認首頁、Live View 和設定都能完整顯示。
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−** 和 **+** 把每一邊往內移；**完成** 會儲存設定。"
      - text: "**主題** 也在 **設定 › 顯示** 中：**與這部裝置相同** 會跟隨盒子的設定。"
  - id: auto
    title: "讓它自動開啟"
    body: |
      在 **設定 › 顯示** 的 **開啟 Live View** 底下：

      - **這個裝置啟動時開啟 CommaView**：適用於隨車輛一起重新啟動的盒子。
      - **藍牙連線時開啟 CommaView**，並選擇您的手機：適用於會進入休眠的盒子。
      - **連線時開啟 Live View**：車輛發動後，comma 一連線就直接進入 Live View。

      請允許 **顯示在其他應用程式上層**，CommaView 才能自動開啟。沒有這項權限時，會改用通知提醒您開啟。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**連線時開啟 Live View**。"
  - id: check
    title: "確認 Live View 能播放，再上路"
    body: |
      車輛發動後，在盒子上開啟 Live View。它的控制項位於駕駛側的側欄中，螢幕較矮時會變得精簡。上路前請確認畫面能播放，而且沒有任何內容被裁掉。
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "**錄影**，在側欄頂端。"
      - target: details
        text: "**詳細資訊**，在側欄較下方。"
    note: "盒子的畫面是以影像形式傳到車上的，所以 Live View 在途中會多編碼一次。跟拿在手上的手機相比，畫面會稍微柔一點，也會稍有延遲。"
check: "車上的螢幕先顯示 CommaView 的首頁，再顯示 Live View，串流狀態標籤顯示 **即時**，**螢幕邊緣** 的那條線整圈都看得到。"
fixes:
  - q: "盒子無法安裝 CommaView"
    a: "有些盒子禁止從瀏覽器安裝 App。請在電腦上下載 App，用隨身碟複製到盒子上，再從盒子的檔案管理員開啟。系統封閉、只能使用固定 App 清單的盒子則完全無法安裝。"
  - q: "盒子找不到 comma"
    a: "請確認兩者在同一個網路中，而且盒子沒有為了無線 CarPlay 而斷開 Wi‑Fi。必要時請輸入 comma 的 IP 位址：在 comma 自己的熱點上是 192.168.43.1。詳情請看[在車上連線](/zh-tw/guides/connect-in-the-car)。"
  - q: "畫面卡頓或無法播放"
    a: "comma 傳送的道路鏡頭影像是 1928 × 1208 的 HEVC（H.265），最便宜的盒子的解碼器可能應付不來。某個解碼器失敗時，CommaView 會自動嘗試盒子上的其他解碼器。全部都不行時，Live View 會顯示 **無法播放這台 comma 的影像**：請從盒子傳送支援回報。"
  - q: "「Live View 已在另一部裝置上開啟」"
    a: "您的 comma 一次只會串流到一支手機或一台車機。在手機上的 CommaView 回到首頁，盒子上的 Live View 就會自行開始。"
  - q: "還能用手機的 CarPlay 嗎？"
    a: "可以。大多數盒子都能以無線方式轉接手機的 CarPlay 或 Android Auto，您可以在它和盒子的 Android 之間切換。CommaView 在盒子的 Android 模式下執行。"
  - q: "盒子需要 SIM 卡嗎？"
    a: "Live View 不需要。Beta 期間，CommaView 需要不時連上網路來續期存取通行證，家裡的 Wi‑Fi、手機熱點或盒子裡的 SIM 卡都可以提供。"
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## 四種「CarPlay 轉接器」

店家用同一個名稱賣著四種完全不同的東西，只有一種能執行 CommaView。

| 類型 | 用途 | 能執行 CommaView 嗎？ |
| --- | --- | --- |
| **Android AI 盒** | 在車上的螢幕執行完整的 Android，可以像手機一樣安裝 App | **能** |
| **封閉式「影音」盒** | 在鎖定的系統上執行幾款內建的影音 App | 不能 |
| **無線轉接器** | 把有線 CarPlay 或 Android Auto 變成無線的，本身沒有 Android | 不能 |
| **可攜式 CarPlay 螢幕** | 給手機 CarPlay 用的獨立螢幕，裡面通常不是 Android | 不能 |

[最適合 CommaView 的 Android AI 盒](/blog/android-ai-box-commaview) 比較了值得購買的盒子。Tesla 沒有 CarPlay 或 Android Auto：請改用 [Browser View](/zh-tw/guides/browser-view)。

更新 comma 的執行環境時，請先更新盒子上的 CommaView，就像每一部觀看您 comma 的裝置一樣。

## 安全

請在停車時設定好盒子，之後就別再操作。開車時請勿操作 CommaView：依照 openpilot 的要求，眼睛看路、雙手握住方向盤。comma 自己的警示和車輛的儀表永遠優先。CommaView 只會顯示 comma 看到的內容。
