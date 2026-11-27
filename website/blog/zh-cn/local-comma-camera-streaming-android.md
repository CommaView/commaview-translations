---
title: "在 Android 上本地推流 comma 摄像头：CommaView 能做什么"
description: "CommaView 通过您自己的网络，把 comma 的道路摄像头画面连同驾驶叠加图层推流到 Android：Live View、录像、直播，以及它不做的事。"
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma 摄像头推流
  - comma four
  - Android 应用
  - CommaView
  - 本地推流
heroLabel: "产品定位"
draft: false
---

CommaView 通过您自己的网络，把 comma 的道路摄像头画面连同驾驶叠加图层，推流到 Android 手机、平板或车机上。comma 和手机之间没有云端，也不需要先上传任何内容。

它由两部分组成：CommaView 应用，以及 comma 上的一个小型运行环境 `commaviewd`，后者把摄像头画面和驾驶数据提供给应用。引导设置会安装并检查这个运行环境。

## 为什么要推流

comma four 的屏幕只有 1.9 英寸。就它的用途而言，这块屏幕不错，但它很小，车主们也这么说。comma 提供的其他获取视频的方式，是为别的用途设计的：

- **comma connect** 会把上传的行程保留 3 天，开通 comma prime 则保留一年（[comma.ai/prime](https://comma.ai/prime)）。自 [openpilot 0.11.2](https://blog.comma.ai/0112release/) 起，在安装了 comma power 的情况下，它可以在车辆停放时通过互联网直播道路摄像头和车内摄像头画面，并在 comma 上剪出 MP4 短片。
- **SSH** 可以从 comma 的存储中取出原始的一分钟 HEVC 片段。

这两种方式都不能在您行驶时显示带有 openpilot 驾驶叠加图层的道路画面。CommaView 就是为此而做的。

## CommaView 能做什么

### Live View

实时的道路摄像头画面，上面绘制着您的分支版本自己的画面：comma four 的、comma 3X 的，或者 CommaView 自己的样式，把您的车速、最大设定速度（MAX）、限速、前车和变道集中在一个仪表区中。Live View 会按每个分支版本新增的内容来绘制它的画面，从 sunnypilot 的 MADS 到 StarPilot 自己的 HUD。它的帧率最高可达 comma 的每秒 20 帧，并能在画中画模式下继续运行。

在平板或 Android 车机上，CommaView 会以仪表盘的方式布局，Live View 的控件位于驾驶员一侧。

### 录像

在 Live View 中点按 **录制**，停车后，CommaView 会下载 comma 自己录下的那一段视频（最长 10 分钟），并在您的手机上把分支版本的画面绘制上去：这就是回放。您可以播放、分享，或在其他应用中打开它。实时副本会在您行驶时保存 Live View 显示的画面，720p 或 1080p，停车那一刻就能看，没有 10 分钟的限制。录像会一直保存在您的手机上，直到您删除。

### 直播

直播会把 Live View 显示的内容，也就是道路和 CommaView 的叠加图层，以 720p 或 1080p 推流到您的 YouTube 频道或任意 RTMP 服务器。**使用 YouTube 登录** 一次后，它会为您创建、开始和结束每场直播。直播初始为 **不公开列出**；观看的人都能看到您开车经过的地方。

### 仅限已配对的手机

您 comma 的摄像头和数据只会发送到与它配对的手机和车机。视频、行程和地点只会从您的 comma 传到您的手机，不会去别处，除非您主动发送、直播或贡献它们。

## 哪些功能需要互联网

Live View 和录像不需要：它们在同一个本地网络上，直接从 comma 传到您的手机。这个网络可以是您的 Wi‑Fi，也可以是车内由手机、车机、AI 盒子或 comma 开启的热点。登录、应用和运行环境更新、**车辆位置** 中的地图、排行榜、直播以及您发送给 CommaView 的任何内容，则需要互联网。

## 支持哪些设备

comma 3X 和 comma four，运行 openpilot、sunnypilot、StarPilot、xnor-tech 的 openpilot、AdventurePilot、SunnyPilot-TeslaHW1 或 carrotpilot。其他 openpilot 分支版本以尽力支持的方式运行：设置会先检查分支版本，并在安装前征求您的同意。comma 3 不受支持：它运行的是一个已冻结的 openpilot 版本，CommaView 无法从它的画面绘制叠加图层。[支持的分支版本](/forks)。

您需要一部运行 Android 8 或更高版本的 Android 手机、平板或车机。

## CommaView 不是什么

- **不是 comma connect。** 它不会把行程存在云端，也不能让您在城市另一头查看自己的车。这些请用 connect。
- **不是行车记录仪。** 如果您需要可作为证据的碰撞或停车监控录像，[请使用专门的行车记录仪](/zh-cn/blog/is-comma-a-dashcam)。
- **不是驾驶辅助或安全系统。** 它显示的是 comma 看到的内容；以实际路况为准。

## 安全使用

请在停车时设置 CommaView。您开车时，乘客可以观看 Live View；如果您独自驾驶，请像对待 comma 自己的屏幕一样对待它，眼睛始终看着路面。

CommaView 目前处于仅限邀请的 Beta 阶段。[加入名单](https://my.commaview.com/join)，轮到您时我们会发邮件通知您。

CommaView 是非官方软件，与 comma.ai、sunnypilot 或它支持的任何 openpilot 分支版本均无关联，也未获得它们的认可。它是 Beta 软件，不是安全系统：切勿让它分散您的驾驶注意力。
