---
title: "JoBlood — Lab Staff"
summary: "The day-to-day lab role: scan donor QRs on arrival, record donations, print barcoded blood-bag labels, monitor storage and temperature. Same screens as Lab Manager, with the privileged actions stripped out."
weight: 3
tags: ["Flutter", "JoBlood", "Lab Staff"]
---

[← Back to JoBlood overview](/projects/joblood/)

## What lab staff can do

Lab Staff renders the **same screens as the [Lab Manager](/projects/joblood/lab-manager/)** — the UI is the same code path, the role check happens inside each handler. Day-to-day operational work:

- **Staff home** — today's scheduled donations for the lab, current storage temperature with a red banner when out of range, quick links to add donations, scan a blood unit, and view the donation log.
- **Scan donor QR on arrival** — opens the camera, decodes the donor's `userID` from a `qr_flutter` payload, looks them up.
- **Record donations** — fill the donation form, `INSERT INTO donation_log`, auto-create the matching `blood_unit` with the next 9-digit barcode (year-prefixed).
- **Print barcoded labels** — Code 128 SVG for the blood bag, drawn from the `barcode` Dart package.
- **Scan blood-unit barcodes** — for in-storage lookups and updates (e.g. marking `is_safe` after lab tests).
- **View the donation log and upcoming scheduled donations** — same lab-wide queries the manager uses.
- **View blood storage and the live temperature graph** — read-only on the thresholds.

## What lab staff **cannot** do (manager-only)

The backend gates these behind `_isManagerOrAdmin` (role id ≥ 3), so the relevant buttons / forms are hidden in the staff build:

- **Accept / reject staff applicants** — the *Add or remove staff* page is manager-or-admin. Staff can't approve newcomers or remove other staff.
- **Edit lab info** — working hours, address, lab name, and the per-blood-type minimum-stock thresholds (`minCounts`) are manager-editable only.
- **Lab-to-lab transfer requests** — creating a request, sending counter-offers, and accepting / cancelling transfers are manager actions. Staff sees the list, not the controls.
- **Emergency fan-out requests** — the FCM broadcast to every donor of a given blood type in the lab's city is triggered from the manager UI.
- **Manager ↔ Admin chat** — escalation thread is the lab manager's, not staff's.

> No dedicated screenshots for this role on purpose — every screen lives on the **[Lab Manager](/projects/joblood/lab-manager/)** page. The staff build just renders fewer buttons.
