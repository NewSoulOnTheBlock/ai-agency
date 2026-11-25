# AI Business Operations Agency: the 15-Loop Build Plan

A complete, step-by-step script for building an AI operations agency that serves home-services
companies (HVAC, plumbing, roofing, electrical, garage doors). You paste one prompt per session
into Claude Code, and each loop builds one piece of the business: positioning, pricing,
contracts, CRM, infrastructure, two working demos, onboarding, a paid audit product, a website,
a prospect list, an outreach system, client delivery, and monthly reporting.

## Why this is free

Most people would take this, wrap it in a landing page, and charge you $29.99 for an info product.

I'm not doing that. I'm embracing the new open source: I'm tokenizing it and giving it away for free.

Read it, fork it, run it, change the industry, build your own agency with it. No email gate,
no upsell, no course.

**If it was useful or valuable to you, buy the token. Thanks.**

> Token: `TICKER` — contract address: `PASTE-CONTRACT-ADDRESS-HERE`
>
> Only trust the address written in this file, in this repo. The token is a way to say thanks.
> It is not an investment, it gives you no rights to anything, and nothing here is financial advice.

## What's in here

| Path | What it is |
|---|---|
| `LOOP-PROMPTS.md` | The script. All 15 loop prompts, the runner prompt and the rules. |
| `agencyscript.md` | The same script under its original name. |
| `00-EXECUTIVE/` | Loop 1's real output: positioning, offer ladder, state tracker, decision log. |
| `01-SALES/` … `09-CLIENTS/` | The folder outline the script asks for. Each folder has a README saying what goes there and who owns it. |

## How to use it

1. Clone the repo to `~/dev/ai-agency` (or change that path in the prompts).
2. Open Claude Code in the folder and paste the runner prompt from the top of `LOOP-PROMPTS.md`.
3. Run one loop per session, and `/clear` between loops.
4. A loop is done only when its exit check passes. If it fails, the next run repeats that loop.
5. Anything outward-facing (sending email, publishing, charging money, calling) is drafted,
   never sent. You do those yourself.

To start from zero instead of from my answers, delete the four files in `00-EXECUTIVE/` and run Loop 1.

## The 15 loops

| # | Loop | Builds |
|---|---|---|
| 1 | Positioning and offer | Ideal customer, pain points, promise, offer ladder |
| 2 | Workspace scaffold | The folder tree, shared operating instruction, handoff template |
| 3 | Department prompts | Instructions for 10 Claude Projects, one per department |
| 4 | Pricing, scope and contracts | Price book, unit economics, SOW and change-order drafts |
| 5 | Internal CRM | A pipeline that matches the agency's client journey |
| 6 | Automation and data infrastructure | n8n hosting, multi-tenant schema, tenant isolation tests |
| 7 | Demo 1: Operations Engine | Missed call → text-back → booked job → review request |
| 8 | Demo 2: Sales Engine | Lead → qualification → quote draft → follow-up |
| 9 | Onboarding, delivery and QA | Client template, SOPs, QA checklists, hours log |
| 10 | The $499 audit product | Audit template, research prompt, one sample audit |
| 11 | Agency website | A static site, deployed as a preview |
| 12 | First 100 prospects | A sourced prospect database |
| 13 | Outreach system | Email sequence, call scripts, compliance checklist, 10 drafts |
| 14 | Close and deliver client #1 | Proposal, onboarding, implementation, handover |
| 15 | Measure, report, expand | KPI scorecard, client reports, the next division to open |

## Honest status

- This is a plan, not a proven business. Loop 1 is done. Loops 2–15 are prompts that have not been run yet.
- The prices, margins and pain points are untested assumptions. `00-EXECUTIVE/STATE.md` lists the open issues.
- There are no results, testimonials or revenue numbers here, because there aren't any yet.
- Loop 5 assumes a CRM I already had (Alfred). Swap in your own, or HubSpot's free CRM.
- Contract and SMS-consent material the loops produce are drafts. Have a qualified attorney
  review them before you use them with a real client.

## License

MIT. See [LICENSE](LICENSE). Use it, change it, sell what you build with it. Just keep the
copyright notice in copies of this repo.

## Rules the script enforces

- Never fabricate data, testimonials or results. Label assumptions as assumptions.
- Client data lives only in `09-CLIENTS/CLIENT-00N/`, which git ignores.
- Secrets go in `.env`, never in a commit.
