# Decision Log

Append-only. Newest at the bottom. One row per decision. If a decision is reversed, add a new row that references the old one; do not edit history.

| # | Date | Loop | Decision | Reason | Decided by |
|---|---|---|---|---|---|
| 001 | 2026-11-25 | 1 | Industry is home services: HVAC, plumbing, roofing, electrical. Garage doors accepted as adjacent. | Set by the build plan. | Owner (plan) |
| 002 | 2026-11-25 | 1 | Launch with two divisions only: Operations Engine and Sales Engine. The other four are Phase 2 upsells. | Set by the build plan; keeps delivery scope small until there are paying clients. | Owner (plan) |
| 003 | 2026-11-25 | 1 | Ladder prices: Audit $499; Essentials $1,500 + $500/mo; Growth $3,500 + $1,250/mo; Premium $7,500+ + $2,500/mo. | Set by the build plan. Unverified against delivery cost until Loop 4. | Owner (plan) |
| 004 | 2026-11-25 | 1 | Pain points get stable IDs P1–P7 and every deliverable carries a `Pain` column. | Makes the "every deliverable traces to a pain point" check scriptable and repeatable in later loops. | Claude (Loop 1) |
| 005 | 2026-11-25 | 1 | Proof points are statements of system behavior a prospect can watch in a demo, each with a build status. None may be described as working until built and tested. | We have no client results; behavior is the only thing we can honestly demonstrate. | Claude (Loop 1) |
| 006 | 2026-11-25 | 1 | Essentials is Operations-only. Sales Engine deliverables start at Growth. | Gives a clear reason to upgrade and keeps the entry package small. Open to change in Loop 4 if margins say otherwise. | Claude (Loop 1), pending owner review |
| 007 | 2026-11-25 | 1 | Review requests go to every customer; no satisfaction filtering. Wanting otherwise is a disqualifier (D5). | Review gating breaks Google's review policies and is deceptive. | Claude (Loop 1), pending owner review |
| 008 | 2026-11-25 | 1 | Customer-facing messages are drafted for human approval by default across all rungs. | Matches the plan's "drafted, never sent" rule and limits the damage of a bad automated message. | Claude (Loop 1), pending owner review |
