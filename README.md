# Dairy Hisab Android Studio Project — v2 starter

## Configured for
- App name: Dairy Hisab
- Languages: Gujarati, Hindi, English (language selector in Settings)
- Business use: household milk customers and dairy/farmer collection parties
- Local-first database with optional Firebase cloud sync scaffold

## Included
- Kotlin + Jetpack Compose UI
- Room local database
- Dashboard
- Customer/party management (Customer / Farmer / Collection centre)
- Morning/evening milk entry with litres, rate, fat and SNF
- Language selector
- Cloud setup screen and Firebase sync service scaffold

## Not yet a finished Play Store release
Cloud sync is intentionally disabled until you configure your own Firebase project, add `google-services.json`, enable Authentication and Firestore, and apply secure Firestore rules. The code includes a sync scaffold, but it is not a full multi-device conflict-resolution system. Monthly invoice PDF, payment collection/ledger, automated WhatsApp messages, subscription and production QA still need implementation.

## Open in Android Studio
1. Extract this ZIP.
2. Open this folder in Android Studio.
3. Use JDK 17 and install Android SDK 36 if requested.
4. Sync Gradle and run on an emulator or Android phone.

## Enable Firebase
1. Create a Firebase project at https://console.firebase.google.com/
2. Register an Android app using the final application ID (currently `com.example.dairyhisab`).
3. Download `google-services.json` into `app/`.
4. In root `build.gradle.kts`, add `id("com.google.gms.google-services") version "4.4.2" apply false`.
5. In `app/build.gradle.kts`, add `id("com.google.gms.google-services")`.
6. Enable Email/Password or Anonymous Authentication and Cloud Firestore in Firebase Console.
7. Configure Firestore security rules so each authenticated user can read/write only their own `users/{uid}/...` documents. Never publish with open rules.
8. Re-sync, test sign-in and sync with two test devices, and inspect error handling before enabling the cloud UI.

The app currently works locally without Firebase. Do not put service-account credentials or private keys in the Android app.

## Play Store checklist
- Change `applicationId` to a unique ID you own before first release.
- Replace app icon and branding; use your own app name/logo.
- Test fresh install, upgrade, offline mode, data retention, all languages, large fonts, and supported Android versions.
- Add a public privacy policy URL and complete Data safety, content rating, ads, target audience, and app access declarations accurately.
- Remove debug logging and test with release signing.
- Build a signed Android App Bundle (.aab), run internal testing, then meet the Play Console testing/production access requirements that apply to your developer account.
- Confirm current target API and Play policy deadlines in Play Console before submission.
