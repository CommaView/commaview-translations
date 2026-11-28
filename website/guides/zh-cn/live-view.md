---
title: "在 Live View 中观看您的 comma"
description: "打开 Live View，在手机上查看 comma 的道路摄像头画面和行车画面，了解它的控件、详细信息，以及出现问题时它会显示什么。"
topic: screens
order: 1
kind: walkthrough
lede: "**Live View** 会实时显示您 comma 的道路摄像头画面，并在上面绘制行车画面：comma four 的、comma 3X 的，或 CommaView 自己的。画面通过您自己的网络直接从 comma 传来，不经过互联网。"
parked: true
updated: 2026-11-27
needs:
  - title: "已设置好 CommaView"
    text: "Android 手机上的 CommaView 已与您的 comma 配对。还没有？[设置 CommaView](/zh-cn/guides/setup)。"
  - title: "车辆已通电"
    text: "openpilot 只在行驶状态下发送视频。车辆熄火时，Live View 会等待，车辆启动后自行开始。"
  - title: "同一个网络"
    text: "您的手机和 comma 连接同一个 Wi‑Fi 或热点。在车上，请看[在车上连接](/zh-cn/guides/connect-in-the-car)。"
steps:
  - id: open
    title: "从首页打开 Live View"
    body: |
      在 **首页** 上，当您的 comma 已连接且车辆已通电时，点按 **打开 Live View**。几秒钟内就会出现道路画面，推流状态标签显示 **实时**。
    screen: phone-home
    pins:
      - target: open-live-view
        text: "**打开 Live View**，首页的主按钮。"
    note: "车辆熄火时，Live View 会显示 **您的 comma 已在线，但目前没有行驶**。车辆启动后它会自行开始，也可以点按 **刷新** 立即开始。"
  - id: controls
    title: "认识画面下方的控件"
    body: |
      竖着拿手机时，控件位于视频下方：

      - **录制** 会保存这一段行程。请看[录制行程](/zh-cn/guides/record)。
      - **保存** 会保留行程中刚过去的 3 分钟和接下来的 1 分钟。
      - 行车画面切换按钮以当前显示的画面命名（**CommaView**、**comma 4**、**comma 3X**），每点按一次就切换到下一个。请看[选择行车画面](/zh-cn/guides/overlays)。
      - **直播** 会推流 Live View 显示的内容，需要先完成设置。请看[直播](/zh-cn/guides/go-live)。
      - **车内摄像头** 会在画面一角显示车内摄像头画面。
      - **详细信息** 会打开 Live View 的各项信息和卡片。

      在您手机的宽度和文字大小下放不下的控件会收进 **更多**。不会缩小或裁掉任何内容。
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**录制**。"
      - target: onroad-screen-button
        text: "行车画面切换按钮。"
      - target: driver-cam-button
        text: "**车内摄像头**。"
      - target: go-live-button
        text: "**直播**，设置好直播后显示。"
      - text: "**更多** 里是放不下的控件。"
    note: "录制进行时，行车画面切换按钮和 **车内摄像头** 会变暗：请在点按 **录制** 之前选好。"
  - id: details
    title: "打开详细信息"
    body: |
      点按 **详细信息**，或向上拉起屏幕底部的面板。它会显示推流状况、视频、运行环境、comma 的软件和地址、是否正在录制或推流，以及 **Browser View** 卡片。其中的链接可以打开 **录像** 和 comma 的 **设备设置**。
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**详细信息** 面板。"
      - text: "摘要：推流状态、视频和运行环境。"
      - target: recordings-link
        text: "**录像**。"
      - target: device-settings-link
        text: "这台 comma 的 **设备设置**。"
  - id: turn
    title: "把手机横过来，或使用更大的屏幕"
    body: |
      把手机横过来，视频就会占满屏幕，控件位于驾驶员一侧的侧栏中。**详细信息** 会在画面旁打开，**退出** 会离开 Live View。
    tabs:
      - label: "横向手机"
        body: "侧栏中是同样的控件。屏幕较矮时会变得紧凑。"
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "**录制**，位于侧栏顶部。"
          - target: more
            text: "**更多** 里有 **车内摄像头** 和 **详细信息**。"
          - target: exit
            text: "**退出** 会离开 Live View。"
      - label: "平板或车载屏幕"
        body: "在宽屏上，侧栏保持在驾驶员一侧。请看[在车载屏幕上使用 CommaView](/zh-cn/guides/car-screens)。"
        screen: car-live-view
        pins:
          - target: record-button
            text: "**录制**。"
          - target: onroad-screen-button
            text: "行车画面切换按钮。"
          - target: driver-cam-button
            text: "**车内摄像头**。"
          - target: details
            text: "**详细信息**。"
          - target: exit
            text: "**退出**。"
  - id: auto
    title: "让 Live View 自行打开"
    body: |
      如果某部手机或车机只用来显示 Live View，请打开 **设置 › 显示**，在 **打开 Live View** 下开启 **连接时打开 Live View**。这样，车辆通电后 comma 一连接，Live View 就会自行打开。手动离开后，它会保持关闭，直到下一次。

      紧接在下方的 **保留状态栏** 会在 Live View 上方显示系统时钟，而不是占满整个屏幕。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**连接时打开 Live View**。"
  - id: leave
    title: "用完后离开 Live View"
    body: |
      停车后点按 **退出** 或返回。离开 Live View 也会结束直播、Browser View 和实时副本。同一时间只有一部手机或一台车机能打开 Live View，所以请先在一台上离开，再在另一台上打开。
check: "推流状态标签显示 **实时**，道路画面在动，详细信息中的推流状态显示 **良好**。"
fixes:
  - q: "“您的 comma 已在线，但目前没有行驶”"
    a: "车辆已熄火，或 openpilot 尚未启动。车辆启动后 30 秒内 Live View 会自行恢复，也可以点按 **刷新**。"
  - q: "“连接不到这台 comma”"
    a: "您的手机必须与 comma 连接同一个 Wi‑Fi，或连接它的热点。comma 响应后 Live View 会重新连接，也可以点按 **重试**。还是不行？请看 [CommaView 找不到您的 comma](/zh-cn/guides/comma-not-found)。"
  - q: "“Live View 已在另一台设备上打开”"
    a: "您的 comma 一次只向一部手机或一台车机推流。在另一台设备的 CommaView 中回到首页，这里的 Live View 就会自行开始。"
  - q: "“收不到车辆数据”"
    a: "视频能收到，但车速、信号和警报收不到。重启 comma 即可解决。"
  - q: "“视频延迟”"
    a: "已有一秒没有收到新的画面帧。Live View 会在画面旁提示，如果视频没有恢复，它会自行重新连接。"
  - q: "“无法播放这台 comma 的视频”"
    a: "手机的视频解码器都无法播放它。CommaView 会继续尝试。请从“设置”发送支持报告，以便 CommaView 调查：请看[发送支持报告](/zh-cn/guides/support-bundle)。"
related: [overlays, record, browser-view, car-screens]
---

## 安全

请在停车时打开 Live View，之后就不要再操作。行驶中请勿操作 CommaView：按照 openpilot 的要求，眼睛看路，双手握住方向盘。comma 自己的警报和车辆的仪表始终优先。CommaView 只显示 comma 看到的内容。
