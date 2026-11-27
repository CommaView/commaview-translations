---
title: "Check your comma and fork are supported"
description: "CommaView works with openpilot, sunnypilot, StarPilot, xnor, AdventurePilot, SunnyPilot-TeslaHW1, carrotpilot, BluePilot, dragonpilot and OPGM, and best effort with other forks."
topic: start
order: 2
kind: reference
lede: "CommaView shows your comma’s road camera with the driving overlay of the software it runs. It works with openpilot and nine of its forks, on the comma 3X and comma four, and, best effort, with other openpilot forks. Setup checks which fork your comma runs before it changes anything."
updated: 2026-11-27
needs:
  - title: "A comma 3X or comma four"
    text: "The comma 3 isn’t supported, including the forks’ comma 3 builds such as xnor-c3. [Why the comma 3 isn’t supported](/#faq-comma-3)."
  - title: "Your fork, as it runs"
    text: "Installed and running as usual. CommaView adds its runtime beside it and never changes how it drives."
steps:
  - id: unlisted
    title: "On a fork CommaView doesn’t list, setup asks you first"
    body: |
      Guided setup checks which repository your comma’s software was installed from, and installs CommaView’s hook for that fork. On a fork it doesn’t list, it checks the fork first, without changing anything.
    tabs:
      - label: "Best effort"
        body: "If CommaView can add its view, setup shows **CommaView hasn’t verified this fork**. It names the fork by its repository and says what is drawn (the cameras, the path, lanes, the car ahead, alerts and speed) and what isn’t (the fork’s own buttons, colours and widgets). **Install anyway** installs on that fork, and only that one. **Back** returns to choosing the comma; nothing was installed."
        screen: setup-unlisted-fork
        pins:
          - target: install-anyway
            text: "**Install anyway** adds CommaView’s view to this fork, best effort."
      - label: "Video only (early access)"
        body: "For FrogPilot and KisaPilot, whose screens can’t take CommaView’s view, testers with the Video only flag see **Video only on this fork**: CommaView streams the cameras and draws its own view from the driving data, changing nothing in the fork. It hasn’t been tried on a comma yet. Without the flag, setup says the fork isn’t supported and changes nothing."
        screen: setup-video-only
        pins:
          - target: install-video-only
            text: "**Install video only**."
    note: "When the check refuses a fork, setup says “CommaView can’t add its view to … safely” and “Nothing on your comma was changed.”"
  - id: details
    title: "See which fork Live View draws"
    body: |
      In Live View, open **Details**. The **Software** line names your comma’s fork, and a fork CommaView doesn’t list is named by its repository, such as “crwusiz/openpilot · best effort”.
    screen: phone-live-view-details
    pins:
      - target: details
        text: "**Details**, under the picture."
      - text: "**Software**: the fork your comma runs."
related: [setup, overlays, uninstall]
---

## Supported forks

| Fork | Where it comes from | Supported since |
| --- | --- | --- |
| **openpilot** | comma.ai, github.com/commaai/openpilot | The first beta |
| **sunnypilot** | github.com/sunnypilot/sunnypilot | The first beta |
| **StarPilot** | github.com/StarPilotHQ/StarPilot, formerly github.com/firestar5683/StarPilot | 0.0.162 |
| **xnor** (xnor and rx builds) | xnor-tech, github.com/xnor-tech/openpilot | 0.0.163 |
| **AdventurePilot** | github.com/AdventurePilotDev/AdventurePilot | 0.0.163 |
| **SunnyPilot-TeslaHW1** | github.com/P6g9YHK6/SunnyPilot-TeslaHW1 | 0.0.164 |
| **carrotpilot** | github.com/ajouatom/openpilot, installed from i.carrotpilot.app | 0.0.164 |
| **BluePilot** | github.com/BluePilotDev/bluepilot | 0.0.166 |
| **dragonpilot** | github.com/dragonpilot/dragonpilot | 0.0.166 |
| **OPGM** | github.com/opgm/openpilot | 0.0.166 |

On a fork it doesn’t list, setup checks whether CommaView can add its view and asks you first; where it can’t, setup stops and leaves your comma as it was.

## What each fork shows

### openpilot

comma.ai’s own software. Live View draws the comma four’s screen, the comma 3X’s, or CommaView’s own overlay, with your speed, MAX, the speed limit, the car ahead and lane changes.

### sunnypilot

CommaView draws sunnypilot’s screen with what sunnypilot adds: MADS’s steering-only and speed-only states, speed-limit assist, the rainbow path and blind-spot indicators, and on the comma 3X screen its speed-limit sign, smart cruise and developer UI. It reads your sunnypilot settings, so the screen matches the comma’s.

### StarPilot

StarPilot shows its driving modes through colour, and CommaView uses the colours StarPilot chose: its border, path and widgets on the comma four and comma 3X screens, its alerts, and its camera choice, including the driver camera.

Turn off StarPilot’s **Disable Logging** setting. It stops the video encoder that Live View streams from.

### xnor-tech’s openpilot: xnor and rx

xnor-tech’s openpilot comes in two builds. Its **xnor** branches run openpilot’s screen and its **rx** branches run sunnypilot’s, each with xnor-tech’s car ports. CommaView draws whichever your comma runs, with its alerts as the comma writes them.

On a Rivian running rx, the wheel turns green while the car steers by angle and blue while it steers by torque: the comma four’s wheel, and on the comma 3X screen the experimental mode button’s.

### AdventurePilot

AdventurePilot is a sunnypilot fork with its own car ports. CommaView draws sunnypilot’s screen with what AdventurePilot adds:

- its lane-centering indicator: a pill with the push and offset on the comma 3X screen, a compact bar on the comma four’s;
- the CURVE chip on the comma 3X screen, which blinks while curve speed control acts;
- its steering mode’s wheel tint, and a torque bar that shows lateral acceleration while a Rivian steers on its angle channel.

### SunnyPilot-TeslaHW1

SunnyPilot-TeslaHW1 is a sunnypilot fork that adds Tesla’s HW1 (Autopilot 1) cars. Its screen is sunnypilot’s, so CommaView draws sunnypilot’s screen with everything sunnypilot adds, and names the fork in the app.

Its `op fork update` can’t move the fork while CommaView’s hook is installed: [uninstall CommaView’s runtime](/guides/uninstall) first, or use the fork switcher on the comma’s screen, which works as usual.

### carrotpilot

carrotpilot is an openpilot fork for Hyundai, Kia and Genesis cars, installed from `i.carrotpilot.app`. CommaView draws openpilot’s screen for it, with your speed, the path, lanes and the car ahead. What carrotpilot adds to its own screen, such as its navigation, speed cameras and HUD, isn’t drawn yet.

carrotpilot’s auto-update, and the Git tools on its web page, remove CommaView’s hook until the comma reboots. The app asks for the reboot, and Live View comes back after it.

### BluePilot, dragonpilot and OPGM

Listed from CommaView 0.0.166 with its runtime. CommaView names each and draws it in its base’s look: BluePilot as sunnypilot, dragonpilot and OPGM as openpilot, with dragonpilot’s ALKA shown as steering. A comma that ran one best effort moves to it at the boot after the runtime update. None has been driven with CommaView yet. CommaView’s official [overlay packs](/guides/overlays) draw more of BluePilot’s and dragonpilot’s own screens.

## Forks CommaView doesn’t list

From CommaView 0.0.165, with its runtime on your comma, setup can add CommaView’s view to an openpilot fork it doesn’t list, best effort. Live View draws the fork in openpilot’s look, or sunnypilot’s when the fork builds on sunnypilot’s screen. To undo it, **Uninstall runtime** in Device settings puts the fork’s files back as they were.

- **Best effort.** CommaView’s releases aren’t checked against your fork. If the fork updates itself into something CommaView can’t follow, CommaView’s view turns off and your fork drives and shows its own screen as usual, until a CommaView release handles the change.
- **Not every fork.** Forks built on openpilot’s older native screen aren’t supported (below).
- **Your yes is for that fork.** If your comma switches to another fork CommaView doesn’t list, CommaView asks again in setup before it adds its view there.

### Forks that pass the install check (best effort)

Each of these **passes CommaView’s install check; best effort, not tested on a car.** Checked November 2026, for the branches named, against the runtime CommaView 0.0.165 installs: the installer offers the fork, adds CommaView’s view once you agree, and checks it, as it would on your comma. Nothing here was tried on a comma in a car, a fork may not support every car on both devices, and a fork’s next update can change the answer.

| Fork | Branches checked | Devices | Drawn as |
| --- | --- | --- | --- |
| **crwusiz** (github.com/crwusiz/openpilot) | master_c4, master_c3 | comma four, comma 3X | openpilot |
| **jixiexiaoge’s Carrot** (github.com/jixiexiaoge/openpilot) | Carrot | comma four, comma 3X | openpilot |
| **MoreTore** (github.com/MoreTore/openpilot) | release-mici | comma four | openpilot |
| **zoompilot** (github.com/zoompilot/zoompilot) | main | comma four, comma 3X | sunnypilot |
| **AlexandreSato** (github.com/AlexandreSato/openpilot) | master | comma four, comma 3X | openpilot |
| **lukasloetkolben** (github.com/lukasloetkolben/openpilot) | master | comma four, comma 3X | openpilot |
| **mvl-boston** (github.com/mvl-boston/openpilot) | master, 0111-op-honda | comma four, comma 3X | openpilot |
| **mouxangithub** (github.com/mouxangithub/openpilot) | master-c3 | comma four, comma 3X | sunnypilot |
| **programanichiro** (github.com/programanichiro/openpilot) | release-piZ2 | comma four, comma 3X | openpilot |
| **infiniteCable2** (github.com/infiniteCable2/openpilot) | master | comma four, comma 3X | sunnypilot |
| **herizon1054** (github.com/herizon1054/openpilot) | dplcc | comma four, comma 3X | openpilot |
| **NotAutopilot** (github.com/NotAutopilot/openpilot) | nap-release, naponsp-alpha | comma four, comma 3X | openpilot (nap-release), sunnypilot (naponsp-alpha) |

Your fork isn’t here? It may still work: setup checks it before it changes anything.

### Not supported

These forks’ screens can’t take CommaView’s view, so setup says so and changes nothing on your comma:

- **FrogPilot** (github.com/FrogAi/FrogPilot). It runs openpilot’s older native (Qt) screen, which has no place for CommaView’s view. Video only is in early access.
- **KisaPilot** (github.com/kisapilot/openpilot). Its Python screen is switched off: it runs openpilot’s older native (Qt) screen. Video only is in early access.
- **IQ.Pilot** (github.com/IQLvbs/iqpilot). Since October 2026 it runs on its own IQ.OS; support waits until CommaView can support it as a fork of its own.
- **hikee9123** (github.com/hikee9123/openpilot). It runs openpilot’s older native (Qt) screen.

**Early access: video only for FrogPilot and KisaPilot.** With the Video only flag, setup offers to play their cameras in Live View with CommaView’s own overlay in place of their own screens, changing nothing in the fork. It hasn’t been tried on a comma yet. Without the flag, setup still says they aren’t supported and changes nothing.

## Which comma devices

The comma 3X and the comma four. The comma 3 isn’t supported, including the forks’ comma 3 builds such as xnor-c3: [why the comma 3 isn’t supported](/#faq-comma-3). The app runs on an Android phone, tablet or head unit.

## Release and development branches

Before each release, CommaView’s runtime is built and checked against these forks’ release builds. openpilot’s nightly and sunnypilot’s dev branches are checked each day they change, as an early warning. A development branch can change faster than CommaView: if a change stops CommaView’s hook from loading, your fork’s screen and driving carry on as usual.

## Your fork isn’t listed?

Try it best effort, and ask for it to be listed on the feature board at [my.commaview.com](https://my.commaview.com), or send an idea from the app (Settings › **Support & diagnostics**). A listed fork is checked before each release. See [what’s new](/whats-new) in each release.

## Questions

**Does CommaView change how my fork drives?** No. It adds a small runtime beside your fork and a small hook in its on-screen UI, so CommaView can draw the same path, lanes and alerts. How your car drives doesn’t change.

**Does CommaView work with StarPilot?** Yes, from CommaView 0.0.162. Live View shows StarPilot’s own colours, widgets and camera choice. Turn off StarPilot’s **Disable Logging** setting, which stops the video encoder CommaView streams from.

**Does CommaView work with carrotpilot?** Yes, from CommaView 0.0.164. Live View draws openpilot’s screen for it; what carrotpilot adds to its own screen, such as its navigation and speed cameras, isn’t drawn yet. After carrotpilot updates itself, the app asks for a reboot that brings Live View back.

**Does CommaView work with FrogPilot?** Not yet: it runs openpilot’s older native (Qt) screen, which has no place for CommaView’s view, so setup says it isn’t supported and changes nothing. Video only is in early access for FrogPilot and KisaPilot, for testers.
