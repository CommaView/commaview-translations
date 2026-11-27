---
title: "从您的 comma 移除 CommaView"
description: "在设备设置中从 comma 卸载 CommaView 运行环境，把分支版本的文件恢复原状，并在手机上忘记这台 comma。"
topic: account
order: 3
kind: walkthrough
lede: "**卸载运行环境** 会从您的 comma 移除 CommaView：它会撤销 CommaView 的钩子，停止它的运行环境，并删除 `/data/commaview`。您的分支版本会照常驾驶。可以用它来移除 CommaView，或从头重新运行引导设置。"
parked: true
updated: 2026-11-27
needs:
  - title: "手机和 comma 在一起"
    text: "与 comma 连接同一个 Wi‑Fi，或连接它的热点。设备设置需要连接 comma 才能管理更新和移除。"
  - title: "车辆通电并挂入 P 挡"
    text: "如果车辆正在行驶，comma 会先安排卸载，等车辆挂入 P 挡且 openpilot 未启用时再执行。"
steps:
  - id: device-settings
    title: "打开 comma 的设备设置"
    body: |
      从首页打开您 comma 的 **设备设置**，然后点按 **运行环境**（“更新或卸载”）。
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**运行环境**：更新或移除 CommaView。"
  - id: uninstall
    title: "点按“卸载运行环境”"
    body: |
      在运行环境更新下方，**卸载运行环境** 会从这台 comma 移除 CommaView。之后引导设置就可以从头再运行一次。
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**卸载运行环境**。"
  - id: confirm
    title: "确认"
    body: |
      **将移除 CommaView**：CommaView 会撤销它的运行环境钩子、停止运行，并从这台 comma 删除 `/data/commaview`。这台 comma 仍会保存在您的手机上。短暂倒计时结束后，点按 **卸载运行环境**。
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**将移除 CommaView**，以及这会做什么。"
      - text: "倒计时结束后点按 **卸载运行环境**。**取消** 会保留 CommaView。"
    note: "如果车辆正在行驶，comma 会先安排卸载：等车辆挂入 P 挡且 openpilot 未启用时，CommaView 才会被移除，在此之前它会继续运行。"
  - id: forget
    title: "如有需要，在手机上忘记这台 comma"
    body: |
      设备设置现在会显示运行环境已移除。如果也想把这台 comma 从手机上移除，请点按设备设置底部的 **忘记这台 comma**：CommaView 将不再显示这台 comma，并删除它的配对密钥。要移除应用本身，请像卸载任何应用一样，在 Android 的设置中卸载 CommaView。
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**忘记这台 comma**。"
check: "对话框显示 **已卸载运行环境**，设备设置中的运行环境显示 **已移除**：“已从您的 comma 卸载 CommaView。请运行引导设置以重新安装。”"
fixes:
  - q: "“因 SSH 权限错误，卸载失败”"
    a: "comma 没有允许这部手机通过 SSH 登录。请确认 comma 上 **设置 → 设备 → SSH** 已开启，且它的 GitHub 用户名下有这部手机的密钥，然后点按 **再次卸载**。"
  - q: "“comma 无法卸载 CommaView，因此保持原状”"
    a: "没有移除任何东西。请在车辆挂入 P 挡时重试。"
  - q: "“已安排卸载，等待车辆挂入 P 挡”"
    a: "车辆正在行驶。请挂入 P 挡并让 openpilot 处于未启用状态，保持车辆通电，comma 会自行移除 CommaView。"
  - q: "“卸载”按钮呈灰色"
    a: "CommaView 已在更新或卸载运行环境。请等它完成后重试。"
related: [setup, update-runtime, forks]
---

## 卸载会恢复什么

- **在列出的分支版本上**，它会撤销 CommaView 加在分支版本屏幕界面中的小钩子。
- **在 CommaView 未列出的分支版本上**（尽力支持），它会把分支版本的文件恢复原状。
- **仅视频** 模式没有改动分支版本的任何文件，卸载会移除运行环境。

在 SunnyPilot-TeslaHW1 上，请先卸载运行环境，再运行 `op fork update`，因为安装了 CommaView 的钩子时，它无法切换分支版本。更多内容见[检查您的 comma 和分支版本是否受支持](/zh-cn/guides/forks)。

## 重新设置 CommaView

卸载后，这台 comma 仍会保存在您的手机上。运行[引导设置](/zh-cn/guides/setup)，即可作为全新安装重新安装。
