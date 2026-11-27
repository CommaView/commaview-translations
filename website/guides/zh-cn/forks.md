---
title: "检查您的 comma 和分支版本是否受支持"
description: "CommaView 支持 openpilot、sunnypilot、StarPilot、xnor、AdventurePilot、SunnyPilot-TeslaHW1、carrotpilot、BluePilot、dragonpilot 和 OPGM，并尽力支持其他分支版本。"
topic: start
order: 2
kind: reference
lede: "CommaView 会显示您 comma 的道路摄像头画面，并叠加它所运行软件的驾驶画面。它支持 comma 3X 和 comma four 上的 openpilot 及其九个分支版本，并尽力支持其他 openpilot 分支版本。设置在做出任何更改之前，会先检查您的 comma 运行的是哪个分支版本。"
updated: 2026-11-27
needs:
  - title: "一台 comma 3X 或 comma four"
    text: "不支持 comma 3，包括各分支版本的 comma 3 版本，例如 xnor-c3。[为什么不支持 comma 3](/#faq-comma-3)。"
  - title: "照常运行的分支版本"
    text: "已安装并照常运行。CommaView 会在它旁边加入运行环境，绝不改变它的驾驶方式。"
steps:
  - id: unlisted
    title: "在 CommaView 未列出的分支版本上，设置会先询问您"
    body: |
      引导设置会检查您 comma 的软件是从哪个仓库安装的，并为该分支版本安装 CommaView 的钩子。在未列出的分支版本上，它会先检查分支版本，不做任何更改。
    tabs:
      - label: "尽力支持"
        body: "如果 CommaView 可以加入它的画面，设置会显示 **CommaView 尚未验证此分支版本**。它会以仓库名称标明分支版本，并说明会绘制什么（摄像头画面、行驶路径、车道线、前车、警报和车速），以及不会绘制什么（分支版本自己的按钮、颜色和小组件）。**仍要安装** 会安装到这个分支版本上，且仅限这一个。**返回** 会回到选择 comma 的步骤；不会安装任何东西。"
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**仍要安装** 会以尽力支持的方式把 CommaView 的画面加入这个分支版本。"
      - label: "仅视频模式（抢先体验）"
        body: "FrogPilot 和 KisaPilot 的画面无法加入 CommaView 的画面，持有“仅视频”标记的测试人员会看到 **此分支版本仅视频模式**：CommaView 推流摄像头画面，并根据驾驶数据绘制自己的画面，不改动分支版本的任何内容。它还没有在 comma 上实际试过。没有该标记时，设置会说明此分支版本不受支持，并且不做任何更改。"
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**安装仅视频模式**。"
    note: "检查拒绝某个分支版本时，设置会显示“CommaView 无法安全地将其画面加入 …”以及“您的 comma 上没有任何更改。”"
  - id: details
    title: "查看 Live View 绘制的是哪个分支版本"
    body: |
      在 Live View 中打开 **详细信息**。**软件** 一行会显示您 comma 的分支版本；CommaView 未列出的分支版本以仓库名称显示，例如“crwusiz/openpilot · best effort”。
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**详细信息**，在画面下方。"
      - text: "**软件**：您的 comma 运行的分支版本。"
related: [setup, overlays, uninstall]
---

## 支持的分支版本

| 分支版本 | 来源 | 开始支持的版本 |
| --- | --- | --- |
| **openpilot** | comma.ai，github.com/commaai/openpilot | 第一个 Beta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | 第一个 Beta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot，原 github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor**（xnor 和 rx 版本） | xnor-tech，github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot，从 i.carrotpilot.app 安装 | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

在未列出的分支版本上，设置会检查 CommaView 能否加入它的画面，并先询问您；如果不能，设置会停止，让您的 comma 保持原样。

## 每个分支版本显示什么

### openpilot

comma.ai 自己的软件。Live View 会绘制 comma four 的画面、comma 3X 的画面或 CommaView 自己的叠加图层，显示您的车速、MAX、限速、前车和变道。

### sunnypilot

CommaView 会绘制 sunnypilot 的画面以及 sunnypilot 新增的内容：MADS 的仅转向和仅速度状态、限速辅助、彩虹路径和盲区指示，在 comma 3X 画面上还有它的限速标志、智能巡航和开发者界面。它会读取您的 sunnypilot 设置，让画面与 comma 上的一致。

### StarPilot

StarPilot 用颜色表示驾驶模式，CommaView 会使用 StarPilot 选定的颜色：comma four 和 comma 3X 画面上的边框、路径和小组件，它的警报，以及它的摄像头选择，包括车内摄像头。

请关闭 StarPilot 的 **Disable Logging** 设置。它会停止 Live View 推流所用的视频编码器。

### xnor-tech 的 openpilot：xnor 和 rx

xnor-tech 的 openpilot 有两种版本。**xnor** 分支运行 openpilot 的画面，**rx** 分支运行 sunnypilot 的画面，两者都带有 xnor-tech 的车型适配。CommaView 会绘制您的 comma 运行的那一种，警报文字与 comma 上的一致。

在运行 rx 的 Rivian 上，车辆按角度转向时方向盘图标显示为绿色，按扭矩转向时显示为蓝色：comma four 上是方向盘图标，comma 3X 画面上则是实验模式按钮的方向盘。

### AdventurePilot

AdventurePilot 是一个带有自己车型适配的 sunnypilot 分支版本。CommaView 会绘制 sunnypilot 的画面以及 AdventurePilot 新增的内容：

- 它的车道居中指示器：comma 3X 画面上是显示推力和偏移的标签，comma four 画面上是紧凑的条形；
- comma 3X 画面上的 CURVE 标记，弯道速度控制起作用时会闪烁；
- 它的转向模式的方向盘色调，以及 Rivian 通过角度通道转向时显示横向加速度的扭矩条。

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 是一个 sunnypilot 分支版本，增加了对 Tesla HW1（Autopilot 1）车辆的支持。它的画面就是 sunnypilot 的，因此 CommaView 会绘制 sunnypilot 的画面及其新增的所有内容，并在应用中显示这个分支版本的名称。

安装了 CommaView 的钩子时，它的 `op fork update` 无法切换分支版本：请先[卸载 CommaView 的运行环境](/zh-cn/guides/uninstall)，或使用 comma 屏幕上的分支版本切换器，它可以照常使用。

### carrotpilot

carrotpilot 是一个面向 Hyundai、Kia 和 Genesis 车辆的 openpilot 分支版本，从 `i.carrotpilot.app` 安装。CommaView 会为它绘制 openpilot 的画面，显示您的车速、行驶路径、车道线和前车。carrotpilot 在自己画面上新增的内容，例如导航、测速摄像头和 HUD，目前还不会绘制。

carrotpilot 的自动更新以及它网页上的 Git 工具会移除 CommaView 的钩子，直到 comma 重启为止。应用会提示您重启，重启后 Live View 就会恢复。

### BluePilot、dragonpilot 和 OPGM

从 CommaView 0.0.166 及其运行环境起列为支持。CommaView 会显示它们各自的名称，并以其基础版本的样式绘制：BluePilot 按 sunnypilot，dragonpilot 和 OPGM 按 openpilot，dragonpilot 的 ALKA 显示为转向。之前以尽力支持方式运行其中之一的 comma，会在运行环境更新后的下次开机时切换过来。它们都还没有搭配 CommaView 实际开过车。CommaView 的官方[叠加包](/zh-cn/guides/overlays)可以绘制更多 BluePilot 和 dragonpilot 自己画面上的内容。

## CommaView 未列出的分支版本

从 CommaView 0.0.165 起，只要您的 comma 上装有其运行环境，设置就能以尽力支持的方式把 CommaView 的画面加入它未列出的 openpilot 分支版本。Live View 会以 openpilot 的样式绘制该分支版本；如果分支版本基于 sunnypilot 的画面，则以 sunnypilot 的样式绘制。要撤销，设备设置中的 **卸载运行环境** 会把分支版本的文件恢复原状。

- **尽力支持。** CommaView 的版本没有针对您的分支版本进行检查。如果分支版本自行更新成 CommaView 无法跟上的样子，CommaView 的画面会关闭，您的分支版本照常驾驶并显示自己的画面，直到有 CommaView 版本处理了这项变化。
- **并非所有分支版本都可以。** 基于 openpilot 旧版原生画面的分支版本不受支持（见下文）。
- **您的同意只针对该分支版本。** 如果您的 comma 换成了另一个 CommaView 未列出的分支版本，CommaView 会在设置中再次询问您，然后才把画面加入那里。

### 通过安装检查的分支版本（尽力支持）

以下每一个都**通过了 CommaView 的安装检查；尽力支持，未在车上测试。** 检查于 2026 年 11 月进行，针对所列分支，使用 CommaView 0.0.165 安装的运行环境：安装程序会提供该分支版本，在您同意后加入 CommaView 的画面并进行检查，就像在您的 comma 上一样。这里没有任何一项在车里的 comma 上试过，分支版本也不一定在两种设备上都支持所有车型，而且分支版本的下一次更新可能改变结果。

| 分支版本 | 检查的分支 | 设备 | 绘制样式 |
| --- | --- | --- | --- |
| **crwusiz**（github.com/crwusiz/openpilot） | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **jixiexiaoge’s Carrot**（github.com/jixiexiaoge/openpilot） | Carrot | comma four, comma 3X | openpilot |
| **MoreTore**（github.com/MoreTore/openpilot） | release-mici | comma four | openpilot |
| **zoompilot**（github.com/zoompilot/zoompilot） | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato**（github.com/AlexandreSato/openpilot） | master | comma four, comma 3X | openpilot |
| **lukasloetkolben**（github.com/lukasloetkolben/openpilot） | master | comma four, comma 3X | openpilot |
| **mvl-boston**（github.com/mvl-boston/openpilot） | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub**（github.com/mouxangithub/openpilot） | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro**（github.com/programanichiro/openpilot） | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2**（github.com/infiniteCable2/openpilot） | master | comma four, comma 3X | sunnypilot |
| **herizon1054**（github.com/herizon1054/openpilot） | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot**（github.com/NotAutopilot/openpilot） | nap-release, naponsp-alpha | comma four, comma 3X | openpilot（nap-release），sunnypilot（naponsp-alpha） |

您的分支版本不在这里？它仍可能可以使用：设置在做出任何更改之前都会先检查它。

### 不受支持

这些分支版本的画面无法加入 CommaView 的画面，所以设置会如实说明，并且不改动您 comma 上的任何内容：

- **FrogPilot**（github.com/FrogAi/FrogPilot）。它运行 openpilot 旧版的原生（Qt）画面，没有加入 CommaView 画面的位置。仅视频模式正在抢先体验中。
- **KisaPilot**（github.com/kisapilot/openpilot）。它的 Python 画面已关闭：运行的是 openpilot 旧版的原生（Qt）画面。仅视频模式正在抢先体验中。
- **IQ.Pilot**（github.com/IQLvbs/iqpilot）。自 2026 年 10 月起，它运行在自己的 IQ.OS 上；要等 CommaView 能把它作为独立的分支版本来支持。
- **hikee9123**（github.com/hikee9123/openpilot）。它运行 openpilot 旧版的原生（Qt）画面。

**抢先体验：FrogPilot 和 KisaPilot 的仅视频模式。** 持有“仅视频”标记时，设置会提供在 Live View 中播放它们的摄像头画面，并用 CommaView 自己的叠加图层代替它们的画面，不改动分支版本的任何内容。它还没有在 comma 上实际试过。没有该标记时，设置仍会说明它们不受支持，并且不做任何更改。

## 支持哪些 comma 设备

comma 3X 和 comma four。不支持 comma 3，包括各分支版本的 comma 3 版本，例如 xnor-c3：[为什么不支持 comma 3](/#faq-comma-3)。应用可在 Android 手机、平板或车机上运行。

## 正式版与开发分支

每次发布前，CommaView 的运行环境都会针对这些分支版本的正式版构建进行构建和检查。openpilot 的 nightly 和 sunnypilot 的 dev 分支在每次有变化的当天都会检查，作为预警。开发分支的变化可能比 CommaView 更快：如果某项变化让 CommaView 的钩子无法加载，您的分支版本的画面和驾驶都会照常进行。

## 您的分支版本没有列出？

可以先以尽力支持的方式试用，并在 [my.commaview.com](https://my.commaview.com) 的功能建议板上请求列入，或从应用中提出建议（设置 › **支持与诊断**）。列出的分支版本在每次发布前都会经过检查。每个版本的变化请见[新功能](/whats-new)。

## 常见问题

**CommaView 会改变我的分支版本的驾驶方式吗？** 不会。它只是在您的分支版本旁加入一个小型运行环境，并在其屏幕界面中加入一个小钩子，好让 CommaView 绘制同样的路径、车道线和警报。您车辆的驾驶方式不会改变。

**CommaView 支持 StarPilot 吗？** 支持，从 CommaView 0.0.162 起。Live View 会显示 StarPilot 自己的颜色、小组件和摄像头选择。请关闭 StarPilot 的 **Disable Logging** 设置，它会停止 CommaView 推流所用的视频编码器。

**CommaView 支持 carrotpilot 吗？** 支持，从 CommaView 0.0.164 起。Live View 会为它绘制 openpilot 的画面；carrotpilot 在自己画面上新增的内容，例如导航和测速摄像头，目前还不会绘制。carrotpilot 自行更新后，应用会提示重启，重启后 Live View 就会恢复。

**CommaView 支持 FrogPilot 吗？** 暂时不支持：它运行 openpilot 旧版的原生（Qt）画面，没有加入 CommaView 画面的位置，所以设置会说明它不受支持，并且不做任何更改。FrogPilot 和 KisaPilot 的仅视频模式正在面向测试人员抢先体验。
