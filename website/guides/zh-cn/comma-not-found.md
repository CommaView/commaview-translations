---
title: "CommaView 找不到您的 comma"
description: "首页显示“离线”，或 Live View 连接不到您的 comma？请依次检查网络、comma 的地址和配对。"
topic: troubleshooting
order: 2
kind: fixes
lede: "CommaView 通过本地网络直接与您的 comma 通信，中间没有任何云服务。找不到它时，几乎总是因为手机和 comma 不在同一个网络中、车辆熄火后 comma 进入了休眠，或者它的地址变了。请先检查这几项，再检查配对。"
parked: true
updated: 2026-11-27
needs:
  - title: "车辆已通电"
    text: "车辆熄火时 comma 会进入休眠。请让车辆通电并挂入 P 挡。"
  - title: "同一个网络"
    text: "您的手机与 comma 连接同一个 Wi‑Fi，或连接它的热点。在车上：[在车上连接](/zh-cn/guides/connect-in-the-car)。"
steps:
  - id: home
    title: "看看首页显示什么"
    body: |
      手机连接不到 comma 时，首页会显示它 **离线**，并提供 **重新连接** 和一张 **无法连接？** 卡片：“这部手机必须与 comma 连接同一个 Wi‑Fi，或连接它的热点。车辆熄火时 comma 会进入休眠。”

      检查这两项，然后点按 **重新连接**。
    screen: home-cant-connect
    pins:
      - target: reconnect
        text: "**重新连接**。"
      - target: cant-connect
        text: "**无法连接？** 卡片。"
  - id: live-view
    title: "在 Live View 中：等待或重试"
    body: |
      Live View 会说明它停止的原因。**连接不到这台 comma** 表示您的手机无法在网络中找到它。comma 响应后它会自行重新连接；**重试** 会立即再试一次。
    screen: phone-live-view-unreachable
    pins:
      - target: cant-reach
        text: "**连接不到这台 comma**：Live View 停止的原因。"
      - target: retry
        text: "**重试**。"
  - id: network
    title: "检查手机的网络"
    body: |
      打开手机的 Wi‑Fi 设置，确认它连接的是 comma 所在的网络：同一个家庭 Wi‑Fi、已让 comma 加入的手机热点，或 comma 自己的热点。

      - 手机如果因为某个 Wi‑Fi 不能上网而改用移动数据，就无法连接 comma。请重新连接那个 Wi‑Fi。
      - 手机上的 VPN 可能会把流量转发到别处。请关闭它再试一次。
      - 有些热点会阻止连接的设备互相访问。请换一个网络试试，例如 comma 自己的热点。
    note: "Android 的 Wi‑Fi 和热点设置没有配图：每部手机看起来都不一样。"
  - id: address
    title: "检查 comma 的地址"
    body: |
      comma 加入其他网络，或路由器给它分配新地址时，它的地址就会改变。CommaView 在网络中看到它时会自行重新找到它；如果没有找到，请自己保存它的地址。

      在 comma 上，到 **设置 → 网络** 中找到它的 IP 地址。在 CommaView 中，从首页打开 **设备设置**，点按 **更改名称或地址**，然后编辑 **IP 地址**，输入 comma 的地址，再点按 **保存**。
    screen: device-name-address
    pins:
      - target: comma-ip
        text: "comma 的 IP 地址。"
      - target: save
        text: "**保存**。"
  - id: add
    title: "还是找不到？重新添加"
    body: |
      在首页点按 **添加 comma**。**在此网络中** 会列出手机所在网络中运行 CommaView 的 comma：点按您的那台。如果没有，请点按 **输入地址和配对码**，或在已与它配对的手机上使用 **扫描二维码**。
    screen: add-comma
    pins:
      - target: found-comma
        text: "**在此网络中**：在附近找到的 comma。"
      - target: enter-address
        text: "**输入地址和配对码**。"
      - target: scan-qr
        text: "**扫描二维码**。"
  - id: pair
    title: "用它的地址和新的代码配对"
    body: |
      输入 comma 的 IP，以及配对码或邀请码，然后点按 **配对 comma**。代码很快就会过期：已与 comma 配对的手机可以在 **设备设置** 的 **配对另一部手机或平板** 下显示新的代码。
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "comma 的 IP。"
      - target: pair-code
        text: "**配对码或邀请码**。"
      - target: pair
        text: "**配对 comma**。"
    note: "如果输入地址可以连接，但 comma 从不自动出现，说明网络屏蔽了 CommaView 的搜索功能。这没关系：关键是地址。"
check: "首页显示您的 comma **已连接**，点按 **打开 Live View** 可以看到画面。"
fixes:
  - q: "“连接不到这台 comma”"
    a: "您的手机必须与 comma 连接同一个 Wi‑Fi，或连接它的热点。comma 响应后 Live View 会重新连接。请检查网络（[第 3 步](#step-network)）和 comma 的地址（[第 4 步](#step-address)）。"
  - q: "“CommaView 没有响应”"
    a: "comma 有响应，但它上面的 CommaView 没有。它可能正在 comma 上重启：恢复后 Live View 会重新连接。如果一直如此，请在停车时重启 comma。"
  - q: "“这台 comma 没有视频”"
    a: "它有响应，但视频没有传回来。请重试，或返回检查 comma：openpilot 可能还在启动。"
  - q: "“Live View 已在另一台设备上打开”"
    a: "这台 comma 一次只向一部手机或一台车机推流。在另一台设备的 CommaView 中回到首页，这里的 Live View 就会自行开始。"
  - q: "“comma 没有及时响应。”"
    a: "连接信号弱或网络繁忙。请确认手机连接的是 comma 的 Wi‑Fi 或热点，尽量靠近一些，然后重试。"
  - q: "“comma 拒绝了连接。CommaView 可能正在它上面重启。”"
    a: "稍等片刻让它恢复，然后重试。"
  - q: "“收不到车辆数据”"
    a: "视频能收到，但车速、信号和警报收不到。重启 comma 即可解决。"
  - q: "“配对失败：配对码已过期。请生成新的配对码后重试。”"
    a: "请在已与 comma 配对的手机上，从 **设备设置 › 配对另一部手机或平板** 获取新的代码，然后重新配对。"
  - q: "“配对失败：配对码无效。请检查配对码或扫描二维码。”"
    a: "请检查您输入的代码（连字符可省略），或改为扫描它的二维码。"
  - q: "“更新这台 comma 的运行环境”或“更新 CommaView”"
    a: "此应用与 comma 的运行环境版本相差太大，无法通信。请更新它提到的那一项：从设备设置更新运行环境（[更新运行环境](/zh-cn/guides/update-runtime)），或更新应用。"
  - q: "“无法读取您已保存的 comma”"
    a: "无法读取这部手机上已保存的 comma，所以一台都没有显示。它们并没有被删除。请重试，或点按 **重新开始** 并重新配对每台 comma：旧列表会保留至少 90 天。"
related: [connect-in-the-car, setup-troubleshooting, another-phone]
---

## CommaView 如何找到 comma

- **搜索**：在手机所在的网络中查找运行 CommaView 的 comma，这样您就不必输入地址。有些网络会屏蔽搜索。
- **地址**：CommaView 实际连接的目标。无论搜索是否有效，输入地址都能连接。
- **配对**：用一组短时有效的代码，让您的手机获得这台 comma 的专属密钥。搜索和配对是两回事：手机能连接到的 comma 仍然需要配对。
- **已保存的 comma**：CommaView 通过它的身份而不只是地址来识别它，所以当它以新地址出现时，CommaView 会更新已保存的那台。

## 安全

请在停车时检查网络和配对。行驶中请勿操作 CommaView。
