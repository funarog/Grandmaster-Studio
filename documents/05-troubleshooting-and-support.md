# 05 — Troubleshooting & Support Guide

This guide addresses common questions, system alerts, and troubleshooting workflows for Grandmaster Studio.

---

## 1. Common Installation & Launch Issues

### Problem: macOS displays *"Grandmaster Studio cannot be opened..."*
* **Cause**: macOS Gatekeeper checks direct-distribution builds and blocks unnotarized binaries by default.
* **Solution**: In Finder, navigate to `/Applications`, right-click (or Control-click) `Grandmaster Studio.app`, and choose **Open**. In the confirmation dialog, click **Open**. Alternatively, authorize the app in **System Settings ▸ Privacy & Security**.

---

### Problem: *"Cannot access PGN files on External Drive or Desktop"*
* **Cause**: macOS Sequoia enforces strict file access permissions for non-sandboxed applications accessing user directories.
* **Solution**:
  1. Open **System Settings ▸ Privacy & Security ▸ Files and Folders**.
  2. Locate **Grandmaster Studio** in the list.
  3. Ensure toggles for **Removable Volumes**, **Desktop Folder**, or **Documents Folder** are set to **Allow**.

---

### Problem: Custom UCI Engine fails to start or crashes
* **Cause**: The external binary may be an Intel (`x86_64`) executable running without Rosetta 2, or missing execute permissions (`chmod +x`).
* **Solution**:
  1. Open Terminal and verify the architecture:
     ```bash
     file /path/to/engine_binary
     ```
     Ensure the output indicates `Mach-O 64-bit executable arm64`.
  2. Ensure execute permissions are granted:
     ```bash
     chmod +x /path/to/engine_binary
     ```

---

## 2. Licensing Troubleshooting

### Problem: *"License Key Invalid or Corrupted"*
* **Cause**: Trailing whitespace, linebreaks, or incomplete strings during copy-paste.
* **Solution**: Ensure the entire string beginning with `GMS1.` and ending after the signature is copied completely without leading or trailing spaces. If using the one-click activation link (`gmstudio://license/...`), try pasting the raw key manually in **Grandmaster Studio ▸ Help ▸ Beta License…**.

### Problem: App entered *"Read-Only Grace Mode"*
* **Cause**: Your beta evaluation period has expired.
* **Solution**: You can continue reading, viewing, and exporting all existing games and databases indefinitely. To restore editing, engine indexing, and AI Mentor dialogues, enter an updated beta key in **Settings ▸ License**.

---

## 3. Submitting Diagnostic Feedback

If you encounter unexpected behavior or an issue:

1. Open **Grandmaster Studio ▸ Help ▸ Send Feedback…** (or press `Cmd + Shift + F`).
2. Describe what you were doing when the issue occurred.
3. The built-in feedback tool automatically bundles an anonymized diagnostic package containing:
   * macOS version and Mac hardware identifier.
   * Engine process status and recent crash/error logs.
   * *Note*: Your personal games, PGN contents, and identity remain strictly confidential.
4. Click **Send Report** to submit.

---

## 4. Support & Community

* **Website**: [grandmaster.studio](https://grandmaster.studio)
* **Direct Feedback Email**: [support@grandmaster.studio](mailto:support@grandmaster.studio)
* **Bug Reports**: Use the in-app feedback dialog for fastest resolution.
