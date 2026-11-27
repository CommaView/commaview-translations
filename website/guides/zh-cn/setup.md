---
title: "设置 CommaView"
description: "在 Android 上安装 CommaView 应用，准备好您的 comma 3X 或 comma four，然后让引导设置安装运行环境并配对您的 comma。"
topic: start
order: 1
kind: walkthrough
lede: "CommaView 由两部分组成：您 Android 手机、平板或车机上的应用，以及 comma 上的小型运行环境。先安装应用，再由应用中的引导设置把运行环境装到 comma 上、检查并完成配对。整个过程只需几分钟，请在车辆挂入 P 挡、openpilot 未启用时进行。"
parked: true
updated: 2026-11-27
needs:
  - title: "一台 comma 3X 或 comma four"
    text: "运行 openpilot 或[支持的分支版本](/zh-cn/guides/forks)。不支持 comma 3：它的 openpilot 版本已在上游冻结，画面的绘制方式也不同，因此 CommaView 无法显示它的叠加图层。[为什么不支持 comma 3](/#faq-comma-3)。"
  - title: "一台 Android 设备和您的邀请"
    text: "Android 8 或更高版本，以及收到邀请的电子邮箱。CommaView 目前处于 Beta 阶段：请使用受邀的账号登录。"
  - title: "同一个网络"
    text: "您的手机和 comma 在同一个本地网络中：您的 Wi‑Fi、手机热点、comma 自己的热点，或两者都能加入的任何其他网络。在车上？请看[不用家里的 Wi‑Fi，在车上连接](/zh-cn/guides/connect-in-the-car)。"
  - title: "一个 GitHub 账号"
    text: "comma 会接受您提供的 GitHub 用户名下的 SSH 密钥。CommaView 会生成密钥，您在设置过程中把它添加到 GitHub。"
howItWorks:
  - title: "您的手机"
    text: "生成一把 SSH 密钥，由您添加到 GitHub。"
    edge: "SSH"
  - title: "您的 comma"
    text: "从您的 GitHub 用户名获取密钥。CommaView 会在您的分支版本旁安装它的运行环境。"
    edge: "本地网络"
  - title: "CommaView"
    text: "检查运行环境有响应，并保存您的 comma。之后它会自行重新连接。"
steps:
  - id: get-the-app
    title: "获取应用并登录"
    body: |
      在您的 Android 设备上，用收到邀请的电子邮箱登录 [my.commaview.com](https://my.commaview.com)。在 **Get the app** 下点按 **Download CommaView**。如果想校验文件，旁边会显示它的 SHA-256 校验码。

      打开下载的文件。Android 会请您允许从浏览器安装应用：仅为这次安装允许，装完后再关闭。

      打开 CommaView。它会询问一次是否要 **帮助改进 CommaView**：选择 **发送** 或 **不发送**。然后它会请您登录：点按 **登录**，使用收到邀请的电子邮箱。之后，只要访问通行证有效，它就可以离线使用。
    tabs:
      - label: "帮助改进 CommaView"
        body: "崩溃报告，以及您的 comma 运行的驾驶软件，绝不包括视频、行程、地点或名称。您可以随时在设置 › **隐私与分享** 中更改。"
        screen: improve-commaview
        pins:
          - target: send
            text: "**发送** 崩溃报告，帮助修复问题。"
          - target: dont-send
            text: "**不发送** 则把报告留在手机上。"
      - label: "登录"
        body: "Beta 期间，CommaView 需要您的受邀账号。**登录** 会打开您的浏览器。"
        screen: sign-in
        pins:
          - target: sign-in
            text: "用收到邀请的电子邮箱 **登录**。"
    note: "要安装在车机上，或连接车载屏幕的 AI 盒子上？[车载屏幕](/zh-cn/guides/car-screens) 介绍了它的网络设置以及如何与您的 comma 配对。"
  - id: connect
    title: "开始设置您的 comma"
    body: |
      阅读提示，勾选您了解这是非官方软件、并由您负责安全使用，然后点按 **我了解 — 继续**。

      在 **连接您的 comma** 页面，点按 **在您的 comma 上设置 CommaView**。
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**在您的 comma 上设置 CommaView**，适用于尚未运行 CommaView 的 comma。"
      - target: pair-runs
        text: "已经通过另一部手机运行 CommaView？请改为点按 **配对已运行 CommaView 的 comma**：见[添加另一部手机或平板](/zh-cn/guides/another-phone)。"
  - id: setup-path
    title: "选择设置方式"
    tabs:
      - label: "引导设置"
        body: "选择 **引导设置**（标有“推荐”），然后点按 **继续引导设置**。CommaView 会生成 SSH 密钥、引导您完成连接并检查您的 comma。接下来的步骤都按它进行。"
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**引导设置**，标有“推荐”。"
          - target: continue
            text: "**继续引导设置**。"
      - label: "手动设置"
        body: "仅适用于您的电脑已经能以用户 `comma` 通过 SSH 连接 comma 的情况。选择 **手动设置**，再点按 **继续手动设置**，然后在终端运行命令。安装程序显示一次性配对码后，点按 **我已运行命令**，输入 comma 的 IP 和配对码，再点按 **添加 comma**。[通过终端手动设置](#manual-setup-from-a-terminal) 列出了每一步。"
        screen: setup-manual-instructions
        pins:
          - text: "**轻点即可复制** 会复制命令。"
          - target: ran-command
            text: "安装程序显示配对码后，点按 **我已运行命令**。"
  - id: ssh-key
    title: "将 SSH 密钥添加到 GitHub"
    body: |
      CommaView 会为这部手机生成一把 SSH 密钥。点按 **复制密钥并打开 GitHub**：它会复制公钥，并打开 GitHub 的新建 SSH 密钥页面。

      在 GitHub 上，把密钥粘贴到 **Key** 字段，标题随意填写（CommaView 会预先填好一个），然后点按 **Add SSH key** 保存。回到 CommaView，点按 **继续**。
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**复制密钥并打开 GitHub**。它会显示“已复制 SSH 密钥。正在打开 GitHub…”"
      - target: own-key
        text: "**使用我自己的 SSH 密钥** 可导入您在 GitHub 上已有的密钥对。"
      - target: continue
        text: "密钥在 GitHub 上保存后，点按 **继续**。"
    note: "在 GitHub 上已有密钥对？可以改用 **使用我自己的 SSH 密钥** 导入。私钥会留在您的手机上。"
  - id: comma-ssh
    title: "在 comma 上开启 SSH"
    body: |
      在 comma 的屏幕上，前往 **设置 → 设备 → SSH**：

      1. 输入您的 GitHub 用户名。
      2. 等待 comma 获取您的 GitHub 密钥。
      3. 开启 SSH。

      然后回到 CommaView，点按 **继续**。
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "SSH 开启后，点按 **继续**。"
    note: "comma 只会在您输入用户名时获取一次密钥。如果是在添加密钥之前输入的用户名，请移除后重新输入，让 comma 再获取一次密钥。"
  - id: choose-comma
    title: "选择您的 comma"
    body: |
      CommaView 会列出这个 Wi‑Fi 网络中已运行 CommaView 的 comma，所以第一次设置的 comma 通常还不在列表里。点按 **列表中没有我的 comma**，输入它的 IP 地址，然后点按 **安装 CommaView**。

      IP 地址可在 comma 的 **设置 → 网络** 中找到：comma four 上在 Wi‑Fi 按钮的网络名称下方，comma 3X 上在 **高级** 中。
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "已运行 CommaView 的 comma。保存在这部手机上的会标为 **已保存在这部手机上**。"
      - text: "**列表中没有我的 comma**：输入它的 IP 地址。"
      - target: install
        text: "**安装 CommaView**。"
  - id: safe-install
    title: "开始安全安装"
    body: |
      **安全安装** 对话框会显示要安装到哪台 comma。阅读说明，短暂倒计时结束后点按 **开始安全安装**。
    tabs:
      - label: "车辆已挂入 P 挡"
        body: "如果车辆已挂入 P 挡且 openpilot 未启用，CommaView 会立即安装。"
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "倒计时结束后点按 **开始安全安装**。"
      - label: "车辆正在行驶"
        body: "comma 会先安排安装，等车辆挂入 P 挡且 openpilot 未启用时再执行，因此绝不会打断行程。设置会显示 **已安排安装**：请将车辆挂入 P 挡并让 openpilot 处于未启用状态，等一两分钟，然后点按 **完成设置**。"
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "车辆挂入 P 挡后，点按 **完成设置**。"
    note: "接着 CommaView 会通过 SSH 连接 comma，确认是哪台 comma，并安装与此版本应用一起测试过的运行环境。它会检查安装是否有响应，并把您的 comma 保存在这部手机上。完成之前，请让手机保持在同一个网络中。"
    warn: "请保持车辆通电并挂入 P 挡。没有常电线时，车辆熄火也会让 comma 关机，从而中断安装。"
  - id: ready
    title: "CommaView 已就绪"
    body: |
      您的 comma 已安装并配对，下次启动时会自行重新连接。
    tabs:
      - label: "CommaView 已就绪"
        body: "点按 **完成**。"
        screen: setup-done
        pins:
          - target: finish
            text: "**完成** 会带您回到首页。"
      - label: "重启以完成设置"
        body: "有时设置会显示 **重启以完成设置**：comma 重启一次后才会向您的手机推流。请在车辆熄火，或挂入 P 挡且 openpilot 未启用时，点按 **重启 comma 并完成**。重启期间 openpilot 会停止约一分钟。"
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**重启 comma 并完成**。"
check: "首页会显示您的车辆，其 comma 为 **已连接**，以及运行环境和 comma 的地址。点按 **打开 Live View**：道路画面实时播放，上面画着行驶路径和前车。从此以后，只要手机和 comma 在同一个网络中，即使 comma 的地址变了，应用也会自行找到它。"
fixes:
  - q: "无法通过 SSH 连接"
    a: "请检查 comma 上 **设置 → 设备 → SSH** 已开启，GitHub 用户名是您自己的，且 CommaView 密钥已添加到该 GitHub 账号。如果是在输入用户名之后才添加的密钥，请移除用户名再重新输入，让 comma 获取密钥。"
  - q: "列表里没有我的 comma"
    a: "第一次设置时这很正常：列表只显示已运行 CommaView 的 comma。点按 **列表中没有我的 comma**，输入它的 IP 地址（comma 上的 **设置 → 网络**：comma four 上在 Wi‑Fi 按钮的网络名称下方，comma 3X 上在 **高级** 中）。请确认手机与 comma 在同一个网络中，且没有使用 VPN。"
  - q: "设置显示“已安排安装”"
    a: "comma 检测到车辆正在行驶，所以会等待。请将车辆挂入 P 挡并让 openpilot 处于未启用状态，等一分钟，然后点按 **完成设置**。请保持车辆通电：没有常电线时，车辆熄火也会让 comma 关机。"
  - q: "设置显示我的 comma 不受支持"
    a: "在 comma 3 上，设置会停止，并提供 **在 comma 3X 或 comma four 上设置 CommaView**。如果分支版本的画面无法加入 CommaView 的画面，设置会如实说明，并且不做任何更改。[检查您的 comma 和分支版本是否受支持](/zh-cn/guides/forks)。"
  - q: "配对码无效"
    a: "配对码只能使用一次，而且很快就会过期。请重新运行安装程序获取新的配对码，并确认输入与显示的一致（连字符可省略）。"
  - q: "已连接，但没有视频"
    a: "设置和配对都已完成，问题出在视频流。请确认 comma 已开机并可以行驶，让手机保持在同一个网络中，然后重新打开 Live View。如果显示 **连接不到这台 comma**，请看 [CommaView 找不到您的 comma](/zh-cn/guides/comma-not-found)。"
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## 通过终端手动设置

仅适用于您的电脑已经能以用户 `comma` 通过 SSH 连接 comma 的情况。

1. 在 CommaView 中选择 **手动设置**，再点按 **继续手动设置**。应用会在 **从您的终端安装** 页面显示适用于其运行环境的命令，可直接复制（**轻点即可复制**）。它类似下面这条安装当前版本运行环境的命令：

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. 在与 comma 处于同一个 Wi‑Fi 网络的电脑上运行它，并把 `COMMA_IP` 替换为 comma 的 IP 地址（comma 上的 **设置 → 网络**：comma four 上在 Wi‑Fi 按钮的网络名称下方，comma 3X 上在 **高级** 中）。您的电脑会下载安装程序，再通过 SSH 以用户 `comma` 在 comma 上运行它。
3. 安装程序完成后，CommaView 会在 comma 上启动，并显示一次性配对码。
4. 回到 CommaView，点按 **我已运行命令**。在 **添加您的 comma** 页面，选择您的 comma 或输入它的 IP，输入配对码，然后点按 **添加 comma**。应用会检查运行环境并保存这台 comma。

## 第一次行驶之前

上路前，先在停车时试一试。

- 首页显示您的 comma 为 **已连接**。
- Live View 可以播放，行驶路径会随车辆移动。
- 如果应用显示警告或要求修复，请在行驶前处理好。
- 把一切设置好，让它在行驶中不需要您操作。

还是没解决？请在 [CommaView Discord](https://discord.gg/UuMhz9K8ft) 提问，或从应用中发送反馈。如果支持人员需要日志，请[发送支持数据包](/zh-cn/guides/support-bundle)。
