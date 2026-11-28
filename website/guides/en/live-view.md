---
title: "Watch your comma in Live View"
description: "Open Live View to see your comma’s road camera and its onroad screen on your phone, and learn its controls, Details and what it says when something’s wrong."
topic: screens
order: 1
kind: walkthrough
lede: "**Live View** shows your comma’s road camera, live, with the onroad screen drawn over it: the comma four’s, the comma 3X’s or CommaView’s own. It comes straight from the comma over your own network, not the internet."
parked: true
updated: 2026-11-27
needs:
  - title: "CommaView is set up"
    text: "CommaView on an Android phone, paired with your comma. Not yet? [Set up CommaView](/guides/setup)."
  - title: "The car is on"
    text: "openpilot sends video only onroad. With the car off, Live View waits and starts by itself once the car starts."
  - title: "One network"
    text: "Your phone and your comma on the same Wi‑Fi or hotspot. In the car, see [Connect in the car](/guides/connect-in-the-car)."
steps:
  - id: open
    title: "Open Live View from Home"
    body: |
      On **Home**, with your comma connected and the car on, tap **Open Live View**. The road shows within a few seconds, with the stream pill saying **Live**.
    screen: phone-home
    pins:
      - target: open-live-view
        text: "**Open Live View**, Home’s main button."
    note: "With the car off, Live View says **Your comma is online but not driving**. It starts by itself when the car does, or at once with **Refresh**."
  - id: controls
    title: "Learn the controls under the picture"
    body: |
      Held upright, the controls sit under the video:

      - **Record** saves this stretch of the drive. See [Record a drive](/guides/record).
      - **Save** keeps the last 3 minutes and the next minute of the drive.
      - The onroad screen switch, named for the screen it shows (**CommaView**, **comma 4**, **comma 3X**), moves to the next one with each tap. See [Choose the onroad screen](/guides/overlays).
      - **Go live** streams what Live View shows, once you’ve set it up. See [Go live](/guides/go-live).
      - **Driver cam** shows the driver camera in a corner of the picture.
      - **Details** opens Live View’s facts and cards.

      What doesn’t fit at your phone’s width and text size goes into **More**. Nothing is shrunk or cut off.
    screen: phone-live-view
    pins:
      - target: record-button
        text: "**Record**."
      - target: onroad-screen-button
        text: "The onroad screen switch."
      - target: driver-cam-button
        text: "**Driver cam**."
      - target: go-live-button
        text: "**Go live**, once live streaming is set up."
      - text: "**More** holds what doesn’t fit."
    note: "While a recording runs, the onroad screen switch and **Driver cam** are dimmed: choose them before you tap **Record**."
  - id: details
    title: "Open Details"
    body: |
      Tap **Details**, or lift the sheet at the foot of the screen. It shows how the stream is doing, the video, the runtime, your comma’s software and its address, whether you’re recording or streaming, and the **Browser View** card. Its links open **Recordings** and your comma’s **Device settings**.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "The **Details** sheet."
      - text: "The summary: the stream’s health, the video and the runtime."
      - target: recordings-link
        text: "**Recordings**."
      - target: device-settings-link
        text: "**Device settings** for this comma."
  - id: turn
    title: "Turn the phone, or use a bigger screen"
    body: |
      Turn the phone on its side and the video takes the screen, with the controls in a rail on the driver’s side. **Details** opens beside the picture, and **Exit** leaves Live View.
    tabs:
      - label: "Phone on its side"
        body: "The rail holds the same controls. On a short screen it turns compact."
        screen: phone-live-view-landscape
        pins:
          - target: record-button
            text: "**Record**, at the top of the rail."
          - target: more
            text: "**More** holds **Driver cam** and **Details**."
          - target: exit
            text: "**Exit** leaves Live View."
      - label: "Tablet or car screen"
        body: "On a wide screen the rail stays on the driver’s side. See [Use CommaView on a car screen](/guides/car-screens)."
        screen: car-live-view
        pins:
          - target: record-button
            text: "**Record**."
          - target: onroad-screen-button
            text: "The onroad screen switch."
          - target: driver-cam-button
            text: "**Driver cam**."
          - target: details
            text: "**Details**."
          - target: exit
            text: "**Exit**."
  - id: auto
    title: "Let Live View open by itself"
    body: |
      For a phone or head unit that’s there only to show Live View, open **Settings › Display** and turn on **Open Live View when connected**, under **Opening Live View**. Live View then opens by itself when your comma connects with the car on. Leave it and it stays closed until the next time.

      **Keep the status bar**, just below it, shows the system’s clock above Live View instead of using the whole screen.
    screen: settings-display-opening-live-view
    pins:
      - target: open-live-view-when-connected
        text: "**Open Live View when connected**."
  - id: leave
    title: "Leave Live View when you’re done"
    body: |
      Tap **Exit**, or back, once you’ve parked. Leaving Live View ends Go live, Browser View and live copies too. Live View is open on one phone or head unit at a time, so leave it on one before you open it on another.
check: "The stream pill says **Live**, the road moves, and Details’ stream health says **Good**."
fixes:
  - q: "“Your comma is online but not driving”"
    a: "The car is off, or openpilot hasn’t started. Live View comes back by itself within 30 seconds of the car starting, or tap **Refresh**."
  - q: "“Can’t reach this comma”"
    a: "Your phone must be on the same Wi‑Fi as the comma, or on its hotspot. Live View reconnects when the comma answers, or tap **Retry**. Still nothing? See [CommaView can’t find your comma](/guides/comma-not-found)."
  - q: "“Live View is open on another device”"
    a: "Your comma streams to one phone or head unit at a time. Go back to Home in CommaView on the other one, and Live View starts here by itself."
  - q: "“Car data isn’t coming through”"
    a: "The video arrives, but the car’s speed, signals and alerts don’t. Reboot the comma to fix it."
  - q: "“Video delayed”"
    a: "No new frame has arrived for a second. Live View says so beside the picture, and reconnects by itself if the video doesn’t come back."
  - q: "“Can’t play this comma’s video”"
    a: "None of the phone’s video decoders could play it. CommaView keeps trying. Send a support report from Settings so CommaView can look into it: see [Send a support report](/guides/support-bundle)."
related: [overlays, record, browser-view, car-screens]
---

## Safety

Open Live View parked, then leave it alone. Don’t operate CommaView while driving: keep your eyes on the road and your hands on the wheel, as openpilot asks. Your comma’s own alerts and your car’s instruments come first. CommaView only shows what the comma sees.
