---
title: "Fix a setup that stops"
description: "What CommaView’s setup messages mean, in the order setup goes: SSH, the install, then pairing. Find the message you see and what to do about it."
topic: troubleshooting
order: 1
kind: fixes
lede: "Setup goes in order: it signs in to your comma over SSH, installs CommaView’s runtime, then pairs your phone with it. When it stops, its message says which part failed, so fix that part first. SSH working only proves the first: a pair code can’t work while the runtime never started."
parked: true
updated: 2026-11-27
needs:
  - title: "In Park"
    text: "The car in Park with openpilot disengaged, and on: without a power harness, switching it off switches the comma off too."
  - title: "One network"
    text: "Your phone on the same Wi‑Fi as the comma, or on its hotspot. A laptop reaching the comma doesn’t prove your phone can."
steps:
  - id: read
    title: "Read what setup says, and copy the details"
    body: |
      When the install fails, setup says what went wrong, whether your comma was put back the way it was, and what to do. Find that sentence under [If it doesn’t work](#fixes) below.

      **Copy details** copies the report support reads: the app’s version, the release, the installer’s last stage and its whole output. Paste it into an email to support@commaview.com when the message says to.
    tabs:
      - label: "The install failed"
        body: "Setup says what failed and offers **Copy details**."
        screen: setup-install-failed
        pins:
          - target: copy-details
            text: "**Copy details**."
          - target: install
            text: "**Install CommaView** tries again once you’ve fixed the cause."
      - label: "SSH failed"
        body: "Before anything is installed, setup says why it couldn’t get onto the comma, such as **SSH authentication failed**, and what to check."
        screen: setup-ssh-failed
        pins:
          - target: error
            text: "What went wrong, and what to check."
  - id: address
    title: "Check the comma’s address"
    body: |
      Setup looks for commas on your phone’s network. If yours isn’t listed, tap **My comma is not listed** and type its IP address. On your comma, it’s under **Settings → Network**: under the network’s name on the Wi‑Fi button on a comma four, or under **Advanced** on a comma 3X.

      The comma has a different address on each network: your home Wi‑Fi, a hotspot, a VPN. Use the one for the network your phone is on now.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "A comma setup found on this network."
      - text: "**My comma is not listed**: type the IP address when it isn’t found."
  - id: pair-code
    title: "Pair with a fresh code"
    body: |
      Pair codes are short-lived and work once. If one is refused, don’t type it again: get a fresh one. After a manual install, the installer shows one; a phone already paired with the comma shows one under **Device settings › Pair another phone or tablet**.
    screen: setup-manual-add
    pins:
      - target: comma-ip
        text: "**Comma IP address**."
      - target: pair-code
        text: "**Pair code**. Hyphen optional."
  - id: runs
    title: "Already installed? Pair instead"
    body: |
      If the comma already runs CommaView, from another phone or an earlier setup, you don’t need to install again. On Home, tap **Add a comma**, then **Enter address and code**, and pair with the comma’s IP and a pair code or an invitation.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "The comma’s IP."
      - target: pair-code
        text: "**Pair code or invitation**."
      - target: pair
        text: "**Pair comma**."
  - id: no-video
    title: "Installed and paired, but no video"
    body: |
      Past pairing, a missing picture is a streaming problem, not an SSH one. Live View says what it sees, such as **Can’t reach this comma**, and reconnects by itself when the comma answers. See [CommaView can’t find your comma](/guides/comma-not-found).
    screen: phone-live-view-unreachable
    pins:
      - target: retry
        text: "**Retry**."
fixes:
  - q: "“SSH authentication failed.”"
    a: "Check the CommaView key is on GitHub (any title), and SSH is on on the comma. If you entered your GitHub username on the comma before adding the key, remove it and enter it again, so the comma fetches your keys again."
  - q: "“Connection refused at 192.168.1.50:22. Make sure SSH is enabled on your comma.”"
    a: "On the comma, go to **Settings → Device → SSH** and turn on SSH."
  - q: "“Connection timed out to …” or “No route to …”"
    a: "Your phone can’t reach that address. Check your phone is on the same Wi‑Fi as the comma, or on its hotspot, that the comma is awake (the car on), and that the IP address is the comma’s address on this network."
  - q: "“Could not find a comma at … Check the IP address.”"
    a: "Nothing answered at that address. Check the IP on the comma’s **Settings → Network**."
  - q: "“This comma’s SSH identity changed since it was last set up.”"
    a: "If you reset or reflashed the comma, run setup again."
  - q: "“CommaView couldn’t make its SSH key on this phone. Try again, or use your own SSH key.”"
    a: "Tap **Try again**, or **Use my own SSH key** to import a key pair you already have on GitHub."
  - q: "“Install queued.”"
    a: "The car was being driven, so the comma queued the install instead of interrupting the drive. Put the car in Park with openpilot disengaged, leave it a minute or two with the car on, then tap **Finish setup**."
  - q: "“The car is being driven, so the install didn’t run.”"
    a: "Put the car in Park with openpilot disengaged, then try again."
  - q: "“Another CommaView install, update or repair is already running on your comma.”"
    a: "Wait a few minutes for it to finish, then try again."
  - q: "“Your comma couldn’t download CommaView.”"
    a: "The comma downloads the runtime itself. Check it’s connected to the internet, over Wi‑Fi or its own SIM, then try again. A phone hotspot with mobile data works."
  - q: "“CommaView’s download reached your comma incomplete or damaged.”"
    a: "Try again. If it happens again, copy the details and send them to support@commaview.com."
  - q: "“Your comma ran out of storage space during the install.”"
    a: "Try again later. If it happens again, copy the details and send them to support@commaview.com."
  - q: "“CommaView doesn’t support the driving software on your comma yet.”"
    a: "Your comma runs software CommaView can’t install on. [Check which forks it works with](/guides/forks). To ask for yours, copy the details and send them to support@commaview.com."
  - q: "“CommaView can’t add its view to … safely”"
    a: "Your fork is one CommaView doesn’t list, and its check found its screen differs where CommaView connects to it. Nothing on your comma was changed. To ask for your fork, copy the details and send them to support@commaview.com."
  - q: "“comma 3 isn’t supported”"
    a: "CommaView works with the comma 3X and comma four. The comma 3’s openpilot release is frozen upstream and draws its screen differently, so CommaView can’t show its overlay."
  - q: "“CommaView didn’t start on your comma after the install.”"
    a: "Restart your comma, then try again. If it happens again, copy the details and send them to support@commaview.com."
  - q: "“Verify failed. Could not reach CommaView API at 192.168.1.50:5002.”"
    a: "The install finished, but your phone can’t reach the runtime. Check your phone is still on the comma’s network, then try again. If SSH works from a computer but not this, the computer is on a network your phone isn’t."
  - q: "“Pair code could not be redeemed. Generate a fresh code and try again.”"
    a: "The code expired, was used already or was typed wrong. Get a fresh one ([step 3](#step-pair-code))."
  - q: "“Pairing failed: CommaView runtime API was not reachable”"
    a: "Your phone can’t reach the comma on that address. Check the hotspot or network, then try again."
  - q: "“CommaView won’t start by itself after a reboot”"
    a: "CommaView is installed, but nothing starts it when your comma boots: your comma’s `/data/continue.sh` has no `exec ./launch_openpilot.sh` line. Once it has one, install CommaView again."
related: [setup, comma-not-found, support-bundle]
---

## The parts setup goes through

Each part needs the one before it, so check them in this order:

1. **SSH**, port 22: how setup gets onto the comma to install. It needs your GitHub key, your GitHub username on the comma, and SSH on.
2. **The install**: the comma downloads the runtime and installs it. Read its result before anything later.
3. **The runtime**, port 5002 on the comma: setup checks it answers, then pairs with it.
4. **Pairing**: a one-time pair code gives your phone a key of its own for the comma.
5. **Video**, ports 8200 to 8202: Live View’s cameras.

If discovery doesn’t find the comma but you know its address, typing it works just as well: discovery is a convenience, and reaching the comma is what matters.

## Safety

Do setup, installs and troubleshooting with the car in Park and openpilot disengaged. Never set up or tap through the app while driving.
