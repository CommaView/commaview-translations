---
title: "comma connect 还是本地视频：哪个能满足您的需要？"
description: "openpilot 0.11.2 之后，comma connect、SSH 和 CommaView 的对比：停车直播、短片、行程保留期、画质、隐私，以及各自的用途。"
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - 本地视频访问
  - comma four
  - CommaView
heroLabel: "选择指南"
draft: false
---

comma connect 是 comma 自己的网页应用，大多数车主都会先在这里查看自己的行程，而且对很多事情来说，它就是正确的地方。自 openpilot 0.11.2 起，它能做的比以前更多：可以直播停放中的车辆，也可以在设备上剪出 MP4 短片。本地访问，无论是通过 SSH 还是 CommaView，做的是另一件事：在您自己的网络上，直接从 comma 获取视频。

简短的回答：

- **在任何地方查看最近的一段行程：** comma connect。
- **车辆停放时查看车辆情况：** comma connect 的直播。
- **开车时在更大的屏幕上观看带有分支版本驾驶叠加图层的道路画面：** CommaView 的 Live View。
- **用于开发或存档的原始摄像头文件：** SSH。
- **在手机上得到一段您刚刚看到的、带叠加图层的短片，无需上传：** CommaView 的 **录制**。

## comma connect 能做什么

**它会把您的行程在云端保存一段时间。** comma 的 [prime 页面](https://comma.ai/prime) 说，录像“会上传到 connect，并在那里保存 3 天”。开通 comma prime（每月 24 美元，仅限美国，含流量）或 prime lite（每月 14 美元，如需蜂窝网络请自备 SIM 卡）后，connect 会保存一年。

**它默认显示的是小尺寸视频。** comma 的[日志文档](https://docs.comma.ai/concepts/logs/) 说，connect 中的视频来自 qcamera 文件，即“fcamera.hevc 的低分辨率版本”，这些文件是为了在慢速网络上快速上传而制作的。全分辨率的 HEVC 文件会留在 comma 上，除非您也上传它们。

**自 0.11.2 起，它可以直播停放中的车辆。** [0.11.2 的发布文章](https://blog.comma.ai/0112release/)（2026 年 10 月 23 日）说，在有互联网连接（“家里的 Wi‑Fi 或 comma prime 的 LTE”）并安装了 comma power 的情况下，“您可以直播道路摄像头和车内摄像头，在车辆停放时查看周围发生的情况。”您可以在任何地方通过 connect 观看。

**它也能剪短片。** 同一版本在 connect 中加入了短片按钮：选取行程的一部分，“您的 comma 会把它拼接并重新编码为兼容性广泛的 MP4（H.264）。”在它处理期间让 comma 保持开机，然后从 connect 下载短片。

这是实实在在的进步。如果您想在办公桌前看看停着的车，或者把昨晚行程的一段短片发给朋友，现在 connect 两样都能做到。

## comma connect 不做什么

- **它不能在您行驶时直播。** 直播是给停放中的车辆用的。
- **它不会绘制 openpilot 的驾驶叠加图层。** 直播和短片都是摄像头视频，没有您在 comma 屏幕上看到的路径、车道、警告或车速。
- **它需要互联网。** 直播需要家里的 Wi‑Fi 或 prime 的 LTE，行程也必须先上传，connect 才能显示。
- **没有 prime 时，3 天后它就不再保留。** 之后 connect 就不再显示这段行程，即使 comma 上还有。

这些都不是缺陷。connect 是一项云服务，让您无论身在何处都能查看自己的车和行程。

## 本地访问能做什么

本地访问是指在同一个网络上，直接从 comma 本身获取视频，而不是从 comma 的服务器获取。

### SSH：原始文件

每段 openpilot 行程都以一分钟为单位的片段保存在 comma 上，每个片段都有自己的文件：`fcamera.hevc`（道路）、`ecamera.hevc`（广角道路）、`dcamera.hevc`（驾驶员）、`qcamera.ts`（小尺寸预览）以及日志。通过 SSH，只要 comma 上还有，您可以复制其中任何一个；空间不足时，comma 会删除最早的行程。这是获取全分辨率视频用于开发或个人存档的方法，但得到的是一分钟长的 HEVC 文件，而不是可以直接分享的短片。我们的[下载 comma 录像](/zh-cn/blog/download-comma-dashcam-footage)指南会一步步说明。

### CommaView：Android 上的 Live View 和录像

CommaView 是一款 Android 应用，外加 comma 上的一个小型运行环境 `commaviewd`，它通过您自己的本地网络把摄像头画面和驾驶数据发送到您的手机：可以是您的 Wi‑Fi，也可以是车内的热点，无论是手机、车机还是 comma 开的热点。

- **开车时的 Live View。** 道路摄像头画面上绘制着您的分支版本自己的画面，与 comma four 或 comma 3X 上绘制的一样，或者是 CommaView 自己的样式，显示在手机、仪表台上的平板或 Android 车机上。comma four 的屏幕是 1.9 英寸；您手机的屏幕要大得多。
- **保存在手机上的录像。** 在 Live View 中点按 **录制**，停车后，CommaView 会下载 comma 自己录下的那一段视频（最长 10 分钟），并在手机上把分支版本的画面绘制上去。或者保存 Live View 所显示画面的实时副本，720p 或 1080p，没有 10 分钟的限制。您可以播放、分享，或在其他应用中打开它。
- **直播。** 把 Live View 显示的内容，也就是道路和叠加图层，以 720p 或 1080p 推流到您的 YouTube 频道或任意 RTMP 服务器。
- **无需订阅，无需上传。** Live View 和录像从您的 comma 传到您的手机，录像会一直保存在那里，直到您删除。您 comma 的摄像头只会发送到与它配对的手机和车机。

它支持 comma 3X 和 comma four，运行 openpilot、sunnypilot、StarPilot、xnor、AdventurePilot、SunnyPilot-TeslaHW1 或 carrotpilot，其他分支版本则以尽力支持的方式运行。[支持哪些分支版本，以及 Live View 在各分支版本上绘制什么](/forks)。

## 并排对比

| 功能 | comma connect | CommaView |
| --- | --- | --- |
| 实时视频 | 道路和车内摄像头，车辆停放时 | 道路摄像头，行驶时 |
| 驾驶叠加图层 | 无 | 您的分支版本的画面，或 CommaView 的样式 |
| 视频去向 | 经由互联网，在 connect 中观看 | 您自己的本地网络（Wi‑Fi 或热点），发送到已配对的手机 |
| 需要 | 互联网；直播还需要 comma power | 同一网络上的 Android 手机、平板或车机 |
| 短片 | 行程的任意部分，在 comma 上剪成 MP4，从 connect 下载 | 您在 Live View 中录制的内容：最长 10 分钟的回放，或实时副本，带叠加图层 |
| 行程保存多久 | 3 天，开通 prime 后一年 | 在您的手机上，直到您删除 |
| 费用 | 免费，或 prime 每月 24 美元 / lite 每月 14 美元 | 无需订阅；CommaView 目前处于仅限邀请的 Beta 阶段 |

## 两者都用

它们并不是在争夺同一份工作。用 connect 随时随地查看车辆、把想要的行程存到云端；用 CommaView 在更大的屏幕上观看带有分支版本叠加图层的道路画面、录下您看到的内容并进行直播。您开车时，乘客可以观看 Live View；如果您独自驾驶，请像对待 comma 自己的屏幕一样对待它，眼睛始终看着路面。

## 延伸阅读

- [comma prime](https://comma.ai/prime)：connect 的套餐以及行程保存时长
- [openpilot 0.11.2](https://blog.comma.ai/0112release/)：直播和短片功能
- [如何下载 comma 录像](/zh-cn/blog/download-comma-dashcam-footage)：通过 SSH
- [设置 CommaView](/zh-cn/guides/setup)

CommaView 是非官方软件，与 comma.ai、sunnypilot 或它支持的任何 openpilot 分支版本均无关联，也未获得它们的认可。它是 Beta 软件，不是安全系统：切勿让它分散您的驾驶注意力。
