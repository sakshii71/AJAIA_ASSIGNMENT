# SidelineReel — PM Take-Home Assessment & Core Prototype

Built for the **Ajaia LLC** Product Manager assessment ([https://ajaia.ai](https://ajaia.ai)).

[![Live Prototype](https://img.shields.io/badge/Live%20Prototype-Netlify-00C7B7?style=for-the-badge&logo=netlify)](https://moonlit-croissant-663e90.netlify.app)
[![Loom Walkthrough](https://img.shields.io/badge/Loom-Walkthrough%20Video-625DF5?style=for-the-badge&logo=loom)](https://www.loom.com/share/e6430ae21da1450db2d58424b3aca1e6)
[![Assignment Doc](https://img.shields.io/badge/Document-assignment.md-4F46E5?style=for-the-badge)](assignment.md)

---

## 📌 Executive Summary

SidelineReel automates youth sports video: coaches upload game footage, computer vision extracts each athlete's highlights, and families automatically receive personalized highlight reels and weekly team recaps.

### The Strategic Decision
* **#1 What We Build Next — Roster-Tagging Accuracy Engine & Coach Review:** Fix computer vision digit confusion (e.g. 14 vs 4, 1 vs 11, transposed 16 vs 61) that drives "wrong kid" thumbnails, contributes to ~30% unopened reels, causes severe family disappointment, and risks child privacy.
* **#2 Local Quiet-Hours Notification Dispatch:** Solves late-night notification drops to lift open rates.
* **#3 Scout & Family Pass for Ridgeline:** Provides verified public web links for grandparents and college scouts, solving the root access need without committing to high-risk live video infrastructure ahead of signups.
* **What We Are NOT Building Now:**
  1. *Full Live Streaming (Carla / Ridgeline \$180k request):* High technical/field hardware risk, unvalidated bandwidth feasibility on youth fields [Assumption, engineering to validate], and protects the wrong asset (reels are what renewed parents).
  2. *Reel Editor Upgrades (58% survey ask):* Classic say-do gap. Only 6% of parents ever opened the editor, and under 1% of those who opened finished an edit (under 0.06% of all parents).

---

## 🔗 Submission Links

| Deliverable | Link | Description |
| :--- | :--- | :--- |
| **🎥 Video Walkthrough** | [Loom Recording](https://www.loom.com/share/e6430ae21da1450db2d58424b3aca1e6) | 3-minute screen recording walking through the prototype & strategy |
| **🚀 Live Prototype** | [Netlify App](https://moonlit-croissant-663e90.netlify.app) | Fully interactive 3-screen working prototype (no login required) |
| **📄 Full Written Response** | [assignment.md](assignment.md) | Submit-ready markdown file (240 lines) covering Tasks 1–4 |

---

## 📂 Repository Structure

```text
.
├── assignment.md         # Full PM take-home submission covering Tasks 1 to 4
├── prototype/
│   ├── index.html        # Self-contained interactive prototype (HTML5/CSS3/Vanilla JS)
│   └── README.md         # Prototype documentation & deployment guides
└── README.md             # Repository landing overview
```

---

## 💻 The Core Prototype Flows

The working prototype (`prototype/index.html`) demonstrates the end-to-end human-in-the-loop accuracy system:

1. **Screen 1: Coach "Needs Your Eyes" Review Queue**
   - Shows 5 ambiguous digit cases from pilot clubs: #14 Maya Lin vs #4 Ava Chen (Ridgeline), #1 Leo Miller vs #11 Sam Brody (Cobblestone), #16 Tyler Adams vs #61 Noah Vance (Brightwater), opposing team color conflict, and muddy digit blur.
   - Interactive options: `Confirm [Player]`, `Reassign (dropdown)`, and `Can't tell, leave out` (conservative withhold default).
   - Strict gating: Steps 2 and 3 remain locked until all 5 clips are reviewed.

2. **Screen 2: Parent Reel Preview & Safety Safeguard**
   - Shows Maya Lin's (#14) personalized reel with verified clips only.
   - Displays an **Accuracy Protection** banner whenever an unconfirmed clip was held back.
   - Interactive `[This isn't my kid]` button immediately purges mistakes with zero friction and re-renders the reel.
   - `[Share Reel]` button demonstrates the 90%+ viral loop for grandparents and scouts.

3. **Screen 3: Weekly Impact & Telemetry**
   - Live telemetry computed from user actions on Screens 1 and 2 (Confirmed count, Withheld count, Parent flags).
   - Before vs. After comparison highlighting risk reduction and transparency.
   - `[Start Over / Reset Demo]` button to test alternative branches.

---

## 🚀 Running Locally

The prototype requires **zero build steps, package installations, or external runtime dependencies**:

```bash
# Clone the repository
git clone https://github.com/sakshii71/AJAIA_ASSIGNMENT.git
cd AJAIA_ASSIGNMENT/prototype

# Option A: Simply double-click index.html in file explorer

# Option B: Run via lightweight local server
python -m http.server 8000
# Open http://localhost:8000 in your browser
```

---

*Note: All roster names, athlete profiles, and game scenarios in this repository are mock data.*
