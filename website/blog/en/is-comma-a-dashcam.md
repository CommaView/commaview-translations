---
title: "Is a comma device a dashcam? Useful, but not a replacement"
description: "A safety-first look at comma footage after openpilot 0.11.2: route files, connect retention and clips, local storage, crash footage, parking mode and dashcams."
date: 2026-11-06
slug: is-comma-a-dashcam
tags:
  - comma dashcam
  - comma device video
  - dashcam footage
  - openpilot
heroLabel: "Dashcam reality check"
draft: false
---

A comma device can record useful road and cabin footage. That does not make it a drop-in replacement for a dedicated dashcam.

The footage can help with route review, debugging, exports, and incident context. But a dedicated dashcam is built around different assumptions: crash-resilient evidence capture, simple removable storage, parking mode, rear-camera coverage, and appliance-like retrieval.

If dependable crash or insurance footage matters, run a dedicated dashcam alongside the comma device. Boring answer, correct answer.

## What a comma device records

openpilot records routes while the device is running. Current logging docs describe routes as segment-based, with camera and log files such as:

- `fcamera.hevc` — road camera video
- `ecamera.hevc` — wide road camera video
- `dcamera.hevc` — driver/cabin camera video
- `qcamera.ts` — lower-resolution preview video
- `rlog.zst` — full route log
- `qlog.zst` — smaller route log

That is very useful data.

It is also not one simple “dashcam clip.” It is openpilot route logging: segmented files, route IDs, upload behavior, local retention, codecs, logs, and tooling.

## Where footage may be available

There are two broad places people look first:

1. **comma connect** for recent cloud-visible drives.
2. **local device storage** for files that still exist on the comma device.

comma's [prime page](https://comma.ai/prime) says uploaded drives are kept in connect for 3 days, or 1 year with comma prime. By default connect shows the lower-resolution `qcamera` video ([comma's log docs](https://docs.comma.ai/concepts/logs/)).

Since [openpilot 0.11.2](https://blog.comma.ai/0112release/) (October 2026), connect can also cut a clip from part of a drive: the comma re-encodes it as an MP4 while it stays on, and you download it from connect. That makes getting one shareable clip much easier than it was.

Local openpilot storage is different. On current comma hardware, the practical route-data area is under `/data/media/0/realdata/`. But local storage is not infinite. openpilot has low-space cleanup behavior, so older routes are not a permanent archive.

If something matters, preserve it promptly.

## Why people still use comma footage

comma footage can be genuinely useful.

Good uses include:

- reviewing what happened on a route
- debugging openpilot behavior
- checking camera/log context
- exporting clips or raw HEVC files
- sharing development or support examples
- feeding replay/testing workflows

If you already have a comma device, ignoring that footage would be silly. It is valuable.

The mistake is assuming “valuable” means “same job as a dedicated dashcam.”

## Why it is not a dedicated dashcam replacement

A dedicated dashcam is usually built for evidence capture first.

That often means simple storage, quick retrieval, parking modes, rear or interior camera options, independent operation, and workflows designed around preserving clips after an event.

A comma device is built to run openpilot. The camera data exists because openpilot needs logging, model development, debugging, route review, and connect preview workflows.

Those priorities overlap with dashcam needs, but they are not identical.

## The risk areas

### Crash and power-loss resilience

If the device loses power, is damaged, or shuts down at the wrong time, recent footage may be harder to recover or may not be complete.

That does not mean comma footage is useless in every incident. It means it should not be your only evidence plan.

### Parking mode

Dedicated dashcams often sell hardwire-kit parking mode as a core feature.

openpilot 0.11.2 lets you livestream the road and driver cameras of a parked car in connect, with an internet connection and a comma power installed. comma's post describes it as a way to see what's happening around the car; it doesn't present it as a parking-mode event recorder.

Treat parking surveillance as dedicated dashcam territory unless you have a very specific, validated setup and understand the risks.

### Rear coverage

comma road, wide-road, and cabin/driver cameras are not the same as a rear-facing dashcam.

If rear coverage matters, use hardware that records rear coverage.

### Storage and export friction

A dashcam usually aims for simple clip retrieval from microSD, app, or display.

comma retrieval can involve connect visibility windows, manual upload, segment IDs, SSH/SFTP, HEVC files, local pruning, VLC/ffmpeg/remuxing, or helper tools. connect's new clips help, but the comma has to stay on while it makes one, and the drive has to still be there.

That is fine for technical users. It is not appliance-simple.

## When comma footage may be enough

comma footage may be enough for:

- casual road-footage reference
- openpilot route review
- debugging and testing
- development support
- local export when the route still exists
- reviewing an event shortly after it happened

That is a strong list.

It still does not make the comma device your only serious evidence recorder.

## When to add a dashcam

Use a dedicated dashcam if you care about:

- dependable crash or insurance footage
- parking surveillance
- rear coverage
- easiest possible retrieval
- removable storage
- independent recording if the comma device loses power
- a simpler tool for non-technical drivers

The combo is not weird. A comma device can be great for openpilot workflows while a dashcam handles boring evidence capture.

## Where CommaView fits

CommaView is an Android app and a small runtime on the comma. It shows the comma's road camera with your fork's driving overlay live on your phone, tablet or Android head unit, over your own network, and it saves what you record to your phone. Tap Record in Live View, and once you park it downloads the comma's own video for that stretch, up to 10 minutes, and draws the overlay over it; or save a live copy of what Live View shows, with no 10-minute limit. Nothing uploads, and recordings stay on your phone until you delete them. It records when you tap Record, not by itself, so it's no help with an event you didn't see coming.

That makes getting a clip of what you saw a lot easier. It does not turn a comma device into a safety-critical dashcam.

It does not guarantee evidence preservation.

It is not a driving aid.

And it works with the comma 3X and comma four only, not the comma 3. CommaView is unofficial and not affiliated with or endorsed by comma.ai.

## Practical checklist after an incident

Not legal advice, just practical triage:

1. Stop driving and handle safety/emergency needs first.
2. Do not rely on connect retention alone.
3. Preserve/export relevant route segments as soon as practical.
4. If using connect, identify the route and time window you need.
5. If connect does not expose the files but the device still has them, use owner-authorized SSH/SFTP or a trusted local tool.
6. Keep original files when possible.
7. Avoid destructive edits or cleanup until important footage is copied.
8. For legal/insurance matters, talk to the appropriate professionals.

The main point: move quickly, copy carefully, and do not assume the footage will wait around forever.

## The honest answer

A comma device is a useful camera and data recorder for openpilot routes. It can provide valuable video context.

But if the question is “can I skip a dashcam?” the safe answer is no.

Use comma footage for route review, debugging, and local workflows. Use a dedicated dashcam when dependable evidence capture is the requirement.
