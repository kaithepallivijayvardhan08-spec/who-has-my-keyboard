# 🦆 WHO HAS MY KEYBOARD?
> *The high-octane, chaotic multiplayer couch & party arena where everyone wants the golden duck, but only one keyboard survives.*

[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-19.0-61dafb?logo=react&logoColor=black)](https://react.dev/)
[![Express](https://img.shields.io/badge/Express-4.21-000000?logo=express&logoColor=white)](https://expressjs.com/)
[![Socket.IO](https://img.shields.io/badge/Socket.IO-4.8-010101?logo=socketdotio&logoColor=white)](https://socket.io/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.1-38bdf8?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-emerald)](#license)

---

## 🎯 What Is This?

Ever sat on a couch with friends, wanting to play a fast-paced multiplayer party brawl without buying four separate $70 console controllers?

**WHO HAS MY KEYBOARD?** solves this with a modern Jackbox-meets-Smash-Bros architecture. It turns your PC or big-screen TV into the **Main Arena Display**, while allowing anyone in the room to pull out their smartphone, scan a dynamic QR code, and transform their phone into a zero-install, responsive touchscreen gamepad with haptic feedback, directional joystick controls, and power-up buttons.

Hold the Golden Keyboard Duck for **15 seconds** to claim victory. But watch out: other players can tackle you at full speed, reverse your screen controls, drop banana peels, slap you into an uncontrollable 3-second disco dance, or freeze you in ice!

---

## ✨ Core Highlights

- 📱 **Zero-Install Phone Controller (BYOD)**  
  Players scan an on-screen QR code to immediately join the lobby from Safari or Chrome. No apps to download, no Bluetooth pairing headaches.
- ⚡ **Authoritative 60 FPS Physics Simulation**  
  Server-authoritative game loop with sub-millisecond Socket.IO tick broadcasts, predictive client-side interpolation, and responsive physical collisions.
- 💥 **Tackle & Bump Dynamics**  
  Sprint into the duck carrier to forcefully knock the golden keyboard loose with realistic angular impulse recoil.
- 🌀 **Hilarious & Disruptive Power-Ups**
  - 🏎️ **Super Speed**: 2x boost with burning tire tracks.
  - 🍌 **Banana Peel**: Leaves slippery traps that spin players out of control.
  - 🔄 **Glitch Reversal**: Inverts all opposing players' joystick axes.
  - 🕺 **Disco Ball**: Traps opponents in an involuntary neon dance break.
  - ❄️ **Freeze Wave**: Coats rivals in a block of ice.
  - 🛡️ **Shield Bubble**: Deflects incoming hits and traps.
- 🌍 **Full Multi-Language Localization (`i18n`)**  
  English, Español, Français, Deutsch, 日本語, 한국어, and Português.
- 🎵 **Procedural Web Audio Synthesizer**  
  No external audio assets required. All arcade chiptunes, tackle bumps, power hums, and victory jingles are synthesized in real-time.
- 💾 **Hybrid Persistence Engine**  
  MongoDB integration for persistent stats, match histories, and accounts, with an automatic resilient in-memory fallback for instant offline or zero-config development.

---

## 🏗️ Architecture & Technology Stack

```
 ┌─────────────────────────────────────────────────────────────┐
 │                      THE MAIN ARENA                         │
 │      (PC Screen / Living Room TV / Laptop Projector)        │
 │                                                             │
 │   • 60 FPS HTML5 Canvas Arena Engine                        │
 │   • Real-time HUD, Kill-feed announcements & Timers         │
 │   • Web Audio Chiptune Synthesizer                          │
 └──────────────────────────────┬──────────────────────────────┘
                                │
                      WebSocket / Socket.IO
                                │
 ┌──────────────────────────────┴──────────────────────────────┐
 │                AUTHORITATIVE GAME SERVER                    │
 │               (Node.js + Express + tsx)                     │
 │                                                             │
 │   • 60 Hz Physics & Collision Simulation (Arena Bounds)     │
 │   • Duck Carrier Timer & Tackling Impulse Calculations      │
 │   • Room Manager (4-character unique alphanumeric codes)    │
 │   • Optional MongoDB User Profile & Stats Layer             │
 └──────────────────────────────┬──────────────────────────────┘
                                │
                     Local Wi-Fi / Tunnel Link
                                │
 ┌──────────────────────────────┴──────────────────────────────┐
 │               SMARTPHONE CONTROLLER CLIENTS                 │
 │            (Player 1, Player 2, Player 3, Player 4)         │
 │                                                             │
 │   • Zero-install Mobile Touch D-Pad & Action Buttons        │
 │   • Real-time Carrier Alert Vibration / Visual HUD          │
 │   • One-tap Ready Up & Power Activation                     │
 └─────────────────────────────────────────────────────────────┘
```

---

## 🚀 Quick Start (Play in 60 Seconds)

### Prerequisites
- [Node.js](https://nodejs.org/) (version 18 or higher recommended)
- `npm` or `yarn`

### 1. Clone & Install
```bash
git clone https://github.com/your-username/who-has-my-keyboard.git
cd who-has-my-keyboard
npm install
```

### 2. Start the Full-Stack Game Server
```bash
npm run dev
```

Your terminal will display your connection addresses:
```text
🦆 WHO HAS MY KEYBOARD? server running on port 3000!
  ➜ Local:   http://localhost:3000
  ➜ Network: http://192.168.1.45:3000
```

### 3. Jump In
1. Open `http://localhost:3000` in your desktop browser.
2. Click **Create Room** or **Quick Play**.
3. Scan the QR code with your phone (or click **📱 Open Controller in New Tab** to test on one machine).
4. Hit **Ready Up** and let the keyboard snatching begin!

---

## 🎮 How to Play with Friends on Local Wi-Fi (VS Code / Local PC)

When running locally on your computer:

1. **Connect to the same Wi-Fi network**: Make sure your phone and computer are on the same Wi-Fi.
2. **Dynamic QR Code**: The lobby automatically detects your computer's local network IP (e.g., `http://192.168.x.x:3000`) and bakes it into the QR code.
3. **Scan with Phone Camera**: Point your iOS or Android camera at the QR code on the desktop monitor, tap the prompt, and you're in the game!

> 💡 **Remote / Cellular Play**: If friends want to join from outside your home Wi-Fi, you can use **VS Code Port Forwarding** (set port `3000` visibility to *Public*) or [ngrok](https://ngrok.com/) (`ngrok http 3000`).

---

## 🕹️ Controls Reference

### 💻 Desktop Keyboard
| Key | Action |
|:---:|:---|
| <kbd>W</kbd> <kbd>A</kbd> <kbd>S</kbd> <kbd>D</kbd> or <kbd>▲</kbd> <kbd>◀</kbd> <kbd>▼</kbd> <kbd>▶</kbd> | Move Character |
| <kbd>Space</kbd> or <kbd>E</kbd> | Activate Stored Power-Up |
| <kbd>Esc</kbd> or <kbd>P</kbd> | Pause Match / Open Menu |

### 📱 Smartphone Controller
| Control | Action |
|:---:|:---|
| **Virtual D-Pad / Touch Stick** | 360-degree directional analog movement |
| **POW Button** | Trigger collected power-up |
| **Ready / Rematch** | Instant one-tap lobby readiness |

---

## 🛠️ Project Structure

```
├── server.ts                 # Authoritative Express + Socket.IO physics engine & API routes
├── src/
│   ├── main.tsx              # React entry point
│   ├── App.tsx               # Orchestrator (Rooms, Navigation, Account Modals)
│   ├── types.ts              # Unified type definitions (GameRoomState, Powers, Slots)
│   ├── data/
│   │   └── gameConstants.ts  # Character attributes, arena dimensions, power specs
│   ├── services/
│   │   ├── socketClient.ts   # Resilient WebSocket client wrapper
│   │   └── soundService.ts   # Pure Web Audio API synthesized soundscape
│   ├── i18n/                 # Localization engine (EN, ES, FR, DE, JA, KO, PT)
│   └── components/
│       ├── ArenaCanvas.tsx   # 60 FPS HTML5 rendering canvas & visual particle FX
│       ├── LobbyView.tsx     # Party lobby, character picker & QR code generator
│       ├── MobileController.tsx # Mobile phone touchscreen gamepad view
│       ├── GameHUD.tsx       # Live in-game standings, countdowns & alerts
│       ├── ResultsModal.tsx  # Podium celebration, confetti & match statistics
│       └── NavigationModals.tsx # How to play, pause screen, and settings
├── package.json              # Scripts and dependencies
└── tsconfig.json             # TypeScript configuration
```

---

## ⚙️ Available Scripts

| Command | Description |
|:---|:---|
| `npm run dev` | Starts server + Vite development server with hot reloads |
| `npm run build` | Compiles client assets and bundles server to `dist/server.cjs` |
| `npm start` | Runs the compiled production build on port 3000 |
| `npm run lint` | Performs strict TypeScript type checks across the entire codebase |

---

## 🤝 Contributing

Got an idea for a ridiculous power-up, hilarious character skin, or new game mode?
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/MegaAnvilPower`)
3. Commit your Changes (`git commit -m 'feat: Add Mega Anvil power-up'`)
4. Push to the Branch (`git push origin feature/MegaAnvilPower`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<p align="center">
  Built for chaotic couch nights, office tournaments, and family showdowns.<br/>
  <strong>Now grab that duck! 🦆</strong>
</p>
