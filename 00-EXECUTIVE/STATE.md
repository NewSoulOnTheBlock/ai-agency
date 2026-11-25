# STATE

The single source of truth for where the build is. Every loop reads this first and updates it last.

- Agency root: `~/dev/ai-agency`
- Loop prompts: `LOOP-PROMPTS.md`
- Last updated: 2026-11-25 (end of Loop 1)
- **Next loop: 2 (Workspace scaffold)**

## Loop status

Status values: `TODO`, `IN PROGRESS`, `BLOCKED`, `DONE`. A loop is DONE only when its exit check passes.

| Loop | Name | Status | Date | Outputs |
|---|---|---|---|---|
| 1 | Positioning and offer | DONE | 2026-11-25 | `00-EXECUTIVE/Positioning.md`, `00-EXECUTIVE/Offer-Ladder.md`, `00-EXECUTIVE/STATE.md`, `00-EXECUTIVE/Decision-Log.md` |
| 2 | Workspace scaffold | IN PROGRESS | 2026-11-25 | Done early, outside a loop run: folder tree with a README per folder, `.gitignore`, `git init`, root `README.md`. Still to do: `Master-Department-Instruction.md`, `Handoff-Template.md`, `Master-Task-Tracker.md`, any blueprint subfolders the script doesn't name, and the exit check. |
| 3 | Department prompts | TODO | | |
| 4 | Pricing, scope and contracts | TODO | | |
| 5 | Internal CRM (reuse Alfred) | TODO | | |
| 6 | Automation and data infrastructure | TODO | | |
| 7 | Demo 1: Operations Engine | TODO | | |
| 8 | Demo 2: Sales Engine | TODO | | |
| 9 | Onboarding, delivery and QA | TODO | | |
| 10 | The $499 audit product | TODO | | |
| 11 | Agency website | TODO | | |
| 12 | First 100 prospects | TODO | | |
| 13 | Outreach system | TODO | | |
| 14 | Close and deliver client #1 | TODO | | Repeats per active deal |
| 15 | Measure, report, expand | TODO | | Repeats monthly |

## Loop 1 exit check (2026-11-25)

| Check | Result |
|---|---|
| Every Offer-Ladder deliverable traces to a pain point in Positioning.md | PASS. 28 deliverables (A1–A7, E1–E6, G1–G8, X1–X7), all cite IDs within P1–P7. Verified by script. |
| Every pain point is covered by at least one paid rung above the Audit | PASS. P1–P7 all covered. |
| STATE.md shows Loop 1 DONE | PASS. |

## Key decisions so far

See `Decision-Log.md` for the full list. Decisions 006–008 were made by Claude and are waiting for owner review:

- 006: Essentials is Operations-only; Sales Engine starts at Growth.
- 007: Review requests go to every customer, no filtering.
- 008: Customer-facing messages are drafted for approval by default.

## Open issues

| # | Issue | Raised | Needed by |
|---|---|---|---|
| 1 | Ladder prices are unverified against delivery cost. Margin and floor prices are unknown. | Loop 1 | Loop 4 |
| 2 | The seven pain points and their ranking are a hypothesis, not validated with prospects. | Loop 1 | Loops 10, 13 |
| 3 | All three proof points are unbuilt. They cannot be shown or described as working yet. | Loop 1 | Loops 6–8 |
| 4 | SMS consent and wording (missed-call text-back, reminders, review requests) need review by a qualified attorney before any live client launch. Carrier registration for business texting (A2P 10DLC) also has to be done per client. | Loop 1 | Loop 7 (design), Loop 14 (live) |
| 5 | `~/dev/ai-agency` sits inside the home-directory git repo. Loop 2 runs `git init` here, which creates a nested repo. Checked 2026-11-25: the home repo does NOT ignore `dev/ai-agency`, so a `git add` from `~` could pick these files up. Loop 2 should add the ignore rule (owner's OK needed to edit `~/.gitignore`). | Loop 1 | Loop 2 |
| 6 | Target metro areas are not chosen. | Loop 1 | Loop 12 |
| 7 | Agency name, domain and business address are not recorded. The address is required for CAN-SPAM. | Loop 1 | Loops 11, 13 |

## Assumptions in force

- ICP thresholds (5–50 employees, $500K–$10M) come from the plan and are untested.
- Buying triggers in Positioning.md are our guess.
- Some FSM plans limit API access; Premium integration scope is confirmed per client in discovery.
