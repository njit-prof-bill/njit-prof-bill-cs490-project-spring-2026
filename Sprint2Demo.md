# Sprint 2 Demo Script (Spring 2026)

_ATS for Candidates - CS 490 Capstone_

## Demo Intent

Sprint 2 demo has two goals:

1. Verify that each team delivered Sprint 2 application workflow outcomes.
2. Verify that the team can explain technical implementation quality, not only UI behavior.

This is not a feature tour. It is a focused verification demo.

## Class Timing Model

There are several teams and a 2.5-hour demo window. To finish on time, each team has a strict 15-minute presentation slot, with a 5-minute setup/transition allocation outside the team presentation time.

### Per-Team Timebox (15 minutes presentation time)

1. **Phase A - Scripted Product Demo**: 8 minutes
2. **Phase B - Technical Evidence and Q&A**: 7 minutes

### Setup/Transition Allocation (5 minutes each)

This 5-minute allocation is used:

1. Before the first team begins.
2. Between team presentations for projector/device transition.

Suggested sequence per team block:

1. **Transition/Setup**: 5 minutes
2. **Phase A - Scripted Product Demo**: 8 minutes
3. **Phase B - Technical Evidence and Q&A**: 7 minutes

## Time Enforcement Rules

1. Team presentation clock starts when the 15-minute presentation slot begins.
2. Setup/transition is limited to the 5-minute allocation outside presentation time.
3. Missing evidence is scored as missing; extra time is not granted.
4. One presenter should drive. One backup teammate may assist if needed.

---

## Required Preparation (Before Demo Day)

Each team must be ready with:

1. A working runnable or deployed environment.
2. Seed data with at least 8 jobs spanning multiple stages.
3. At least 2 profile entries each for Experience, Education, and Skills.
4. At least 2 AI-generated document drafts saved from job context.
5. CI evidence and unit test evidence ready to show quickly.

Recommended:

1. Keep a one-page "demo run sheet" with exact click order.
2. Keep credentials, URLs, and test IDs ready in a text file.

---

## Phase A - Scripted Product Demo (8 minutes)

Show only required Sprint 2 outcomes using a happy-path walkthrough.

### A1. Dashboard Search/Filter/Sort and Card Status (2 minutes)

Required actions:

1. Open Dashboard/Job Board with seeded jobs.
2. Run a search by title or company.
3. Apply at least one filter and one sort.
4. Show stage/status indicators on cards.

### A2. Card Expansion to Job Detail and Workflow (2 minutes)

Required actions:

1. Open a job card into Job Detail.
2. Show overview data editing.
3. Update stage and show stage transition persistence.
4. Show deadline and recruiter/contact notes fields.

### A3. Interview/Activity/Outcome Workflow (2 minutes)

Required actions:

1. Add an interview event in Job Detail.
2. Add one follow-up/reminder item.
3. Show timeline updates.
4. Record or update outcome state.

### A4. Profile Completion + AI Job-Context Document Flow (2 minutes)

Required actions:

1. Show completed profile sections added in Sprint 2 (Experience, Education, Skills, Preferences).
2. From Job Detail, generate AI resume draft using profile + job context.
3. Generate AI cover letter draft and show at least one rewrite/improve action.
4. Save generated output as a document linked to the job.
5. Show baseline dashboard metrics (stage counts/response tracking).

---

## Phase B - Technical Evidence and Instructor Q&A (7 minutes)

This section is instructor-led. Team answers concise technical questions with evidence.

### B1. Workflow and Data Integrity Evidence (2 minutes)

Required evidence:

1. Show one end-to-end workflow where a state change propagates correctly across related data.
2. Show the backend implementation point that enforces this workflow integrity.

Acceptable demonstration pattern:

1. Change a job stage in Job Detail.
2. Show that timestamp and activity timeline update correctly.
3. Show that dashboard metrics reflect the updated state.
4. Show the corresponding backend service/handler path that performs and persists the update.
5. Show one unit test that validates this workflow behavior (including a negative or edge case).

### B2. CI and Meaningful Testing Evidence (3 minutes)

Required evidence:

1. Show CI checks passing for build + tests.
2. Show one unit test for dashboard workflow logic.
3. Show one unit test for profile completion logic.
4. Show one non-happy-path test (validation/error/unauthorized).
5. Briefly explain why that negative-path test protects real behavior.

Note: Phase A remains happy-path by design. Error handling is demonstrated here through tests and evidence.

### B3. Architecture and Implementation Q&A (2 minutes)

Instructor may ask any of the following:

1. How does Sprint 2 extend your Sprint 1 architecture without breaking prior flows?
2. Where is stage transition logic implemented and why?
3. How does Job Detail coordinate timeline, interview, and document actions?
4. How do profile entities feed AI generation inputs?
5. What technical debt did Sprint 2 introduce, and how will Sprint 3 address it?

Team should answer briefly and show artifacts only when needed.

---

## Sprint 2 Scoring Rubric

Total: 50 points

Project weighting model:

1. Sprint 1: 50 points
2. Sprint 2: 50 points
3. Sprint 3: 100 points

### 1) Preparation and Time Discipline (8 points)

1. Setup readiness and start on time (2)
2. Demo flow preparedness and pacing (3)
3. Completion within slot (3)

### 2) Product Workflow Delivery (24 points)

1. Dashboard search/filter/sort + status indicators (6)
2. Job Detail workflow (overview/stage/deadline/contact) (6)
3. Interview/follow-up/timeline/outcome flow (6)
4. Profile completion + AI doc generation + save/link flow (6)

### 3) Technical Evidence Quality (13 points)

1. Workflow/data-integrity proof for Sprint 2 state transitions (5)
2. CI pipeline evidence (3)
3. Meaningful unit test evidence (5)

### 4) Architecture Understanding (5 points)

1. Clear explanation of implementation decisions and tradeoffs (5)

---

## Failure Modes and Penalties

1. Missing core Sprint 2 workflow evidence: major deduction in Product Workflow Delivery.
2. No workflow/data-integrity proof: major deduction in Technical Evidence.
3. CI unavailable or failing: deduction in Technical Evidence.
4. Only happy-path tests shown: partial credit only for testing criterion.
5. Demo exceeds slot: remaining items scored as not demonstrated.
