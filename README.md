<div align="center">

# ReelWise: Reels Counter

### Understand your scrolling. Set limits. Build better digital habits.

An Android app that helps you become more aware of your short-form video consumption by counting supported reels and Shorts, setting daily limits, and tracking your progress.

[![Google Play](https://img.shields.io/badge/Google_Play-Download-34A853?style=for-the-badge&logo=googleplay&logoColor=white)](https://play.google.com/store/apps/details?id=com.dvexo.reelguard)
[![Kotlin](https://img.shields.io/badge/Kotlin-2C2C2C?style=for-the-badge&logo=kotlin&logoColor=7F52FF)](https://kotlinlang.org/)
[![Android](https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://developer.android.com/)
[![Jetpack Compose](https://img.shields.io/badge/UI-Jetpack%20Compose-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white)](https://developer.android.com/compose)

</div>

---

## About the Project

**ReelWise** is an Android utility designed to help people understand and manage their short-form video scrolling habits. It automatically counts supported short-video feed activity, lets users define daily limits, and turns their activity into useful progress and statistics.

Instead of relying only on screen-time estimates, ReelWise focuses on the number of short-form videos viewed. Users can monitor their habits, set realistic goals, receive limit reminders, and work toward more intentional social-media use.

- **App name:** ReelWise: Reels Counter
- **Android package:** `com.dvexo.reelguard`
- **Current app version:** `1.1.1` (`versionCode 11`)
- **Minimum Android version:** Android 8.0 (API 26)
- **Target / compile SDK:** API 37
- **Repository:** [github.com/abdullahalnuman0/reelwise](https://github.com/abdullahalnuman0/reelwise)
- **Google Play:** [Download ReelWise](https://play.google.com/store/apps/details?id=com.dvexo.reelguard)

## Key Features

### Automatic Reel & Shorts Counting

Uses Android's `AccessibilityService` to recognize supported short-form video feed activity in enabled apps and maintain platform-specific counts.

### Daily Limits and Reminders

- Set a daily viewing limit for supported platforms.
- Choose how ReelWise responds when a limit is reached.
- Receive a reminder or use the available feed-blocking option, depending on the selected settings.

### Insights and Activity History

- Review daily and historical counts.
- Compare activity across supported platforms.
- Explore scrolling trends and progress over time.
- See how your usage changes as you work toward your goals.

### Goals, Streaks, and Challenges

Build consistency with personal goals, streak tracking, and challenges that encourage more intentional scrolling habits.

### Leaderboards

Explore aggregate rankings and compare progress with other users where the optional Firebase-backed leaderboard service is configured and available.

### Local Data and Optional Account Features

Core counting and app features are designed to work without signing in to social-media platforms. Optional ReelWise account features provide authentication and cloud-backed statistics or leaderboard functionality where enabled.

## Supported Platforms

ReelWise is designed to count short-form video activity on the following platforms:

| Platform | Supported content |
|---|---|
| Facebook | Facebook Reels |
| Instagram | Instagram Reels |
| TikTok | TikTok short-form video feed |
| Snapchat | Spotlight |
| YouTube | YouTube Shorts |

> **Compatibility note:** Counting depends on the relevant app's interface, accessibility events, Android version, and the version of each third-party app. Platform updates may affect detection or availability.

ReelWise is an independent utility. It is not affiliated with, sponsored by, endorsed by, or officially connected to Meta, Instagram, Facebook, TikTok, Snap Inc., Snapchat, Google, or YouTube. All product names and trademarks belong to their respective owners.

## Screenshots

Screenshots for this repository are intended to be stored in [`assets/screenshot/`](assets/screenshot/). The folder is currently a placeholder. Add the latest app screenshots there (for example, `dashboard.png`, `insights.png`, `limits.png`, and `leaderboard.png`), then enable and update the gallery snippet below to match the actual filenames.

<!--
After adding the image files, uncomment and update this gallery to match their actual names.

<p align="center">
  <img src="assets/screenshot/dashboard.png" width="190" alt="ReelWise dashboard" />
  <img src="assets/screenshot/insights.png" width="190" alt="ReelWise insights" />
  <img src="assets/screenshot/limits.png" width="190" alt="ReelWise daily limits" />
  <img src="assets/screenshot/leaderboard.png" width="190" alt="ReelWise leaderboard" />
</p>
-->

## How It Works

1. **Accessibility-based detection:** After the user enables the required Android Accessibility permission, ReelWise processes relevant accessibility events from supported apps to recognize short-form feed activity.
2. **Counting and tracking:** Recognized activity is used to update the user's reel and Shorts counts, platform breakdowns, limits, and progress.
3. **On-device persistence:** Room provides the local database layer for app data and history.
4. **Optional cloud features:** Firebase Authentication and Firebase Realtime Database support account-related and leaderboard/statistics features when configured.
5. **Advertising and consent:** Google Mobile Ads provides advertising, while Google's User Messaging Platform (UMP) supports consent flows where applicable.

ReelWise does not need users' Instagram, Facebook, TikTok, Snapchat, or YouTube passwords. The counting feature is not designed to upload screenshots, screen recordings, video/audio files, captions, comments, direct messages, or the general content of the social-media apps being monitored.

## Technology Stack

| Technology | Purpose |
|---|---|
| **Kotlin** | Primary application language |
| **Jetpack Compose** | Declarative Android UI |
| **Material 3** | UI components and visual design system |
| **Navigation Compose** | In-app navigation |
| **AndroidX Lifecycle & ViewModel** | Lifecycle-aware UI state integration |
| **Room** | Local database and persistence |
| **KSP** | Room code generation |
| **WorkManager** | Scheduled and deferrable background work |
| **Kotlin Coroutines** | Asynchronous and background operations |
| **Firebase Authentication** | Optional anonymous, email/password, and Google sign-in flows |
| **Firebase Realtime Database** | Optional cloud-backed leaderboard/statistics features |
| **Android Credential Manager + Google ID** | Google sign-in integration |
| **Google Mobile Ads SDK (Next-Gen)** | In-app advertising |
| **Google User Messaging Platform (UMP)** | Advertising consent messages |
| **JUnit, AndroidX Test, Espresso, Compose UI Test, Room Testing** | Unit and Android instrumentation testing |
| **Gradle Kotlin DSL** | Android build configuration |

## Android & Build Configuration

The current Android application configuration includes:

| Setting | Value |
|---|---|
| Application ID | `com.dvexo.reelguard` |
| Minimum SDK | `26` (Android 8.0) |
| Compile SDK | `37` |
| Target SDK | `37` |
| Version name | `1.1.1` |
| Version code | `11` |
| Java source compatibility | `Java 11` |
| Java target compatibility | `Java 11` |
| Release minification | Enabled |
| Release resource shrinking | Enabled |

Release packaging validates the AdMob app and banner unit IDs. A release build requires real, correctly matched AdMob IDs; Google's demo IDs are reserved for debug/testing builds.

Firebase configuration is optional for building the non-leaderboard parts of the app. When a Firebase configuration file is not present, the rest of the app can still build and run, while the leaderboard reports that Firebase has not been configured. Google Sign-In also requires the appropriate OAuth web client configuration.

## Privacy & Permissions

### Accessibility Permission

Automatic counting requires the user to explicitly enable ReelWise's AccessibilityService from Android Settings. This system capability is used to recognize supported short-form feed activity. Users can disable it at any time; automatic counting will stop when access is disabled.

### Data Handling

- Counting and history data are stored locally for core app functionality.
- Optional account features may use Firebase Authentication and cloud services for account-related information and aggregate statistics.
- ReelWise does not require credentials for third-party social-media accounts.
- The counting feature is not intended to upload the media or private content displayed inside monitored apps.
- Google Mobile Ads may process device, advertising, approximate-location, and ad-interaction signals under Google's policies and the user's consent/settings.

Read the full [ReelWise Privacy Policy](https://abdullahalnuman-dev.github.io/reel-wise/).

For details about Google's data processing, review the applicable [Google Privacy Policy](https://policies.google.com/privacy) and [Firebase Privacy and Security information](https://firebase.google.com/support/privacy).

## Repository Scope

This repository is a **public documentation and project showcase** for ReelWise. It contains the project README and is intended to hold app screenshots in `assets/screenshot/`.

The Android application's source code is **not included in this repository**. Therefore, this repository is not a clone-and-build distribution of the app.

## Download

<div align="center">

### Take a more intentional approach to short-form video scrolling.

[![Get it on Google Play](https://img.shields.io/badge/Get_it_on-Google_Play-414141?style=for-the-badge&logo=googleplay&logoColor=white)](https://play.google.com/store/apps/details?id=com.dvexo.reelguard)

[Open ReelWise on Google Play](https://play.google.com/store/apps/details?id=com.dvexo.reelguard)

</div>

## Contact

**Abdullah Al Numan** — Android Developer

- **Email:** [abdullahalnuman.dev@gmail.com](mailto:abdullahalnuman.dev@gmail.com)
- **GitHub:** [github.com/abdullahalnuman0](https://github.com/abdullahalnuman0)
- **Portfolio:** [abdullahalnuman0.github.io](https://abdullahalnuman0.github.io)
- **Project repository:** [github.com/abdullahalnuman0/reelwise](https://github.com/abdullahalnuman0/reelwise)

For app support, feedback, or bug reports, please use the support email above or open an issue in this repository.

---

<div align="center">

**Built with Kotlin and Jetpack Compose.**

</div>
