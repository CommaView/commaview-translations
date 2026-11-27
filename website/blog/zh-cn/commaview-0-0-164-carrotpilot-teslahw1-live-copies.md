---
title: "CommaView 0.0.164：carrotpilot、SunnyPilot-TeslaHW1 和实时副本"
description: "CommaView 0.0.164 新增 carrotpilot 和 SunnyPilot-TeslaHW1，以及在行驶中保存 Live View 画面的实时副本。另外，导航和 Surround 开放抢先体验。"
date: 2026-10-22
slug: commaview-0-0-164-carrotpilot-teslahw1-live-copies
tags:
  - openpilot 分支版本
  - carrotpilot
  - SunnyPilot-TeslaHW1
  - Tesla
  - Hyundai
  - 录像
heroLabel: "版本说明"
draft: false
---

CommaView 0.0.164 已向 Beta 的所有成员推出。它新增了两个 openpilot 分支版本 **carrotpilot** 和 **SunnyPilot-TeslaHW1**，因此 CommaView 现在支持七种：openpilot、sunnypilot、StarPilot、xnor-tech 的 openpilot、AdventurePilot、SunnyPilot-TeslaHW1 和 carrotpilot。它还带来了 **实时副本**：在您行驶时保存 Live View 显示的画面，停车的那一刻就能看。

它配套运行环境 `v0.0.60-beta`，可以识别这两个新的分支版本。应用提示时，请在应用中更新运行环境，并在应用要求时重启 comma。

## SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 是一个 sunnypilot 分支版本，增加了对 Tesla HW1（Autopilot 1）车型的支持。它的画面就是 sunnypilot 的画面，所以 CommaView 会绘制 sunnypilot 的画面以及 sunnypilot 新增的全部内容，并在应用中显示这个分支版本的名称。

有一点需要注意：安装了 CommaView 的钩子时，它的 `op fork update` 无法切换分支版本。请先卸载 CommaView，或使用 comma 屏幕上的分支版本切换器，它照常可用。

## carrotpilot

carrotpilot 是一个面向现代、起亚和捷尼赛思车型的 openpilot 分支版本，从 `i.carrotpilot.app` 安装。CommaView 为它绘制 openpilot 的画面，包括您的车速、路径、车道和前车，并在应用中显示这个分支版本的名称。

目前有两点限制：

- **carrotpilot 自己的画面还不会绘制。** 它在 openpilot 画面上新增的内容，例如导航、测速摄像头和 HUD，不会显示在 Live View 中。
- **它的更新会移除 CommaView 的钩子，直到 comma 重启。** carrotpilot 的自动更新以及它网页上的 Git 工具，会在运行时重置它的文件。不会有任何损坏：应用会请求重启，重启后 Live View 就会恢复。

## 实时副本

此前，**录制** 生成的是回放：停车后，应用下载 comma 自己的视频，并在上面绘制 HUD。这仍然是画质最好的方式，但行程结束后要等一会儿，而且每段录像最长 10 分钟。

现在可以在 设置 › 录像 › **在 Live View 中录制** 中选择 **录制** 生成什么：

| 选项 | 您得到的内容 |
| --- | --- |
| **回放**（默认） | comma 自己的视频，上面绘制着 HUD，停车后生成。画质最好，每段录像最长 10 分钟。 |
| **实时副本** | 您行驶时 Live View 显示的画面，保存在手机上，停车那一刻就出现在“录像”中，没有 10 分钟的限制。 |
| **两者** | 现在得到实时副本，行程结束后再得到回放。 |

实时副本为 720p（每小时约 1.4 GB）或 1080p（每小时约 2.3 GB），每秒 20 帧。切换应用或锁定手机时它会继续录制，并显示一条通知，您可以从通知中停止。手机存储空间用完之前，它会妥善停止；如果录制时应用关闭，除了最后一分钟，其余内容都会保留。

实时副本保存在您的手机上，绝不会上传。

## 0.0.164 的其他改进

- **设置页面用满整个屏幕。** **录像**、**显示** 和 **直播** 的布局与 **离线地图** 一致，空间足够时分为两栏，在平板、车机和横握的手机上排列整齐。
- **安装失败的原因。** 如果设置、运行环境更新或卸载失败，应用会说明出了什么问题以及该怎么做：CommaView 不支持的分支版本、车辆正在行驶、comma 没有网络、下载内容损坏。它会告诉您 comma 是否已恢复原状，**复制详细信息** 会复制支持人员需要的报告。
- **回放更快。** 回放只下载它要显示的视频，而且在制作一段回放时，队列中的下一段行程会同时下载。因应用关闭、10 分钟限制或车辆熄火而中断的录像，现在也可以制作成回放。
- **回放画质设置恢复正常。** Balanced、High 和 Max 又会生成不同的回放了：此前所有回放都以同样的 40 Mbit/s 生成。默认的 High 现在在 comma 3X 上生成的文件大小约为原来的一半。

## 抢先体验：导航和 Surround

部分功能还处于早期开发阶段：**导航**、**Surround**、**直播** 和 **发送给 CommaView**。我们通过功能开关向一小部分测试者开放，同时收集反馈，因此只有开启了这些功能的账号才能看到。

- **导航** 提供从首页到 Live View 的逐向引导：搜索地点、选择路线，然后跟随转向卡片、语音提示，以及在 CommaView 画面上绘制在您车道里的箭头。走错路口后，几秒内就会找到新路线。它只用于显示：不会向您的 comma 或车辆发送任何内容。
- **Surround** 是车辆周围道路的 3D 视图：摄像头看到的道路及其车道线和路口，以及您周围的汽车、卡车和红绿灯。

其中一些功能依赖付费服务，例如导航的路线规划，所以在弄清正常使用的成本之前，我们会保持小范围测试。如果您愿意帮忙测试，请在我们的 [Discord](https://discord.gg/UuMhz9K8ft) 上联系我们，并准备好告诉我们它们在您的行程中表现如何。

## 如何获取

CommaView 目前处于仅限邀请的 Beta 阶段。如果您已加入，应用会自动提供 0.0.164 更新。更新后，在应用中更新 comma 上的运行环境，然后在提示时重启 comma。运行环境更新会等到车辆挂入 P 挡且 openpilot 未启用时才进行，因此绝不会打断行驶。

第一次使用 CommaView？[设置指南](/zh-cn/guides/setup) 会带您完成应用安装和 comma 连接。

## 延伸阅读

- [哪些 openpilot 分支版本支持 CommaView](/forks)，包括 [SunnyPilot-TeslaHW1](/forks#teslahw1) 和 [carrotpilot](/forks#carrotpilot)
- 每个版本的[新功能](/whats-new)
- [CommaView 的版本发布方式](/zh-cn/guides/releases)

CommaView 是非官方软件，与 comma.ai、sunnypilot、carrotpilot 或 SunnyPilot-TeslaHW1 均无关联。它是 Beta 软件，不是安全系统：切勿让它分散您的驾驶注意力。
