---
title: "設定中途停止時的解決方法"
description: "CommaView 設定訊息的意思，依照設定進行的順序排列：SSH、安裝，再來是配對。找到您看到的訊息，以及該怎麼處理。"
topic: troubleshooting
order: 1
kind: fixes
lede: "設定會依序進行：先透過 SSH 登入您的 comma，再安裝 CommaView 的執行環境，然後讓您的手機和它配對。中途停止時，訊息會說明是哪個部分失敗，請先處理那個部分。SSH 能用只證明了第一步：執行環境沒有啟動時，配對碼不可能有效。"
parked: true
updated: 2026-11-27
needs:
  - title: "打入 P 檔"
    text: "車輛打入 P 檔、openpilot 未啟用，並保持發動：沒有常時供電線時，車輛熄火也會讓 comma 關機。"
  - title: "同一個網路"
    text: "您的手機和 comma 連上同一個 Wi‑Fi，或連上它的熱點。筆電連得到 comma，不代表手機也可以。"
steps:
  - id: read
    title: "閱讀設定的說明，並複製詳細資料"
    body: |
      安裝失敗時，設定會說明出了什麼問題、您的 comma 是否已還原為原本的狀態，以及該怎麼做。請在下方的[如果沒有成功](#fixes)中找到那句話。

      **複製詳細資料** 會複製支援人員要看的報告：App 的版本、發布版本、安裝程式的最後階段和完整輸出。訊息要求時，請把它貼到寄給 support@commaview.com 的電子郵件中。
    tabs:
      - label: "安裝失敗"
        body: "設定會說明失敗的原因，並提供 **複製詳細資料**。"
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**複製詳細資料**。"
          - target: install
            text: "排除原因後，輕觸 **安裝 CommaView** 再試一次。"
      - label: "SSH 失敗"
        body: "在安裝任何東西之前，設定會說明它為什麼無法登入 comma，例如 **SSH 驗證失敗**，以及要檢查什麼。"
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "出了什麼問題，以及要檢查什麼。"
  - id: address
    title: "檢查 comma 的位址"
    body: |
      設定會在您手機所在的網路上尋找 comma。如果清單中沒有您的那一台，請輕觸 **清單中沒有我的 comma**，輸入它的 IP 位址。在您的 comma 上，它位於 **設定 → 網路**：comma four 上在 Wi‑Fi 按鈕的網路名稱底下，comma 3X 上在 **進階** 中。

      comma 在每個網路上的位址都不同：家裡的 Wi‑Fi、熱點、VPN。請使用手機目前所在網路上的那個位址。
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "設定在這個網路上找到的 comma。"
      - text: "**清單中沒有我的 comma**：找不到時輸入 IP 位址。"
  - id: pair-code
    title: "用新的配對碼配對"
    body: |
      配對碼的有效時間很短，而且只能使用一次。如果被拒絕，不要再輸入同一組：請取得新的。手動安裝後，安裝程式會顯示一組；已經和 comma 配對的手機也可以在 **裝置設定 › 配對另一支手機或平板** 底下顯示一組。
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**comma IP 位址**。"
      - target: pair-code
        text: "**配對碼**。連字號可省略。"
  - id: runs
    title: "已經安裝過了？直接配對"
    body: |
      如果 comma 已經在執行 CommaView（來自另一支手機或之前的設定），就不需要重新安裝。在首頁輕觸 **新增 comma**，再輕觸 **輸入位址與配對碼**，用 comma 的 IP 和配對碼或邀請碼配對。
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "comma 的 IP。"
      - target: pair-code
        text: "**配對碼或邀請碼**。"
      - target: pair
        text: "**配對 comma**。"
  - id: no-video
    title: "已安裝並配對，但沒有影像"
    body: |
      配對完成後還是沒有畫面，是串流的問題，而不是 SSH 的問題。Live View 會說明它看到的情況，例如 **連不到這台 comma**，並在 comma 回應時自行重新連線。請看 [CommaView 找不到您的 comma](/zh-tw/guides/comma-not-found)。
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**重試**。"
fixes:
  - q: "「SSH 驗證失敗。」"
    a: "請確認 CommaView 金鑰已加入 GitHub（標題不拘），而且 comma 已開啟 SSH。如果您是在加入金鑰之前在 comma 上輸入 GitHub 使用者名稱，請移除後重新輸入，讓 comma 再取得一次您的金鑰。"
  - q: "「192.168.1.50:22 拒絕連線。請確認您的 comma 已啟用 SSH。」"
    a: "在 comma 上前往 **設定 → 裝置 → SSH**，開啟 SSH。"
  - q: "「連線到 … 逾時。」或「無法連到 …。」"
    a: "您的手機連不到那個位址。請確認手機和 comma 連上同一個 Wi‑Fi 或它的熱點、comma 處於喚醒狀態（車輛已發動），而且 IP 位址是 comma 在這個網路上的位址。"
  - q: "「在 … 找不到 comma。請檢查 IP 位址。」"
    a: "那個位址沒有任何回應。請在 comma 的 **設定 → 網路** 中確認 IP。"
  - q: "「這台 comma 的 SSH 身分自上次設定後已變更。」"
    a: "如果您重設或重新刷機過這台 comma，請重新執行設定。"
  - q: "「CommaView 無法在這支手機上建立 SSH 金鑰。請再試一次，或使用您自己的 SSH 金鑰。」"
    a: "輕觸 **重試**，或輕觸 **使用我自己的 SSH 金鑰**，匯入您在 GitHub 上已有的金鑰組。"
  - q: "「已排入安裝。」"
    a: "車輛正在行駛，所以 comma 沒有中斷行程，而是先排入安裝。請把車輛打入 P 檔並讓 openpilot 未啟用，讓車輛保持發動一兩分鐘，然後輕觸 **完成設定**。"
  - q: "「車輛正在行駛，因此沒有進行安裝。」"
    a: "請把車輛打入 P 檔並讓 openpilot 未啟用，再試一次。"
  - q: "「您的 comma 上已有另一項 CommaView 安裝、更新或修復正在執行。」"
    a: "請等幾分鐘讓它完成，再試一次。"
  - q: "「您的 comma 無法下載 CommaView。」"
    a: "執行環境是由 comma 自己下載的。請確認它已連上網際網路（透過 Wi‑Fi 或它自己的 SIM 卡），再試一次。使用行動數據的手機熱點也可以。"
  - q: "「您的 comma 收到的 CommaView 下載內容不完整或已損毀。」"
    a: "請再試一次。如果再次發生，請複製詳細資料並寄到 support@commaview.com。"
  - q: "「您的 comma 在安裝期間儲存空間不足。」"
    a: "請稍後再試。如果再次發生，請複製詳細資料並寄到 support@commaview.com。"
  - q: "「CommaView 尚不支援您 comma 上的駕駛軟體。」"
    a: "您的 comma 執行的軟體無法安裝 CommaView。[查看支援哪些分支版本](/zh-tw/guides/forks)。如果想要求支援您的軟體，請複製詳細資料並寄到 support@commaview.com。"
  - q: "「CommaView 無法安全地將其畫面加入 …」"
    a: "您的分支版本不在 CommaView 的清單中，檢查發現它的畫面在 CommaView 接入的地方有所不同。您 comma 上沒有任何變更。如果想要求支援您的分支版本，請複製詳細資料並寄到 support@commaview.com。"
  - q: "「不支援 comma 3」"
    a: "CommaView 支援 comma 3X 和 comma four。comma 3 的 openpilot 版本已在上游凍結，畫面的繪製方式也不同，因此 CommaView 無法顯示它的疊加圖層。"
  - q: "「安裝後，CommaView 沒有在您的 comma 上啟動。」"
    a: "請重新啟動 comma，再試一次。如果再次發生，請複製詳細資料並寄到 support@commaview.com。"
  - q: "「確認失敗。無法連上 192.168.1.50:5002 上的 CommaView API。」"
    a: "安裝已完成，但您的手機連不到執行環境。請確認手機仍在 comma 的網路上，再試一次。如果電腦可以用 SSH 連線、手機卻不行，表示電腦所在的網路手機不在上面。"
  - q: "「無法兌換配對碼。請產生新的配對碼後再試一次。」"
    a: "配對碼已過期、已被使用或輸入錯誤。請取得新的（[第 3 步](#step-pair-code)）。"
  - q: "「配對失敗：無法連上 CommaView 執行環境 API」"
    a: "您的手機無法透過那個位址連到 comma。請檢查熱點或網路，再試一次。"
  - q: "「重新啟動後 CommaView 不會自行啟動」"
    a: "CommaView 已安裝，但 comma 開機時沒有任何東西啟動它：您 comma 上的 `/data/continue.sh` 裡沒有 `exec ./launch_openpilot.sh` 這一行。加上這一行之後，請重新安裝 CommaView。"
related: [setup, comma-not-found, support-bundle]
---

## 設定會經過的各個部分

每個部分都依賴前一個，所以請依照這個順序檢查：

1. **SSH**，連接埠 22：設定登入 comma 進行安裝的方式。它需要您的 GitHub 金鑰、comma 上的 GitHub 使用者名稱，以及已開啟的 SSH。
2. **安裝**：comma 下載並安裝執行環境。請先看它的結果，再看後面的步驟。
3. **執行環境**，comma 上的連接埠 5002：設定會檢查它有回應，再和它配對。
4. **配對**：一次性配對碼讓您的手機取得這台 comma 專屬的金鑰。
5. **影像**，連接埠 8200 到 8202：Live View 的鏡頭畫面。

如果搜尋找不到 comma，但您知道它的位址，直接輸入也一樣有效：搜尋只是為了方便，能連到 comma 才是重點。

## 安全

請在車輛打入 P 檔且 openpilot 未啟用時進行設定、安裝和疑難排解。開車時絕對不要設定或操作 App。
