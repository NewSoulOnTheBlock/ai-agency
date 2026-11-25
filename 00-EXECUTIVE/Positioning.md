# Positioning

Status: v1, written in Loop 1 (2026-11-25). Owner: 00 Executive.
Everything here is a starting position. Items marked **(assumption)** have not been tested against real prospects yet.

## One-line promise

> We are the outsourced operations department that makes sure no lead, call or job falls through the cracks.

Short form for headlines: **No lead, call or job falls through the cracks.**

## Ideal customer profile (ICP)

| Attribute | Target |
|---|---|
| Industry | Home services: HVAC, plumbing, roofing, electrical. Garage doors is an adjacent trade we accept. |
| Size | 5–50 employees |
| Revenue | $500K–$10M per year |
| Model | Local or regional, serves homeowners (residential or mixed residential/light commercial) |
| Buyer | Owner or general manager. The office manager or dispatcher is the daily user and the main influencer. |
| Lead flow | Inbound calls and web forms already arrive. We fix what happens to them; we do not generate demand. |
| Tooling | Uses, or is willing to adopt, a field-service or scheduling tool (ServiceTitan, Jobber, Housecall Pro or similar) and a phone system that can forward or report missed calls |
| Mindset | Knows work is leaking and wants it handled, not another piece of software to learn |

**Buying triggers (assumption):** the office manager quits or is overloaded, a busy season is coming (first heat wave, first freeze, storm season for roofers), the owner is still answering the phone at night, a bad review mentions "never called me back", or a new truck/tech was added without adding office staff.

## The top 7 pain points

Each has an ID. Offer-Ladder.md refers to these IDs, and every deliverable must map to at least one.

| ID | Pain point | What it looks like in the shop | What it costs them |
|---|---|---|---|
| P1 | **Missed calls** | Calls go to voicemail during jobs, lunch, after hours and weekends. Nobody calls back until the next day, if at all. | A homeowner with no heat calls the next company on the list. |
| P2 | **Slow quote follow-up** | Estimates go out and nobody chases them. Follow-up depends on someone remembering. | Quoted work is lost to whoever followed up first. |
| P3 | **No-show appointments** | The tech arrives and nobody is home, or the customer forgot. No confirmation or reminder was sent. | A wasted truck roll and an empty slot that could have been sold. |
| P4 | **Review neglect** | Happy customers are never asked for a review. Existing reviews go unanswered. | A thinner, older review profile than competitors who ask every time. |
| P5 | **Dispatch chaos** | Scheduling lives on a whiteboard, in texts and in someone's head. Double bookings, late arrivals, customers not told who is coming or when. | Overtime, callbacks, and angry "where is my tech" calls that tie up the phone. |
| P6 | **Paper job tickets** | Handwritten tickets get lost, are illegible, or reach the office days later. | Late invoicing, missing job history, and no record when a customer disputes the work. |
| P7 | **No reporting** | The owner cannot say how many leads came in, how fast they were answered, or what share of quotes closed. | Decisions made on gut feel. Leaks stay invisible. |

These seven are our working hypothesis about the market, drawn from the build plan. We have not yet validated their ranking with prospect interviews **(assumption)**. Loop 10 audits and Loop 13 discovery calls are where that gets tested.

## Starting divisions

We sell two divisions now. The other four are future upsells and are not offered yet.

| Division | Covers | Status |
|---|---|---|
| **Operations Engine** | P1, P3, P4, P5, P6, P7 | Active |
| **Sales Engine** | P1 (lead response), P2, P7 (pipeline) | Active |
| Customer Experience, Marketing, Knowledge, Intelligence | — | Phase 2, dormant until Loop 15 |

## Three proof points we can demonstrate

These are claims about **what the system does**, which a prospect can watch happen in a demo. They are not results we have achieved for a client. We have no clients and no results yet.

| # | Claim | How a prospect verifies it | Build status |
|---|---|---|---|
| 1 | A missed call or web inquiry gets a text reply with a booking link in under 60 seconds. | They call the demo number, let it ring out, and time the text on their own phone. | Not built. Loop 7. |
| 2 | Every quote gets a follow-up drafted on day 1, 3 and 7 until the lead books, replies or is marked lost. Nothing depends on someone remembering. | We submit a test lead and show the queued drafts and the stop-on-reply behavior. | Not built. Loop 8. |
| 3 | Every automated step is logged, so for any lead you can see what happened, when, and whether it failed. | We open the run log for the test lead from proof points 1 and 2. | Not built. Loops 6–8. |

**Rule:** until a proof point's build status reads "Built and tested", nobody describes it to a prospect as working. After that, we still say "here is what it does", never "here is what it will earn you".

## What we do not claim

- No revenue, booking-rate or ROI numbers. We have none.
- No testimonials, logos or case studies until a real client gives written permission.
- No industry statistics unless they carry a citation we have read ourselves.
- Impact estimates (in audits and proposals) always show their assumptions next to the number.

## Disqualifiers: who we won't sell to

| # | Disqualifier | Why |
|---|---|---|
| D1 | Fewer than 5 employees or under $500K revenue | Too little volume for the automation to pay for itself; the owner usually is the whole office. Offer the $499 Audit only. |
| D2 | More than 50 employees or over $10M revenue | They need enterprise integration and procurement we are not set up for yet. |
| D3 | No real inbound lead flow | We stop leaks. If nothing is coming in, they need marketing, which is a Phase 2 division. |
| D4 | Wants cold texts or automated calls to people who did not ask to be contacted | TCPA exposure for them and for us. Not negotiable. |
| D5 | Wants fake reviews, or to ask only happy customers for reviews (review gating) | Against Google's review policies and deceptive. We ask every customer the same way. |
| D6 | Wants a guaranteed revenue or lead-count outcome | We cannot control their pricing, close rate or service quality. We guarantee what the system does, not what the market does. |
| D7 | Will not grant the access needed (phone system, calendar, FSM tool) or has a franchise stack that forbids third-party integration | We cannot deliver without it. |
| D8 | No owner or GM sponsor; the office manager is expected to buy and run it alone | Projects without a decision-maker stall at the approval step. |
| D9 | Refuses any software for scheduling and intends to stay on paper only | Nothing for the automation to connect to. Revisit if they adopt a tool. |

The employee and revenue thresholds in D1 and D2 come from the ICP definition. The reasoning beside them is our judgement **(assumption)** and should be revisited once Loop 4 unit economics exist.
