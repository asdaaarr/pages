# Privacy Policy

**Deka English**
**Last updated:** September 11, 2026
**Effective date:** September 11, 2026

**Data controller:** KUCHERENKO DENIS VALERII, Individual Entrepreneur (PE) registered in the
Republic of Armenia on 22 June 2026, state registration No. 286.1590908, TIN 20324621, registered
address: N. Zaryan St. 22A, Arabkir, Yerevan 0051, Republic of Armenia ("we", "our", "the
developer"). Contact: devasdaaar@gmail.com

---

## 1. Introduction

Deka English ("the App", "we", "our") is a vocabulary learning application that uses spaced repetition to help users study English. The App is built with a local-first architecture: your data stays on your device.

This Privacy Policy explains what data the App collects, how it is used, and what choices you have.

---

## 2. Data We Collect

### 2.1 Data You Create

When you use the App, you create and store the following content **locally on your device**:

- **Flashcards** — words, phrases, definitions, pronunciation (IPA), example sentences, collocations, usage notes, and saved practice prompts
- **Decks** — named collections of flashcards
- **Tags** — labels you assign to cards for organization
- **Study progress** — spaced repetition data: review intervals, ease factors, repetition counts, due dates, lapse counts
- **Settings** — your preferred language mode, proficiency level, AI proxy server URL, practice preferences, deck-specific SRS parameters, theme preference

All of this data is stored in a local database (SQLite) on your device. We do not have access to it, and it is never uploaded to our servers automatically.

### 2.2 Data Sent to External Services

The App includes an optional AI-assisted card drafting feature. When you use this feature, the following data is sent to an AI proxy server:

| Feature | Data Sent |
|---------|-----------|
| Card drafting | The word or phrase you want to learn, your language mode (English-only or English-Russian), your proficiency level |
| Text extraction from images | The image file you select, optional language and source hints |
| Practice prompt generation | Card front, short meaning, examples, collocations, nuances, your proficiency level and language preferences |
| Answer checking | Your written answer, the practice prompt, card content (front, meaning, examples, collocations, nuances), your proficiency level and language preferences |
| Card audio | The exact English card front or example shown in the App |
| Every AI-assisted request | A random installation identifier generated on your device (see below), the App version, and a device attestation token issued by Apple (iOS) |

This data is transmitted to a proxy server via HTTPS. The proxy server forwards requests to OpenAI's API for processing. **The OpenAI API key is stored on the proxy server only — it is never present in the App.**

For card audio, the proxy sends the English text to Google Cloud Text-to-Speech to create an
AI-synthesized voice recording. The resulting audio is stored in Cloudflare R2 object storage and
served to the App through Cloudflare's public CDN. Audio objects are keyed by a cryptographic hash
of the exact spoken text and audio settings; the object key does not contain the card text or a user
identifier.

You can configure the proxy server URL in the App's settings. Card audio preparation may run after
you save or import a card; other AI-assisted requests run only when you use their corresponding
features.

**Installation identifier.** So that free usage limits and subscription entitlements can be applied
to your copy of the App, the App generates a random identifier the first time it starts and sends it
with AI-assisted requests. It is not derived from your name, email, phone number, device serial
number, or advertising identifier, and it is not shared with OpenAI. It is reset if you delete and
reinstall the App.

**Device attestation (iOS).** To block automated abuse of the AI features, the App uses Apple's App
Attest service. Apple's framework produces a cryptographic assertion proving the request comes from
a genuine, unmodified copy of the App on a real Apple device. This assertion contains no personal
data and no card content, and we cannot use it to identify you or your device outside the App.

### 2.3 Data We Do NOT Collect

- Personal identification information (name, email, phone number)
- Account credentials (the App does not require an account)
- Location data
- Contacts
- Continuous/background camera or microphone recording
- Full photo library contents (except images you explicitly select for text extraction)
- The iOS advertising identifier (IDFA) unless you explicitly allow tracking through Apple's App Tracking Transparency prompt
- Cookies or tracking pixels
- Browsing history

### 2.4 Aggregated Analytics and Crash Diagnostics

To keep the App stable and understand feature usage at a high level, we use Firebase services:

- **Firebase Analytics** (aggregated product usage events)
- **Firebase Crashlytics** (crash and non-fatal diagnostics)

What is sent:
- Event names and coarse technical attributes (for example: feature used, source mode, count buckets)
- Crash stack traces, app version, OS version, device model, and technical diagnostic metadata

What is **not** sent:
- Card text content (front/meaning/examples/collocations/nuances)
- User account IDs (the App has no accounts)

This telemetry is used only for App functionality and reliability, is transmitted over HTTPS, and is not used for advertising personalization.

### 2.5 Install Attribution

When attribution is enabled for a release, the App uses Tenjin to understand which advertising campaign led to an installation and to measure coarse product milestones such as onboarding completion, first card creation, review completion, trial start, and purchase.

On iOS:

- Before the tracking choice is resolved, attribution events remain in memory and are not sent to Tenjin.
- If you explicitly allow tracking through Apple's App Tracking Transparency prompt, Tenjin may process the iOS advertising identifier (IDFA) for install attribution.
- If you decline or choose "Not now," the App initializes Tenjin without IDFA. Apple's privacy-preserving SKAdNetwork conversion values continue through the system API. Delivery of Tenjin events without IDFA is not guaranteed because iOS may block requests to declared tracking domains when tracking is not authorized.

On Android, Tenjin may process the Android advertising identifier when attribution is enabled and the identifier is available under your device and platform settings.

Attribution data may include advertising or campaign information, a device or installation identifier, app version, platform information, and the coarse milestone events listed above. It is used for install attribution and campaign measurement, not advertising personalization. We do not sell this data.

---

### 2.6 Subscription Data

Deka Premium is sold as an auto-renewable subscription through Apple's In-App Purchase system. Apple
is the merchant of record. **We never receive your payment card details, billing address, or Apple ID
credentials** — payment is handled entirely by Apple.

To know whether your copy of the App has an active subscription, we use Adapty, a subscription
management service. What is processed:

| Data | Purpose |
|------|---------|
| Your installation identifier (see 2.2) | Linking a purchase to the copy of the App that made it |
| Apple's App Store transaction receipt / transaction identifiers | Verifying that a purchase or renewal is genuine |
| Subscription status, product identifier, purchase and expiry dates, trial and cancellation state | Unlocking or locking paid features, and knowing when access ends |
| Country of the App Store account, App version, platform and OS version | Showing the correct prices and products |

Adapty notifies our server when your subscription starts, renews, expires, or is refunded. Our server
stores the installation identifier together with the resulting entitlement state and its expiry date,
so that the App can unlock paid features. This record contains no name, email, payment details, or
card content.

We do not use subscription data for advertising and we do not sell it.

---

## 3. How We Use Your Data

| Data | Purpose | Storage |
|------|---------|---------|
| Flashcards, decks, tags | Core learning functionality | Device only |
| Study progress (SRS data) | Scheduling card reviews using spaced repetition | Device only |
| App settings | Personalizing your experience | Device only |
| Text sent via AI features | Generating card content, practice prompts, and answer feedback | Transmitted to proxy server; generated card content and reusable practice prompts may be stored locally on your device |
| Aggregated usage events | Product quality and feature usage insights | Firebase (Google) |
| Crash diagnostics | Detecting, triaging, and fixing runtime failures | Firebase Crashlytics (Google) |
| Install and campaign attribution | Measuring which campaigns lead to installs and coarse product milestones | Tenjin |
| Subscription status and entitlement | Unlocking Deka Premium features and enforcing free usage limits | Adapty; our proxy server (entitlement record keyed by installation identifier) |
| Installation identifier | Applying free limits and entitlements to your copy of the App | Device; our proxy server |

We do not sell your data or use it for advertising personalization. Attribution data is used only to measure install sources and campaign performance.

---

## 4. Data Sharing with Third Parties

### 4.1 OpenAI (via AI Proxy Server)

When you use AI-assisted features, your request data is forwarded to OpenAI's API through our proxy server. OpenAI processes this data according to their own privacy policy: [https://openai.com/privacy](https://openai.com/privacy).

We do not control how OpenAI processes data once it is received by their API.

### 4.2 Firebase (Google)

The App uses Firebase Analytics and Firebase Crashlytics for aggregated analytics and technical diagnostics. These services process telemetry according to Google's Firebase privacy terms: [https://firebase.google.com/support/privacy](https://firebase.google.com/support/privacy).

### 4.3 Tenjin

When attribution is enabled, the App uses Tenjin for install and campaign attribution. On iOS, IDFA is available to Tenjin only after your explicit App Tracking Transparency authorization. Without that authorization, Tenjin initializes without IDFA; Apple's SKAdNetwork conversion values continue through the system API, while delivery of Tenjin events without IDFA is not guaranteed. Tenjin processes data according to its privacy policy: [https://tenjin.com/privacy/](https://tenjin.com/privacy/).

### 4.4 Adapty and Apple (Subscriptions)

Purchases are processed by **Apple** under Apple's own privacy policy:
[https://www.apple.com/legal/privacy/](https://www.apple.com/legal/privacy/). We receive no payment
details from Apple.

Subscription state is managed through **Adapty**, which processes the data listed in section 2.6
under its privacy policy: [https://adapty.io/privacy/](https://adapty.io/privacy/).

### 4.5 No Data Sale or Ad Serving

We do not sell, rent, or trade your data to advertisers or data brokers. The App contains no:
- Third-party ad-serving SDKs or in-app advertising
- Social media integrations
- Data brokers or aggregators

---

## 5. Data Storage and Security

### 5.1 Local Storage

All user-created content and study progress are stored locally on your device in an SQLite database within the App's private storage area. This data is accessible only to the App and is protected by your device's operating system security.

### 5.2 Network Security

- **Production builds:** All network communication uses HTTPS (TLS encryption). Cleartext HTTP traffic is prohibited.
- **Debug builds:** HTTP is permitted only for local development addresses (localhost, 127.0.0.1, 10.0.2.2).

### 5.3 Backup Files

The App allows you to export your flashcards as a JSON file. This export:
- Is initiated manually by you
- Contains your cards' content (words, definitions, examples, collocations, notes), saved practice prompts, metadata (timestamps, deck assignments), and supported learning metadata such as tags, settings, and study progress
- Is saved as an unencrypted plaintext file

You are responsible for the security of exported backup files. We recommend storing them in a secure location.

### 5.4 Android System Backup

The App allows Android's built-in backup service (`android:allowBackup="true"`). This means Android may include App data in device backups (e.g., Google Drive backup). You can control this through your device's backup settings.

---

## 6. Your Rights and Choices

### 6.1 Access and Control

You have full control over your data at all times:

- **View** all your cards, decks, tags, and settings within the App
- **Edit** any card, deck, tag, or setting
- **Delete** individual cards, entire decks, or tags
- **Export** your cards as a JSON backup file
- **Import** cards from a backup file (duplicate cards are skipped by ID to prevent data loss)

### 6.2 Delete Your Data

- **Delete individual items:** Remove specific cards, decks, or tags through the App's interface. When deleting a deck, you can choose to delete all cards in it or move them to another deck you select.
- **Delete all data on your device:** Uninstalling the App permanently removes all locally stored
  data — cards, decks, tags, study progress, and settings. We hold no copy of it.
- **Data held on our server:** The only records our server keeps are the free-usage counter and the
  subscription entitlement associated with your installation identifier. Uninstalling the App does
  not delete these records, and reinstalling generates a new installation identifier. Subscription
  and purchase records held by Apple and by Adapty are also retained under their own policies and by
  the accounting rules that apply to us. To have the records associated with your installation
  identifier deleted, email devasdaaar@gmail.com; note that deleting an active subscription record
  does not cancel the subscription itself — cancel it in your Apple ID subscription settings.

### 6.3 Opt Out of AI Features

AI-assisted features are optional. If you do not use them, no data is transmitted from your device. You can also configure a custom proxy server URL if you prefer to route AI requests through your own server.

### 6.4 Tracking and Advertising Identifier Choices

On iOS, you can decline the App Tracking Transparency request or change the permission later in iOS Settings. If you do not authorize tracking, the App does not make IDFA available to Tenjin. Apple's SKAdNetwork conversion values continue through the system API; delivery of Tenjin events without IDFA is not guaranteed. On Android, availability of the advertising identifier follows your device and Google settings.

---

## 7. Children's Privacy

The App is not directed at children under the age of 13. We do not knowingly collect personal information from children under 13. If you believe a child under 13 has provided data through the App, please contact us and we will take steps to delete such information.

---

## 8. International Users

The App stores data locally on your device. When you use AI-assisted features or purchase a
subscription, data may be transmitted to and processed on servers located outside your country of
residence — including the United States and the European Union. This applies to OpenAI (AI
processing), Google Cloud and Firebase (speech synthesis, analytics, crash diagnostics), Cloudflare
(audio storage and delivery), Vercel (our proxy server hosting), Adapty (subscription management),
Apple (payments), and Tenjin (attribution, when enabled). By using these features you consent to
this transfer.

If you are located in the European Economic Area (EEA), United Kingdom, or another jurisdiction with data protection laws, you have the right to:
- Request information about what data is processed
- Request deletion of your data
- Object to data processing

Since we maintain no user accounts and your learning content never leaves your device, most of these
rights are exercised simply by editing or deleting cards in the App or uninstalling it. For the
server-side records described in section 6.2, send your request to devasdaaar@gmail.com.

---

## 9. Changes to This Policy

We may update this Privacy Policy from time to time. The updated version will be indicated by the "Last updated" date at the top of this page. We encourage you to review this Privacy Policy periodically.

If we make material changes to how we treat user data, we will update the App to notify you.

---

## 10. Permissions and Access Requests

The App requests the following device permissions:

| Permission | Purpose |
|------------|---------|
| Internet (`android.permission.INTERNET`, Android) | Required for AI-assisted drafting, OCR extraction requests, and practice features. Not used if AI features are not activated. |
| Advertising ID (`com.google.android.gms.permission.AD_ID`, Android) | Used for install and campaign attribution when attribution is enabled and the identifier is available under your device settings. |
| Camera access (iOS) | Requested only when you explicitly choose the Camera source for text extraction from images. |
| Photo library access (iOS) | Requested only when you explicitly choose the Gallery/Photos source for text extraction from images. |
| App Tracking Transparency (iOS) | Requested only after the in-app explanation. IDFA is used for install attribution only if you explicitly allow tracking. |

The App does not request access to your contacts, location, or background media capture. Media access is user-initiated and limited to the image(s) you explicitly choose for OCR.

---

## 11. Platform Availability

The App is available on:
- **Android:** version 7.0 (API level 24) and above
- **iOS:** supported via Kotlin Multiplatform

---

## 12. Contact Us

If you have any questions or concerns about this Privacy Policy or the App's data practices, please contact us at:

**Email:** devasdaaar@gmail.com

---

*This Privacy Policy applies to Deka English version 1.0.0 and later.*
