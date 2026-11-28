---
title: "comma connect or local video: which one does what you need?"
description: "comma connect, SSH and CommaView compared after openpilot 0.11.2: parked livestreams, clips, drive retention, video quality, privacy and what each one is for."
date: 2026-11-06
slug: comma-connect-vs-local-video-access
tags:
  - comma connect
  - local video access
  - comma four
  - CommaView
heroLabel: "Decision guide"
draft: false
---

comma connect, comma's own web app, is where most owners look at their drives first, and for a lot of jobs it's the right place to look. Since openpilot 0.11.2 it does more than before: it can livestream a parked car and cut MP4 clips on the device. Local access, over SSH or with CommaView, does a different job: it gets video straight off the comma on your own network.

The short answer:

- **A recent drive, from anywhere:** comma connect.
- **Checking on the car while it's parked:** comma connect's livestream.
- **Watching the road with your fork's driving overlay while you drive, on a bigger screen:** CommaView's Live View.
- **The raw camera files, for development or archiving:** SSH.
- **A clip of what you just saw, with the overlay on it, on your phone, with no upload:** CommaView's Record.

## What comma connect does

**It keeps your drives in the cloud, for a while.** comma's [prime page](https://comma.ai/prime) says recordings "will upload to connect where they will be stored for 3 days". With comma prime ($24 a month, US only, data included) or prime lite ($14 a month, bring your own SIM if you want cellular), connect keeps them for a year.

**What it shows by default is the small video.** comma's [log documentation](https://docs.comma.ai/concepts/logs/) says the video in connect comes from the qcamera files, "lower res versions of the fcamera.hevc", which are made to upload quickly on a slow connection. The full-resolution HEVC files stay on the comma unless you upload them too.

**Since 0.11.2, it can livestream a parked car.** The [0.11.2 release post](https://blog.comma.ai/0112release/) (23 October 2026) says that with an internet connection, "home Wi-Fi or comma prime LTE", and a comma power installed, "you can livestream your road and driver cameras to see what is happening around your vehicle while it's parked." You watch it in connect, from anywhere.

**It cuts clips, too.** The same release adds a clips button in connect: pick part of a drive and "your comma will stitch and re-encode it as a widely supported MP4 (H.264)." Leave the comma on while it works, then download the clip from connect.

That's a real step forward. If you want to see your parked car from your desk, or send a friend a clip of last night's drive, connect now does both.

## What comma connect doesn't do

- **It doesn't stream while you drive.** The livestream is for a parked car.
- **It doesn't draw openpilot's driving overlay.** The livestream and the clips are camera video, without the path, lanes, alerts or speed you see on the comma's screen.
- **It needs the internet.** The livestream needs your home Wi-Fi or prime's LTE, and drives have to upload before connect can show them.
- **It forgets after 3 days without prime.** After that, connect no longer shows the drive, even if the comma still has it.

None of that is a flaw. connect is a cloud service for seeing your car and your drives from wherever you are.

## What local access does

Local access means getting video from the comma itself, on the same network, instead of from comma's servers.

### SSH: the raw files

Every openpilot drive is saved on the comma as one-minute segments, each with its own files: `fcamera.hevc` (road), `ecamera.hevc` (wide road), `dcamera.hevc` (driver), `qcamera.ts` (the small preview) and the logs. Over SSH you can copy any of them while the comma still has them; it deletes the oldest drives when it runs short of space. That's the way to get full-resolution video for development or your own archive, but it's one-minute HEVC files, not a clip you can share. Our guide to [downloading comma footage](/blog/download-comma-dashcam-footage) walks through it.

### CommaView: Live View and Recordings on Android

CommaView is an Android app and a small runtime on the comma, `commaviewd`, that sends the camera and driving data to your phone over your own local network: your Wi-Fi, or a hotspot in the car, whether it's your phone's, your head unit's or the comma's.

- **Live View, while you drive.** The road camera with your fork's own screen drawn on it, as the comma four or comma 3X draws it, or CommaView's own screen, on a phone, a tablet on the dash or an Android head unit. The comma four's screen is 1.9 inches; your phone's is a lot bigger.
- **Recordings on your phone.** Tap Record in Live View, and once you park, CommaView downloads the comma's own video for that stretch, up to 10 minutes, and draws your fork's screen over it on the phone. Or save a live copy of what Live View shows, at 720p or 1080p, with no 10-minute limit. Play it back, share it or open it in another app.
- **Go live.** Stream what Live View shows, road and overlay, to your YouTube channel or any RTMP server, at 720p or 1080p.
- **No subscription, no upload.** Live View and recordings go from your comma to your phone, and recordings stay there until you delete them. Your comma's cameras go only to the phones and head units paired with it.

It works with the comma 3X and comma four, on openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 and carrotpilot, and on other forks best effort. [Which forks, and what Live View draws on each](/forks).

## Side by side

| Feature | comma connect | CommaView |
| --- | --- | --- |
| Live video | Road and driver cameras, while parked | Road camera, while you drive |
| Driving overlay | No | Your fork's screen, or CommaView's |
| Where the video goes | Over the internet, watched in connect | Your own local network (Wi-Fi or a hotspot), to your paired phones |
| Needs | Internet, a comma power for the livestream | An Android phone, tablet or head unit on the same network |
| Clips | Any part of a drive, as an MP4 cut on the comma and downloaded from connect | What you recorded in Live View: a replay of up to 10 minutes, or a live copy, with the overlay |
| How long drives last | 3 days, a year with prime | On your phone until you delete them |
| Cost | Free, or prime $24 / lite $14 a month | No subscription; CommaView is in an invite-only beta |

## Use both

They don't compete for the same job. Keep connect for seeing the car from anywhere and for drives you want in the cloud; use CommaView for watching the road with your fork's overlay on a bigger screen, recording what you saw and streaming it. A passenger can watch Live View while you drive; if you drive alone, treat it like the comma's own screen and keep your eyes on the road.

## Further reading

- [comma prime](https://comma.ai/prime), for connect's plans and how long it keeps drives
- [openpilot 0.11.2](https://blog.comma.ai/0112release/), for the livestream and clips
- [How to download comma footage](/blog/download-comma-dashcam-footage), over SSH
- [Set up CommaView](/guides/setup)

CommaView is unofficial and not affiliated with or endorsed by comma.ai, sunnypilot or any openpilot fork it works with. It is beta software and not a safety system: never let it distract you from driving.
