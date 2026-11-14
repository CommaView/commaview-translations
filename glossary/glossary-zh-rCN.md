# 简体中文（中国大陆）glossary

The words every Simplified Chinese string uses for CommaView's terms, so screens translated apart say the same thing.
Where openpilot already translates a term (`selfdrive/ui/translations/app_zh-CHS.po`, taken from the `v0.10.1` tag:
master no longer has the file), its word is used, so the app says what the car's screen says. The Traditional
Chinese (zh-TW) strings were the model, but the words are mainland ones (软件, 设置, 视频, 登录, 账号, 网络, 信息,
文件, 默认, 屏幕, 应用), not converted characters. Machine drafted; a native speaker's review is owed before release
(the plan).

## Kept as they are

Names are never translated: **CommaView**, **comma** (the device, lower case, as comma writes it), **comma 3X**,
**comma four**, **openpilot**, **sunnypilot**, **dragonpilot**, **carrotpilot**, **StarPilot**, **BluePilot** and the
other forks, **Live View** (the feature's name, as on commaview.com), **Surround**, **Car screen**, **YouTube**,
**Twitch**, **X**, **Stadia Maps**, **OpenStreetMap**, **Buy Me a Coffee**, **GitHub**, **Discord**, **Wi‑Fi**,
**SSH**, **QR**, **Beta**, **Alpha**, units (`km/h`, `mph`, `m`, `ft`, `GB`, `MB`, `fps`). openpilot's .po writes
公里/时 and 英里/时; the app keeps `km/h` and `mph`, as every other language does, because they sit in narrow HUD
pills and match the car's own screen in most forks.

## Style

- Address the person as **您**, as openpilot's translation does.
- Full-width punctuation in Chinese text: ，。、：；？！（）. Quotes are “” (openpilot's), nested ‘’. Ellipsis stays …
- A half-width space between Chinese and a Latin word or number ("在 comma 上", "25.7 GB 可用"), none before or after
  full-width punctuation.
- Buttons are short verbs: 取消, 完成, 保存, 删除, 重试, 继续, 打开, 关闭.
- No trailing 。 on titles, buttons, row titles or pills; whole sentences in body text end with 。.
- Android's own Simplified Chinese words where Android has one: 应用 (not 应用程序), 通知, 权限, 存储空间, 小组件.

## Terms

| English | 简体中文 | Note |
|---|---|---|
| Home (dock) | 首页 | |
| Recordings | 录像 | the section and its saved drives |
| Settings | 设置 | |
| recording, a recording | 录像 | |
| drive (a trip the comma recorded) | 行程 | |
| replay | 回放 | |
| live copy | 实时副本 | |
| saved moment | 保存的片段 | |
| Record | 录制 | the rail's button: a verb, where zh-TW uses 錄影 for both |
| Go live / live streaming | 直播 | |
| onroad screen | 行车画面 | |
| onroad / offroad (the comma's state) | 行驶中 / 停车中 | |
| design (an onroad screen's look) | 样式 | |
| overlay pack | 叠加包 | zh-TW 疊加套件 |
| fork | 分支版本 | "fork" alone when it's openpilot jargon in a sentence for developers |
| runtime (commaviewd) | 运行环境 | |
| update / install / uninstall | 更新 / 安装 / 卸载 | openpilot's |
| reboot | 重启 | openpilot's |
| power off | 关机 | openpilot's |
| pair / pairing | 配对 | openpilot's |
| device (the comma) | 设备 | openpilot's |
| this phone / this device (the device CommaView runs on) | 这部手机 / 这台设备 | `common_this_phone` / `common_this_device`, a sentence's placeholder (how-to-localize.md, "This phone or this device"); both are 这 + measure word + noun, so either fits every sentence |
| your phone / your device (`common_your_*`) | 您的手机 / 您的设备 | no spaces around the placeholder |
| connected / disconnected | 已连接 / 已断开连接 | |
| offline | 离线 | openpilot's |
| engaged / disengaged | 已启用 / 未启用 | openpilot's ACTIVE is 已启用; it shows "脱离" for the act of disengaging |
| override | 驾驶员介入 | |
| experimental mode | 实验模式 | openpilot's |
| driver monitoring | 驾驶员监控 | openpilot's |
| driver camera | 车内摄像头 | openpilot's |
| road camera / wide camera | 道路摄像头 / 广角摄像头 | 摄像头 as openpilot's 车内摄像头 |
| lead car | 前车 | |
| speed limit | 限速 | |
| set speed / MAX | 设定速度 / 最大 | openpilot's MAX is 最大 |
| lane change | 变道 | |
| calibration | 校准 | openpilot's |
| driver position (left/right-hand drive) | 驾驶座位置（左舵／右舵） | |
| daylight contrast | 日光对比度 | |
| offline maps | 离线地图 | |
| navigation | 导航 | |
| Home / Work (places) | 家 / 公司 | |
| vehicle location | 车辆位置 | |
| account / sign in / sign out | 账号 / 登录 / 退出登录 | openpilot's 账号 |
| leaderboard | 排行榜 | |
| achievement | 成就 | |
| privacy | 隐私 | |
| diagnostics | 诊断数据 | |
| report a problem | 反馈问题 | |
| Details (Live View's pane) | 详细信息 | |
| stream health | 推流状态 | |
| storage | 存储空间 | Android's |
| hotspot | 热点 | |
| Live / Delayed (Live View's state) | 实时 / 延迟 | |
| frame pacing | 帧节奏 | |
| inset (a picture in the picture) | 画中画 | |
| framing: Fill / Exact / Extend / Auto | 填满屏幕 / 精确 / 延伸 / 自动 | |
| camera framing | 摄像头取景 | |
| reduce motion | 减少动态效果 | |
| screen edges | 屏幕边缘 | |
| View (Surround's) / chase / high / top-down | 视角 / 追随 / 高处 / 俯视 | |
| vehicle detection / detector / model | 车辆检测 / 检测器 / 检测模型 | |
| renderer | 渲染器 | |
| key (an API key, an SSH key) | 密钥 | openpilot's (SSH 密钥); public / private: 公钥 / 私钥 |
| dashboard (a service's) | 控制台 | |
| reroute | 重新规划路线 | |
| Where to? | 要去哪里？ | |
| map source | 地图来源 | |
| Powered by | 技术支持 | |
| steering / speed active, manual (the HUD's control line) | 转向生效中 / 速度生效中 / 手动控制 | review on a drive |
| steering only / speed only | 仅转向 / 仅速度 | |
| blind spot | 盲区 | |
| green light / lead car moving | 绿灯 / 前车起步 | |
| safe update / install / repair | 安全更新 / 安全安装 / 安全修复 | |
| overlays (drawn on video) | 叠加图层 | not overlay packs (叠加包) |
| telemetry | 遥测数据 | |
| patch | 补丁 | |
| in Park | 挂入 P 挡 | |
| power harness | 常电线 | |
| guided / manual setup | 引导设置 / 手动设置 | |
| boot hook / runtime hook | 开机钩子 / 运行环境钩子 | |
| vehicle security key | 车辆安全密钥 | |
| pair code / invitation | 配对码 / 邀请码 | |
| phones with a key | 持有密钥的手机 | |
| shared token | 共享令牌 | |
| development runtime | 开发版运行环境 | |
| controller | 控制设备 | |
| best effort | 尽力支持 | |
| video only | 仅视频模式 | |
| widgets | 小组件 | Android's |
| backup / restore | 备份 / 恢复 | |
| read-only | 只读 | |
| head unit | 车机 | |
| nearby devices | 附近的设备 | Android's permission |
| display over other apps | 显示在其他应用的上层 | Android's permission |
| set aside (saved lists) | 另行保留 | |
| Not now / Review | 以后再说 / 查看 | openpilot's REVIEW is 查看 |
| queue | 队列 | |
| Needs processing | 待处理 | |
| pull drives | 拉取行程 | |
| whole drive | 完整行程 | |
| export | 导出 | |
| pack studio | 叠加包工作室 | |
| clip | 短片 | |
| log excerpt | 日志摘录 | |
| support bundle | 支持数据包 | |
| Driving insights | 驾驶统计 | |
| contribute | 贡献 | |
| route / segment (openpilot's) | 路线 / 片段 | openpilot's 片段 |
| Privacy & sharing | 隐私与分享 | the Settings page |
| stream key | 推流密钥 | |
| destination (Go live's) | 直播目的地 | |
| Go live | 开始直播 | |
| YouTube Studio | YouTube 工作室 | |
| Auto-start | 自动开始 | |
| Public / Unlisted / Private | 公开 / 不公开列出 / 私享 | YouTube's Simplified Chinese |
| input (microphone) | 输入源 | |
| car hands-free | 车载免提 | |
| metered / monthly limit | 计量 / 每月上限 | openpilot's 计量 |
| Your requests | 您的请求 | |
| Open / Closed (a request) | 处理中 / 已关闭 | |
| license | 许可证 | |
| map library | 地图库 | |
| map theme | 地图主题 | |
| spoken guidance | 语音引导 | |
| dev build | 开发版本 | |
| access pass | 访问通行证 | the account's |
| waitlist | 候补名单 | |
| beta member / admin | Beta 成员 / 管理员 | |
| display name / public name | 显示名称 / 公开名称 | the leaderboard's |
| This week / Last week / Lifetime (the board's periods) | 本周 / 上周 / 累计 | |
| finalized (a week) | 已确定 | |
| badge / share card | 徽章 / 分享卡片 | |
| Official / Community (packs) | 官方 / 社区 | |
| reviewed by CommaView / unreviewed | 经 CommaView 审核 / 未经审核 | |
| Update ready | 可更新 | |
| training collection | 训练数据集 | car detection's; openpilot's 训练数据集 |
| recording metadata | 录像元数据 | |
| SSH identity (a comma's host key) | SSH 身份 | |
| keystore | 密钥库 | Android's |
| repository (a fork's) | 仓库 | |
| driving software | 驾驶软件 | openpilot or a fork, as a message names it |
| put back the way it was (rolled back) | 恢复原状 | |
| QR code | 二维码 | openpilot's; "QR" alone stays where the English has only the letters |
| Wi‑Fi network | Wi‑Fi 网络 | openpilot's |
| cellular | 蜂窝网络 | openpilot's |
| username | 用户名 | openpilot's |
| serial (number) | 序列号 | openpilot's |
