---
title: "How to download dashcam footage from a comma device"
description: "A practical guide to comma video files, comma 3/3X/four differences, and the safest ways to export route footage."
date: 2026-05-14
updatedDate: 2026-10-22
slug: download-comma-dashcam-footage
tags:
  - comma device video
  - dashcam footage
  - openpilot tools
  - SSH
heroLabel: "comma device guide"
draft: false
---

Need to get video off a comma device? The usual paths are comma connect, Openpilot Toolkit, or direct SSH/SFTP access.

The part that trips people up is the file layout. comma devices record openpilot routes in short segments, not one giant dashcam clip. Each segment can include raw camera files, preview video, and route logs. Once that clicks, exporting footage gets a lot less mysterious.

One important note up front: a comma device can be useful for road footage, debugging, and route review, but it is not a drop-in replacement for a dedicated dashcam.

## comma devices are useful cameras, not perfect dashcams

A dedicated dashcam is built around evidence capture: fast boot, crash resilience, parking mode, simple file export, rear-camera options, and removable storage.

A comma device is built to run openpilot. It records route data because that is useful for driving models, debugging, connect previews, and development. That footage can be valuable, but it comes with tradeoffs:

- footage can be harder to retrieve than pulling an SD card
- a crash or sudden power loss can cost recent footage
- parking-mode recording is not the main design goal
- rear-facing dashcam coverage is not included
- old local data is deleted when the device needs space

If the goal is dependable crash footage, run a real dashcam. If the goal is openpilot route footage, development review, or local video export, the comma workflow is worth learning.

## What files does openpilot record?

Official openpilot logging docs describe routes as one-minute segments. For each segment, modern openpilot records these file types:

| File | What it contains |
| --- | --- |
| `fcamera.hevc` | road camera video, H.265/HEVC |
| `ecamera.hevc` | wide road camera video, H.265/HEVC |
| `dcamera.hevc` | driver/cabin camera video, H.265/HEVC |
| `qcamera.ts` | lower-resolution H.264 preview from the road camera |
| `rlog.zst` | full route logs |
| `qlog.zst` | smaller/decimated route logs |

The video shown in comma connect is the lower-resolution `qcamera.ts`. Full-resolution camera footage lives in the HEVC files and may need to be uploaded manually through connect or copied directly from the device.

Older routes, older forks, or older docs may show `rlog`/`qlog` without `.zst`, or older `.bz2` log names. For current openpilot, use the names above.

## comma 3, comma 3X, and comma four: what changes?

There are two separate things people mix together: camera hardware and file layout.

The camera hardware is different by generation:

| Device | Camera/storage notes |
| --- | --- |
| comma 3 | Three 1080p cameras with 120 dB HDR. Community docs list several storage variants: 1TB, 250GB, late 64GB, and early 32GB. |
| comma 3X | Same triple-camera arrangement as comma 3, upgraded OX03C10 image sensors, 140 dB HDR, and commonly listed as 128GB storage. |
| comma four | comma describes it as having the same compute, sensor suite, and functionality as comma 3X, but in a much smaller physical package. The triple-camera system fits inside the 1.9-inch display footprint, with two road-facing cameras and a night-vision cabin camera. comma lists 128GB storage and 10 hours of footage. |

The file notes here apply to all three. CommaView itself works with the comma 3X and comma four only.

For current openpilot, the practical file layout is shared across comma hardware. The modern segment files are `fcamera.hevc`, `ecamera.hevc`, `dcamera.hevc`, `qcamera.ts`, `rlog.zst`, and `qlog.zst`.

That means the cameras can change physically while the export names stay familiar. `fcamera.hevc` is the road camera. `ecamera.hevc` is the wide road camera. `dcamera.hevc` is the driver/cabin camera.

If you are running a custom fork, verify on-device before assuming every file is present. Forks can change recording settings, and driver/cabin recording can depend on device settings.

## Where are the files stored locally?

On comma hardware, openpilot’s current log root is:

```text
/data/media/0/realdata
```

Inside that folder, each route segment gets its own timestamped folder, for example:

```text
/data/media/0/realdata/2026-05-14--12-30-05--3/
```

That folder is where you look for files like:

```text
fcamera.hevc
ecamera.hevc
dcamera.hevc
qcamera.ts
rlog.zst
qlog.zst
```

For direct SSH/SFTP workflows, this is the folder to start from. The official docs explain how to connect to a comma 3X or comma four over SSH, and openpilot uses `/data/media/0/realdata` as the on-device log root.

## Option 1: Use comma connect

For recent drives, comma connect is usually the easiest place to start.

Use connect when:

- the route is recent
- the device uploaded the route successfully
- preview video is enough
- you want a web UI instead of SSH
- you only need a few clips or files

connect is also where many users first identify the route and segment numbers they need. The catch is retention: connect may stop showing a route before the local device has deleted it. If connect no longer exposes a route but the files still exist on-device, SSH/SFTP may still recover them.

Also remember that connect previews are based on `qcamera.ts`. If you need full-resolution camera footage, make sure the full video files are uploaded or pull the raw HEVC files directly.

## Option 2: Use Openpilot Toolkit

Openpilot Toolkit is a community tool that can make local export less painful. It includes workflows for SSH setup, file browsing, drive video preview, and raw export.

Use Openpilot Toolkit when:

- you want a GUI
- you do not want to hand-roll SSH commands
- you need help setting up keys
- you are on Windows or Android
- you want to browse and export route footage more directly

For many users, this is the best middle ground: more control than connect, less friction than manual terminal work.

## Option 3: Use SSH or SFTP directly

Direct SSH/SFTP gives the most control and the least hand-holding.

At a high level, SSH access usually means:

1. Create or use a GitHub account with SSH keys.
2. Enable SSH in the comma device settings.
3. Enter your GitHub username on the comma device so it can fetch your public keys.
4. Connect as user `comma` on port `22`.

Once connected, browse or copy from:

```text
/data/media/0/realdata
```

Use direct access when:

- you need raw `fcamera.hevc`, `ecamera.hevc`, or `dcamera.hevc` files
- connect does not expose the file you need
- you want to archive a whole route
- you are comfortable with SFTP clients like FileZilla or WinSCP
- you are comfortable with `ssh`, `scp`, or `rsync`

Raw `.hevc` files often play in VLC. If another app needs MP4, remux with ffmpeg instead of re-encoding when possible.

## Which method should you use?

Use comma connect if the drive is recent and normal route review is enough.

Use Openpilot Toolkit if you want a friendlier local workflow without doing every SSH/SFTP step manually.

Use SSH or SFTP if you need raw files, older local files, complete route archives, or direct control over what gets copied.

## Where CommaView fits

CommaView is a local-first Android app for comma-device camera streaming, overlays, runtime setup, recordings, and replay workflows.

That overlaps with the same world of local camera access, but it is not comma connect, not Openpilot Toolkit, and not a traditional dashcam. It should not be used as a driving aid or as the only evidence-capture system in a vehicle.

CommaView works with the comma 3X and comma four, running openpilot or a [supported fork](/forks): sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1 or carrotpilot. The comma 3 isn't supported: comma moved it to a frozen long-term openpilot release whose screen CommaView can't draw its overlay from ([why](/#faq-comma-3)).

## Further reading

- Official openpilot logging docs: [Logging](https://docs.comma.ai/concepts/logs/)
- Official comma SSH docs: [connect to a comma 3X or comma four](https://docs.comma.ai/how-to/connect-to-comma/)
- comma connect: [comma.ai/connect](https://comma.ai/connect)
- openpilot wiki: [Video Files](https://github.com/commaai/openpilot/wiki/Video-Files)
- HowToComma: [Getting Videos From Device](https://docs.howtocomma.com/docs/getting-videos-from-device)
- Openpilot Toolkit: [project page](https://spektor56.github.io/OpenpilotToolkit/)
