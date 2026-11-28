---
title: "更新您 comma 的运行环境"
description: "从首页或设备设置更新您 comma 上的 CommaView 运行环境。安全更新会等车辆挂入 P 挡，所以更新绝不会打断行程。"
topic: account
order: 1
kind: walkthrough
lede: "您 comma 上的 CommaView 运行环境只会从应用中更新，绝不会自行更新。请先更新 CommaView，等应用提供运行环境更新时再更新运行环境。如果车辆正在行驶，**安全更新** 会先在 comma 上安排更新，等车辆挂入 P 挡且 openpilot 未启用时再安装。"
updated: 2026-11-27
needs:
  - title: "手机和 comma 在一起"
    text: "与 comma 连接同一个 Wi‑Fi，或连接它的热点。"
  - title: "车辆已通电"
    text: "请保持车辆通电并挂入 P 挡。没有常电线时，车辆熄火也会让 comma 关机。"
howItWorks:
  - title: "CommaView"
    text: "每个应用版本都会指明与它一起测试过的运行环境，并只提供那一个。"
  - title: "您的 comma"
    text: "在车辆挂入 P 挡后下载、检查并安装它。"
    edge: "重启"
  - title: "Live View"
    text: "comma 重启后重新开始。"
steps:
  - id: app-first
    title: "先更新 CommaView"
    body: |
      应用会安装与它一起测试过的运行环境，所以请先更新应用，再更新运行环境。有更新就绪时，首页顶部和设置 › **关于** 中会显示 **更新**。点按它：**更新 CommaView** 会显示版本号、渠道和大小。点按 **下载**；CommaView 会在后台下载并检查，然后由 Android 请您确认安装。
    screen: app-update-offer
    pins:
      - target: download
        text: "**下载**。"
      - target: channel
        text: "版本的渠道：**Beta**，或面向测试人员的 **Alpha**。"
    note: "在更新这台 comma 的运行环境之前，请先更新每部观看它的手机、平板和车载屏幕上的 CommaView。"
  - id: open
    title: "打开运行环境更新"
    tabs:
      - label: "从首页"
        body: "这台 comma 有新的运行环境就绪时，首页会显示 **运行环境更新已就绪**。点按 **查看更新**：**运行环境更新** 卡片会显示 **已安装** 和 **可用** 的版本，以及车辆是否已就绪。点按 **更新运行环境**；车辆行驶中则点按 **安排更新**。"
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**运行环境更新**：已安装、可用，以及车辆是否已就绪。"
          - target: update-runtime
            text: "**更新运行环境**（车辆行驶中为 **安排更新**）。"
      - label: "从设备设置"
        body: "打开 comma 的 **设备设置**，然后点按 **运行环境**（有更新就绪时会显示 **更新**）。页面会显示已安装的和可用的运行环境。点按 **立即更新**。"
        screen: device-runtime
        pins:
          - target: update-now
            text: "**立即更新**。"
  - id: install
    title: "安装，或让安全更新先安排"
    body: |
      从设备设置进入时，**运行环境更新** 对话框会说明车辆是否已就绪。
    tabs:
      - label: "车辆已挂入 P 挡"
        body: "它会显示“车辆已挂入 P 挡，openpilot 未启用。可以安全开始更新运行环境。”点按 **安装更新**。"
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**安装更新**。"
          - target: close
            text: "**关闭** 则留待以后。"
      - label: "车辆正在行驶"
        body: "它会显示“车辆正在行驶。安全更新会先在 comma 上安排更新，等车辆挂入 P 挡且 openpilot 未启用时再安装。”点按 **安全更新…**，阅读说明，短暂倒计时结束后点按 **开始安全更新**。如果 CommaView 无法确认车辆是否正在行驶，也会这样处理。"
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**安全更新…**，然后 **开始安全更新**。"
    note: "CommaView 绝不会停止 openpilot 或您的分支版本：已安排的更新会等车辆挂入 P 挡，行程绝不会被打断。"
  - id: progress
    title: "让它运行"
    body: |
      comma 会下载新版本，检查它完整且未被篡改，安装后重启 CommaView，应用会显示每一步。您可以切换应用或锁屏：更新会继续进行，它的通知会显示进度。

      在 comma 开始安装之前，**取消更新** 可以停止它，您 comma 上的任何内容都不会改变。
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "各个步骤：下载、验证、安装、重启 CommaView、重新连接。"
  - id: queued
    title: "已安排的更新会等车辆挂入 P 挡"
    body: |
      已安排的更新会在首页的 **运行环境更新** 卡片上显示为 **等待车辆挂入 P 挡**。车辆挂入 P 挡数秒且 openpilot 未启用后，它就会安装。安装期间请保持车辆通电。
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "**等待车辆挂入 P 挡**，以及当前步骤。"
  - id: reboot
    title: "重启 comma 以完成"
    body: |
      运行环境更新后，comma 需要重启，CommaView 才能再次从它推流：openpilot 只有在 comma 重启时才会加载 CommaView 新的画面代码。应用绝不会自行重启它。

      请在车辆熄火或挂入 P 挡时，点按首页卡片上的 **重启 comma**，或对话框中的 **立即重启 comma**。openpilot 会停止约一分钟。您也可以在 comma 上重启：**设置 → 设备 → 重启**。
check: "更新的最后一步显示 **已更新**，设备设置中新的运行环境显示 **已是最新版本**。重启后，Live View 会连同叠加图层一起播放。"
fixes:
  - q: "“这台 comma 的运行环境比此应用所安装的更新”"
    a: "请更新 CommaView，然后重试。comma 上没有任何更改。"
  - q: "“需要更新”"
    a: "此应用和这台 comma 的运行环境彼此都不够新。请先更新 CommaView，再更新运行环境。"
  - q: "“comma 没有安装 …：它运行的是 CommaView 未列出的 …”"
    a: "comma 没有做任何更改，保留了原来的运行环境。如需以尽力支持的方式把 CommaView 加入那个分支版本，请为这台 comma 重新运行设置：它会检查分支版本并先询问您。"
  - q: "“每次开始时车辆都再次启动，因此 comma 停止了尝试”"
    a: "请将车辆挂入 P 挡并让 openpilot 处于未启用状态，然后重试。"
  - q: "“运行环境更新已回滚”"
    a: "comma 恢复了原来的运行环境。请重试；如果再次失败，请[发送支持数据包](/zh-cn/guides/support-bundle)。"
  - q: "“CommaView 已在更新或卸载运行环境”"
    a: "同一时间只能运行一项运行环境任务。请等它完成后重试。"
  - q: "更新后没有叠加图层或遥测数据"
    a: "comma 还没有重启。请在车辆熄火或挂入 P 挡时重启它。"
related: [releases, uninstall, another-phone]
---

## 为什么更新要等车辆挂入 P 挡

安装运行环境时，comma 上的 CommaView 会在替换文件期间停止，并重启它的服务，所以 comma 只会在车辆挂入 P 挡且 openpilot 未启用时进行。安全更新不会要求 openpilot 进入停车状态：它会在 comma 上安排这项工作，由 comma 在车辆挂入 P 挡后执行。您不需要熄火；保持通电并挂入 P 挡即可。

在改动 comma 上的任何内容之前，它会先下载新版本，并检查它完整且未被篡改。如果之后安装失败，comma 会恢复原来的运行环境。
