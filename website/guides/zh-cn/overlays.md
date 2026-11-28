---
title: "选择行车画面并添加叠加包"
description: "选择 Live View 绘制道路的方式：comma four 的画面、comma 3X 的画面，或 CommaView 自己的。然后添加叠加包，补上您的分支版本在自己画面上绘制的内容。"
topic: screens
order: 6
kind: walkthrough
lede: "Live View 会在道路摄像头画面上绘制行车画面：**comma four** 的、**comma 3X** 的，或 **CommaView** 自己的。comma 的画面会以您的分支版本的样式绘制。**叠加包** 会补上您的分支版本自己画面上有、而 CommaView 没有绘制的内容，例如 BluePilot 的混合动力仪表或 dragonpilot 的彩虹路径。"
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "Live View 可以正常使用"
    text: "Android 手机上的 CommaView 已与您的 comma 配对。还没有？[设置 CommaView](/zh-cn/guides/setup)。"
  - title: "使用商店需要登录"
    text: "成员可以浏览 CommaView 的叠加包。未登录时，仍可以从文件或链接添加叠加包。"
steps:
  - id: switch
    title: "在 Live View 中切换画面"
    body: |
      在 Live View 中点按行车画面切换按钮。它以当前显示的画面命名，每点按一次就切换到下一个：**comma 4**、**comma 3X**、**CommaView**，然后循环。您最后停留的那个会保留到下次。
    screen: phone-live-view
    clip: onroad-screen
    pins:
      - target: onroad-screen-button
        text: "行车画面切换按钮，以当前显示的画面命名。"
    note: "在其他控件旁放不下时，它会以 **行车画面** 的名称收进 **更多**。录制进行时它会变暗：录像会保持开始时的画面。"
  - id: display
    title: "或在设置 › 显示中选择"
    body: |
      想在选择前看看每种画面，请打开 **设置 › 显示**。**行车画面** 卡片会在一张道路照片上预览所选的画面，按您 comma 的摄像头取景，并以您的分支版本的样式绘制。下方的 **已启用**、**驾驶员介入** 和 **未启用** 会切换显示的时刻；它们不会保存任何设置。
    screen: settings-display
    pins:
      - target: onroad-screen-card
        text: "所选画面的预览。"
      - target: onroad-screen
        text: "**行车画面**：点按即可查看列表。"
  - id: pick
    title: "选择一种画面"
    body: |
      列表中的每种画面都有一张小图和一段说明：

      - **comma four**：MAX 在道路上方，随时变化，旁边是方向盘和置信度。
      - **comma 3X**：状态边框、MAX 框、大号车速，以及底部的警报。
      - **CommaView**：流动的路径、锁定前车的标记，以及 CommaView 自己的车速、状态和警报。

      选择一种就会保存，并更新预览、它的选项和 Live View。任何画面都可以在任一款 comma 上使用。
    screen: settings-display-onroad-screens
    clip: display-pick
    pins:
      - target: comma-four-option
        text: "**comma four**。"
      - target: comma-3x-option
        text: "**comma 3X**。"
      - target: commaview-option
        text: "**CommaView**。"
    note: "无论您选择哪种画面，警报、警告和驾驶员监控状态始终使用您 comma 自己的颜色。"
  - id: store
    title: "打开叠加包商店"
    body: |
      打开 **设置 › 叠加包**，或点按首页上的 **叠加包** 卡片。
    tabs:
      - label: "已登录"
        body: |
          商店会先列出 CommaView 的 **官方** 叠加包，然后是 **社区** 的，每一个都经过 CommaView 审核。**适用您的 comma** 会推荐适合您 comma 所运行分支版本的官方叠加包。可以搜索，也可以用 **全部**、**官方**、**社区** 和 **适用我的 comma** 缩小列表范围。
        screen: overlay-packs-store
        pins:
          - target: search
            text: "**搜索叠加包**。"
          - text: "**适用您的 comma**：适合您 comma 分支版本的官方叠加包。"
          - target: bluepilot-row
            text: "**官方** 叠加包，例如 BluePilot HUD。"
          - target: yours
            text: "**您的叠加包**：这部手机上已有的。"
      - label: "从文件或链接添加"
        body: |
          有人分享了 `.cvpack` 文件或链接（GitHub、gist、Discord 附件）？打开 **您的叠加包**，在 **自行添加叠加包** 下点按 **从文件安装** 或 **粘贴链接**。以这种方式添加的叠加包未经 CommaView 审核，安装对话框也会这样说明。
  - id: install
    title: "安装叠加包"
    body: |
      点按一个叠加包，查看它的预览、**适用于** 哪些分支版本，以及它会给 Live View 增加什么。点按 **安装**，然后在对话框中再次点按 **安装**。叠加包会安装到这部手机和您已配对的 comma 上。
    screen: overlay-pack-detail
    pins:
      - text: "预览：加上叠加包后的 Live View。点按即可放大。"
      - target: install
        text: "**安装**。"
    note: "官方叠加包只会在它适用的分支版本上运行。如果您已配对的 comma 都没有运行这些分支版本，对话框会如实说明；它仍会安装，但在有 comma 运行这些分支版本之前不会显示在 Live View 中。"
  - id: drive
    title: "下次行驶时查看效果"
    body: |
      安装后，商店会说明叠加包会在这部手机连接到 comma 时传过去，并在车辆熄火时在那里生效。下次行驶时打开 Live View：叠加包会绘制在 comma four、comma 3X 和 CommaView 画面上，位于行车画面自己的警报下方。

      要关闭叠加包，请打开 **您的叠加包**：每个叠加包只有一个开关，同时作用于这部手机和每台已配对的 comma。
check: "在 Live View 的 **详细信息** 中，**叠加包** 一行会显示该叠加包的名称，并标为 **运行中**。"
fixes:
  - q: "行车画面切换按钮变暗了"
    a: "正在录制。停止录制或等它结束后再切换。"
  - q: "详细信息显示叠加包“不适用于此分支版本”"
    a: "这个叠加包是为其他分支版本的画面制作的，在您的画面上不会绘制任何内容。官方叠加包会在 **适用于** 下说明它适用的分支版本。"
  - q: "Live View 中还没有出现叠加包"
    a: "它会在您的手机连接到 comma 时传过去，并在车辆熄火时在那里生效。请在手机连接 comma 网络的情况下，让车辆熄火再重新启动，然后打开 Live View。"
  - q: "“登录以查看 CommaView 的叠加包”"
    a: "商店只向已登录的成员列出 CommaView 的叠加包。点按 **登录**。退出登录期间，手机上已有的叠加包会继续运行。"
  - q: "“无法连接到 my.commaview.com”"
    a: "请检查这部手机的网络连接，然后点按 **重试**。**您的叠加包** 仍会列出手机上的所有叠加包。"
related: [live-view, record, forks]
blogPost: commaview-0-0-166-languages-browser-view
---

## 每种画面的选项

在预览下方，**设置 › 显示** 会显示所选画面自己的选项：

- **comma four 选项**：**预览取景**（与 comma four 的取景完全一致、显示更多摄像头画面，或裁切以填满这块屏幕）和 **紧凑置信度面板**（更小的面板和球，留出更多视频空间）。
- **CommaView 选项**：**摄像头取景**（**填满屏幕** 会裁切摄像头画面以填满横向屏幕；**完整画面** 会显示全部画面，必要时加上黑边）和 **减少动态效果**，它会让 CommaView 的路径、车速和锁定标记保持静止。
- **comma 3X**：没有选项。它完全按 comma 的画法绘制。

接着是 **所有画面**：**驾驶座位置**（镜像控件）、**主题**、在阳光和眩光下使用的 **日光对比度**，以及针对会裁掉画面边缘的车载屏幕的 **屏幕边缘**（[车载屏幕](/zh-cn/guides/car-screens)）。

在“录像”中制作的回放会绘制您录制时 Live View 绘制的内容，无论之后您怎么选择。

## 叠加图层从哪里来

CommaView 不会凭空猜测要绘制什么。您 comma 上的运行环境会在视频旁一并发送 openpilot 自己的画面所读取的驾驶数据（行驶路径、车道线、前车、车速、警报、驾驶员监控），应用再在您的手机上把它绘制出来，并与正在显示的摄像头画面对齐。当这些数据延迟、缺失或属于另一个摄像头时，CommaView 会略过那一部分，而不是画出可能有误的内容。

## 安全

请在停车时选择画面和安装叠加包。行驶中请勿操作 CommaView：按照 openpilot 的要求，眼睛看路，双手握住方向盘。叠加图层只是用来看的，不是驾驶辅助：comma 自己的警报和车辆的仪表始终优先。驾驶员监控图标并不能证明您在专心驾驶，回放中的叠加图层是用来回顾行程的，不能作为当时实际情况的确切证据。
