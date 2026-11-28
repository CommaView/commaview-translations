---
title: "Set up CommaView"
description: "Install the CommaView app on Android, get your comma 3X or comma four ready, and let guided setup install the runtime and pair your comma."
topic: start
order: 1
kind: walkthrough
lede: "CommaView has two pieces: the app on your Android phone, tablet or head unit, and its small runtime on your comma. Install the app, then guided setup in the app puts the runtime on your comma, checks it and pairs it. It takes a few minutes, in Park with openpilot disengaged."
parked: true
updated: 2026-11-27
needs:
  - title: "A comma 3X or comma four"
    text: "On openpilot or a [supported fork](/guides/forks). The comma 3 isn’t supported: its openpilot release is frozen upstream and draws its screen differently, so CommaView can’t show its overlay. [Why the comma 3 isn’t supported](/#faq-comma-3)."
  - title: "An Android device and your invite"
    text: "Android 8 or later, and the email your invite came to. CommaView is in beta: you sign in with the invited account."
  - title: "The same network"
    text: "Your phone and the comma on one local network: your Wi‑Fi, your phone’s hotspot, the comma’s own hotspot or any other they can both join. In the car? [Connect without home Wi‑Fi](/guides/connect-in-the-car)."
  - title: "A GitHub account"
    text: "The comma lets in SSH keys from the GitHub username you give it. CommaView makes the key; you add it to GitHub during setup."
howItWorks:
  - title: "Your phone"
    text: "Makes an SSH key, which you add to GitHub."
    edge: "SSH"
  - title: "Your comma"
    text: "Takes the key from your GitHub username. CommaView installs its runtime beside your fork."
    edge: "local network"
  - title: "CommaView"
    text: "Checks the runtime answers and saves your comma. It reconnects by itself from then on."
steps:
  - id: get-the-app
    title: "Get the app and sign in"
    body: |
      On your Android device, sign in at [my.commaview.com](https://my.commaview.com) with the email your invite came to. Under **Get the app**, tap **Download CommaView**. Its SHA-256 checksum is shown beside it if you want to check the file.

      Open the download. Android asks you to allow installs from your browser: allow it for this install, then turn it back off.

      Open CommaView. It asks once whether to **Help improve CommaView**: **Send** or **Don’t send**. Then it asks you to sign in: tap **Sign in** and use the email your invite came to. After that it works offline while its access pass is valid.
    tabs:
      - label: "Help improve CommaView"
        body: "Crash reports and which driving software your comma runs, never video, drives, places or names. You can change it any time in Settings › **Privacy & sharing**."
        screen: improve-commaview
        pins:
          - target: send
            text: "**Send** crash reports to help fix problems."
          - target: dont-send
            text: "**Don’t send** keeps them on the phone."
      - label: "Sign in"
        body: "During the beta, CommaView needs your invited account. **Sign in** opens your browser."
        screen: sign-in
        pins:
          - target: sign-in
            text: "**Sign in** with the email your invite came to."
    note: "Installing on a head unit or an AI box on your car’s screen? [Car screens](/guides/car-screens) covers its network and pairing it with your comma."
  - id: connect
    title: "Start setting up your comma"
    body: |
      Read the notice, tick that you understand it’s unofficial software and you’re responsible for safe use, and tap **I understand — continue**.

      On **Connect your comma**, tap **Set up CommaView on your comma**.
    screen: onboarding-connect
    pins:
      - target: set-up-on-comma
        text: "**Set up CommaView on your comma**, for a comma that doesn’t run CommaView yet."
      - target: pair-runs
        text: "Already runs CommaView from another phone? **Pair a comma that runs CommaView** instead: [Add another phone or tablet](/guides/another-phone)."
  - id: setup-path
    title: "Pick a setup path"
    tabs:
      - label: "Guided setup"
        body: "Choose **Guided setup** (it’s marked Recommended) and tap **Continue to guided setup**. CommaView makes an SSH key, guides the connection and checks your comma. The next steps follow it."
        screen: setup-choose-method
        pins:
          - target: guided
            text: "**Guided setup**, marked Recommended."
          - target: continue
            text: "**Continue to guided setup**."
      - label: "Manual setup"
        body: "Only if SSH already works from your computer to the comma as user `comma`. Choose **Manual setup**, then **Continue to manual setup**, and run the command from your terminal. When the installer shows a one-time pair code, tap **I ran the command**, enter your comma’s IP and the code, and tap **Add a comma**. [Manual setup from a terminal](#manual-setup-from-a-terminal) has each step."
        screen: setup-manual-instructions
        pins:
          - text: "**Tap to copy** copies the command."
          - target: ran-command
            text: "**I ran the command**, once the installer shows its pair code."
  - id: ssh-key
    title: "Add the SSH key to GitHub"
    body: |
      CommaView makes an SSH key for this phone. Tap **Copy key and open GitHub**: it copies the public key and opens GitHub’s new SSH key page.

      On GitHub, paste the key into the **Key** field, give it any title (CommaView fills one in), then save with **Add SSH key**. Come back to CommaView and tap **Continue**.
    screen: setup-ssh-key
    clip: setup-key
    pins:
      - target: copy-key
        text: "**Copy key and open GitHub**. It says “SSH key copied. Opening GitHub…”"
      - target: own-key
        text: "**Use my own SSH key** imports a key pair you already have on GitHub."
      - target: continue
        text: "**Continue**, once the key is saved on GitHub."
    note: "Already have a key pair on GitHub? **Use my own SSH key** imports it instead. The private key stays on your phone."
  - id: comma-ssh
    title: "Turn on SSH on your comma"
    body: |
      On the comma’s screen, go to **Settings → Device → SSH**:

      1. Enter your GitHub username.
      2. Wait for the comma to fetch your GitHub keys.
      3. Turn on SSH.

      Then come back to CommaView and tap **Continue**.
    screen: setup-enable-comma-ssh
    pins:
      - target: continue
        text: "**Continue**, once SSH is on."
    note: "The comma fetches your keys once, when you enter the username. Entered it before adding the key? Remove it and enter it again, so the comma fetches the keys again."
  - id: choose-comma
    title: "Choose your comma"
    body: |
      CommaView lists the commas on this Wi‑Fi network that already run CommaView, so a comma you’re setting up for the first time usually isn’t there yet. Tap **My comma is not listed** and type its IP address. Then tap **Install CommaView**.

      You’ll find the IP on the comma under **Settings → Network**: under the network’s name on the Wi‑Fi button on a comma four, or under **Advanced** on a comma 3X.
    screen: setup-choose-comma
    pins:
      - target: found-comma
        text: "A comma that already runs CommaView. One saved on this phone is marked **Saved on this phone**."
      - text: "**My comma is not listed**: enter its IP address."
      - target: install
        text: "**Install CommaView**."
  - id: safe-install
    title: "Start the Safe Install"
    body: |
      The **Safe Install** dialog names the comma it installs on. Read the note, then tap **Start Safe Install** once its short countdown ends.
    tabs:
      - label: "The car is in Park"
        body: "If the car is in Park and openpilot isn’t engaged, CommaView installs now."
        screen: setup-safe-install
        pins:
          - target: start-safe-install
            text: "**Start Safe Install**, after its countdown."
      - label: "The car is being driven"
        body: "The comma queues the install and runs it once the car is in Park with openpilot disengaged, so a drive is never interrupted. Setup shows **Install queued**: put the car in Park with openpilot disengaged, wait a minute or two, then tap **Finish setup**."
        screen: setup-install-queued
        pins:
          - target: finish-setup
            text: "**Finish setup**, once the car is in Park."
    note: "Then CommaView connects to the comma over SSH, checks which comma it is, and installs the runtime this version of the app was tested with. It checks the install is answering and saves your comma on this phone. Keep the phone on the same network until it’s done."
    warn: "Keep the car on, in Park. Without a power harness, switching the car off switches the comma off too, which stops the install."
  - id: ready
    title: "CommaView is ready"
    body: |
      Your comma is installed, paired, and reconnects by itself the next time it starts.
    tabs:
      - label: "CommaView is ready"
        body: "Tap **Done**."
        screen: setup-done
        pins:
          - target: finish
            text: "**Done** takes you to Home."
      - label: "Restart to finish setup"
        body: "Sometimes setup says **Restart to finish setup**: the comma streams to your phone after one restart. Tap **Restart comma and finish** with the car off or in Park with openpilot disengaged. openpilot stops for about a minute while it restarts."
        screen: setup-restart-to-finish
        pins:
          - target: restart
            text: "**Restart comma and finish**."
check: "Home shows your car with its comma **Connected**, the runtime and the comma’s address. Tap **Open Live View**: the road plays live, with the path and the car ahead drawn over it. From now on the app finds your comma by itself when your phone and the comma are on the same network, even if its address changes."
fixes:
  - q: "Couldn’t connect over SSH"
    a: "Check SSH is on under **Settings → Device → SSH** on the comma, the GitHub username is yours, and the CommaView key is on that GitHub account. If you added the key after entering the username, remove the username and enter it again so the comma fetches the key."
  - q: "My comma isn’t in the list"
    a: "That’s expected the first time: the list shows commas that already run CommaView. Tap **My comma is not listed** and enter its IP address (**Settings → Network** on the comma: under the network’s name on the Wi‑Fi button on a comma four, or under **Advanced** on a comma 3X). Check the phone is on the same network as the comma and not on a VPN."
  - q: "Setup says “Install queued”"
    a: "The comma saw the car being driven, so it waits. Put the car in Park with openpilot disengaged, wait a minute, then tap **Finish setup**. Leave the car on: without a power harness, switching it off switches the comma off too."
  - q: "Setup says my comma isn’t supported"
    a: "On a comma 3, setup stops and offers **Set up CommaView on a comma 3X or comma four**. On a fork whose screen CommaView can’t add its view to, setup says so and changes nothing. [Check your comma and fork are supported](/guides/forks)."
  - q: "The pair code didn’t work"
    a: "Pair codes are one-time and expire quickly. Run the installer again for a fresh code, and check you typed it as shown (the hyphen is optional)."
  - q: "Connected, but no video"
    a: "Setup and pairing are done; this is the video stream. Check the comma is on and onroad-ready, keep the phone on the same network, and reopen Live View. If it says **Can’t reach this comma**, see [Can’t find your comma](/guides/comma-not-found)."
related: [forks, connect-in-the-car, another-phone, setup-troubleshooting]
---

## Manual setup from a terminal

Only if SSH already works from your computer to the comma as user `comma`.

1. In CommaView choose **Manual setup**, then **Continue to manual setup**. The app shows the command for its runtime on **Install from your terminal**, ready to copy (**Tap to copy**). It looks like this one, which installs the current release’s runtime:

   ```
   curl -fsSL https://commaview.com/commaviewd/install.sh \
     | ssh comma@COMMA_IP bash
   ```

2. Run it from a computer on the same Wi‑Fi network as your comma, with `COMMA_IP` replaced by the comma’s IP address (**Settings → Network** on the comma: under the network’s name on the Wi‑Fi button on a comma four, or under **Advanced** on a comma 3X). Your computer downloads the installer, and SSH runs it on the comma as user `comma`.
3. When the installer finishes, CommaView starts on the comma and shows a one-time pair code.
4. Back in CommaView, tap **I ran the command**. On **Add your comma**, select your comma or enter its IP, type the pair code, and tap **Add a comma**. The app checks the runtime and saves the comma.

## Before your first drive

Try it in Park before you drive.

- Home shows your comma as **Connected**.
- Live View plays and the path moves with the car.
- If the app shows a warning or asks for a repair, sort it out before you drive.
- Set it up so it never needs your attention while driving.

Still stuck? Ask in the [CommaView Discord](https://discord.gg/UuMhz9K8ft), or send feedback from the app. If support asks for logs, [send a support bundle](/guides/support-bundle).
