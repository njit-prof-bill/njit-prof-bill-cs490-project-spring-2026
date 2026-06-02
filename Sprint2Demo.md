# Sprint 2 Demo Script and Grading Checklist (Spring 2026)

_ATS for Candidates - CS 490 Capstone_

## 1. Purpose

This is a single source of truth for Sprint 2 demo execution and grading.

It combines:

1. The live demo script teams must follow.
2. The objective grading checklist used during the demo.
3. The penalty model.
4. The separate subjective Q&A scoring section.

## 2. Timing and Structure

Per team:

1. **15 minutes**: setup and live demo run.
2. **5 minutes**: instructor Q&A.

Total: **20 minutes**.

## 3. Scoring Model

### 3.1 Objective Checklist Score

1. There are **25 checklist items**.
2. Each item is binary: `1` (demonstrated) or `0` (not demonstrated).
3. Objective subtotal = sum of 25 checklist items.

### 3.2 Demo Bug/Fault Penalty (No Cap)

1. Teams lose **1 point for each confirmed bug/failure** exposed during the demo.
2. No cap is applied.

Confirmed bug/failure means any of the following:

1. Crash, unhandled runtime error, or broken flow during a required checklist step.
2. Behavior that clearly contradicts the listed Sprint 2 requirement being demonstrated.
3. Required evidence unavailable when requested (for example, required test evidence page cannot be shown).

### 3.3 Subjective Q&A Score

1. Q&A is the only subjective component.
2. Suggested Q&A score range: 0 to 5.

### 3.4 Recommended Total

1. Recommended total score = `Objective Checklist (0-25) - Bug Penalties + Q&A (0-5)`.

## 4. Required Preparation (Before Demo Day)

Teams must be ready with:

1. Runnable app environment.
2. Seed jobs spanning multiple stages.
3. Seed profile content including completed Sprint 1 baseline and additional Sprint 2 sections.
4. At least one non-engineering profile in the seed data set.
5. At least two AI-generated drafts saved from job context.
6. GitHub Actions page ready for CI and test evidence.
7. At least three negative unit tests ready to show and explain.
8. Test data for at least one invalid stage transition case.

Recommended:

1. Keep a one-page demo run sheet with the exact click path.
2. Keep credentials, URLs, and test IDs ready in a text file.
3. Keep the latest CI workflow link open in a browser tab.

## 5. Live Demo Script (Tied to Checklist)

Run in this order to match grading flow:

1. Readiness and seed data checks: `C01-C04`.
2. Dashboard workflow and navigation checks: `C05-C10`.
3. Job detail, stage, and timeline checks: `C11-C15`.
4. Profile completion checks: `C16-C19`.
5. AI draft and job-context document checks: `C20-C22`.
6. GitHub Actions CI and test evidence: `C23-C25`.
7. Instructor Q&A (subjective section).

## 6. Sprint 2 Objective Checklist (25 Items)

Use this checklist live during demo. Each row is `1` or `0`.

| ID | Checklist Item (Yes/No) | Evidence To Observe | Sprint 2 Story Coverage | Score |
|---|---|---|---|---|
| C01 | Team is ready to begin on time when called | Demo starts without delay beyond allocated transition/setup | S2-001 to S2-026 |  |
| C02 | Demo environment is operational at start | App loads and is usable before scripted steps begin | S2-001 to S2-026 |  |
| C03 | Seed data includes multiple jobs spanning stages | At least a few jobs exist across different stages | S2-001 to S2-010 |  |
| C04 | Seed data includes completed Sprint 1 profile baseline | Identity/contact + summary are already populated | S2-016 to S2-020 |  |
| C05 | Search works across jobs | Search by title/company/keywords returns expected results | S2-001 |  |
| C06 | Filter and sort work on the dashboard | Filter and sort each change visible results | S2-002, S2-003 |  |
| C07 | Stage/status indicators are visible on job cards | Job cards clearly show current stage cues | S2-004 |  |
| C08 | Job card opens into a consistent job detail view | Card expansion takes user to the same detailed workflow pattern | S2-005 |  |
| C09 | Job detail overview is editable | Core job fields can be edited in detail view | S2-006, S2-007 |  |
| C10 | Dashboard/job workflow updates persist after refresh | Updated job remains after reload/navigation | S2-006 to S2-009 |  |
| C11 | Stage transition works for valid forward move | Team demonstrates a legal stage change | S2-008, S2-009 |  |
| C12 | Invalid stage transition is blocked with clear feedback (negative) | Team shows a blocked transition and warning/confirmation behavior | S2-004 to S2-009 |  |
| C13 | Timeline reflects stage changes and activity entries | Timeline updates after stage/activity changes | S2-009, S2-010, S2-012, S2-013 |  |
| C14 | Interview entries can be added with round/date/notes | Interview data is stored and visible | S2-010, S2-011 |  |
| C15 | Follow-up/reminder tracking works | Follow-up item is created and visible for the job | S2-012 |  |
| C16 | Outcome tracking works | User can record or update outcome state | S2-013 |  |
| C17 | Profile sections beyond Sprint 1 are present | Experience, Education, Skills, and Preferences are visible | S2-014, S2-016 to S2-020 |  |
| C18 | Profile validation failure shows clear field-level feedback (negative) | Example invalid entry is rejected with useful error text | S2-015 to S2-017 |  |
| C19 | Duplicate skill prevention works (negative) | Duplicate skill entry is blocked | S2-016 to S2-020 |  |
| C20 | AI resume draft can be generated from profile + job context | Draft is produced from the current job detail | S2-018, S2-019, S2-021 |  |
| C21 | AI cover letter draft can be generated and rewritten | Draft is created and at least one improve action is shown | S2-018, S2-019, S2-022, S2-023 |  |
| C22 | Generated output can be saved back into job context | AI draft is saved and linked to the job | S2-019, S2-020, S2-024 |  |
| C23 | Team opens GitHub Actions and shows latest relevant workflow run | Actions page is shown live with recent run context | S2-026 |  |
| C24 | GitHub Actions evidence shows build + unit test execution | Workflow details clearly include build/test jobs | S2-026 |  |
| C25 | Team is prepared to show at least three negative unit tests and explain each | Three negative tests are shown and briefly explained | S2-008, S2-015, S2-017, S2-026 |  |

## 7. Subjective Q&A (Only Subjective Portion)

Suggested Q&A prompts:

1. Why does your workflow logic belong in Job Detail rather than separate screens?
2. What is the hardest validation rule you added in Sprint 2 and why?
3. How did you keep AI output editable and still useful?
4. What tradeoff did the team make in Sprint 2 and why?

Suggested subjective scoring guide (0 to 5):

1. `0-1`: unclear explanations; weak technical understanding.
2. `2-3`: acceptable understanding with partial depth.
3. `4-5`: clear, accurate, evidence-backed technical reasoning.

## 8. Fast Grading Summary

1. Objective checklist subtotal: ____ / 25
2. Bug/failure penalties (no cap): -____
3. Subjective Q&A score: +____ / 5
4. Final score: ____
