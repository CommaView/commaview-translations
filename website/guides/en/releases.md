---
title: "How CommaView releases work"
description: "How the CommaView app and the runtime on your comma are released: alphas, then a beta, signed downloads, matched runtimes and updates that wait for Park."
topic: account
order: 2
kind: reference
lede: "CommaView has two parts that update together: the Android app, and the small runtime on your comma. Here is how a release gets to you, and how updates stay safe."
updated: 2026-11-27
steps:
  - id: version
    title: "See which version you have"
    body: |
      Settings › **About** shows the app’s version, and whether it’s **Up to date** or an update is available, with its version. CommaView checks your account for a new release and tells you when one is ready.
    screen: support-about
    pins:
      - target: version
        text: "The app’s version."
      - target: up-to-date
        text: "**Up to date**, or the release ready for you."
  - id: app-update
    title: "Update the app from inside it"
    body: |
      When a release is ready, **Update** shows at the top of Home and in **About**. **Update CommaView** names the version and its channel: **Beta** for everyone invited, or **Alpha**, “An early build for testers. It may have more problems than the beta.” Tap **Download**: CommaView downloads it in the background, checks it, then Android asks you to confirm the install.
    screen: app-update-offer
    pins:
      - target: channel
        text: "The channel: **Beta** or **Alpha**."
      - target: download
        text: "**Download**. **Not now** leaves it for later."
  - id: runtime
    title: "Then update your comma’s runtime"
    body: |
      Each app release names the runtime it was tested with. Once the app is updated, Home offers that runtime with **Runtime update ready**. Runtime updates start from the app, never on their own. [Update your comma’s runtime](/guides/update-runtime) has each step.
    screen: home-runtime-update
    pins:
      - target: update-card
        text: "**Runtime update**: the installed and the available runtime."
related: [update-runtime, uninstall, setup]
---

## Alpha, then beta

- Each version is first released as a series of alphas to a few testers.
- When an alpha holds up, it becomes that version’s beta and goes to everyone invited.
- Your account at [my.commaview.com](https://my.commaview.com) always offers the release that’s right for you.

## Signed and matched

- Every app download is a signed release build, never a debug build, with its SHA-256 checksum shown beside it on my.commaview.com. The app checks the size and checksum of an update it downloads before it offers to install it: “The download didn’t match its checksum, so it wasn’t installed.”
- Each app release names the runtime it was tested with, and the app installs exactly that one on your comma.
- An older app is never offered a runtime it hasn’t been tested with. A comma whose runtime is newer than the app installs says so: update CommaView, then try again.

## Updating your comma safely

- Runtime updates start from Home or Device settings, never on their own.
- Updates never interrupt a drive. If the car is being driven, Safe Update queues the update and the comma installs it once the car is in Park with openpilot disengaged. You don’t need to switch the car off.
- After a runtime update, the comma needs a reboot before CommaView streams again. The app asks for it.
- You can remove the runtime from Device settings at any time: [Remove CommaView](/guides/uninstall).

## Where you hear about it

- The app tells you when a new release is ready.
- [What’s new](/whats-new) lists every change.
- We email you about important changes, and you can send feedback from the app at any time (Settings › **Support & diagnostics**).
