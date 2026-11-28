---
title: "发送支持数据包"
description: "保持诊断数据开启，让问题再次出现，然后从设置 › 支持与诊断发送一份附带手机和 comma 日志的反馈。"
topic: troubleshooting
order: 3
kind: walkthrough
lede: "支持数据包是一个小小的 zip 文件，包含 CommaView 应用在您手机上看到的情况，以及它的运行环境在您 comma 上看到的情况。有了它，我们不用坐进您的车里也能找到问题。它只包含日志：没有视频，也没有位置。"
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "诊断数据已开启"
    text: "**在这部手机上保存诊断数据** 默认开启，除非有人关掉了它。请在问题再次出现之前检查一下。"
  - title: "已连接您的 comma"
    text: "要附带 comma 的日志，发送时首页需要显示您的 comma **已连接**。"
  - title: "登录后才能发送"
    text: "发送需要您的 Beta 账号。未登录时，**保存为文件** 仍然可用。"
howItWorks:
  - title: "您的手机"
    text: "保留最近 10 段行程的日志和计数器。"
  - title: "您的 comma"
    text: "在您点按“发送”时加入其运行环境的日志，并移除位置、VIN、各类 ID、Wi‑Fi 名称和令牌。"
    edge: "点按“发送”时"
  - title: "CommaView 团队"
    text: "在私有存储中查看，并通过电子邮件回复。"
steps:
  - id: open
    title: "打开支持与诊断"
    body: |
      在 CommaView 中，点按底部导航栏中的 **设置**。在平板或车机上，它在侧边的侧栏中。点按靠近底部、位于“关于”之前的 **支持与诊断**。
    screen: support-settings
    pins:
      - text: "**支持与诊断**。"
  - id: keep-diagnostics
    title: "在这部手机上保存诊断数据"
    body: |
      **在这部手机上保存诊断数据** 默认开启，除非有人关掉了它：应用会保留最近 10 段行程的日志和计数器，这样报告才能说明发生了什么。如果它是关闭的，请开启它，然后让问题再次出现。
    screen: support-diagnostics
    pins:
      - target: keep-diagnostics
        text: "**在这部手机上保存诊断数据**。"
    note: "诊断数据会一直保留在这部手机上，直到您发送报告：它们绝不会自动上传。"
  - id: happen-again
    title: "在停车时让问题再次出现"
    body: |
      像平时一样连接您的 comma：手机连接 comma 的 Wi‑Fi 或热点，首页显示您的 comma **已连接**。重复出问题的操作；例如打开 Live View，切换到出问题的行车画面，并停留 10 到 20 秒。大致记下发生的时间和您做了什么。录屏也会有帮助。
    warn: "请在挂入 P 挡时重现问题。如果它只在路上出现，就让它发生，停车后再发送报告：记录会等着您。行驶中切勿操作应用。"
  - id: open-send
    title: "打开“发送给 CommaView”"
    body: |
      在 **支持与诊断** 中，点按 **反馈问题或提出建议**。

      也可以从问题本身开始：应用显示失败的地方，点按它的 **反馈**；对于某段录像，在它的 **录像操作** 中选择 **发送给 CommaView…**。它们都会打开同一个面板，并预先填好相关内容。
    screen: support-diagnostics
    pins:
      - target: report
        text: "**反馈问题或提出建议**。"
  - id: send
    title: "选择要附带的内容，然后发送"
    body: |
      选择 **问题**，并描述发生了什么。在 **附件** 下，让 **这部手机的诊断数据** 和您 comma 的日志保持开启。**查看** 会准确显示每一项包含的内容。在这些行下方，面板会列出每份报告都会附带的信息：应用版本、手机型号和 Android 版本，以及您 comma 的驾驶软件和设置。

      点按 **发送**：“正在发送。它会在后台进行，并等待联网。”
    screen: support-send-feedback
    pins:
      - target: problem
        text: "**问题** 或 **想法**。"
      - text: "**附件**：每一行都有一个开关和 **查看**。"
      - target: send
        text: "**发送**。"
    note: "请在应用已连接您的 comma 时发送：它会在您点按“发送”时向 comma 索取日志。如果 comma 已关机或连接不到，数据包会说明原因，并仍然包含应用自己的日志。"
  - id: save-file
    title: "或者保存为文件"
    body: |
      支持人员要的是文件本身，或者您没有登录？请点按 **保存为文件**，而不是“发送”。应用会生成同样的数据包，一个小小的 `.zip`，并打开 Android 的分享面板。把它发送到支持人员要求的地方：Discord 私信、电子邮件或云盘链接。
    screen: support-share-bug-report
    pins:
      - target: save-file
        text: "**保存为文件**。"
  - id: afterwards
    title: "阅读我们的回复"
    body: |
      我们回复时，回复会通过电子邮件发送，也会和您的报告一起出现在 my.commaview.com 的 [Your feedback](https://my.commaview.com/feedback) 中。在我们关闭之前，请在那里回复我们；关闭后 30 天内您还可以重新打开。**支持与诊断** 中的 **您的请求** 也会列出它们。
    screen: support-diagnostics
    pins:
      - target: your-requests
        text: "**您的请求**：回复以及您与 CommaView 的对话。"
check: "面板关闭时显示“正在发送。它会在后台进行，并等待联网。”，发送完成后，报告会出现在 **您的请求** 下。"
fixes:
  - q: "数据包里没有 comma 的日志"
    a: "您点按“发送”时应用连接不到您的 comma，或者 **附件** 下它的那一行是关闭的。打开“发送给 CommaView”之前，请确认首页显示您的 comma **已连接**，并让 comma 那一行保持开启。如果应用要求您重新配对 comma，请先配对，然后再发送一次。"
  - q: "“发送”按钮显示 **登录以发送**"
    a: "您已退出登录。点按它，用您的 Beta 账号登录，或使用 **保存为文件**。"
  - q: "“附件超过一份反馈可携带的 25 MB。请关闭其中一项，或使用‘保存为文件’。”"
    a: "关闭不需要的附件，或点按 **保存为文件**，再把文件发送到支持人员要求的地方。"
  - q: "点按“保存为文件”没有反应"
    a: "这台设备上没有能接收文件的 Android 应用。这在车机上很常见。请改为把它[发送](#step-send)给 CommaView，或从运行 CommaView 的手机上保存。"
  - q: "“无法准备反馈。请检查本地存储空间后重试。”"
    a: "应用无法写入数据包，通常是因为设备存储空间不足。请释放一些空间后重试。"
related: [setup-troubleshooting, comma-not-found, releases]
---

## 支持数据包里有什么

- **这部手机的诊断数据。** CommaView 在这部手机上的诊断日志和计数器：视频流、绘制、连接和录制错误，以及应用版本、手机型号和 Android 版本。使用导航时，还包括每种地点搜索成功或失败的次数，绝不包括您搜索的内容。
- **您 comma 的日志。** 当您 comma 那一行开启时：CommaView 运行环境的日志、计数器和设置，哪些 openpilot 进程停止了及其原因，以及 comma 内核中的内存不足记录。
- **绝不会放进数据包的内容。** 没有视频、没有 GPS 位置、没有 VIN，也没有原始行程遥测数据：您发送的录像会放在数据包旁边，而不是里面。最新的 comma 运行环境在发送日志之前，会移除 GPS 坐标、VIN、Wi‑Fi 名称、公网 IP 地址、令牌和完整的 dongle ID。
- **只在您发送时。** 只有当您点按“发送”或“保存为文件”时，数据包才会离开您的手机。您保存的文件只会去您发送的地方。本地 IP 地址、会话 ID 和版本信息可能仍会保留，所以请只与您信任的人分享数据包。

## 它会去哪里、保留多久

您发送的数据包会进入 CommaView 的私有存储，只有 CommaView 团队能打开。它会在您发送 180 天后删除；如果您提出要求或删除账号，则会提前立即删除（[隐私](/privacy)）。如需提出要求，请发电子邮件至 support@commaview.com。

要删除应用在这部手机上保留的内容，请在 **支持与诊断** 中点按 **清除本地诊断数据**。它绝不会删除您的录像。如果从此只想保留录制错误的历史，请在同一页面关闭 **在这部手机上保存诊断数据**。

不确定发到哪里？请在 [CommaView Discord](https://discord.gg/UuMhz9K8ft) 提问。
