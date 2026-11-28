---
title: "在车上的浏览器中显示 Live View"
description: "Browser View 在车辆自带的网页浏览器（包括 Tesla 的）中显示 CommaView 的 Live View，由您的手机通过热点提供。车上无需安装任何东西。"
topic: screens
order: 2
kind: walkthrough
lede: "**Browser View** 会在车辆自带的网页浏览器中显示 Live View 的画面。由您的手机通过热点或 Wi‑Fi 提供给车辆，所以车上无需安装任何东西。它是为 Tesla 这类有浏览器、却没有 CarPlay 或 Android Auto 的车辆设计的，任何能连接到您手机的浏览器都可以使用。"
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View 可以正常使用"
    text: "Android 手机上的 CommaView 已与您的 comma 配对。还没有？[设置 CommaView](/zh-cn/guides/setup)。"
  - title: "车上有浏览器"
    text: "Tesla、其他带网页浏览器的车辆，或车上的平板、笔记本电脑。"
  - title: "同一个网络"
    text: "车辆和 comma 都连接您的手机热点，或三者共同连接的任何网络。"
howItWorks:
  - title: "您的 comma"
    text: "像平时一样把 Live View 发送到您的手机。"
  - title: "您的手机"
    text: "以网页形式提供画面，需要一组八位数代码才能访问。"
    edge: "热点"
  - title: "车上的浏览器"
    text: "打开网页：每秒 20 帧，720p 或 1080p，最多四个浏览器。"
steps:
  - id: hotspot
    title: "让车辆连接您的手机热点"
    body: |
      开启手机热点，然后在车辆的 Wi‑Fi 设置中连接它。请确认车辆连接的是您的手机，而不是它已经记住的其他 Wi‑Fi。如果 comma 还没有连接这个热点，也请让它连接：您的手机仍然需要像平时一样连接 comma。
    note: "**在 Tesla 上**，请先关闭手机的 Wi‑Fi，让热点共享移动数据。"
  - id: start
    title: "从 Live View 的“详细信息”中开始 Browser View"
    body: |
      在手机上打开 **Live View**，然后点按 **详细信息**。靠近底部的 **Browser View** 卡片会说明它的作用以及它会告诉 CommaView 什么。点按 **开始**。
    screen: live-view-browser-view
    clip: browser-view-start
    pins:
      - target: browser-view-card
        text: "**Browser View** 卡片，靠近 **详细信息** 的底部。"
      - target: start-button
        text: "**开始**。第一次使用时，请给手机几秒钟获取证书。"
      - target: privacy-policy
        text: "Browser View 运行时会告诉 CommaView 什么，以及 **隐私政策**。"
  - id: vpn
    title: "在 Tesla 上开启 VPN 地址"
    tabs:
      - label: "Tesla"
        body: |
          Tesla 的浏览器无法打开热点分配的地址。在卡片上点按 **开启 VPN 地址**，并在 Android 询问是否允许 CommaView 设置 VPN 时允许。您的手机会获得一个 Tesla 能打开的地址：`169.254.99.1`。它不传输任何流量，开启期间其他 VPN 应用都会关闭。
        screen: live-view-browser-view-vpn
        pins:
          - target: short-link
            text: "短链接，Tesla 也能用：**在车上的浏览器（包括 Tesla 的）中打开**。"
          - target: vpn-address
            text: "手机在 VPN 地址上的地址：`169.254.99.1`。"
        note: "Android 关于 VPN 的询问没有配图：那是 Android 自己的界面，每部手机看起来都不一样。"
      - label: "其他车辆"
        body: |
          这一步无需操作：其他车辆的浏览器可以打开热点的地址。请直接进行下一步。
  - id: open
    title: "在车上的浏览器中输入短链接"
    body: |
      卡片会显示一个带有您八位数代码的短链接，例如 `commaview.app/48291374`。在车上的浏览器中输入它，然后点按 **打开**。只要车辆联网且 CommaView 已登录，网页就会找到您的手机，并通过安全连接打开 Live View：显示锁形图标、没有警告，画面也最流畅。
    screen: live-view-browser-view-on
    pins:
      - target: short-link
        text: "要在车上输入的短链接，包含您的代码。"
      - target: show-addresses
        text: "**车上没有网络？显示地址**：手机自己的地址。"
      - target: quality
        text: "**Browser View 画质**：720p 或 1080p。"
      - target: stop-button
        text: "**停止** 会结束 Browser View。"
    warn: "**车上没有网络？** 短链接需要联网。请改用手机自己的地址：见[车上没有网络](#车上没有网络)。"
  - id: bookmark
    title: "把网页加入书签"
    body: |
      网页的地址保持不变，所以下次车辆联网时，直接打开书签即可，不必再输入短链接。
check: "手机上的卡片会显示谁在观看，以及车上的浏览器在绘制什么，例如 **1 个浏览器正在观看** 和 `Tesla 2025.20.6 · H.264 over HTTPS via the VPN name · 20 fps`。"
fixes:
  - q: "显示“正在等待车上的浏览器”，但什么都打不开"
    a: "请确认车辆连接的是您的手机热点，而不是其他 Wi‑Fi。在 Tesla 上，请开启 VPN 地址（[第 3 步](#step-vpn)）。"
  - q: "“开启这部手机的热点”"
    a: "手机既没有连接 Wi‑Fi，也没有开启可与车辆共享的热点。两者中任一项开启后，5 秒内就会显示地址。"
  - q: "短链接显示 VPN 地址已关闭"
    a: "在卡片上开启它，然后重新加载网页。"
  - q: "出现无法跳过的警告"
    a: "请在车辆联网时使用短链接，或使用基本画质（[车上没有网络](#车上没有网络)）。"
  - q: "挂入 D 挡后画面停止"
    a: "行驶中车上的浏览器是否继续绘制画面，取决于汽车制造商。卡片上的报告行会显示车辆绘制的内容（“0 fps · hidden”表示车辆停止了画面）。请告诉我们您的车型及其软件版本：行驶前开启 **在这部手机上保存诊断数据**，之后从“设置”发送 **反馈问题或提出建议**。"
related: [car-screens, ai-box, go-live]
blogPost: commaview-0-0-166-languages-browser-view
---

## 车上没有网络

短链接需要车辆联网才能加载网页，可以通过热点的移动数据，也可以通过车辆自己的网络连接。没有网络时，请直接打开手机的地址。在卡片上点按 **车上没有网络？显示地址**：

- **最佳画质**：一个 HTTPS 地址，例如 `https://192.168.43.1:8443/48291374`。浏览器会先显示警告，因为这个地址的证书是手机自己签发的：接受警告即可继续。Tesla 的浏览器无法跳过此警告。
- **基本画质**：同一地址的 HTTP 版本，例如 `192.168.43.1:8090/48291374`。任何浏览器（包括 Tesla 的）都不会显示警告，但画质较低，也没那么流畅。

开启 VPN 地址后，卡片会改为显示它的地址：`https://169.254.99.1:8443/<code>` 和 `169.254.99.1:8090/<code>`。在没有网络的 Tesla 上，请使用基本画质的地址。

您手机热点的地址可能与示例不同；卡片上显示的始终是正确的地址，每个旁边都有复制按钮。

## 卡片上的选项

- **Browser View 画质：720p 或 1080p。** 1080p 更清晰，但会占用更多手机和热点资源。在您选择之前为 720p。
- **随 Live View 开始。** 每次打开 Live View 时都会启动 Browser View，如果开启了 VPN 地址，也会一并使用。手动停止后，它会保持停止，直到 Live View 再次打开。
- **新代码。** 生成新的八位数代码，让别人看到过的地址失效。请在车上打开新地址。
- **车上的控件。** 录制、保存片段以及 Live View 的其他控件会显示在画面下方或驾驶员一侧，绝不会盖住画面。卡片上的 **车上的控件** 可以关闭它们。
- **车内摄像头画面**：当 Live View 的 **车内摄像头** 开启时，车上也会显示。

## 运行期间

- **手机锁屏后 Browser View 仍会继续运行**，切换到其他应用时也一样。它的通知会显示“正在 Browser View 中显示 Live View”，通知中的 **停止** 可结束它。
- **离开 Live View 就会结束它**，就像会结束直播和实时副本一样。
- **在 Browser View 运行时直播** 会共用它的画面。如果在 Browser View 单独运行时开始直播，推流将没有声音：如需声音，请先停止 Browser View。

## 隐私与安全

- 画面只会发送到连接您手机热点或 Wi‑Fi、并且持有代码的浏览器。绝不经过移动数据，也绝不经过 CommaView 的服务器。
- 同一台设备在一分钟内输错十次代码，就会被拒绝访问一分钟，已在观看的设备不受影响。
- Browser View 运行期间，您的手机会把它的代码、端口、VPN 地址是否开启，以及热点或 Wi‑Fi 的私有地址发送给 CommaView 的账号服务，好让短链接找到您的手机。持有代码的人都能看到这些信息以及您手机的 `commaview.app` 名称，时间为 Browser View 运行期间，以及意外停止后最多 2 小时；没有您手机的热点或 Wi‑Fi，这些信息打不开任何东西。它们会在 Browser View 最后一次运行 30 天后删除。您手机的 `commaview.app` 名称及其最新证书的日期会一直保留，直到您的账号删除。证书是公开的，因此这个名称会保留在证书透明度（Certificate Transparency）日志中；它不会透露任何关于您、您的车辆或 comma 的信息。详情请见[隐私政策](/privacy)。
- VPN 地址由您决定是否开启，绝不会自行开启，也不传输任何流量。

## 常见问题

**我需要 AI 盒子或新车机吗？** 不需要。Browser View 使用车上已有的浏览器。如果您的车辆配备的是 CarPlay 或 Android Auto，[Android AI 盒子](/blog/android-ai-box-commaview)可以直接在车载屏幕上运行 CommaView。

**会用到我的移动数据吗？** 画面不会：它通过热点从手机传到车上。短链接的网页以及车辆自己使用热点时会用到。

**可以用 comma 的热点代替手机的吗？** 对大多数浏览器来说可以：让手机和车辆都连接 comma 的热点，然后打开卡片上显示的地址。Tesla 需要使用 VPN 地址，而它只适用于连接手机自己热点的车辆。

## 安全

请在停车时设置好 Browser View，之后就不要再操作。行驶中请勿操作 CommaView：按照 openpilot 的要求，眼睛看路，双手握住方向盘。comma 自己的警报和车辆的仪表始终优先。CommaView 只显示 comma 看到的内容。
