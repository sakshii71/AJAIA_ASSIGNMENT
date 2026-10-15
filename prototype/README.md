# SidelineReel Prototype — Roster-Tagging Accuracy Engine

This interactive prototype demonstrates the frontline coach review queue, parent reel preview with instant clip retraction, and weekly recap telemetry for Ajaia's **SidelineReel** platform.

Built for the Ajaia Product Manager assessment: [https://ajaia.ai](https://ajaia.ai)

---

## Prototype Features & Core Flow

1. **Screen 1: Coach "Needs Your Eyes" Review Queue**
   - Presents ambiguous digit test cases: #14 vs #4 (Ridgeline), 1 vs 11 (Cobblestone), 16 vs 61 transposed digits (Brightwater), opposing team duplicate #7, and low-confidence visual occlusion.
   - Interactive options: `Confirm [Player]`, `Reassign (dropdown)`, `Can't tell, leave out` (conservative withhold).
   - Dynamic progress tracker (`X of 5 Reviewed`) unlocks the flow once all ambiguous clips are reviewed.

2. **Screen 2: Parent Reel Preview & Safety Safeguard**
   - Renders Maya Lin's (#14) personalized highlight reel with confirmed clips only (all roster names are mock data).
   - Displays a prominent notice explaining that ambiguous clips were withheld for accuracy.
   - Includes the 1-tap `[This isn't my kid]` button to immediately retract and flag incorrect footage.
   - Functional `[Share Reel]` button demonstrating the frictionless web loop for grandparents and scouts.

3. **Screen 3: Weekly Recap & Impact Telemetry**
   - Live recap metrics showing total processed clips, confirmed clips, withheld clips, and parent 'not my kid' flags.
   - Clear Before vs. After comparison highlighting risk reduction.
   - `[Start Over / Reset Demo]` button to test various resolution combinations.

---

## Deployment Instructions

The prototype is a self-contained, single-file HTML application with zero build steps or external dependencies.

### Option A: Netlify Drop (Fastest — 60 Seconds, Free)
1. Go to [https://app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag and drop the `prototype/` folder directly onto the browser window.
3. Netlify will instantly provide a live HTTPS URL (e.g., `https://sidelinereel-accuracy.netlify.app`).
4. Copy and paste this URL into your submission.

### Option B: GitHub Pages (Free)
1. Push this repository to GitHub.
2. In your repository, navigate to **Settings** $\rightarrow$ **Pages**.
3. Under **Branch**, select `main` and set the folder to `/prototype` (or root if moved).
4. Click **Save**. Within 1–2 minutes, your live site will be accessible at `https://<username>.github.io/<repo-name>/prototype/`.

### Option C: Local Testing
Open `prototype/index.html` directly in any modern web browser (Chrome, Safari, Edge, Firefox), or run a lightweight local server:
```bash
# Using Python 3
cd prototype
python -m http.server 8000
# Open http://localhost:8000 in your browser
```
