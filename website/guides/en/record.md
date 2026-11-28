---
title: "Record a drive from Live View"
description: "Tap Record in Live View, then make the drive’s replay once you park: the comma’s own video with your fork’s screen drawn over it, saved on your phone."
topic: recordings
order: 1
kind: walkthrough
lede: "**Record** in Live View saves a drive. Unless you choose otherwise, it makes a **replay**: once you park, CommaView downloads the comma’s own video for what you recorded, up to 10 minutes, and draws the onroad screen over it on your phone. Nothing is uploaded: recordings stay on your phone until you delete them."
parked: true
updated: 2026-11-27
needs:
  - title: "Live View works"
    text: "CommaView on your phone, paired with your comma. Not yet? [Set up CommaView](/guides/setup), then [open Live View](/guides/live-view)."
  - title: "The car on"
    text: "Record starts once the comma has started a drive, so switch the car on first. Start recording in Park, before you pull away."
  - title: "Room on your phone"
    text: "A replay is made on your phone, from the comma’s video. Settings › Recordings shows the storage it uses and what’s free."
howItWorks:
  - title: "Record in Live View"
    text: "Opens the comma’s capture window: it keeps the onroad screen’s data while you record."
    edge: "after you park"
  - title: "Make replay"
    text: "The phone downloads the comma’s video for that stretch, one drive at a time."
  - title: "Recordings"
    text: "The replay plays on your phone, with the screen drawn over the video."
steps:
  - id: choose
    title: "Choose what Record makes"
    body: |
      Tap **Settings**, then **Recordings**. Under **Record in Live View**, **Replay** is chosen until you change it: “The best picture: the comma’s own video with the HUD drawn over it, made after you park. Up to 10 minutes a recording.”

      **Live copy** saves what Live View shows instead, with no time limit, and **Both** makes the two. They have [a guide of their own](/guides/live-copy).
    screen: settings-recordings
    pins:
      - target: record-in-live-view
        text: "**Record in Live View**: **Replay**, **Live copy** or **Both**."
      - text: "**Replay** opens its quality: **Balanced**, **High** or **Max**. Higher quality takes longer to make and makes larger files."
  - id: start
    title: "Tap Record in Live View"
    body: |
      With the car on and still in Park, open **Live View** and tap **Record**. It reads **Starting…** for a moment while CommaView syncs with the drive, then its timer runs.
    screen: phone-live-view
    clip: record
    pins:
      - target: record-button
        text: "**Record**. On a tablet, a head unit or a phone on its side, it’s in the rail."
    warn: "Start recording before you drive off, or let a passenger handle it. Don’t tap through CommaView while you drive."
  - id: recording
    title: "Let it record"
    body: |
      While it records, Record shows the time and **Details** says **Recording ·** and the time. Tap Record again to stop. A replay also stops by itself at 10 minutes, and when Live View closes.
    screen: phone-live-view-recording
    pins:
      - target: stop-recording
        text: "Record, with its timer. Tap it again to stop."
      - target: recording
        text: "**Recording ·** the time, in **Details**."
      - text: "**Save** keeps the last 3 minutes and the next minute, without Record. It’s copied to your phone once you park."
    note: "**Save** shows only where your comma’s runtime lists its drives. A tap within that next minute keeps another minute, up to 10 minutes. Leave it to a passenger while you drive."
  - id: make-replay
    title: "Park, then make the replay"
    body: |
      Once you’ve parked, open **Recordings** from the bar at the bottom (the rail on a bigger screen). The drive you recorded says **Needs processing**. Open it and tap **Make replay**: the app says “Replay queued. Follow it in Queue.”

      The comma shares a drive only while the car is in Park with openpilot disengaged, so keep the car on and your phone on the comma’s network until the replay is made. Without a power harness, switching the car off switches the comma off too.
    screen: recordings-make-replay
    pins:
      - text: "**Make replay**."
      - target: queue
        text: "**Queue** shows each replay being made, one at a time, with Pause, Retry and Remove."
    note: "**Make replay** can take up to a minute to appear after you park: a comma that said it was being driven is asked again a minute later."
  - id: watch
    title: "Watch it in Recordings"
    body: |
      When it’s made, the app says **Replay made** with its number of frames, and the drive plays in Recordings. Tap it to watch, full screen if you like.
    screen: phone-recordings
    pins:
      - text: "The drive’s replay, grouped under the day."
      - target: filter
        text: "**Filter**: **All drives**, **Ready** or **Needs processing**, and which comma."
check: "The drive’s row no longer says **Needs processing**, and it plays when you tap it. To share it or save it elsewhere, see [Share and export recordings](/guides/export-share)."
fixes:
  - q: "“Recording can start once the comma has started a drive.”"
    a: "The comma is offroad. Switch the car on and wait for openpilot to start, then tap Record again."
  - q: "“CommaView is still syncing with this drive. Try Record again in a moment.”"
    a: "Record needs the comma’s frame times, which come with its driving data. They hadn’t arrived within 5 seconds. Wait a moment and tap Record again."
  - q: "“CommaView isn’t receiving driving data from the comma. Check the connection, then try Record again.”"
    a: "The video may still play, but the driving data stopped. Check your phone is still on the comma’s Wi‑Fi or hotspot, then try again. If Live View says **Car data isn’t coming through**, reboot the comma."
  - q: "“Reboot the comma first: CommaView was installed, updated or repaired, and records again after a reboot.”"
    a: "Reboot the comma when the car is in Park, then record again."
  - q: "“Recording storage is full. Free up some space, then try Record again.”"
    a: "Delete drives you no longer need in Recordings, or choose another storage under **Settings › Recordings › Storage** with **Change**."
  - q: "“The comma has no room left for this drive’s HUD data (about 55 minutes of recordings). Record again on your next drive.”"
    a: "The comma keeps up to about 55 minutes of recordings’ HUD data for each drive. Make the replays of what you recorded, and record again on the next drive."
  - q: "“Shift into Park to make this replay”, or the drive says “Waiting until you park”"
    a: "The comma shares a drive only parked, with openpilot disengaged. Put the car in Park and keep it on. The replay waits and asks again every 15 seconds; after 30 minutes of driving it stops with “The car was still being driven, so the comma couldn’t share this drive. Retry once you’re parked.” Tap **Retry** in Queue once you’re parked."
  - q: "“Connect to Comma Chameleon to make this replay”"
    a: "Your phone couldn’t reach the comma that recorded the drive (it names yours). Join your phone to the comma’s Wi‑Fi or hotspot, then tap **Retry** in Queue. See [CommaView can’t find your comma](/guides/comma-not-found)."
  - q: "“Drive deleted from the comma”"
    a: "The comma deleted this drive to make room for newer ones before its replay was made, so it can’t be made now. You can delete the recording. A drive that says **Make the replay soon** is close to that: make it while you can."
  - q: "The replay says “HUD missing for 2 min”"
    a: "The comma didn’t save the onroad screen’s data for part of the recording. The replay shows **HUD data unavailable** over that stretch, and Watch’s **HUD data** fact says how long."
  - q: "“Replay made: 4,860 frames. It ends early, where the comma lost power.”"
    a: "The comma lost power as the drive ended, so its last moments weren’t saved. Recordings may show **Your comma may have lost power as a drive ended**; its **How to fix it** explains comma power and the offroad time setting."
related: [live-copy, export-share, live-view]
---

## Replay, live copy or both

| Record makes | What you get |
| --- | --- |
| **Replay** (the default) | The comma’s own video with the onroad screen drawn over it, made after you park. The best picture, up to 10 minutes a recording, while the comma still has the drive. The road and wide cameras only: there’s no driver camera in a replay. |
| **Live copy** | What Live View shows, saved on your phone as you drive and ready the moment you stop. No replay to make and no time limit. [Record a live copy](/guides/live-copy). |
| **Both** | A live copy now, and the replay after the drive. The replay keeps its 10-minute limit. |

## Where recordings are kept

Recordings stay on your phone. **Settings › Recordings › Storage** shows the storage they use and what’s free, and **Change** picks another one when your phone has it. Android’s backup and a transfer to a new phone leave them out. **Send to CommaView** sends only the comma’s own data for a drive, and only when you send it.

## Safety

Start Record before you pull away, and make replays once you’ve parked. Don’t operate CommaView while driving: keep your eyes on the road and your hands on the wheel, as openpilot asks. CommaView isn’t a dashcam or a safety system, and a recording can fail.
