---
name: merge-a-pr
description: Use when the user asks to read a pull request's checks, or to merge it.
---

# Merge a pull request

## Reading checks

Read the pull request's status from the app, and its checks from the host. Show a table with each check, its result and its time. Say whether it can merge cleanly. Never merge with failing checks.

## Merging

Only after the user says yes.

- Squash merge, with the pull request's title as the commit title.
- The body lists the branch's commit messages, followed by the co-author line.
- Delete the branch, update the local main branch, and confirm that the issue closed.

## Afterwards

Update the progress notes, and say what comes next.
