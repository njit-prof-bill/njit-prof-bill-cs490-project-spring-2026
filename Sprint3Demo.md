# Sprint 3 Demo Script and Grading Checklist (Spring 2026)

_ATS for Candidates - CS 490 Capstone_

## 1. Purpose

This is a single source of truth for Sprint 3 demo execution and grading.

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
2. Behavior that clearly contradicts the listed Sprint 3 requirement being demonstrated.
3. Required evidence unavailable when requested (for example, required CI/CD artifact cannot be shown).

### 3.3 Subjective Q&A Score

1. Q&A is the only subjective component.
2. Suggested Q&A score range: 0 to 5.

### 3.4 Recommended Total

1. Recommended total score = `Objective Checklist (0-25) - Bug Penalties + Q&A (0-5)`.

## 4. Required Preparation (Before Demo Day)

Teams must be ready with:

1. Stable deployed environment or reliable local runtime.
2. One primary demo user with seeded documents across multiple types/statuses/tags.
3. At least two jobs linked to documents.
4. One company research note and one interview prep note.
5. Timeline/events data sufficient to show analytics.
6. A second user account for ownership checks.
7. GitHub Actions page ready for deployment and test evidence.
8. At least three negative unit tests ready to show and explain.

Recommended:

1. Keep a one-page click path with timestamps for each section.
2. Keep copy/paste snippets ready for search terms, tags, and note text.
3. Pre-open key tabs (Dashboard, Job Detail, Document Library, Actions) for fast transitions.

## 5. Live Demo Script (Tied to Checklist)

Run in this order to match grading flow:

1. Readiness and deployment data checks: `C01-C04`.
2. Document workflow checks: `C05-C10`.
3. Job-context linking and AI note workflows: `C11-C16`.
4. Analytics and production-readiness checks: `C17-C20`.
5. GitHub Actions CI, deployment, and test evidence: `C21-C25`.
6. Instructor Q&A (subjective section).

## 6. Sprint 3 Objective Checklist (25 Items)

Use this checklist live during demo. Each row is `1` or `0`.

| ID | Checklist Item (Yes/No) | Evidence To Observe | Sprint 3 Story Coverage | Score |
|---|---|---|---|---|
| C01 | Team is ready to begin on time when called | Demo starts without delay beyond allocated transition/setup | S3-015 to S3-022 |  |
| C02 | Demo environment is operational at start | Deployed app or stable runtime loads successfully | S3-015, S3-017, S3-022 |  |
| C03 | Seed data includes a primary demo user with multiple documents | At least 6-8 documents are available for the demo | S3-001 to S3-010 |  |
| C04 | Second user account exists for ownership checks | Team can switch users for security evidence | S3-002, S3-012, S3-020, S3-021 |  |
| C05 | Document library list view is available | Global document list is visible and usable | S3-001 |  |
| C06 | Document metadata displays correctly | Title, type, status, tags, and updated date are visible | S3-002 |  |
| C07 | Document upload validation works | Supported format uploads succeed and unsupported are rejected | S3-004, S3-005 |  |
| C08 | Version history is visible and usable | Team can open version metadata/history for a document | S3-003, S3-007, S3-008 |  |
| C09 | Duplicate and rename workflow works | A document can be duplicated and renamed cleanly | S3-007 |  |
| C10 | Archive and restore workflow works | Document can be archived and restored without losing history | S3-008, S3-009 |  |
| C11 | Job detail shows linked documents clearly | Linked document section is visible and understandable | S3-009, S3-010 |  |
| C12 | One resume and one cover letter max are enforced per job (negative/constraint case) | Replacement or duplicate link is blocked/confirmed as required | S3-010, S3-011, S3-012 |  |
| C13 | Company research can be triggered from job detail | User-provided prompt/context drives research generation | S3-011 |  |
| C14 | Company research output saves as editable job notes | Research output persists to the job record | S3-012 |  |
| C15 | Interview prep notes section is usable | Structured notes can be edited and saved | S3-013 |  |
| C16 | Analytics show velocity and stage conversion | Dashboard metrics reflect persisted events | S3-014 |  |
| C17 | Analytics are based on stored backend data, not UI-only state | Team can explain source of metric values | S3-014, S3-015 |  |
| C18 | Deployment checks and health checks are visible in CI/CD evidence | Pipeline includes deployment and health verification | S3-015, S3-017, S3-018 |  |
| C19 | Centralized error handling/logging evidence is shown | Sanitized error output or logged failure path is visible | S3-018 |  |
| C20 | Smoke-test or release-readiness evidence is present | Demo-critical flow has verification evidence | S3-020, S3-022 |  |
| C21 | Team opens GitHub Actions and shows latest relevant workflow run | Actions page is shown live with recent run context | S3-017, S3-018, S3-022 |  |
| C22 | GitHub Actions evidence shows build + unit test execution | Workflow details clearly include build/test jobs | S3-020, S3-021, S3-022 |  |
| C23 | Team can show negative unit tests for document/workflow rules | At least one negative test is demonstrated live | S3-007, S3-010, S3-021 |  |
| C24 | Team can show negative unit tests for deployment/reliability checks | At least one negative test tied to CI/CD or error handling is demonstrated | S3-018, S3-019, S3-022 |  |
| C25 | Team is prepared to show at least three negative unit tests and explain each | Three negative tests are shown and briefly explained | S3-010, S3-018, S3-021, S3-022 |  |

## 7. Subjective Q&A (Only Subjective Portion)

Suggested Q&A prompts:

1. How did you keep the user experience coherent while adding document and deployment workflows?
2. What was the highest risk area in Sprint 3 and how did you reduce it?
3. What would you improve next if given one additional sprint?
4. How did you keep analytics grounded in persisted data?

Suggested subjective scoring guide (0 to 5):

1. `0-1`: unclear explanations; weak technical understanding.
2. `2-3`: acceptable understanding with partial depth.
3. `4-5`: clear, accurate, evidence-backed technical reasoning.

## 8. Fast Grading Summary

1. Objective checklist subtotal: ____ / 25
2. Bug/failure penalties (no cap): -____
3. Subjective Q&A score: +____ / 5
4. Final score: ____
