# ATS for Candidates - Sprint 1 Stories (Spring 2026)

This is the Sprint 1 backlog slice from the unified planning pass.

Story writing format for Jira:

- Story ID
- Title
- Outcome (what must be true when complete)

Sprint 1 focus: Dashboard foundation, authentication, CI/CD, and profile baseline.

Total stories: 23

## CI/CD and Testing Requirements (Required)

These requirements apply to all Sprint 1 stories.

### CI/CD Baseline Gate

1. Every pull request must run lint, build, and unit tests.
2. A pull request with any failing check cannot be merged.
3. CI output must be visible to reviewers before merge.

### Test Baseline Expectations

1. Every story must include at least one automated test update (new test or updated existing test).
2. Authentication and authorization stories must include negative-path tests.
3. Validation stories must include field-level error assertions.
4. Ownership rules must be tested to prove cross-user access is denied.

### Minimum Test Evidence by Story Type

1. Happy-path behavior test.
2. At least one non-happy-path test (validation, unauthorized, or failure handling).
3. Persistence check where data is created or updated.

### Definition of Done Additions

1. Story outcome works in running app.
2. Required tests pass locally and in CI.
3. Story does not reduce existing test coverage in touched modules.
4. Pull request description includes a short "test evidence" section.

## Canonical Business Rules (Sprint 1)

These rules are authoritative for Sprint 1 implementation and grading.

### S1-BR Authentication and Access

1. **S1-BR-001**: User authentication is required for all protected application routes.
2. **S1-BR-002**: Unauthenticated access to protected routes must be denied by backend checks.
3. **S1-BR-003**: User registration must prevent duplicate email accounts.
4. **S1-BR-004**: Password reset must require secure user verification before password update.
5. **S1-BR-005**: Session invalidation on logout must block subsequent protected API access.

### S1-BR Data Ownership and Security

1. **S1-BR-006**: All user-scoped records must be isolated by owner identity.
2. **S1-BR-007**: Cross-user read/write attempts must be denied.
3. **S1-BR-008**: Ownership enforcement must be implemented server-side (frontend checks are not sufficient).

### S1-BR Profile Baseline

1. **S1-BR-009**: Identity/contact and summary fields form the Sprint 1 profile baseline.
2. **S1-BR-010**: Profile updates must persist across refresh and new sessions.
3. **S1-BR-011**: Profile completion indicator must reflect baseline required fields only.

### S1-BR Dashboard Baseline

1. **S1-BR-012**: Dashboard is the home page and baseline job workspace.
2. **S1-BR-013**: Users can create and edit baseline job records with persistence.
3. **S1-BR-014**: Baseline job card must display at least title, company, stage, and last activity.

### Rule Usage in Stories and Jira

1. Any Sprint 1 story may reference one or more S1-BR IDs instead of repeating rule text.
2. If story behavior conflicts with a canonical rule, the canonical rule prevails.

---

## A. AI Context Documents (required before feature coding)

1. **S1-001 - Create Engineering Coding Standards Context Document**
   Outcome: Team publishes a context doc for AI and humans covering naming conventions, folder structure, linting/formatting rules, error handling style, and API response conventions.
   Rules: S1-BR-001, S1-BR-006, S1-BR-008

2. **S1-002 - Create UI/UX Standards Context Document**
   Outcome: Team publishes a context doc defining chosen navigation model, dashboard interaction model, component usage rules, spacing/typography conventions, and consistency rules.
   Rules: S1-BR-001, S1-BR-006, S1-BR-008

3. **S1-003 - Create Data and Security Guardrails Context Document**
   Outcome: Team publishes a context doc defining per-user data ownership, authorization checks, protected route behavior, and prohibited cross-user access patterns.
   Rules: S1-BR-001, S1-BR-006, S1-BR-008

4. **S1-004 - Create AI Prompting and Review Context Document**
   Outcome: Team publishes a context doc for how AI-generated code is prompted, reviewed, tested, and approved before merge.
   Rules: S1-BR-001, S1-BR-006, S1-BR-008

## B. Project and Delivery Baseline

5. **S1-005 - Initialize Monorepo/Project Structure**
   Outcome: Repo has stable frontend/backend structure, shared config, and documented run commands.
   Rules: S1-BR-001, S1-BR-006

6. **S1-006 - Configure Linting and Formatting**
   Outcome: Lint/format tools are installed and runnable in CI; formatting is consistent across team contributions.
   Rules: S1-BR-001, S1-BR-006

7. **S1-007 - Configure Unit Test Frameworks**
   Outcome: Unit test frameworks are set up for frontend and backend with one passing sample test per side.
   Rules: S1-BR-001, S1-BR-006

8. **S1-008 - Configure CI Pipeline for Build and Test**
   Outcome: Pull requests run automated build and unit tests; failing checks block merge.
   Rules: S1-BR-001, S1-BR-006

9. **S1-009 - Configure Environment Management**
   Outcome: Team has documented `.env` strategy for local/dev/prod without committing secrets.
   Rules: S1-BR-001, S1-BR-006

## C. Authentication and User Ownership

10. **S1-010 - Implement User Self-Registration**
    Outcome: New users can create accounts through a registration form with validation and duplicate-email handling.
    Rules: S1-BR-001, S1-BR-003, S1-BR-006

11. **S1-011 - Implement User Login and Session Handling**
    Outcome: Registered users can sign in and maintain authenticated session state.
    Rules: S1-BR-001, S1-BR-005

12. **S1-012 - Implement Logout and Session Invalidation**
    Outcome: Users can sign out cleanly and protected data becomes inaccessible until next login.
    Rules: S1-BR-001, S1-BR-005

13. **S1-013 - Implement Password Reset Workflow**
    Outcome: Users can request reset and set a new password through secure token flow.
    Rules: S1-BR-001, S1-BR-004, S1-BR-006

14. **S1-014 - Enforce Route Protection**
    Outcome: Unauthenticated users are redirected from protected pages and APIs return correct auth errors.
    Rules: S1-BR-001, S1-BR-002

15. **S1-015 - Enforce Per-User Data Authorization**
    Outcome: API/resource access is constrained to owner account; cross-user reads/writes are blocked.
    Rules: S1-BR-006, S1-BR-007, S1-BR-008

## D. Dashboard Foundation and Job Baseline

16. **S1-016 - Build Global App Shell and Navigation**
    Outcome: App has consistent navigation and page layout for Dashboard, Profile, Document Library, and Settings.
    Rules: S1-BR-012

17. **S1-017 - Implement Settings Page Baseline**
    Outcome: Settings page exists with baseline account settings structure and consistent app-shell behavior.
    Rules: S1-BR-012

18. **S1-018 - Build Dashboard Home Skeleton**
    Outcome: Dashboard home page renders stable structure for job board workspace.
    Rules: S1-BR-012

19. **S1-019 - Implement Basic Job Entity and Storage**
    Outcome: Job records can be created, stored, and retrieved with user ownership.
    Rules: S1-BR-012, S1-BR-013, S1-BR-006

20. **S1-020 - Implement Basic Job Card Rendering**
    Outcome: Dashboard shows job cards with baseline fields (title, company, stage, activity date).
    Rules: S1-BR-012, S1-BR-014

21. **S1-021 - Implement Basic Job Create/Edit Form**
    Outcome: Users can create and update job records from dashboard flow.
    Rules: S1-BR-012, S1-BR-013

## E. Profile Baseline

22. **S1-022 - Implement Profile Baseline (Identity + Summary)**
    Outcome: Users can create/update identity/contact fields and summary with persistence.
    Rules: S1-BR-009, S1-BR-010

23. **S1-023 - Implement Profile Baseline Completion Indicator**
    Outcome: Profile page shows completion status for baseline fields and updates after save.
    Rules: S1-BR-009, S1-BR-011
