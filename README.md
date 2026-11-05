# CODM Performance Booster

An Android Studio starter project containing:
- `app`: standalone Android companion app (APK project).
- `booster-core`: reusable Android library module that can be integrated into another Android app.

## Features
- Shows available and total RAM using Android's public `ActivityManager` API.
- Shows Android thermal status on Android 10+.
- Launches the Global or Garena CODM app if installed.
- Shortcuts to Android app and storage settings.
- Provides safe gaming tips.

## Important limitations
This is a companion utility, not a system-level booster. Normal Android apps cannot reliably:
- force-stop other apps,
- overclock CPU/GPU,
- change CODM's internal graphics/FPS settings,
- guarantee zero lag or fixed FPS,
- read another app's private performance data.

It does not modify CODM, inject code, automate gameplay, or access game memory.

## Build the APK
1. Install Android Studio on a computer.
2. Open this folder as an existing project.
3. Allow Gradle sync to finish (internet is needed the first time).
4. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Android Studio will show the APK location when the build completes.

Recommended: use JDK 17 with Android Gradle Plugin 8.7.3.

## Integrate the plugin/library into another Android app
1. Copy the `booster-core` folder into the target Android Studio project.
2. Add `include(":booster-core")` to the target project's `settings.gradle.kts`.
3. Add `implementation(project(":booster-core"))` to the target app module dependencies.
4. Use `DeviceMonitor.read(context)` from the library.

Example:
```kotlin
val status = DeviceMonitor.read(context)
println(status.availableRamMb)
println(status.thermalLabel)
```

## Compatibility
- Minimum Android version: Android 8.0 (API 26).
- Thermal status requires Android 10 (API 29) or newer.
- CODM launch detection includes common Global and Garena package IDs.
