---
title: "CommaView 找不到您的 comma"
description: "首頁顯示「離線」，或 Live View 連不到您的 comma？請依序檢查網路、comma 的位址和配對。"
topic: troubleshooting
order: 2
kind: fixes
lede: "CommaView 透過區域網路直接和您的 comma 溝通，中間沒有任何雲端服務。找不到它時，幾乎都是因為手機和 comma 不在同一個網路、車輛熄火後 comma 進入休眠，或它的位址變了。請先檢查這幾項，再檢查配對。"
parked: true
updated: 2026-11-27
needs:
  - title: "車輛已發動"
    text: "車輛熄火時 comma 會進入休眠。請發動車輛並打入 P 檔。"
  - title: "同一個網路"
    text: "您的手機和 comma 連上同一個 Wi‑Fi，或連上它的熱點。在車上：[在車上連線](/zh-tw/guides/connect-in-the-car)。"
steps:
  - id: home
    title: "看看首頁顯示什麼"
    body: |
      手機連不到 comma 時，首頁會顯示它 **離線**，並提供 **重新連線** 和一張 **無法連線？** 卡片：「這支手機必須與 comma 連上相同的 Wi‑Fi，或連上它的熱點。車輛熄火時 comma 會進入休眠。」

      檢查這兩項，然後輕觸 **重新連線**。
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**重新連線**。"
      - target: cant-connect
        text: "**無法連線？** 卡片。"
  - id: live-view
    title: "在 Live View 中：等待或重試"
    body: |
      Live View 會說明它停止的原因。**連不到這台 comma** 表示您的手機無法在網路上連到它。comma 有回應時它會自行重新連線；**重試** 會立刻再試一次。
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**連不到這台 comma**：Live View 停止的原因。"
      - target: retry
        text: "**重試**。"
  - id: network
    title: "檢查手機的網路"
    body: |
      開啟手機的 Wi‑Fi 設定，確認它連上的是 comma 所在的網路：同一個家用 Wi‑Fi、已讓 comma 連上的手機熱點，或 comma 自己的熱點。

      - 手機如果因為某個 Wi‑Fi 沒有網路而改用行動數據，就連不到 comma。請重新連上那個 Wi‑Fi。
      - 手機上的 VPN 可能會把流量導到別處。請關閉後再試一次。
      - 有些熱點會阻止連上的裝置彼此連線。請換一個網路試試，例如 comma 自己的熱點。
    note: "Android 的 Wi‑Fi 和熱點設定沒有附圖：每支手機看起來都不一樣。"
  - id: address
    title: "檢查 comma 的位址"
    body: |
      comma 連上其他網路，或路由器分配新位址給它時，它的位址就會改變。CommaView 在網路上看到它時會自行重新找到它；如果沒有，請自己儲存它的位址。

      在 comma 上，到 **設定 → 網路** 找到它的 IP 位址。在 CommaView 中，從首頁開啟 **裝置設定**，輕觸 **變更名稱或位址**，再編輯 **IP 位址**，輸入 comma 的位址並輕觸 **儲存**。
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "comma 的 IP 位址。"
      - target: save
        text: "**儲存**。"
  - id: add
    title: "還是找不到？重新新增"
    body: |
      在首頁輕觸 **新增 comma**。**在這個網路上** 會列出手機所在網路中執行 CommaView 的 comma：輕觸您的那一台。如果沒有，請輕觸 **輸入位址與配對碼**，或在已經和它配對的手機上使用 **掃描 QR 碼**。
    screen: add-comma
    pins:
      - target: found-comma
        text: "**在這個網路上**：在附近找到的 comma。"
      - target: enter-address
        text: "**輸入位址與配對碼**。"
      - target: scan-qr
        text: "**掃描 QR 碼**。"
  - id: pair
    title: "用它的位址和新的代碼配對"
    body: |
      輸入 comma 的 IP，以及配對碼或邀請碼，然後輕觸 **配對 comma**。代碼很快就會過期：已經和 comma 配對的手機可以在 **裝置設定** 的 **配對另一支手機或平板** 底下顯示新的代碼。
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "comma 的 IP。"
      - target: pair-code
        text: "**配對碼或邀請碼**。"
      - target: pair
        text: "**配對 comma**。"
    note: "如果輸入位址就能連線，但 comma 從來不會自動出現，表示網路擋住了 CommaView 的搜尋功能。這沒關係：重點是位址。"
check: "首頁顯示您的 comma **已連線**，**開啟 Live View** 也能開啟畫面。"
fixes:
  - q: "「連不到這台 comma」"
    a: "您的手機必須和 comma 連上同一個 Wi‑Fi，或連上它的熱點。comma 有回應時 Live View 會重新連線。請檢查網路（[第 3 步](#step-network)）和 comma 的位址（[第 4 步](#step-address)）。"
  - q: "「CommaView 沒有回應」"
    a: "comma 有回應，但上面的 CommaView 沒有。它可能正在 comma 上重新啟動：恢復後 Live View 會重新連線。如果一直如此，請在停車時重新啟動 comma。"
  - q: "「這台 comma 沒有影像」"
    a: "它有回應，但影像沒有傳回來。請重試，或返回檢查 comma：openpilot 可能還在啟動。"
  - q: "「Live View 已在另一部裝置上開啟」"
    a: "這台 comma 一次只會串流到一支手機或一台車機。在另一部裝置的 CommaView 回到首頁，這裡的 Live View 就會自行開始。"
  - q: "「comma 沒有及時回應。」"
    a: "連線訊號弱或網路忙碌。請確認手機連上的是 comma 的 Wi‑Fi 或熱點，盡量靠近一點，再重試。"
  - q: "「comma 拒絕了連線。CommaView 可能正在它上面重新啟動。」"
    a: "稍等一下讓它恢復，再重試。"
  - q: "「收不到車輛資料」"
    a: "影像收得到，但車速、方向燈和警示收不到。重新啟動 comma 即可解決。"
  - q: "「配對失敗：配對碼已過期。請產生新的配對碼後再試一次。」"
    a: "請在已經和 comma 配對的手機上，從 **裝置設定 › 配對另一支手機或平板** 取得新的代碼，再重新配對。"
  - q: "「配對失敗：配對碼無效。請檢查配對碼或掃描 QR 碼。」"
    a: "請檢查您輸入的代碼（連字號可省略），或改為掃描它的 QR 碼。"
  - q: "「更新這台 comma 的執行環境」或「更新 CommaView」"
    a: "這個 App 和 comma 的執行環境版本差太多，無法溝通。請更新它指出的那一項：從裝置設定更新執行環境（[更新執行環境](/zh-tw/guides/update-runtime)），或更新 App。"
  - q: "「無法讀取您已儲存的 comma」"
    a: "無法讀取這支手機上已儲存的 comma，所以一台也沒有顯示。它們並沒有被刪除。請再試一次，或輕觸 **重新開始** 並重新配對每一台 comma：舊的清單至少會保留 90 天。"
related: [connect-in-the-car, setup-troubleshooting, another-phone]
---

## CommaView 如何找到 comma

- **搜尋**：在手機所在的網路中尋找執行 CommaView 的 comma，讓您不必輸入位址。有些網路會擋住搜尋。
- **位址**：CommaView 實際連線的目標。不論搜尋是否有效，輸入位址都能連線。
- **配對**：用一組短時間有效的代碼，讓您的手機取得這台 comma 專屬的金鑰。搜尋和配對是兩回事：手機連得到的 comma 仍然需要配對。
- **已儲存的 comma**：CommaView 透過它的身分而不只是位址來辨識它，所以它以新位址出現時，CommaView 會更新已儲存的那一台。

## 安全

請在停車時檢查網路和配對。開車時請勿操作 CommaView。
