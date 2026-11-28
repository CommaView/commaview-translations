---
title: "不用家裡的 Wi‑Fi，在車上連線"
description: "在車上讓手機和 comma 連上同一個網路：手機的熱點、comma 的熱點或車用螢幕的熱點，以及 CommaView 連不到 comma 時該怎麼辦。"
topic: start
order: 3
kind: walkthrough
lede: "Live View 透過區域網路直接從 comma 傳到您的手機，不經過網際網路。CommaView 不在乎是誰的網路：手機和 comma 只要在同一個網路中就行。在車上，通常是熱點。"
parked: true
updated: 2026-11-27
needs:
  - title: "已設定好 CommaView"
    text: "您的 comma 已和這支手機配對。還沒有嗎？[設定 CommaView](/zh-tw/guides/setup)。"
  - title: "不使用 VPN"
    text: "使用 CommaView 時，請關閉手機或車用螢幕上的任何 VPN。"
howItWorks:
  - title: "您的 comma"
    text: "在它所在的網路上提供 Live View 和錄影。"
    edge: "同一個熱點"
  - title: "您的手機"
    text: "在那個網路上自行找到 comma，就算它的位址改變也一樣。"
steps:
  - id: network
    title: "讓手機和 comma 連上同一個網路"
    body: |
      選擇適合您車輛的方式：會隨車輛發動而自動開啟的那一個通常最省事。要讓 comma 連上網路，請在 comma 自己的螢幕上操作，位置是 **設定 › 網路**。
    tabs:
      - label: "手機的熱點"
        body: "開啟手機熱點，讓 comma 連上。同一支手機上的 CommaView 會透過它連到 comma，comma 也會透過它上網。"
      - label: "comma 的熱點"
        body: "開啟 comma 的熱點（openpilot 稱為網路分享：在 comma four 上是 **設定 › 網路 › 啟用網路分享**；在 comma 3X 上是 **設定 › 網路 › 進階 › 啟用網路分享**），再從手機的 Wi‑Fi 設定連上。comma 的熱點無法上網。"
      - label: "車用螢幕的熱點"
        body: "如果 AI 盒或車機可以分享熱點（很多有 SIM 卡的裝置都可以），請開啟熱點，讓 comma 連上；如果您也用手機，也讓手機連上。[車用螢幕](/zh-tw/guides/car-screens) 有更多說明。"
    note: "有些熱點會把連上的裝置彼此隔開。如果 CommaView 在某個熱點上找不到 comma，請換一個試試。"
  - id: home
    title: "開啟 CommaView"
    body: |
      comma 在新網路上回應後，首頁會顯示它 **已連線**：CommaView 會自行找到它，即使位址改了也一樣。車輛熄火時 comma 會進入休眠，所以請先發動車輛。

      如果首頁顯示 comma 離線，並出現 **無法連線？**，請確認手機和 comma 連上同一個 Wi‑Fi，或連上它的熱點，然後輕觸 **重新連線**。
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**重新連線** 會再次嘗試連上 comma。"
      - target: cant-connect
        text: "**無法連線？** 會說明手機需要什麼：和 comma 連上同一個 Wi‑Fi，或連上它的熱點。"
  - id: address
    title: "如果還是找不到，請輸入它的位址"
    body: |
      開啟 comma 的 **裝置設定**，再輕觸 **名稱與位址**，編輯它的 IP 位址。在 comma 自己的熱點上，位址是 **192.168.43.1**（每台 comma 都一樣）。在其他網路上，則是 comma 在 **設定 › 網路** 中顯示的位址：comma four 上在 Wi‑Fi 按鈕的網路名稱底下，comma 3X 上在 **進階** 中。輕觸 **儲存**。
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "comma 在這個網路上的 IP 位址。"
      - target: save
        text: "**儲存**。"
  - id: live-view
    title: "開啟 Live View"
    body: |
      在首頁輕觸 **開啟 Live View**。如果手機和 comma 斷線，Live View 會說明原因，並在 comma 回應時自行重新連線。**連不到這台 comma** 表示手機不在 comma 的網路上：解決後輕觸 **重試**。
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**連不到這台 comma**：Live View 停止的原因。"
      - target: retry
        text: "手機回到 comma 的網路後，輕觸 **重試**。"
check: "首頁顯示您的 comma **已連線**，Live View 播放道路畫面，上面畫著行駛路徑。"
fixes:
  - q: "「連不到這台 comma」"
    a: "手機必須和 comma 連上同一個 Wi‑Fi，或連上它的熱點。請確認手機連上的是哪個網路（它可能自動連回了記住的 Wi‑Fi），關閉任何 VPN，然後輕觸 **重試**。"
  - q: "「Live View 已在另一部裝置上開啟」"
    a: "這台 comma 一次只會串流到一支手機或一台車機。在另一部裝置的 CommaView 回到首頁，這裡的 Live View 就會自行開始。"
  - q: "「CommaView 沒有回應」"
    a: "它可能正在 comma 上重新啟動。恢復後 Live View 會重新連線。"
  - q: "CommaView 表示需要連網續期"
    a: "Beta 期間，CommaView 會不時續期存取通行證，而 comma 的熱點不算連上網路。請讓手機暫時使用行動數據或可以上網的 Wi‑Fi。"
  - q: "在一個熱點上可以用，換一個就不行"
    a: "有些熱點會把連上的裝置彼此隔開，手機因此看不到 comma。請改用第 1 步中的其他網路。"
related: [comma-not-found, car-screens, browser-view, setup-troubleshooting]
---

## 搜尋、配對和位址

有三件不同的事都必須正常，知道是哪一件出問題，就知道該修什麼：

- **找到 comma。** CommaView 會在手機所在的網路上尋找您的 comma，在新的地方找到同一台 comma 時會更新已儲存的位址。有些網路會擋住這種搜尋；輸入位址（第 3 步）可以繞過它。
- **連到它。** 手機必須能在那個網路上連到 comma。筆電能透過 SSH 連到 comma，並不代表手機也能。
- **配對。** 連上之後，手機會使用配對時取得的金鑰。換網路不會取消配對：不需要重新配對。
