---
title: "直播到 YouTube 或其他伺服器"
description: "把 Live View 顯示的道路和行車畫面，以 720p 或 1080p 串流到您的 YouTube 頻道或任何 RTMP 伺服器。設定一次，之後從 Live View 開始直播。"
topic: screens
order: 5
kind: walkthrough
lede: "**直播** 會把 Live View 顯示的內容，也就是道路和它的行車畫面，從您的手機以 720p 或 1080p 串流到您的 YouTube 頻道或任何 RTMP 伺服器。在「設定」中設定一次，之後從 Live View 開始。"
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View 可以正常使用"
    text: "Android 手機上的 CommaView 已與您的 comma 配對。還沒有嗎？[設定 CommaView](/zh-tw/guides/setup)。"
  - title: "串流的目的地"
    text: "一個可以登入的 YouTube 頻道，或從 YouTube 工作室或其他 RTMP 伺服器取得的串流金鑰。"
  - title: "手機能上網"
    text: "comma 的 Wi‑Fi 無法上網時，串流會使用手機的行動數據：720p 每小時約 1.4 GB。"
howItWorks:
  - title: "您的 comma"
    text: "像平常一樣把 Live View 傳到您的手機。"
  - title: "您的手機"
    text: "串流 Live View 繪製的內容：每秒 20 格，720p 或 1080p。"
    edge: "網際網路"
  - title: "YouTube 或您的伺服器"
    text: "播給您允許觀看的人。"
steps:
  - id: settings
    title: "開啟設定 › 直播"
    body: |
      開啟 **設定**，輕觸 **直播**。在您設定好之前，這一列會顯示 **需設定**。
    screen: support-settings
    pins:
      - target: live-streaming-row
        text: "**直播**。"
  - id: destination
    title: "選擇串流的目的地"
    tabs:
      - label: "使用 YouTube 登入"
        body: |
          輕觸 **使用 YouTube 登入**。Google 的登入頁面會在瀏覽器中開啟，您可以在那裡選擇帳號和頻道。登入後，每次直播都會在您的頻道上建立一場直播，並由 YouTube 自動開始：不需要串流金鑰，也不用在 YouTube 工作室中按任何按鈕。之後 **直播目的地** 卡片會顯示您的頻道，以及 **已登入**。
        screen: settings-live-streaming
        pins:
          - target: destination-row
            text: "**直播目的地**：您的頻道，已登入。"
        note: "Google 自己的登入頁面沒有附圖。"
      - label: "串流金鑰或伺服器"
        body: |
          輕觸 **使用串流金鑰**（或 **設定直播目的地**），選擇 **平台**：**YouTube** 或 **其他伺服器**，再貼上串流金鑰。如果是 YouTube：在 YouTube 工作室中依序選擇「建立 › 進行直播 › 串流」，複製串流金鑰，並在那裡開啟「自動開始」，讓每場直播都在影像送達時開始。如果是其他伺服器，還要貼上它的 `rtmp://` 或 `rtmps://` 位址。輕觸 **儲存直播目的地**。
        screen: settings-live-streaming-destination
        pins:
          - target: platform
            text: "**平台**。"
          - target: stream-key
            text: "串流金鑰。它只保存在這支手機上，也只會傳給它對應的伺服器。"
          - target: save
            text: "**儲存直播目的地**。"
        note: "`rtmp://` 會以未加密的方式傳送串流金鑰。如果伺服器支援，請使用 `rtmps://`。"
  - id: choices
    title: "確認誰可以觀看、畫質和聲音"
    body: |
      - **誰可以觀看**（使用 YouTube 登入時）：**公開**、**不公開** 或 **私人**。預設為 **不公開**。使用串流金鑰時，請在 YouTube 工作室中選擇。觀看的人都會看到您開到哪裡。
      - **標題與說明**（使用 YouTube 登入時）：每場直播的名稱，可以用標籤插入日期、車輛等資訊。
      - **畫質**：720p 或 1080p，並顯示各自每小時大約會用掉多少行動數據。
      - **聲音**：預設關閉，除非您選擇 comma 的麥克風或這支手機的麥克風。車上每個人的聲音都會被收進去，包括乘客。聲音只會進入您的串流和即時副本，絕不會傳給 CommaView。

      **開始直播前** 會整理所有資訊：數據用量、車內鏡頭，以及串流何時停止。
    screen: settings-live-streaming
    pins:
      - text: "**標題與說明**。"
      - target: sound-row
        text: "**聲音**。"
  - id: go
    title: "在 Live View 中輕觸「直播」"
    body: |
      開啟 Live View，輕觸 **直播**。它會顯示 **啟動中…**，接著顯示您已經直播了多久。請在出發前開始，之後就別再操作。
    screen: phone-live-view
    pins:
      - target: go-live-button
        text: "**直播**。放不下時，它會在 **更多** 裡。"
    warn: "只要 **車內鏡頭** 開啟，串流就會顯示車內鏡頭畫面，此時 **車內鏡頭** 會顯示 **直播中**。關閉 **車內鏡頭**，車內畫面就不會出現在串流中。"
  - id: share
    title: "分享觀看連結"
    body: |
      在 **詳細資訊** 中，串流那一列會顯示 **直播中** 和時長，以及傳送速率、已用數據和網路。使用 YouTube 登入時，下方的 **分享觀看連結** 會分享您這場直播的 `youtu.be` 連結。
    screen: phone-live-view-go-live
    pins:
      - target: stop-live
        text: "直播中的 **直播** 按鈕，附計時器。"
      - target: streaming
        text: "**直播中** 和時長。"
      - target: share-watch-link
        text: "**分享觀看連結**。"
  - id: stop
    title: "停好車後停止串流"
    body: |
      再輕觸一次 **直播** 即可停止。離開 Live View、輕觸通知中的 **停止**，或影像中斷一分鐘後，串流也會停止。切換 App 或鎖定手機時，串流會繼續。
check: "Live View 的 **直播** 按鈕以直播配色顯示正在計時，詳細資訊顯示 **直播中**，您的直播在 YouTube 或您的伺服器上播放。"
fixes:
  - q: "Live View 中沒有「直播」"
    a: "直播還沒設定：詳細資訊會顯示 **在『設定』中設定直播後，即可從這裡開始直播**。或者它在 **更多** 裡，因為控制項放不下。"
  - q: "「請在『設定』›『直播』中新增串流金鑰」"
    a: "直播沒有可以串流的地方。請在 **設定 › 直播** 中使用 YouTube 登入，或新增串流金鑰。"
  - q: "使用串流金鑰時，YouTube 直播沒有開始"
    a: "使用串流金鑰時，請在 YouTube 工作室中手動開始每場直播，或在那裡開啟「自動開始」。使用 YouTube 登入時，直播會自動開始。"
  - q: "「這組金鑰含有空格」"
    a: "請從您的串流服務重新複製金鑰再貼上。"
  - q: "「沒有聲音：Browser View 正在無聲執行」"
    a: "直播會共用 Browser View 的畫面，而它沒有聲音。需要聲音時，請在開始直播前停止 Browser View。在沒有聲音的情況下開始的錄影也是如此。"
  - q: "串流自己停止了"
    a: "Live View 每次都會用一則訊息說明原因。影像中斷一分鐘後，以及您離開 Live View 時，串流也會停止。"
related: [live-view, browser-view, live-copy]
blogPost: commaview-0-0-165-go-live-send-to-commaview
---

## 保留每次直播的副本

**設定 › 錄影 › 儲存每次直播** 會把每次直播依照傳送時的畫質，存成「錄影」中的一個 MP4。它會保存在您的手機上。請看[保留即時副本](/zh-tw/guides/live-copy)。

## 串流中有什麼、沒有什麼

- **有：** 道路和畫在上面的行車畫面，以及 **車內鏡頭** 開啟時的車內鏡頭畫面。
- **沒有：** Live View 的控制項、詳細資訊和訊息。導航地圖只有在「設定」提供並開啟 **在串流中顯示地圖** 時才會出現，而且只有 CommaView 角落裡的地圖。
- 錄影和直播互不影響：您可以同時錄下和串流同一段行程。

## 安全

請在停車時設定並開始直播，之後就別再操作。開車時請勿操作 CommaView：依照 openpilot 的要求，眼睛看路、雙手握住方向盤。觀看的人都會看到您開到哪裡。
