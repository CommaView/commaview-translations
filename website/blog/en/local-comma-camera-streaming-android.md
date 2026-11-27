---
title: "Local comma camera streaming on Android: what CommaView does"
description: "CommaView streams your comma's road camera with its driving overlay to Android over your own network: Live View, Recordings, Go live, and what it doesn't do."
date: 2026-11-06
slug: local-comma-camera-streaming-android
tags:
  - comma camera streaming
  - comma four
  - Android app
  - CommaView
  - local streaming
heroLabel: "Product fit"
draft: false
---

CommaView streams your comma's road camera, with its driving overlay, to an Android phone, tablet or head unit over your own network. No cloud sits between the comma and your phone, and nothing has to upload first.

It's two pieces: the CommaView app, and a small runtime on the comma, `commaviewd`, that serves the camera and driving data to the app. Guided setup installs the runtime and checks it.

## Why stream it at all

The comma four's screen is 1.9 inches. It's a good screen for what it does, but it's small, and owners say so. The comma's other ways to get video are made for other jobs:

- **comma connect** keeps uploaded drives for 3 days, or a year with comma prime ([comma.ai/prime](https://comma.ai/prime)). Since [openpilot 0.11.2](https://blog.comma.ai/0112release/) it can livestream the road and driver cameras while the car is parked, over the internet, with a comma power installed, and cut MP4 clips on the comma.
- **SSH** gets you the raw one-minute HEVC segments from the comma's storage.

Neither shows the road with openpilot's driving overlay while you drive. That's what CommaView is for.

## What CommaView does

### Live View

The road camera, live, with your fork's own screen drawn on it: the comma four's, the comma 3X's, or CommaView's own, with your speed, MAX, the speed limit, the car ahead and lane changes in one cluster. Live View draws each fork's screen with what that fork adds, from sunnypilot's MADS to StarPilot's own HUD. It runs at up to the comma's 20 frames a second, and keeps going in picture-in-picture.

On a tablet or an Android head unit, CommaView lays out as a dashboard, with the Live View controls on the driver's side.

### Recordings

Tap Record in Live View, and once you park, CommaView downloads the comma's own video for that stretch, up to 10 minutes, and draws your fork's screen over it on your phone: a replay. Play it back, share it or open it in another app. A live copy saves what Live View shows as you drive, at 720p or 1080p, ready the moment you stop, with no 10-minute limit. Recordings stay on your phone until you delete them.

### Go live

Go live streams what Live View shows, the road and CommaView's overlay, to your YouTube channel or any RTMP server, at 720p or 1080p. Sign in with YouTube once and it makes, starts and ends each broadcast. Streams start Unlisted; anyone watching sees where you drive.

### Paired phones only

Your comma's cameras and data go only to the phones and head units paired with it. Video, drives and places go from your comma to your phone and nowhere else, unless you send, stream or contribute them.

## What needs the internet

Live View and recordings don't: they go straight from the comma to your phone, on the same local network: your Wi-Fi, or a hotspot in the car from your phone, head unit, AI box or the comma. Signing in, app and runtime updates, the map in Vehicle location, the leaderboard, Go live and anything you send to CommaView do.

## What it works with

The comma 3X and comma four, on openpilot, sunnypilot, StarPilot, xnor-tech's openpilot, AdventurePilot, SunnyPilot-TeslaHW1 and carrotpilot. Other openpilot forks work best effort: setup checks the fork and asks you before it installs. The comma 3 isn't supported: it's on a frozen openpilot release whose screen CommaView can't draw its overlay from. [Supported forks](/forks).

You need an Android phone, tablet or head unit on Android 8 or later.

## What CommaView isn't

- **Not comma connect.** It doesn't keep drives in a cloud or show your car from across town. Use connect for that.
- **Not a dashcam.** [Run a dedicated dashcam](/blog/is-comma-a-dashcam) if you need evidence-grade crash or parking footage.
- **Not a driving aid or a safety system.** It shows what the comma sees; the road is the source of truth.

## Use it safely

Set CommaView up while parked. A passenger can watch Live View while you drive; if you drive alone, treat it like the comma's own screen and keep your eyes on the road.

CommaView is in an invite-only beta. [Join the list](https://my.commaview.com/join) and we'll email you when it's your turn.

CommaView is unofficial and not affiliated with or endorsed by comma.ai, sunnypilot or any openpilot fork it works with. It is beta software and not a safety system: never let it distract you from driving.
