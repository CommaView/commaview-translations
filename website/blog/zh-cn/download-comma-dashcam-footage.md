---
title: "如何从 comma 设备下载行车录像"
description: "一份实用指南：comma 的视频文件、comma 3/3X/four 之间的差异，以及导出路线录像最稳妥的方法。"
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma 设备视频
  - 行车记录仪录像
  - openpilot 工具
  - SSH
heroLabel: "comma 设备指南"
draft: false
---

需要从 comma 设备上取出视频？常用的途径有 comma connect、Openpilot Toolkit，或直接通过 SSH/SFTP 访问。

让人犯难的是文件结构。comma 设备把 openpilot 路线录成一段段很短的片段，而不是一个巨大的行车记录仪视频。每个片段都可能包含原始摄像头文件、预览视频和路线日志。弄明白这一点之后，导出录像就没那么神秘了。

先说一个重要提醒：comma 设备在道路录像、调试和路线回顾方面很有用，但它不能直接替代专门的行车记录仪。

## comma 设备是有用的摄像头，但不是完美的行车记录仪

专门的行车记录仪是围绕取证设计的：快速启动、碰撞后仍能保存、停车监控、简单的文件导出、可选的后方摄像头，以及可拆卸存储。

comma 设备是为运行 openpilot 而设计的。它录制路线数据，是因为这些数据对驾驶模型、调试、connect 预览和开发很有用。这些录像可能很有价值，但也有取舍：

- 取录像可能比拔出 SD 卡更麻烦
- 碰撞或突然断电可能导致最近的录像丢失
- 停车监控录制不是主要的设计目标
- 不包含朝后拍摄的行车记录仪画面
- 设备需要空间时，会删除旧的本地数据

如果目标是可靠的碰撞录像，请使用真正的行车记录仪。如果目标是 openpilot 路线录像、开发回顾或本地视频导出，那么 comma 的这套流程值得学一学。

## openpilot 会录下哪些文件？

openpilot 官方日志文档把路线描述为一分钟一段的片段。对于每个片段，新版 openpilot 会录下这些类型的文件：

| 文件 | 内容 |
| --- | --- |
| `fcamera.hevc` | 道路摄像头视频，H.265/HEVC |
| `ecamera.hevc` | 广角道路摄像头视频，H.265/HEVC |
| `dcamera.hevc` | 驾驶员/车内摄像头视频，H.265/HEVC |
| `qcamera.ts` | 来自道路摄像头的较低分辨率 H.264 预览 |
| `rlog.zst` | 完整路线日志 |
| `qlog.zst` | 较小的/抽样的路线日志 |

comma connect 中显示的视频是较低分辨率的 `qcamera.ts`。全分辨率的摄像头录像保存在 HEVC 文件中，可能需要通过 connect 手动上传，或直接从设备上复制。

较早的路线、较早的分支版本或较早的文档，可能会显示不带 `.zst` 的 `rlog`/`qlog`，或更早的 `.bz2` 日志文件名。对于当前的 openpilot，请使用上面的文件名。

## comma 3、comma 3X 和 comma four：有什么不同？

人们常把两件事混为一谈：摄像头硬件和文件结构。

摄像头硬件因代际而不同：

| 设备 | 摄像头/存储说明 |
| --- | --- |
| comma 3 | 三个 1080p 摄像头，120 dB HDR。社区文档列出了几种存储版本：1TB、250GB、后期的 64GB 和早期的 32GB。 |
| comma 3X | 与 comma 3 相同的三摄像头布局，升级为 OX03C10 图像传感器，140 dB HDR，通常标注为 128GB 存储。 |
| comma four | comma 称它与 comma 3X 拥有相同的算力、传感器组合和功能，但体积小得多。三摄像头系统装在 1.9 英寸屏幕大小的机身里，包括两个朝向道路的摄像头和一个夜视车内摄像头。comma 标注其存储为 128GB，可保存 10 小时录像。 |

这里关于文件的说明适用于这三款设备。CommaView 本身只支持 comma 3X 和 comma four。

对于当前的 openpilot，各款 comma 硬件的实际文件结构是相同的。新版的片段文件为 `fcamera.hevc`、`ecamera.hevc`、`dcamera.hevc`、`qcamera.ts`、`rlog.zst` 和 `qlog.zst`。

也就是说，摄像头的物理硬件可以变，导出的文件名却保持熟悉。`fcamera.hevc` 是道路摄像头，`ecamera.hevc` 是广角道路摄像头，`dcamera.hevc` 是驾驶员/车内摄像头。

如果您运行的是自定义分支版本，请先在设备上确认，不要想当然地认为每个文件都在。分支版本可能会更改录制设置，而驾驶员/车内摄像头的录制可能取决于设备设置。

## 文件在本地存放在哪里？

在 comma 硬件上，openpilot 当前的日志根目录是：

```text
/data/media/0/realdata
```

在这个文件夹里，每个路线片段都有一个以时间戳命名的文件夹，例如：

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

您要在这个文件夹里查找如下文件：

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

对于直接使用 SSH/SFTP 的流程，就从这个文件夹开始。官方文档说明了如何通过 SSH 连接 comma 3X 或 comma four，而 openpilot 使用 `/data/media/0/realdata` 作为设备上的日志根目录。

## 方法一：使用 comma connect

对于最近的行程，comma connect 通常是最简单的起点。

在以下情况下使用 connect：

- 路线是最近的
- 设备已成功上传该路线
- 预览视频就够用
- 您想用网页界面而不是 SSH
- 您只需要几段短片或几个文件

很多用户也是先在 connect 中找到自己需要的路线和片段编号。问题在于保留期：connect 可能在本地设备删除路线之前就不再显示它。如果 connect 不再显示某条路线，但文件仍在设备上，通过 SSH/SFTP 也许还能找回。

另外请记住，connect 的预览基于 `qcamera.ts`。如果您需要全分辨率的摄像头录像，请确保完整视频文件已上传，或直接拉取原始 HEVC 文件。

## 方法二：使用 Openpilot Toolkit

Openpilot Toolkit 是一款社区工具，可以让本地导出没那么痛苦。它提供 SSH 设置、文件浏览、行程视频预览和原始文件导出等流程。

在以下情况下使用 Openpilot Toolkit：

- 您想要图形界面
- 您不想自己手写 SSH 命令
- 您需要帮助设置密钥
- 您使用的是 Windows 或 Android
- 您想更直接地浏览和导出路线录像

对很多用户来说，这是最好的折中方案：比 connect 更有掌控力，又比手动操作终端省事。

## 方法三：直接使用 SSH 或 SFTP

直接使用 SSH/SFTP 掌控力最强，但也最需要自己动手。

概括来说，SSH 访问通常意味着：

1. 创建或使用一个配置了 SSH 密钥的 GitHub 账号。
2. 在 comma 设备的设置中启用 SSH。
3. 在 comma 设备上输入您的 GitHub 用户名，让它获取您的公钥。
4. 以用户 `comma` 连接端口 `22`。

连接后，从以下位置浏览或复制：

```text
/data/media/0/realdata
```

在以下情况下使用直接访问：

- 您需要原始的 `fcamera.hevc`、`ecamera.hevc` 或 `dcamera.hevc` 文件
- connect 中没有您需要的文件
- 您想存档整条路线
- 您熟悉 FileZilla 或 WinSCP 这类 SFTP 客户端
- 您熟悉 `ssh`、`scp` 或 `rsync`

原始 `.hevc` 文件通常可以用 VLC 播放。如果其他应用需要 MP4，尽量用 ffmpeg 重新封装，而不是重新编码。

## 该用哪种方法？

如果行程是最近的，而普通的路线回顾就够用，请使用 comma connect。

如果您想要更友好的本地流程，而不想手动完成每一步 SSH/SFTP 操作，请使用 Openpilot Toolkit。

如果您需要原始文件、较早的本地文件、完整的路线存档，或想直接控制要复制的内容，请使用 SSH 或 SFTP。

## CommaView 的定位

CommaView 是一款本地优先的 Android 应用，用于 comma 设备的摄像头推流、叠加图层、运行环境设置、录像和回放流程。

它与本地摄像头访问属于同一领域，但它不是 comma connect，不是 Openpilot Toolkit，也不是传统的行车记录仪。它不应被用作驾驶辅助工具，也不应作为车上唯一的取证系统。

CommaView 支持 comma 3X 和 comma four，运行 openpilot 或[支持的分支版本](/forks)：sunnypilot、StarPilot、xnor、AdventurePilot、SunnyPilot-TeslaHW1 或 carrotpilot。comma 3 不受支持：comma 把它转到了一个冻结的长期 openpilot 版本上，CommaView 无法从它的画面绘制叠加图层（[原因](/zh-cn#faq-comma-3)）。

## 延伸阅读

- openpilot 官方日志文档：[Logging](https://docs.comma.ai/concepts/logs/)
- comma 官方 SSH 文档：[连接 comma 3X 或 comma four](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect：[comma.ai/connect](https://comma.ai/connect)
- openpilot wiki：[Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma：[Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit：[项目页面](https://spektor56.github.io/OpenpilotToolkit/)
