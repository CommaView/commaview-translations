---
title: "不用家里的 Wi‑Fi，在车上连接"
description: "在车上让手机和 comma 连接同一个网络：手机热点、comma 的热点或车载屏幕的热点，以及 CommaView 连接不到 comma 时该怎么办。"
topic: start
order: 3
kind: walkthrough
lede: "Live View 通过本地网络直接从 comma 传到您的手机，不经过互联网。CommaView 不在乎是谁的网络：手机和 comma 只要在同一个网络中就行。在车上，通常是热点。"
parked: true
updated: 2026-11-27
needs:
  - title: "已设置好 CommaView"
    text: "您的 comma 已与这部手机配对。还没有？[设置 CommaView](/zh-cn/guides/setup)。"
  - title: "不使用 VPN"
    text: "使用 CommaView 时，请关闭手机或车载屏幕上的任何 VPN。"
howItWorks:
  - title: "您的 comma"
    text: "在它所在的网络中提供 Live View 和录像。"
    edge: "同一个热点"
  - title: "您的手机"
    text: "在该网络中自行找到 comma，即使它的地址变了。"
steps:
  - id: network
    title: "让手机和 comma 连接同一个网络"
    body: |
      选择适合您车辆的方式：随车辆启动而自动开启的那个通常最省事。让 comma 加入网络要在 comma 自己的屏幕上操作，位置是 **设置 › 网络**。
    tabs:
      - label: "手机热点"
        body: "开启手机热点，并让 comma 加入。同一部手机上的 CommaView 会通过它连接 comma，comma 也会通过它上网。"
      - label: "comma 的热点"
        body: "开启 comma 的热点（openpilot 称之为网络共享：在 comma four 上是 **设置 › 网络 › 启用 WiFi 热点**；在 comma 3X 上是 **设置 › 网络 › 高级 › 启用 WiFi 热点**），然后在手机的 Wi‑Fi 设置中加入。comma 的热点无法上网。"
      - label: "车载屏幕的热点"
        body: "如果 AI 盒子或车机可以共享热点（许多带 SIM 卡的设备都可以），请开启热点，让 comma 加入；如果您也用手机，也让手机加入。[车载屏幕](/zh-cn/guides/car-screens) 有更多说明。"
    note: "有些热点会把连接的设备彼此隔开。如果 CommaView 在某个热点上找不到 comma，请换一个试试。"
  - id: home
    title: "打开 CommaView"
    body: |
      comma 在新网络中响应后，首页会显示它 **已连接**：CommaView 会自行找到它，即使地址变了也一样。车辆熄火时 comma 会进入休眠，所以请先启动车辆。

      如果首页显示 comma 离线，并出现 **无法连接？**，请确认手机与 comma 连接同一个 Wi‑Fi，或连接它的热点，然后点按 **重新连接**。
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**重新连接** 会再次尝试连接 comma。"
      - target: cant-connect
        text: "**无法连接？** 会说明手机需要什么：与 comma 连接同一个 Wi‑Fi，或连接它的热点。"
  - id: address
    title: "如果还是找不到，请输入它的地址"
    body: |
      打开 comma 的 **设备设置**，然后点按 **名称与地址**，编辑它的 IP 地址。在 comma 自己的热点上，地址是 **192.168.43.1**（每台 comma 都一样）。在其他网络上，则是 comma 在 **设置 › 网络** 中显示的地址：comma four 上在 Wi‑Fi 按钮的网络名称下方，comma 3X 上在 **高级** 中。点按 **保存**。
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "comma 在此网络中的 IP 地址。"
      - target: save
        text: "**保存**。"
  - id: live-view
    title: "打开 Live View"
    body: |
      在首页点按 **打开 Live View**。如果手机与 comma 断开，Live View 会说明原因，并在 comma 响应后自行重新连接。**连接不到这台 comma** 表示手机不在 comma 的网络中：解决后点按 **重试**。
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**连接不到这台 comma**：Live View 停止的原因。"
      - target: retry
        text: "手机回到 comma 的网络后，点按 **重试**。"
check: "首页显示您的 comma **已连接**，Live View 播放道路画面，上面画着行驶路径。"
fixes:
  - q: "“连接不到这台 comma”"
    a: "手机必须与 comma 连接同一个 Wi‑Fi，或连接它的热点。请检查手机连接的是哪个网络（它可能自动连回了记住的 Wi‑Fi），关闭任何 VPN，然后点按 **重试**。"
  - q: "“Live View 已在另一台设备上打开”"
    a: "这台 comma 一次只向一部手机或一台车机推流。在另一台设备的 CommaView 中回到首页，这里的 Live View 就会自行开始。"
  - q: "“CommaView 没有响应”"
    a: "它可能正在 comma 上重启。恢复后 Live View 会重新连接。"
  - q: "CommaView 提示需要联网续期"
    a: "Beta 期间，CommaView 会不时续期访问通行证，而 comma 的热点不算联网。请让手机暂时使用移动数据或可以上网的 Wi‑Fi。"
  - q: "在一个热点上可以用，换一个就不行"
    a: "有些热点会把连接的设备彼此隔开，手机因此看不到 comma。请换用第 1 步中的其他网络。"
related: [comma-not-found, car-screens, browser-view, setup-troubleshooting]
---

## 搜索、配对和地址

有三件不同的事必须都正常，知道是哪一件出了问题，就知道该修什么：

- **找到 comma。** CommaView 会在手机所在的网络中寻找您的 comma，在新的位置找到同一台 comma 时会更新已保存的地址。有些网络会屏蔽这种搜索；输入地址（第 3 步）可以绕过它。
- **连接它。** 手机必须能在该网络中连接到 comma。笔记本电脑能通过 SSH 连接 comma，并不代表手机也能。
- **配对。** 连接上之后，手机会使用配对时获得的密钥。更换网络不会取消配对：无需重新配对。
