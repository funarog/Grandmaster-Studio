# 01 — Installation & Setup Guide

This guide walks you through system requirements, downloading, installing, and authorizing **Grandmaster Studio** on macOS.

---

## 1. System Requirements

Grandmaster Studio is engineered from the ground up specifically for modern Mac hardware:

* **Operating System**: macOS 15.6 or later (macOS Sequoia).
* **Hardware Architecture**: Native Apple Silicon only (`arm64`). Supported processors include:
  * Apple M1, M1 Pro, M1 Max, M1 Ultra
  * Apple M2, M2 Pro, M2 Max, M2 Ultra
  * Apple M3, M3 Pro, M3 Max
  * Apple M4, M4 Pro, M4 Max
* **Memory & Graphics**: Unified memory architecture with native Apple Metal API support for real-time 60fps board rendering, piece vector shaders, and neural-network engine backends.
* **On-Device Intelligence**: Compatible with Apple Intelligence / Foundation Models (`LanguageModelSession`) for the AI Chess Mentor, with local fallback options to Core ML and local LLM endpoints.

> **Note**: Intel-based Macs (`x86_64`) are not supported due to the deep integration with Apple Silicon neural engines and unified memory bandwidth.

---

## 2. Direct Distribution Model

Grandmaster Studio is distributed directly as an archive (`GrandmasterStudio-Beta.zip` or `.dmg`) from [grandmaster.studio](https://grandmaster.studio).

### Why Direct Distribution?
Modern chess analysis requires spawning and controlling separate background engine subprocesses using the Universal Chess Interface (UCI) protocol (such as Leela Chess Zero and Stockfish). Apple's standard Mac App Store sandbox restrictions prohibit managing arbitrary or bundled subprocess engines in this manner. Distributing directly gives you full control over your engines, database directories, and performance.

---

## 3. Standard Installation Steps

1. **Download**: Obtain the latest build from the official website or your beta welcome link.
2. **Mount / Extract**: Open the downloaded `.dmg` image or `.zip` file.
3. **Install**: Drag **Grandmaster Studio.app** directly into your Mac's local `/Applications` folder:

```
[ Grandmaster Studio.app ]  ───►  📁 /Applications
```

4. **Launch**: Launch Grandmaster Studio from `/Applications`, Spotlight (`Cmd + Space`), or Launchpad.

---

## 4. macOS Gatekeeper & Security Onboarding

Because early preview and beta builds are distributed directly outside the Mac App Store, macOS Gatekeeper may display a security dialog upon first launch:

> *"Grandmaster Studio cannot be opened because Apple cannot check it for malicious software."*

This is standard macOS security behavior for newly distributed developer applications. You can authorize the app in seconds using either method below:

### Method A: Right-Click "Open" (Recommended)
1. Open **Finder** and navigate to your `/Applications` folder.
2. **Control-click** (or right-click) on **Grandmaster Studio.app**.
3. Choose **Open** from the context menu.
4. A security dialog appears featuring an explicit **Open** button. Click **Open**.
5. The app launches immediately and macOS permanently stores this authorization.

### Method B: System Settings Override
1. Double-click **Grandmaster Studio.app**. When the warning dialog appears, click **Done** or **OK**.
2. Open **System Settings** on your Mac.
3. Select **Privacy & Security** in the sidebar.
4. Scroll down to the **Security** heading.
5. You will see: *"Grandmaster Studio was blocked from use because it is not from an identified developer."*
6. Click **Open Anyway** and authenticate with Touch ID or your Mac administrator password.

---

## 5. Seamless Subsequent Updates

Once you complete this initial one-time authorization, subsequent updates downloaded through the built-in **Sparkle** updater are automatically recognized and will **not** trigger Gatekeeper dialogs again.
