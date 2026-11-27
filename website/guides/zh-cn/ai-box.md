---
title: "在 Android AI 盒子上运行 CommaView"
description: "用 Android AI 盒子把 Live View 放到车辆原厂的 CarPlay 或 Android Auto 屏幕上：插上盒子，安装 CommaView，接入 comma 的网络，完成配对并调整画面。"
topic: screens
order: 4
kind: walkthrough
lede: "如果您的车辆原厂配备**有线** CarPlay 或 Android Auto，**Android AI 盒子**可以把 CommaView 的 Live View 放到车辆自己的屏幕上，无需更换音响，也无需布线。这种盒子是一台小型 Android 电脑，插在您平时连接手机的 USB 接口上。CommaView 在盒子上运行，您的手机就可以空出来打电话和看地图。"
parked: true
updated: 2026-11-27
needs:
  - title: "有线 CarPlay 或 Android Auto"
    text: "原厂有线 CarPlay 或有线 Android Auto，且 USB 接口支持数据传输。请确认盒子支持您车辆的系统。"
  - title: "运行真正 Android 系统的盒子"
    text: "Android 8 或更高版本，并允许从文件安装应用。封闭式“视频”盒子和普通无线适配器无法运行 CommaView。[该买哪款盒子](/blog/android-ai-box-commaview)。"
  - title: "手机上的 CommaView"
    text: "先用手机设置好您的 comma，再配对盒子。[设置 CommaView](/zh-cn/guides/setup)。"
howItWorks:
  - title: "您的 comma"
    text: "通过本地网络把 Live View 发送到盒子。"
    edge: "Wi‑Fi"
  - title: "AI 盒子"
    text: "像任何 Android 设备一样运行 CommaView。"
    edge: "USB"
  - title: "车载屏幕"
    text: "像显示 CarPlay 一样显示盒子的画面。"
steps:
  - id: plug-in
    title: "插上盒子并安装 CommaView"
    body: |
      把盒子插到车辆的 CarPlay 或 Android Auto USB 接口，等它启动。暂时先把它连接到可以上网的 Wi‑Fi。

      在盒子的浏览器中，用收到邀请的电子邮箱登录 [my.commaview.com](https://my.commaview.com)，在 **Get the app** 下点按 **Download CommaView**。仅为这次安装允许从浏览器安装应用，装完后再关闭。打开 CommaView 并登录。
    note: "请在盒子的 Android 模式下运行 CommaView，而不是通过手机的 CarPlay 投屏。"
  - id: network
    title: "让盒子和 comma 连接同一个网络"
    body: |
      Live View 通过本地网络直接从 comma 传到盒子，不经过互联网，两者共同连接的任何网络都可以。
    tabs:
      - label: "盒子的热点"
        body: "带 SIM 卡的盒子通常可以共享热点。开启热点，然后在 comma 的 **设置 › 网络** 中让 comma 加入。"
      - label: "手机热点"
        body: "让盒子和 comma 都加入您的手机热点，它们也会通过热点上网。"
      - label: "comma 的热点"
        body: "开启 comma 的热点（openpilot 称之为网络共享），然后让盒子加入。"
    note: "大多数盒子也会用 Wi‑Fi 连接手机以实现无线 CarPlay，有些盒子在这时会断开 Wi‑Fi 的互联网连接。请关闭盒子上的任何 VPN。"
  - id: pair
    title: "将盒子与您的 comma 配对"
    body: |
      在手机上打开 comma 的 **设备设置**，点按 **配对其他手机**，然后在 **添加另一部手机** 下点按 **显示邀请码**。在盒子上点按 **配对已运行 CommaView 的 comma**，选择您的 comma，输入代码或点按 **扫描二维码**。每一步的说明：[在平板或车载屏幕上使用 CommaView](/zh-cn/guides/car-screens#step-pair)。
  - id: edges
    title: "让应用避开车辆裁掉的边缘"
    body: |
      有些车辆会裁掉盒子输出画面的边缘，而 Android 无从得知。打开 **设置 › 显示 › 屏幕边缘**。一条线标出应用的边界：用 **−** 和 **+** 把每条边往里移，直到整圈线都能看到，然后点按 **完成**。**重置** 会关闭此功能。

      然后检查首页、Live View 和设置是否都能完整显示。
    screen: settings-screen-edges
    pins:
      - target: done
        text: "**−** 和 **+** 把每条边往里移；**完成** 保存设置。"
      - text: "**主题** 也在 **设置 › 显示** 中：**与这台设备相同** 会跟随盒子的设置。"
  - id: auto
    title: "让它自行打开"
    body: |
      在 **设置 › 显示** 的 **打开 Live View** 下：

      - **此设备启动时打开 CommaView**：适用于随车辆一起重启的盒子。
      - **蓝牙连接时打开 CommaView**，并选择您的手机：适用于会进入休眠的盒子。
      - **连接时打开 Live View**：车辆通电后，comma 一连接就直接进入 Live View。

      请允许 **显示在其他应用的上层**，CommaView 才能自行打开。没有这项权限时，会改由通知提示您打开它。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**连接时打开 Live View**。"
  - id: check
    title: "确认 Live View 可以播放，然后再上路"
    body: |
      车辆通电后，在盒子上打开 Live View。它的控件位于驾驶员一侧的侧栏中，屏幕较矮时会变得紧凑。上路前，请确认画面能播放，且没有任何内容被裁掉。
    screen: ai-box-live-view
    pins:
      - target: record-button
        text: "**录制**，位于侧栏顶部。"
      - target: details
        text: "**详细信息**，位于侧栏较下方。"
    note: "盒子的画面是以视频形式传到车上的，所以 Live View 在途中会多编码一次。与拿在手里的手机相比，画面会稍软一点，也会稍有延迟。"
check: "车载屏幕先显示 CommaView 的首页，然后显示 Live View，推流状态标签显示 **实时**，**屏幕边缘** 的那条线整圈都能看到。"
fixes:
  - q: "盒子无法安装 CommaView"
    a: "有些盒子禁止从浏览器安装应用。请在电脑上下载应用，用 U 盘拷到盒子上，再从盒子的文件管理器打开。系统封闭、只能使用固定应用列表的盒子则完全无法安装。"
  - q: "盒子找不到 comma"
    a: "请确认两者在同一个网络中，并且盒子没有为了无线 CarPlay 而断开 Wi‑Fi。必要时请输入 comma 的 IP 地址：在 comma 自己的热点上是 192.168.43.1。更多内容见[在车上连接](/zh-cn/guides/connect-in-the-car)。"
  - q: "画面卡顿或无法播放"
    a: "comma 发送的道路摄像头视频是 1928 × 1208 的 HEVC（H.265），最便宜的盒子的解码器可能力不从心。如果某个解码器失败，CommaView 会自动尝试盒子上的其他解码器。全部都不行时，Live View 会显示 **无法播放这台 comma 的视频**：请从盒子发送支持报告。"
  - q: "“Live View 已在另一台设备上打开”"
    a: "您的 comma 一次只向一部手机或一台车机推流。在手机上的 CommaView 中回到首页，盒子上的 Live View 就会自行开始。"
  - q: "我还能用手机的 CarPlay 吗？"
    a: "可以。大多数盒子都能以无线方式转接手机的 CarPlay 或 Android Auto，您可以在它和盒子的 Android 之间切换。CommaView 在盒子的 Android 模式下运行。"
  - q: "盒子需要 SIM 卡吗？"
    a: "Live View 不需要。Beta 期间，CommaView 需要不时联网来续期访问通行证，家里的 Wi‑Fi、手机热点或盒子里的 SIM 卡都可以提供网络。"
related: [car-screens, browser-view, another-phone, connect-in-the-car]
blogPost: android-ai-box-commaview
---

## 四种“CarPlay 适配器”

商店里用同一个名字卖着四种完全不同的东西，只有一种能运行 CommaView。

| 类型 | 用途 | 能运行 CommaView 吗？ |
| --- | --- | --- |
| **Android AI 盒子** | 在车载屏幕上运行完整的 Android，可以像手机一样安装应用 | **能** |
| **封闭式“视频”盒子** | 在锁定的系统上运行几款内置的视频应用 | 不能 |
| **无线适配器** | 把有线 CarPlay 或 Android Auto 变成无线的，自身没有 Android | 不能 |
| **便携式 CarPlay 屏幕** | 给手机 CarPlay 用的独立屏幕，里面通常不是 Android | 不能 |

[最适合 CommaView 的 Android AI 盒子](/blog/android-ai-box-commaview) 比较了值得购买的盒子。Tesla 没有 CarPlay 或 Android Auto：请改用 [Browser View](/zh-cn/guides/browser-view)。

更新 comma 的运行环境时，请先更新盒子上的 CommaView，就像对每台观看您 comma 的设备一样。

## 安全

请在停车时设置好盒子，之后就不要再操作。行驶中请勿操作 CommaView：按照 openpilot 的要求，眼睛看路，双手握住方向盘。comma 自己的警报和车辆的仪表始终优先。CommaView 只显示 comma 看到的内容。
