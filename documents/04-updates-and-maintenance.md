# 04 — Updates & Maintenance Guide

Grandmaster Studio utilizes the industry-standard **Sparkle** open-source framework for reliable, cryptographically verified in-app updates.

---

## 1. Update Architecture

The update delivery pipeline is designed to be frictionless, secure, and respectful of your workflow:

* **Secure HTTPS Appcast Feed**: Monitored at `https://grandmaster.studio/beta/appcast.xml`.
* **Ed25519 Release Signatures**: Every downloadable release package is signed with an independent Ed25519 developer key. The Sparkle engine verifies the cryptographic signature before any files are unpacked or replaced.
* **Preserved User Data**: Application databases, configuration files, and PGN libraries are stored safely in standard macOS Application Support directories (`~/Library/Application Support/Grandmaster Studio`) and are never modified or overwritten during an application update.

---

## 2. Automatic & Manual Update Checks

### Automatic Background Checks
By default, Grandmaster Studio checks the release feed once per day in the background. When an update is ready:
1. A non-intrusive notification badge appears.
2. Clicking the update prompt displays the release notes, new features, and bug fixes.
3. You can choose **Install and Relaunch** immediately, or **Remind Me Later**.

### Manual Check
You can check for new builds at any time:
1. Click **Grandmaster Studio** in the macOS menu bar.
2. Select **Check for Updates…**.
3. If an update is available, the updater dialogue will display the latest release notes and download options.

---

## 3. Gatekeeper Compatibility

One of the major advantages of the Sparkle update architecture is that once you have authorized Grandmaster Studio upon its initial launch, macOS Gatekeeper trusts subsequent updates installed through Sparkle. You will **not** need to perform the right-click "Open" procedure on subsequent updates.
