---
title: Privacy Policy
description: How Watchword handles your information.
---

_Last updated: 2026-06-05_

This Privacy Policy explains how **We Are So Back Ltd** ("we", "us"), a company registered in the Republic of Cyprus, handles information when you use **Watchword** (the "App").

## TL;DR

- No accounts, no sign-up. The App uses the iCloud account already on your phone.
- No analytics, advertising, or tracking SDKs.
- Your family's code words are never stored or transmitted anywhere — they are computed on your device, on demand, from a shared secret.
- The shared secret syncs between family members through **your own iCloud**, end-to-end encrypted. We never see it and operate no servers.
- Family member names and activity stay on your device.
- Subscription billing is handled by Apple. RevenueCat helps us verify it. Neither receives your name or email from us.
- We do not sell or share personal information.

## Who we are

We Are So Back Ltd, Cyprus. Contact: **wearesobackltd@gmail.com**.

We are the data controller for any personal data processed via the App. We have not appointed a Data Protection Officer because we do not meet the thresholds in GDPR Article 37.

## How the App works (and why that matters for privacy)

Watchword gives your family a shared code word that changes on a schedule. The word is never sent anywhere: every family member's phone independently derives the same word, at the same time, from a shared **secret key** (a random 256-bit value). Only that key needs to be shared — once — when a family member joins.

## Information we collect today

**Stored only on your device** (we never see it):

- Your onboarding answers and preferences (in iOS `UserDefaults`).
- Your family's name, the names you enter for family members, and the App's local activity feed (via `SwiftData`).
- The family secret key (in the iOS Keychain).

**Stored in your iCloud (processed by Apple, not by us):**

- A small "family" record containing the family name, the word-rotation schedule, and the family secret key. This lives in the **iCloud private database of the family member who created the family** and is shared with invited members through Apple's iCloud sharing. The secret key field uses CloudKit's end-to-end encryption: it is encrypted on-device and readable only by the members of your family share — not by Apple in plaintext, and never by us.
- When you invite someone, Apple processes the share invitation (including the participants' Apple IDs) under the [iCloud Terms](https://www.apple.com/legal/internet-services/icloud/).

**Sent off-device when you use the App:**

- **Subscription data.** When you subscribe, restore, or open the App with an active subscription, Apple receives your Apple ID and payment information (we do not), and RevenueCat receives a randomly generated anonymous App User ID, your subscription status, and basic device identifiers provided by Apple's servers.

That is the full list. The App contains no sign-in, no profiles, no backend servers operated by us, no analytics SDKs, no third-party crash-reporting SDKs, no ad networks, and no tracking technologies.

## Contacts

During setup the App can open the iOS contact picker so you can choose a family member to invite. The App receives only the name you pick, uses it to label that member in your family list, and stores it on your device. Your contact list is never read in the background, uploaded, or shared.

## Information we may collect in the future

We may, in the future, introduce **privacy-respecting diagnostic or aggregate analytics** (for example, an opt-in upload of crash reports, or a first-party privacy-preserving analytics provider) to help us improve stability and usability. If we do:

1. We will update this Policy with the provider name, the data they receive, and the legal basis.
2. We will post the update **at least 30 days before** it takes effect.
3. Where consent is required by law (GDPR / UK GDPR / similar), we will request your consent in-app before enabling any non-essential collection.

This forward-looking statement is here so you know what to expect. Today's Policy still describes today's behaviour.

## How we use information

- To provide the App: verify your subscription, restore purchases.
- To protect the App: prevent fraud and abuse of the subscription system.
- To comply with our legal obligations (tax records for subscription transactions).

## Legal bases under the GDPR

Where the GDPR applies, we rely on:

- **Contractual necessity** (Art. 6(1)(b)) for subscription management and restore purchases.
- **Legitimate interests** (Art. 6(1)(f)) for fraud prevention and security. You may object to this processing at any time.
- **Consent** (Art. 6(1)(a)) for any non-essential analytics or tracking we add in the future.

## Third-party services and subprocessors

| Service | Why we use it | What they receive |
|---|---|---|
| [Apple iCloud / CloudKit](https://www.apple.com/legal/privacy/) | Sync the family record and secret key between your family's devices | The family record described above, stored in your iCloud; share participants' Apple IDs |
| [Apple App Store / StoreKit](https://www.apple.com/legal/privacy/) | Process subscription purchases | Apple ID, payment info, transaction details |
| [RevenueCat](https://www.revenuecat.com/privacy) | Verify subscription receipts and entitlements | Anonymous App User ID, subscription status, device identifiers from Apple |

## International transfers

Some service providers are located outside the EEA, including in the United States (Apple, RevenueCat). Transfers of personal data outside the EEA are made under the European Commission's **Standard Contractual Clauses** and/or the **EU-US Data Privacy Framework** where the provider is certified.

## Data retention

We do not maintain user accounts or store personal information about you on our own servers. Where third parties retain data on our behalf:

- Apple retains the iCloud family record for as long as the family share exists; the family creator can delete it at any time (log out in the App, or delete the App's data in iCloud settings).
- Apple and RevenueCat keep subscription and transaction records for the lifetime of your subscription plus the period required by accounting and tax law (typically seven years under Cypriot / EU law).

You can delete all device-side data — onboarding answers, family list, activity, and the secret key — by logging out in the App's Settings or uninstalling the App.

## Your rights — GDPR (EU / EEA / UK / Switzerland)

You have the right to:

- access the personal data we hold about you;
- have it rectified or erased;
- restrict or object to processing;
- portability;
- withdraw consent at any time, where consent was the legal basis;
- lodge a complaint with your supervisory authority. In Cyprus this is the [Office of the Commissioner for Personal Data Protection](https://www.dataprotection.gov.cy/).

To exercise any right, email **wearesobackltd@gmail.com**. We respond within 30 days.

## Your rights — California (CCPA / CPRA)

If you are a California resident:

- **Categories of personal information collected** in the last 12 months: identifiers (the anonymous App User ID used to verify your subscription) and commercial information (your subscription status).
- **Categories sold or shared:** **None.** We do not sell or share personal information as defined under the CCPA, and we have not done so in the preceding 12 months. We do not engage in cross-context behavioural advertising.
- **Your rights:** to know, delete, correct, and non-discrimination. To exercise, email wearesobackltd@gmail.com.

## Children's privacy

The App is designed for families and may be used by family members of all ages under the supervision of the adult who set up the family. It is not directed at children under 13 (or under 16 in the EEA / UK), and we do not knowingly collect personal information from children — the App collects no personal information from any user beyond what is described above. If you believe a child has provided us information, contact us and we will delete it.

## Security

The family secret key is stored in the iOS Keychain on-device and end-to-end encrypted in transit and at rest in iCloud. All network requests use HTTPS. Because we hold no personal data on our own servers, there is no centralised user dataset on our side. Our service providers maintain their own security programmes and certifications.

## Changes to this Policy

We may update this Policy. For **material** changes, we will give you at least **30 days' notice** in the App and update the "Last updated" date at the top. Material changes include new categories of data, new service providers, or new purposes of use. Non-material changes (clarifications, typo fixes) take effect when posted.

The full revision history of this Policy is public in the [Git history of the page source](https://github.com/josegoncalvespt/wearesoback.com/commits/main/watchword/privacy.md).

## Contact

**We Are So Back Ltd**
Cyprus
wearesobackltd@gmail.com
