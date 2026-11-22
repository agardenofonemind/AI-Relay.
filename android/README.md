# AI Relay Android

This directory contains the first minimal Kotlin + Jetpack Compose Android application.

## Current scope

- A single launcher activity and a static Compose screen.
- Android Gradle Plugin 9.4.0.
- Kotlin Compose compiler plugin 2.4.10.
- Compile/target SDK 36; minimum SDK 26.
- No model API, GitHub synchronization, local database, or AI-client automation.

## Cloud build

The repository workflow `.github/workflows/android-debug-apk.yml` installs Gradle 9.6.0 on the GitHub-hosted runner and runs:

```shell
gradle --no-daemon assembleDebug
```

The generated APK is uploaded as the `ai-relay-debug-apk` workflow artifact.

A committed Gradle Wrapper is intentionally deferred from this first bootstrap. The CI runner installs a pinned Gradle distribution directly; wrapper files can be added after the first successful bootstrap build.

## Package

`com.agardenofonemind.airelay`
