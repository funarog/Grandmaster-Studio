# Grandmaster Studio — Web & Growth Brainstorming

*Captured on: October 2, 2026*
*Context: Brainstorming product-led growth, website structure, and community building for Grandmaster Studio.*

## 1. Web Architecture (Dog-fooding the App)
Instead of adopting a heavy web framework, the website should be an organic extension of **Grandmaster Studio's native capabilities**.
*   **Tech Stack:** Vanilla HTML/CSS (matching the existing `index.html` dark-mode theme).
*   **The Content Engine:** All blog posts, documentation, and analysis are authored natively in Grandmaster Studio using the **Doc-as-Chess** workflow (`DocAsChessCodec` / `AsciiDocNotesStore`).
*   **Core Pages to Build:**
    *   `/blog.html` — Directory for "The Art of Modern Chess Analysis".
    *   `/timman.html` — Landing page/hub for the collaborative analysis project.
    *   `/guide.html` — The User Guide (which shares identical structure/files with the offline macOS app manual).
    *   `/post-template.html` — A CSS-styled container designed to flawlessly render exported AsciiDoc from the macOS app.

## 2. Lead Magnet: The Web Utility
To compete with tools like *Forward Chess* and *Chessify*, we offer a taste of GM Studio's core capability directly in the browser.
*   **The Concept:** A standalone web utility (e.g., `grandmaster.studio/converter`).
*   **The Function:** A drag-and-drop zone where users can drop `.pgn` files and the site instantly converts them into beautifully formatted `.adoc` (AsciiDoc) files.
*   **The "Why":** It trains users on the Doc-as-Chess format. They see how text maps to chess notation, planting the seed that they need the full native macOS app to properly view, edit, and analyze these documents.

## 3. Top-of-Funnel Traffic Steering
Leverage existing giants (Lichess, Chess.com) rather than trying to build a rival blogging engine from scratch.
*   **Lichess Studies:** Create exceptionally detailed interactive studies using GM Studio's AI Mentor. In the chapter notes: *"Generated with Grandmaster Studio. Read the full topological breakdown at [link]"*.
*   **Chess.com Blogs:** Publish part 1 of deep-dive articles ("The Art of Modern Chess Analysis") using Eval Graph screenshots to drive curiosity, pushing readers to the main site for the conclusion.
*   **PGN Watermarking:** Automatically inject `[Site "Analyzed in Grandmaster Studio"]` into all PGNs exported from the macOS app.

## 4. Community & Collaboration: "What Timman Knew"
Inspired by Andy Lee's essay on *Lit & Chess*, the goal is to build a platform that resurrects **"Chess Analysis as a Conversation."** Modern engines provide "the truth," which shuts down discussion. Grandmaster Studio intends to lean into the collaborative, argumentative side of chess.
*   **The Problem:** The original Substack article gained very little interaction (only 1 comment). Why? Because Substack doesn't let users drag/drop PGNs, move pieces, or debate variations seamlessly. 
*   **The Solution (Discourse vs. Reddit):**
    *   **Reddit (`r/chess`):** Use purely as the **Discovery Layer**. Post the *conclusions* of analyses here to drive clicks. Do not expect long-term collaboration here; Reddit threads are ephemeral and trend toward beginner-level engine spam.
    *   **Discourse (The Archival / Collaboration Layer):** The true mechanism for the "What Timman Knew" concept. Embed Discourse directly at the bottom of `/timman.html` (or host at `forum.grandmaster.studio`). Discourse supports markdown plugins allowing users to paste PGNs and render them as boards. It allows for multi-day, multi-branch discussions where players can debate middlegame archetypes without relying solely on engine evaluations.

## 5. Content Strategy: The Anchor Article
The flagship piece for launching the "collaboration" idea will be the analysis of **Portisch vs. Smyslov (1971)**.
*   **The Narrative Hook:** A deep dive into the human elements of the game. For 15 moves, it remains in the draw zone despite deep GM analysis. 
*   **The Human Irony:** The analysis reveals that Portisch could have adopted Smyslov's own strategy to secure drawing chances. Even more ironic, neither player found the critical move that benefited Portisch—highlighting a classic human cognitive bias over pure computational truth. And incredibly, at move 20, Portisch still possessed an explosive, hidden resource to salvage a draw.
*   **Why this works for Grandmaster Studio:** This is exactly the kind of nuanced, psychology-driven analysis that engines kill but Grandmaster Studio's AI Mentor / Doc-as-Chess format is designed to illuminate and debate. This article, published on `/timman.html` (or as the first major blog entry), will be the ultimate proof-of-concept for why "chess analysis is a conversation," using the Discourse backend to invite users to debate the missed move 20 resource.
