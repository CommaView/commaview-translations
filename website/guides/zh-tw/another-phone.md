---
title: "新增另一支手機或平板"
description: "用 10 分鐘內有效的邀請碼，讓另一支手機、平板或車用螢幕取得自己的 comma 金鑰，並查看和移除擁有金鑰的手機。"
topic: start
order: 4
kind: walkthrough
lede: "每一支觀看您 comma 的手機都有自己的金鑰。要新增另一支手機、平板或車用螢幕，請在已經連接這台 comma 的手機上顯示邀請碼，再到新裝置上輸入或掃描。不需要 SSH，也不必重新設定。"
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "一支擁有金鑰的手機"
    text: "一支已與您的 comma 配對的手機，使用 CommaView 0.0.166 以上版本及其執行環境。還沒有嗎？[設定 CommaView](/zh-tw/guides/setup)。"
  - title: "新裝置上的 CommaView"
    text: "已安裝並登入，版本為 0.0.166 以上。[取得 App](/zh-tw/guides/setup#step-get-the-app)。"
  - title: "同一個網路"
    text: "兩者都和 comma 連上同一個 Wi‑Fi，或都連上 comma 的熱點。"
howItWorks:
  - title: "您的手機"
    text: "向 comma 要求一組邀請碼：一組代碼或一個 QR 碼，10 分鐘內有效。"
  - title: "新手機"
    text: "用邀請碼加入，並取得自己的金鑰。"
    edge: "區域網路"
  - title: "您的 comma"
    text: "通知每一支擁有金鑰的手機：有新手機取得了金鑰。"
steps:
  - id: device-settings
    title: "在手機上開啟「配對其他手機」"
    body: |
      在已經連接您 comma 的手機上，從首頁開啟 comma 的 **裝置設定**，再輕觸 **配對其他手機**。
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**配對其他手機**：產生一組短時間有效的代碼，讓另一支手機或平板可以連線。"
  - id: show-invitation
    title: "顯示邀請碼"
    body: |
      在 **擁有金鑰的手機** 底下，**新增另一支手機** 會為還沒有這台 comma 的手機顯示邀請碼。輕觸 **顯示邀請碼**。
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**顯示邀請碼**。"
      - text: "擁有這台 comma 金鑰的手機，目前這支排在最前面。"
  - id: invitation
    title: "讓邀請碼保持顯示"
    body: |
      **新增另一支手機** 會顯示分成三組的代碼、一個 QR 碼和 comma 的 IP 位址。它在 10 分鐘內有效，而且只能使用一次。過期後，請再顯示一組新的。
    screen: invitation-dialog
    pins:
      - target: code
        text: "要在新手機上輸入的代碼。"
      - target: qr
        text: "或是掃描這個 QR 碼。"
      - text: "**… 後過期**：從顯示時起算 10 分鐘。"
  - id: add-comma
    title: "在新手機上新增 comma"
    body: |
      在新手機的 **連接您的 comma** 畫面輕觸 **配對已執行 CommaView 的 comma**。如果新手機上已經有 comma，請改為在首頁輕觸 **新增 comma**。

      您的 comma 會出現在 **在這個網路上** 底下。輕觸它，或輕觸 **掃描 QR 碼** 掃描邀請碼。如果清單中沒有它，請輕觸 **輸入位址與配對碼**。
    screen: add-comma
    pins:
      - target: found-comma
        text: "在這個網路上找到的您的 comma。"
      - target: scan-qr
        text: "**掃描 QR 碼** 來掃描邀請碼。"
      - target: enter-address
        text: "清單中沒有時，輕觸 **輸入位址與配對碼**。"
  - id: pair
    title: "輸入邀請碼並配對"
    body: |
      確認 **comma IP**，在 **配對碼或邀請碼** 中輸入邀請碼（或輕觸 QR 碼按鈕掃描），然後輕觸 **配對 comma**。新手機會取得自己的金鑰，並在首頁顯示您的 comma。
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**comma IP**，找到的 comma 會自動填入。"
      - target: pair-code
        text: "**配對碼或邀請碼**。"
      - target: scan-qr
        text: "**掃描配對 QR 碼**。"
      - target: pair
        text: "**配對 comma**。"
  - id: new-key
    title: "在其他手機上確認"
    body: |
      每一支擁有金鑰的手機都會收到通知：**有新手機取得了金鑰**，並附上它的名稱和時間。輕觸 **這是我的**。如果不是您的裝置，請輕觸 **移除**；**查看手機** 會開啟 **配對其他手機**，列出每一支擁有金鑰的手機。
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "**這是我的**：適用於您自己的手機或平板。"
      - target: review
        text: "**查看手機** 會列出每一支擁有金鑰的手機。"
check: "新手機在首頁顯示您的 comma，而且能開啟 Live View。在第一支手機上，**配對其他手機** 會在 **擁有金鑰的手機** 底下列出它。"
fixes:
  - q: "「無法使用該邀請碼加入」"
    a: "它可能輸入錯誤、已經過期或已被使用。請在已經有這台 comma 的手機上顯示新的邀請碼（在它的裝置設定中依序輕觸 **配對其他手機**、**新增另一支手機**）。"
  - q: "「這台 comma 的執行環境早於手機金鑰功能」"
    a: "請先更新 comma 的執行環境：[更新 comma 的執行環境](/zh-tw/guides/update-runtime)。然後再顯示邀請碼。"
  - q: "「連不到這台 comma」"
    a: "兩支手機都必須和 comma 連上同一個 Wi‑Fi，或連上它的熱點。[在車上連線](/zh-tw/guides/connect-in-the-car)。"
  - q: "「配對失敗：這台 comma 已不再透過配對碼配對」"
    a: "comma 已經不再接受舊的共用權杖。請從已經擁有金鑰的手機新增這支手機（在它的設定中輕觸 **新增另一支手機**），或重新為這台 comma 執行設定。"
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## 移除手機

在擁有金鑰的手機上，開啟 comma 的 **裝置設定**，再輕觸 **配對其他手機**。在清單中某支手機旁輕觸 **移除**。之後它就無法再連上這台 comma，除非再次用邀請碼或重新設定 comma 把它加回來。

## 使用舊版 CommaView 的手機

0.0.166 以前，每支手機都會傳送同一個共用權杖給 comma。升級到 0.0.166 的手機會在下次連線時取得自己的金鑰，不必重新配對。

- **配對其他手機** 中的 **舊版 CommaView App** 會顯示，使用舊版 CommaView 的手機還能用共用權杖使用這台 comma 多少天：從第一支手機取得金鑰起算 90 天。在那之前，**供舊版 App 使用的配對碼** 可以配對使用舊版 CommaView 的手機。
- 當每一支使用共用權杖的手機都有了金鑰，**立即停止** 會讓 comma 不再接受共用權杖。屆時使用舊版 CommaView 的手機將無法再使用這台 comma，更新之前也無法重新配對。
- 此後，沒有金鑰的手機需要 CommaView 0.0.166 以上版本和一組邀請碼。

更新 comma 的執行環境時，請先更新每一部觀看它的裝置上的 CommaView，車用螢幕也一樣。
