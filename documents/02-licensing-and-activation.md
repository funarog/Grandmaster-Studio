# 02 — Licensing & Activation Guide

Grandmaster Studio implements a modern, privacy-first licensing system based on offline public-key cryptography. There are no tracking scripts, telemetry agents, or periodic server phone-home requirements.

---

## 1. Cryptographic Model (Offline Ed25519)

Your license key is cryptographically signed using an **Ed25519** private key. The application bundles the corresponding public key and verifies your license mathematically on your device without transmitting data over the Internet.

* **No Account Required**: You never need to create an online account or maintain a persistent Internet connection to use the app.
* **Zero Telemetry**: We never track your game analyses, database sizes, opening choices, or session duration.
* **Portable**: Your license can be backed up or transferred effortlessly.

---

## 2. License Key Format

Grandmaster Studio license keys follow the standard `GMS1` token format:

```
GMS1.<base64url_payload>.<base64url_signature>
```

* **Header (`GMS1`)**: Identifies the Grandmaster Studio schema version 1.
* **Payload**: Encodes license metadata (Licensee Name, Email, Issue Date, Expiration Date, and Tier).
* **Signature**: Cryptographic Ed25519 signature guaranteeing that the license was issued authentically and has not been altered.

---

## 3. Activation Methods

You can activate Grandmaster Studio using either of the following methods:

### Method A: One-Click Instant Activation (Recommended)
If you received an invitation or beta onboarding email, click the provided activation link:

```
gmstudio://license/GMS1.eyJzdWI...
```

1. Clicking the link prompts macOS to open **Grandmaster Studio**.
2. The application intercepts the `gmstudio://` URL scheme, validates the cryptographic signature instantly, and displays a confirmation dialog.
3. Your studio environment unlocks immediately.

### Method B: Manual License Entry
1. Copy the full license key string (`GMS1...`) from your confirmation email.
2. Launch **Grandmaster Studio**.
3. If this is your first launch, paste the key into the activation field in the Welcome window.
4. If the app is already open, navigate to the menu bar:
   * Select **Grandmaster Studio ▸ Help ▸ Beta License…** (or **Settings ▸ License**).
5. Paste your key and click **Activate**.

---

## 4. Application Operating States

Grandmaster Studio believes you should never be locked out of your own intellectual work. The software operates under two distinct states:

### 1. Active State (Fully Licensed)
* Complete access to high-speed SQLite and PGN database indexing.
* Full authoring, editing, and game annotation capabilities.
* Integrated Leela Chess Zero (LC0) neural-network evaluations and Win/Draw/Loss probability curves.
* Context-aware AI Chess Mentor dialogues.
* Multi-format export (PGN, AsciiDoc, HTML web reports, PDF).

### 2. Read-Only Grace Mode (Unlicensed or Expired)
If your beta license expires or is removed, the app does **not** lock you out or corrupt your files. Instead, it gracefully enters **Read-Only Mode**:
* **Always Accessible**: You can continue to launch the app, open all of your existing PGN databases, inspect historical game collections, replay moves, and view previously generated evaluations.
* **Full Export Access**: You can export your games, annotations, and study materials at any time.
* **Paused Features**: New game edits, database rebuilds, live background engine indexing, and AI Mentor conversations are temporarily suspended until a valid license is entered.
