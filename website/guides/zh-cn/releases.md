---
title: "CommaView 的版本发布方式"
description: "CommaView 应用和您 comma 上的运行环境是如何发布的：先是 Alpha，然后是 Beta；经过签名的下载、匹配的运行环境，以及等到挂入 P 挡才进行的更新。"
topic: account
order: 2
kind: reference
lede: "CommaView 由两部分组成，它们会一起更新：Android 应用，以及您 comma 上的小型运行环境。下面介绍一个版本如何送到您手中，以及更新如何保持安全。"
updated: 2026-11-27
steps:
  - id: version
    title: "查看您使用的版本"
    body: |
      设置 › **关于** 会显示应用的版本，以及它是 **已是最新版本**，还是有可用的更新及其版本号。CommaView 会在您的账号中检查是否有新版本，并在新版本就绪时通知您。
    screen: support-about
    pins:
      - target: version
        text: "应用的版本。"
      - target: up-to-date
        text: "**已是最新版本**，或为您准备好的新版本。"
  - id: app-update
    title: "在应用内更新应用"
    body: |
      有新版本就绪时，首页顶部和 **关于** 中会显示 **更新**。**更新 CommaView** 会显示版本号及其渠道：**Beta** 面向所有受邀用户；**Alpha** 则是“面向测试人员的早期版本，可能比 Beta 问题更多。”点按 **下载**：CommaView 会在后台下载并检查，然后由 Android 请您确认安装。
    screen: app-update-offer
    pins:
      - target: channel
        text: "渠道：**Beta** 或 **Alpha**。"
      - target: download
        text: "**下载**。**以后再说** 则留待以后。"
  - id: runtime
    title: "然后更新您 comma 的运行环境"
    body: |
      每个应用版本都会指明与它一起测试过的运行环境。应用更新后，首页会以 **运行环境更新已就绪** 提供那个运行环境。运行环境更新只会从应用中开始，绝不会自行进行。[更新 comma 的运行环境](/zh-cn/guides/update-runtime) 列出了每一步。
    screen: home-runtime-update
    pins:
      - target: update-card
        text: "**运行环境更新**：已安装的和可用的运行环境。"
related: [update-runtime, uninstall, setup]
---

## 先 Alpha，后 Beta

- 每个版本会先以一系列 Alpha 版发给少数测试人员。
- 某个 Alpha 版表现稳定后，它就成为该版本的 Beta 版，发给所有受邀用户。
- 您在 [my.commaview.com](https://my.commaview.com) 的账号总会提供适合您的版本。

## 签名与匹配

- 每个应用下载都是经过签名的正式构建，绝不是调试构建，my.commaview.com 上会在旁边显示它的 SHA-256 校验码。应用在提供安装之前，会先检查下载的更新的大小和校验码：“下载内容与校验码不符，因此未安装。”
- 每个应用版本都会指明与它一起测试过的运行环境，应用会在您的 comma 上安装的正是那一个。
- 旧版应用绝不会被提供未经它测试的运行环境。如果 comma 的运行环境比应用所安装的更新，应用会如实说明：请更新 CommaView，然后重试。

## 安全地更新您的 comma

- 运行环境更新从首页或设备设置开始，绝不会自行进行。
- 更新绝不会打断行程。如果车辆正在行驶，安全更新会先安排更新，等车辆挂入 P 挡且 openpilot 未启用时，comma 再进行安装。您不需要熄火。
- 运行环境更新后，comma 需要重启，CommaView 才能再次推流。应用会提示您重启。
- 您可以随时在设备设置中移除运行环境：[移除 CommaView](/zh-cn/guides/uninstall)。

## 从哪里得到消息

- 有新版本就绪时，应用会通知您。
- [新功能](/whats-new) 列出了每一项变化。
- 有重要变化时我们会发电子邮件给您，您也可以随时从应用中发送反馈（设置 › **支持与诊断**）。
