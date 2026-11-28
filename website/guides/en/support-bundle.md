---
title: "Send a support bundle"
description: "Keep diagnostics on, make the problem happen again, then send a report with your phone’s and your comma’s logs from Settings › Support & diagnostics."
topic: troubleshooting
order: 3
kind: walkthrough
lede: "A support bundle is a small zip of what the CommaView app saw on your phone, and what its runtime saw on your comma. It lets us find a problem without being in your car. It holds logs only: no video, no location."
appVersion: "0.0.165"
parked: true
updated: 2026-11-27
needs:
  - title: "Diagnostics on"
    text: "**Keep diagnostics on this phone**, on unless someone turned it off. Check it before the problem happens again."
  - title: "Connected to your comma"
    text: "For your comma’s logs, Home shows your comma **Connected** when you send."
  - title: "Signed in to send"
    text: "Sending needs your beta account. Signed out, **Save as a file** still works."
howItWorks:
  - title: "Your phone"
    text: "Keeps its logs and counters from your last 10 drives."
  - title: "Your comma"
    text: "Adds its runtime’s logs when you tap Send, with location, VIN, IDs, Wi‑Fi names and tokens removed."
    edge: "when you tap Send"
  - title: "CommaView’s team"
    text: "Reads it in private storage, and replies by email."
steps:
  - id: open
    title: "Open Support & diagnostics"
    body: |
      In CommaView, tap **Settings** in the bar at the bottom. On a tablet or head unit it’s in the rail at the side. Tap **Support & diagnostics**, near the end, before About.
    screen: support-settings
    pins:
      - text: "**Support & diagnostics**."
  - id: keep-diagnostics
    title: "Keep diagnostics on this phone"
    body: |
      **Keep diagnostics on this phone** is on unless someone turned it off: the app keeps its logs and counters from your last 10 drives, so a report can say what happened. If it’s off, turn it on, then make the problem happen again.
    screen: support-diagnostics
    pins:
      - target: keep-diagnostics
        text: "**Keep diagnostics on this phone**."
    note: "Diagnostics stay on this phone until you send a report: they’re never uploaded automatically."
  - id: happen-again
    title: "Make it happen again, parked"
    body: |
      Connect to your comma as usual: your phone on the comma’s Wi‑Fi or hotspot, and Home showing your comma **Connected**. Do what went wrong; for example, open Live View, switch to the onroad screen that misbehaves, and leave it there for 10 to 20 seconds. Note roughly when it happened and what you did. A screen recording helps too.
    warn: "Make it happen in Park. If it only happens on the road, let it happen and send the report once you’ve parked: the record waits for you. Never tap through the app while driving."
  - id: open-send
    title: "Open Send to CommaView"
    body: |
      On **Support & diagnostics**, tap **Report a problem or send an idea**.

      Or start from the problem: where the app shows a failure, tap its **Report**; for a recording, choose **Send to CommaView…** in its **Recording actions**. Each opens the same sheet, with what’s relevant filled in.
    screen: support-diagnostics
    pins:
      - target: report
        text: "**Report a problem or send an idea**."
  - id: send
    title: "Choose what goes, and send"
    body: |
      Choose **Problem** and say what happened. Under **Attached**, leave **This phone’s diagnostics** and your comma’s logs on. **See** shows exactly what each one holds. Under the rows, the sheet lists what goes with every report: the app version, your phone’s model and Android version, and your comma’s driving software and setup.

      Tap **Send**: “Sending. It goes in the background and waits for a connection.”
    screen: support-send-feedback
    pins:
      - target: problem
        text: "**Problem** or **Idea**."
      - text: "**Attached**: each row has a switch and **See**."
      - target: send
        text: "**Send**."
    note: "Send while the app is connected to your comma: it asks the comma for its logs when you tap Send. If the comma is off or out of reach, the bundle says why and still holds the app’s own logs."
  - id: save-file
    title: "Or save it as a file"
    body: |
      Support asked for the file itself, or you’re not signed in? Tap **Save as a file** instead of Send. The app builds the same bundle, a small `.zip`, and opens Android’s share sheet. Send it wherever support asked for it: a direct message on Discord, an email, or a cloud drive link.
    screen: support-share-bug-report
    pins:
      - target: save-file
        text: "**Save as a file**."
  - id: afterwards
    title: "Read our reply"
    body: |
      When we answer, the reply comes by email, and it’s on [Your feedback](https://my.commaview.com/feedback) at my.commaview.com with your report. Answer us there until we close it; you can reopen it for 30 days after. **Your requests**, on **Support & diagnostics**, lists them too.
    screen: support-diagnostics
    pins:
      - target: your-requests
        text: "**Your requests**: replies and your conversations with CommaView."
check: "The sheet closes with “Sending. It goes in the background and waits for a connection.”, and the report shows under **Your requests** once it’s sent."
fixes:
  - q: "The bundle has no comma logs"
    a: "The app couldn’t reach your comma when you tapped Send, or its row under **Attached** was off. Check Home shows your comma **Connected** before you open Send to CommaView, and leave your comma’s row on. If the app asks you to pair your comma again, pair it first, then send again."
  - q: "Send reads **Sign in to send**"
    a: "You’re signed out. Tap it to sign in with your beta account, or use **Save as a file**."
  - q: "“The attachments come to more than the 25 MB a report can carry. Turn one off, or use Save as a file.”"
    a: "Turn off an attachment you don’t need, or tap **Save as a file** and send the file where support asks."
  - q: "Nothing happens when I tap Save as a file"
    a: "Android has no app on this device that can take a file. That’s common on head units. [Send it](#step-send) to CommaView instead, or save it from a phone running CommaView."
  - q: "“Couldn’t prepare the report. Check local storage and try again.”"
    a: "The app couldn’t write the bundle, usually because the device is short of storage. Free some space and try again."
related: [setup-troubleshooting, comma-not-found, releases]
---

## What’s in a support bundle

- **This phone’s diagnostics.** CommaView’s diagnostic logs and counters from this phone: the video stream, drawing, connection and recording errors, with the app version and the phone’s model and Android version. With Navigation, also how many place searches of each kind worked or failed, never what you searched for.
- **Your comma’s logs.** With your comma’s row on: the CommaView runtime’s logs, counters and settings, which openpilot processes stopped and why, and out-of-memory lines from the comma’s kernel.
- **Never in a bundle.** No video, no GPS location, no VIN and no raw drive telemetry: a recording you send goes beside the bundle, not in it. An up-to-date comma runtime removes GPS coordinates, VINs, Wi‑Fi names, public IP addresses, tokens and the full dongle ID before it sends its logs.
- **Only when you send.** A bundle leaves your phone only when you tap Send or Save as a file. A file you save goes only where you send it. Local IP addresses, session IDs and version details can remain, so share a bundle only with people you trust.

## Where it goes, and for how long

A bundle you send goes to CommaView’s private storage, where only the CommaView team opens it. It’s deleted 180 days after you send it, or sooner, at once, when you ask us to or delete your account ([Privacy](/privacy)). To ask, email support@commaview.com.

To remove what the app keeps on this phone, tap **Clear local diagnostic data** on **Support & diagnostics**. It never deletes your recordings. To keep only the history of recording errors from then on, turn off **Keep diagnostics on this phone** on the same page.

Not sure where to send it? Ask in the [CommaView Discord](https://discord.gg/UuMhz9K8ft).
