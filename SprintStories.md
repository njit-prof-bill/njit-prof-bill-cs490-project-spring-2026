# ATS for Candidates - Story Backlog (Spring 2026)

This is the working backlog to implement the product defined in `spring-2026/ATS-PRD.md`.

I did not force this list to exactly 60 stories. I sized it for coverage and implementation risk. The backlog below contains **64 stories** across 3 sprints, including non-functional requirements and setup work for AI coding context.

## Story Format

Each story is written for Jira as:

- Story ID
- Title
- Outcome (what must be true when complete)

Teams can add sub-tasks under each story for implementation details.

---

## Sprint 1 - Dashboard Foundation, Auth, CI/CD, and Profile Baseline (23 stories)

### A. AI Context Documents (required before feature coding)

1. **S1-001 - Create Engineering Coding Standards Context Document**
   Outcome: Team publishes a context doc for AI and humans covering naming conventions, folder structure, linting/formatting rules, error handling style, and API response conventions.

2. **S1-002 - Create UI/UX Standards Context Document**
   Outcome: Team publishes a context doc defining chosen navigation model, dashboard interaction model, component usage rules, spacing/typography conventions, and consistency rules.

3. **S1-003 - Create Data and Security Guardrails Context Document**
   Outcome: Team publishes a context doc defining per-user data ownership, authorization checks, protected route behavior, and prohibited cross-user access patterns.

4. **S1-004 - Create AI Prompting and Review Context Document**
   Outcome: Team publishes a context doc for how AI-generated code is prompted, reviewed, tested, and approved before merge.

### B. Project and Delivery Baseline

5. **S1-005 - Initialize Monorepo/Project Structure**
   Outcome: Repo has stable frontend/backend structure, shared config, and documented run commands.

6. **S1-006 - Configure Linting and Formatting**
   Outcome: Lint/format tools are installed and runnable in CI; formatting is consistent across team contributions.

7. **S1-007 - Configure Unit Test Frameworks**
   Outcome: Unit test frameworks are set up for frontend and backend with one passing sample test per side.

8. **S1-008 - Configure CI Pipeline for Build and Test**
   Outcome: Pull requests run automated build and unit tests; failing checks block merge.

9. **S1-009 - Configure Environment Management**
   Outcome: Team has documented `.env` strategy for local/dev/prod without committing secrets.

### C. Authentication and User Ownership

10. **S1-010 - Implement User Self-Registration**
    Outcome: New users can create accounts through a registration form with validation and duplicate-email handling.

11. **S1-011 - Implement User Login and Session Handling**
    Outcome: Registered users can sign in and maintain authenticated session state.

12. **S1-012 - Implement Logout and Session Invalidation**
    Outcome: Users can sign out cleanly and protected data becomes inaccessible until next login.

13. **S1-013 - Implement Password Reset Workflow**
    Outcome: Users can request reset and set a new password through secure token flow.

14. **S1-014 - Enforce Route Protection**
    Outcome: Unauthenticated users are redirected from protected pages and APIs return correct auth errors.

15. **S1-015 - Enforce Per-User Data Authorization**
    Outcome: API/resource access is constrained to owner account; cross-user reads/writes are blocked.

### D. Dashboard Foundation and Job Baseline

16. **S1-016 - Build Global App Shell and Navigation**
    Outcome: App has consistent navigation and page layout for Dashboard, Profile, Document Library, and Settings.

17. **S1-017 - Implement Settings Page Baseline**
    Outcome: Settings page exists with baseline account settings structure and consistent app-shell behavior.

18. **S1-018 - Build Dashboard Home Skeleton**
    Outcome: Dashboard home page renders stable structure for job board workspace.

19. **S1-019 - Implement Basic Job Entity and Storage**
    Outcome: Job records can be created, stored, and retrieved with user ownership.

20. **S1-020 - Implement Basic Job Card Rendering**
    Outcome: Dashboard shows job cards with baseline fields (title, company, stage, activity date).

21. **S1-021 - Implement Basic Job Create/Edit Form**
    Outcome: Users can create and update job records from dashboard flow.

### E. Profile Baseline

22. **S1-022 - Implement Profile Baseline (Identity + Summary)**
    Outcome: Users can create/update identity/contact fields and summary with persistence.

23. **S1-023 - Implement Profile Baseline Completion Indicator**
    Outcome: Profile page shows completion status for baseline fields and updates after save.

---

## Sprint 2 - Dashboard Completion and Profile Completion (25 stories)

### A. Dashboard Core Workflow Completion

24. **S2-001 - Implement Job Search Across Dashboard**
    Outcome: Users can search jobs by title/company/keywords with immediate result updates.

25. **S2-002 - Implement Job Filter Controls**
    Outcome: Users can filter by stage, location, and deadline state.

26. **S2-003 - Implement Job Sorting Controls**
    Outcome: Users can sort by last activity, deadline, company, and created date.

27. **S2-004 - Implement Stage/Status Indicators on Job Cards**
    Outcome: Cards clearly display current stage and urgency cues.

28. **S2-005 - Implement Job Card to Job Detail Expansion Pattern**
    Outcome: Every job card opens to a consistent job detail UI pattern.

29. **S2-006 - Implement Job Detail Overview Section**
    Outcome: Users can edit core job data in a dedicated overview panel.

30. **S2-007 - Implement Job Deadline and Recruiter/Contact Notes Fields**
    Outcome: Job detail supports deadline field and recruiter/contact notes with persistence and edit support.

31. **S2-008 - Implement Pipeline Stage Transition Controls**
    Outcome: Users can change stage from detail view and dashboard controls.

32. **S2-009 - Persist Stage Transition Timestamps**
    Outcome: Stage changes are recorded with timestamps for timeline and analytics use.

33. **S2-010 - Implement Job Activity Timeline**
    Outcome: Timeline displays key events (applied, follow-up, interview, outcome).

34. **S2-011 - Implement Interview Tracking in Job Detail**
    Outcome: Users can add/edit interview events with round type, date/time, and notes.

35. **S2-012 - Implement Follow-Up and Reminder Tracking**
    Outcome: Users can create and manage follow-up tasks/reminders tied to a job.

36. **S2-013 - Implement Outcome Tracking Controls**
    Outcome: Users can record final outcome states and notes for each job.

37. **S2-014 - Implement Job Archive and Restore Workflow**
    Outcome: Users can archive and restore jobs while preserving full history and linked records.

38. **S2-015 - Implement Job Delete Workflow**
    Outcome: Users can delete jobs through a guarded workflow (confirmation and ownership checks).

### B. Profile Completion

39. **S2-016 - Implement Experience Section CRUD**
    Outcome: Users can add/edit/delete/reorder employment and project entries.

40. **S2-017 - Implement Education Section CRUD**
    Outcome: Users can add/edit/delete education records with full required fields.

41. **S2-018 - Implement Skills Section CRUD**
    Outcome: Users can add/edit/delete/reorder skills with optional category/proficiency.

42. **S2-019 - Implement Career Preferences Section CRUD**
    Outcome: Users can maintain target roles, location preferences, work mode, and salary preference.

43. **S2-020 - Implement Section-Level Save/Validation UX for Profile**
    Outcome: Each profile section saves independently with clear validation feedback.

### C. AI-Powered Job Context Workflows

44. **S2-021 - Implement AI Resume Draft from Profile + Job Context**
    Outcome: Users can generate a resume draft from job detail using profile data and job data.

45. **S2-022 - Implement AI Cover Letter Draft from Profile + Job Context**
    Outcome: Users can generate a cover letter draft from job detail using profile and job context.

46. **S2-023 - Implement AI Rewrite/Improve Actions for Draft Content**
    Outcome: Users can request AI rewrites/improvements and compare before saving.

47. **S2-024 - Implement Document Save from Job Context**
    Outcome: Generated/edited drafts can be saved as document records linked to job context.

### D. Dashboard Metrics and Quality

48. **S2-025 - Implement Dashboard Metrics (Stage Counts and Response Tracking)**
    Outcome: Dashboard displays baseline metrics computed from stored job/outcome data.

49. **S2-026 - Add Unit Tests for Job Workflow and Profile Completion Logic**
    Outcome: Core domain logic for stage transitions, timeline events, and profile completeness is unit-tested.

---
