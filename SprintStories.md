# ATS for Candidates - Story Index and Integrity Rules (Spring 2026)

This file is the cross-sprint index and quality gate for story planning.

Detailed stories now live in sprint-specific files:

1. `Sprint1Stories.md`
2. `Sprint2Stories.md`
3. `Sprint3Stories.md`

## Why This Structure

Stories are still planned as one coherent backlog across the semester, then published into three sprint files.

This preserves two goals at the same time:

1. Sprint-specific working documents for implementation.
2. Whole-program review to prevent duplicate or conflicting stories.

## Story Ranges and Counts

1. Sprint 1 range: `S1-001` to `S1-023` (23 stories)
2. Sprint 2 range: `S2-001` to `S2-026` (26 stories)
3. Sprint 3 range: `S3-001` to `S3-022` (22 stories)
4. Total: 71 stories

## Cross-Sprint Integrity Rules

Use these rules whenever stories are added, removed, merged, or moved.

1. One story ID appears in one sprint file only.
2. Story IDs are immutable once published for a semester.
3. No two stories may have materially identical outcomes.
4. If a later sprint extends earlier sprint behavior, it must say "extend" or "expand" and reference the upstream story ID.
5. Contradictory outcomes are not allowed across sprint files.
6. Every story must have a testable outcome sentence.

## Conflict and Duplication Review Checklist

Run this review before finalizing any semester update:

1. Check ID uniqueness across all three sprint files.
2. Check for duplicate titles or near-duplicate outcomes.
3. Check for semantic conflicts across sprint outcomes.
4. Check that prerequisite stories appear in earlier or same sprint.
5. Check story counts in this index match the three sprint files.
6. Check that all story IDs are contiguous inside each sprint range.

## Change Workflow

1. Draft all proposed story changes across all three sprints first.
2. Run integrity checklist against all three files together.
3. Resolve duplicates/conflicts before publishing edits.
4. Update story counts and ranges in this file.
5. Only then export/update Jira import artifacts.

## Semester Transition Notes

If a future semester changes scope significantly:

1. Keep ID ranges stable where possible for easier historical comparison.
2. Prefer adding new IDs over repurposing old IDs with different intent.
3. Mark intentionally retired stories explicitly in the sprint file where they were removed.
