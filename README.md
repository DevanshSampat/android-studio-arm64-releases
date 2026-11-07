# Android Studio for Windows ARM64 (Unofficial)

> **Unofficial build.** This is an independent project. It is not made, endorsed or supported by Google. Android and Android Studio are trademarks of Google LLC.

This repository publishes Android Studio for **Windows 11 ARM64** PCs (Snapdragon X and similar), together with an Android Emulator that runs on Windows Hypervisor Platform.

## Download

Get `AndroidStudio-2026.2.2-Windows-ARM64-Setup.exe` (about 1.5 GB) from the [latest release](https://github.com/DevanshSampat/android-studio-arm64-releases/releases/latest). It installs Android Studio Rabbit 2 (2026.2.2 Patch 1) and the Android Emulator.

The installer isn't signed with a commercial certificate, so SmartScreen may say it "prevented an unrecognized app from starting". Choose **More info**, then **Run anyway**. Or unblock it first in PowerShell:

```powershell
Unblock-File -Path .\AndroidStudio-2026.2.2-Windows-ARM64-Setup.exe
```

## What this build is

Google publishes Android Studio for Windows on x64 only. This build runs natively on ARM64:

- **Android Studio's own code** is Google's official Rabbit 2 release, unchanged. Its Java code is the same on every platform.
- **Everything that loads into the IDE process is ARM64:** the JetBrains Runtime (Java 25), the launcher and its helpers, and the native libraries for JNA, Skiko, pty4j and SQLite. These come from JetBrains' IntelliJ IDEA for Windows ARM64 on the same platform build (262.10968.63), so each one matches the Java code that calls it.
- **Layoutlib** (XML and Compose previews) uses ARM64 builds of `layoutlib_jni.dll` and `libandroid_runtime.dll`, compiled from AOSP in [layoutlib-windows-arm64](https://github.com/DevanshSampat/layoutlib-windows-arm64).
- **Device frames** are converted from WebP to PNG data, because Studio's WebP decoder is x64 only.
- The About screen says "Unofficial Windows ARM64 build".

Some tools Studio starts as separate programs stay x64 and run under Windows' x64 emulation: LLDB, clangd, simpleperf, the trace processor, and the local model server in the Gemini plugin. Five x64-only libraries can't load into an ARM64 process, so the features that need them don't work: WebP image decoding (`image_converter.dll`, `webp_jni.dll`), simpleperf report parsing (`libsimpleperf_report.dll`), an object-tagging profiler agent (`jni_object_tagger.dll`), and whatever uses `video_decoder.dll`, which is new in Rabbit 2.

The assembly script is `installer/assemble_studio.py` in [android-emulator-windows-arm64](https://github.com/DevanshSampat/android-emulator-windows-arm64).

## Related repositories

- [android-emulator-windows-arm64](https://github.com/DevanshSampat/android-emulator-windows-arm64): the Android Emulator for Windows ARM64, the installer and the Studio assembly script.
- [layoutlib-windows-arm64](https://github.com/DevanshSampat/layoutlib-windows-arm64): native Windows ARM64 Layoutlib.
- [android-studio-tools-base-arm64](https://github.com/DevanshSampat/android-studio-tools-base-arm64) and [android-studio-tools-adt-idea-arm64](https://github.com/DevanshSampat/android-studio-tools-adt-idea-arm64): the Bazel setup used to build the 2026.2.1 releases from source. Rabbit 2 releases use Google's published Studio code instead.
