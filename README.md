# Android Studio Windows ARM64 - Official Releases & Installers

Welcome to the official repository for native **Windows 11 ARM64** builds of **Android Studio**.

Engineered for full native execution on ARM64-powered Windows laptops, including:
- **Snapdragon X Elite** & **Snapdragon X Plus**
- **Snapdragon 8cx Gen 3 / Gen 2**
- **Microsoft SQ3 / SQ2 / SQ1** (Surface Pro 9 5G, Surface Pro X)
- **All future Windows on ARM PCs**

---

## 🚀 Downloads (Latest Release: Android Studio 2026.2.1)

Direct links are available on the [**Latest Release Page**](https://github.com/DevanshSampat/android-studio-arm64-releases/releases/latest):

| Asset | Size | Description |
|---|---|---|
| 📦 **[AndroidStudio-2026.2.1-Windows-ARM64-Setup.exe](https://github.com/DevanshSampat/android-studio-arm64-releases/releases/latest)** | ~1.20 GB | **Recommended Installer**. Registers in Windows Start Menu, Desktop shortcuts, and Apps & Features. |
| 🗜️ **[AndroidStudio-2026.2.1-Windows-ARM64-Portable.zip](https://github.com/DevanshSampat/android-studio-arm64-releases/releases/latest)** | ~1.47 GB | Standalone Portable Archive. Extract anywhere and launch `bin\studio64.exe`. |
| 🎨 **[AndroidStudioArm64LayoutlibSetup.exe](https://github.com/DevanshSampat/android-studio-arm64-releases/releases/latest)** | ~20.2 MB | Native ARM64 Layoutlib & Skia graphics engine installer for Compose & XML preview rendering. |

---

## 🛡️ Windows Defender SmartScreen Notice

Because these open-source binaries are freshly compiled and not signed with a paid commercial Extended Validation (EV) certificate, Windows SmartScreen will display:

> *"Windows protected your PC: Microsoft Defender SmartScreen prevented an unrecognized app from starting"*

### How to Proceed:
1. Click **More info** on the prompt.
2. Click **Run anyway**.

Alternatively, unblock the installer via PowerShell:
```powershell
Unblock-File -Path .\AndroidStudio-2026.2.1-Windows-ARM64-Setup.exe
```

---

## ⚡ Why Native Windows ARM64?

- **Zero Emulation Overhead**: Runs directly on Cortex-X / Oryon CPU cores without Microsoft Prism or x64 emulation.
- **Cool & Power Efficient**: Lower battery consumption and minimal thermal throttling during long builds.
- **Embedded ARM64 OpenJDK**: Comes pre-packaged with ARM64 JetBrains Runtime 21.0.6.
- **Ultra-fast Native Binaries**: Native `studio64.exe`, `fsnotifier.exe`, `WinProcessListHelper.exe`, `WinShellIntegrationBridge.dll`, and `restarter.exe`.

---

## 🛠️ Related Repositories

- [android-studio-tools-base-arm64](https://github.com/DevanshSampat/android-studio-tools-base-arm64): Bazel cross-toolchains & native ARM64 platform targets.
- [android-studio-tools-adt-idea-arm64](https://github.com/DevanshSampat/android-studio-tools-adt-idea-arm64): Studio packaging & launcher configurations.
- [layoutlib-windows-arm64](https://github.com/DevanshSampat/layoutlib-windows-arm64): Native Windows ARM64 Layoutlib & Skia graphics runtime.
