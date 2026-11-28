---
title: "添加另一部手机或平板"
description: "用 10 分钟有效的邀请码，让另一部手机、平板或车载屏幕获得自己的 comma 密钥，并查看和移除持有密钥的手机。"
topic: start
order: 4
kind: walkthrough
lede: "每部观看您 comma 的手机都有自己的密钥。要添加另一部手机、平板或车载屏幕，请在已连接这台 comma 的手机上显示邀请码，再在新设备上输入或扫描。无需 SSH，也无需重新设置。"
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "一部持有密钥的手机"
    text: "一部已与您的 comma 配对的手机，使用 CommaView 0.0.166 或更高版本及其运行环境。还没有？[设置 CommaView](/zh-cn/guides/setup)。"
  - title: "新设备上的 CommaView"
    text: "已安装并登录，版本为 0.0.166 或更高。[获取应用](/zh-cn/guides/setup#step-get-the-app)。"
  - title: "同一个网络"
    text: "两者都与 comma 连接同一个 Wi‑Fi，或都连接 comma 的热点。"
howItWorks:
  - title: "您的手机"
    text: "向 comma 请求邀请码：一组代码或一个二维码，10 分钟内有效。"
  - title: "新手机"
    text: "用邀请码加入，并获得自己的密钥。"
    edge: "本地网络"
  - title: "您的 comma"
    text: "通知每部持有密钥的手机：有新手机获得了密钥。"
steps:
  - id: device-settings
    title: "在手机上打开“配对其他手机”"
    body: |
      在已连接您 comma 的手机上，从首页打开 comma 的 **设备设置**，然后点按 **配对其他手机**。
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**配对其他手机**：生成一组短时有效的代码，让另一部手机或平板可以连接。"
  - id: show-invitation
    title: "显示邀请码"
    body: |
      在 **持有密钥的手机** 下，**添加另一部手机** 会为还没有这台 comma 的手机显示邀请码。点按 **显示邀请码**。
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**显示邀请码**。"
      - text: "持有这台 comma 密钥的手机，当前这部排在最前。"
  - id: invitation
    title: "让邀请码保持显示"
    body: |
      **添加另一部手机** 会显示分成三组的代码、一个二维码和 comma 的 IP 地址。它在 10 分钟内有效，且只能使用一次。过期后，请再显示一个新的。
    screen: invitation-dialog
    pins:
      - target: code
        text: "要在新手机上输入的代码。"
      - target: qr
        text: "或者扫描这个二维码。"
      - text: "**… 后过期**：从显示时起算 10 分钟。"
  - id: add-comma
    title: "在新手机上添加 comma"
    body: |
      在新手机的 **连接您的 comma** 页面点按 **配对已运行 CommaView 的 comma**。如果新手机上已经有 comma，请改为在首页点按 **添加 comma**。

      您的 comma 会显示在 **在此网络中** 下。点按它，或点按 **扫描二维码** 扫描邀请码。如果列表中没有它，请点按 **输入地址和配对码**。
    screen: add-comma
    pins:
      - target: found-comma
        text: "在此网络中找到的您的 comma。"
      - target: scan-qr
        text: "**扫描二维码** 来扫描邀请码。"
      - target: enter-address
        text: "列表中没有时，点按 **输入地址和配对码**。"
  - id: pair
    title: "输入邀请码并配对"
    body: |
      检查 **comma IP**，在 **配对码或邀请码** 中输入邀请码（或点按二维码按钮扫描），然后点按 **配对 comma**。新手机会获得自己的密钥，并在首页显示您的 comma。
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**comma IP**，找到的 comma 会自动填入。"
      - target: pair-code
        text: "**配对码或邀请码**。"
      - target: scan-qr
        text: "**扫描配对二维码**。"
      - target: pair
        text: "**配对 comma**。"
  - id: new-key
    title: "在其他手机上确认"
    body: |
      每部持有密钥的手机都会收到通知：**有新手机获得了密钥**，并附上它的名称和时间。点按 **这是我的**。如果不是您的设备，请点按 **移除**；**查看手机** 会打开 **配对其他手机**，其中列出了每部持有密钥的手机。
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "**这是我的**：适用于您自己的手机或平板。"
      - target: review
        text: "**查看手机** 会列出每部持有密钥的手机。"
check: "新手机在首页显示您的 comma，并能打开 Live View。在第一部手机上，**配对其他手机** 会在 **持有密钥的手机** 下列出它。"
fixes:
  - q: "“无法使用该邀请码加入”"
    a: "它可能输入有误、已过期或已被使用。请在已有这台 comma 的手机上显示一个新的邀请码（在它的设备设置中依次点按 **配对其他手机**、**添加另一部手机**）。"
  - q: "“这台 comma 的运行环境早于手机密钥功能”"
    a: "请先更新 comma 的运行环境：[更新 comma 的运行环境](/zh-cn/guides/update-runtime)。然后再显示邀请码。"
  - q: "“连接不到这台 comma”"
    a: "两部手机都必须与 comma 连接同一个 Wi‑Fi，或连接它的热点。[在车上连接](/zh-cn/guides/connect-in-the-car)。"
  - q: "“配对失败：这台 comma 已不再通过配对码配对”"
    a: "comma 已停止接受旧的共享令牌。请从已持有密钥的手机添加这部手机（在它的设置中点按 **添加另一部手机**），或重新为这台 comma 运行设置。"
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## 移除手机

在持有密钥的手机上，打开 comma 的 **设备设置**，然后点按 **配对其他手机**。在列表中某部手机旁点按 **移除**。之后它就无法再连接这台 comma，直到再次通过邀请码或重新设置 comma 把它添加回来。

## 使用旧版 CommaView 的手机

0.0.166 之前，每部手机都向 comma 发送同一个共享令牌。升级到 0.0.166 的手机会在下次连接时获得自己的密钥，无需重新配对。

- **配对其他手机** 中的 **旧版 CommaView 应用** 会显示，使用旧版 CommaView 的手机还能用共享令牌使用这台 comma 多少天：从第一部手机获得密钥起算 90 天。在此之前，**用于旧版应用的配对码** 可以配对使用旧版 CommaView 的手机。
- 当每部使用共享令牌的手机都有了密钥后，**立即停止** 会让 comma 不再接受共享令牌。届时，使用旧版 CommaView 的手机将无法再使用这台 comma，在更新之前也无法再次配对。
- 此后，没有密钥的手机需要 CommaView 0.0.166 或更高版本以及一个邀请码。

更新 comma 的运行环境时，请先更新每台观看它的设备上的 CommaView，车载屏幕也一样。
