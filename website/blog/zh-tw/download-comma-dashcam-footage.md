---
title: "如何從 comma 裝置下載行車錄影"
description: "一份實用指南：comma 的影片檔案、comma 3/3X/four 之間的差異，以及匯出路線錄影最穩妥的方法。"
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma 裝置影片
  - 行車記錄器影像
  - openpilot 工具
  - SSH
heroLabel: "comma 裝置指南"
draft: false
---

需要從 comma 裝置取出影片嗎？常見的方式有 comma connect、Openpilot Toolkit，或直接透過 SSH/SFTP 存取。

讓人卡關的是檔案結構。comma 裝置會把 openpilot 路線錄成一段段很短的片段，而不是一支巨大的行車記錄器影片。每個片段都可能包含原始鏡頭檔案、預覽影片和路線記錄。搞懂這一點之後，匯出錄影就沒那麼神祕了。

先講一個重要提醒：comma 裝置在道路錄影、除錯和路線回顧上很有用，但它無法直接取代專門的行車記錄器。

## comma 裝置是有用的鏡頭，但不是完美的行車記錄器

專門的行車記錄器是圍繞蒐證設計的：快速開機、碰撞後仍能保存、停車監控、簡單的檔案匯出、可選的後方鏡頭，以及可拆式儲存。

comma 裝置是為了執行 openpilot 而設計的。它錄下路線資料，是因為這些資料對駕駛模型、除錯、connect 預覽和開發很有用。這些錄影可能很有價值，但也有取捨：

- 取出錄影可能比拔 SD 卡麻煩
- 碰撞或突然斷電可能讓最近的錄影遺失
- 停車監控錄影不是主要的設計目標
- 不包含朝後拍攝的行車記錄器畫面
- 裝置需要空間時，會刪除舊的本機資料

如果目標是可靠的碰撞錄影，請使用真正的行車記錄器。如果目標是 openpilot 路線錄影、開發回顧或本機影片匯出，那麼 comma 的這套流程值得學起來。

## openpilot 會錄下哪些檔案？

openpilot 官方記錄文件把路線描述為一分鐘一段的片段。每個片段中，新版 openpilot 會錄下這些類型的檔案：

| 檔案 | 內容 |
| --- | --- |
| `fcamera.hevc` | 道路鏡頭影片，H.265/HEVC |
| `ecamera.hevc` | 廣角道路鏡頭影片，H.265/HEVC |
| `dcamera.hevc` | 駕駛／車內鏡頭影片，H.265/HEVC |
| `qcamera.ts` | 來自道路鏡頭的較低解析度 H.264 預覽 |
| `rlog.zst` | 完整路線記錄 |
| `qlog.zst` | 較小的／抽樣的路線記錄 |

comma connect 中顯示的影片是較低解析度的 `qcamera.ts`。完整解析度的鏡頭錄影存在 HEVC 檔案中，可能需要透過 connect 手動上傳，或直接從裝置複製。

較舊的路線、較舊的分支版本或較舊的文件，可能會顯示不含 `.zst` 的 `rlog`/`qlog`，或更舊的 `.bz2` 記錄檔名稱。對於目前的 openpilot，請使用上面的檔名。

## comma 3、comma 3X 和 comma four：有什麼不同？

大家常把兩件事混在一起：鏡頭硬體和檔案結構。

鏡頭硬體依世代而不同：

| 裝置 | 鏡頭／儲存說明 |
| --- | --- |
| comma 3 | 三顆 1080p 鏡頭，120 dB HDR。社群文件列出幾種儲存容量版本：1TB、250GB、後期的 64GB 和早期的 32GB。 |
| comma 3X | 和 comma 3 相同的三鏡頭配置，升級為 OX03C10 影像感測器，140 dB HDR，通常標示為 128GB 儲存空間。 |
| comma four | comma 表示它擁有和 comma 3X 相同的運算能力、感測器組合和功能，但機身小得多。三鏡頭系統裝在 1.9 吋螢幕大小的機身裡，包括兩顆朝向道路的鏡頭和一顆夜視車內鏡頭。comma 標示其儲存空間為 128GB，可存 10 小時的錄影。 |

這裡關於檔案的說明適用於這三款裝置。CommaView 本身只支援 comma 3X 和 comma four。

對於目前的 openpilot，各款 comma 硬體的實際檔案結構是相同的。新版的片段檔案為 `fcamera.hevc`、`ecamera.hevc`、`dcamera.hevc`、`qcamera.ts`、`rlog.zst` 和 `qlog.zst`。

也就是說，鏡頭的實體硬體可以改變，匯出的檔名卻維持熟悉。`fcamera.hevc` 是道路鏡頭，`ecamera.hevc` 是廣角道路鏡頭，`dcamera.hevc` 是駕駛／車內鏡頭。

如果您執行的是自訂分支版本，請先在裝置上確認，不要假設每個檔案都在。分支版本可能會變更錄影設定，而駕駛／車內鏡頭的錄影可能取決於裝置設定。

## 檔案存在本機的哪裡？

在 comma 硬體上，openpilot 目前的記錄根目錄是：

```text
/data/media/0/realdata
```

在這個資料夾裡，每個路線片段都有一個以時間戳記命名的資料夾，例如：

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

您要在這個資料夾裡找以下檔案：

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

如果直接使用 SSH/SFTP，就從這個資料夾開始。官方文件說明了如何透過 SSH 連線到 comma 3X 或 comma four，而 openpilot 使用 `/data/media/0/realdata` 作為裝置上的記錄根目錄。

## 方法一：使用 comma connect

對於最近的行程，comma connect 通常是最簡單的起點。

以下情況請使用 connect：

- 路線是最近的
- 裝置已成功上傳這條路線
- 預覽影片就夠用
- 您想用網頁介面而不是 SSH
- 您只需要幾段片段或幾個檔案

很多使用者也是先在 connect 中找出自己需要的路線和片段編號。問題在於保留期限：connect 可能在本機裝置刪除路線之前，就不再顯示它。如果 connect 不再顯示某條路線，但檔案還在裝置上，透過 SSH/SFTP 或許還能救回來。

另外請記得，connect 的預覽是根據 `qcamera.ts`。如果您需要完整解析度的鏡頭錄影，請確認完整影片檔已上傳，或直接拉取原始 HEVC 檔案。

## 方法二：使用 Openpilot Toolkit

Openpilot Toolkit 是一款社群工具，可以讓本機匯出輕鬆一點。它提供 SSH 設定、檔案瀏覽、行程影片預覽和原始檔案匯出等流程。

以下情況請使用 Openpilot Toolkit：

- 您想要圖形介面
- 您不想自己手寫 SSH 指令
- 您需要協助設定金鑰
- 您使用的是 Windows 或 Android
- 您想更直接地瀏覽和匯出路線錄影

對很多使用者來說，這是最好的折衷：比 connect 更能掌控，又比手動操作終端機省事。

## 方法三：直接使用 SSH 或 SFTP

直接使用 SSH/SFTP 最能掌控，但也最需要自己動手。

大致來說，SSH 存取通常代表：

1. 建立或使用一個設定了 SSH 金鑰的 GitHub 帳號。
2. 在 comma 裝置的設定中啟用 SSH。
3. 在 comma 裝置上輸入您的 GitHub 使用者名稱，讓它取得您的公開金鑰。
4. 以使用者 `comma` 連線到連接埠 `22`。

連線後，從以下位置瀏覽或複製：

```text
/data/media/0/realdata
```

以下情況請使用直接存取：

- 您需要原始的 `fcamera.hevc`、`ecamera.hevc` 或 `dcamera.hevc` 檔案
- connect 中沒有您需要的檔案
- 您想封存整條路線
- 您熟悉 FileZilla 或 WinSCP 這類 SFTP 用戶端
- 您熟悉 `ssh`、`scp` 或 `rsync`

原始 `.hevc` 檔案通常可以用 VLC 播放。如果其他 App 需要 MP4，盡量用 ffmpeg 重新封裝，而不是重新編碼。

## 該用哪一種方法？

如果行程是最近的，一般的路線回顧就夠用，請使用 comma connect。

如果您想要更友善的本機流程，又不想手動完成每一個 SSH/SFTP 步驟，請使用 Openpilot Toolkit。

如果您需要原始檔案、較舊的本機檔案、完整的路線封存，或想直接控制要複製什麼，請使用 SSH 或 SFTP。

## CommaView 的定位

CommaView 是一款以本機為優先的 Android App，用於 comma 裝置的鏡頭串流、疊加圖層、執行環境設定、錄影和回放流程。

它和本機鏡頭存取屬於同一個領域，但它不是 comma connect，不是 Openpilot Toolkit，也不是傳統的行車記錄器。它不應被當作駕駛輔助工具，也不該是車上唯一的蒐證系統。

CommaView 支援 comma 3X 和 comma four，執行 openpilot 或[支援的分支版本](/forks)：sunnypilot、StarPilot、xnor、AdventurePilot、SunnyPilot-TeslaHW1 或 carrotpilot。comma 3 不支援：comma 把它移到一個凍結的長期 openpilot 版本上，CommaView 無法從它的畫面繪製疊加圖層（[原因](/zh-tw#faq-comma-3)）。

## 延伸閱讀

- openpilot 官方記錄文件：[Logging](https://docs.comma.ai/concepts/logs/)
- comma 官方 SSH 文件：[連線到 comma 3X 或 comma four](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect：[comma.ai/connect](https://comma.ai/connect)
- openpilot wiki：[Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma：[Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit：[專案頁面](https://spektor56.github.io/OpenpilotToolkit/)
