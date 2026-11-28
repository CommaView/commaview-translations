---
title: "使用您自己的 Stadia Maps 密钥导航"
description: "添加您的 Stadia Maps 密钥，在首页搜索地点，选择路线，然后在 Live View 中跟随转向卡片和语音提示前进。也可以把地点发送到您的 comma。"
topic: navigation
order: 1
kind: walkthrough
lede: "**导航** 会在 Live View 中引导您前往某个地点。在首页用 **要去哪里？** 搜索地点，选择路线，点按 **开始**，然后跟随转向卡片和语音提示。路线由 Stadia Maps 根据您自己的密钥提供，密钥加密保存在您的手机上。导航仅供显示，绝不会控制车辆。"
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "已登录"
    text: "CommaView 0.0.167 或更高版本，并用您的 Beta 账号登录。未登录时不提供导航。"
  - title: "一把 Stadia Maps 密钥"
    text: "来自您自己的 Stadia Maps 账号的 API 密钥。路线请求在您的账号及其条款下进行。"
  - title: "开启车辆位置"
    text: "导航跟随您 comma 的 GPS。请在首页为您的 comma 开启 **车辆位置**。"
  - title: "手机能上网"
    text: "用于搜索和获取路线。comma 的 Wi‑Fi 无法上网时，它们会使用移动数据。"
howItWorks:
  - title: "要去哪里？"
    text: "根据 OpenStreetMap 的数据（Photon）查找 comma 附近的地点。"
    edge: "您的密钥"
  - title: "Stadia Maps"
    text: "规划路线，由您的手机用您的密钥发出请求。不经过 CommaView。"
  - title: "Live View"
    text: "根据 comma 的位置引导您：转向卡片、地图和语音提示。"
steps:
  - id: open
    title: "打开地图与导航"
    body: |
      点按 **设置**，然后点按 **地图与导航**。登录后，它就在原来“离线地图”所在的那一行。
    screen: support-settings
    pins:
      - target: maps-row
        text: "**地图与导航**。"
  - id: get-key
    title: "从 Stadia Maps 获取密钥"
    body: |
      在 **您的 Stadia Maps 密钥** 下，**API 密钥** 显示 **尚未添加**。点按 **从 Stadia Maps 获取密钥**：它会在浏览器中打开 Stadia 的注册页面。注册后，从您的 Stadia Maps 控制台复制 API 密钥。
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**您的 Stadia Maps 密钥**：“路线需要你自己的 Stadia Maps 密钥…”"
      - target: get-key
        text: "**从 Stadia Maps 获取密钥** 会打开 Stadia 的注册页面。"
      - target: add-key
        text: "复制好密钥后，点按 **添加**。"
    note: "Stadia 的网站没有配图：那是他们的网站。它的控制台会显示您密钥的用量、套餐和限额。"
  - id: add-key
    title: "粘贴密钥，然后检查并保存"
    body: |
      回到 CommaView，点按 **添加**。点按 **粘贴** 把密钥填入字段，然后点按 **检查并保存**。CommaView 会向 Stadia Maps 请求一条两个固定地点之间的短路线来检查密钥，不涉及您的任何信息：**正在向 Stadia Maps 检查…**。密钥被接受后，**API 密钥** 会以遮盖形式显示，例如 **•••• e1f0**。
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "**您的 Stadia Maps API 密钥**，已遮盖。"
      - target: paste
        text: "从剪贴板 **粘贴**。"
      - target: check-and-save
        text: "**检查并保存**。"
    note: "“仅加密保存在这部手机上。保存前会向 Stadia Maps 查询一条短路线来检查。”它绝不会出现在支持数据包或崩溃报告中。"
  - id: where-to
    title: "在首页点按“要去哪里？”"
    body: |
      停车时，点按首页上 comma 卡片下方的 **要去哪里？**。输入地点或地址，或点按麦克风说出来。保存过之后，**家** 和 **公司** 在卡片上一点即达。
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**要去哪里？** 会打开搜索。"
      - target: voice
        text: "**用语音说要去哪里**。"
      - target: home-chip
        text: "**家**，保存后显示。"
  - id: pick
    title: "选择地点"
    body: |
      结果按离您 comma 的远近排列，每个都显示地址和距离，之后是您已保存和最近的地点。点按您要去的那个。
    screen: navigation-search
    pins:
      - target: search-field
        text: "**搜索地点或地址**。"
      - target: first-result
        text: "一个结果，显示地址以及与您 comma 的距离。"
    note: "车辆行驶时无法输入文字：“车辆行驶中无法输入文字。请使用语音或已保存的地点。”"
  - id: start
    title: "选择路线并点按“开始”"
    body: |
      路线预览会在地图上显示路线、时间、距离和预计到达时间。每条路线都有一个标签：**最快**、**路线 2** 等。点按 **开始**：导航开始，并打开 Live View。

      **保存为家** 和 **保存为公司** 会保存这个地点，之后在首页一点即达。
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "路线：**最快**、**路线 2**…"
      - target: start
        text: "**开始**。"
      - target: save-home
        text: "**保存为家**，旁边是 **保存为公司**。"
  - id: follow
    title: "在 Live View 中跟随导航"
    body: |
      转向卡片会显示下一个转弯：箭头、距离、指示和再下一步，以及您的预计到达时间。每个转弯前约 20 秒会有一次语音提示，快到时再提示一次，到达时也会提示。在 CommaView 自己的行车画面中，您所在的车道以及转弯的出口处会画上箭头标记。

      错过转弯后，几秒内就会有新路线。到达并熄火后，行程会自行结束。
    tabs:
      - label: "手机"
        body: |
          竖着拿时，转向卡片和地图位于视频下方。
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "转向卡片。"
          - target: end
            text: "**结束导航**。"
          - target: mute
            text: "**导航语音静音**。"
          - target: map-button
            text: "**地图** 会在本次行程中隐藏地图，再点一次就会恢复。"
      - label: "车载屏幕"
        body: |
          在车机上，如果视频旁有空间，地图和转向卡片会放在单独的窗格中。没有空间时，CommaView 的画面会把地图融入视频的角落。拖动分隔线可以调整窗格的宽度。
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "转向卡片。"
          - target: divider
            text: "分隔线，用来调整地图的宽度。"
          - target: map-button
            text: "**地图**。"
    warn: "请在停车时设置好行程。行驶中请勿操作 CommaView：转向卡片和语音就是为了让您不必操作，而且 openpilot 和车辆自己的警报始终优先。"
  - id: send
    title: "如果分支版本支持，把地点发送到您的 comma"
    body: |
      对于自身导航可以接收目的地的分支版本，路线预览中 **开始** 下方会有 **发送到 comma**：StarPilot、carrotpilot，以及 openpilot 的导航（alpha），还有基于它的 sunnypilot 导航。其他分支版本不会显示。

      点按它。CommaView 会先询问，并根据分支版本当前的设置说明它会对驾驶产生什么影响，例如在转弯前减速。点按 **发送**：“已发送到 comma。StarPilot 会在那里规划自己的路线。”分支版本会用自己的服务规划路线，所以路线可能与 CommaView 的不同。**从 comma 清除** 会把它撤下，结束行程时也会一并清除。
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**发送**。"
    note: "“发送到 comma”下方的 **将每次行程发送到此 comma** 会在您点按“开始”时发送每次行程。如果分支版本的驾驶设置发生变化，它会自动暂停，直到您再次同意。"
check: "在 **地图与导航** 中，**API 密钥** 以遮盖形式显示您的密钥，路线预览显示 **路线由 Stadia Maps 提供 · 导航仅供显示，绝不会控制车辆。**"
fixes:
  - q: "“添加你自己的 Stadia Maps 密钥以获取路线：设置 › 地图和导航。”"
    a: "还没有保存密钥。在路线预览中点按 **添加密钥**，或按照[第 2 步和第 3 步](#step-get-key)操作。没有密钥时，“要去哪里？”、搜索和地点也能使用。"
  - q: "“Stadia Maps 不接受此密钥（401）。请确认您已从控制台完整复制。”"
    a: "从您的 Stadia Maps 控制台重新完整复制密钥，再粘贴一次。"
  - q: "“这不是 Stadia Maps 密钥。”"
    a: "您粘贴的内容不像 API 密钥，所以没有发送任何东西。请从您的 Stadia Maps 控制台复制 API 密钥：由字母、数字和连字符组成。"
  - q: "“Stadia Maps 拒绝了此密钥（403）：它的套餐可能不包含路线规划。”"
    a: "请在您的 Stadia Maps 控制台中查看套餐。"
  - q: "“您的 Stadia Maps 密钥已超出用量（429）”"
    a: "本月的额度已用完，或刚才请求太频繁。请在您的 Stadia Maps 控制台中查看。应用在五分钟内不会再用它发出请求。"
  - q: "“无法连接 Stadia Maps 来检查密钥。请检查这部手机的网络连接后重试。”"
    a: "您的手机现在无法上网。请使用移动数据或可以上网的 Wi‑Fi 再试一次。"
  - q: "首页上没有 **要去哪里？**"
    a: "导航从 CommaView 0.0.167 起向已登录的成员提供。未登录，或访问通行证校验不通过时，不会提供。在中国大陆不提供导航。"
  - q: "转向卡片显示“车辆位置已关闭”"
    a: "导航需要您 comma 的位置。请在首页为这台 comma 开启 **车辆位置**。"
  - q: "转向卡片显示“正在等待 GPS”"
    a: "导航会在 comma 首次定位后开始。请在开阔的天空下稍等片刻。"
  - q: "“单次行程太远”"
    a: "导航只规划 1500 公里（930 英里）以内的路线。请先选择途中的一个停靠点，再从那里继续。"
  - q: "没有 **发送到 comma**"
    a: "它只会在路线预览中显示，而且只适用于导航可以接收目的地的分支版本：StarPilot、carrotpilot，或 openpilot 和 sunnypilot 的导航（alpha）。"
  - q: "“无法连接到你的 comma 来发送这次行程。”"
    a: "请将这部手机连接到与 comma 相同的网络，然后点按 **重试**。"
  - q: "“comma 上 openpilot 的导航（alpha）已关闭。”"
    a: "请在停车时点按 **开启导航（alpha）**。在每次启动都会关闭它的正式版构建上，目前还无法让它保持开启。"
related: [live-view, car-screens, overlays]
---

## Live View 中的地图

**设置 › 地图与导航 › Live View 地图** 决定地图放在哪里：

- **布局**：**自动**（有空间时在视频旁，否则在角落）、**视频旁** 或 **角落**。comma 3X、comma four、StarPilot 和 Surround 画面总是把地图放在视频旁。
- **视频旁的宽度** 通过在 Live View 中拖动分隔线来设置。**重置** 会恢复默认。
- **地图主题**：**与应用相同**（默认：CommaView 使用浅色时为浅色，使用深色时为深色）、**自动**（按 comma 所在地，日出到日落使用浅色）、**与手机相同**、**浅色** 或 **深色**。它适用于每张地图：Live View 的地图、首页的位置卡片、**车辆位置** 和路线预览。

## 语音引导和您的地点

- **语音引导** 用来开启或关闭语音提示。转向卡片上的扬声器按钮 **导航语音静音** 是同一项设置。
- **您的地点**：**家** 和 **公司**，以及 **最近的地点**，都保存在这部手机上。**清除** 会删除最近的地点。

## 来自其他应用的地点

在 Google 地图或其他地图应用中分享一个地点，然后选择 **用 CommaView 导航**。它的路线预览会在首页打开，就像已保存的地点一样。

## Mapbox

如果您的账号提供此功能，“设置 › 地图与导航”可以改用您自己的 Mapbox 令牌来规划路线，代替 Stadia Maps。

## 隐私

您的 Stadia Maps 密钥只加密保存在这部手机上，绝不会被记录到日志或放进支持数据包。路线请求带着它从您的手机发往 Stadia Maps；不会发送任何内容到 CommaView 的账号服务。搜索请求会发往 Photon，并以您 comma 的位置为中心。清除密钥或退出登录，就会把它从手机上删除。

## 安全

请在停车时设置好行程，让转向卡片和语音来引导您。导航仅供显示：它绝不会转向、制动，也不会改变 openpilot 的任何行为。行驶中请勿操作 CommaView：按照 openpilot 的要求，眼睛看路，双手握住方向盘。
