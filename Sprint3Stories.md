# ATS for Candidates - Sprint 3 Stories (Spring 2026)

This is the Sprint 3 backlog slice from the unified planning pass.

Story writing format for Jira:

- Story ID
- Title
- Outcome (what must be true when complete)

Sprint 3 focus: document workflows, company research support, deployment, and final hardening.

Total stories: 22

## CI/CD and Testing Requirements (Required)

These requirements are self-contained and mandatory for Sprint 3 delivery.

### Carry-Forward Requirements from Sprint 1 and Sprint 2

1. Every pull request must run lint, build, unit tests, and Sprint 2 coverage gates.
2. A pull request with any failing check cannot be merged.
3. Every story must include automated test updates with happy-path and non-happy-path coverage.
4. Ownership, authorization, and validation protections must remain covered by regression tests.

### Sprint 3 Ratchet Requirements

1. CI/CD pipeline must include deployment steps and post-deploy health checks.
2. Add smoke tests for demo-critical user flows after deployment.
3. Add migration verification checks for production database changes.
4. Add reliability tests for error-handling paths in document and workflow services.
5. Add regression tests for document versioning and linking rules.

### Minimum Test Evidence for Sprint 3 Stories

1. One test for expected behavior of the story outcome.
2. One test for failure/edge behavior.
3. One test that protects against regression in a previously delivered feature.
4. Deployment-related stories must include CI/CD evidence and at least one post-deploy verification artifact.

### Definition of Done Additions

1. Story outcome works in running app.
2. Story tests pass locally and in CI.
3. Story satisfies Sprint 3 CI/CD gates, including deployment and smoke-check expectations.
4. Pull request includes a "test evidence" section with links or artifacts for deployment verification where applicable.

## Canonical Business Rules (Sprint 3)

These rules are authoritative for Sprint 3 implementation and grading.

### S3-BR Document Domain Scope

1. **S3-BR-001**: Supported document business types are resume and cover letter only.
2. **S3-BR-002**: Document ownership must remain user-scoped and isolated.
3. **S3-BR-003**: Document actions must preserve audit-friendly timestamps.

### S3-BR Document Format and File Handling

1. **S3-BR-004**: Supported upload formats are PDF, DOCX, and TXT.
2. **S3-BR-005**: Unsupported formats must be rejected with clear validation messages.
3. **S3-BR-006**: Export/download must support defined output formats for user documents.

### S3-BR Versioning and History

1. **S3-BR-007**: New document versions are created only by explicit version-creation actions.
2. **S3-BR-008**: Version history must capture version label/number, timestamp, and ownership metadata.
3. **S3-BR-009**: Archive/restore must preserve version history.

### S3-BR Job-Document Relationship

1. **S3-BR-010**: A job can be linked to at most one resume and at most one cover letter at a time.
2. **S3-BR-011**: Replacing a currently linked document must require confirmation.
3. **S3-BR-012**: Link changes must preserve referential integrity and ownership checks.

### S3-BR Analytics Definitions

1. **S3-BR-013**: Velocity equals the number of Interested -> Applied transitions in a rolling 7-day window.
2. **S3-BR-014**: Stage conversion equals Applied -> Interview conversion within 14 days using persisted timestamps.
3. **S3-BR-015**: Analytics must be computed from backend persisted events, not transient UI state.

### S3-BR Deployment and Reliability

1. **S3-BR-016**: Main-branch deployment must be automated through CI/CD pipeline execution.
2. **S3-BR-017**: Deployment must include post-deploy health checks.
3. **S3-BR-018**: Production database changes must use versioned migration workflow.
4. **S3-BR-019**: Centralized error handling/logging must exist for server-side failures.
5. **S3-BR-020**: Demo-critical flows must be covered by smoke-test verification before release/demo.

### Rule Usage in Stories and Jira

1. Any Sprint 3 story may reference one or more S3-BR IDs instead of repeating rule text.
2. If story behavior conflicts with a canonical rule, the canonical rule prevails.

---

## A. Document Library Implementation

1. **S3-001 - Implement Document Library List View**
   Outcome: Users can view all their documents in a global library.
   Rules: S3-BR-001, S3-BR-002

2. **S3-002 - Implement Document Metadata Model and Persistence**
   Outcome: Documents support title, type, status, tags, ownership, and timestamps.
   Rules: S3-BR-001, S3-BR-002, S3-BR-003

3. **S3-003 - Implement Document Version Model and Persistence**
   Outcome: Documents support version history with version metadata.
   Rules: S3-BR-007, S3-BR-008

4. **S3-004 - Implement Document Upload Workflow**
   Outcome: Users can upload supported document files, validate file constraints, and store them in library records.
   Rules: S3-BR-001, S3-BR-004, S3-BR-005

5. **S3-005 - Implement Document Download/Export Workflow**
   Outcome: Users can download/export selected document versions from library and job context views.
   Rules: S3-BR-006

6. **S3-006 - Implement Library Filtering and Sorting**
   Outcome: Users can filter/sort by type, status, tag, and updated date.
   Rules: S3-BR-001

7. **S3-007 - Implement Document Duplicate and Rename Actions**
   Outcome: Users can duplicate existing artifacts and rename cleanly.
   Rules: S3-BR-007, S3-BR-008

8. **S3-008 - Implement Archive and Restore for Documents**
   Outcome: Users can archive and restore documents without hard deletion.
   Rules: S3-BR-009

9. **S3-009 - Implement Job-to-Library Linking UX**
   Outcome: Job detail allows linking/unlinking library documents to applications.
   Rules: S3-BR-010, S3-BR-011, S3-BR-012

10. **S3-010 - Implement Library Visibility in Job Detail Context**
    Outcome: Job detail displays linked documents and relevant versions clearly.
    Rules: S3-BR-010, S3-BR-012

## B. Company Research and Advanced Workflow Support

11. **S3-011 - Implement Company Research Input and Prompt UX in Job Detail**
    Outcome: Users can trigger AI-assisted company research from job detail using user-provided context.
    Rules: S3-BR-002

12. **S3-012 - Persist Company Research Notes to Job Record**
    Outcome: Research output is saved as editable notes tied to the job.
    Rules: S3-BR-002, S3-BR-003

13. **S3-013 - Add Interview Preparation Notes Section in Job Detail**
    Outcome: Users can maintain structured prep notes for interviews.
    Rules: S3-BR-003

14. **S3-014 - Expand Dashboard Analytics (Velocity and Stage Conversion)**
    Outcome: Dashboard includes conversion and time-in-stage analytics from stored events.
    Rules: S3-BR-013, S3-BR-014, S3-BR-015

## C. Deployment, Reliability, and Final Quality

15. **S3-015 - Provision Cloud Runtime for Frontend and Backend**
    Outcome: App is deployed to cloud with public URL and documented environment setup.
    Rules: S3-BR-016, S3-BR-017

16. **S3-016 - Configure Production Database and Migrations**
    Outcome: Production data store is provisioned with migration strategy and rollback plan.
    Rules: S3-BR-018

17. **S3-017 - Configure CI/CD Deployment Pipeline**
    Outcome: Merge to main triggers production deployment with health checks.
    Rules: S3-BR-016, S3-BR-017

18. **S3-018 - Implement Centralized Error Handling and Logging**
    Outcome: Server/client errors are captured consistently with actionable context.
    Rules: S3-BR-019

19. **S3-019 - Implement Performance and Accessibility Pass**
    Outcome: Team executes and documents fixes for major performance/accessibility issues.
    Rules: S3-BR-019, S3-BR-020

20. **S3-020 - Expand Unit Test Coverage for Security and Ownership Rules**
    Outcome: Critical authorization and ownership enforcement paths are unit-tested.
    Rules: S3-BR-002

21. **S3-021 - Expand Unit Test Coverage for Document Logic**
    Outcome: Document versioning, archive/restore, upload/download, and job-link ownership rules are unit-tested.
    Rules: S3-BR-007, S3-BR-010, S3-BR-012

22. **S3-022 - Final Release Readiness and Demo Hardening**
    Outcome: Team completes release checklist, smoke tests, and demo stabilization.
    Rules: S3-BR-016, S3-BR-017, S3-BR-020
