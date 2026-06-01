# ATS for Candidates - Sprint 2 Stories (Spring 2026)

This is the Sprint 2 backlog slice from the unified planning pass.

Story writing format for Jira:

- Story ID
- Title
- Outcome (what must be true when complete)

Sprint 2 focus: Dashboard workflow completion, profile completion, AI job-context workflows, and baseline metrics/testing.

Total stories: 26

## CI/CD and Testing Requirements (Required)

These requirements are self-contained and mandatory for Sprint 2 delivery.

### Carry-Forward Requirements from Sprint 1

1. Every pull request must run lint, build, and unit tests.
2. A pull request with any failing check cannot be merged.
3. Every story must include test updates with happy-path and non-happy-path coverage.
4. Auth, validation, and ownership behaviors must continue to have automated negative-path tests.

### Sprint 2 Ratchet Requirements

1. Add CI coverage enforcement for changed files or changed modules.
2. Add integration tests for critical workflow paths in dashboard/job detail logic.
3. Require workflow integrity tests for stage changes and timeline event propagation.
4. Require profile completion logic tests for boundary and edge cases.
5. Require API tests that verify per-user ownership constraints still hold after workflow updates.

### Minimum Test Evidence for Workflow Stories

1. One test proving expected forward workflow behavior.
2. One test proving invalid transition/invalid input handling.
3. One test proving persisted state is reflected in dependent views or metrics.

### Definition of Done Additions

1. Story outcome works in running app.
2. Story tests pass locally and in CI.
3. Story meets Sprint 2 coverage gate in CI.
4. Pull request includes a "test evidence" section describing workflow and negative-path tests.

## Canonical Business Rules (Sprint 2)

These rules are authoritative for Sprint 2 implementation and grading.

### S2-BR Job Posting and Core Job Data

1. **S2-BR-001**: A job must include company, title, and full job posting body.
2. **S2-BR-002**: Job posting body is required at job creation time.
3. **S2-BR-003**: Job posting body must be editable after creation.

### S2-BR Campaign Workflow and Stage Rules

1. **S2-BR-004**: Canonical stages are Interested, Applied, Interview, Offer, Rejected, and Archived.
2. **S2-BR-005**: Allowed forward transitions are:
   - Interested -> Applied or Rejected
   - Applied -> Interview or Rejected
   - Interview -> Offer or Rejected
   - Offer -> Archived or Rejected
3. **S2-BR-006**: Archived is terminal for normal flow.
4. **S2-BR-007**: Non-forward transitions require warning and explicit user confirmation.
5. **S2-BR-008**: Confirmed override transitions must be logged with timestamp and user identity.
6. **S2-BR-009**: Stage transitions must persist timestamped history for timeline and analytics.

### S2-BR Interview and Activity Rules

1. **S2-BR-010**: A job may have multiple interview entries while in Interview stage.
2. **S2-BR-011**: Interview entries require round type, date/time, and notes.
3. **S2-BR-012**: Follow-up/reminder events must be tied to a specific job.
4. **S2-BR-013**: Timeline must reflect stage changes and activity events in chronological order.

### S2-BR Profile Completion and Validation

1. **S2-BR-014**: Profile sections Experience, Education, Skills, and Preferences must support CRUD.
2. **S2-BR-015**: End date cannot be earlier than corresponding start date for dated entries.
3. **S2-BR-016**: Duplicate skills are not allowed within a single user profile.
4. **S2-BR-017**: Section-level save must return clear field-level validation errors.

### S2-BR AI and Job-Context Document Rules

1. **S2-BR-018**: AI drafting must be triggered by explicit user action.
2. **S2-BR-019**: AI resume and cover letter drafts must use profile plus job context inputs.
3. **S2-BR-020**: Generated output is editable before save.
4. **S2-BR-021**: Job-context save operations must preserve ownership boundaries.

### S2-BR Metrics Definitions

1. **S2-BR-022**: Baseline dashboard metrics in Sprint 2 are stage counts and response tracking only.
2. **S2-BR-023**: Metric values must be computed from persisted job and event records, not UI-only state.

### Rule Usage in Stories and Jira

1. Any Sprint 2 story may reference one or more S2-BR IDs instead of repeating rule text.
2. If story behavior conflicts with a canonical rule, the canonical rule prevails.

---

## A. Dashboard Core Workflow Completion

1. **S2-001 - Implement Job Search Across Dashboard**
   Outcome: Users can search jobs by title/company/keywords with immediate result updates.

2. **S2-002 - Implement Job Filter Controls**
   Outcome: Users can filter by stage, location, and deadline state.

3. **S2-003 - Implement Job Sorting Controls**
   Outcome: Users can sort by last activity, deadline, company, and created date.

4. **S2-004 - Implement Stage/Status Indicators on Job Cards**
   Outcome: Cards clearly display current stage and urgency cues.

5. **S2-005 - Implement Job Card to Job Detail Expansion Pattern**
   Outcome: Every job card opens to a consistent job detail UI pattern.

6. **S2-006 - Implement Job Detail Overview Section**
   Outcome: Users can edit core job data in a dedicated overview panel.

7. **S2-007 - Implement Job Deadline and Recruiter/Contact Notes Fields**
   Outcome: Job detail supports deadline field and recruiter/contact notes with persistence and edit support.

8. **S2-008 - Implement Pipeline Stage Transition Controls**
   Outcome: Users can change stage from detail view and dashboard controls.

9. **S2-009 - Persist Stage Transition Timestamps**
   Outcome: Stage changes are recorded with timestamps for timeline and analytics use.

10. **S2-010 - Implement Job Activity Timeline**
    Outcome: Timeline displays key events (applied, follow-up, interview, outcome).

11. **S2-011 - Implement Interview Tracking in Job Detail**
    Outcome: Users can add/edit interview events with round type, date/time, and notes.

12. **S2-012 - Implement Follow-Up and Reminder Tracking**
    Outcome: Users can create and manage follow-up tasks/reminders tied to a job.

13. **S2-013 - Implement Outcome Tracking Controls**
    Outcome: Users can record final outcome states and notes for each job.

14. **S2-014 - Implement Job Archive and Restore Workflow**
    Outcome: Users can archive and restore jobs while preserving full history and linked records.

15. **S2-015 - Implement Job Delete Workflow**
    Outcome: Users can delete jobs through a guarded workflow (confirmation and ownership checks).

## B. Profile Completion

16. **S2-016 - Implement Experience Section CRUD**
    Outcome: Users can add/edit/delete/reorder employment and project entries.

17. **S2-017 - Implement Education Section CRUD**
    Outcome: Users can add/edit/delete education records with full required fields.

18. **S2-018 - Implement Skills Section CRUD**
    Outcome: Users can add/edit/delete/reorder skills with optional category/proficiency.

19. **S2-019 - Implement Career Preferences Section CRUD**
    Outcome: Users can maintain target roles, location preferences, work mode, and salary preference.

20. **S2-020 - Implement Section-Level Save/Validation UX for Profile**
    Outcome: Each profile section saves independently with clear validation feedback.

## C. AI-Powered Job Context Workflows

21. **S2-021 - Implement AI Resume Draft from Profile + Job Context**
    Outcome: Users can generate a resume draft from job detail using profile data and job data.

22. **S2-022 - Implement AI Cover Letter Draft from Profile + Job Context**
    Outcome: Users can generate a cover letter draft from job detail using profile and job context.

23. **S2-023 - Implement AI Rewrite/Improve Actions for Draft Content**
    Outcome: Users can request AI rewrites/improvements and compare before saving.

24. **S2-024 - Implement Document Save from Job Context**
    Outcome: Generated/edited drafts can be saved as document records linked to job context.

## D. Dashboard Metrics and Quality

25. **S2-025 - Implement Dashboard Metrics (Stage Counts and Response Tracking)**
    Outcome: Dashboard displays baseline metrics computed from stored job/outcome data.

26. **S2-026 - Add Unit Tests for Job Workflow and Profile Completion Logic**
    Outcome: Core domain logic for stage transitions, timeline events, and profile completeness is unit-tested.
