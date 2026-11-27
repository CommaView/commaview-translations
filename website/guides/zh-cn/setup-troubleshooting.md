---
title: "设置中途停止时的解决方法"
description: "CommaView 设置消息的含义，按设置进行的顺序排列：SSH、安装，然后是配对。找到您看到的消息，以及该怎么处理。"
topic: troubleshooting
order: 1
kind: fixes
lede: "设置按顺序进行：先通过 SSH 登录您的 comma，再安装 CommaView 的运行环境，然后把您的手机与它配对。中途停止时，消息会说明是哪一部分失败了，请先解决那一部分。SSH 能用只证明了第一步：运行环境没有启动时，配对码不可能有效。"
parked: true
updated: 2026-11-27
needs:
  - title: "挂入 P 挡"
    text: "车辆挂入 P 挡、openpilot 未启用，并保持通电：没有常电线时，车辆熄火也会让 comma 关机。"
  - title: "同一个网络"
    text: "您的手机与 comma 连接同一个 Wi‑Fi，或连接它的热点。笔记本电脑能连接 comma，并不代表手机也能。"
steps:
  - id: read
    title: "阅读设置的说明，并复制详细信息"
    body: |
      安装失败时，设置会说明出了什么问题、您的 comma 是否已恢复原状，以及该怎么做。请在下方的[如果不成功](#fixes)中找到那句话。

      **复制详细信息** 会复制支持人员要看的报告：应用的版本、发布版本、安装程序的最后阶段及其完整输出。消息提示时，请把它粘贴到发往 support@commaview.com 的电子邮件中。
    tabs:
      - label: "安装失败"
        body: "设置会说明失败的原因，并提供 **复制详细信息**。"
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**复制详细信息**。"
          - target: install
            text: "解决原因后，点按 **安装 CommaView** 重试。"
      - label: "SSH 失败"
        body: "在安装任何东西之前，设置会说明它为什么无法登录 comma，例如 **SSH 验证失败**，以及需要检查什么。"
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "出了什么问题，以及需要检查什么。"
  - id: address
    title: "检查 comma 的地址"
    body: |
      设置会在您手机所在的网络中查找 comma。如果列表中没有您的那台，请点按 **列表中没有我的 comma**，输入它的 IP 地址。在您的 comma 上，它位于 **设置 → 网络**：comma four 上在 Wi‑Fi 按钮的网络名称下方，comma 3X 上在 **高级** 中。

      comma 在每个网络中的地址都不同：家里的 Wi‑Fi、热点、VPN。请使用手机当前所在网络中的那个地址。
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "设置在此网络中找到的 comma。"
      - text: "**列表中没有我的 comma**：找不到时输入 IP 地址。"
  - id: pair-code
    title: "用新的配对码配对"
    body: |
      配对码有效时间很短，且只能使用一次。如果被拒绝，不要再输入同一个：请获取新的。手动安装后，安装程序会显示一个；已与 comma 配对的手机也可以在 **设备设置 › 配对另一部手机或平板** 下显示一个。
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**comma IP 地址**。"
      - target: pair-code
        text: "**配对码**。连字符可省略。"
  - id: runs
    title: "已经安装过？直接配对"
    body: |
      如果 comma 已经在运行 CommaView（来自另一部手机或之前的设置），就不需要重新安装。在首页点按 **添加 comma**，然后点按 **输入地址和配对码**，用 comma 的 IP 和配对码或邀请码配对。
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "comma 的 IP。"
      - target: pair-code
        text: "**配对码或邀请码**。"
      - target: pair
        text: "**配对 comma**。"
  - id: no-video
    title: "已安装并配对，但没有视频"
    body: |
      配对完成后还没有画面，是推流问题，而不是 SSH 问题。Live View 会说明它看到的情况，例如 **连接不到这台 comma**，并在 comma 响应后自行重新连接。请看 [CommaView 找不到您的 comma](/zh-cn/guides/comma-not-found)。
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**重试**。"
fixes:
  - q: "“SSH 验证失败。”"
    a: "请确认 CommaView 密钥已添加到 GitHub（标题不限），并且 comma 已开启 SSH。如果您是在添加密钥之前在 comma 上输入的 GitHub 用户名，请移除后重新输入，让 comma 再获取一次您的密钥。"
  - q: "“192.168.1.50:22 拒绝连接。请确认您的 comma 已启用 SSH。”"
    a: "在 comma 上前往 **设置 → 设备 → SSH**，开启 SSH。"
  - q: "“连接 … 超时。”或“无法连接到 …。”"
    a: "您的手机无法连接到那个地址。请确认手机与 comma 连接同一个 Wi‑Fi 或连接它的热点、comma 处于唤醒状态（车辆已通电），并且 IP 地址是 comma 在此网络中的地址。"
  - q: "“在 … 找不到 comma。请检查 IP 地址。”"
    a: "那个地址没有任何响应。请在 comma 的 **设置 → 网络** 中检查 IP。"
  - q: "“这台 comma 的 SSH 身份自上次设置后已更改。”"
    a: "如果您重置或重新刷机过这台 comma，请重新运行设置。"
  - q: "“CommaView 无法在这部手机上创建 SSH 密钥。请重试，或使用您自己的 SSH 密钥。”"
    a: "点按 **重试**，或点按 **使用我自己的 SSH 密钥**，导入您在 GitHub 上已有的密钥对。"
  - q: "“已安排安装。”"
    a: "车辆正在行驶，所以 comma 没有打断行程，而是先安排了安装。请将车辆挂入 P 挡并让 openpilot 处于未启用状态，保持车辆通电一两分钟，然后点按 **完成设置**。"
  - q: "“车辆正在行驶，因此没有进行安装。”"
    a: "请将车辆挂入 P 挡并让 openpilot 处于未启用状态，然后重试。"
  - q: "“您的 comma 上已有另一项 CommaView 安装、更新或修复正在进行。”"
    a: "请等几分钟让它完成，然后重试。"
  - q: "“您的 comma 无法下载 CommaView。”"
    a: "运行环境是由 comma 自己下载的。请确认它已连接互联网（通过 Wi‑Fi 或它自己的 SIM 卡），然后重试。使用移动数据的手机热点也可以。"
  - q: "“您的 comma 收到的 CommaView 下载内容不完整或已损坏。”"
    a: "请重试。如果再次发生，请复制详细信息并发送到 support@commaview.com。"
  - q: "“您的 comma 在安装期间存储空间不足。”"
    a: "请稍后重试。如果再次发生，请复制详细信息并发送到 support@commaview.com。"
  - q: "“CommaView 尚不支持您 comma 上的驾驶软件。”"
    a: "您的 comma 运行的软件无法安装 CommaView。[查看支持哪些分支版本](/zh-cn/guides/forks)。如需申请支持您的软件，请复制详细信息并发送到 support@commaview.com。"
  - q: "“CommaView 无法安全地将其画面加入 …”"
    a: "您的分支版本不在 CommaView 的列表中，检查发现它的画面在 CommaView 接入的地方有所不同。您 comma 上没有任何更改。如需申请支持您的分支版本，请复制详细信息并发送到 support@commaview.com。"
  - q: "“不支持 comma 3”"
    a: "CommaView 支持 comma 3X 和 comma four。comma 3 的 openpilot 版本已在上游冻结，画面的绘制方式也不同，因此 CommaView 无法显示它的叠加图层。"
  - q: "“安装后，CommaView 没有在您的 comma 上启动。”"
    a: "请重启 comma，然后重试。如果再次发生，请复制详细信息并发送到 support@commaview.com。"
  - q: "“确认失败。无法连接 192.168.1.50:5002 上的 CommaView API。”"
    a: "安装已完成，但您的手机无法连接到运行环境。请确认手机仍在 comma 的网络中，然后重试。如果电脑能通过 SSH 连接、手机却不行，说明电脑所在的网络手机不在。"
  - q: "“无法兑换配对码。请生成新的配对码后重试。”"
    a: "配对码已过期、已被使用或输入有误。请获取新的（[第 3 步](#step-pair-code)）。"
  - q: "“配对失败：无法连接 CommaView 运行环境 API”"
    a: "您的手机无法通过那个地址连接到 comma。请检查热点或网络，然后重试。"
  - q: "“重启后 CommaView 不会自行启动”"
    a: "CommaView 已安装，但 comma 开机时没有任何东西启动它：您 comma 上的 `/data/continue.sh` 中没有 `exec ./launch_openpilot.sh` 这一行。加上这一行后，请重新安装 CommaView。"
related: [setup, comma-not-found, support-bundle]
---

## 设置经过的各个部分

每个部分都依赖前一个，所以请按这个顺序检查：

1. **SSH**，端口 22：设置登录 comma 进行安装的方式。它需要您的 GitHub 密钥、comma 上的 GitHub 用户名，以及已开启的 SSH。
2. **安装**：comma 下载并安装运行环境。请先看它的结果，再看后面的步骤。
3. **运行环境**，comma 上的端口 5002：设置会检查它是否有响应，然后与它配对。
4. **配对**：一次性配对码让您的手机获得这台 comma 的专属密钥。
5. **视频**，端口 8200 到 8202：Live View 的摄像头画面。

如果搜索找不到 comma，但您知道它的地址，直接输入也一样有效：搜索只是为了方便，能连接上 comma 才是关键。

## 安全

请在车辆挂入 P 挡且 openpilot 未启用时进行设置、安装和故障排除。行驶中切勿设置或操作应用。
