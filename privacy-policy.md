---
title: Offshift privacy policy
---
# Offshift privacy policy

**Last updated:** 22.10.2026

Offshift is a roster and shift-planning app for shift workers, made by Brandon Cox, Brisbane, Queensland, Australia ("we", "us"). This policy explains what information the app handles, who it goes to and how to have it deleted. We follow the Australian Privacy Principles in the *Privacy Act 1988* (Cth).

**Questions or requests:** support@offshift.info

## The short version

- **Your roster, events, diary, tasks and settings stay on your phone.** Offshift works fully without an account, and we never receive that data in bulk.
- An **account is optional**. You only need one for the online AI assistant, for photo import of your roster, and for Offshift Pro.
- When you use the AI assistant or photo import, **only what that request needs** is sent to our server and on to **OpenAI in the United States** to be processed. We don't store what you ask or what comes back.
- We use a handful of service providers (listed below). We don't sell your information, show ads or run advertising trackers.
- You can delete your account in the app or by email. One thing is kept after deletion: a one-way scrambled (hashed) version of your email address, so the three free photo imports can't be reset. Details in section 4.

## 1. What stays on your phone

These are stored only in the app's private storage on your phone, and we can't see them:

- your roster (shift types and which day is which shift), events and templates, all-day events, diary notes, tasks, categories and statistics;
- your preferences, including activities, sleep times, shift rules and any notes you write for the assistant;
- calendar links you add (kept in the phone's secure storage) and events read from your phone's calendars (read-only);
- a local log of AI usage (counts only), and any backups or exports you create yourself.

If you uninstall the app, this data goes with it. Backups and exports you make (JSON, CSV, ICS) go wherever you choose to save or share them; that is up to you.

Reminders are notifications created on your phone. No notification service of ours is involved.

## 2. Accounts

You can sign in with **Google** or with a **6-digit code sent to your email**. We use **Supabase** (a database and sign-in service) for this; our project is hosted in **Sydney, Australia**.

What we hold about your account:

| What | Why |
|---|---|
| Your email address. If you use Google sign-in, also the Google account ID and the name and picture Google provides. Sign-in times. | To sign you in |
| A profile: when it was created, whether AI is switched on, your plan and monthly limits, and how many free photo imports you have used | To run the AI limits and the free allowance |
| A usage log: time, kind of request, AI model, number of tokens and cost. **Counts only, never what you wrote** | To enforce monthly and daily limits and keep costs under control |

Sign-in codes are emailed from noreply@offshift.info through **Resend**, an email delivery service based in the United States, so Resend handles your email address and the code to deliver them. When you ask for a code, an anti-abuse check from **Cloudflare (Turnstile)** runs; it may look at technical details of your device and connection to tell people from bots.

Like most online services, Supabase and its hosting providers record technical logs, such as IP addresses and timestamps, when your phone contacts them. We don't use these to identify you.

## 3. The AI assistant and photo import

By default the assistant is **offline**: a rule-based helper on your phone that sends nothing anywhere. The online assistant is used only when you are signed in, your plan includes it, and you are within your monthly limit.

**What is sent.** Each request goes from your phone, over an encrypted connection, to our server (Supabase, Sydney), which passes it to **OpenAI**. We send only what the request needs:

- *Every request:* the text you typed (up to 2,000 characters), today's date and weekday, the day you opened the chat from, and the **names** of your event categories, shift types and templates.
- *Bigger planning requests:* the assistant can ask, one piece at a time, for the roster, events and all-day events for the days involved (titles, times, categories), your planning preferences and any **planning notes you wrote for the assistant**, free-time calculations, and summary statistics. It gets your **diary notes and tasks only if your request is about them**.
- *Never sent:* event notes, calendar names and locations, calendar links, backups, public holidays, your email address or account ID, or any other data in the app.

**Roster photo import.** Nothing is sent until you tap **Send** on a screen that shows what will be sent. Only the two strips you cropped (the row of dates and your own row) are sent, as images, plus today's date. The original photo never leaves your phone. Please keep colleagues' names out of your strips; if a name is inside a strip, it is in the image that is sent.

**What happens to it.** Our server checks your account and limits, forwards the request to OpenAI and returns the answer. **We do not store or log what you ask or what comes back**; it exists in memory while the request runs. We keep only the usage counts described in section 2.

**OpenAI** processes these requests on its servers in the **United States**. We ask OpenAI not to store them. OpenAI's API terms say it doesn't train its models on API data by default and may keep API requests for a limited period for abuse monitoring. OpenAI may keep API requests for up to 30 days to monitor for abuse, then deletes them. Our organisation does not have a zero-retention agreement. OpenAI's own privacy policy explains how it handles data.

**Sending information overseas (APP 8).** Sending your request to OpenAI discloses personal information to an overseas recipient in the United States. By using the online assistant or photo import you agree to that. We take reasonable steps to make sure it is handled consistently with the Australian Privacy Principles, but OpenAI is not bound by the Privacy Act and we can't guarantee how it handles the data. If you don't want this, don't use the online features: the rest of Offshift works without them. Your account data stays in Australia (Supabase, Sydney). Sign-in emails are delivered through Resend in the United States, and crash reports are processed by Sentry in the European Union (section 6).

## 4. The photo-import allowance (the email hash we keep)

Every person gets **3 free roster photo imports**. To stop that allowance being reset by deleting an account and signing up again, we keep a record made from your email address: we lowercase it and scramble it with a secret key (an HMAC-SHA256 hash), and store the result next to a count of imports used.

- It is **one-way**: we can't turn it back into your email address, and it isn't stored with your name or anything else.
- It is **not deleted when you delete your account**, because deleting it would defeat its purpose. Our reason for keeping it is to prevent misuse of a free allowance that costs us money to provide.
- You can ask us to remove it by emailing us. Removing it means your free allowance can be used again.

## 5. Purchases (Offshift Pro)

Offshift doesn't sell anything in the app yet. If we add purchases, we'll update this policy before they go live.

## 6. Crash reports

Release builds send crash and error reports to **Sentry**, so we can fix bugs. They contain technical details: the app version, Android version, device model and the code location of the error. We set the app **not to send personal information**, and we strip request text, event titles, notes, roster data, emails and tokens from reports before they are sent. Sentry processes and stores reports in the **European Union** and deletes them after **90 days**.

## 7. Other services that may see technical data

- **Expo (EAS Update):** the app checks Expo's servers for app updates. As with any download, that reveals your IP address and the app and Android version.
- **Google Play:** installing and updating the app is between you and Google.
- **Calendar links you add:** the app fetches the link directly from the calendar's host (for example your employer's or Google's server), which sees your IP address as with any web request.
- **Operational email (Resend):** we use **Resend** to email ourselves a daily summary and alerts about how the service is running. These contain totals and error counts, plus a short scrambled code for the highest-spending account. They contain no email addresses or user content, and aren't sent to users.

## 8. How long we keep things

| What | How long |
|---|---|
| Account, profile and usage log | Until you delete your account |
| AI request and answer content | Not kept by us. Held briefly by OpenAI as described in section 3 |
| Email hash for the free-import allowance | Kept after deletion (section 4) |
| Server technical logs (codes, costs, timings; no content) | About 7 days, under Supabase's log retention |
| Crash reports | 90 days (Sentry) |

## 9. Deleting your account and your rights

- **In the app:** Settings → Account → Delete account. This removes your sign-in, profile and usage log. Your roster and other data stay on your phone until you remove them or uninstall.
- **By email:** write to support@offshift.info from the address on the account. We'll delete it within 30 days.
- Step by step, including what is kept: the [account deletion page](delete-account).

You can also ask for access to, or correction of, the personal information we hold about you, using the email above. We'll respond within a reasonable time (normally 30 days). Because we hold so little, this is usually your email, profile and usage counts.

## 10. Security

Connections between the app and our servers are encrypted. Sign-in tokens are kept in the phone's secure storage. Server keys are never in the app. No method is perfectly secure, and we can't guarantee the safety of data on your phone or in transit.

## 11. Children

Offshift is for working adults and isn't directed at children under 18.

## 12. Changes and complaints

If this policy changes materially, we'll update the date above and, where practical, tell you in the app. If you are unhappy with how we've handled your information, contact us first at the address above. You can also complain to the Office of the Australian Information Commissioner (oaic.gov.au).
