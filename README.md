# Exp2

An Android application project built with Kotlin and Gradle Kotlin DSL. The app’s entry point is `MainActivity`, which inflates an XML layout (`activity_main_linear_form`) and serves as a simple foundation for a responsive UI example.

- Entry point: [MainActivity.kt](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/app/src/main/java/com/example/responsiveuiapp/MainActivity.kt)
- Manifest: [AndroidManifest.xml](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/app/src/main/AndroidManifest.xml)
- App module build script: [build.gradle.kts](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/app/build.gradle.kts)
- Project settings: [settings.gradle.kts](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/settings.gradle.kts)
- ProGuard/R8 rules: [proguard-rules.pro](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/app/proguard-rules.pro)

## Tech stack

- Kotlin for Android
- Android XML views (inflated via `setContentView`)
- Gradle Kotlin DSL for build configuration
- AndroidX libraries (via the app module’s Gradle configuration)
- ProGuard/R8 for release builds

## Project structure

```text
MadlSem6/
├─ .gitignore
├─ .idea/                     # IDE project files
├─ app/
│  ├─ .gitignore
│  ├─ build.gradle.kts        # App module build configuration (Kotlin DSL)
│  ├─ proguard-rules.pro      # Shrinker/obfuscation rules
│  └─ src/
│     ├─ androidTest/         # Instrumentation tests
│     ├─ main/
│     │  ├─ AndroidManifest.xml
│     │  ├─ java/
│     │  │  └─ com/example/responsiveuiapp/
│     │  │     ├─ MainActivity.kt
│     │  │     └─ ui/         # UI-related Kotlin sources (if present)
│     │  └─ res/              # XML resources: layouts, drawables, strings, etc.
│     └─ test/                # Unit tests
├─ gradle/                    # Gradle wrapper files
├─ gradle.properties
├─ gradlew
├─ gradlew.bat
└─ settings.gradle.kts        # Root project settings (Kotlin DSL)
```

## Overview

The app launches `MainActivity`, which sets the content view to an XML layout:

- `MainActivity` calls `setContentView(R.layout.activity_main_linear_form)`, indicating the primary UI is defined in an XML layout resource named `activity_main_linear_form.xml` under `app/src/main/res/layout/`.

This setup is typical for view-based Android apps that use XML for layouts rather than Jetpack Compose.

## Getting started

### Prerequisites

- Android Studio (latest stable)
- Android SDK and platform tools
- A recent JDK compatible with your Android Gradle Plugin version (Android Studio bundles JDK by default)
- An Android device or emulator for testing

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Yash-Mahajan-28/MadlSem6.git
   cd MadlSem6
   ```

2. Open the project in Android Studio:
   - File → Open… → select the `MadlSem6` folder
   - Let Gradle sync complete

3. Build the project:
   - Android Studio: Build → Make Project
   - Or via CLI:
     ```bash
     ./gradlew assembleDebug
     ```

4. Run on a device/emulator:
   - Android Studio: Run → Run ‘app’
   - Or select a device from the device dropdown and press the Run button

## Running tests

- Unit tests:
  ```bash
  ./gradlew test
  ```
- Instrumentation tests (require a connected device/emulator):
  ```bash
  ./gradlew connectedAndroidTest
  ```

## Module details

- `app` module
  - [AndroidManifest.xml](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/app/src/main/AndroidManifest.xml): Declares activities, permissions, and app metadata.
  - [MainActivity.kt](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/app/src/main/java/com/example/responsiveuiapp/MainActivity.kt): Entry point that inflates the main layout.
  - `ui/`: Intended for UI-related classes/components.
  - `res/`: Contains layout XMLs, drawables, and other resources referenced via `R.*`.

## Build configuration

- The project uses Gradle Kotlin DSL:
  - Root settings: [settings.gradle.kts](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/settings.gradle.kts)
  - App module: [app/build.gradle.kts](https://github.com/Yash-Mahajan-28/MadlSem6/blob/main/app/build.gradle.kts)

- Use the Gradle wrapper for reproducible builds:
  ```bash
  ./gradlew clean build
  ```

## Contributing

- Fork the repository
- Create a feature branch:
  ```bash
  git checkout -b feature/your-feature
  ```
- Commit changes and open a pull request

## License

If you plan to share or publish this project, consider adding a license (e.g., MIT, Apache 2.0) to clarify usage terms.

## Notes

- If `activity_main_linear_form.xml` is missing from `res/layout/`, create it to match the `setContentView` call in `MainActivity`.
- Ensure your Gradle plugin and Kotlin versions in the build scripts are compatible with your Android Studio version.
