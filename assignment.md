Video: https://www.loom.com/share/e6430ae21da1450db2d58424b3aca1e6
Prototype: https://moonlit-croissant-663e90.netlify.app
Built for the Ajaia assessment (https://ajaia.ai)

# Task 1. The roadmap call

## 1.1 Signal-by-Signal Evidence Analysis

| Source | Claim / Request | Evidence Quality | Incentive & Underlying Bias | Verdict |
| :--- | :--- | :--- | :--- | :--- |
| **M1: Carla Reyes (Ridgeline)** | Needs live streaming for grandparents and scouts in 6 weeks or will take to board before renewal. Notes highlight reels are "a big part of why half our parents renewed this year". | Anecdotal customer demand from 1 club. No behavioral usage data for live streaming. | Defending board budget; anchored on competitor features; high leverage threat ahead of renewal. | **Defer full live streaming.** Address root need (grandparent and scout access) via shareable links; protect core value. |
| **M2: Parent Survey (Research)** | 58% of 210 parents across 40 clubs ask for "More editing controls (trim reel, add music)" as top ask. | Stated preference survey with self-selection bias. Sample is 210 parents across 40 clubs. | Parents imagine ideal creative control when prompted in an abstract survey context. | **Do NOT build.** Classic say-do gap: revealed preference shows feature is virtually unused. |
| **M2: Product Analytics (90d)** | Share button used in 90% of weekly recaps. Reel Editor opened by 6% of parents; under 1% of those who opened finished an edit (under 0.06% of all parents). | Strong quantitative behavioral telemetry (revealed preference) across all accounts over 90 days. | Objective platform telemetry; zero self-reporting bias. | **Primary foundation.** Parents want frictionless consumption and sharing, not creative editing workflows. |
| **M3: Support Ticket Log** | 3 mis-tag complaints (14 vs 4, swapped digits 16 vs 61, 1 vs 11) across 3 clubs and 3 sports; 1 icon request; 1 logo watermark issue. | Low volume (3 tickets), but cross-account, cross-sport pattern that suggests digit confusion (assuming OCR/CV digit detection is the method used for roster tagging). | High friction required to file ticket; indicates severe user emotional disappointment ("daughter so disappointed"). | **Top Priority.** Validates algorithmic blindspot that directly threatens core value proposition and child privacy. |
| **M4: Jamal Whitfield (VP Sales)** | Carla threatened to shop around; Ridgeline is \$180k/season (highest-risk renewal); demands roadmap commitment. | Commercial escalation citing M1. Validates account financial value, but provides no product feasibility. | Sales quota preservation and commission risk. Prone to feature-promising under churn threats. | **Manage commercially.** Deliver concrete non-streaming solution for Carla's scouts and grandparents without derailing engineering. |
| **M5: Product Health Dashboard** | 92% share rate on opened reels, but approx 30% generated reels never opened (late notifications + wrong kid thumbnails). | Strong telemetry, but headline metric requires careful mathematical qualification. | Internal health tracking; identifies critical conversion drop-off points before reel consumption. | **Core roadmap input.** Fix notification timing and eliminate wrong-kid thumbnails to drive opened volume. |

## 1.2 Metric Correction & Clarification
* **The Misleading 92% Metric:** Dashboard M5 reports a 92% Reel Share Rate, but specifies this is *calculated only over reels a parent opened*. Because approx 30% of reels are never opened, the honest upper bound on generated reel sharing is approx 0.92 x (1 - 0.30) = 64.4% (Target: increase opened rate to lift absolute shares).
* **Distinct Metrics:** Do not conflate the 90% recap share rate (M2: weekly team summary) with the 92% open-to-share reel rate (M5: individual player highlight). Both demonstrate that *sharing* is SidelineReelâ€™s viral growth loop, provided the content is seen and accurate.

## 1.3 Ranked Roadmap

| Rank | Candidate Feature | Cited Evidence & Strategic Justification |
| :--- | :--- | :--- |
| **#1** | **Roster-Tagging Accuracy Engine & Coach Verification** | **M3, M5, M1.** Fixes digit confusion (14/4, 1/11, 16/61) that drives "wrong kid" thumbnails (causing approx 30% unopened reels) and brand-damaging errors. Child safety and trust must precede expansion. |
| **#2** | **Intelligent Local Quiet-Hours Notification Dispatch** | **M5.** Directly addresses the other primary cause of unopened reels (late-night delivery). Ships alongside #1 as a low-lift backend scheduling rule (no spec required here). |
| **#3** | **Grandparent & Scout Public Sharing Portal (Ridgeline Plan)** | **M1, M4, M2.** Solves Carla's stated problem (scouts/grandparents remote viewing) by leveraging the proven 90% sharing loop instead of high-risk, unvalidated live video infrastructure. |
| **#4** | **Backlog: Watermark Fix & Multi-Sport App Icons** | **M3.** 1 coach ticket noted watermark missing on camera roll save ("not urgent"); 1 anonymous ticket asked for non-soccer icon. Low impact; log in technical backlog. |

## 1.4 What We Are NOT Building Now (and Why)
1. **Full Live Streaming Infrastructure (Ridgeline Request):**
   * *High-Risk Execution:* Requires real-time ingest, field uplink hardware, transcoding, and low-latency CDN. Field cellular bandwidth at youth sports venues can be unreliable, risking failed streams [Assumption, engineering to validate].
   * *Single-Account Pressure:* This is one loud customer (\$180k) amplified three times (Carla -> Jamal -> Sales Ops). We do not know total ARR, so concentration risk cannot justify an architectural pivot.
   * *Protects the Wrong Asset:* Carla notes highlight reels are a big part of why half her parents renewed. If we build live streaming but deliver reels with the wrong kids (M3 Ticket #1 was a Ridgeline parent!), Ridgeline will face churn risk regardless.
2. **Reel Editor Upgrades (Trimming, Music):**
   * *Classic Say-Do Gap:* While 58% of survey respondents asked for it (M2), behavioral telemetry shows only 6% of parents ever opened the editor, and under 1% of those who opened it finished an edit (under 0.06% of all parents). Parents want automated delivery, not video editing tasks. Building this wastes capital on stated preference illusions.

## 1.5 Concrete Ridgeline Retention Plan (Without Live Streaming)
* **Immediate Executive Engagement:** Schedule a 30-minute discovery session with Carla Reyes and her board athletic director this week. Acknowledge her need to serve distant grandparents and college recruiting scouts.
* **Proactive Transparency on Ticket #1:** Inform Carla that a Ridgeline parent experienced a mis-tagged reel (#14 vs #4), and that our upcoming release specifically eliminates wrong-kid reels and guarantees thumbnail accuracy before Ridgelineâ€™s signups open in 6 weeks.
* **The "Scout & Family Pass" Interim Solution:** Scope a lightweight, frictionless web link that allows parents and coaches to publish high-definition game recaps and player reels to a verified, web-accessible view for college scouts and grandparents. This leverages our 90% share behavior at a fraction of the cost and complexity of live streaming [Assumption on relative cost, engineering to validate].
* **Two-Week Answer & Pre-Signup Checkpoint:** Give Carla a concrete feasibility answer within 2 weeks following initial engineering sizing. Hold the formal live streaming decision checkpoint within 4 weeks (comfortably before Ridgeline's signups open in 6 weeks). We will consider live streaming only if: (1) Multiple clubs confirm willingness to pay a dedicated streaming surcharge; (2) Engineering validates field cellular feasibility; (3) Third-party camera/hardware integrations are established.

## 1.6 Anticipated Pushback & Rebuttals
* **Pushback A: Carla / Ridgeline Board â€” "Just commit to live streaming now or we shop around."**
  * *Rebuttal:* Live streaming on youth sports fields faces significant cellular uplink and hardware constraints [Assumption, engineering to validate], risking buffering or failed streams. What renewed half your parents was the delight of personalized highlight reels. We can provide scouts and grandparents high-definition remote access via verified web share links (solving remote viewing, though not real-time broadcast), with a firm delivery date committed once engineering completes technical sizing this week, while guaranteeing no child receives the wrong clips.
  * *What changes my mind:* 3+ peer clubs providing signed letters of intent with a dedicated streaming surcharge, alongside a third-party camera hardware partnership.
* **Pushback B: Jamal Whitfield (VP Sales) â€” "You're gambling our biggest \$180k renewal."**
  * *Rebuttal:* Committing to full live streaming before technical sizing risks failed streams on game day and severe renewal churn [Assumption, engineering to validate]. Prioritizing tagging accuracy protects the core highlight product Carla credits for renewals. Scoping the Scout & Family Pass addresses remote family and scout access (though not real-time live streaming), with delivery dates committed only after engineering sizing, giving sales a credible, concrete plan instead of an unvalidated promise.
  * *What changes my mind:* If Carla rejects the discovery call and presents a verified competitive quote from a platform with proven field streaming.
* **Pushback C: User Research Lead â€” "58% of surveyed parents explicitly asked for editor tools."**
  * *Rebuttal:* Surveys capture aspirational desires; telemetry captures true behavior. Only 6% of parents open the editor, and under 1% of that 6% (under 0.06% of all parents) finish an edit. Optimizing an authoring tool with a finished-edit rate under 0.06% while 30% of reels go unviewed due to wrong thumbnails is an inefficient allocation of sprint capacity.
  * *What changes my mind:* If an in-app prompt asking parents "Trim this clip before sharing?" achieves over 25% completion in a live A/B test.
* **Pushback D: Executive Stakeholder â€” "Why not compromise and build both the editor and the accuracy fix?"**
  * *Rebuttal:* Parallel development fragments engineering focus. Tagging accuracy requires machine learning threshold tuning, coach UI workflows, and automated fallback logic. Splitting focus produces an inaccurate reel generator with a clunky video editor that parents still won't use.
  * *What changes my mind:* Additional dedicated engineering headcount specifically contracted for frontend media composition.

---

# Task 2. The spec

## 2.1 Problem & Target Users
* **Problem Statement:** Computer vision digit mis-identification (e.g., single-digit substring confusion 14 vs 4, 1 vs 11; swapped digits 16 vs 61; opposing team duplicate numbers) introduces incorrect player clips into personalized reels. This causes wrong-kid video thumbnails, contributing to approx 30% unopened reels (M5), severe family disappointment (M3), child privacy risks, and churn risk for high-value accounts (M1, M4). Note: All athlete and roster names referenced are mock data.
* **Target Users:**
  1. *Coaches (Primary Verifier):* Time-constrained volunteers/staff needing an under 60-second workflow to clear ambiguous tags.
  2. *Parents (End Consumer & Secondary Safety Net):* Expect accurate, immediate reels of their child; need a 1-tap mechanism to remove incorrect footage.
  3. *Ajaia Support/Ops:* Internal team auditing mis-tag patterns and recalibrating CV models.

## 2.2 Outcome & Success Metrics
* **Core Outcome:** Zero wrong-kid clips delivered in published reels, restoring parent trust and driving opened reel volume.
* **Metrics:**
  * *Mis-tag Support Tickets:* Baseline: [Baseline unknown, instrument first; currently 3 tickets/week]; Target: under 0.1 tickets per 1,000 reels.
  * *Clips Flagged by Parents ("This isn't my kid"):* Baseline: [Baseline unknown, instrument first; feature is new]; Target: under 0.5% of delivered clips.
  * *Coach Review Completion Rate:* Baseline: [New feature]; Target: over 80% of flagged queues resolved within 18 hours.
  * *Median Coach Queue Handling Time:* Target: under 45 seconds total per game.
  * *Reel Open Rate:* Baseline: approx 70% (M5 indicates approx 30% unopened); Target: at least 85% within 60 days of rollout.

## 2.3 Scope
* **IN SCOPE:**
  * Algorithmic Ambiguity Detection Rules (sub-strings, transpositions, identical numbers across opposing teams).
  * Confidence scoring engine with configurable withholding threshold [Default assumption: 85%].
  * Coach "Needs Your Eyes" quick-review web/mobile responsive interface.
  * Conservative "Withhold by Default" automated fallback with 24-hour delivery deadline.
  * Parent in-player "This isn't my kid" removal flow with instant clip retraction.
  * Basic team roster metadata management (jersey number, secondary color disambiguation).
* **OUT OF SCOPE:**
  * Video editing tools (trimming, music, canvas effects).
  * Real-time live streaming ingest or player infrastructure.
  * Automated facial recognition or biometric tracking (strict child privacy compliance).
  * Coach-side video re-cutting or manual bounding-box manipulation.

## 2.4 Functional Requirements

### A. Ambiguity Detection & Similarity Logic
The vision ingestion pipeline must flag a clip as ambiguous if detected jersey digits match any of the following rules against the team roster:
1. *Single-Digit Substring Overlap:* A detected two-digit number contains a rostered single digit, or vice versa (e.g., detected #14 matches player #14 Maya Lin and player #4 Ava Chen; detected #11 matches #1 Leo Miller and #11 Sam Brody).
2. *Transposed / Swapped Digits:* Detected digits represent a numerical inversion of another rostered player (e.g., #16 Tyler Adams vs #61 Noah Vance; #23 vs #32).
3. *Cross-Team Duplicate Numbers:* Opposing team roster has the same jersey number, and visual color separation between team kits has a confidence score under 90%.
4. *Visual Occlusion / Low Confidence:* OCR bounding-box digit confidence score under 85% [Assumption: 85%].

### B. Confidence Scoring & Review Queue States
* Every clip tag receives a normalized confidence score: C in range 0.0 to 1.0.
* **Routing Logic:**
  * C >= 0.85 AND no similarity conflict: **AUTO-CONFIRMED** -> Added to kid's reel.
  * C < 0.85 OR similarity conflict detected: **FLAGGED FOR REVIEW** -> Routed to Coach Review Queue.
* **Clip States:**
  * `PENDING_REVIEW`: Awaiting coach decision.
  * `CONFIRMED`: Coach verified identity -> Published to reel.
  * `REASSIGNED`: Coach reassigned to correct player -> Routed to correct player's reel.
  * `WITHHELD`: Coach selected "Can't tell, leave out" OR deadline expired -> Excluded from all reels.

### C. Coach "Needs Your Eyes" Review Queue
* Grouped by game, accessible via expiring, single-use SMS/push magic links (no password barrier for volunteers, secure and time-limited).
* Card interface displaying:
  * CSS-rendered detected jersey badge and timestamp.
  * 3-second looping clip preview (muted, lightweight MP4/WebM).
  * Plain-English explanation banner (e.g., *"Flagged: #14 Maya Lin and #4 Ava Chen both on roster"*).
  * AI Confidence score.
  * 3 explicit actions:
    1. `Confirm [Player Name]` (Primary action, 1-tap).
    2. `Reassign` (Dropdown pre-populated with matched ambiguous candidate players first, then full roster).
    3. `Can't tell, leave out` (Marks clip as `WITHHELD`).
* Header displays progress: *"X of Y clips reviewed"*.

### D. Conservative Withhold-vs-Send Logic & Auto-Send Deadline
* **Core Safety Rule:** Under no circumstances may an unconfirmed ambiguous clip be published to a parent's reel. Better to deliver a reel with 4 verified highlights than 5 highlights where 1 shows another child.
* **Auto-Send Deadline:** Coaches receive a 24-hour window [Assumption: 24 hours] post-game to complete reviews. If unreviewed when the deadline expires:
  * All remaining `PENDING_REVIEW` clips are automatically transitioned to `WITHHELD`.
  * The reel publishes immediately with confirmed clips only.
  * The parent sees an in-app badge: *"1 clip withheld for accuracy review."*
  * Reels are **never** blocked from delivery indefinitely.

### E. Parent Flagging & Instant Retraction Flow
* In the reel playback viewer, every individual clip includes a visible button: `[This isn't my kid]`.
* When clicked:
  * Clip immediately vanishes from the player's active reel in real-time.
  * Confirmation toast: *"Thanks. We've removed this clip from [Child's Name]'s reel and flagged it for review."*
  * Reel thumbnail automatically regenerates to the highest-confidence remaining clip.
  * Event `clip_parent_flagged` dispatched to backend; clip logged in Ops audit queue.

### F. Roster Edge Cases
* *Duplicate Jersey Numbers:* System displays a setup warning to coaches before season start: *"Two players share #7. Clips will require manual review unless positions/colors differ."*
* *Missing Jersey Number:* Player marked as `UNASSIGNED`; clips are held in coach queue with a prompt to assign jersey number.
* *Obscured / Muddy Number:* Handled identically to low-confidence (C < 0.85); routed to queue or withheld.
* *Mid-Season Roster Updates:* Adding a player re-indexes past game footage retroactively only if requested; future games immediately inherit updated ambiguity checks.

## 2.5 Human-in-the-Loop Architecture
```
                  [ Raw Game Footage Ingestion ]
                                |
                   [ CV Detection & OCR Engine ]
                                |
               Does clip trigger Ambiguity / Low C?
                             /       \
                       YES  /         \  NO (C >= 0.85)
                           v           v
           [ Coach "Needs Your Eyes" Queue ]   [ Auto-Confirmed ]
                   |               |                   |
            Coach Confirms   Coach Ignores /           |
            or Reassigns     24h Deadline              |
                   |               |                   |
                   v               v                   v
            [ Published ]    [ Withheld ]        [ Published ]
                   \               /                   /
                    -----> [ Parent Reel ] <-----------
                                   |
                         Parent Flags Clip?
                            ("Not my kid")
                             /          \
                       YES  /            \  NO
                           v              v
               [ Instant Retraction ]   [ Reel Enjoyed / Shared ]
                           |
             [ Ops Auditing & CV Retraining ]
```
1. **Coach as Frontline Verifier:** Human context resolves digit ambiguities that vision models cannot reliably distinguish.
2. **Parent as Secondary Safeguard:** Parents have instant veto power to retract clips without waiting for support.
3. **Internal Ops Oversight:** Flagged clips feed internal labeling dashboards; no clip is algorithmically re-added once flagged by a parent without human Ops review.

## 2.6 Acceptance Criteria (Given / When / Then)

* **AC 1 (Substring Ambiguity 14 vs 4):**
  * *Given* player #14 Maya Lin and player #4 Ava Chen are both on the Ridgeline roster,
  * *When* footage detects a jersey reading #14 with OCR confidence of 82%,
  * *Then* the clip must be flagged with reason *"14 and 4 are easily confused"*, routed to the coach queue, and excluded from Maya's and Ava's reels until confirmed.
* **AC 2 (Repetition Confusion 1 vs 11):**
  * *Given* player #1 Leo Miller and player #11 Sam Brody are on the Cobblestone roster,
  * *When* a highlight clip detects digit #1,
  * *Then* the system must trigger a similarity conflict rule and require coach confirmation before publishing.
* **AC 3 (Transposed Digits 16 vs 61):**
  * *Given* player #16 Tyler Adams and player #61 Noah Vance are on the Brightwater roster,
  * *When* a highlight clip detects number 61 with visual blur,
  * *Then* the clip must list Tyler and Noah as primary disambiguation candidates in the coach review queue.
* **AC 4 (Withheld Clips Never Appear):**
  * *Given* a clip flagged for coach review is marked *"Can't tell, leave out"* or remains unreviewed at the 24h deadline,
  * *When* the parent opens the child's highlight reel,
  * *Then* the withheld clip must NOT be rendered in the video player or used as the reel thumbnail.
* **AC 5 (Timely Delivery with Remaining Clips):**
  * *Given* a game has 4 confirmed clips and 1 pending clip at the 24-hour auto-send deadline,
  * *When* the deadline passes,
  * *Then* the recap notification must send automatically with the 4 confirmed clips, displaying an informative label indicating 1 clip is withheld.
* **AC 6 (Parent Instant Removal):**
  * *Given* a parent is watching their child's published reel,
  * *When* the parent clicks *"This isn't my kid"*,
  * *Then* the clip must disappear from the player within under 500 ms, display a confirmation toast, trigger a `clip_parent_flagged` event, and re-render the thumbnail if necessary.
* **AC 7 (Coach Reassignment Routing):**
  * *Given* a clip initially attributed to #14 Maya Lin is reassigned by the coach to #4 Ava Chen,
  * *When* reels are generated,
  * *Then* the clip must appear in Ava's reel and be completely absent from Maya's reel.

## 2.7 Key Analytics Events
* `clip_ambiguity_flagged`: `{clip_id, game_id, detected_number, matched_rules: [], confidence_score}`
* `coach_queue_opened`: `{coach_id, game_id, queue_size, timestamp}`
* `coach_clip_resolved`: `{clip_id, coach_id, action: ['confirm'|'reassign'|'withhold'], duration_ms, reassigned_to_player_id}`
* `coach_queue_completed`: `{coach_id, game_id, total_clips, total_time_ms, auto_expired: boolean}`
* `reel_published_withheld_count`: `{reel_id, player_id, confirmed_count, withheld_count}`
* `clip_parent_flagged`: `{clip_id, player_id, parent_id, timestamp, current_playback_time}`

## 2.8 Privacy, Child Safety & Compliance
* **Child Safety & Minor Protection:** Footage of youth athletes must never be broadcast or cross-pollinated into unverified parent accounts. Mis-tagging constitutes a child privacy risk (legal review needed).
* **No Biometrics:** The system relies strictly on jersey typography, roster metadata, and coach human verification. No facial embeddings or biometric profiles of minors are stored.
* **Parental Revocation:** A parent's retraction immediately purges the clip association from public caches.

## 2.9 Top Three Failure Modes & Mitigation Controls

### Failure Mode 1: Coach Queue Overload & Rubber-Stamping
* **How it Fails:** If a game generates 20+ ambiguous clips, volunteer coaches become overwhelmed, face decision fatigue, and rapidly click "Confirm" on every card without watching the video, defeating the verification layer.
* **Catch & Mitigation:**
  1. *Metric / Alert:* Monitor `coach_median_resolution_time`. Trigger automated alert if over 30% of clips are confirmed in under 1.5 seconds per clip ("rubber-stamp pattern").
  2. *Queue Throttling:* Hard cap of maximum 6 clips [Assumption: maximum 6 clips] sent to coach queue per game. Lower-confidence excess clips are automatically withheld.
  3. *Audit Sampling:* Internal Ops samples 5% of coach-approved clips weekly for manual accuracy validation.

### Failure Mode 2: High-Confidence False Positives (Clean but Wrong)
* **How it Fails:** The CV model detects a crisp, unobstructed number "4" with 98% confidence on an opposing team's player or when jersey wrinkles mask a "14", bypassing the coach review queue entirely and publishing straight to the wrong kid's reel.
* **Catch & Mitigation:**
  1. *Metric / Alert:* Monitor `parent_flag_rate` by club and team. Any team exceeding target over 1.5% [Target: over 1.5%] triggers an immediate model audit.
  2. *Cross-Check Safeguards:* Enforce mandatory team jersey color contrast validation and field position feasibility checks prior to auto-confirmation.
  3. *Weekly Labeled Ground-Truth Audits:* Sample 200 auto-confirmed clips weekly to evaluate algorithmic precision and dynamically adjust confidence thresholds.

### Failure Mode 3: Coach Non-Response (Thin Reels & Stagnant Open Rates)
* **How it Fails:** Busy volunteer coaches ignore review notifications altogether before the 24-hour auto-send deadline. Consequently, conservative fallback withholds all ambiguous clips, producing sparse or 1-clip reels that fail to delight families, causing reel open rates to remain depressed.
* **Catch & Mitigation:**
  1. *Metric / Alert:* Monitor withheld-clip % per reel and coach queue completion rate per team. Trigger alerts if withheld clips exceed 30% of total team highlights across consecutive weeks.
  2. *Automated Reminders:* Dispatch SMS nudge at 18 hours (6 hours before deadline).
  3. *Escalation / Assistant Coach Routing:* If the head coach does not open the queue within 12 hours, automatically route an access link to the designated team manager or assistant coach.

## 2.10 Rollout Plan & Open Questions
* **Phase 1 (Weeks 1-2):** Design-partner pilot with Ridgeline Youth Soccer, Brightwater Lacrosse, and Cobblestone Little League (the 3 ticket submitters). Validate coach queue completion and calibrate threshold.
* **Phase 2 (Weeks 3-4):** General release to all clubs ahead of Ridgeline's 6-week renewal deadline.
* **Open Questions:**
  1. *Baseline Mis-tag Rate:* What is the exact percentage of generated clips currently mis-tagged across historical games? (Must instrument in Phase 1; baseline unknown).
  2. *Unopened Reel Attribution:* What exact proportion of the approx 30% unopened reels stems from late-night notifications vs wrong-kid thumbnails?

---

# Task 3. Working prototype

## 3.1 Overview & Architecture
The prototype is a self-contained, interactive single-page application built in standard HTML5, CSS3, and vanilla JavaScript (`prototype/index.html`). It requires no build tools, runtime compilers, or external dependencies, and is immediately deployable to Netlify Drop or GitHub Pages. All athlete and roster names are mock data.

## 3.2 Core Flows & Click-Through Steps
Follow these 4 steps to test the prototype:
1. **Step 1 (Coach Queue):** Review the 5 ambiguous cards across pilot clubs. Click "Confirm Maya Lin (#14)" on Card 1, "Reassign" on Card 3 (#16 Tyler Adams), and "Can't tell, leave out" on Card 5. Notice the progress bar tracks to 5/5, unlocking the Finish button.
2. **Step 2 (Unlock & Transition):** Click "Finish & Preview Parent Reel". (Note that Steps 2 and 3 remain locked until all 5 queue cards are resolved).
3. **Step 3 (Parent Reel & Safety Veto):** On Screen 2, note the prominent "Accuracy Protection" banner indicating held-back clips. Click "This isn't my kid" on any clip to verify instant removal, toast confirmation, and thumbnail re-indexing. Click "Share Reel" to test the scout/family web loop.
4. **Step 4 (Recap & Impact Telemetry):** Click "View Weekly Recap Telemetry" to advance to Screen 3. Verify that all metrics (Coach Confirmed, Withheld, Parent 'not my kid' flags) are dynamically calculated from your exact actions in Steps 1 and 2, with zero contradictory captions. Click "Start Over / Reset Demo" to test other resolution branches.

## 3.3 Deliberate Mock Assumptions (What It Fakes)
* *Placeholder Footage Animation:* Video playback utilizes a lightweight 2D canvas simulation (animated field markers, bounding boxes, and jersey digits) because no real youth athlete video footage exists in the assessment materials, and to respect minor privacy.
* *SMS/Push Delivery Simulation:* Delivery notifications and coach magic links are simulated via accessible in-app toast alerts.
* *State Persistence:* Application state persists across screen steps in memory rather than a remote database.
* *Risk Model Visualization:* The Before vs. After comparison illustrates unverified OCR risk vs post-verification accuracy protection (historical baseline unknown, instrument first; not real telemetry).

---

# Task 4. AI Workflow Note

[I WILL WRITE THIS MYSELF: which tasks I used AI for / what I kept human / one thing AI got wrong or I rejected]
