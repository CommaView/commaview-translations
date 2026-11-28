---
title: "在 Live View 中觀看您的 comma"
description: "開啟 Live View，在手機上看 comma 的道路鏡頭畫面和行車畫面，並認識它的控制項、詳細資訊，以及出問題時它會顯示什麼。"
topic: screens
order: 1
kind: walkthrough
lede: "**Live View** 會即時顯示您 comma 的道路鏡頭畫面，並在上面畫出行車畫面：comma four 的、comma 3X 的，或 CommaView 自己的。畫面透過您自己的網路直接從 comma 傳來，不經過網際網路。"
parked: true
updated: 2026-11-27
needs:
  - title: "已設定好 CommaView"
    text: "Android 手機上的 CommaView 已與您的 comma 配對。還沒有嗎？[設定 CommaView](/zh-tw/guides/setup)。"
  - title: "車輛已發動"
    text: "openpilot 只在行駛狀態下傳送影像。車輛熄火時，Live View 會等待，車輛發動後自行開始。"
  - title: "同一個網路"
    text: "您的手機和 comma 連上同一個 Wi‑Fi 或熱點。在車上時，請看[在車上連線](/zh-tw/guides/connect-in-the-car)。"
steps:
  - id: open
    title: "從首頁開啟 Live View"
    body: |
      在 **首頁** 上，當您的 comma 已連線、車輛也已發動時，輕觸 **開啟 Live View**。幾秒內就會出現道路畫面，串流狀態標籤顯示 **即時**。
    screen: phone-home
    pins:
      - target: open-live-view
        text: "**開啟 Live View**，首頁的主要按鈕。"
    note: "車輛熄火時，Live View 會顯示 **您的 comma 已上線，但目前沒有在行駛**。車輛發動後它會自行開始，也可以輕觸 **重新整理** 立刻開始。"
  - id: controls
    title: "認識畫面下方的控制項"
    body: |
      直拿手機時，控制項位於影像下方：

      - **錄影** 會儲存這一段行程。請看[錄下行程](/zh-tw/guides/record)。
      - **保存** 會保留行程中剛過去的 3 分鐘和接下來的 1 分鐘。
      - 行車畫面切換按鈕以目前顯示的畫面命名（**CommaView**、**comma 4**、**comma 3X**），每輕觸一次就切換到下一個。請看[選擇行車畫面](/zh-tw/guides/overlays)。
      - **直播** 會串流 Live View 顯示的內容，需要先完成設定。請看[直播](/zh-tw/guides/go-live)。
      - **車內鏡頭** 會在畫面一角顯示車內鏡頭畫面。
      - **詳細資訊** 會開啟 Live View 的各項資訊和卡片。

      以您手機的寬度和文字大小放不下的控制項會收進 **更多**。不會縮小或裁掉任何內容。
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**錄影**。"
      - target: onroad-screen-button
        text: "行車畫面切換按鈕。"
      - target: driver-cam-button
        text: "**車內鏡頭**。"
      - target: go-live-button
        text: "**直播**，設定好直播後才會出現。"
      - text: "**更多** 裡是放不下的控制項。"
    note: "錄影進行中時，行車畫面切換按鈕和 **車內鏡頭** 會變暗：請在輕觸 **錄影** 之前選好。"
  - id: details
    title: "開啟詳細資訊"
    body: |
      輕觸 **詳細資訊**，或把螢幕底部的面板往上拉。它會顯示串流狀況、影像、執行環境、comma 的軟體和位址、是否正在錄影或串流，以及 **Browser View** 卡片。其中的連結可以開啟 **錄影** 和 comma 的 **裝置設定**。
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**詳細資訊** 面板。"
      - text: "摘要：串流狀態、影像和執行環境。"
      - target: recordings-link
        text: "**錄影**。"
      - target: device-settings-link
        text: "這台 comma 的 **裝置設定**。"
  - id: turn
    title: "把手機轉成橫向，或使用更大的螢幕"
    body: |
      把手機轉成橫向，影像就會填滿螢幕，控制項位於駕駛側的側欄中。**詳細資訊** 會在畫面旁開啟，**離開** 則會離開 Live View。
    tabs:
      - label: "橫向手機"
        body: "側欄中是同樣的控制項。螢幕較矮時會變得精簡。"
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "**錄影**，在側欄頂端。"
          - target: more
            text: "**更多** 裡有 **車內鏡頭** 和 **詳細資訊**。"
          - target: exit
            text: "**離開** 會離開 Live View。"
      - label: "平板或車用螢幕"
        body: "在寬螢幕上，側欄會維持在駕駛側。請看[在車用螢幕上使用 CommaView](/zh-tw/guides/car-screens)。"
        screen: car-live-view
        pins:
          - target: record-button
            text: "**錄影**。"
          - target: onroad-screen-button
            text: "行車畫面切換按鈕。"
          - target: driver-cam-button
            text: "**車內鏡頭**。"
          - target: details
            text: "**詳細資訊**。"
          - target: exit
            text: "**離開**。"
  - id: auto
    title: "讓 Live View 自動開啟"
    body: |
      如果某支手機或車機只用來顯示 Live View，請開啟 **設定 › 顯示**，在 **開啟 Live View** 底下開啟 **連線時開啟 Live View**。這樣車輛發動後，comma 一連線，Live View 就會自動開啟。手動離開後，它會保持關閉，直到下一次。

      緊接在下方的 **保留狀態列** 會在 Live View 上方顯示系統時鐘，而不是占滿整個螢幕。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**連線時開啟 Live View**。"
  - id: leave
    title: "用完後離開 Live View"
    body: |
      停好車後輕觸 **離開** 或返回。離開 Live View 也會結束直播、Browser View 和即時副本。同一時間只有一支手機或一台車機能開啟 Live View，所以請先在一部上離開，再到另一部上開啟。
check: "串流狀態標籤顯示 **即時**，道路畫面在動，詳細資訊中的串流狀態顯示 **良好**。"
fixes:
  - q: "「您的 comma 已上線，但目前沒有在行駛」"
    a: "車輛已熄火，或 openpilot 還沒啟動。車輛發動後 30 秒內 Live View 會自行恢復，也可以輕觸 **重新整理**。"
  - q: "「連不到這台 comma」"
    a: "您的手機必須和 comma 連上同一個 Wi‑Fi，或連上它的熱點。comma 有回應時 Live View 會重新連線，也可以輕觸 **重試**。還是不行？請看 [CommaView 找不到您的 comma](/zh-tw/guides/comma-not-found)。"
  - q: "「Live View 已在另一部裝置上開啟」"
    a: "您的 comma 一次只會串流到一支手機或一台車機。在另一部裝置的 CommaView 回到首頁，這裡的 Live View 就會自行開始。"
  - q: "「收不到車輛資料」"
    a: "影像收得到，但車速、方向燈和警示收不到。重新啟動 comma 即可解決。"
  - q: "「影像延遲」"
    a: "已經一秒沒有收到新的影格。Live View 會在畫面旁提示，如果影像沒有恢復，它會自行重新連線。"
  - q: "「無法播放這台 comma 的影像」"
    a: "手機上沒有任何影像解碼器能播放它。CommaView 會繼續嘗試。請從「設定」傳送支援回報，讓 CommaView 調查：請看[傳送支援回報](/zh-tw/guides/support-bundle)。"
related: [overlays, record, browser-view, car-screens]
---

## 安全

請在停車時開啟 Live View，之後就別再操作。開車時請勿操作 CommaView：依照 openpilot 的要求，眼睛看路、雙手握住方向盤。comma 自己的警示和車輛的儀表永遠優先。CommaView 只會顯示 comma 看到的內容。
