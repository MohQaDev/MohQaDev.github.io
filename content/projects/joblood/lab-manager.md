---
title: "JoBlood — Lab Manager"
summary: "The lab manager experience: storage and temperature monitoring, staff acceptance, lab-to-lab transfers, low-stock thresholds, and a manager↔admin chat."
weight: 2
tags: ["Flutter", "JoBlood", "Lab Manager"]
---

[← Back to JoBlood overview](/projects/joblood/)

## What the lab manager can do

- **Storage dashboard** — live count of blood units per type, color-coded against the per-type low-stock thresholds the manager sets.
- **Live temperature graphs** — drawn with `CustomPainter`, with a green band marking the medically safe **2–6 °C** range. Readings outside the range drop each unit's *safety percentage* (a fuzzy-logic score 0–100); units that hit zero are flagged terminated.
- **Donation log** — record new donations, generate a Code 128 barcode label for the bag, doctor-approve / reject.
- **Blood-unit management** — add / update / mark as used; auto-calculated expiry; each used unit triggers a "thanks, your donation was used" notification to the donor.
- **Lab-to-lab transfer requests** — request units from another lab, counter-offer reduced quantities, accept / cancel, mark **on the way** / **received**.
- **Emergency requests** — fire a fan-out FCM notification to every donor of a target blood type in the lab's city, with an optional message.
- **Staff & sub-manager acceptance** — accept or reject users who applied to join the lab.
- **Chat with the admin** for escalation / coordination, with unread counts.

> **Note on Lab Staff:** Lab Staff uses the **same screens** as Lab Manager with reduced privileges — see the dedicated **[Lab Staff page](/projects/joblood/staff/)** for what's gated off.

## Screens

![Staff home page](/images/projects/joblood/lab-manager/staff_home_page.png)

![Menu](/images/projects/joblood/lab-manager/menu.png)

![Blood storage dashboard](/images/projects/joblood/lab-manager/blood_storage.png)

![Upcoming schedules](/images/projects/joblood/lab-manager/upcoming_schedules_page.png)

![Add or remove staff](/images/projects/joblood/lab-manager/add_or_remove_staff_page.png)

![Staff info](/images/projects/joblood/lab-manager/staff_info.png)

![Edit user info](/images/projects/joblood/lab-manager/edit_user_info.png)

![Blood-unit request to another lab](/images/projects/joblood/lab-manager/blood_unit_request_to_other_lab.png)

![Emergency blood request to donors](/images/projects/joblood/lab-manager/emergency_blood_request_to_user.png)

![Manager chat](/images/projects/joblood/lab-manager/manager_chat.png)

> A full walkthrough video of the lab side lives on the **[JoBlood overview page](/projects/joblood/#demo)**.
