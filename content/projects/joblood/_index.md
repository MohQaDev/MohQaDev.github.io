---
title: "JoBlood — Open-Source Blood Bank System"
summary: "Full-stack blood bank management system that digitizes the entire donation lifecycle. Flutter + Shelf/Dart + PostgreSQL, four user roles, bilingual EN/AR, Firebase auth, FCM push notifications. University final-year project."
date: 2025-09-01
weight: 1
cover:
  image: "/images/projects/joblood/fullLogo.png"
  alt: "JoBlood logo"
  relative: false
tags: ["Flutter", "Dart", "Shelf", "PostgreSQL", "Firebase", "Docker"]
---

## What it is

**JoBlood** is a full-stack, multi-role blood bank management system that digitizes the entire donation lifecycle — from donor scheduling and staff-recorded donations to lab storage monitoring and administrative oversight. Built as my **university final-year project** at PSUT — full feature set shipped.

---

## Tech stack

| Layer        | Tech                                                                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| **Frontend** | Flutter / Dart — responsive cross-platform (mobile, web, desktop)                                                                     |
| **Backend**  | Shelf + shelf_router (stateless REST API, 30+ endpoints)                                                                              |
| **Database** | PostgreSQL — 10+ tables with relational constraints, foreign keys, and business rules (unique booking, auto-calculated expiry, blacklist checks) |
| **Auth**     | Firebase Auth (ID tokens, JWT-style) + Firebase Phone Auth (OTP)                                                                       |
| **Push**     | Firebase Cloud Messaging (FCM)                                                                                                         |
| **Deploy**   | Docker (containerized for streamlined deployment + environment consistency)                                                            |
| **State**    | Vanilla `ValueNotifier` — no external state management packages                                                                        |

---

## Highlights

- **Four user roles** with separate role-based home pages: Donor, Lab Staff, Lab Manager, Admin.
- **4-step donation scheduling wizard** for donors.
- **Live temperature graphs** for blood storage drawn with `CustomPainter`, color-coded against the medically safe 2–6 °C range.
- **Bilingual UI** — instant English / Arabic toggle, RTL-aware, driven by a single global `ValueNotifier`.
- **Lab-to-lab transfer requests** with counter-offers and accepted/in-transit/received states.
- **Emergency requests** that fan out FCM push notifications to every donor of a matching blood type in the lab's city.
- **Manager ↔ Admin chat**, unread counts, real-time-ish notification polling.
- **Barcode label generation** (Code 128) for printed blood-bag labels.

---

## Walkthroughs by role

The app behaves differently depending on who's logged in. Each link below shows the screens, key flows, and a short demo video for that role.

- **[Donor](/projects/joblood/donor/)** — schedule donations, view history, get notified on emergencies.
- **[Lab Manager](/projects/joblood/lab-manager/)** — manage storage, staff, lab-to-lab requests, temperature monitoring.
- **[Lab Staff](/projects/joblood/staff/)** — same screens as the manager with privileged actions stripped out (no approvals, no lab-config edits, no transfer-request authoring).
- **[Administrator](/projects/joblood/administrator/)** — system-wide oversight: labs, managers, configuration.

---

## Sign-up & login

![Home screen](/images/projects/joblood/home/Home_Screen.png)

![Login](/images/projects/joblood/home/Login.png)

![Signup](/images/projects/joblood/home/Signup.png)

![Phone OTP](/images/projects/joblood/home/OTP.png)

---

## Demo

<video controls width="100%" preload="metadata" src="/images/projects/joblood/demo.mp4">
Your browser doesn't support embedded video.
</video>
