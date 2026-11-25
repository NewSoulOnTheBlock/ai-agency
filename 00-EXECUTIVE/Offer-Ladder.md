# Offer Ladder

Status: v1, written in Loop 1 (2026-11-25). Owner: 00 Executive. Pricing detail is owned by 08 Finance from Loop 4 onward.

Pain-point IDs (P1–P7) are defined in [Positioning.md](Positioning.md). **Every deliverable below maps to at least one.** A deliverable that cannot be mapped does not belong on the ladder.

| Rung | Setup | Monthly | Division(s) | Who it is for |
|---|---|---|---|---|
| Audit | $499 one-time | — | Diagnostic | Anyone in or near the ICP. Entry point. |
| Essentials | $1,500 | $500 | Operations Engine (core) | Shops losing calls and appointments |
| Growth | $3,500 | $1,250 | Operations Engine + Sales Engine | Shops that also quote work and lose it to slow follow-up |
| Premium | $7,500+ | $2,500 | Both, integrated with their FSM tool | Larger shops that want it wired into the system they already run |

Each rung includes everything in the rung below it.

Prices are the plan's starting numbers. They have not been checked against delivery cost. Loop 4 (Unit-Economics.md) tests each for a 60% gross margin and sets floor prices **(assumption until then)**.

## Audit: $499 one-time

A written diagnostic plus a 30-minute walkthrough. Built from public evidence and a short owner interview. No system access needed.

| ID | Deliverable | Pain |
|---|---|---|
| A1 | Call-response test: we call during and after hours and record what happens | P1 |
| A2 | Web-form response test: we submit an inquiry and time the first reply | P1, P2 |
| A3 | Booking-path walkthrough: how a customer schedules, and whether they get a confirmation or reminder | P3 |
| A4 | Review profile snapshot: count, rating, recency, and whether the owner replies | P4 |
| A5 | Intake-to-invoice process map, from an owner interview: how a job moves from first call to dispatch to ticket to invoice | P5, P6 |
| A6 | Reporting gap list: which numbers the owner can and cannot produce today | P7 |
| A7 | Three recommended automations, ranked, each with complexity and an impact estimate that states its assumptions | P1, P2, P3, P4, P5, P6, P7 |

A7 draws its three recommendations from whichever pain points A1–A6 found. Template and research prompt are built in Loop 10.

## Essentials: $1,500 setup + $500/mo

Stops the most visible leaks: unanswered calls, forgotten appointments, unrequested reviews.

| ID | Deliverable | Pain |
|---|---|---|
| E1 | Missed-call text-back: a missed call triggers a text with a booking link in under 60 seconds | P1 |
| E2 | Web-inquiry instant reply: a form submission gets an immediate acknowledgement and booking link | P1 |
| E3 | Appointment confirmation plus 24-hour and 2-hour reminders | P3 |
| E4 | Review request after each completed job, sent to every customer, queued for approval | P4 |
| E5 | Monthly summary report: missed calls recovered, appointments booked, reminders sent, reviews requested | P7 |
| E6 | Failure alerts: if a step breaks, an admin is notified rather than a lead silently lost | P1, P3 |

## Growth: $3,500 setup + $1,250/mo

Adds the Sales Engine and gets job information off paper.

| ID | Deliverable | Pain |
|---|---|---|
| G1 | Lead capture and qualification: each lead scored 1–5 with a written reason, checked against service area | P2 |
| G2 | Hot-lead alert: urgent leads notify the owner or dispatcher immediately | P1, P2 |
| G3 | Quote drafting: a quote filled from the lead details, approved by a human before it is sent | P2 |
| G4 | Quote follow-up sequence: day 1, 3 and 7 drafts until booked or lost, stopping when the lead replies | P2 |
| G5 | No-show recovery: a missed appointment triggers a reschedule message | P3 |
| G6 | Technician assignment and "on the way" notices to the customer | P5 |
| G7 | Digital job ticket: a mobile completion form replaces the paper ticket and reaches the office the same day | P6 |
| G8 | Weekly pipeline report: leads, response time, quotes sent, quotes won | P7 |

## Premium: $7,500+ setup + $2,500/mo

Quoted per client. The same engines, connected to the client's own system of record and extended to edge cases.

| ID | Deliverable | Pain |
|---|---|---|
| X1 | Two-way sync with their FSM tool (ServiceTitan, Jobber, Housecall Pro) so jobs and customers are entered once | P5, P6 |
| X2 | After-hours intake with emergency routing: urgent requests reach the on-call tech under the client's emergency policy | P1, P5 |
| X3 | Double-booking and schedule-conflict checks before an appointment is confirmed | P5 |
| X4 | Dormant-quote reactivation: old unanswered quotes get a drafted re-engagement message, limited to existing contacts | P2 |
| X5 | Review reply drafts for new reviews, for owner approval | P4 |
| X6 | Owner dashboard: live view of leads, response time, bookings, no-shows and quote conversion | P7 |
| X7 | Multi-location or multi-trade routing rules | P5 |

The "+" in $7,500+ covers integration effort, which varies by FSM tool and plan tier. Some FSM plans restrict API access; that is confirmed during discovery, not assumed.

## Rules that apply to every rung

1. **Drafted, not sent, by default.** Quotes, follow-ups, review requests and review replies queue for human approval unless the client signs off on auto-send for a specific message.
2. **Consent first.** Texts go only to people who contacted the business or are existing customers. No cold texting (Positioning D4). Message wording and consent handling need legal review before a live client launch (see open issues in STATE.md).
3. **Every customer is asked for a review the same way.** No filtering by satisfaction (Positioning D5).
4. **Third-party costs** (SMS, voice, software seats) are passed through or capped by a usage allowance. Loop 4 sets the numbers.
5. **We promise behavior, not outcomes.** "A text goes out in under 60 seconds" is a commitment. "You will book more jobs" is not something we say.

## Traceability check

Coverage of each pain point across the ladder:

| Pain | Audit | Essentials | Growth | Premium |
|---|---|---|---|---|
| P1 Missed calls | A1, A2, A7 | E1, E2, E6 | G2 | X2 |
| P2 Slow quote follow-up | A2, A7 | — | G1, G2, G3, G4 | X4 |
| P3 No-shows | A3, A7 | E3, E6 | G5 | — |
| P4 Review neglect | A4, A7 | E4 | — | X5 |
| P5 Dispatch chaos | A5, A7 | — | G6 | X1, X2, X3, X7 |
| P6 Paper job tickets | A5, A7 | — | G7 | X1 |
| P7 No reporting | A6, A7 | E5 | G8 | X6 |

Every pain point is addressed by at least one paid rung above the Audit. P2, P5 and P6 are not addressed in Essentials; that gap is the reason to move a client to Growth.
