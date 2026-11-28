---
title: "設定 CommaView"
description: "在 Android 上安裝 CommaView App，準備好您的 comma 3X 或 comma four，再讓引導設定安裝執行環境並配對您的 comma。"
topic: start
order: 1
kind: walkthrough
lede: "CommaView 有兩個部分：您 Android 手機、平板或車機上的 App，以及 comma 上的小型執行環境。先安裝 App，再由 App 中的引導設定把執行環境裝到 comma 上、加以檢查並完成配對。整個過程只要幾分鐘，請在車輛打入 P 檔、openpilot 未啟用時進行。"
parked: true
updated: 2026-11-27
needs:
  - title: "一台 comma 3X 或 comma four"
    text: "執行 openpilot 或[支援的分支版本](/zh-tw/guides/forks)。不支援 comma 3：它的 openpilot 版本已在上游凍結，畫面的繪製方式也不同，因此 CommaView 無法顯示它的疊加圖層。[為什麼不支援 comma 3](/#faq-comma-3)。"
  - title: "一部 Android 裝置和您的邀請"
    text: "Android 8 以上版本，以及收到邀請的電子郵件地址。CommaView 目前是 Beta 版：請用受邀的帳號登入。"
  - title: "同一個網路"
    text: "您的手機和 comma 在同一個區域網路中：您的 Wi‑Fi、手機熱點、comma 自己的熱點，或兩者都能連上的其他網路。人在車上？請看[不用家裡的 Wi‑Fi，在車上連線](/zh-tw/guides/connect-in-the-car)。"
  - title: "一個 GitHub 帳號"
    text: "comma 會接受您提供的 GitHub 使用者名稱底下的 SSH 金鑰。金鑰由 CommaView 產生，您在設定過程中把它加入 GitHub。"
howItWorks:
  - title: "您的手機"
    text: "產生一把 SSH 金鑰，由您加入 GitHub。"
    edge: "SSH"
  - title: "您的 comma"
    text: "從您的 GitHub 使用者名稱取得金鑰。CommaView 會在您的分支版本旁安裝它的執行環境。"
    edge: "區域網路"
  - title: "CommaView"
    text: "檢查執行環境有回應，並儲存您的 comma。之後它會自行重新連線。"
steps:
  - id: get-the-app
    title: "取得 App 並登入"
    body: |
      在您的 Android 裝置上，用收到邀請的電子郵件地址登入 [my.commaview.com](https://my.commaview.com)。在 **Get the app** 底下輕觸 **Download CommaView**。如果想驗證檔案，旁邊會顯示它的 SHA-256 校驗碼。

      開啟下載的檔案。Android 會請您允許從瀏覽器安裝 App：只為這次安裝允許，裝好後再關閉。

      開啟 CommaView。它會詢問一次是否要 **協助改善 CommaView**：選擇 **傳送** 或 **不傳送**。接著它會請您登入：輕觸 **登入**，並使用收到邀請的電子郵件地址。之後只要存取通行證有效，它就能離線使用。
    tabs:
      - label: "協助改善 CommaView"
        body: "當機回報，以及您的 comma 執行的駕駛軟體，絕不包含影片、行程、地點或名稱。您隨時可以在設定 › **隱私權與分享** 中變更。"
        screen: improve-commaview
        pins:
          - target: send
            text: "**傳送** 當機回報，協助修正問題。"
          - target: dont-send
            text: "**不傳送** 則讓回報留在手機上。"
      - label: "登入"
        body: "Beta 期間，CommaView 需要您受邀的帳號。**登入** 會開啟您的瀏覽器。"
        screen: sign-in
        pins:
          - target: sign-in
            text: "用收到邀請的電子郵件地址 **登入**。"
    note: "要裝在車機上，或接在車上螢幕的 AI 盒上？[車用螢幕](/zh-tw/guides/car-screens) 說明了它的網路設定，以及如何與您的 comma 配對。"
  - id: connect
    title: "開始設定您的 comma"
    body: |
      閱讀注意事項，勾選表示您了解這是非官方軟體、並由您負責安全使用，然後輕觸 **我了解 — 繼續**。

      在 **連接您的 comma** 畫面，輕觸 **在您的 comma 上設定 CommaView**。
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**在您的 comma 上設定 CommaView**，適用於還沒有執行 CommaView 的 comma。"
      - target: pair-runs
        text: "已經透過另一支手機執行 CommaView？請改用 **配對已執行 CommaView 的 comma**：請看[新增另一支手機或平板](/zh-tw/guides/another-phone)。"
  - id: setup-path
    title: "選擇設定方式"
    tabs:
      - label: "引導設定"
        body: "選擇 **引導設定**（標示為「建議」），然後輕觸 **繼續進行引導設定**。CommaView 會產生 SSH 金鑰、引導您完成連線並檢查您的 comma。接下來的步驟都依照它進行。"
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**引導設定**，標示為「建議」。"
          - target: continue
            text: "**繼續進行引導設定**。"
      - label: "手動設定"
        body: "只適用於您的電腦已經能以使用者 `comma` 透過 SSH 連上 comma 的情況。選擇 **手動設定**，再輕觸 **繼續進行手動設定**，然後在終端機執行指令。安裝程式顯示一次性配對碼後，輕觸 **我已執行指令**，輸入 comma 的 IP 和配對碼，再輕觸 **新增 comma**。[從終端機手動設定](#從終端機手動設定) 列出了每個步驟。"
        screen: setup-manual-instructions
        pins:
          - text: "**輕觸即可複製** 會複製指令。"
          - target: ran-command
            text: "安裝程式顯示配對碼後，輕觸 **我已執行指令**。"
  - id: ssh-key
    title: "把 SSH 金鑰加入 GitHub"
    body: |
      CommaView 會為這支手機產生一把 SSH 金鑰。輕觸 **複製金鑰並開啟 GitHub**：它會複製公開金鑰，並開啟 GitHub 的新增 SSH 金鑰頁面。

      在 GitHub 上，把金鑰貼到 **Key** 欄位，標題隨意命名（CommaView 會先填好一個），然後按 **Add SSH key** 儲存。回到 CommaView，輕觸 **繼續**。
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**複製金鑰並開啟 GitHub**。畫面會顯示「已複製 SSH 金鑰。正在開啟 GitHub…」"
      - target: own-key
        text: "**使用我自己的 SSH 金鑰** 可以匯入您在 GitHub 上已有的金鑰組。"
      - target: continue
        text: "金鑰在 GitHub 上儲存後，輕觸 **繼續**。"
    note: "GitHub 上已經有金鑰組了？可以改用 **使用我自己的 SSH 金鑰** 匯入。私密金鑰會留在您的手機上。"
  - id: comma-ssh
    title: "在 comma 上開啟 SSH"
    body: |
      在 comma 的螢幕上，前往 **設定 → 裝置 → SSH**：

      1. 輸入您的 GitHub 使用者名稱。
      2. 等 comma 取得您的 GitHub 金鑰。
      3. 開啟 SSH。

      然後回到 CommaView，輕觸 **繼續**。
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "SSH 開啟後，輕觸 **繼續**。"
    note: "comma 只會在您輸入使用者名稱時取得一次金鑰。如果是在加入金鑰之前輸入使用者名稱，請移除後重新輸入，讓 comma 再取得一次金鑰。"
  - id: choose-comma
    title: "選擇您的 comma"
    body: |
      CommaView 會列出這個 Wi‑Fi 網路上已經執行 CommaView 的 comma，所以第一次設定的 comma 通常還不會出現。輕觸 **清單中沒有我的 comma**，輸入它的 IP 位址，然後輕觸 **安裝 CommaView**。

      IP 位址可以在 comma 的 **設定 → 網路** 中找到：comma four 上在 Wi‑Fi 按鈕的網路名稱底下，comma 3X 上則在 **進階** 中。
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "已經執行 CommaView 的 comma。儲存在這支手機上的會標示 **已儲存在這支手機上**。"
      - text: "**清單中沒有我的 comma**：輸入它的 IP 位址。"
      - target: install
        text: "**安裝 CommaView**。"
  - id: safe-install
    title: "開始安全安裝"
    body: |
      **安全安裝** 對話方塊會顯示要安裝到哪一台 comma。閱讀說明，等短暫的倒數結束後輕觸 **開始安全安裝**。
    tabs:
      - label: "車輛已打入 P 檔"
        body: "如果車輛已打入 P 檔且 openpilot 未啟用，CommaView 會立即安裝。"
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "倒數結束後輕觸 **開始安全安裝**。"
      - label: "車輛行駛中"
        body: "comma 會先排入安裝，等車輛打入 P 檔且 openpilot 未啟用時才執行，所以絕不會中斷行程。設定會顯示 **已排入安裝**：請把車輛打入 P 檔並讓 openpilot 未啟用，等一兩分鐘，然後輕觸 **完成設定**。"
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "車輛打入 P 檔後，輕觸 **完成設定**。"
    note: "接著 CommaView 會透過 SSH 連上 comma，確認是哪一台 comma，並安裝與這個版本的 App 一起測試過的執行環境。它會檢查安裝有回應，並把您的 comma 儲存在這支手機上。完成之前，請讓手機留在同一個網路中。"
    warn: "請讓車輛保持發動並打入 P 檔。沒有常時供電線時，車輛熄火也會讓 comma 關機，安裝就會中斷。"
  - id: ready
    title: "CommaView 已就緒"
    body: |
      您的 comma 已安裝並配對完成，下次啟動時會自行重新連線。
    tabs:
      - label: "CommaView 已就緒"
        body: "輕觸 **完成**。"
        screen: setup-done
        pins:
          - target: finish
            text: "**完成** 會帶您回到首頁。"
      - label: "重新啟動以完成設定"
        body: "有時設定會顯示 **重新啟動以完成設定**：comma 重新啟動一次後，才會串流到您的手機。請在車輛熄火，或打入 P 檔且 openpilot 未啟用時，輕觸 **重新啟動 comma 並完成**。重新啟動期間，openpilot 會停止約一分鐘。"
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**重新啟動 comma 並完成**。"
check: "首頁會顯示您的車輛，其 comma 為 **已連線**，還有執行環境和 comma 的位址。輕觸 **開啟 Live View**：道路畫面即時播放，上面畫著行駛路徑和前車。從現在起，只要手機和 comma 在同一個網路中，就算 comma 的位址改變，App 也會自行找到它。"
fixes:
  - q: "無法透過 SSH 連線"
    a: "請確認 comma 上 **設定 → 裝置 → SSH** 已開啟、GitHub 使用者名稱是您的，而且 CommaView 金鑰已加入那個 GitHub 帳號。如果是在輸入使用者名稱之後才加入金鑰，請移除使用者名稱再重新輸入，讓 comma 取得金鑰。"
  - q: "清單裡沒有我的 comma"
    a: "第一次設定時這很正常：清單只會列出已經執行 CommaView 的 comma。輕觸 **清單中沒有我的 comma**，輸入它的 IP 位址（comma 上的 **設定 → 網路**：comma four 上在 Wi‑Fi 按鈕的網路名稱底下，comma 3X 上在 **進階** 中）。請確認手機和 comma 在同一個網路中，而且沒有使用 VPN。"
  - q: "設定顯示「已排入安裝」"
    a: "comma 偵測到車輛正在行駛，所以會等待。請把車輛打入 P 檔並讓 openpilot 未啟用，等一分鐘，然後輕觸 **完成設定**。請讓車輛保持發動：沒有常時供電線時，車輛熄火也會讓 comma 關機。"
  - q: "設定顯示我的 comma 不受支援"
    a: "在 comma 3 上，設定會停止，並提供 **在 comma 3X 或 comma four 上設定 CommaView**。如果分支版本的畫面無法加入 CommaView 的畫面，設定會如實告知，而且不會變更任何東西。[檢查您的 comma 和分支版本是否受支援](/zh-tw/guides/forks)。"
  - q: "配對碼沒有用"
    a: "配對碼只能使用一次，而且很快就會過期。請重新執行安裝程式取得新的配對碼，並確認輸入的內容與顯示的一致（連字號可省略）。"
  - q: "已連線，但沒有影像"
    a: "設定和配對都已完成，問題出在影像串流。請確認 comma 已開機並可以上路，讓手機留在同一個網路中，然後重新開啟 Live View。如果顯示 **連不到這台 comma**，請看 [CommaView 找不到您的 comma](/zh-tw/guides/comma-not-found)。"
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## 從終端機手動設定

只適用於您的電腦已經能以使用者 `comma` 透過 SSH 連上 comma 的情況。

1. 在 CommaView 中選擇 **手動設定**，再輕觸 **繼續進行手動設定**。App 會在 **從您的終端機安裝** 畫面顯示適用於其執行環境的指令，可以直接複製（**輕觸即可複製**）。它類似下面這行安裝目前版本執行環境的指令：

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. 在與 comma 連上同一個 Wi‑Fi 網路的電腦上執行它，並把 `COMMA_IP` 換成 comma 的 IP 位址（comma 上的 **設定 → 網路**：comma four 上在 Wi‑Fi 按鈕的網路名稱底下，comma 3X 上在 **進階** 中）。您的電腦會下載安裝程式，再透過 SSH 以使用者 `comma` 在 comma 上執行。
3. 安裝程式完成後，CommaView 會在 comma 上啟動，並顯示一次性配對碼。
4. 回到 CommaView，輕觸 **我已執行指令**。在 **新增您的 comma** 畫面選擇您的 comma 或輸入它的 IP，輸入配對碼，然後輕觸 **新增 comma**。App 會檢查執行環境並儲存這台 comma。

## 第一次上路之前

開車之前，先在停車時試試看。

- 首頁顯示您的 comma 為 **已連線**。
- Live View 可以播放，行駛路徑會隨車輛移動。
- 如果 App 顯示警告或要求修復，請在上路前處理好。
- 把一切設定好，讓它在開車時不需要您操作。

還是卡住了？請到 [CommaView Discord](https://discord.gg/UuMhz9K8ft) 發問，或從 App 傳送意見回饋。如果支援人員需要記錄，請[傳送支援資料包](/zh-tw/guides/support-bundle)。
