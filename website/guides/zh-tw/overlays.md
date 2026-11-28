---
title: "選擇行車畫面並新增疊加套件"
description: "選擇 Live View 繪製道路的方式：comma four 的畫面、comma 3X 的畫面，或 CommaView 自己的。再新增疊加套件，補上您的分支版本在自己畫面上繪製的內容。"
topic: screens
order: 6
kind: walkthrough
lede: "Live View 會在道路鏡頭畫面上畫出行車畫面：**comma four** 的、**comma 3X** 的，或 **CommaView** 自己的。comma 的畫面會以您分支版本的樣式繪製。**疊加套件** 會補上您分支版本自己畫面上有、但 CommaView 沒有繪製的內容，例如 BluePilot 的油電儀表或 dragonpilot 的彩虹路徑。"
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View 可以正常使用"
    text: "Android 手機上的 CommaView 已與您的 comma 配對。還沒有嗎？[設定 CommaView](/zh-tw/guides/setup)。"
  - title: "使用商店需要登入"
    text: "成員可以瀏覽 CommaView 的疊加套件。未登入時，仍可以從檔案或連結新增套件。"
steps:
  - id: switch
    title: "在 Live View 中切換畫面"
    body: |
      在 Live View 中輕觸行車畫面切換按鈕。它以目前顯示的畫面命名，每輕觸一次就切換到下一個：**comma 4**、**comma 3X**、**CommaView**，然後再從頭開始。您最後停留的那一個會保留到下次。
    screen: phone-live-view
    clip: onroad-screen
    pins:
      - target: onroad-screen-button
        text: "行車畫面切換按鈕，以目前顯示的畫面命名。"
    note: "和其他控制項並排放不下時，它會以 **行車畫面** 的名稱收進 **更多**。錄影進行中時它會變暗：錄影會維持開始時的畫面。"
  - id: display
    title: "或在設定 › 顯示中選擇"
    body: |
      想在選擇之前先看看每一種畫面，請開啟 **設定 › 顯示**。**行車畫面** 卡片會在一張道路照片上預覽所選的畫面，依照您 comma 的鏡頭取景，並以您分支版本的樣式繪製。下方的 **已啟用**、**駕駛介入** 和 **未啟用** 會切換顯示的時刻；它們不會儲存任何設定。
    screen: settings-display
    pins:
      - target: onroad-screen-card
        text: "所選畫面的預覽。"
      - target: onroad-screen
        text: "**行車畫面**：輕觸即可查看清單。"
  - id: pick
    title: "選擇一種畫面"
    body: |
      清單中的每一種畫面都有一張小圖和一段說明：

      - **comma four**：MAX 在道路上方，隨時變化，旁邊是方向盤和信心指示。
      - **comma 3X**：狀態邊框、MAX 方塊、大字車速，以及底部的警示。
      - **CommaView**：流動的路徑、鎖定前車的標記，以及 CommaView 自己的車速、狀態和警示。

      選擇一種就會儲存，並更新預覽、它的選項和 Live View。任何畫面都能在兩款 comma 上使用。
    screen: settings-display-onroad-screens
    clip: display-pick
    pins:
      - target: comma-four-option
        text: "**comma four**。"
      - target: comma-3x-option
        text: "**comma 3X**。"
      - target: commaview-option
        text: "**CommaView**。"
    note: "不論您選擇哪一種畫面，警示、警告和駕駛監控狀態一律使用您 comma 自己的顏色。"
  - id: store
    title: "開啟疊加套件商店"
    body: |
      開啟 **設定 › 疊加套件**，或輕觸首頁上的 **疊加套件** 卡片。
    tabs:
      - label: "已登入"
        body: |
          商店會先列出 CommaView 的 **官方** 套件，接著是 **社群** 的，每一個都經過 CommaView 審查。**適用您的 comma** 會推薦適合您 comma 所執行分支版本的官方套件。可以搜尋，也可以用 **全部**、**官方**、**社群** 和 **適用我的 comma** 縮小清單範圍。
        screen: overlay-packs-store
        pins:
          - target: search
            text: "**搜尋套件**。"
          - text: "**適用您的 comma**：適合您 comma 分支版本的官方套件。"
          - target: bluepilot-row
            text: "**官方** 套件，例如 BluePilot HUD。"
          - target: yours
            text: "**您的套件**：這支手機上已有的套件。"
      - label: "從檔案或連結新增"
        body: |
          有人分享了 `.cvpack` 檔案或連結（GitHub、gist、Discord 附件）？開啟 **您的套件**，在 **自行新增套件** 底下輕觸 **從檔案安裝** 或 **貼上連結**。用這種方式新增的套件沒有經過 CommaView 審查，安裝對話方塊也會這樣告知。
  - id: install
    title: "安裝套件"
    body: |
      輕觸一個套件，查看它的預覽、**適用於** 哪些分支版本，以及它會為 Live View 加上什麼。輕觸 **安裝**，再在對話方塊中輕觸一次 **安裝**。套件會安裝到這支手機和您已配對的 comma 上。
    screen: overlay-pack-detail
    pins:
      - text: "預覽：加上套件後的 Live View。輕觸即可放大。"
      - target: install
        text: "**安裝**。"
    note: "官方套件只會在它適用的分支版本上執行。如果您已配對的 comma 都沒有執行這些分支版本，對話方塊會如實告知；它仍會安裝，但要等到有 comma 執行這些分支版本，才會出現在 Live View 中。"
  - id: drive
    title: "下次開車時查看效果"
    body: |
      安裝後，商店會說明套件會在這支手機連到 comma 時傳過去，並在車輛熄火時於 comma 上生效。下次開車時開啟 Live View：套件會畫在 comma four、comma 3X 和 CommaView 畫面上，位於行車畫面自己的警示下方。

      要關閉套件，請開啟 **您的套件**：每個套件只有一個開關，同時套用到這支手機和每一台已配對的 comma。
check: "在 Live View 的 **詳細資訊** 中，**疊加套件** 一列會顯示套件名稱，並標示為 **執行中**。"
fixes:
  - q: "行車畫面切換按鈕變暗了"
    a: "正在錄影。停止錄影或等它結束後再切換。"
  - q: "詳細資訊顯示套件「不適用於此分支版本」"
    a: "這個套件是為其他分支版本的畫面製作的，在您的畫面上不會繪製任何東西。官方套件會在 **適用於** 底下說明它適用的分支版本。"
  - q: "Live View 中還沒有出現套件"
    a: "它會在您的手機連到 comma 時傳過去，並在車輛熄火時於 comma 上生效。請在手機連著 comma 網路的情況下，讓車輛熄火再重新發動，然後開啟 Live View。"
  - q: "「登入以查看 CommaView 的套件」"
    a: "商店只會向已登入的成員列出 CommaView 的套件。輕觸 **登入**。登出期間，手機上已有的套件會繼續運作。"
  - q: "「無法連線到 my.commaview.com」"
    a: "請檢查這支手機的網路連線，再輕觸 **再試一次**。**您的套件** 仍會列出手機上的所有套件。"
related: [live-view, record, forks]
blogPost: commaview-0-0-166-languages-browser-view
---

## 每種畫面的選項

在預覽下方，**設定 › 顯示** 會顯示所選畫面自己的選項：

- **comma four 選項**：**預覽取景**（和 comma four 的取景完全一致、顯示更多鏡頭畫面，或裁切成填滿這個螢幕）和 **精簡信心面板**（較小的面板和圓球，留出更多影像空間）。
- **CommaView 選項**：**鏡頭取景**（**填滿螢幕** 會裁切鏡頭畫面以填滿橫向螢幕；**完整鏡頭** 會顯示完整畫面，必要時加上黑邊）和 **減少動態效果**，它會讓 CommaView 的路徑、車速和鎖定標記保持靜止。
- **comma 3X**：沒有選項。它完全依照 comma 的畫法繪製。

接著是 **所有畫面**：**駕駛座位置**（左右對調控制項）、**主題**、在陽光和眩光下使用的 **日光對比**，以及針對會裁掉畫面邊緣的車用螢幕的 **螢幕邊緣**（[車用螢幕](/zh-tw/guides/car-screens)）。

在「錄影」中製作的回放，會畫出您錄影時 Live View 畫的內容，不論之後您怎麼選擇。

## 疊加圖層從哪裡來

CommaView 不會憑空猜測要畫什麼。您 comma 上的執行環境會在影像旁一併傳送 openpilot 自己的畫面所讀取的駕駛資料（行駛路徑、車道線、前車、車速、警示、駕駛監控），App 再在您的手機上畫出來，並和正在顯示的鏡頭畫面對齊。這些資料延遲、缺漏或屬於另一個鏡頭時，CommaView 會略過那個部分，而不是畫出可能有錯的內容。

## 安全

請在停車時選擇畫面和安裝套件。開車時請勿操作 CommaView：依照 openpilot 的要求，眼睛看路、雙手握住方向盤。疊加圖層只是用來看的，不是駕駛輔助：comma 自己的警示和車輛的儀表永遠優先。駕駛監控圖示並不能證明您專心駕駛，回放中的疊加圖層是用來回顧行程的，不能當作當時實際情況的確切證據。
