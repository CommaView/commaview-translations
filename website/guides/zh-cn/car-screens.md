---
title: "在平板或车载屏幕上使用 CommaView"
description: "在更大的屏幕上运行 CommaView 的 Live View：Android 车机、连接车辆原厂屏幕的 Android AI 盒子，或支架上的平板。安装、网络、配对和布局。"
topic: screens
order: 3
kind: walkthrough
lede: "comma 3X 和 comma four 的屏幕都很小。CommaView 可以把您 comma 的 Live View 显示在更大的屏幕上：Android 车机、连接车辆原厂屏幕的 Android AI 盒子，或支架上的手机或平板。车载屏幕会运行它自己的一份 CommaView，并与您的 comma 配对。"
parked: true
updated: 2026-11-27
needs:
  - title: "Android 8 或更高版本"
    text: "运行 Android 8 或更高版本、并允许安装应用的车机、AI 盒子、手机或平板。"
  - title: "您的邀请"
    text: "收到 CommaView 邀请的电子邮箱，用于登录 my.commaview.com 和应用。"
  - title: "手机上的 CommaView"
    text: "最简单的做法：先用手机设置好您的 comma，再配对车载屏幕。[设置 CommaView](/zh-cn/guides/setup)。"
howItWorks:
  - title: "您的 comma"
    text: "通过本地网络发送 Live View，不经过互联网。"
    edge: "热点或 Wi‑Fi"
  - title: "车载屏幕"
    text: "运行自己的 CommaView，并与您的 comma 配对。"
steps:
  - id: install
    title: "在车载屏幕上安装 CommaView"
    body: |
      在车机、AI 盒子、手机或平板上打开网页浏览器，用收到邀请的电子邮箱登录 [my.commaview.com](https://my.commaview.com)。在 **Get the app** 下点按 **Download CommaView**，打开下载的文件，并仅为这次安装允许从浏览器安装应用，装完后再关闭，与[设置指南](/zh-cn/guides/setup)中的做法相同。

      打开 CommaView 并登录。Beta 期间，它需要不时联网来续期访问通行证，所以请至少偶尔让它连上可以上网的 Wi‑Fi。
    note: "有些车机和盒子禁止从浏览器安装应用。请在电脑上下载应用，用 U 盘拷过去，再从设备的文件管理器打开。"
  - id: network
    title: "让它和 comma 连接同一个网络"
    body: |
      Live View 通过本地网络直接从 comma 传到车载屏幕。两者只需在同一个网络中，在车上通常是热点。请选择随车辆启动而自动开启的那个：通常最省事。
    tabs:
      - label: "车载屏幕的热点"
        body: "如果 AI 盒子或车机可以共享热点（许多带 SIM 卡的设备都可以），请开启热点，然后在 comma 的 **设置 › 网络** 中让 comma 加入。"
      - label: "手机热点"
        body: "让 comma 和车载屏幕都加入您的手机热点，它们也会通过热点上网。"
      - label: "comma 的热点"
        body: "开启 comma 的热点（openpilot 称之为网络共享：在 comma four 上是 **设置 › 网络 › 启用 WiFi 热点**；在 comma 3X 上是 **设置 › 网络 › 高级 › 启用 WiFi 热点**），然后让车载屏幕加入。"
      - label: "家里的 Wi‑Fi"
        body: "在家时，两者都连接您的 Wi‑Fi。设置时很方便，但开车离开后就断了。"
    note: "请关闭车载屏幕上的任何 VPN。有些热点会把连接的设备彼此隔开：如果车载屏幕在某个热点上找不到 comma，请换一个试试。更多内容见[在车上连接](/zh-cn/guides/connect-in-the-car)。"
  - id: pair
    title: "与您的 comma 配对"
    body: |
      如果您的 comma 已经通过手机运行 CommaView，请直接配对车载屏幕，无需重新设置。它会获得自己的密钥。
    tabs:
      - label: "在手机上"
        body: |
          打开 comma 的 **设备设置**，然后点按 **配对其他手机**。在 **添加另一部手机** 下点按 **显示邀请码**：一组可输入的代码或一个二维码，10 分钟内有效，只能使用一次。
        screen: device-pairing
        pins:
          - target: show-invitation
            text: "**显示邀请码**。"
          - target: this-phone
            text: "持有密钥的手机，当前这部标为 **这部手机**。车载屏幕也会加入其中。"
      - label: "在车载屏幕上"
        body: |
          在 **连接您的 comma** 页面点按 **配对已运行 CommaView 的 comma**（如果已添加过 comma，请改为打开 **添加 comma**）。选择您的 comma，然后点按 **输入它的配对码**，或点按 **扫描二维码**。如果列表中没有它，请点按 **输入地址和配对码**。在 **配对码或邀请码** 中输入邀请码，然后点按 **配对 comma**。
        screen: add-comma
        pins:
          - target: found-comma
            text: "在此网络中找到的您的 comma。"
          - target: scan-qr
            text: "**扫描二维码**。"
          - target: enter-address
            text: "列表中没有时，点按 **输入地址和配对码**。"
    note: "之后您的手机会显示 **有新手机获得了密钥**。点按 **这是我的**。每一步的说明：[添加另一部手机或平板](/zh-cn/guides/another-phone)。"
  - id: fit
    title: "让画面适合您的屏幕"
    body: |
      在宽屏上，CommaView 会以仪表板的形式排版，导航放在侧边的侧栏中。请把设备的文字大小保持在一眼就能看清的程度：CommaView 会按照在该文字大小下可用的空间来排版。

      Live View 的控件位于驾驶员一侧。设为 **自动** 时，CommaView 会跟随您的 comma 报告的驾驶侧；如需自行设定，请选择 **设置 › 显示 › 驾驶座位置**：**自动**、**左舵** 或 **右舵**。所有画面上的控件都会随之镜像。
    tabs:
      - label: "平板"
        body: "首页会并排显示车辆、您这一周、地图和您的行程，侧栏在侧边。"
        screen: tablet-home
        pins:
          - target: home-tab
            text: "侧栏：**首页**、**录像**、**设置**。"
          - target: open-live-view
            text: "**打开 Live View**。"
      - label: "车机"
        body: "同样的仪表板，尺寸适合中控屏。"
        screen: car-home
        pins:
          - target: home-tab
            text: "侧栏：**首页**、**录像**、**设置**。"
          - target: open-live-view
            text: "**打开 Live View**。"
      - label: "通过 AI 盒子"
        body: |
          有些车辆会裁掉 AI 盒子输出画面的边缘，而 Android 无从得知。打开 **设置 › 显示 › 屏幕边缘**，把每条边往里移，直到整圈线都能看到。然后检查首页、Live View 和设置是否都能完整显示。那里的 **主题** 可以跟随车载屏幕：**与这台设备相同**。
        screen: settings-screen-edges
        pins:
          - target: done
            text: "**−** 和 **+** 把每条边往里移；**完成** 保存设置。"
  - id: live-view
    title: "打开 Live View 并确认可以播放"
    body: |
      车辆通电后，点按 **打开 Live View**。它的控件位于道路画面旁、驾驶员一侧的侧栏中，屏幕较矮时会变得紧凑。
    tabs:
      - label: "平板"
        body: "**详细信息** 会在视频旁的窗格中打开。"
        screen: tablet-live-view
        pins:
          - target: details-pane
            text: "详细信息，在视频旁。"
          - target: record-button
            text: "**录制**。"
          - target: go-live-button
            text: "**直播**。"
      - label: "车机"
        body: "侧栏中有录制、行车画面切换、车内摄像头、详细信息和退出。"
        screen: car-live-view
        pins:
          - target: record-button
            text: "**录制**。"
          - target: onroad-screen-button
            text: "行车画面切换按钮。"
          - target: driver-cam-button
            text: "**车内摄像头**。"
          - target: details
            text: "**详细信息**，在车内摄像头下方。"
          - target: exit
            text: "**退出**。"
  - id: auto
    title: "让它自行打开"
    body: |
      在 **设置 › 显示** 的 **打开 Live View** 下：

      - **连接时打开 Live View**：车辆通电后，comma 一连接就自行打开 Live View。
      - **此设备启动时打开 CommaView**：适用于随车辆一起重启的车机。会进入休眠的车机可能有自己的开机自启应用列表。
      - **蓝牙连接时打开 CommaView**：在您选择的设备连接时打开，可以是您的车辆，在车机上也可以是您的手机。

      允许 **显示在其他应用的上层** 后，CommaView 就能自行打开；否则会改由通知提示您打开它。
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**连接时打开 Live View**。"
check: "车辆通电后，车载屏幕会打开 Live View，推流状态标签显示 **实时**，所有控件都在屏幕边缘以内。"
fixes:
  - q: "可以通过 CarPlay 或 Android Auto 使用 CommaView 吗？"
    a: "无法从手机使用。CommaView 不是 CarPlay 或 Android Auto 应用，而且这些平台不允许手机应用在车辆行驶时显示视频。Android AI 盒子可以绕过这个限制，因为它本身就是一台 Android 设备：CommaView 在盒子上运行，车辆显示盒子的画面。请看[在 Android AI 盒子上运行 CommaView](/zh-cn/guides/ai-box)。"
  - q: "能在车辆内置的 Android Automotive（Google built-in）上使用吗？"
    a: "暂时不能。搭载 Google built-in 的车辆只能从自己的 Play 商店安装应用，而那里没有 CommaView。如果您用其他方法试过，请告诉我们结果。"
  - q: "车载屏幕和手机可以同时用同一台 comma 吗？"
    a: "可以：分别把它们与 comma 配对。同一时间只有一台能打开 Live View，所以请先在另一台上离开 Live View。Live View 会显示 **Live View 已在另一台设备上打开**，等您在另一台上回到首页后，它就会自行开始。"
  - q: "车辆裁掉了画面的边缘"
    a: "有些车辆会裁掉 AI 盒子输出的画面，而 Android 无从得知。**设置 › 显示 › 屏幕边缘** 可以让应用避开您设定的每条边。"
  - q: "车载屏幕找不到 comma"
    a: "在同一个网络中，即使 comma 的地址变了，CommaView 也会自行找到它。如果找不到，请输入 comma 的 IP 地址：在 comma 自己的热点上是 192.168.43.1（每台 comma 都一样）；在其他网络上，则是 comma 在 **设置 › 网络** 中显示的 IP 地址：comma four 上在 Wi‑Fi 按钮的网络名称下方，comma 3X 上在 **高级** 中。"
  - q: "更新运行环境后，车载屏幕收不到视频了"
    a: "更新 comma 的运行环境时，请先更新每台观看它的设备上的 CommaView，车载屏幕也一样。使用旧版 CommaView 的车载屏幕，在 comma 的第一部手机获得密钥后还能继续使用 90 天；之后需要 CommaView 0.0.166 或更高版本以及一个邀请码。"
related: [ai-box, browser-view, another-phone, connect-in-the-car]
---

## 行驶中可以使用的设备

CommaView 是一款 Android 应用，所以您面前需要有一台 Android 设备。以下任何一种都能在行驶中运行它：

- **Android 车机。** 运行 Android 8 或更高版本的后装车机：CommaView 可以像在手机上一样安装，行驶中在车载屏幕上运行。
- **Android “AI 盒子”。** 一台小型 Android 电脑，插到车辆的有线 CarPlay 或 Android Auto 接口上，在那里显示自己的 Android 画面。CommaView 在盒子上运行，而不是在您的手机上。请看[在 Android AI 盒子上运行 CommaView](/zh-cn/guides/ai-box)。
- **支架上的手机或平板。** 任何 Android 手机或平板，装在不挡视线的仪表台或出风口支架上。这是最简单的方式，也是大多数人使用的方式。

配有网页浏览器的车辆（例如 Tesla）也可以改在浏览器中显示 Live View：请看[在车上的浏览器中显示 Live View](/zh-cn/guides/browser-view)。

## 不能使用的方式及原因

- **从手机使用 CarPlay 和 Android Auto。** CommaView 不是 CarPlay 或 Android Auto 应用。这些平台不允许手机应用在车辆行驶时显示视频。
- **CarPlay 和 Android Auto 中的停车视频。** Apple 和 Google 正在为部分车辆加入视频功能，但只能在停车时使用，所以无法在路上显示 Live View。
- **把手机投屏到车上。** 不支持通过 CarPlay 或 Android Auto 镜像手机屏幕的适配器。请改用能自行运行 CommaView 的 Android AI 盒子或车机。
- **Google built-in（Android Automotive）。** 这些车辆只能从自己的 Play 商店安装应用，而那里没有 CommaView。

## 已测试的硬件

CommaView 团队实际开车用过的车载屏幕。CommaView 应该能在任何 Android 8 或更高版本的设备上运行，但以下是我们检查过的：

| 设备 | 类型 | 我们检查了什么 |
| --- | --- | --- |
| **Doro 车机**（Qualcomm QCM6125，Android 13，1280 × 720） | 车机 | 城市道路行驶中的 Live View（2026 年 10 月）。 |
| **Dasaita 10.2″ 车机**（1280 × 720，装在 Toyota RAV4 上） | 车机 | 行驶中的 Live View；停车时的录像上传。 |

**帮我们测试。** 每块车载屏幕都不一样。如果您在车机或盒子上运行 CommaView，请[告诉我们效果如何](#告诉我们您的车载屏幕)，我们核实后会把它加到这里。

## 告诉我们您的车载屏幕

请直接从车载屏幕发送给我们，这样报告会带上它的型号和屏幕尺寸：

1. 在车机或盒子上的 CommaView 中，打开 **设置 › 支持与诊断**，点按 **反馈问题或提出建议**。
2. 选择 **想法**，然后开启 **这台设备的诊断数据**（选择“想法”时默认不附带）：它会告诉我们设备的品牌、型号和屏幕尺寸。
3. 在备注中写下您的车型、车机或盒子（品牌和型号）、连接方式（谁的热点，或 Wi‑Fi），以及哪些正常、哪些不正常。然后点按 **发送**。

您发送的内容和我们的回复都可以在 [my.commaview.com](https://my.commaview.com/feedback) 的 Your feedback 中找到。还没加入 Beta，或者应用无法启动？请在 [CommaView Discord](https://discord.gg/UuMhz9K8ft) 告诉我们。

## 安全

- 请在停车时完成安装、配对和布局设置。上路前确认 Live View 可以播放。
- 行驶中请勿操作 CommaView。按照 openpilot 的要求，眼睛看路，双手握住方向盘。
- comma 自己的警报和车辆的仪表始终优先。CommaView 只显示 comma 看到的内容。
- 把手机或平板装在不挡视线、不挡安全气囊的位置，并遵守当地关于车内屏幕的规定。
