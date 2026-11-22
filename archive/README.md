# Archive

This directory stores warm historical records that are no longer part of the active project state.

## What belongs here

- Completed task summaries, including final task status, artifact trust labels, verification evidence, and deliverable links.
- Important HANDOFF Blocks that preserve review findings, decisions, and unresolved issues.
- Milestone summaries when they help explain why a project decision was made.

## Suggested organization

- Monthly or milestone task summaries, for example `2026-11-tasks.md`.
- Important handoffs under `handoffs/`, using stable handoff IDs in filenames where practical.

## Archiving rules

1. Keep STATE.md focused on the current stage, active tasks/claims, and key blockers.
2. Once a task is completed and its handoff is complete, remove it from STATE.md during the next state update and place its summary here.
3. Preserve the task ID and links to related artifacts and handoffs.
4. Keep the final trust label for each important deliverable or conclusion, with its evidence.
5. Do not copy secrets or private data into this public repository.

Git commit history remains the cold audit trail for file-level changes; do not create a duplicate manual change log.
