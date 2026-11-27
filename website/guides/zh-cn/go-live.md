---
title: "直播到 YouTube 或其他服务器"
description: "把 Live View 显示的道路和行车画面，以 720p 或 1080p 推流到您的 YouTube 频道或任何 RTMP 服务器。设置一次，之后从 Live View 开始直播。"
topic: screens
order: 5
kind: walkthrough
lede: "**直播** 会把 Live View 显示的内容，也就是道路及其行车画面，从您的手机以 720p 或 1080p 推流到您的 YouTube 频道或任何 RTMP 服务器。在“设置”中设置一次，之后从 Live View 开始。"
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View 可以正常使用"
    text: "Android 手机上的 CommaView 已与您的 comma 配对。还没有？[设置 CommaView](/zh-cn/guides/setup)。"
  - title: "推流的去处"
    text: "一个可以登录的 YouTube 频道，或从 YouTube 工作室或其他 RTMP 服务器获取的推流密钥。"
  - title: "手机能上网"
    text: "comma 的 Wi‑Fi 无法上网时，推流会使用手机的移动数据：720p 下每小时约 1.4 GB。"
howItWorks:
  - title: "您的 comma"
    text: "像平时一样把 Live View 发送到您的手机。"
  - title: "您的手机"
    text: "推流 Live View 绘制的内容：每秒 20 帧，720p 或 1080p。"
    edge: "互联网"
  - title: "YouTube 或您的服务器"
    text: "播给您允许观看的人。"
steps:
  - id: settings
    title: "打开设置 › 直播"
    body: |
      打开 **设置**，点按 **直播**。在您设置好之前，这一行会显示 **需设置**。
    screen: support-settings
    pins:
      - target: live-streaming-row
        text: "**直播**。"
  - id: destination
    title: "选择推流的去处"
    tabs:
      - label: "使用 YouTube 登录"
        body: |
          点按 **使用 YouTube 登录**。Google 的登录页会在浏览器中打开，您可以在那里选择账号和频道。登录后，每次直播都会在您的频道上创建一场直播，并由 YouTube 自动开始：无需推流密钥，也无需在 YouTube 工作室中按任何按钮。之后 **直播目的地** 卡片会显示您的频道，以及 **已登录**。
        screen: settings-live-streaming
        pins:
          - target: destination-row
            text: "**直播目的地**：您的频道，已登录。"
        note: "Google 自己的登录页没有配图。"
      - label: "推流密钥或服务器"
        body: |
          点按 **使用推流密钥**（或 **设置直播目的地**），选择 **平台**：**YouTube** 或 **其他服务器**，然后粘贴推流密钥。对于 YouTube：在 YouTube 工作室中依次选择“创建 › 进行直播 › 直播”，复制推流密钥，并在那里开启“自动开始”，这样每场直播都会在视频到达时开始。对于其他服务器，还要粘贴它的 `rtmp://` 或 `rtmps://` 地址。点按 **保存直播目的地**。
        screen: settings-live-streaming-destination
        pins:
          - target: platform
            text: "**平台**。"
          - target: stream-key
            text: "推流密钥。它只保存在这部手机上，也只会发送到它对应的服务器。"
          - target: save
            text: "**保存直播目的地**。"
        note: "`rtmp://` 会以不加密的方式发送推流密钥。如果服务器支持，请使用 `rtmps://`。"
  - id: choices
    title: "检查谁可以观看、画质和声音"
    body: |
      - **谁可以观看**（使用 YouTube 登录时）：**公开**、**不公开列出** 或 **私享**。默认为 **不公开列出**。使用推流密钥时，请在 YouTube 工作室中选择。观看的人都能看到您开到了哪里。
      - **标题与说明**（使用 YouTube 登录时）：每场直播的名称，可以用标签插入日期、车辆等信息。
      - **画质**：720p 或 1080p，并显示各自每小时大约使用多少移动数据。
      - **声音**：默认关闭，除非您选择 comma 的麦克风或这部手机的麦克风。车内所有人的声音都会被录进去，包括乘客。声音只会进入您的推流和实时副本，绝不会发送给 CommaView。

      **开始直播前** 汇总了所有信息：数据用量、车内摄像头，以及推流何时停止。
    screen: settings-live-streaming
    pins:
      - text: "**标题与说明**。"
      - target: sound-row
        text: "**声音**。"
  - id: go
    title: "在 Live View 中点按“直播”"
    body: |
      打开 Live View，点按 **直播**。它会显示 **启动中…**，然后显示您已直播了多久。请在出发前开始，之后就不要再操作。
    screen: phone-live-view
    pins:
      - target: go-live-button
        text: "**直播**。放不下时，它在 **更多** 里。"
    warn: "只要 **车内摄像头** 开启，推流就会显示车内摄像头画面，此时 **车内摄像头** 会显示 **直播中**。关闭 **车内摄像头**，车内画面就不会出现在推流中。"
  - id: share
    title: "分享观看链接"
    body: |
      在 **详细信息** 中，推流那一行会显示 **直播中** 和时长，以及发送速率、已用数据和网络。使用 YouTube 登录时，下方的 **分享观看链接** 会分享您这场直播的 `youtu.be` 链接。
    screen: phone-live-view-go-live
    pins:
      - target: stop-live
        text: "正在直播的 **直播** 按钮，带计时器。"
      - target: streaming
        text: "**直播中** 及时长。"
      - target: share-watch-link
        text: "**分享观看链接**。"
  - id: stop
    title: "停车后停止推流"
    body: |
      再次点按 **直播** 即可停止。离开 Live View、点按通知中的 **停止**，或视频中断一分钟后，推流也会停止。切换应用或锁屏时，推流会继续。
check: "Live View 的 **直播** 按钮以直播配色显示正在计时，详细信息显示 **直播中**，您的直播在 YouTube 或您的服务器上播放。"
fixes:
  - q: "Live View 中没有“直播”"
    a: "直播尚未设置：详细信息会显示 **在‘设置’中设置直播后，即可从这里开始直播**。或者它在 **更多** 里，因为控件放不下。"
  - q: "“请在‘设置’›‘直播’中添加推流密钥”"
    a: "直播没有可推流的地方。请在 **设置 › 直播** 中使用 YouTube 登录，或添加推流密钥。"
  - q: "使用推流密钥时，YouTube 直播没有开始"
    a: "使用推流密钥时，请在 YouTube 工作室中手动开始每场直播，或在那里开启“自动开始”。使用 YouTube 登录时，直播会自动开始。"
  - q: "“此密钥含有空格”"
    a: "请从您的推流服务重新复制密钥并粘贴。"
  - q: "“没有声音：Browser View 正在无声运行”"
    a: "直播会共用 Browser View 的画面，而它没有声音。如需声音，请在开始直播前停止 Browser View。在没有声音的情况下开始的录制也是如此。"
  - q: "推流自行停止了"
    a: "每次 Live View 都会用一条消息说明原因。视频中断一分钟后，以及您离开 Live View 时，推流也会停止。"
related: [live-view, browser-view, live-copy]
blogPost: commaview-0-0-165-go-live-send-to-commaview
---

## 保留每次直播的副本

**设置 › 录像 › 保存每次直播** 会把每次直播按发送时的画质保存为“录像”中的一个 MP4。它会保留在您的手机上。请看[保留实时副本](/zh-cn/guides/live-copy)。

## 推流中包含什么、不包含什么

- **包含：** 道路及其上绘制的行车画面，以及 **车内摄像头** 开启时的车内摄像头画面。
- **不包含：** Live View 的控件、详细信息和消息。导航地图只有在“设置”提供并开启 **在推流中显示地图** 时才会出现，而且只有 CommaView 角落里的地图。
- 录制和直播互不影响：您可以同时录制和推流同一段行程。

## 安全

请在停车时设置并开始直播，之后就不要再操作。行驶中请勿操作 CommaView：按照 openpilot 的要求，眼睛看路，双手握住方向盘。观看的人都能看到您开到了哪里。
