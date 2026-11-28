---
title: "CommaView 的版本發布方式"
description: "CommaView App 和您 comma 上的執行環境如何發布：先是 Alpha，再是 Beta；經過簽署的下載檔、相符的執行環境，以及等到打入 P 檔才進行的更新。"
topic: account
order: 2
kind: reference
lede: "CommaView 有兩個部分，會一起更新：Android App，以及您 comma 上的小型執行環境。以下說明一個版本如何送到您手上，以及更新如何保持安全。"
updated: 2026-11-27
steps:
  - id: version
    title: "查看您使用的版本"
    body: |
      設定 › **關於** 會顯示 App 的版本，以及它是 **已是最新版本**，還是有可用的更新和更新的版本號碼。CommaView 會在您的帳號中檢查是否有新版本，並在新版本準備好時通知您。
    screen: support-about
    pins:
      - target: version
        text: "App 的版本。"
      - target: up-to-date
        text: "**已是最新版本**，或為您準備好的新版本。"
  - id: app-update
    title: "在 App 中更新 App"
    body: |
      有新版本時，首頁頂端和 **關於** 中會顯示 **更新**。**更新 CommaView** 會顯示版本號碼和發布管道：**Beta** 給所有受邀的使用者；**Alpha** 則是「給測試人員的早期版本，可能比 Beta 問題更多。」輕觸 **下載**：CommaView 會在背景下載並檢查，接著由 Android 請您確認安裝。
    screen: app-update-offer
    pins:
      - target: channel
        text: "發布管道：**Beta** 或 **Alpha**。"
      - target: download
        text: "**下載**。**稍後再說** 則留到之後再處理。"
  - id: runtime
    title: "接著更新您 comma 的執行環境"
    body: |
      每個 App 版本都會指明與它一起測試過的執行環境。App 更新後，首頁會以 **執行環境更新已就緒** 提供那個執行環境。執行環境更新只會從 App 開始，絕不會自行進行。[更新 comma 的執行環境](/zh-tw/guides/update-runtime) 列出了每個步驟。
    screen: home-runtime-update
    pins:
      - target: update-card
        text: "**執行環境更新**：已安裝的和可用的執行環境。"
related: [update-runtime, uninstall, setup]
---

## 先 Alpha，再 Beta

- 每個版本會先以一系列 Alpha 版發給少數測試人員。
- 某個 Alpha 版表現穩定後，它就成為這個版本的 Beta 版，發給所有受邀的使用者。
- 您在 [my.commaview.com](https://my.commaview.com) 的帳號一律會提供適合您的版本。

## 簽署與相符

- 每個 App 下載檔都是經過簽署的正式版建置，絕不是偵錯建置，my.commaview.com 上會在旁邊顯示它的 SHA-256 校驗碼。App 在提供安裝之前，會先檢查下載的更新的大小和校驗碼：「下載內容與校驗碼不符，因此未安裝。」
- 每個 App 版本都會指明與它一起測試過的執行環境，App 在您 comma 上安裝的就是那一個。
- 舊版 App 絕不會收到沒有和它一起測試過的執行環境。如果 comma 的執行環境比 App 會安裝的還新，App 會如實告知：請更新 CommaView，再試一次。

## 安全地更新您的 comma

- 執行環境更新從首頁或裝置設定開始，絕不會自行進行。
- 更新絕不會中斷行程。如果車輛正在行駛，安全更新會先排入更新，等車輛打入 P 檔且 openpilot 未啟用時，comma 再進行安裝。您不需要熄火。
- 執行環境更新後，comma 需要重新啟動，CommaView 才能再次串流。App 會請您重新啟動。
- 您隨時可以在裝置設定中移除執行環境：[移除 CommaView](/zh-tw/guides/uninstall)。

## 從哪裡得到消息

- 有新版本時，App 會通知您。
- [最新消息](/whats-new) 列出了每一項變更。
- 有重要變更時我們會寄電子郵件給您，您也隨時可以從 App 傳送意見回饋（設定 › **支援與診斷**）。
