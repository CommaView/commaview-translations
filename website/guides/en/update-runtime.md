---
title: "Update your comma’s runtime"
description: "Update the CommaView runtime on your comma from Home or Device settings. Safe Update waits for Park, so an update never interrupts a drive."
topic: account
order: 1
kind: walkthrough
lede: "The CommaView runtime on your comma updates from the app, never on its own. Update CommaView first, then the runtime when the app offers it. If the car is being driven, **Safe Update** queues the update on the comma and installs it once the car is in Park with openpilot disengaged."
updated: 2026-11-27
needs:
  - title: "The phone and the comma together"
    text: "On the same Wi‑Fi as the comma, or on its hotspot."
  - title: "The car on"
    text: "Keep the car on, in Park. Without a power harness, switching it off switches the comma off too."
howItWorks:
  - title: "CommaView"
    text: "Each app release names the runtime it was tested with, and offers exactly that one."
  - title: "Your comma"
    text: "Downloads it, checks it and installs it, once the car is in Park."
    edge: "reboot"
  - title: "Live View"
    text: "Starts again once the comma reboots."
steps:
  - id: app-first
    title: "Update CommaView first"
    body: |
      The app installs the runtime it was tested with, so update the app before the runtime. When an update is ready, **Update** shows at the top of Home and in Settings › **About**. Tap it: **Update CommaView** says the version, its channel and size. Tap **Download**; CommaView downloads it in the background and checks it, then Android asks you to confirm the install.
    screen: app-update-offer
    pins:
      - target: download
        text: "**Download**."
      - target: channel
        text: "The release’s channel: **Beta**, or **Alpha** for testers."
    note: "Update CommaView on every phone, tablet and car screen that watches this comma before you update its runtime."
  - id: open
    title: "Open the runtime update"
    tabs:
      - label: "From Home"
        body: "Home shows **Runtime update ready** when a new runtime is ready for this comma. Tap **Review update**: the **Runtime update** card shows the **Installed** and **Available** versions and whether the car is ready. Tap **Update runtime**, or **Queue update** while the car is being driven."
        screen: home-runtime-update-review
        pins:
          - target: update-card
            text: "**Runtime update**: Installed, Available and whether the car is ready."
          - target: update-runtime
            text: "**Update runtime** (**Queue update** while the car is driven)."
      - label: "From Device settings"
        body: "Open the comma’s **Device settings**, then **Runtime** (it shows **Update** when one is ready). The page shows the installed and available runtime. Tap **Update now**."
        screen: device-runtime
        pins:
          - target: update-now
            text: "**Update now**."
  - id: install
    title: "Install it, or let Safe Update queue it"
    body: |
      From Device settings, the **Runtime update** dialog says whether the car is ready.
    tabs:
      - label: "The car is in Park"
        body: "It says “The car is in Park and openpilot isn’t engaged. Runtime update is safe to start.” Tap **Install update**."
        screen: runtime-update-dialog
        pins:
          - target: install-update
            text: "**Install update**."
          - target: close
            text: "**Close** leaves it for later."
      - label: "The car is being driven"
        body: "It says “The car is being driven. Safe Update queues the update on the comma and installs it once the car is in Park with openpilot disengaged.” Tap **Safe Update…**, read the note, and tap **Start Safe Update** once its short countdown ends. The same happens when CommaView couldn’t confirm whether the car is being driven."
        screen: runtime-update-safe-update
        pins:
          - target: safe-update
            text: "**Safe Update…**, then **Start Safe Update**."
    note: "CommaView never stops openpilot or your fork: a queued update waits for Park, and a drive is never interrupted."
  - id: progress
    title: "Let it run"
    body: |
      The comma downloads the release, checks it is complete and unaltered, installs it and restarts CommaView, and the app shows each step. You can switch apps or lock your phone: the update carries on, and its notification shows how far it is.

      Until the comma starts installing, **Cancel update** stops it, and nothing on your comma changes.
    screen: runtime-update-progress
    clip: safe-update
    pins:
      - text: "The steps: Downloading, Verifying, Installing, Restarting CommaView, Reconnecting."
  - id: queued
    title: "A queued update waits for Park"
    body: |
      A queued update shows on Home’s **Runtime update** card as **Waiting for the car to be in Park**. It installs once the car has been in Park a few seconds with openpilot disengaged. Leave the car on while it installs.
    screen: home-runtime-update-queued
    pins:
      - target: update-card
        text: "**Waiting for the car to be in Park**, with its step."
  - id: reboot
    title: "Reboot the comma to finish"
    body: |
      After a runtime update, the comma needs a reboot before CommaView streams from it again: openpilot loads CommaView’s new screen code only when the comma restarts. The app never reboots it by itself.

      Tap **Reboot comma** on Home’s card, or **Reboot comma now** in the dialog, with the car off or in Park. openpilot stops for about a minute. You can also reboot it from the comma itself: **Settings → Device → Reboot**.
check: "The update’s last step says **Updated**, and Device settings shows the new runtime **Up to date**. After the reboot, Live View plays with its overlay."
fixes:
  - q: "“This comma’s runtime is newer than this app installs”"
    a: "Update CommaView, then try again. Nothing on the comma was changed."
  - q: "“Update needed”"
    a: "This app and this comma’s runtime aren’t new enough for each other. Update CommaView first, then the runtime."
  - q: "“The comma didn’t install …: it runs …, which CommaView doesn’t list”"
    a: "The comma changed nothing and kept the runtime it had. To add CommaView to that fork as best effort, run setup for this comma again: it checks the fork and asks you first."
  - q: "“The car came back on each time it started, so the comma stopped trying”"
    a: "Put the car in Park with openpilot disengaged, then try again."
  - q: "“Runtime update rolled back”"
    a: "The comma put back the runtime it had. Try again, and if it fails again, [send a support bundle](/guides/support-bundle)."
  - q: "“CommaView is already updating or uninstalling a runtime”"
    a: "One runtime job runs at a time. Try again when it has finished."
  - q: "No overlays or telemetry after the update"
    a: "The comma hasn’t restarted yet. Reboot it with the car off or in Park."
related: [releases, uninstall, another-phone]
---

## Why updates wait for Park

Installing the runtime stops CommaView on the comma while its files are replaced and restarts its services, so the comma does it only with the car in Park and openpilot disengaged. Safe Update doesn’t ask openpilot to go offroad: it queues the work on the comma, which runs it once the car is in Park. You don’t need to switch the car off; keep it on, in Park.

Before anything on the comma changes, it downloads the release and checks it is complete and unaltered. If an install fails after that, the comma puts back the runtime it had.
