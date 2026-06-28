---
title: "ISS — Client mode (Android over SSH)"
summary: "Run the app on Android and connect to the Linux host over SSH. Same dashboard, same panels — every command is shipped over the wire by dartssh2."
weight: 2
tags: ["Flutter", "ISS", "Android", "SSH"]
---

[← Back to ISS overview](/projects/iss/)

## What client mode does

Client mode is for the **Android phone**. On the connection screen you tap **Connect Remotely** and fill in:

- IP address (the LAN IP the host showed you)
- SSH port (usually 22)
- Username
- Password

The app then:

1. Opens a TCP socket to the host on the SSH port.
2. Runs the SSH handshake using `dartssh2` (a pure-Dart SSH client — necessary because `dart:io`'s `Process` doesn't work on Android).
3. Authenticates with the password you provided (the `onPasswordRequest` callback simply returns the stored password).
4. Opens the dashboard with `runner = SshRunner(client)` — every panel sends its commands across the SSH connection byte-for-byte.

From here, every panel behaves identically to host mode — same UI, same logic — but commands run on the remote server. The embedded Python ransomware detector? Still works, because the Python source is sent as a shell command and executed on the server.

> The one feature missing in client mode is CSV-persistence for the Traffic panel — the app can't easily write to a persistent file on Android with the same lifecycle, so the chart starts empty each session.

## Demo

<video controls width="100%" preload="metadata" src="/images/projects/iss/client/demo.mp4">
Your browser doesn't support embedded video.
</video>
