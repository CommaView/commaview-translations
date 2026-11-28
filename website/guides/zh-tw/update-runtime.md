---
title: "更新您 comma 的執行環境"
description: "從首頁或裝置設定更新您 comma 上的 CommaView 執行環境。安全更新會等車輛打入 P 檔，所以更新絕不會中斷行程。"
topic: account
order: 1
kind: walkthrough
lede: "您 comma 上的 CommaView 執行環境只會從 App 更新，絕不會自行更新。請先更新 CommaView，等 App 提供執行環境更新時再更新執行環境。如果車輛正在行駛，**安全更新** 會先在 comma 上排入更新，等車輛打入 P 檔且 openpilot 未啟用時再安裝。"
updated: 2026-11-27
needs:
  - title: "手機和 comma 在一起"
    text: "和 comma 連上同一個 Wi‑Fi，或連上它的熱點。"
  - title: "車輛已發動"
    text: "請讓車輛保持發動並打入 P 檔。沒有常時供電線時，車輛熄火也會讓 comma 關機。"
howItWorks:
  - title: "CommaView"
    text: "每個 App 版本都會指明與它一起測試過的執行環境，並只提供那一個。"
  - title: "您的 comma"
    text: "在車輛打入 P 檔後下載、檢查並安裝它。"
    edge: "重新啟動"
  - title: "Live View"
    text: "comma 重新啟動後再次開始。"
steps:
  - id: app-first
    title: "先更新 CommaView"
    body: |
      App 會安裝與它一起測試過的執行環境，所以請先更新 App，再更新執行環境。有更新時，首頁頂端和設定 › **關於** 中會顯示 **更新**。輕觸它：**更新 CommaView** 會顯示版本號碼、發布管道和大小。輕觸 **下載**；CommaView 會在背景下載並檢查，接著由 Android 請您確認安裝。
    screen: app-update-offer
    pins:
      - target: download
        text: "**下載**。"
      - target: channel
        text: "版本的發布管道：**Beta**，或給測試人員的 **Alpha**。"
    note: "更新這台 comma 的執行環境之前，請先更新每一支觀看它的手機、平板和車用螢幕上的 CommaView。"
  - id: open
    title: "開啟執行環境更新"
    tabs:
      - label: "從首頁"
        body: "這台 comma 有新的執行環境時，首頁會顯示 **執行環境更新已就緒**。輕觸 **查看更新**：**執行環境更新** 卡片會顯示 **已安裝** 和 **可用** 的版本，以及車輛是否準備好了。輕觸 **更新執行環境**；車輛行駛中則輕觸 **排入更新**。"
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**執行環境更新**：已安裝、可用，以及車輛是否準備好了。"
          - target: update-runtime
            text: "**更新執行環境**（車輛行駛中為 **排入更新**）。"
      - label: "從裝置設定"
        body: "開啟 comma 的 **裝置設定**，再輕觸 **執行環境**（有更新時會顯示 **更新**）。頁面會顯示已安裝的和可用的執行環境。輕觸 **立即更新**。"
        screen: device-runtime
        pins:
          - target: update-now
            text: "**立即更新**。"
  - id: install
    title: "安裝，或讓安全更新先排入"
    body: |
      從裝置設定進入時，**執行環境更新** 對話方塊會說明車輛是否準備好了。
    tabs:
      - label: "車輛已打入 P 檔"
        body: "它會顯示「車輛已打入 P 檔，openpilot 未啟用。可以安全開始更新執行環境。」輕觸 **安裝更新**。"
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**安裝更新**。"
          - target: close
            text: "**關閉** 則留到之後再處理。"
      - label: "車輛行駛中"
        body: "它會顯示「車輛行駛中。安全更新會先在 comma 上排入更新，等車輛打入 P 檔且 openpilot 未啟用時再安裝。」輕觸 **安全更新…**，閱讀說明，等短暫的倒數結束後輕觸 **開始安全更新**。如果 CommaView 無法確認車輛是否正在行駛，也會這樣處理。"
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**安全更新…**，再輕觸 **開始安全更新**。"
    note: "CommaView 絕不會停止 openpilot 或您的分支版本：排入的更新會等車輛打入 P 檔，行程絕不會被中斷。"
  - id: progress
    title: "讓它執行"
    body: |
      comma 會下載新版本，檢查它完整且未遭竄改，安裝後重新啟動 CommaView，App 會顯示每個步驟。您可以切換 App 或鎖定手機：更新會繼續進行，它的通知會顯示進度。

      在 comma 開始安裝之前，**取消更新** 可以停止它，您 comma 上的任何東西都不會改變。
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "各個步驟：下載、驗證、安裝、重新啟動 CommaView、重新連線。"
  - id: queued
    title: "排入的更新會等車輛打入 P 檔"
    body: |
      排入的更新會在首頁的 **執行環境更新** 卡片上顯示為 **等待車輛打入 P 檔**。車輛打入 P 檔幾秒、且 openpilot 未啟用後，它就會安裝。安裝期間請讓車輛保持發動。
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "**等待車輛打入 P 檔**，以及目前的步驟。"
  - id: reboot
    title: "重新啟動 comma 以完成"
    body: |
      執行環境更新後，comma 需要重新啟動，CommaView 才能再次從它串流：openpilot 只有在 comma 重新啟動時，才會載入 CommaView 新的畫面程式碼。App 絕不會自行重新啟動它。

      請在車輛熄火或打入 P 檔時，輕觸首頁卡片上的 **重新啟動 comma**，或對話方塊中的 **立即重新啟動 comma**。openpilot 會停止約一分鐘。您也可以在 comma 上重新啟動：**設定 → 裝置 → 重新啟動**。
check: "更新的最後一步顯示 **已更新**，裝置設定中新的執行環境顯示 **已是最新版本**。重新啟動後，Live View 會連同疊加圖層一起播放。"
fixes:
  - q: "「這台 comma 的執行環境比這個 App 所安裝的還新」"
    a: "請更新 CommaView，再試一次。comma 上沒有任何變更。"
  - q: "「需要更新」"
    a: "這個 App 和這台 comma 的執行環境對彼此來說都不夠新。請先更新 CommaView，再更新執行環境。"
  - q: "「comma 沒有安裝 …：它執行的是 CommaView 未列出的 …」"
    a: "comma 沒有變更任何東西，保留了原本的執行環境。如果想以盡力支援的方式把 CommaView 加入那個分支版本，請為這台 comma 重新執行設定：它會檢查分支版本並先詢問您。"
  - q: "「每次開始時車輛都再次發動，因此 comma 停止嘗試」"
    a: "請把車輛打入 P 檔並讓 openpilot 未啟用，再試一次。"
  - q: "「執行環境更新已還原」"
    a: "comma 還原了原本的執行環境。請再試一次；如果還是失敗，請[傳送支援資料包](/zh-tw/guides/support-bundle)。"
  - q: "「CommaView 已在更新或解除安裝執行環境」"
    a: "同一時間只能執行一項執行環境工作。請等它完成後再試一次。"
  - q: "更新後沒有疊加圖層或遙測資料"
    a: "comma 還沒有重新啟動。請在車輛熄火或打入 P 檔時重新啟動它。"
related: [releases, uninstall, another-phone]
---

## 為什麼更新要等車輛打入 P 檔

安裝執行環境時，comma 上的 CommaView 會在替換檔案期間停止，並重新啟動它的服務，所以 comma 只會在車輛打入 P 檔且 openpilot 未啟用時進行。安全更新不會要求 openpilot 進入停車狀態：它會在 comma 上排入這項工作，由 comma 在車輛打入 P 檔後執行。您不需要熄火；保持發動並打入 P 檔即可。

在變更 comma 上的任何東西之前，它會先下載新版本，並檢查它完整且未遭竄改。如果之後安裝失敗，comma 會還原原本的執行環境。
