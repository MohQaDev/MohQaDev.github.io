---
title: "JoBlood — Donor"
summary: "The donor experience: signup, medical questionnaire, donation scheduling, history, and emergency-request notifications."
weight: 1
tags: ["Flutter", "JoBlood", "Donor"]
---

[← Back to JoBlood overview](/projects/joblood/)

## What the donor can do

- **Sign up** with national ID, name, phone (verified via Firebase OTP), DOB, address, and a short medical questionnaire (allergies, chronic illness, recent meds, gender).
- **Schedule a donation** through a 4-step wizard: pick a lab → pick a date → pick an available time slot → confirm. Booked slots and per-day availability (`free` / `partial` / `full`) are pre-fetched so the calendar feels instant.
- **View donation history** — every past donation with date, lab, blood type, PCV level, and doctor approval status.
- **Edit the medical questionnaire** anytime.
- **Receive emergency requests** — when a lab is critically low on the donor's blood type, an FCM push notification fires to every matching donor in the lab's city.
- **Get notified** when a unit they donated has been used (with a thank-you message).
- **Manage their profile** — change password (with phone OTP), update info, switch between English and Arabic on the fly.

## Screens

![Donor home page](/images/projects/joblood/donor/donorHomePage.png)

![Donor home page (alt)](/images/projects/joblood/donor/donorHomePage2.png)

![Scheduling — step 1](/images/projects/joblood/donor/donorScheduling1.png)

![Scheduling — step 2](/images/projects/joblood/donor/donorScheduling2.png)

![Scheduling — step 3](/images/projects/joblood/donor/donorScheduling3.png)

![Scheduling — step 4](/images/projects/joblood/donor/donorScheduling4.png)

![Scheduling — step 5](/images/projects/joblood/donor/donorScheduling5.png)

![QR check-in display](/images/projects/joblood/donor/QRDisplay.png)
