<div align="center">

# 🕹️ Neon Arcade — 15 Games

### A Single-Page, No-Build Arcade Hub

<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white">
<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white">
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">
<img src="https://img.shields.io/badge/Games-15-FF00E5?style=for-the-badge">
<img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge">

> A single-page, no-build arcade hub built with vanilla HTML, CSS, and JavaScript — 15 fully playable classic and original games behind one neon-themed launcher screen.

**[🎮 Play Live](https://akshatsingh1427.github.io/NeonArcade/)**

</div>

---

## Table of Contents

- [Live Demo](#-live-demo)
- [What It Is](#what-it-is)
- [Games Included](#games-included)
- [File Structure](#file-structure)
- [How to Run](#how-to-run)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Notes](#notes)

---

## 🌐 Live Demo

**[https://akshatsingh1427.github.io/NeonArcade/](https://akshatsingh1427.github.io/NeonArcade/)**

Hosted on GitHub Pages — open the link and start playing, no setup required.

---

## What It Is

**Neon Arcade** is a browser-based games hub. The landing page shows a grid of 15 game cards; clicking one opens a modal that boots the selected game on an HTML canvas, tracks your score, and records it against a running best score and games-played counter — all client-side, no backend, no build step.

---

## Games Included

| Game | Type | Description |
|---|---|---|
| Snake | Classic | Eat food, grow longer, avoid walls |
| Breakout | Arcade | Break all bricks with your ball |
| Tic Tac Toe | Strategy | Beat the minimax AI — if you can |
| Flappy Bird | Action | Tap to fly through the pipes |
| Memory | Puzzle | Match all emoji pairs to win |
| Pong | Classic | Classic Pong — you vs. smart AI |
| 2048 | Puzzle | Merge tiles to reach 2048 |
| Minesweeper | Strategy | Clear the board, avoid the mines |
| Type Racer | Arcade | Type words fast — 30 second sprint |
| Simon Says | Classic | Watch and repeat the color pattern |
| Wordle | Puzzle | Guess the 5-letter word in 6 tries |
| Dino Run | Action | Jump over cacti — endless runner |
| Tetris | Classic | Stack blocks, clear lines, survive |
| Trivia Quiz | Strategy | 10 questions — test your knowledge |
| Ball Shoot | Action | Aim and shoot moving targets |

---

## File Structure

```
neon-arcade/
├── index.html    ← page markup, links to style.css and script.js
├── style.css     ← all styling: layout, card grid, modal, neon theme, animations
└── script.js     ← game registry, launcher/modal logic, and all 15 game implementations
```

All three files must stay in the same folder — `index.html` references the other two by relative path (`<link href="style.css">`, `<script src="script.js">`).

---

## How to Run

No install, no server, no dependencies required.

```
1. Keep index.html, style.css, and script.js in the same folder
2. Open index.html in any modern browser
3. Click a game card to launch it in the modal
4. Play — score and best-score tracking happens automatically
```

---

## Architecture

- **`GAMES` array** (in `script.js`) — defines each game's id, name, emoji, description, category tag, and preview color; the launcher grid is rendered from this array
- **Launcher/modal system** — clicking a card opens `#ov`/`#modal`, injects a `<canvas>` or DOM-based game board into `#gcw`, and calls the matching `launchX()` function
- **Per-game functions** — each game (`launchSnake()`, `launchBreakout()`, `launchTicTac()`, etc.) is self-contained: sets up its own game loop via `requestAnimationFrame` (or interval-based logic for turn-based games like Tic Tac Toe/Minesweeper/Quiz), handles its own input, and reports score back through a shared `setScore()` call
- **Stars background** — a lightweight canvas particle effect running behind the whole page (`canvas#stars`), independent of any game

---

## Tech Stack

<div align="center">

<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white">
<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white">
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">

</div>

| Layer | Technology |
|---|---|
| **Structure** | HTML5 |
| **Styling** | Vanilla CSS — Grid/Flexbox, `clamp()` for responsive sizing, CSS gradients for the neon theme |
| **Logic** | Vanilla JavaScript — ES5-style `var`/`function`, no framework, no build tooling |
| **Rendering** | HTML5 Canvas (per-game) |
| **Fonts** | Orbitron, Rajdhani (Google Fonts) |

---

## Notes

- This is the **desktop-oriented build** — it doesn't include the touch-event handling or mobile viewport tuning found in the mobile-optimized variant of this project, so on-screen touch controls won't appear on mobile.
- All game state (best score, games played) lives in memory for the session only; nothing persists between page reloads.

<div align="center">

**Built with vanilla web technologies — zero dependencies, zero build step.**

</div>
