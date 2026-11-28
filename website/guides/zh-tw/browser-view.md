---
title: "在車上的瀏覽器中顯示 Live View"
description: "Browser View 會在車輛內建的網頁瀏覽器（包括 Tesla 的）中顯示 CommaView 的 Live View，由您的手機透過熱點提供。車上不需要安裝任何東西。"
topic: screens
order: 2
kind: walkthrough
lede: "**Browser View** 會在車輛內建的網頁瀏覽器中顯示 Live View 的畫面。由您的手機透過熱點或 Wi‑Fi 提供給車輛，所以車上不需要安裝任何東西。它是為 Tesla 這類有瀏覽器、卻沒有 CarPlay 或 Android Auto 的車輛設計的，任何能連到您手機的瀏覽器都能使用。"
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View 可以正常使用"
    text: "Android 手機上的 CommaView 已與您的 comma 配對。還沒有嗎？[設定 CommaView](/zh-tw/guides/setup)。"
  - title: "車上有瀏覽器"
    text: "Tesla、其他有網頁瀏覽器的車輛，或車上的平板、筆電。"
  - title: "同一個網路"
    text: "車輛和 comma 都連上您的手機熱點，或三者共同連上的任何網路。"
howItWorks:
  - title: "您的 comma"
    text: "像平常一樣把 Live View 傳到您的手機。"
  - title: "您的手機"
    text: "以網頁形式提供畫面，需要一組八位數代碼才能觀看。"
    edge: "熱點"
  - title: "車上的瀏覽器"
    text: "開啟網頁：每秒 20 格，720p 或 1080p，最多四個瀏覽器。"
steps:
  - id: hotspot
    title: "讓車輛連上您的手機熱點"
    body: |
      開啟手機熱點，然後在車輛的 Wi‑Fi 設定中連上它。請確認車輛連上的是您的手機，而不是它記住的其他 Wi‑Fi。如果 comma 還沒有連上這個熱點，也請讓它連上：您的手機仍然需要像平常一樣連接 comma。
    note: "**在 Tesla 上**，請先關閉手機的 Wi‑Fi，讓熱點分享行動數據。"
  - id: start
    title: "從 Live View 的「詳細資訊」開始 Browser View"
    body: |
      在手機上開啟 **Live View**，再輕觸 **詳細資訊**。靠近底部的 **Browser View** 卡片會說明它的用途，以及它會告訴 CommaView 什麼。輕觸 **開始**。
    screen: live-view-browser-view
    clip: browser-view-start
    pins:
      - target: browser-view-card
        text: "**Browser View** 卡片，在 **詳細資訊** 的底部附近。"
      - target: start-button
        text: "**開始**。第一次使用時，請給手機幾秒鐘取得憑證。"
      - target: privacy-policy
        text: "Browser View 執行時會告訴 CommaView 什麼，以及 **隱私權政策**。"
  - id: vpn
    title: "在 Tesla 上開啟 VPN 位址"
    tabs:
      - label: "Tesla"
        body: |
          Tesla 的瀏覽器無法開啟熱點分配的位址。在卡片上輕觸 **開啟 VPN 位址**，並在 Android 詢問是否允許 CommaView 設定 VPN 時允許。您的手機會取得一個 Tesla 能開啟的位址：`169.254.99.1`。它不傳輸任何流量，開啟期間其他 VPN App 都會關閉。
        screen: live-view-browser-view-vpn
        pins:
          - target: short-link
            text: "短網址，Tesla 也能用：**在車上的瀏覽器（包括 Tesla 的）中開啟**。"
          - target: vpn-address
            text: "手機在 VPN 位址上的位址：`169.254.99.1`。"
        note: "Android 對 VPN 的詢問沒有附圖：那是 Android 自己的畫面，每支手機看起來都不一樣。"
      - label: "其他車輛"
        body: |
          這一步不需要操作：其他車輛的瀏覽器可以開啟熱點的位址。請直接進行下一步。
  - id: open
    title: "在車上的瀏覽器輸入短網址"
    body: |
      卡片會顯示一個含有您八位數代碼的短網址，例如 `commaview.app/48291374`。在車上的瀏覽器輸入它，再輕觸 **開啟**。只要車輛連上網路、CommaView 也已登入，網頁就會找到您的手機，並透過安全連線開啟 Live View：會顯示鎖頭圖示、沒有警告，畫面也最流暢。
    screen: live-view-browser-view-on
    pins:
      - target: short-link
        text: "要在車上輸入的短網址，含有您的代碼。"
      - target: show-addresses
        text: "**車上沒有網路？顯示位址**：手機本身的位址。"
      - target: quality
        text: "**Browser View 畫質**：720p 或 1080p。"
      - target: stop-button
        text: "**停止** 會結束 Browser View。"
    warn: "**車上沒有網路？** 短網址需要網路。請改用手機本身的位址：請看[車上沒有網路](#車上沒有網路)。"
  - id: bookmark
    title: "把網頁加入書籤"
    body: |
      網頁的網址不會改變，所以下次車輛連上網路時，直接開啟書籤就好，不必再輸入短網址。
check: "手機上的卡片會顯示誰在觀看，以及車上瀏覽器正在繪製什麼，例如 **1 個瀏覽器正在觀看** 和 `Tesla 2025.20.6 · H.264 over HTTPS via the VPN name · 20 fps`。"
fixes:
  - q: "顯示「正在等待車上的瀏覽器」，但什麼都打不開"
    a: "請確認車輛連上的是您的手機熱點，而不是其他 Wi‑Fi。在 Tesla 上，請開啟 VPN 位址（[第 3 步](#step-vpn)）。"
  - q: "「開啟這支手機的熱點」"
    a: "手機既沒有連上 Wi‑Fi，也沒有開啟可以和車輛共用的熱點。只要其中一項開啟，5 秒內就會顯示位址。"
  - q: "短網址顯示 VPN 位址已關閉"
    a: "在卡片上開啟它，然後重新載入網頁。"
  - q: "出現無法略過的警告"
    a: "請在車輛連上網路時使用短網址，或使用基本畫質（[車上沒有網路](#車上沒有網路)）。"
  - q: "打入 D 檔後畫面停止"
    a: "開車時車上的瀏覽器是否繼續繪製畫面，由車廠決定。卡片上的回報列會顯示車輛繪製的內容（「0 fps · hidden」表示車輛停止了畫面）。請告訴我們您的車款和它的軟體版本：上路前開啟 **在這支手機上保存診斷資料**，之後再從「設定」傳送 **回報問題或提供建議**。"
related: [car-screens, ai-box, go-live]
blogPost: commaview-0-0-166-languages-browser-view
---

## 車上沒有網路

短網址需要車輛連上網路才能載入網頁，可以透過熱點的行動數據，也可以用車輛本身的網路連線。沒有網路時，請直接開啟手機本身的位址。在卡片上輕觸 **車上沒有網路？顯示位址**：

- **最佳畫質**：一個 HTTPS 位址，例如 `https://192.168.43.1:8443/48291374`。瀏覽器會先顯示警告，因為這個位址的憑證是手機自己簽署的：接受警告即可繼續。Tesla 的瀏覽器無法略過這個警告。
- **基本畫質**：同一個位址的 HTTP 版本，例如 `192.168.43.1:8090/48291374`。任何瀏覽器（包括 Tesla 的）都不會顯示警告，但畫質較低，也沒那麼流暢。

開啟 VPN 位址後，卡片會改為顯示它的位址：`https://169.254.99.1:8443/<code>` 和 `169.254.99.1:8090/<code>`。在沒有網路的 Tesla 上，請使用基本畫質的位址。

您手機熱點的位址可能和範例不同；卡片上顯示的一定是正確的位址，每一個旁邊都有複製按鈕。

## 卡片上的選項

- **Browser View 畫質：720p 或 1080p。** 1080p 比較清晰，但會占用更多手機和熱點的資源。您選擇之前預設為 720p。
- **隨 Live View 開始。** 每次開啟 Live View 時都會啟動 Browser View，如果 VPN 位址已開啟，也會一併使用。手動停止後，它會保持停止，直到 Live View 再次開啟。
- **新代碼。** 產生新的八位數代碼，讓別人看過的位址失效。請在車上開啟新的位址。
- **車上的控制項。** 錄影、保存片段和 Live View 的其他控制項會放在畫面下方或駕駛側，絕不會蓋住畫面。卡片上的 **車上的控制項** 可以關閉它們。
- **車內鏡頭畫面**：Live View 的 **車內鏡頭** 開啟時，車上也會顯示。

## 執行期間

- **手機鎖定時 Browser View 仍會繼續執行**，切換到其他 App 時也一樣。它的通知會顯示「正在 Browser View 中顯示 Live View」，通知中的 **停止** 可以結束它。
- **離開 Live View 就會結束它**，就像會結束直播和即時副本一樣。
- **在 Browser View 執行時直播** 會共用它的畫面。如果在 Browser View 單獨執行時開始直播，串流將沒有聲音：需要聲音時，請先停止 Browser View。

## 隱私權與安全性

- 畫面只會傳給連上您手機熱點或 Wi‑Fi、而且有代碼的瀏覽器。絕不透過行動數據傳送，也絕不經過 CommaView 的伺服器。
- 同一部裝置一分鐘內輸錯十次代碼，就會被擋一分鐘，已經在觀看的裝置不受影響。
- Browser View 執行期間，您的手機會把它的代碼、連接埠、VPN 位址是否開啟，以及熱點或 Wi‑Fi 的私人位址傳給 CommaView 的帳號服務，讓短網址能找到您的手機。有代碼的人都能看到這些資訊和您手機的 `commaview.app` 名稱，期間為 Browser View 執行時，以及意外停止後最多 2 小時；沒有您手機的熱點或 Wi‑Fi，這些資訊打不開任何東西。它們會在 Browser View 最後一次執行的 30 天後刪除。您手機的 `commaview.app` 名稱和最新憑證的日期會保留到您的帳號刪除為止。憑證是公開的，因此這個名稱會留在憑證透明度（Certificate Transparency）記錄中；它不會透露任何關於您、您的車輛或 comma 的資訊。詳情請看[隱私權政策](/privacy)。
- VPN 位址由您決定是否開啟，絕不會自行開啟，也不傳輸任何流量。

## 常見問題

**我需要 AI 盒或新的車機嗎？** 不需要。Browser View 使用車上原本就有的瀏覽器。如果您的車輛配備的是 CarPlay 或 Android Auto，[Android AI 盒](/blog/android-ai-box-commaview)可以直接在車上的螢幕執行 CommaView。

**會用到我的行動數據嗎？** 畫面不會：它透過熱點從手機傳到車上。短網址的網頁以及車輛本身使用熱點時會用到。

**可以用 comma 的熱點代替手機的嗎？** 大多數瀏覽器都可以：讓手機和車輛都連上 comma 的熱點，再開啟卡片上顯示的位址。Tesla 需要 VPN 位址，而它只適用於連上手機本身熱點的車輛。

## 安全

請在停車時設定好 Browser View，之後就別再操作。開車時請勿操作 CommaView：依照 openpilot 的要求，眼睛看路、雙手握住方向盤。comma 自己的警示和車輛的儀表永遠優先。CommaView 只會顯示 comma 看到的內容。
