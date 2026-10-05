# 03 — Engine & Hardware Configuration Guide

Grandmaster Studio is optimized for Apple Silicon hardware, pairing deep GPU compute with advanced chess engines and on-device natural language models.

---

## 1. Apple Silicon & Metal Architecture

Unlike legacy chess software adapted from x86 platforms, Grandmaster Studio leverages macOS-native frameworks:

* **Unified Memory Architecture (UMA)**: The CPU, GPU, and Apple Neural Engine (ANE) share a high-bandwidth unified memory bus (up to 800+ GB/s on Max/Ultra chips). This enables lightning-fast neural network weights loading without copying data over discrete PCIe links.
* **Metal Compute Shaders**: Chessboard rendering, vector piece transformations, and neural matrix multiplications run directly through the Apple Metal API for smooth 60fps interaction and low thermal impact.

---

## 2. Integrated Leela Chess Zero (LC0)

Grandmaster Studio bundles a custom build of **Leela Chess Zero (LC0)** compiled with native Metal acceleration:

* **Win/Draw/Loss (WDL) Metrics**: In addition to standard centipawn numbers, Leela delivers precise probability curves (e.g., `wdl:[35%, 52%, 13%]`) revealing the practical winnable margin of any position.
* **Pawn Structure Intuition**: Neural-network evaluations prioritize long-term positional harmony, king safety, and structural imbalances over superficial tactical brute force.
* **Network Weights Selection**: High-performance neural weights are bundled natively, with options to drop in custom `.pb` or `.onnx` weight files via **Settings ▸ Engines ▸ Leela**.

---

## 3. Custom UCI Engine Integration

Grandmaster Studio fully supports the Universal Chess Interface (UCI) standard. You can connect any UCI-compliant engine:

### Adding an External Engine (e.g., Stockfish)
1. Open **Grandmaster Studio ▸ Settings…** (`Cmd + ,`).
2. Navigate to the **Engines** tab.
3. Click **Add Engine (+)**.
4. Select your compiled ARM64 binary (e.g., `/usr/local/bin/stockfish`).
5. Configure your hardware allocation:
   * **Threads**: Recommend setting to the number of Performance cores on your Mac.
   * **Hash Size (RAM)**: Unified memory allows generous hash allocation (e.g., 4096 MB – 16384 MB depending on available system RAM).
6. Click **Save**. The engine is now available in your analysis panels and match tournaments.

---

## 4. On-Device AI Chess Mentor

Grandmaster Studio integrates an on-device conversational Chess Mentor designed to explain the *why* behind moves rather than reciting lines of algebraic notation:

* **Apple Intelligence Foundation Models**: Runs through native `LanguageModelSession` on macOS 15.6+ with complete privacy. Your games and questions never leave your device.
* **Fallback Options**:
  * **Core ML**: Local transformer models optimized for the Apple Neural Engine.
  * **Local Endpoints**: Connect to local runners such as LM Studio or Ollama for power users seeking specialized fine-tuned chess explanation models.
* **Contextual Analysis**: The Mentor receives real-time FEN states, active engine evaluations, and historical opening statistics to provide human-like grandmaster commentary.
