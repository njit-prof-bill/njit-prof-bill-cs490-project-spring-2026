# ATS for Candidates - Sprint 2 Stories (Spring 2026)

This is the Sprint 2 backlog slice from the unified planning pass.

Story writing format for Jira:

- Story ID
- Title
- Outcome (what must be true when complete)

Sprint 2 focus: Dashboard workflow completion, profile completion, AI job-context workflows, and baseline metrics/testing.

Total stories: 26

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
