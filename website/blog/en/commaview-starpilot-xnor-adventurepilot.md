---
title: "CommaView now works with StarPilot, xnor and AdventurePilot"
description: "CommaView 0.0.163 adds xnor-tech's openpilot and AdventurePilot, after StarPilot in 0.0.162. What each openpilot fork shows in Live View on the comma 3X and comma four."
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "Release notes"
draft: false
---

CommaView now works with five openpilot builds: **openpilot**, **sunnypilot**, **StarPilot**, **xnor-tech's openpilot** (its xnor and rx builds) and **AdventurePilot**. StarPilot arrived in CommaView 0.0.162, and the 0.0.163 beta adds xnor and AdventurePilot. On each one, Live View draws the fork's own screen on your Android phone, tablet or head unit, with what that fork adds to it.

Until now, setup on these forks stopped with "unsupported upstream remote". With the 0.0.163 app and its runtime, it installs and pairs as it does on openpilot.

## What each fork shows in Live View

CommaView doesn't guess from the fork's name. The runtime on your comma tells the app what the fork's screen adds, and the app draws it on the comma four's screen, the comma 3X's, or CommaView's own.

| Fork | What CommaView draws |
| --- | --- |
| openpilot | The comma four and comma 3X screens, or CommaView's own overlay |
| sunnypilot | sunnypilot's screen: MADS, speed-limit assist, the rainbow path, blind-spot indicators, and its comma 3X additions |
| StarPilot | StarPilot's colours, widgets, alerts and camera choice |
| xnor | openpilot's screen on the xnor builds, sunnypilot's on rx, and rx's Rivian wheel tint |
| AdventurePilot | sunnypilot's screen with its lane-centering indicator, CURVE chip and steering mode tint |

## StarPilot

StarPilot shows its driving modes through colour, and CommaView uses the colours StarPilot chose: its border, path and widgets, its alerts, and its camera choice, including the driver camera. Turn off StarPilot's **Disable Logging** setting first: it stops the video encoder Live View streams from.

## xnor-tech's openpilot: xnor and rx

xnor-tech's openpilot comes in two builds from one repository. Its **xnor** branches run openpilot's screen and its **rx** branches run sunnypilot's, each with xnor-tech's car ports. CommaView works out which one your comma runs and draws that screen, with its alerts as the comma writes them.

On a Rivian running rx, the wheel shows how the car is steering: green while it steers by angle, blue while it steers by torque. CommaView draws the same colours on the comma four's wheel and on the comma 3X's experimental mode button.

## AdventurePilot

AdventurePilot is a sunnypilot fork with its own car ports. CommaView draws sunnypilot's screen with what AdventurePilot adds:

- its **lane-centering indicator**, a pill with the push and offset on the comma 3X screen and a compact bar on the comma four's;
- the **CURVE chip** on the comma 3X screen, which blinks while curve speed control acts;
- its **steering mode tint** on the wheel, and a torque bar that shows lateral acceleration while a Rivian steers on its angle channel.

## How to get it

CommaView is in an invite-only beta. If you're in, the app offers the 0.0.163 update on its own. After the app updates, update the runtime on your comma from the app, then reboot the comma when it asks. Runtime updates wait until the car is in Park with openpilot disengaged, so a drive is never interrupted.

New to CommaView? The [setup guide](/guides/setup) walks through installing the app and connecting your comma.

## What hasn't changed

- CommaView works on the **comma 3X** and **comma four**. The comma 3 still isn't supported, including the forks' comma 3 builds such as xnor-c3 ([why](/#faq-comma-3)).
- CommaView never changes how your fork drives. It adds a small runtime beside it and a small hook in its on-screen UI, so it can draw the same path, lanes and alerts.
- On a fork CommaView doesn't support yet, setup stops and leaves your comma as it was. You can ask for your fork on the feature board at my.commaview.com.

## Further reading

- [Which openpilot forks work with CommaView](/forks), with what each one shows
- [What's new](/whats-new) in every release
- [How CommaView releases work](/guides/releases)

CommaView is unofficial and not affiliated with comma.ai, sunnypilot, StarPilot, xnor-tech or AdventurePilot. It is beta software and not a safety system: never let it distract you from driving.
