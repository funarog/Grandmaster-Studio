# Grandmaster Studio — Documentation Hub

Welcome to the documentation repository for **Grandmaster Studio**, the native chess database, interactive analytical studio, and AI mentor built exclusively for Apple Silicon and macOS Sequoia (macOS 15.6+).

This directory contains the proposed documentation suite structured as modular Markdown specifications. Once reviewed and refined, these documents will serve as the master content source for the official website user guides and online manual.

---

## Documentation Structure

| Document | Topic | Summary |
| :--- | :--- | :--- |
| **[01. Installation & Setup](./01-installation-and-setup.md)** | Getting Started | System requirements, direct distribution rationale, standard installation, and macOS Gatekeeper onboarding. |
| **[02. Licensing & Activation](./02-licensing-and-activation.md)** | License Management | Offline Ed25519 cryptographic licensing, one-click URL activation, manual key entry, and Read-Only Grace Mode. |
| **[03. Engine & Hardware Configuration](./03-engine-and-hardware-configuration.md)** | Performance & Engines | Metal API GPU acceleration, bundled Leela Chess Zero (LC0) WDL setup, custom UCI engines, and on-device AI Mentor. |
| **[04. Updates & Maintenance](./04-updates-and-maintenance.md)** | Lifecycle | Secure Sparkle update pipeline, automatic daily checks, and manual update verification. |
| **[05. Troubleshooting & Support](./05-troubleshooting-and-support.md)** | Diagnostics & Help | Built-in feedback reporter, resolving Gatekeeper alerts, permission handling, and support contacts. |

---

## Core Principles

1. **Native Apple Silicon First**: Every feature leverages Apple Silicon unified memory, Metal compute shaders, and hardware-accelerated machine learning.
2. **Zero-Telemetry & Privacy**: All game data, PGN databases, engine calculations, and cryptographic licenses operate 100% locally on your Mac.
3. **Graceful Degradation**: Expired or unlicensed installations remain fully functional as readers and viewers, safeguarding your intellectual property and game archives.

---

*Note: Review each guide in this folder. Web page conversion (`guide.html`, `docs/index.html`, etc.) will proceed following your feedback.*
