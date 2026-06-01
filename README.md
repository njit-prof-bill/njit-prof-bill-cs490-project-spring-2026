# ATS for Candidates - Product Requirements Document (Spring 2026)

_CS 490 Capstone Project_

## 1. Product Purpose and Vision

### 1.1 Product Purpose

ATS for Candidates is a candidate-facing application tracking system.

The purpose is to help job seekers run a disciplined, end-to-end campaign with the same workflow rigor employers use in hiring pipelines.

### 1.2 Product Vision

One coherent web app where a user can:

1. Authenticate and securely manage an account.
2. Build and maintain a professional profile.
3. Track jobs from interest through outcome.
4. Create and manage job-context application artifacts.
5. Use actionable metrics to improve search strategy.

### 1.3 Product Positioning

This is a SaaS-style, multi-user web application with self-registration and strict per-user data isolation.

## 2. Primary UX Principle

The **Dashboard/Job Board** is the center of gravity.

Most day-to-day actions should start or end in dashboard and job detail workflows.

Profile supports those workflows. Document management is important, but secondary to the job campaign flow.

## 3. Core Product Areas

1. Dashboard and Job Detail workflow (primary).
2. User Profile (canonical personal/professional data).
3. Document workflows (job-context first; expanded global management in Sprint 3).
4. Settings and account controls.

## 4. Functional Requirements

## 4.1 Authentication and Ownership

1. Users can register, login, logout, and reset password.
2. Protected routes require authenticated access.
3. Backend enforces data ownership boundaries for all user-scoped entities.
4. Cross-user read/write attempts are denied.

### Acceptance Criteria

1. Unauthenticated user cannot access protected data.
2. User A cannot access User B records.
3. Duplicate registration email is rejected.
4. Session invalidates cleanly on logout.

## 4.2 Dashboard and Job Campaign Workflow

### Job Data Minimums

1. Required fields at job creation:
   - company
   - title
   - full job posting body
2. Job posting body is editable after creation.

### Canonical Stage Model

Stages:

1. Interested
2. Applied
3. Interview
4. Offer
5. Rejected
6. Archived

Allowed forward transitions:

1. Interested -> Applied or Rejected
2. Applied -> Interview or Rejected
3. Interview -> Offer or Rejected
4. Offer -> Archived or Rejected

Override behavior:

1. Non-forward transitions require warning and explicit confirmation.
2. Confirmed overrides are logged with timestamp and user identity.

### Interview and Activity Rules

1. A job can have multiple interview entries while in Interview stage.
2. Interview entries include round type, date/time, and notes.
3. Follow-ups/reminders are tied to specific jobs.
4. Timeline reflects stage changes and activity events in chronological order.

### Acceptance Criteria

1. User can create/edit/search/filter/sort jobs.
2. User can open job detail and manage stage/activity data.
3. Stage transition history is persisted with timestamps.
4. Job workflow updates are reflected consistently across detail view and dashboard views.

## 4.3 User Profile

Profile sections:

1. Identity and Contact
2. Professional Summary
3. Experience
4. Education
5. Skills
6. Career Preferences

Validation rules include:

1. End date cannot be earlier than start date.
2. Duplicate skills are disallowed.
3. Section-level save returns field-level validation errors.

### Acceptance Criteria

1. User can CRUD all profile sections required by sprint scope.
2. Profile updates persist across sessions.
3. Profile completion indicator updates after relevant changes.

## 4.4 Document Handling

### Business Scope

1. Supported document business types: resume and cover letter only.
2. Supported upload formats: PDF, DOCX, TXT.
3. Unsupported formats are rejected with meaningful validation messages.

### Versioning and Links

1. New versions are created by explicit version-creation actions.
2. Version history stores version metadata and timestamps.
3. Archive and restore preserve version history.

### Job-Document Relationship

1. Each job may have at most one linked resume and one linked cover letter at a time.
2. Replacing a linked document requires confirmation.
3. Linking must preserve referential integrity and ownership checks.

### Acceptance Criteria

1. User can upload, version, archive/restore, and download allowed document types.
2. User can link/unlink documents from job detail with cardinality constraints enforced.
3. Document operations respect per-user ownership.

## 4.5 AI Features

Allowed AI usage:

1. Resume draft generation from profile + job context.
2. Cover letter draft generation from profile + job context.
3. Rewrite and improve actions on user-visible draft content.

Constraints:

1. AI actions are explicit user-triggered actions.
2. AI output is editable before save.
3. AI is not a substitute for fake third-party integration behavior.

## 4.6 Metrics

Sprint 2 baseline metrics:

1. Stage counts.
2. Response tracking.

Sprint 3 analytics extensions:

1. **Velocity** = count of Interested -> Applied transitions in rolling 7-day window.
2. **Stage conversion** = Applied -> Interview conversion within 14 days using persisted timestamps.

Metrics must be derived from persisted backend records, not transient UI-only state.

## 5. Non-Functional Requirements

1. Security: per-user data isolation and backend authorization checks are mandatory.
2. Reliability: normal CRUD/workflow paths should execute without crashes.
3. Usability: coherent navigation and clear feedback/error states.
4. Accessibility: reasonable keyboard support, labels, and contrast for major flows.
5. Performance: class-demo-ready responsiveness under expected load.

## 6. CI/CD and Testing Standards

These standards apply across all sprints, with ratcheting expectations.

### Sprint 1 baseline

1. PR CI runs lint, build, and unit tests.
2. Failing checks block merge.
3. Stories include happy-path and non-happy-path tests.

### Sprint 2 ratchet

1. Keep Sprint 1 requirements.
2. Add changed-code coverage gate.
3. Add integration tests for critical workflow paths.

### Sprint 3 ratchet

1. Keep Sprint 1 and Sprint 2 requirements.
2. Add deployment checks, post-deploy health checks, and smoke tests.
3. Add migration verification and reliability regression checks.

## 7. Domain Model (High Level)

Minimum entities:

1. User
2. Profile
3. Job
4. JobActivity
5. Document
6. DocumentVersion
7. JobDocumentLink

Required relationships:

1. User 1:N Job
2. User 1:1 Profile
3. User 1:N Document
4. Document 1:N DocumentVersion
5. Job 1:N JobActivity
6. Job to DocumentVersion links via JobDocumentLink with per-job cardinality constraints by document type

## 8. Sprint Themes and Delivery Order

Story source files:

1. Sprint 1 stories: `Sprint1Stories.md`
2. Sprint 2 stories: `Sprint2Stories.md`
3. Sprint 3 stories: `Sprint3Stories.md`

Themes:

1. Sprint 1: Authentication and User Profile (with engineering baseline)
2. Sprint 2: Job Posts and Workflow
3. Sprint 3: Document Handling and Cloud Deployment

## 9. Student Execution Guidance

1. Treat each sprint story file as authoritative for that sprint.
2. Use canonical business rule IDs in the sprint file when implementing and testing stories.
3. Keep Jira tickets one-to-one with stories.
4. Provide explicit test evidence for each completed story.

## 10. Definition of Done (Project Level)

A team is done when:

1. Full user flow works end-to-end with per-user isolation.
2. Required sprint outcomes are implemented and test-backed.
3. CI/CD quality gates pass for the relevant sprint.
4. Deployed app is stable enough for demonstration.
