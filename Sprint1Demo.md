# Sprint 1 Demo Script and Grading Checklist (Spring 2026)

_ATS for Candidates - CS 490 Capstone_

## 1. Purpose

This is a single source of truth for Sprint 1 demo execution and grading.

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
2. Behavior that clearly contradicts the listed Sprint 1 requirement being demonstrated.
3. Required evidence unavailable when requested (for example, required test evidence page cannot be shown).

### 3.3 Subjective Q&A Score

1. Q&A is the only subjective component.
2. Suggested Q&A score range: 0 to 5.

### 3.4 Recommended Total

1. Recommended total score = `Objective Checklist (0-25) - Bug Penalties + Q&A (0-5)`.

## 4. Required Preparation (Before Demo Day)

Teams must be ready with:

1. Runnable app environment.
2. Two accounts (User A and User B).
3. Seed data including non-engineering profile content.
4. Seed jobs prepared for Dashboard baseline demonstration.
5. GitHub Actions page ready for CI and test evidence.
6. At least three negative unit tests ready to show and explain.

## 5. Live Demo Script (Tied to Checklist)

Run in this order to match grading flow:

1. Readiness and data checks: `C01-C04`.
2. Authentication flow and negative auth checks: `C05-C09`.
3. Ownership/security evidence: `C10`.
4. Dashboard baseline flow: `C11-C15`.
5. Profile baseline and validation flow: `C16-C19`.
6. Settings and UI consistency checks: `C20-C22`.
7. GitHub Actions CI and test evidence: `C23-C25`.
8. Instructor Q&A (subjective section).

## 6. Sprint 1 Objective Checklist (25 Items)

Use this checklist live during demo. Each row is `1` or `0`.

| ID  | Checklist Item (Yes/No)                                                      | Evidence To Observe                                              | Sprint 1 Story Coverage | Score |
| --- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------- | ----------------------- | ----- |
| C01 | Team is ready to begin on time when called                                   | Demo starts without delay beyond allocated transition/setup      | S1-005, S1-008          |       |
| C02 | Demo environment is operational at start (app loads successfully)            | App loads and is usable before scripted steps begin              | S1-005, S1-009          |       |
| C03 | Prepared data includes at least one non-engineering profile                  | Profile data shown is not limited to software roles only         | S1-022, S1-023          |       |
| C04 | Two distinct accounts are prepared (User A and User B)                       | Team can switch between accounts for security checks             | S1-010 to S1-015        |       |
| C05 | User registration works with email and password                              | New user can be created successfully                             | S1-010                  |       |
| C06 | Duplicate-email registration is rejected with clear message (negative)       | Duplicate registration attempt fails with meaningful feedback    | S1-010                  |       |
| C07 | Valid login works for registered user                                        | User reaches authenticated state after login                     | S1-011                  |       |
| C08 | Invalid password login shows meaningful error (negative)                     | Login fails gracefully with clear message                        | S1-011                  |       |
| C09 | Logout invalidates session and protected page access is denied (negative)    | After logout, protected route/API access is blocked              | S1-012, S1-014          |       |
| C10 | User B cannot view/modify User A owned data (negative security case)         | Cross-user access attempt fails as expected                      | S1-015                  |       |
| C11 | Dashboard opens as primary workspace                                         | Dashboard is the main post-login home flow                       | S1-016, S1-018          |       |
| C12 | Job cards render baseline fields                                             | Card includes title, company, stage, last activity               | S1-020                  |       |
| C13 | Team can create a new job from dashboard flow                                | New job appears after create action                              | S1-019, S1-021          |       |
| C14 | Team can edit an existing job from dashboard flow                            | Existing job update is reflected on UI                           | S1-019, S1-021          |       |
| C15 | Job data persists after refresh/navigation                                   | Created/edited job remains after reload                          | S1-019, S1-021          |       |
| C16 | Profile baseline section is present (identity/contact + summary)             | Required Sprint 1 profile sections are visible                   | S1-022                  |       |
| C17 | Profile baseline update saves successfully                                   | Edited profile fields persist after save                         | S1-022                  |       |
| C18 | Profile completion indicator updates when baseline data changes              | Indicator changes after update to baseline fields                | S1-023                  |       |
| C19 | Profile validation failure shows clear field-level feedback (negative)       | Invalid/missing required input produces clear validation message | S1-022, S1-023          |       |
| C20 | Settings page exists and is reachable in app shell                           | Settings is present and navigable                                | S1-017                  |       |
| C21 | Typography is consistent across Dashboard, Profile, and Settings             | Same typographic system is used across major Sprint 1 screens    | S1-016, S1-017, S1-018  |       |
| C22 | Form and error styling is consistent across major Sprint 1 screens           | Inputs/labels/errors follow consistent style rules               | S1-016, S1-022, S1-023  |       |
| C23 | Team opens GitHub Actions and shows latest relevant workflow run             | Actions page is shown live with recent run context               | S1-008                  |       |
| C24 | GitHub Actions evidence shows build + unit test execution                    | Workflow details clearly include build/test jobs                 | S1-007, S1-008          |       |
| C25 | Team is prepared to show at least three negative unit tests and explain each | Three negative tests are shown and briefly explained             | S1-007, S1-015          |       |

## 7. Subjective Q&A (Only Subjective Portion)

Sample Q&A prompts (**Important!** these are sample questions, not the actual questions that will be asked. Not every team will be asked
the same questions):

1. Why this architecture and stack for Sprint 1?
2. Where is ownership enforcement implemented in backend logic?
3. What tradeoff did the team make in Sprint 1 and why?
4. What is the biggest technical risk going into Sprint 2?

Suggested subjective scoring guide (0 to 5):

1. `0-1`: unclear explanations; weak technical understanding.
2. `2-3`: acceptable understanding with partial depth.
3. `4-5`: clear, accurate, evidence-backed technical reasoning.

## 8. Fast Grading Summary

1. Objective checklist subtotal: \_\_\_\_ / 25
2. Bug/failure penalties (no cap): -\_\_\_\_
3. Subjective Q&A score: +\_\_\_\_ / 5
4. Final score: \_\_\_\_
