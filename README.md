# 🧠 KidsLogic — Interactive Early Learning App

KidsLogic is a rich, interactive web application designed for children aged 3–6. Inspired by the **"Khoanh Tròn Số"** (Circle the Number) worksheets, this app helps children practice counting, comparison, and logical thinking through engaging gameplay, delightful animations, and procedural sound effects.

## 🌟 Features

- **6 Unique Game Modes:** Covers counting, comparing, matching, sequencing, coloring, and ordering.
- **Progressive Difficulty:** 5 levels per game mode, ranging from simple 1-3 counting to complex 1-10 challenges with timers.
- **Reward System:** Earn stars (1-3) based on performance and unlock 8 unique achievement badges.
- **Interactive Mascot:** "Cáo Con" (Baby Fox) provides encouragement and helpful hints.
- **Procedural Audio:** Sound effects and Text-to-Speech (TTS) instructions generated via Web Audio API (no external audio files needed).
- **Responsive Design:** Optimized for iPad, iPhone, and Desktop with large touch targets and fluid layouts.
- **Offline Ready:** A single, self-contained HTML file (~2,000 lines) with no external dependencies (uses Tailwind CSS via CDN).
- **Persistence:** High scores and badges are saved locally on the device using `LocalStorage`.

## 🎮 Game Modes

1.  **🔢 Khoanh Tròn Số (Count & Circle):** Count the objects and select the correct number.
2.  **⚖️ Nhiều Hơn - Ít Hơn (More or Less):** Compare two groups of objects to find which is larger or smaller.
3.  **🎯 Tìm Nhóm Đúng (Match the Number):** Look at a number and pick the group with the corresponding quantity.
4.  **🧩 Số Tiếp Theo (Sequence):** Fill in the missing number in a logical sequence.
5.  **🎨 Đếm Theo Màu (Color Count):** Filter objects by color and count only the target items.
6.  **🔤 Sắp Xếp Thứ Tự (Number Ordering):** Tap numbers in ascending or descending order.
7.  **🔗 Nối Số & Hình (Connect & Match):** Draw lines with your finger/mouse to connect numbers with their corresponding object groups.

## 🕹️ Input Protection ("Wait for Turn")

To ensure a frustration-free experience for young children, the app implements a robust input locking system:
- **Locking Mechanism:** Uses an `isProcessingAnswer` guard and `pointer-events: none` to prevent double-taps or rapid-fire answering during animations.
- **Focus Guard:** Interaction is briefly disabled during transition sounds and confetti celebrations to ensure the child observes the feedback before proceeding.
- **Feedback Loop:** Wrong answers trigger a gentle shake animation and mascot hint, encouraging the child to pause and recount before trying again.

## 🏗️ App Structure

The application is built with a modular, class-based architecture contained within a single file for maximum portability:

- **Screen Manager:** A single-page application (SPA) architecture using CSS classes (`hidden`/`flex`) to swap between:
    - `screenHome`: Entry point with mascot and high scores.
    - `screenModeSelect`: Catalog of 6 learning activities.
    - `screenLevelSelect`: Progression mapping for each mode.
    - `screenGamePlay`: The interactive worksheet stage.
    - `screenLevelComplete`: Celebratory results and star awards.
    - `screenBadges`: Achievement showcase.
- **Logic Core (`KidsLogicApp`):** The central controller managing the game state, question progression, and UI updates.
- **Utility Modules:**
    - `SoundEngine`: Generates procedural audio tones and manages Text-to-Speech.
    - `ConfettiEffect`: Handles the canvas-based celebration particles.
    - `StorageManager`: Wraps `LocalStorage` for persistent progress tracking.
- **Procedural Generation:** Questions are dynamically generated at runtime based on level-specific ranges (`range`) and themed emoji libraries (`THEMES`), ensuring no two sessions are identical.

## 🛠️ Technical Details

- **Frontend:** HTML5, CSS3 (Tailwind CSS), Vanilla JavaScript.
- **Graphics:** High-resolution emoji-based visuals with CSS keyframe animations (`bounceIn`, `wobble`, `popIn`).
- **Sound Engine:** Custom `SoundEngine` class using Web Audio API for procedural tones (chimes, pops, fanfares).
- **Feedback:** Haptic-like visual feedback and a canvas-based confetti system for celebrations.
- **Language:** Optimized for Vietnamese instructions and labels.

## 🚀 How to Run

Since the application is contained within a single HTML file, you can run it simply by opening it in any modern web browser:

```bash
open KidsLogic/index.html
```

## ☁️ Deployment (Cloudflare Pages / Wrangler)

KidsLogic is fully static and can be deployed instantly to Cloudflare Pages or Cloudflare Workers using Wrangler.

### 1. Cloudflare Pages Deployment
Publish the directory directly using Wrangler CLI:
```bash
npx wrangler pages deploy . --project-name=kidslogic
```

### 2. Cloudflare Workers (Static Assets) Deployment
Create a `wrangler.toml` in the project root:
```toml
name = "kidslogic"
compatibility_date = "2026-01-01"

[assets]
directory = "."
```
Then deploy via Wrangler:
```bash
npx wrangler deploy
```

## 📂 Project Structure

- `KidsLogic/index.html`: The main application file containing all structure, styles, and logic.
- `KidsLogic/README.md`: Project documentation and technical overview.

---

*Developed with ❤️ for early childhood education.*
