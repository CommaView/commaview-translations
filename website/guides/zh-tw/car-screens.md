---
title: "在平板或車用螢幕上使用 CommaView"
description: "在更大的螢幕上執行 CommaView 的 Live View：Android 車機、接在原廠螢幕上的 Android AI 盒，或架在支架上的平板。安裝、網路、配對和版面。"
topic: screens
order: 3
kind: walkthrough
lede: "comma 3X 和 comma four 的螢幕都很小。CommaView 可以把您 comma 的 Live View 顯示在更大的螢幕上：Android 車機、接在車輛原廠螢幕上的 Android AI 盒，或架在支架上的手機或平板。車用螢幕會執行自己的一份 CommaView，並與您的 comma 配對。"
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 以上版本"
    text: "執行 Android 8 以上版本、並允許安裝 App 的車機、AI 盒、手機或平板。"
  - title: "您的邀請"
    text: "收到 CommaView 邀請的電子郵件地址，用來登入 my.commaview.com 和 App。"
  - title: "手機上的 CommaView"
    text: "最簡單的做法：先用手機設定好您的 comma，再配對車用螢幕。[設定 CommaView](/zh-tw/guides/setup)。"
howItWorks:
  - title: "您的 comma"
    text: "透過區域網路傳送 Live View，不經過網際網路。"
    edge: "熱點或 Wi‑Fi"
  - title: "車用螢幕"
    text: "執行自己的 CommaView，並與您的 comma 配對。"
steps:
  - id: install
    title: "在車用螢幕上安裝 CommaView"
    body: |
      在車機、AI 盒、手機或平板上開啟網頁瀏覽器，用收到邀請的電子郵件地址登入 [my.commaview.com](https://my.commaview.com)。在 **Get the app** 底下輕觸 **Download CommaView**，開啟下載的檔案，並只為這次安裝允許從瀏覽器安裝 App，裝好後再關閉，做法和[設定指南](/zh-tw/guides/setup)相同。

      開啟 CommaView 並登入。Beta 期間，它需要不時連上網路來續期存取通行證，所以請至少偶爾讓它連上可以上網的 Wi‑Fi。
    note: "有些車機和盒子禁止從瀏覽器安裝 App。請在電腦上下載 App，用隨身碟複製過去，再從裝置的檔案管理員開啟。"
  - id: network
    title: "讓它和 comma 連上同一個網路"
    body: |
      Live View 透過區域網路直接從 comma 傳到車用螢幕。兩者只要在同一個網路中就行，在車上通常是熱點。請選擇會隨車輛發動而自動開啟的那一個：通常最省事。
    tabs:
      - label: "車用螢幕的熱點"
        body: "如果 AI 盒或車機可以分享熱點（很多有 SIM 卡的裝置都可以），請開啟熱點，再到 comma 的 **設定 › 網路** 中讓 comma 連上。"
      - label: "手機的熱點"
        body: "讓 comma 和車用螢幕都連上您的手機熱點，它們也會透過熱點上網。"
      - label: "comma 的熱點"
        body: "開啟 comma 的熱點（openpilot 稱為網路分享：在 comma four 上是 **設定 › 網路 › 啟用網路分享**；在 comma 3X 上是 **設定 › 網路 › 進階 › 啟用網路分享**），再讓車用螢幕連上。"
      - label: "家裡的 Wi‑Fi"
        body: "在家時，兩者都連上您的 Wi‑Fi。設定時很方便，但一開車離開就斷了。"
    note: "請關閉車用螢幕上的任何 VPN。有些熱點會把連上的裝置彼此隔開：如果車用螢幕在某個熱點上找不到 comma，請換一個試試。詳情請看[在車上連線](/zh-tw/guides/connect-in-the-car)。"
  - id: pair
    title: "與您的 comma 配對"
    body: |
      如果您的 comma 已經透過手機執行 CommaView，請直接配對車用螢幕，不必重新設定。它會取得自己的金鑰。
    tabs:
      - label: "在手機上"
        body: |
          開啟 comma 的 **裝置設定**，再輕觸 **配對其他手機**。在 **新增另一支手機** 底下輕觸 **顯示邀請碼**：一組可以輸入的代碼或一個 QR 碼，10 分鐘內有效，只能使用一次。
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**顯示邀請碼**。"
          - target: this-phone
            text: "擁有金鑰的手機，目前這支標示為 **這支手機**。車用螢幕也會加入其中。"
      - label: "在車用螢幕上"
        body: |
          在 **連接您的 comma** 畫面輕觸 **配對已執行 CommaView 的 comma**（如果已經新增過 comma，請改為開啟 **新增 comma**）。選擇您的 comma，再輕觸 **輸入它的配對碼** 或 **掃描 QR 碼**。如果清單中沒有它，請輕觸 **輸入位址與配對碼**。在 **配對碼或邀請碼** 中輸入邀請碼，然後輕觸 **配對 comma**。
        screen: add-comma
        pins:
          - target: found-comma
            text: "在這個網路上找到的您的 comma。"
          - target: scan-qr
            text: "**掃描 QR 碼**。"
          - target: enter-address
            text: "清單中沒有時，輕觸 **輸入位址與配對碼**。"
    note: "之後您的手機會顯示 **有新手機取得了金鑰**。輕觸 **這是我的**。每個步驟的說明：[新增另一支手機或平板](/zh-tw/guides/another-phone)。"
  - id: fit
    title: "讓畫面符合您的螢幕"
    body: |
      在寬螢幕上，CommaView 會以儀表板的形式排版，導覽放在側邊的側欄中。請把裝置的文字大小維持在一眼就能看清楚的程度：CommaView 會依照在這個文字大小下能用的空間來排版。

      Live View 的控制項位於駕駛側。設為 **自動** 時，CommaView 會依照您的 comma 回報的駕駛側；如要自行設定，請選擇 **設定 › 顯示 › 駕駛座位置**：**自動**、**左駕** 或 **右駕**。所有畫面上的控制項都會隨之左右對調。
    tabs:
      - label: "平板"
        body: "首頁會並排顯示車輛、您這一週、地圖和您的行程，側欄在旁邊。"
        screen: tablet-home
        pins:
          - target: home-tab
            text: "側欄：**首頁**、**錄影**、**設定**。"
          - target: open-live-view
            text: "**開啟 Live View**。"
      - label: "車機"
        body: "同樣的儀表板，尺寸適合中控螢幕。"
        screen: car-home
        pins:
          - target: home-tab
            text: "側欄：**首頁**、**錄影**、**設定**。"
          - target: open-live-view
            text: "**開啟 Live View**。"
      - label: "透過 AI 盒"
        body: |
          有些車輛會裁掉 AI 盒輸出畫面的邊緣，而 Android 無從得知。開啟 **設定 › 顯示 › 螢幕邊緣**，把每一邊往內移，直到整圈線都看得到。接著確認首頁、Live View 和設定都能完整顯示。那裡的 **主題** 可以跟隨車用螢幕：**與這部裝置相同**。
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−** 和 **+** 把每一邊往內移；**完成** 會儲存設定。"
  - id: live-view
    title: "開啟 Live View 並確認能播放"
    body: |
      車輛發動後，輕觸 **開啟 Live View**。它的控制項位於道路畫面旁、駕駛側的側欄中，螢幕較矮時會變得精簡。
    tabs:
      - label: "平板"
        body: "**詳細資訊** 會在影像旁的窗格中開啟。"
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "詳細資訊，在影像旁。"
          - target: record-button
            text: "**錄影**。"
          - target: go-live-button
            text: "**直播**。"
      - label: "車機"
        body: "側欄中有錄影、行車畫面切換、車內鏡頭、詳細資訊和離開。"
        screen: car-live-view
        pins:
          - target: record-button
            text: "**錄影**。"
          - target: onroad-screen-button
            text: "行車畫面切換按鈕。"
          - target: driver-cam-button
            text: "**車內鏡頭**。"
          - target: details
            text: "**詳細資訊**，在車內鏡頭下方。"
          - target: exit
            text: "**離開**。"
  - id: auto
    title: "讓它自動開啟"
    body: |
      在 **設定 › 顯示** 的 **開啟 Live View** 底下：

      - **連線時開啟 Live View**：車輛發動後，comma 一連線就自動開啟 Live View。
      - **這個裝置啟動時開啟 CommaView**：適用於隨車輛一起重新啟動的車機。會進入休眠的車機可能有自己的開機自動啟動 App 清單。
      - **藍牙連線時開啟 CommaView**：在您選擇的裝置連線時開啟，可以是您的車輛，在車機上也可以是您的手機。

      允許 **顯示在其他應用程式上層** 後，CommaView 就能自動開啟；否則會改用通知提醒您開啟。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**連線時開啟 Live View**。"
check: "車輛發動後，車用螢幕會開啟 Live View，串流狀態標籤顯示 **即時**，所有控制項都在螢幕邊緣以內。"
fixes:
  - q: "可以透過 CarPlay 或 Android Auto 使用 CommaView 嗎？"
    a: "無法從手機使用。CommaView 不是 CarPlay 或 Android Auto App，而且這些平台不允許手機 App 在車輛行駛時顯示影片。Android AI 盒可以繞過這個限制，因為它本身就是一部 Android 裝置：CommaView 在盒子上執行，車輛顯示盒子的畫面。請看[在 Android AI 盒上執行 CommaView](/zh-tw/guides/ai-box)。"
  - q: "可以在車輛內建的 Android Automotive（Google built-in）上使用嗎？"
    a: "目前還不行。搭載 Google built-in 的車輛只能從它自己的 Play 商店安裝 App，而那裡沒有 CommaView。如果您用其他方法試過，請告訴我們結果。"
  - q: "車用螢幕和手機可以同時使用同一台 comma 嗎？"
    a: "可以：分別讓它們和 comma 配對。同一時間只有一部能開啟 Live View，所以請先在另一部上離開 Live View。Live View 會顯示 **Live View 已在另一部裝置上開啟**，等您在另一部回到首頁後，它就會自行開始。"
  - q: "車輛裁掉了畫面的邊緣"
    a: "有些車輛會裁掉 AI 盒輸出的畫面，而 Android 無從得知。**設定 › 顯示 › 螢幕邊緣** 可以讓 App 避開您設定的每一邊。"
  - q: "車用螢幕找不到 comma"
    a: "在同一個網路中，就算 comma 的位址改變，CommaView 也會自行找到它。如果找不到，請輸入 comma 的 IP 位址：在 comma 自己的熱點上是 192.168.43.1（每台 comma 都一樣）；在其他網路上，則是 comma 在 **設定 › 網路** 中顯示的 IP 位址：comma four 上在 Wi‑Fi 按鈕的網路名稱底下，comma 3X 上在 **進階** 中。"
  - q: "更新執行環境後，車用螢幕收不到影像了"
    a: "更新 comma 的執行環境時，請先更新每一部觀看它的裝置上的 CommaView，車用螢幕也一樣。使用舊版 CommaView 的車用螢幕，在 comma 的第一支手機取得金鑰後還能繼續使用 90 天；之後需要 CommaView 0.0.166 以上版本和一組邀請碼。"
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## 開車時可以使用的裝置

CommaView 是 Android App，所以您面前需要有一部 Android 裝置。以下任何一種都能在開車時執行它：

- **Android 車機。** 執行 Android 8 以上版本的副廠車機：CommaView 可以像在手機上一樣安裝，開車時在車上的螢幕執行。
- **Android「AI 盒」。** 一台小型 Android 電腦，插在車輛的有線 CarPlay 或 Android Auto 連接埠上，在那裡顯示自己的 Android 畫面。CommaView 在盒子上執行，而不是在您的手機上。請看[在 Android AI 盒上執行 CommaView](/zh-tw/guides/ai-box)。
- **架在支架上的手機或平板。** 任何 Android 手機或平板，裝在不擋視線的儀表板或冷氣出風口支架上。這是最簡單的方式，也是大多數人使用的方式。

有網頁瀏覽器的車輛（例如 Tesla）也可以改在瀏覽器中顯示 Live View：請看[在車上的瀏覽器中顯示 Live View](/zh-tw/guides/browser-view)。

## 不能使用的方式和原因

- **從手機使用 CarPlay 和 Android Auto。** CommaView 不是 CarPlay 或 Android Auto App。這些平台不允許手機 App 在車輛行駛時顯示影片。
- **CarPlay 和 Android Auto 的停車影片功能。** Apple 和 Google 正為部分車輛加入影片功能，但只能在停車時使用，所以無法在路上顯示 Live View。
- **把手機畫面投放到車上。** 不支援透過 CarPlay 或 Android Auto 鏡像手機畫面的轉接器。請改用能自己執行 CommaView 的 Android AI 盒或車機。
- **Google built-in（Android Automotive）。** 這些車輛只能從它自己的 Play 商店安裝 App，而那裡沒有 CommaView。

## 測試過的硬體

CommaView 團隊實際開車用過的車用螢幕。CommaView 應該能在任何 Android 8 以上版本的裝置上執行，但以下是我們確認過的：

| 裝置 | 類型 | 我們確認了什麼 |
| --- | --- | --- |
| **Doro 車機**（Qualcomm QCM6125，Android 13，1280 × 720） | 車機 | 市區行駛中的 Live View（2026 年 10 月）。 |
| **Dasaita 10.2″ 車機**（1280 × 720，裝在 Toyota RAV4 上） | 車機 | 行駛中的 Live View；停車時的錄影上傳。 |

**協助我們測試。** 每一款車用螢幕都不一樣。如果您在車機或盒子上執行 CommaView，請[告訴我們使用情況](#告訴我們您的車用螢幕)，我們確認後會把它加到這裡。

## 告訴我們您的車用螢幕

請直接從車用螢幕傳送給我們，這樣回報會附上它的型號和螢幕尺寸：

1. 在車機或盒子上的 CommaView 中，開啟 **設定 › 支援與診斷**，輕觸 **回報問題或提供建議**。
2. 選擇 **想法**，再開啟 **這部裝置的診斷資料**（選擇「想法」時預設不附上）：它會告訴我們裝置的廠牌、型號和螢幕尺寸。
3. 在備註中寫下您的車款、車機或盒子（廠牌和型號）、連線方式（誰的熱點，或 Wi‑Fi），以及哪些正常、哪些不正常。然後輕觸 **傳送**。

您傳送的內容和我們的回覆，都可以在 [my.commaview.com](https://my.commaview.com/feedback) 的 Your feedback 中找到。還沒加入 Beta，或 App 無法啟動？請到 [CommaView Discord](https://discord.gg/UuMhz9K8ft) 告訴我們。

## 安全

- 請在停車時完成安裝、配對和版面設定。上路前確認 Live View 能播放。
- 開車時請勿操作 CommaView。依照 openpilot 的要求，眼睛看路、雙手握住方向盤。
- comma 自己的警示和車輛的儀表永遠優先。CommaView 只會顯示 comma 看到的內容。
- 把手機或平板裝在不擋視線、不擋安全氣囊的位置，並遵守當地對車內螢幕的規定。
