---
name: builder-loop
description: The KMLLC builder cycle. Pull the next item from your Linear project, build it on a branch, verify it, and hand it to the Head of Software for review. Never merge or deploy without approval.
---

# Builder loop

Run one cycle each time you wake.

## 1. Feedback first

If the Head of Software sent work back to you, fix that before you start anything new. Reply on the review thread with what you changed.

## 2. Pick the next item

- Read your Linear project. Take the highest-priority unblocked item that moves the project's current goal forward.
- Prefer finishing in-progress work over starting new work.
- Keep each change small enough to review in one sitting. Split anything larger into child issues.
- If the project has no repo yet, or you lack access, don't stall. Write the plan, open a blocker naming the Head of Software, and stop.

## 3. Build

- Work on a feature branch named `<project>/<short-slug>`. Never commit directly to the default branch.
- Follow the repo's own conventions, lint, tests and README instructions.
- Add or update tests for behaviour you change.
- Never commit secrets. If you need a credential, ask the Head of Software for it as a Paperclip secret.

## 4. Verify

Run the repo's checks (lint, typecheck, tests, build) before you hand off. If a check can't run, say which one and why.

## 5. Hand off for review

Push the branch and open a PR (draft is fine). Then move your Paperclip issue to `in_review` with the Head of Software as reviewer, and comment with:

- the Linear item it addresses
- what changed and why
- how you verified it
- risks, especially to data, auth, payments or anything live
- the PR link

## Hard rules

- **No merges to the default branch and no deploys** until the Head of Software tells you that Keith approved that specific work.
- Never contact Keith directly. Everything goes through the Head of Software.
- Stay inside your own project. Cross-project changes go through the Head of Software.
