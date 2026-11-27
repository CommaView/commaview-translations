---
title: "使用您自己的 Stadia Maps 金鑰導航"
description: "新增您的 Stadia Maps 金鑰，在首頁搜尋地點、選擇路線，然後在 Live View 中跟著轉彎卡片和語音提示前進。也可以把地點傳送到您的 comma。"
topic: navigation
order: 1
kind: walkthrough
lede: "**導航** 會在 Live View 中引導您前往某個地點。在首頁用 **要去哪裡？** 搜尋地點、選擇路線、輕觸 **開始**，再跟著轉彎卡片和語音提示走。路線由 Stadia Maps 依照您自己的金鑰提供，金鑰會加密保存在您的手機上。導航僅供顯示，絕不會控制車輛。"
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "已登入"
    text: "CommaView 0.0.167 以上版本，並用您的 Beta 帳號登入。未登入時不提供導航。"
  - title: "一把 Stadia Maps 金鑰"
    text: "來自您自己 Stadia Maps 帳號的 API 金鑰。路線要求會以您的帳號、依照其條款送出。"
  - title: "開啟車輛位置"
    text: "導航會依照您 comma 的 GPS。請在首頁為您的 comma 開啟 **車輛位置**。"
  - title: "手機能上網"
    text: "用於搜尋和取得路線。comma 的 Wi‑Fi 無法上網時，會改用行動數據。"
howItWorks:
  - title: "要去哪裡？"
    text: "依照 OpenStreetMap 的資料（Photon）尋找 comma 附近的地點。"
    edge: "您的金鑰"
  - title: "Stadia Maps"
    text: "規劃路線，由您的手機用您的金鑰提出要求。不經過 CommaView。"
  - title: "Live View"
    text: "依照 comma 的位置引導您：轉彎卡片、地圖和語音提示。"
steps:
  - id: open
    title: "開啟地圖與導航"
    body: |
      輕觸 **設定**，再輕觸 **地圖與導航**。登入後，它就在原本「離線地圖」所在的那一列。
    screen: support-settings
    pins:
      - target: maps-row
        text: "**地圖與導航**。"
  - id: get-key
    title: "向 Stadia Maps 取得金鑰"
    body: |
      在 **您的 Stadia Maps 金鑰** 底下，**API 金鑰** 顯示 **尚未新增**。輕觸 **向 Stadia Maps 取得金鑰**：它會在瀏覽器中開啟 Stadia 的註冊頁面。註冊後，從您的 Stadia Maps 主控台複製 API 金鑰。
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**您的 Stadia Maps 金鑰**：「路線需要你自己的 Stadia Maps 金鑰…」"
      - target: get-key
        text: "**向 Stadia Maps 取得金鑰** 會開啟 Stadia 的註冊頁面。"
      - target: add-key
        text: "複製好金鑰後，輕觸 **新增**。"
    note: "Stadia 的網站沒有附圖：那是他們的網站。它的主控台會顯示您金鑰的用量、方案和限制。"
  - id: add-key
    title: "貼上金鑰，再檢查並儲存"
    body: |
      回到 CommaView，輕觸 **新增**。輕觸 **貼上** 把金鑰填進欄位，再輕觸 **檢查並儲存**。CommaView 會向 Stadia Maps 查詢兩個固定地點之間的一條短路線來檢查金鑰，不涉及您的任何資訊：**正在向 Stadia Maps 檢查…**。金鑰被接受後，**API 金鑰** 會以遮蔽的形式顯示，例如 **•••• e1f0**。
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "**您的 Stadia Maps API 金鑰**，已遮蔽。"
      - target: paste
        text: "從剪貼簿 **貼上**。"
      - target: check-and-save
        text: "**檢查並儲存**。"
    note: "「只會加密保存在這支手機上。保存前會向 Stadia Maps 查詢一條短路線來檢查。」它絕不會出現在支援資料包或當機回報中。"
  - id: where-to
    title: "在首頁輕觸「要去哪裡？」"
    body: |
      停車時，輕觸首頁上 comma 卡片下方的 **要去哪裡？**。輸入地點或地址，或輕觸麥克風用說的。儲存之後，**住家** 和 **公司** 在卡片上輕觸一下就能前往。
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**要去哪裡？** 會開啟搜尋。"
      - target: voice
        text: "**用語音說要去哪裡**。"
      - target: home-chip
        text: "**住家**，儲存後才會出現。"
  - id: pick
    title: "選擇地點"
    body: |
      結果會依照離您 comma 的遠近排列，每一筆都顯示地址和距離，接著是您已儲存和最近的地點。輕觸您要去的那一個。
    screen: navigation-search
    pins:
      - target: search-field
        text: "**搜尋地點或地址**。"
      - target: first-result
        text: "一筆結果，顯示地址以及和您 comma 的距離。"
    note: "車輛行駛時無法打字：「車輛行駛中無法輸入文字。請使用語音或已儲存的地點。」"
  - id: start
    title: "選擇路線並輕觸「開始」"
    body: |
      路線預覽會在地圖上顯示路線、時間、距離和預計抵達時間。每條路線都有一個標籤：**最快**、**路線 2** 等等。輕觸 **開始**：導航開始，並開啟 Live View。

      **儲存為住家** 和 **儲存為公司** 會儲存這個地點，之後在首頁輕觸一下就能前往。
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "路線：**最快**、**路線 2**…"
      - target: start
        text: "**開始**。"
      - target: save-home
        text: "**儲存為住家**，旁邊是 **儲存為公司**。"
  - id: follow
    title: "在 Live View 中跟著導航走"
    body: |
      轉彎卡片會顯示下一個轉彎：箭頭、距離、指示和再下一步，以及您的預計抵達時間。每個轉彎前約 20 秒會有一次語音提示，快到時再提示一次，抵達時也會提示。在 CommaView 自己的行車畫面中，您所在的車道和轉彎的出口處會畫上箭頭標記。

      錯過轉彎時，幾秒內就會重新規劃路線。抵達並熄火後，行程會自行結束。
    tabs:
      - label: "手機"
        body: |
          直拿手機時，轉彎卡片和地圖位於影像下方。
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "轉彎卡片。"
          - target: end
            text: "**結束導航**。"
          - target: mute
            text: "**導航語音靜音**。"
          - target: map-button
            text: "**地圖** 會在這趟行程中隱藏地圖，再輕觸一次就會恢復。"
      - label: "車用螢幕"
        body: |
          在車機上，如果影像旁有空間，地圖和轉彎卡片會放在獨立的窗格中。沒有空間時，CommaView 的畫面會把地圖融入影像的角落。拖曳分隔線可以調整窗格的寬度。
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "轉彎卡片。"
          - target: divider
            text: "分隔線，用來調整地圖的寬度。"
          - target: map-button
            text: "**地圖**。"
    warn: "請在停車時設定好行程。開車時請勿操作 CommaView：轉彎卡片和語音就是為了讓您不必操作，而且 openpilot 和車輛自己的警示永遠優先。"
  - id: send
    title: "如果分支版本支援，把地點傳送到您的 comma"
    body: |
      如果分支版本自己的導航可以接收目的地，路線預覽中 **開始** 下方會有 **傳送到 comma**：StarPilot、carrotpilot，以及 openpilot 的導航（alpha），還有以它為基礎的 sunnypilot 導航。其他分支版本不會顯示。

      輕觸它。CommaView 會先詢問，並依照分支版本目前的設定，說明它會對駕駛有什麼影響，例如轉彎前減速。輕觸 **傳送**：「已傳送到 comma。StarPilot 會在那裡規劃自己的路線。」分支版本會用自己的服務規劃路線，所以路線可能和 CommaView 的不同。**從 comma 清除** 會把它撤下，結束行程時也會一併清除。
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**傳送**。"
    note: "「傳送到 comma」下方的 **將每次行程傳送到此 comma** 會在您輕觸「開始」時傳送每一趟行程。如果分支版本的駕駛設定有變，它會自動暫停，直到您再次同意。"
check: "在 **地圖與導航** 中，**API 金鑰** 以遮蔽形式顯示您的金鑰，路線預覽顯示 **路線由 Stadia Maps 提供 · 導航僅供顯示，絕不會控制車輛。**"
fixes:
  - q: "「新增你自己的 Stadia Maps 金鑰以取得路線：設定 › 地圖與導航。」"
    a: "還沒有儲存金鑰。在路線預覽中輕觸 **新增金鑰**，或依照[第 2 步和第 3 步](#step-get-key)操作。沒有金鑰時，「要去哪裡？」、搜尋和地點也能使用。"
  - q: "「Stadia Maps 不接受此金鑰（401）。請確認您已從主控台完整複製。」"
    a: "從您的 Stadia Maps 主控台重新完整複製金鑰，再貼上一次。"
  - q: "「這不是 Stadia Maps 金鑰。」"
    a: "您貼上的內容看起來不像 API 金鑰，所以沒有傳送任何東西。請從您的 Stadia Maps 主控台複製 API 金鑰：由字母、數字和連字號組成。"
  - q: "「Stadia Maps 拒絕了此金鑰（403）：它的方案可能不包含路線規劃。」"
    a: "請在您的 Stadia Maps 主控台確認方案。"
  - q: "「您的 Stadia Maps 金鑰已超過用量（429）」"
    a: "這個月的額度已經用完，或剛才要求太頻繁。請在您的 Stadia Maps 主控台確認。App 在五分鐘內不會再用它提出要求。"
  - q: "「無法連上 Stadia Maps 來檢查金鑰。請檢查這支手機的網路連線後再試一次。」"
    a: "您的手機現在無法上網。請改用行動數據或可以上網的 Wi‑Fi 再試一次。"
  - q: "首頁上沒有 **要去哪裡？**"
    a: "導航從 CommaView 0.0.167 起提供給已登入的成員。未登入，或存取通行證驗證不通過時，不會提供。中國大陸無法使用導航。"
  - q: "轉彎卡片顯示「車輛位置已關閉」"
    a: "導航需要您 comma 的位置。請在首頁為這台 comma 開啟 **車輛位置**。"
  - q: "轉彎卡片顯示「正在等待 GPS」"
    a: "導航會在 comma 第一次定位後開始。請在空曠處稍等一下。"
  - q: "「單次行程太遠了」"
    a: "導航只規劃 1500 公里（930 英里）以內的路線。請先選擇途中的一個停靠點，再從那裡繼續。"
  - q: "沒有 **傳送到 comma**"
    a: "它只會出現在路線預覽中，而且只適用於導航可以接收目的地的分支版本：StarPilot、carrotpilot，或 openpilot 和 sunnypilot 的導航（alpha）。"
  - q: "「無法連線到你的 comma 來傳送這次行程。」"
    a: "請把這支手機連到和 comma 相同的網路，然後輕觸 **再試一次**。"
  - q: "「comma 上 openpilot 的導航（alpha）已關閉。」"
    a: "請在停車時輕觸 **開啟導航（alpha）**。在每次啟動都會把它關掉的正式版建置上，目前還無法讓它保持開啟。"
related: [live-view, car-screens, overlays]
---

## Live View 中的地圖

**設定 › 地圖與導航 › Live View 地圖** 決定地圖放在哪裡：

- **版面配置**：**自動**（有空間時在影像旁，否則在角落）、**影像旁** 或 **角落**。comma 3X、comma four、StarPilot 和 Surround 畫面一律把地圖放在影像旁。
- **影像旁的寬度** 要在 Live View 中拖曳分隔線來設定。**重設** 會恢復預設值。
- **地圖主題**：**與 App 相同**（預設：CommaView 使用淺色時為淺色，使用深色時為深色）、**自動**（依 comma 所在地，日出到日落使用淺色）、**與手機相同**、**淺色** 或 **深色**。它適用於每張地圖：Live View 的地圖、首頁的位置卡片、**車輛位置** 和路線預覽。

## 語音導引和您的地點

- **語音導引** 可以開啟或關閉語音提示。轉彎卡片上的喇叭按鈕 **導航語音靜音** 是同一項設定。
- **您的地點**：**住家** 和 **公司**，以及 **最近的地點**，都保存在這支手機上。**清除** 會刪除最近的地點。

## 來自其他 App 的地點

在 Google 地圖或其他地圖 App 中分享一個地點，然後選擇 **用 CommaView 導航**。它的路線預覽會在首頁開啟，就像已儲存的地點一樣。

## Mapbox

如果您的帳號提供這項功能，「設定 › 地圖與導航」可以改用您自己的 Mapbox 權杖來規劃路線，取代 Stadia Maps。

## 隱私權

您的 Stadia Maps 金鑰只會加密保存在這支手機上，絕不會寫進記錄或放進支援資料包。路線要求會帶著它從您的手機傳到 Stadia Maps；不會有任何內容傳到 CommaView 的帳號服務。搜尋要求會傳到 Photon，並以您 comma 的位置為中心。清除金鑰或登出，就會把它從手機上刪除。

## 安全

請在停車時設定好行程，讓轉彎卡片和語音引導您。導航僅供顯示：它絕不會轉向、煞車，也不會改變 openpilot 的任何行為。開車時請勿操作 CommaView：依照 openpilot 的要求，眼睛看路、雙手握住方向盤。
