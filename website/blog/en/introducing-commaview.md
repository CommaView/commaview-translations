---
title: "Introducing CommaView: local camera streaming for comma devices"
description: "CommaView is an Android app for local comma-device camera streaming, MICI-style overlays, runtime setup, recordings, and drive replays."
date: 2026-05-02
slug: introducing-commaview
tags:
  - CommaView
  - comma device camera streaming
  - Android app
  - openpilot tools
heroLabel: "Product notes"
draft: false
---

CommaView exists because local comma-device camera access should feel like a real product, not a pile of scripts taped to an SSH session.

The goal is simple: pair an Android device with your comma, stream the road camera locally, show useful driving overlays, and make setup boring in the best possible way.

## Why local-first?

CommaView is not trying to be a cloud dashboard. The app talks to your comma device over your local connection and keeps the core workflow close to the hardware.

That matters because a local-first comma camera streaming app can stay fast, understandable, and privacy-aware. No account should be required just to see what your own device is seeing.

## What CommaView handles

The current alpha focuses on the parts that make day-to-day testing less annoying:

- local road camera streaming to Android
- MICI-style path, lane, status, and driver-monitor overlays
- guided runtime setup for the comma-side `commaviewd` service
- drive recordings and replay export
- app/runtime version pairing so testers install compatible builds

## Why Android first?

CommaView is Android-only because Android is the practical target for this workflow: phones, tablets, sideloading, local networking, and car-friendly hardware all line up better there.

That focus lets the app stay sharp instead of watering itself down for every possible platform.

## What comes next

Early tester access will help harden the install flow, verify device compatibility, and improve live overlay alignment across more cars and comma setups.

If you want in, join the early access list on the homepage. We’ll use the blog for release notes, tester updates, and technical notes as CommaView grows.
