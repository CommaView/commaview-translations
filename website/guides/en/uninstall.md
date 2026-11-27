---
title: "Remove CommaView from your comma"
description: "Uninstall the CommaView runtime from your comma in Device settings, put your fork’s files back as they were, and forget the comma on your phone."
topic: account
order: 3
kind: walkthrough
lede: "**Uninstall runtime** removes CommaView from your comma: it reverts CommaView’s hooks, stops its runtime and removes `/data/commaview`. Your fork keeps driving as it always did. Use it to remove CommaView, or to run guided setup again from the start."
parked: true
updated: 2026-11-27
needs:
  - title: "The phone and the comma together"
    text: "On the same Wi‑Fi as the comma, or on its hotspot. Device settings needs the comma to manage updates and removal."
  - title: "The car on, in Park"
    text: "If the car is being driven, the comma queues the uninstall until it’s in Park with openpilot disengaged."
steps:
  - id: device-settings
    title: "Open the comma’s Device settings"
    body: |
      From Home, open your comma’s **Device settings**, then **Runtime** (“Update or remove CommaView”).
    screen: device-settings
    pins:
      - target: runtime-row
        text: "**Runtime**: update or remove CommaView."
  - id: uninstall
    title: "Tap Uninstall runtime"
    body: |
      Under the runtime update, **Uninstall runtime** removes CommaView from this comma. Guided setup can then run again from the start.
    screen: device-runtime
    pins:
      - target: uninstall
        text: "**Uninstall runtime**."
  - id: confirm
    title: "Confirm"
    body: |
      **CommaView will be removed**: CommaView reverts its runtime hooks, stops, and removes `/data/commaview` from this comma. The comma stays saved on your phone. Tap **Uninstall runtime** once its short countdown ends.
    screen: runtime-uninstall-confirm
    pins:
      - target: removed
        text: "**CommaView will be removed**, and what that does."
      - text: "**Uninstall runtime**, after its countdown. **Cancel** keeps CommaView."
    note: "If the car is being driven, the comma queues the uninstall: CommaView is removed once the car is in Park with openpilot disengaged, and keeps running until then."
  - id: forget
    title: "Forget the comma on your phone, if you like"
    body: |
      Device settings now says the runtime was removed. To take the comma off your phone too, tap **Forget this comma** at the end of Device settings: CommaView stops showing this comma and deletes its pairing key. To remove the app itself, uninstall CommaView from Android’s settings as you would any app.
    screen: device-settings-forget
    pins:
      - target: forget-row
        text: "**Forget this comma**."
check: "The dialog says **Runtime uninstalled**, and Device settings shows the runtime **Removed**: “CommaView was uninstalled from your comma. Run guided setup to install it again.”"
fixes:
  - q: "“Uninstall failed due to SSH permission error”"
    a: "The comma didn’t let this phone in over SSH. Check SSH is on under **Settings → Device → SSH** on the comma and its GitHub username has this phone’s key, then tap **Uninstall again**."
  - q: "“The comma couldn’t uninstall CommaView, so it left it as it was”"
    a: "Nothing was removed. Try again with the car in Park."
  - q: "“Uninstall queued until the car is in Park”"
    a: "The car is being driven. Put it in Park with openpilot disengaged, keep it on, and the comma removes CommaView by itself."
  - q: "The Uninstall button is greyed out"
    a: "CommaView is already updating or uninstalling a runtime. Try again when it has finished."
related: [setup, update-runtime, forks]
---

## What uninstall puts back

- **On a listed fork**, it reverts the small hook CommaView adds to the fork’s on-screen UI.
- **On a fork CommaView doesn’t list** (best effort), it puts the fork’s files back as they were.
- **Video only** changed nothing in the fork’s files, and uninstall removes the runtime.

On SunnyPilot-TeslaHW1, uninstall the runtime before `op fork update`, which can’t move the fork while CommaView’s hook is installed. [Check your comma and fork are supported](/guides/forks) has more.

## Setting CommaView up again

After an uninstall, the comma stays saved on your phone. Run [guided setup](/guides/setup) to install it again as a fresh install.
