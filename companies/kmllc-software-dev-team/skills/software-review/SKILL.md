---
name: software-review
description: How the KMLLC Head of Software reviews builder hand-offs and batches approved work into a single approval for Keith.
---

# Software review

## Review each hand-off

Check, in order:

1. **Goal fit.** Does it move the Linear project's current goal forward? Is it inside the project's scope line?
2. **Correctness.** Read the diff. Look for real bugs: wrong logic, unhandled errors, broken edge cases and regressions.
3. **Safety.** No secrets committed. Auth, Firestore/database rules, data migrations and payment code get extra scrutiny. Public forms must not expose submissions.
4. **Verification.** The builder ran the repo's checks and says how. Tests cover the changed behaviour.
5. **Size.** It's small enough to understand. Ask for a split if it isn't.

## Decide

- **Send back** with numbered, specific fixes. Reassign to the builder and set the issue to `in_progress`.
- **Approve** by adding the PR to the pending summary for Keith. Don't merge or deploy it.

## Batch for Keith

Collect approved work into one `request_board_approval` per summary:

- one line per PR: project, what it does, risk level, link
- anything that needs a decision, login or access, as a separate short list
- nothing else

When Keith approves, tell each builder exactly which PRs to merge or deploy. When he rejects or asks for changes, send the work back with his notes.
