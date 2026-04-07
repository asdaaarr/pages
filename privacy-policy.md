# Privacy Policy

**Deka English**
**Last updated:** April 7, 2026
**Effective date:** April 7, 2026

---

## 1. Introduction

Deka English ("the App", "we", "our") is a vocabulary learning application that uses spaced repetition to help users study English. The App is built with a local-first architecture: your data stays on your device.

This Privacy Policy explains what data the App collects, how it is used, and what choices you have.

---

## 2. Data We Collect

### 2.1 Data You Create

When you use the App, you create and store the following content **locally on your device**:

- **Flashcards** — words, phrases, definitions, pronunciation (IPA), example sentences, collocations, usage notes
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

This data is transmitted to a proxy server via HTTPS. The proxy server forwards requests to OpenAI's API for processing. **The OpenAI API key is stored on the proxy server only — it is never present in the App.**

You can configure the proxy server URL in the App's settings. If you do not use the AI features, no data is transmitted.

### 2.3 Data We Do NOT Collect

- Personal identification information (name, email, phone number)
- Account credentials (the App does not require an account)
- Location data
- Contacts
- Continuous/background camera or microphone recording
- Full photo library contents (except images you explicitly select for text extraction)
- Advertising identifiers (IDFA / AAID)
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
- Advertising identifiers
- Tracking data across third-party apps/websites

This telemetry is used only for App functionality and reliability, is transmitted over HTTPS, and is not used for advertising personalization.

---

## 3. How We Use Your Data

| Data | Purpose | Storage |
|------|---------|---------|
| Flashcards, decks, tags | Core learning functionality | Device only |
| Study progress (SRS data) | Scheduling card reviews using spaced repetition | Device only |
| App settings | Personalizing your experience | Device only |
| Text sent via AI features | Generating card content, practice prompts, and answer feedback | Transmitted to proxy server; not stored by the App after the request completes |
| Aggregated usage events | Product quality and feature usage insights | Firebase (Google) |
| Crash diagnostics | Detecting, triaging, and fixing runtime failures | Firebase Crashlytics (Google) |

We do not use your data for advertising, profiling, marketing, or any purpose other than providing the App's functionality.

---

## 4. Data Sharing with Third Parties

### 4.1 OpenAI (via AI Proxy Server)

When you use AI-assisted features, your request data is forwarded to OpenAI's API through our proxy server. OpenAI processes this data according to their own privacy policy: [https://openai.com/privacy](https://openai.com/privacy).

We do not control how OpenAI processes data once it is received by their API.

### 4.2 Firebase (Google)

The App uses Firebase Analytics and Firebase Crashlytics for aggregated analytics and technical diagnostics. These services process telemetry according to Google's Firebase privacy terms: [https://firebase.google.com/support/privacy](https://firebase.google.com/support/privacy).

### 4.3 No Advertising or Data Brokerage

We do not share, sell, rent, or trade your data with advertisers or data brokers. The App contains no:
- Advertising SDKs
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
- Contains your cards' content (words, definitions, examples, collocations, notes) and metadata (timestamps, deck assignments)
- Does **not** contain your study progress (SRS state), tags, or settings
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

- **Delete individual items:** Remove specific cards, decks, or tags through the App's interface. When deleting a deck, you can choose to delete all cards in it or move them to the default deck.
- **Delete all data:** Uninstalling the App removes all locally stored data permanently.

### 6.3 Opt Out of AI Features

AI-assisted features are optional. If you do not use them, no data is transmitted from your device. You can also configure a custom proxy server URL if you prefer to route AI requests through your own server.

---

## 7. Children's Privacy

The App is not directed at children under the age of 13. We do not knowingly collect personal information from children under 13. If you believe a child under 13 has provided data through the App, please contact us and we will take steps to delete such information.

---

## 8. International Users

The App stores data locally on your device. When you use AI-assisted features, data may be transmitted to servers located outside your country of residence (including the United States, where OpenAI's servers are located). By using AI features, you consent to this transfer.

If you are located in the European Economic Area (EEA), United Kingdom, or another jurisdiction with data protection laws, you have the right to:
- Request information about what data is processed
- Request deletion of your data
- Object to data processing

Since all data is stored locally and we do not maintain user accounts, exercising these rights is as simple as deleting cards within the App or uninstalling the App.

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
| Camera access (iOS) | Requested only when you explicitly choose the Camera source for text extraction from images. |
| Photo library access (iOS) | Requested only when you explicitly choose the Gallery/Photos source for text extraction from images. |

The App does not request access to your contacts, location, advertising identifiers, or background media capture. Media access is user-initiated and limited to the image(s) you explicitly choose for OCR.

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
