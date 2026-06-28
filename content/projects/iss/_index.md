---
title: "ISS Dashboard — Mobile SOC for Linux"
summary: "Turns your phone into a live Security Operations Center for a Linux server. One Flutter codebase, two modes (Host / Client over SSH), 8 panels — traffic, journal, Fail2Ban, firewall, ransomware/entropy detector, services, Lynis & Nmap, and an interactive terminal."
date: 2025-05-01
weight: 2
cover:
  image: "/images/projects/iss/ISSLogo.png"
  alt: "ISS Dashboard logo"
  relative: false
tags: ["Flutter", "Dart", "Security", "SSH", "Linux"]
---

## What it is

**ISS Dashboard** is a mobile + desktop security monitoring app built for a university information security course. It turns your phone into a live **SOC (Security Operations Center)** panel that watches a Linux server in real time.

The big idea: the Linux machine you want to monitor runs the app in **host mode**, and an Android phone runs the same app in **client mode** and connects over SSH. After connecting, both show the same dashboard — every button, every command, every piece of data flows through the SSH connection. The phone never touches the server's internals directly.

---

## Architecture in one paragraph

The core abstraction is a `CmdRunner` interface with two implementations:

- **`LocalRunner`** — `Process.run` / `Process.start` (host mode, runs commands locally).
- **`SshRunner`** — `dartssh2` (client mode, ships commands over SSH).

Every panel calls thin `runCmd(...)` / `streamCmd(...)` wrappers and never knows which runner is underneath. One codebase, two machines, zero conditional logic in the UI.

---

## The 8 panels

Organized into 4 tabs. All panels stay alive in memory via `IndexedStack` so their timers and streams never reset when you switch tabs.

**Tab — Network**
1. **Traffic** — live RX/TX bar chart from `/proc/net/dev`, with a rolling accumulator that aggregates seconds → hours → days → months. CSV-persisted in host mode.
2. **Journal** — streaming `journalctl -f` with color-coded severity.

**Tab — Threats**
3. **Fail2Ban** — lists jails, banned IP counts, one-tap unban.
4. **Firewall** — UFW / iptables auto-detected; add / delete rules through a form.
5. **Entropy Monitor** — a ransomware detector. An embedded Python script walks `/proc/<pid>/fd/`, computes Shannon entropy on open sensitive files, and flags sudden jumps (≥ 2.0 bits to ≥ 6.5) as an **Encryption Alert** — one-tap `kill -9` on the offending process.

**Tab — System**
6. **Services** — running systemd services.

**Tab — Tools**
7. **Pentest** — Lynis security audit and Nmap scans with report history.
8. **Terminal** — an interactive shell over the same `CmdRunner`.

---

## Tech stack

| Layer        | Tech                                                      |
| ------------ | --------------------------------------------------------- |
| **UI**       | Flutter / Dart — Android + Linux desktop, single codebase |
| **SSH**      | `dartssh2` (pure-Dart SSH client)                          |
| **Local**    | `dart:io` `Process.run` / `Process.start`                  |
| **Tools**    | Wraps Linux native tools: `journalctl`, `fail2ban-client`, `ufw` / `iptables`, `lynis`, `nmap`, embedded Python 3 |

---

## Walkthroughs by mode

The app has two modes that use the same dashboard but differ in setup and authentication. Each link has screenshots and a short demo video.

- **[Host mode](/projects/iss/host/)** — running on the Linux machine being monitored.
- **[Client mode](/projects/iss/client/)** — running on Android, connected over SSH.
