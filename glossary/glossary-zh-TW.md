# 繁體中文（台灣）glossary

The words every Traditional Chinese string uses for CommaView's terms, so screens translated apart say the same
thing. Where openpilot already translates a term (`selfdrive/ui/translations/app_zh-CHT.po`), its word is used, so
the app says what the car's screen says. Machine drafted; a native speaker's review is owed before release
(the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`).

## Style

- Address the person as **您**, as openpilot's translation does.
- Full-width punctuation in Chinese text: ，。、：；？！「」（）. A half-width space between Chinese and a Latin word or
  number ("在 comma 上", "25.7 GB 可用"), none before full-width punctuation.
- Quotes are 「」, nested 『』.
- Buttons are short verbs: 取消, 完成, 儲存, 刪除, 重試, 繼續, 開啟, 關閉.
- No trailing 。 on titles, buttons, row titles or pills; whole sentences in body text end with 。.

## Terms

| English | 繁體中文 | Note |
|---|---|---|
| Home (dock) | 首頁 | |
| Recordings | 錄影 | the section and its saved drives |
| Settings | 設定 | |
| recording, a recording | 錄影 | |
| drive (a trip the comma recorded) | 行程 | |
| replay | 回放 | |
| live copy | 即時副本 | |
| saved moment | 保存的片段 | |
| Record | 錄影 | the rail's button |
| Go live / live streaming | 直播 | |
| onroad screen | 行車畫面 | |
| onroad / offroad (the comma's state) | 行駛中 / 停車中 | |
| design (an onroad screen's look) | 樣式 | |
| overlay pack | 疊加套件 | |
| fork | 分支版本 | "fork" alone when it's openpilot jargon in a sentence for developers |
| runtime (commaviewd) | 執行環境 | |
| update / install / uninstall | 更新 / 安裝 / 解除安裝 | openpilot's |
| reboot | 重新啟動 | openpilot's |
| power off | 關機 | openpilot's |
| pair / pairing | 配對 | openpilot's |
| device (the comma) | 裝置 | openpilot's |
| this phone / this device (the device CommaView runs on) | 這支手機 / 這部裝置 | `common_this_phone` / `common_this_device`, a sentence's placeholder (how-to-localize.md, "This phone or this device") |
| your phone / your device (`common_your_*`) | 您的手機 / 您的裝置 | no spaces around the placeholder |
| connected / disconnected | 已連線 / 已中斷連線 | |
| offline | 離線 | |
| engaged / disengaged | 已啟用 / 未啟用 | openpilot shows "脫離" for the act of disengaging |
| override | 駕駛介入 | |
| experimental mode | 實驗模式 | openpilot's |
| driver monitoring | 駕駛監控 | openpilot's |
| driver camera | 車內鏡頭 | openpilot's |
| road camera / wide camera | 道路鏡頭 / 廣角鏡頭 | |
| lead car | 前車 | |
| speed limit | 速限 | |
| set speed / MAX | 設定速度 / 最大 | openpilot's MAX is 最大 |
| lane change | 變換車道 | |
| calibration | 校正 | openpilot's |
| driver position (left/right-hand drive) | 駕駛座位置（左駕／右駕） | |
| daylight contrast | 日光對比 | |
| offline maps | 離線地圖 | |
| navigation | 導航 | |
| Home / Work (places) | 住家 / 公司 | |
| vehicle location | 車輛位置 | |
| account / sign in / sign out | 帳號 / 登入 / 登出 | |
| leaderboard | 排行榜 | |
| achievement | 成就 | |
| privacy | 隱私權 | |
| diagnostics | 診斷資料 | |
| report a problem | 回報問題 | |
| Details (Live View's pane) | 詳細資訊 | |
| stream health | 串流狀態 | |
| storage | 儲存空間 | |
| hotspot | 熱點 | |
| Live / Delayed (Live View's state) | 即時 / 延遲 | |
| frame pacing | 影格節奏 | |
| inset (a picture in the picture) | 子畫面 | |
| framing: Fill / Exact / Extend / Auto | 填滿螢幕 / 精確 / 延伸 / 自動 | |
| camera framing | 鏡頭取景 | |
| reduce motion | 減少動態效果 | |
| screen edges | 螢幕邊緣 | |
| View (Surround's) / chase / high / top-down | 視角 / 追蹤 / 高處 / 俯視 | |
| vehicle detection / detector / model | 車輛偵測 / 偵測器 / 偵測模型 | |
| renderer | 繪製器 | |
| key (an API key, an SSH key) | 金鑰 | public / private: 公開 / 私密金鑰 |
| dashboard (a service's) | 主控台 | |
| reroute | 重新規劃路線 | |
| Where to? | 要去哪裡？ | |
| map source | 地圖來源 | |
| Powered by | 技術提供 | |
| steering / speed active, manual (the HUD's control line) | 轉向作用中 / 速度作用中 / 手動控制 | review on a drive |
| steering only / speed only | 僅轉向 / 僅速度 | |
| blind spot | 盲點 | |
| green light / lead car moving | 綠燈 / 前車起步 | |
| safe update / install / repair | 安全更新 / 安全安裝 / 安全修復 | |
| overlays (drawn on video) | 疊加圖層 | not overlay packs (疊加套件) |
| telemetry | 遙測資料 | |
| patch | 修補程式 | |
| in Park | 打入 P 檔 | |
| power harness | 常時供電線 | |
| guided / manual setup | 引導設定 / 手動設定 | |
| boot hook / runtime hook | 開機掛鉤 / 執行環境掛鉤 | |
| vehicle security key | 車輛安全金鑰 | |
| pair code / invitation | 配對碼 / 邀請碼 | |
| phones with a key | 擁有金鑰的手機 | |
| shared token | 共用權杖 | |
| development runtime | 開發版執行環境 | |
| controller | 控制裝置 | |
| best effort | 盡力支援 | |
| video only | 僅影像模式 | |
| widgets | 小工具 | |
| backup / restore | 備份 / 還原 | |
| read-only | 唯讀 | |
| head unit | 車機 | |
| nearby devices | 鄰近裝置 | Android's permission |
| display over other apps | 顯示在其他應用程式上層 | Android's permission |
| set aside (saved lists) | 另外保留 | |
| Not now / Review | 稍後再說 / 檢視 | |
| queue | 佇列 | |
| Needs processing | 待處理 | |
| pull drives | 拉取行程 | |
| whole drive | 完整行程 | |
| export | 匯出 | |
| pack studio | 套件工作室 | |
| clip | 片段影片 | |
| log excerpt | 記錄摘錄 | |
| support bundle | 支援資料包 | |
| Driving insights | 駕駛統計 | |
| contribute | 貢獻 | |
| route / segment (openpilot's) | 路線 / 片段 | |
| Privacy & sharing | 隱私權與分享 | the Settings page |
| stream key | 串流金鑰 | |
| destination (Go live's) | 直播目的地 | |
| Go live | 開始直播 | |
| YouTube Studio | YouTube 工作室 | |
| Auto-start | 自動開始 | |
| Public / Unlisted / Private | 公開 / 不公開 / 私人 | YouTube's |
| input (microphone) | 輸入來源 | |
| car hands-free | 車用免持 | |
| metered / monthly limit | 計量 / 每月上限 | |
| Your requests | 您的請求 | |
| Open / Closed (a request) | 處理中 / 已結案 | |
| license | 授權 | |
| map library | 地圖庫 | |
| map theme | 地圖主題 | |
| spoken guidance | 語音導引 | |
| dev build | 開發版本 | |
| access pass | 存取通行證 | the account's |
| waitlist | 候補名單 | |
| beta member / admin | Beta 成員 / 管理員 | |
| display name / public name | 顯示名稱 / 公開名稱 | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | 本週 / 上週 / 累計 | |
| finalized (a week) | 已確定 | |
| badge / share card | 徽章 / 分享卡片 | |
| Official / Community (packs) | 官方 / 社群 | |
| reviewed by CommaView / unreviewed | 經 CommaView 審查 / 未經審查 | |
| Update ready | 可更新 | |
| training collection | 訓練資料集 | car detection's |
| recording metadata | 錄影中繼資料 | |
| SSH identity (a comma's host key) | SSH 身分 | |
| keystore | 金鑰儲存區 | Android's |
| repository (a fork's) | 儲存庫 | |
| driving software | 駕駛軟體 | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | 還原為原本的狀態 | |
