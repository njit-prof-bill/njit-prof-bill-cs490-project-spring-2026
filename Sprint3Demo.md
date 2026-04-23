# Sprint 3 Demo Script (Spring 2026)

_ATS for Candidates - CS 490 Capstone_

## Demo Intent

Sprint 3 demo has two goals:

1. Verify that each team delivered Sprint 3 outcomes for document workflows, company research, analytics expansion, and production readiness.
2. Showcase product maturity through polished UI/UX flows, continuity, and confidence.

This is primarily a product experience demo. Technical discussion should be concise and only used as supporting evidence.

## Demo Start Protocol

At the start of each team presentation:

1. The professor opens the team application on the professor device using the team's deployed URL.
2. After the app is confirmed running, the team may continue the presentation from any team device that is ready.
3. If the team does not have a deployed web app, the professor will randomly choose one team member device as the required presentation device for that team.

Teams should be ready to provide the deployed URL immediately when called.

## Class Timing Model

There are several teams and a fixed class demo window. Each team has a strict 15-minute presentation slot, with a 5-minute setup/transition allocation outside team presentation time.

### Per-Team Timebox (15 minutes presentation time)

1. **Phase A - Scripted Product Demo (UI/UX Focus)**: 12 minutes
2. **Phase B - Lightweight Evidence and Q&A**: 3 minutes

### Setup/Transition Allocation (5 minutes each)

This 5-minute allocation is used:

1. Before the first team begins.
2. Between team presentations for projector/device transition.

Suggested sequence per team block:

1. **Transition/Setup**: 5 minutes
2. **Phase A - Scripted Product Demo (UI/UX Focus)**: 12 minutes
3. **Phase B - Lightweight Evidence and Q&A**: 3 minutes

## Time Enforcement Rules

1. Team presentation clock starts when the 15-minute presentation slot begins.
2. Setup/transition is limited to the 5-minute allocation outside presentation time.
3. Missing evidence is scored as missing; extra time is not granted.
4. One presenter should drive the live product; one backup teammate may assist.

---

## Required Preparation (Before Demo Day)

Each team must be ready with:

1. A stable deployed environment (preferred) or stable local runtime with realistic seeded data.
2. One primary demo user with:
   - at least 6 to 8 documents across multiple types/statuses/tags
   - at least 2 jobs linked to documents
   - at least 1 company research note and 1 interview prep note
   - enough timeline/events data to show velocity and stage conversion analytics
3. A second user account to show ownership boundaries when prompted.
4. A short fallback route (bookmark list or run sheet) in case one screen fails.

Recommended:

1. Keep a one-page click path with timestamps for each section.
2. Keep copy/paste snippets ready for quick search terms, tags, and note text.
3. Pre-open key tabs (Dashboard, Job Detail, Document Library) for fast transitions.

---

## Phase A - Scripted Product Demo (12 minutes)

Show required Sprint 3 outcomes as one cohesive candidate journey. Keep emphasis on UI clarity, speed, and interaction quality.

### A1. Product Framing and Navigation Cohesion (1 minute)

Required actions:

1. Start on Dashboard and state the user goal for the flow (apply, prepare, track, and iterate).
2. Navigate quickly through Dashboard -> Job Detail -> Document Library.
3. Highlight consistency of navigation, visual hierarchy, and page-level state feedback.

### A2. Document Library End-to-End Flow (4 minutes)

Required actions:

1. Open global Document Library list and point out document metadata (title, type, status, tags, updated date).
2. Demonstrate filter and sort controls (at least one filter + one sort).
3. Upload one supported file and show validation behavior.
4. Open a document and show version history behavior.
5. Duplicate and rename one document.
6. Archive and restore one document.
7. Download or export a selected version.

Presenter cues:

1. Narrate UX decisions, not backend internals (for example: "We made bulk scanning faster by keeping filters visible and preserving state").
2. Keep motion crisp: each interaction should visibly confirm success or failure.

### A3. Job Context and Document Linking UX (2 minutes)

Required actions:

1. Open one job detail view.
2. Link an existing library document to that job.
3. Unlink and re-link to show control and transparency.
4. Show linked documents section in job detail with relevant versions visible.

Presenter cues:

1. Emphasize that candidates can work from either context (job-first or library-first) without losing orientation.

### A4. Company Research and Interview Prep Workflow (2 minutes)

Required actions:

1. In Job Detail, trigger company research using user-provided prompt/context.
2. Show generated research output and immediately persist it as editable notes on the job.
3. Open interview preparation notes section and show structured editing.

Presenter cues:

1. Focus on how the workflow reduces context switching and keeps preparation artifacts in one place.

### A5. Analytics and "Ready for Production" Experience (2 minutes)

Required actions:

1. Open Dashboard analytics and show velocity + stage conversion views.
2. Explain one insight a candidate can act on immediately.
3. Briefly point out production polish elements visible in UX (error states, loading behavior, responsiveness/accessibility cues).

Presenter cues:

1. Keep this user-impact focused: "what decision the user makes next because of this screen."

---

## Phase B - Lightweight Evidence and Instructor Q&A (3 minutes)

Keep technical detail concise. Show fast evidence, then return to product framing.

### B1. Deployment and Reliability Evidence (2 minutes)

Required evidence:

1. Show one CI/CD run that includes build/test checks, deployment, and health checks.
2. Show one example of centralized error logging/handling output (sanitized).

### B2. Concise Q&A (1 minute)

Instructor may ask:

1. How did you keep UX coherent while adding many Sprint 3 workflows?
2. What was the highest risk area in deployment/hardening and how did you reduce it?
3. What would you improve next if given one additional sprint?

---

## Sprint 3 Scoring Rubric

Total: 100 points

Project weighting model:

1. Sprint 1: 50 points
2. Sprint 2: 50 points
3. Sprint 3: 100 points

### 1) Preparation and Time Discipline (10 points)

1. Setup readiness and start on time (3)
2. Demo flow preparedness and pacing (4)
3. Completion within slot (3)

### 2) UI/UX Product Walkthrough Quality (45 points)

1. Document Library end-to-end flow clarity (15)
2. Job-context linking and visibility flow (10)
3. Company research + interview prep workflow quality (10)
4. Analytics storytelling and user-decision clarity (10)

### 3) Sprint 3 Feature Coverage and Correctness (30 points)

1. Required Sprint 3 workflows demonstrated without major gaps (20)
2. Data persistence and state consistency observable in live flow (10)

### 4) Production Readiness Evidence (15 points)

1. Deployment/CI-CD/health check evidence (6)
2. Reliability and error handling evidence (4)
3. Build/test evidence quality in CI/CD context (5)

---

## Failure Modes and Penalties

1. Missing core Sprint 3 workflow coverage: major deduction in Feature Coverage and Correctness.
2. Demo devolves into architecture deep-dive with weak product flow: deduction in UI/UX Product Walkthrough Quality.
3. No CI/CD deployment/health evidence: major deduction in Production Readiness Evidence.
4. No build/test evidence in CI/CD demonstration: deduction in Production Readiness Evidence.
5. Demo exceeds slot: remaining items scored as not demonstrated.

---
