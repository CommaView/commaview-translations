---
title: "Add another phone or tablet"
description: "Give another phone, tablet or car screen its own key to your comma with a 10-minute invitation, and see and remove the phones that have one."
topic: start
order: 4
kind: walkthrough
lede: "Each phone that watches your comma has a key of its own. To add another phone, tablet or car screen, show an invitation on a phone that already has your comma, and type or scan it on the new one. No SSH, no setting up again."
appVersion: "0.0.166"
parked: true
updated: 2026-11-27
needs:
  - title: "A phone with a key"
    text: "One phone already paired with your comma, on CommaView 0.0.166 or later with its runtime. Not yet? [Set up CommaView](/guides/setup)."
  - title: "CommaView on the new one"
    text: "Installed and signed in, on 0.0.166 or later. [Get the app](/guides/setup#step-get-the-app)."
  - title: "The same network"
    text: "Both on the same Wi‑Fi as the comma, or on its hotspot."
howItWorks:
  - title: "Your phone"
    text: "Asks the comma for an invitation: a code or a QR code, good for 10 minutes."
  - title: "The new phone"
    text: "Joins with the invitation and gets a key of its own."
    edge: "local network"
  - title: "Your comma"
    text: "Tells every phone with a key that a new one has one."
steps:
  - id: device-settings
    title: "On your phone, open Pair another phone"
    body: |
      On the phone that already has your comma, open the comma’s **Device settings** from Home, then **Pair another phone**.
    screen: device-settings
    pins:
      - target: pairing-row
        text: "**Pair another phone**: a short-lived code, so another phone or tablet can connect."
  - id: show-invitation
    title: "Show an invitation"
    body: |
      Under **Phones with a key**, **Add another phone** shows an invitation for a phone that doesn’t have this comma yet. Tap **Show invitation**.
    screen: device-pairing
    clip: invitation
    pins:
      - target: show-invitation
        text: "**Show invitation**."
      - text: "The phones with a key to this comma, this one first."
  - id: invitation
    title: "Keep the invitation on screen"
    body: |
      **Add another phone** shows a code in three groups, a QR code and the comma’s IP address. It’s good for 10 minutes and works once. When it runs out, show a new one.
    screen: invitation-dialog
    pins:
      - target: code
        text: "The code to type on the new phone."
      - target: qr
        text: "Or the QR code to scan."
      - text: "**Expires in …**: 10 minutes from when it’s shown."
  - id: add-comma
    title: "On the new phone, add the comma"
    body: |
      On the new phone, tap **Pair a comma that runs CommaView** on **Connect your comma**. With a comma already on it, tap **Add a comma** on Home instead.

      Your comma shows **On this network**. Tap it, or tap **Scan QR code** and scan the invitation. If it isn’t listed, tap **Enter address and code**.
    screen: add-comma
    pins:
      - target: found-comma
        text: "Your comma, found on this network."
      - target: scan-qr
        text: "**Scan QR code** to scan the invitation."
      - target: enter-address
        text: "**Enter address and code** when it isn’t listed."
  - id: pair
    title: "Type the invitation and pair"
    body: |
      Check the **Comma IP**, type the invitation into **Pair code or invitation** (or tap the QR button to scan it), and tap **Pair comma**. The new phone gets a key of its own and shows your comma on Home.
    screen: pair-comma-dialog
    pins:
      - target: comma-ip
        text: "**Comma IP**, filled in for a comma it found."
      - target: pair-code
        text: "**Pair code or invitation**."
      - target: scan-qr
        text: "**Scan pairing QR**."
      - target: pair
        text: "**Pair comma**."
  - id: new-key
    title: "Confirm it on your other phones"
    body: |
      Each phone with a key is told: **A new phone has a key**, with its name and when. Tap **It’s mine**. If it isn’t one of yours, tap **Remove**; **Review phones** opens **Pair another phone**, where every phone with a key is listed.
    screen: new-phone-key-alert
    pins:
      - target: mine
        text: "**It’s mine**, for your own phone or tablet."
      - target: review
        text: "**Review phones** lists every phone with a key."
check: "The new phone shows your comma on Home and opens Live View. On your first phone, **Pair another phone** lists it under **Phones with a key**."
fixes:
  - q: "“Couldn’t join with that invitation”"
    a: "It may be mistyped, have run out, or have been used. Show a new one on the phone that already has this comma (its Device settings, **Pair another phone**, **Add another phone**)."
  - q: "“This comma’s runtime is from before phone keys”"
    a: "Update the comma’s runtime first: [Update your comma’s runtime](/guides/update-runtime). Then show the invitation."
  - q: "“Can’t reach this comma”"
    a: "Both phones must be on the same Wi‑Fi as the comma, or on its hotspot. [Connect in the car](/guides/connect-in-the-car)."
  - q: "“Pairing failed: this comma no longer pairs by code”"
    a: "The comma has stopped taking the old shared token. Add the phone from one that already has a key (its settings, **Add another phone**), or run setup for the comma again."
related: [car-screens, update-runtime, connect-in-the-car, setup]
blogPost: commaview-0-0-166-languages-browser-view
---

## Remove a phone

On a phone with a key, open the comma’s **Device settings**, then **Pair another phone**. Tap **Remove** beside a phone in the list. It can’t reach this comma again until it is added again, with an invitation or by setting the comma up.

## Phones on an older CommaView

Before 0.0.166, every phone sent the comma the same shared token. A phone on 0.0.166 gets its key the next time it connects, without pairing again.

- **Older CommaView apps** on **Pair another phone** says how many more days a phone with an older CommaView can still use this comma with the shared token: 90 days after its first phone gets a key. Until then, **Pair code for an older app** pairs a phone on an older CommaView.
- **Stop now** stops the comma taking the shared token, once every phone that uses it has a key. Phones with an older CommaView stop working with this comma then, and can’t pair again until they’re updated.
- After that, a phone without a key needs CommaView 0.0.166 or later and an invitation.

When you update your comma’s runtime, update CommaView on every device that watches it first, car screens too.
