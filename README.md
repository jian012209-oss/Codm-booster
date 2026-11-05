# CODM Booster (v2.0)

A safe Android companion app that checks your phone before you play Call of Duty: Mobile
and helps you fix the things that really cause FPS drops: heat, battery saver, low storage and low RAM.

## What it does
- **Readiness score (0–100)** that updates every 3 seconds.
- **Live checklist**: phone temperature, charging, battery saver, battery level, free storage, free RAM, screen refresh rate. Red items show a **Fix** button that opens the right Android setting.
- **Recommended CODM graphics settings** based on your phone's RAM.
- **Play CODM** button (Global and Garena versions).
- **Quick fixes**: Do Not Disturb, battery saver, display/refresh rate, storage, CODM app info (clear cache), Wi‑Fi.
- Dark gaming UI.

## Safe for your account
It never modifies CODM, injects code, reads game memory or automates gameplay.
Android doesn't let normal apps overclock, force-close other apps or lock FPS, so this app doesn't pretend to.

## Get the APK, option A: GitHub (no computer setup needed)
1. Create a free GitHub account and a new repository.
2. Upload all the files in this folder (including the hidden `.github` folder) to the repository.
3. Open the **Actions** tab. The **Build APK** workflow runs automatically (or click **Run workflow**).
4. When it finishes (about 3–5 minutes), open the run and download **CODM-Booster-apk** under *Artifacts*.
5. Unzip it, copy `app-debug.apk` to your phone and install it (allow "Install unknown apps" when asked).

## Get the APK, option B: Android Studio
1. Install Android Studio and open this folder as a project.
2. Wait for Gradle sync to finish (needs internet the first time).
3. **Build → Build Bundle(s) / APK(s) → Build APK(s)**.

Or from a terminal: `./gradlew :app:assembleDebug`. The APK ends up at `app/build/outputs/apk/debug/app-debug.apk`.

## Modules
- `app`: the Android app.
- `booster-core`: reusable library (`DeviceMonitor.read`, `checklist`, `score`, `recommendedSettings`).

Requirements: Android 8.0+ (thermal status needs Android 10+). Built with AGP 8.7.3, Kotlin 2.0.21, Gradle 8.14.3, JDK 17.
