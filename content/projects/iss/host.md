---
title: "ISS — Host mode (Linux)"
summary: "Run the app on the Linux machine being monitored. Starts sshd, detects the local IP, and opens the dashboard directly with LocalRunner."
weight: 1
tags: ["Flutter", "ISS", "Linux"]
---

[← Back to ISS overview](/projects/iss/)

## What host mode does

Host mode is for the **Linux machine you want to monitor and harden**. When you tap **This Machine** on the connection screen, the app:

1. Starts `sshd` if it's not already running (so a phone can connect later).
2. Detects the machine's LAN IP and shows it on screen — you'll type this into the phone.
3. Opens the dashboard with `runner = LocalRunner()` — every panel runs its commands locally via `Process.run` / `Process.start`.

Everything inside the dashboard then behaves exactly like it would in client mode, but with zero network round-trip and full filesystem access — which is why **CSV persistence for the Traffic panel only runs in host mode** (`/tmp/iss_traffic.csv` is read on launch and appended to every second).

## Demo

<video controls width="100%" preload="metadata" src="/images/projects/iss/host/demo.mp4">
Your browser doesn't support embedded video.
</video>
