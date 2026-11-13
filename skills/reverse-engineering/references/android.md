# Android APK Reverse Engineering Guide

Guide for inspecting Android application package structure, configuration, and decompiled code.

## Package Disassembly

- APK Extraction: Unpack APK archive using `unzip` or `apktool`.
  - `apktool d app.apk -o output_dir/`: Recovers decoded `AndroidManifest.xml` and Smali bytecode.
- Java Decompilation: Use JADX (`jadx-gui` or CLI `jadx -d out/ app.apk`) to decompile DEX bytecode into readable Java source.

## Inspection Checklist

### 1. Manifest Analysis (`AndroidManifest.xml`)

- Permissions: Review requested `uses-permission` tags.
- Exported Components: Check `android:exported="true"` on activities, receivers, services, and content providers.
- Deep Links and Intent Filters: Inspect custom URI schemes and accepted URL patterns.
- Debug Flags: Check `android:debuggable="true"` or network security configs allowing cleartext traffic.

### 2. Code Review

- Configuration: Search for API hostnames, endpoint constants, and initialization classes.
- Storage: Inspect SQLite database helpers, SharedPreferences keys, and local caching logic.
- Network Security: Review Retrofit or OkHttp client configurations and SSL pinning implementations.
