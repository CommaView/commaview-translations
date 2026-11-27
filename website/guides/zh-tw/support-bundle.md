---
title: "傳送支援資料包"
description: "讓診斷資料保持開啟，重現問題，再從設定 › 支援與診斷傳送一份附上手機和 comma 記錄的回報。"
topic: troubleshooting
order: 3
kind: walkthrough
lede: "支援資料包是一個小小的 zip 檔，內容是 CommaView App 在您手機上看到的情況，以及它的執行環境在您 comma 上看到的情況。有了它，我們不必坐進您的車也能找出問題。它只有記錄：沒有影片，也沒有位置。"
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "診斷資料已開啟"
    text: "**在這支手機上保存診斷資料** 預設為開啟，除非有人把它關掉。請在問題再次發生之前確認一下。"
  - title: "已連上您的 comma"
    text: "要附上 comma 的記錄，傳送時首頁需要顯示您的 comma **已連線**。"
  - title: "登入才能傳送"
    text: "傳送需要您的 Beta 帳號。未登入時，**儲存為檔案** 仍然可以使用。"
howItWorks:
  - title: "您的手機"
    text: "保留最近 10 段行程的記錄和計數器。"
  - title: "您的 comma"
    text: "在您輕觸「傳送」時加入它執行環境的記錄，並移除位置、VIN、各種 ID、Wi‑Fi 名稱和權杖。"
    edge: "輕觸「傳送」時"
  - title: "CommaView 團隊"
    text: "在私人儲存空間中查看，並以電子郵件回覆。"
steps:
  - id: open
    title: "開啟支援與診斷"
    body: |
      在 CommaView 中，輕觸底部導覽列的 **設定**。在平板或車機上，它在旁邊的側欄中。輕觸靠近底部、位於「關於」之前的 **支援與診斷**。
    screen: support-settings
    pins:
      - text: "**支援與診斷**。"
  - id: keep-diagnostics
    title: "在這支手機上保存診斷資料"
    body: |
      **在這支手機上保存診斷資料** 預設為開啟，除非有人把它關掉：App 會保留最近 10 段行程的記錄和計數器，讓回報能說明發生了什麼事。如果它是關閉的，請開啟它，再重現問題。
    screen: support-diagnostics
    pins:
      - target: keep-diagnostics
        text: "**在這支手機上保存診斷資料**。"
    note: "診斷資料會一直留在這支手機上，直到您傳送回報：它們絕不會自動上傳。"
  - id: happen-again
    title: "在停車時重現問題"
    body: |
      像平常一樣連上您的 comma：手機連上 comma 的 Wi‑Fi 或熱點，首頁顯示您的 comma **已連線**。重複出問題的操作；例如開啟 Live View，切換到有問題的行車畫面，並停留 10 到 20 秒。大概記下發生的時間和您做了什麼。螢幕錄影也很有幫助。
    warn: "請在打入 P 檔時重現問題。如果它只在路上發生，就讓它發生，停好車後再傳送回報：記錄會等著您。開車時絕對不要操作 App。"
  - id: open-send
    title: "開啟「傳送給 CommaView」"
    body: |
      在 **支援與診斷** 中輕觸 **回報問題或提供建議**。

      也可以從問題本身開始：App 顯示失敗的地方，輕觸它的 **回報**；如果是某段錄影，在它的 **錄影動作** 中選擇 **傳送給 CommaView…**。它們都會開啟同一個面板，並預先填好相關內容。
    screen: support-diagnostics
    pins:
      - target: report
        text: "**回報問題或提供建議**。"
  - id: send
    title: "選擇要附上的內容，然後傳送"
    body: |
      選擇 **問題**，並描述發生了什麼事。在 **附件** 底下，讓 **這支手機的診斷資料** 和您 comma 的記錄保持開啟。**查看** 會清楚顯示每一項包含的內容。在這些列下方，面板會列出每份回報都會附上的資訊：App 版本、手機型號和 Android 版本，以及您 comma 的駕駛軟體和設定。

      輕觸 **傳送**：「正在傳送。它會在背景進行，並等待連線。」
    screen: support-send-feedback
    pins:
      - target: problem
        text: "**問題** 或 **想法**。"
      - text: "**附件**：每一列都有一個開關和 **查看**。"
      - target: send
        text: "**傳送**。"
    note: "請在 App 連著您的 comma 時傳送：它會在您輕觸「傳送」時向 comma 索取記錄。如果 comma 已關機或連不到，資料包會說明原因，並仍然包含 App 自己的記錄。"
  - id: save-file
    title: "或是儲存為檔案"
    body: |
      支援人員要的是檔案本身，或是您沒有登入？請輕觸 **儲存為檔案**，而不是「傳送」。App 會產生同樣的資料包，一個小小的 `.zip`，並開啟 Android 的分享選單。把它傳到支援人員指定的地方：Discord 私訊、電子郵件或雲端硬碟連結。
    screen: support-share-bug-report
    pins:
      - target: save-file
        text: "**儲存為檔案**。"
  - id: afterwards
    title: "閱讀我們的回覆"
    body: |
      我們回覆時，回覆會以電子郵件寄出，也會和您的回報一起出現在 my.commaview.com 的 [Your feedback](https://my.commaview.com/feedback) 中。在我們結案之前，請在那裡回覆我們；結案後 30 天內您還可以重新開啟。**支援與診斷** 中的 **您的請求** 也會列出它們。
    screen: support-diagnostics
    pins:
      - target: your-requests
        text: "**您的請求**：回覆以及您和 CommaView 的對話。"
check: "面板關閉時顯示「正在傳送。它會在背景進行，並等待連線。」，傳送完成後，回報會出現在 **您的請求** 底下。"
fixes:
  - q: "資料包裡沒有 comma 的記錄"
    a: "您輕觸「傳送」時 App 連不到您的 comma，或 **附件** 底下它那一列是關閉的。開啟「傳送給 CommaView」之前，請確認首頁顯示您的 comma **已連線**，並讓 comma 那一列保持開啟。如果 App 要求您重新配對 comma，請先配對，再傳送一次。"
  - q: "「傳送」按鈕顯示 **登入以傳送**"
    a: "您已登出。輕觸它，用您的 Beta 帳號登入，或使用 **儲存為檔案**。"
  - q: "「附件超過一份回報可攜帶的 25 MB。請關閉其中一項，或使用『儲存為檔案』。」"
    a: "關閉不需要的附件，或輕觸 **儲存為檔案**，再把檔案傳到支援人員指定的地方。"
  - q: "輕觸「儲存為檔案」沒有反應"
    a: "這部裝置上沒有能接收檔案的 Android App。這在車機上很常見。請改為把它[傳送](#step-send)給 CommaView，或從執行 CommaView 的手機上儲存。"
  - q: "「無法準備回報。請檢查本機儲存空間後再試一次。」"
    a: "App 無法寫入資料包，通常是因為裝置的儲存空間不足。請釋出一些空間後再試一次。"
related: [setup-troubleshooting, comma-not-found, releases]
---

## 支援資料包裡有什麼

- **這支手機的診斷資料。** CommaView 在這支手機上的診斷記錄和計數器：影像串流、繪製、連線和錄影錯誤，以及 App 版本、手機型號和 Android 版本。使用導航時，還包括每種地點搜尋成功或失敗的次數，絕不包括您搜尋的內容。
- **您 comma 的記錄。** 在您 comma 那一列開啟時：CommaView 執行環境的記錄、計數器和設定，哪些 openpilot 程序停止了和停止的原因，以及 comma 核心中的記憶體不足記錄。
- **絕不會放進資料包的內容。** 沒有影片、沒有 GPS 位置、沒有 VIN，也沒有原始行程遙測資料：您傳送的錄影會放在資料包旁邊，而不是裡面。最新的 comma 執行環境在傳送記錄之前，會移除 GPS 座標、VIN、Wi‑Fi 名稱、公用 IP 位址、權杖和完整的 dongle ID。
- **只在您傳送時。** 只有當您輕觸「傳送」或「儲存為檔案」時，資料包才會離開您的手機。您儲存的檔案只會去您傳送的地方。區域 IP 位址、工作階段 ID 和版本資訊可能仍會保留，所以請只和您信任的人分享資料包。

## 它會去哪裡、保留多久

您傳送的資料包會進入 CommaView 的私人儲存空間，只有 CommaView 團隊能開啟。它會在您傳送 180 天後刪除；如果您提出要求或刪除帳號，則會提早立即刪除（[隱私權](/privacy)）。如需提出要求，請寄電子郵件到 support@commaview.com。

要刪除 App 在這支手機上保留的內容，請在 **支援與診斷** 中輕觸 **清除本機診斷資料**。它絕不會刪除您的錄影。如果從現在起只想保留錄影錯誤的紀錄，請在同一個頁面關閉 **在這支手機上保存診斷資料**。

不確定要傳到哪裡？請到 [CommaView Discord](https://discord.gg/UuMhz9K8ft) 發問。
