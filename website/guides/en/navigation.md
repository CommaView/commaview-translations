---
title: "Navigate with your own Stadia Maps key"
description: "Add your Stadia Maps key, search for a place on Home, pick a route and follow its turn card and spoken prompts in Live View. Send the place to your comma, too."
topic: navigation
order: 1
kind: walkthrough
lede: "**Navigation** guides you to a place in Live View. Search for it on Home with **Where to?**, pick a route, tap **Start**, then follow the turn card and spoken prompts. Routes come from Stadia Maps on your own key, which stays sealed on your phone. Guidance is display only and never controls the car."
appVersion: "0.0.167"
parked: true
updated: 2026-11-27
needs:
  - title: "Signed in"
    text: "CommaView 0.0.167 or later, signed in with your beta account. Navigation isn’t offered signed out."
  - title: "A Stadia Maps key"
    text: "An API key from your own Stadia Maps account. Routes are asked for under your account and its terms."
  - title: "Vehicle location on"
    text: "Guidance follows your comma’s GPS. Turn on **Vehicle location** for your comma on Home."
  - title: "Internet on your phone"
    text: "For searches and routes. They go over mobile data when the comma’s Wi‑Fi has no internet."
howItWorks:
  - title: "Where to?"
    text: "Finds places near your comma, from OpenStreetMap’s data (Photon)."
    edge: "your key"
  - title: "Stadia Maps"
    text: "Plans the routes, asked by your phone with your key. Nothing goes through CommaView."
  - title: "Live View"
    text: "Guides you from your comma’s position: the turn card, the map and spoken prompts."
steps:
  - id: open
    title: "Open Maps & navigation"
    body: |
      Tap **Settings**, then **Maps & navigation**. Signed in, it’s the row where Offline maps used to be.
    screen: support-settings
    pins:
      - target: maps-row
        text: "**Maps & navigation**."
  - id: get-key
    title: "Get a key from Stadia Maps"
    body: |
      Under **Your Stadia Maps key**, **API key** says **Not added**. Tap **Get a key from Stadia Maps**: it opens Stadia’s sign-up in your browser. Sign up, then copy your API key from your Stadia Maps dashboard.
    screen: settings-maps-navigation
    pins:
      - target: own-key-panel
        text: "**Your Stadia Maps key**: “Routes need your own Stadia Maps key…”"
      - target: get-key
        text: "**Get a key from Stadia Maps** opens Stadia’s sign-up."
      - target: add-key
        text: "**Add**, once you’ve copied your key."
    note: "Stadia’s site isn’t pictured: it’s theirs. Its dashboard shows your key’s use, plan and limits."
  - id: add-key
    title: "Paste it, then Check and save"
    body: |
      Back in CommaView, tap **Add**. Tap **Paste** to put your key in the field, then **Check and save**. CommaView asks Stadia Maps for one short route between two fixed points, nothing of yours, to check the key: **Checking with Stadia Maps…**. Once it’s taken, **API key** shows it masked, such as **•••• e1f0**.
    screen: stadia-key-dialog
    clip: stadia-key
    pins:
      - target: key-field
        text: "**Your Stadia Maps API key**, masked."
      - target: paste
        text: "**Paste** from the clipboard."
      - target: check-and-save
        text: "**Check and save**."
    note: "“Kept on this phone only, sealed. Checked with one short route to Stadia Maps before it’s kept.” It’s never in a support bundle or a crash report."
  - id: where-to
    title: "Tap Where to? on Home"
    body: |
      Parked, tap **Where to?** on Home, under your comma’s card. Type a place or an address, or tap the microphone to say it. Once you’ve saved them, **Home** and **Work** are one tap away on the card.
    screen: home-where-to
    clip: navigation-search
    pins:
      - target: search
        text: "**Where to?** opens the search."
      - target: voice
        text: "**Where to? by voice**."
      - target: home-chip
        text: "**Home**, once you’ve saved it."
  - id: pick
    title: "Pick the place"
    body: |
      Results are near your comma, each with its address and distance, then your saved and recent places. Tap the one you want.
    screen: navigation-search
    pins:
      - target: search-field
        text: "**Search places or addresses**."
      - target: first-result
        text: "A result, with its address and distance from your comma."
    note: "Typing is off while the car moves: “Typing is off while the car moves. Use voice or a saved place.”"
  - id: start
    title: "Choose a route and tap Start"
    body: |
      The route preview shows the route on a map, the time, the distance and when you’d arrive. Each route has a chip: **Fastest**, **Route 2** and so on. Tap **Start**: guidance begins and Live View opens.

      **Save as Home** and **Save as Work** keep the place for one tap on Home.
    screen: navigation-route-preview
    pins:
      - target: routes
        text: "The routes: **Fastest**, **Route 2**…"
      - target: start
        text: "**Start**."
      - target: save-home
        text: "**Save as Home**, and **Save as Work** beside it."
  - id: follow
    title: "Follow it in Live View"
    body: |
      The turn card shows the next turn: its arrow, the distance, the instruction and the step after it, and when you’ll arrive. A spoken prompt comes about 20 seconds before each turn, another just before it, and one as you arrive. In CommaView’s own onroad screen, chevrons are painted in your lane, and across the turn’s exit.

      Miss a turn and a new route comes within seconds. The trip ends by itself once you’ve arrived and switched off.
    tabs:
      - label: "Phone"
        body: |
          Upright, the turn card and the map sit under the video.
        screen: phone-live-view-navigation
        pins:
          - target: turn-card
            text: "The turn card."
          - target: end
            text: "**End navigation**."
          - target: mute
            text: "**Mute guidance voice**."
          - target: map-button
            text: "**Map** hides the map for the trip, and brings it back."
      - label: "Car screen"
        body: |
          On a head unit, where there’s room beside the video, the map and the turn card sit there in a panel of their own. Where there isn’t, CommaView’s screen blends the map into the video’s corner. Drag the divider to change the panel’s width.
        screen: car-live-view-navigation
        pins:
          - target: turn-card
            text: "The turn card."
          - target: divider
            text: "The divider, to change the map’s width."
          - target: map-button
            text: "**Map**."
    warn: "Set the trip up parked. Don’t tap through CommaView while you drive: the turn card and the voice are there so you don’t have to, and openpilot’s and your car’s own alerts come first."
  - id: send
    title: "Send the place to your comma, if your fork takes one"
    body: |
      Under **Start**, the route preview has **Send to comma** for forks whose own navigation takes a destination: StarPilot, carrotpilot, and openpilot’s navigation (alpha), with sunnypilot’s from it. Other forks don’t show it.

      Tap it. CommaView asks first and says what the fork does to driving with its settings now, such as slowing down for turns. Tap **Send**: “Sent to your comma. StarPilot plans its own route there.” The fork routes with its own service, so its route may differ from CommaView’s. **Clear from comma** takes it off again, and ending the trip clears it too.
    screen: send-to-comma-dialog
    pins:
      - target: send
        text: "**Send**."
    note: "**Send every trip to this comma**, under Send to comma, sends each trip when you tap Start. It pauses by itself if the fork’s driving settings change, until you agree again."
check: "In **Maps & navigation**, **API key** shows your key masked, and the route preview says **Routing by Stadia Maps · Guidance is display only and never controls the car.**"
fixes:
  - q: "“Add your own Stadia Maps key to get routes: Settings › Maps & navigation.”"
    a: "No key is kept yet. Tap **Add your key** in the route preview, or follow [steps 2 and 3](#step-get-key). Where to?, search and places work without one."
  - q: "“Stadia Maps didn’t accept this key (401). Check that it’s copied whole from your dashboard.”"
    a: "Copy the key again from your Stadia Maps dashboard, whole, and paste it once more."
  - q: "“That isn’t a Stadia Maps key.”"
    a: "What you pasted isn’t shaped like an API key, so nothing was sent. Copy the API key from your Stadia Maps dashboard: letters, digits and hyphens."
  - q: "“Stadia Maps refused this key (403): its plan may not include routing.”"
    a: "Check your plan in your Stadia Maps dashboard."
  - q: "“Your Stadia Maps key is over its limit (429)”"
    a: "Its credits for this month are used up, or it asked too often just now. Check it in your Stadia Maps dashboard. The app doesn’t ask with it again for five minutes."
  - q: "“Couldn’t reach Stadia Maps to check the key. Check this phone’s internet connection and try again.”"
    a: "Your phone has no internet just now. Try again with mobile data or a Wi‑Fi that reaches the internet."
  - q: "There’s no **Where to?** on Home"
    a: "Navigation is for signed-in members from CommaView 0.0.167. Signed out, or with a pass that doesn’t check out, it isn’t offered. It’s off in mainland China."
  - q: "The turn card says “Vehicle location is off”"
    a: "Guidance needs your comma’s position. Turn on **Vehicle location** for this comma on Home."
  - q: "The turn card says “Waiting for GPS”"
    a: "Guidance starts with your comma’s first fix. Give it a moment under open sky."
  - q: "“That’s too far for one trip”"
    a: "Navigation plans routes to places up to 1,500 km (930 miles) away. Choose a stop on the way, then carry on from there."
  - q: "**Send to comma** isn’t there"
    a: "It shows only in the route preview, and only for a fork whose navigation takes a destination: StarPilot, carrotpilot, or openpilot’s or sunnypilot’s navigation (alpha)."
  - q: "“Can’t reach your comma to send it this trip.”"
    a: "Connect this phone to the same network as your comma, then tap **Try again**."
  - q: "“openpilot’s navigation (alpha) is off on your comma.”"
    a: "Tap **Turn on navigation (alpha)**, parked. On release builds that turn it off each time they start, it can’t be kept on yet."
related: [live-view, car-screens, overlays]
---

## The map in Live View

**Settings › Maps & navigation › Live View map** chooses where it goes:

- **Layout**: **Automatic** (beside the video where there’s room, else in the corner), **Beside the video**, or **In the corner**. The comma 3X, comma four, StarPilot and Surround screens always show the map beside the video.
- **Width beside the video** is set by dragging the divider in Live View. **Reset** puts it back.
- **Map theme**: **Same as the app** (the default: light maps while CommaView is light, dark while it’s dark), **Auto** (light from sunrise to sunset where your comma is), **Same as the phone**, **Light** or **Dark**. It applies to every map: Live View’s, Home’s location card, Vehicle location and the route preview.

## Spoken guidance and your places

- **Spoken guidance** turns the prompts off and on. The turn card’s speaker, **Mute guidance voice**, is the same setting.
- **Your places**: **Home** and **Work**, and **Recent places**, kept on this phone. **Clear** takes the recent ones off.

## A place from another app

In Google Maps or another maps app, share a place and choose **Navigate with CommaView**. Its route preview opens on Home, as a saved place’s does.

## Mapbox

If your account offers it, Settings › Maps & navigation can route with your own Mapbox token instead of Stadia Maps.

## Privacy

Your Stadia Maps key is kept on this phone only, sealed, and is never logged or put in a support bundle. Routes go from your phone to Stadia Maps with it; nothing goes to CommaView’s account service. Searches go to Photon, near your comma’s position. Clearing your key, or signing out, takes it off the phone.

## Safety

Set up a trip parked, and let the turn card and the voice guide you. Navigation is display only: it never steers, brakes or changes what openpilot does. Don’t operate CommaView while driving: keep your eyes on the road and your hands on the wheel, as openpilot asks.
