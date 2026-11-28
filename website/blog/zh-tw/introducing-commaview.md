---
title: "CommaView 介紹：comma 裝置的本機鏡頭串流"
description: "CommaView 是一款 Android App，可在本機觀看 comma 裝置的鏡頭畫面，提供 MICI 風格的疊加圖層、執行環境設定、錄影和行程回放。"
date: 2026-05-02
slug: introducing-commaview
tags:
  - CommaView
  - comma 裝置鏡頭串流
  - Android App
  - openpilot 工具
heroLabel: "產品說明"
draft: false
---

我們做 CommaView，是因為在本機觀看 comma 裝置的鏡頭，應該是一個真正的產品，而不是一堆黏在 SSH 連線上的指令碼。

目標很單純：把一台 Android 裝置和您的 comma 配對，在本機串流道路鏡頭的畫面，顯示實用的駕駛疊加圖層，並讓設定過程平淡無奇，而這正是最好的那種平淡。

## 為什麼以本機為優先？

CommaView 並不打算成為雲端主控台。App 透過本機連線與您的 comma 裝置溝通，讓核心流程始終貼近硬體。

這很重要：以本機為優先的 comma 鏡頭串流 App 可以保持快速、容易理解，也更重視隱私權。只是想看看自己的裝置看到了什麼，不該需要先註冊帳號。

## CommaView 能做什麼

目前的 Alpha 版專注在讓日常測試少一點麻煩的部分：

- 把道路鏡頭畫面在本機串流到 Android
- MICI 風格的路徑、車道、狀態和駕駛監控疊加圖層
- 為 comma 端的 `commaviewd` 服務提供引導式執行環境設定
- 行程錄影和回放匯出
- App 與執行環境的版本配對，讓測試者安裝彼此相容的版本

## 為什麼先做 Android？

CommaView 只支援 Android，因為 Android 是這套流程最實際的平台：手機、平板、側載安裝、區域網路和適合車上使用的硬體，在這裡都更容易搭配。

專注在這裡，App 才能保持精簡俐落，不必為了遷就每一種平台而處處妥協。

## 接下來

早期測試者的參與，會幫助我們把安裝流程打磨得更穩、驗證裝置相容性，並在更多車款和 comma 配置上改善即時疊加圖層的對齊。

如果想加入，請在首頁登記搶先體驗名單。隨著 CommaView 成長，我們會在部落格發布版本說明、測試者近況和技術筆記。
