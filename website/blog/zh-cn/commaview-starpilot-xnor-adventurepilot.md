---
title: "CommaView 现已支持 StarPilot、xnor 和 AdventurePilot"
description: "继 0.0.162 支持 StarPilot 之后，CommaView 0.0.163 新增 xnor-tech 的 openpilot 和 AdventurePilot。各个 openpilot 分支版本在 comma 3X 和 comma four 的 Live View 中显示什么。"
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot 分支版本
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "版本说明"
draft: false
---

CommaView 现在支持五种 openpilot 版本：**openpilot**、**sunnypilot**、**StarPilot**、**xnor-tech 的 openpilot**（它的 xnor 和 rx 版本）以及 **AdventurePilot**。StarPilot 在 CommaView 0.0.162 中加入，0.0.163 Beta 又加入了 xnor 和 AdventurePilot。在每一种上，Live View 都会在您的 Android 手机、平板或车机上绘制该分支版本自己的画面，连同它新增的内容。

此前，在这些分支版本上进行设置会停在“unsupported upstream remote”。有了 0.0.163 的应用和配套的运行环境，安装和配对都和在 openpilot 上一样。

## 各分支版本在 Live View 中显示什么

CommaView 不会根据分支版本的名字去猜。您 comma 上的运行环境会告诉应用，这个分支版本在画面上加了什么，应用再把它绘制在 comma four 的画面、comma 3X 的画面或 CommaView 自己的画面上。

| 分支版本 | CommaView 绘制的内容 |
| --- | --- |
| openpilot | comma four 和 comma 3X 的画面，或 CommaView 自己的叠加图层 |
| sunnypilot | sunnypilot 的画面：MADS、限速辅助、彩虹路径、盲区指示，以及它在 comma 3X 上新增的内容 |
| StarPilot | StarPilot 的配色、小组件、警告和摄像头选择 |
| xnor | xnor 版本上是 openpilot 的画面，rx 上是 sunnypilot 的画面，以及 rx 的 Rivian 方向盘着色 |
| AdventurePilot | sunnypilot 的画面，加上它的车道居中指示器、CURVE 标签和转向模式着色 |

## StarPilot

StarPilot 用颜色来表示驾驶模式，CommaView 使用的也是 StarPilot 选定的颜色：它的边框、路径和小组件，它的警告，以及它的摄像头选择，包括车内摄像头。请先关闭 StarPilot 的 **Disable Logging** 设置：它会停用 Live View 推流所依赖的视频编码器。

## xnor-tech 的 openpilot：xnor 和 rx

xnor-tech 的 openpilot 在一个仓库里提供两种版本。它的 **xnor** 分支运行 openpilot 的画面，**rx** 分支运行 sunnypilot 的画面，两者都带有 xnor-tech 的车型适配。CommaView 会判断您的 comma 运行的是哪一种，并绘制对应的画面，警告也和 comma 上显示的一致。

在运行 rx 的 Rivian 上，方向盘会显示车辆的转向方式：按角度转向时为绿色，按扭矩转向时为蓝色。CommaView 在 comma four 的方向盘和 comma 3X 的实验模式按钮上绘制同样的颜色。

## AdventurePilot

AdventurePilot 是一个 sunnypilot 分支版本，带有自己的车型适配。CommaView 绘制 sunnypilot 的画面，再加上 AdventurePilot 新增的内容：

- 它的 **车道居中指示器**：在 comma 3X 画面上是显示推力和偏移的药丸形标签，在 comma four 画面上是一条紧凑的横条；
- comma 3X 画面上的 **CURVE 标签**，在弯道速度控制起作用时闪烁；
- 方向盘上的 **转向模式着色**，以及 Rivian 通过角度通道转向时显示横向加速度的扭矩条。

## 如何获取

CommaView 目前处于仅限邀请的 Beta 阶段。如果您已加入，应用会自动提供 0.0.163 更新。应用更新后，在应用中更新 comma 上的运行环境，然后在提示时重启 comma。运行环境更新会等到车辆挂入 P 挡且 openpilot 未启用时才进行，因此绝不会打断行驶。

第一次使用 CommaView？[设置指南](/zh-cn/guides/setup) 会带您完成应用安装和 comma 连接。

## 没有改变的

- CommaView 支持 **comma 3X** 和 **comma four**。comma 3 仍然不受支持，包括各分支版本的 comma 3 版本，例如 xnor-c3（[原因](/zh-cn#faq-comma-3)）。
- CommaView 绝不会改变分支版本的驾驶方式。它只是在旁边加一个小型运行环境，并在屏幕界面中加一个小钩子，以便绘制同样的路径、车道和警告。
- 在 CommaView 尚未支持的分支版本上，设置会停止，并让您的 comma 保持原样。您可以在 my.commaview.com 的功能看板上申请支持您的分支版本。

## 延伸阅读

- [哪些 openpilot 分支版本支持 CommaView](/forks)，以及各自显示的内容
- 每个版本的[新功能](/whats-new)
- [CommaView 的版本发布方式](/zh-cn/guides/releases)

CommaView 是非官方软件，与 comma.ai、sunnypilot、StarPilot、xnor-tech 或 AdventurePilot 均无关联。它是 Beta 软件，不是安全系统：切勿让它分散您的驾驶注意力。
