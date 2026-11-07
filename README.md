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

## 🛠️ Technical Details

- **Frontend:** HTML5, CSS3 (Tailwind CSS), Vanilla JavaScript.
- **Graphics:** High-resolution emoji-based visuals with CSS keyframe animations (`bounceIn`, `wobble`, `popIn`).
- **Sound Engine:** Custom `SoundEngine` class using Web Audio API for procedural tones (chimes, pops, fanfares).
- **Feedback:** Haptic-like visual feedback and a canvas-based confetti system for celebrations.
- **Language:** Optimized for Vietnamese instructions and labels.

## 🚀 How to Run

Since the application is contained within a single HTML file, you can run it simply by opening it in any modern web browser:

```bash
open KidsLogic/KidsLogic.html
```

## 📂 Project Structure

- `KidsLogic/KidsLogic.html`: The main application file containing all structure, styles, and logic.
- `KidsLogic/plan.md`: The original development plan and architectural roadmap.
- `KidsLogic/khoan_tron_so_*.jpeg`: Reference worksheet images used for content inspiration.

---

*Developed with ❤️ for early childhood education.*
