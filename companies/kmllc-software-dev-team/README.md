# KMLLC Software Dev Team

The engineering department for KMLLC: one **Head of Software** who manages one builder per active product. Builders ship branches, the Head of Software reviews everything, and **nothing deploys without Keith's thumbs-up.**

It is built from the *Build spec: Software Dev Team (Oct 21, 2026)* update on the [Paperclip AI Operating Team](https://linear.app/kmllc/project/paperclip-ai-operating-team-bcaf58d78426) project in Linear.

## How it works

1. **Builders** pull work from their Linear project, build it on a branch, verify it and open a PR (`builder-loop` skill).
2. The **Head of Software** reviews every hand-off for quality and against the project's goals, then sends it back or approves it (`software-review` skill).
3. Approved work goes to Keith as **one consolidated summary** (a single board approval). Nothing merges or deploys until he approves it.
4. The Head of Software escalates to Keith **only** for approvals, decisions, logins or access. Everything else is handled autonomously.
5. It runs around the clock: each builder has an hourly build loop (staggered across the hour), the Head of Software sweeps reviews hourly, and Keith gets a daily summary at 5:53am Pacific.

## Org chart

| Agent | Title | Reports to | Owns | Model |
| --- | --- | --- | --- | --- |
| `head-of-software` | Head of Software | Keith (board) | The team, reviews, the summary | Opus 5.5 |
| `coachub-builder` | Builder | Head of Software | CoacHub (high priority; repo TBD) | Sonnet 5.5 |
| `mps-app-builder` | Builder | Head of Software | MPS App / KM Trainer + MPS Backend | Sonnet 5.5 |
| `jiu-jitsu-studio-os-builder` | Builder | Head of Software | Jiu-Jitsu Studio OS | Sonnet 5.5 |
| `academyos-builder` | Builder | Head of Software | AcademyOS (generic shell only) | Sonnet 5.5 |
| `pdf-program-builder` | Builder | Head of Software | PDF Program Builder | Sonnet 5.5 |
| `hr-app-builder` | Builder | Head of Software | HR App (live group heart rate) | Sonnet 5.5 |
| `outlier-health-builder` | Builder | Head of Software | Outlier Health | Sonnet 5.5 |
| `coach-os-website-builder` | Builder | Head of Software | Coach OS Website | Sonnet 5.5 |
| `coach-os-sos-builder` | Builder | Head of Software | Coach OS Chassis, SOS Select 9U MVP, SOS Select Phase 2 | Sonnet 5.5 |
| `youth-performance-planner` | Planner | Head of Software | Youth Performance + Tutoring Facility (plan only) | Sonnet 5.5 |

All agents run on Claude Code (`claude_local`). They also use the `paperclip` skill.

**No builder (archived or scrapped):** Coach App Mold, Kin, Menger Finance, Fractional Fitness Ops site, MPS Brand OS, Jarvis, /am Debrief.

## Getting started

From the Paperclip repo on the Mac running Paperclip:

```sh
# Preview first
paperclipai company import companies/kmllc-software-dev-team --target existing -C <KMLLC company id> --dry-run

# Import into the existing KMLLC company
paperclipai company import companies/kmllc-software-dev-team --target existing -C <KMLLC company id>
```

Or use `--target new` to create a standalone company.

After import:

1. Agents and routines arrive **paused** (Paperclip's import safety default). Review them in the UI.
2. Add `GH_TOKEN` and `LINEAR_API_KEY` as Paperclip secrets for the agents.
3. Set monthly budgets. With 11 agents waking hourly, this is the main cost lever.
4. Resume the Head of Software first. Its "Stand up the team" task maps each builder to a repo and sends you one list of the access it still needs.
5. Resume the builders whose repos are ready.

## References

- [Agent Companies specification](https://agentcompanies.io/specification)
- [Paperclip](https://github.com/paperclipai/paperclip)
