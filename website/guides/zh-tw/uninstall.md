---
title: "從您的 comma 移除 CommaView"
description: "在裝置設定中從 comma 解除安裝 CommaView 執行環境，把分支版本的檔案還原為原本的狀態，並在手機上忘記這台 comma。"
topic: account
order: 3
kind: walkthrough
lede: "**解除安裝執行環境** 會從您的 comma 移除 CommaView：它會復原 CommaView 的掛鉤、停止它的執行環境，並刪除 `/data/commaview`。您的分支版本會照常駕駛。可以用它移除 CommaView，或從頭重新執行引導設定。"
parked: true
updated: 2026-11-27
needs:
  - title: "手機和 comma 在一起"
    text: "和 comma 連上同一個 Wi‑Fi，或連上它的熱點。裝置設定需要連到 comma 才能管理更新和移除。"
  - title: "車輛發動並打入 P 檔"
    text: "如果車輛正在行駛，comma 會先排入解除安裝，等車輛打入 P 檔且 openpilot 未啟用時再執行。"
steps:
  - id: device-settings
    title: "開啟 comma 的裝置設定"
    body: |
      從首頁開啟您 comma 的 **裝置設定**，再輕觸 **執行環境**（「更新或解除安裝」）。
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**執行環境**：更新或移除 CommaView。"
  - id: uninstall
    title: "輕觸「解除安裝執行環境」"
    body: |
      在執行環境更新下方，**解除安裝執行環境** 會從這台 comma 移除 CommaView。之後就可以從頭再執行一次引導設定。
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**解除安裝執行環境**。"
  - id: confirm
    title: "確認"
    body: |
      **將移除 CommaView**：CommaView 會復原它的執行環境掛鉤、停止執行，並從這台 comma 刪除 `/data/commaview`。這台 comma 仍會儲存在您的手機上。短暫的倒數結束後，輕觸 **解除安裝執行環境**。
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**將移除 CommaView**，以及這會做什麼。"
      - text: "倒數結束後輕觸 **解除安裝執行環境**。**取消** 會保留 CommaView。"
    note: "如果車輛正在行駛，comma 會先排入解除安裝：等車輛打入 P 檔且 openpilot 未啟用時才會移除 CommaView，在那之前它會繼續執行。"
  - id: forget
    title: "如果需要，在手機上忘記這台 comma"
    body: |
      裝置設定現在會顯示執行環境已移除。如果也想把這台 comma 從手機上移除，請輕觸裝置設定最下方的 **忘記這台 comma**：CommaView 將不再顯示這台 comma，並刪除它的配對金鑰。要移除 App 本身，請像解除安裝任何 App 一樣，在 Android 的設定中解除安裝 CommaView。
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**忘記這台 comma**。"
check: "對話方塊顯示 **已解除安裝執行環境**，裝置設定中的執行環境顯示 **已移除**：「已從您的 comma 解除安裝 CommaView。請執行引導設定以重新安裝。」"
fixes:
  - q: "「因 SSH 權限錯誤，解除安裝失敗」"
    a: "comma 不允許這支手機透過 SSH 登入。請確認 comma 上 **設定 → 裝置 → SSH** 已開啟，而且它的 GitHub 使用者名稱底下有這支手機的金鑰，然後輕觸 **再次解除安裝**。"
  - q: "「comma 無法解除安裝 CommaView，因此維持原狀」"
    a: "沒有移除任何東西。請在車輛打入 P 檔時再試一次。"
  - q: "「已排入解除安裝，等待車輛打入 P 檔」"
    a: "車輛正在行駛。請打入 P 檔並讓 openpilot 未啟用，保持車輛發動，comma 會自行移除 CommaView。"
  - q: "「解除安裝」按鈕呈灰色"
    a: "CommaView 已經在更新或解除安裝執行環境。請等它完成後再試一次。"
related: [setup, update-runtime, forks]
---

## 解除安裝會還原什麼

- **在列出的分支版本上**，它會復原 CommaView 加在分支版本螢幕介面中的小掛鉤。
- **在 CommaView 未列出的分支版本上**（盡力支援），它會把分支版本的檔案還原為原本的狀態。
- **僅影像** 模式沒有變動分支版本的任何檔案，解除安裝會移除執行環境。

在 SunnyPilot-TeslaHW1 上，請先解除安裝執行環境，再執行 `op fork update`，因為安裝了 CommaView 的掛鉤時，它無法切換分支版本。詳情請看[檢查您的 comma 和分支版本是否受支援](/zh-tw/guides/forks)。

## 重新設定 CommaView

解除安裝後，這台 comma 仍會儲存在您的手機上。執行[引導設定](/zh-tw/guides/setup)，就能以全新安裝的方式重新安裝。
