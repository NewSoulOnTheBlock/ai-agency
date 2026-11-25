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

> Token: **$AGENCY** — contract address: `PASTE-CONTRACT-ADDRESS-HERE`
>
> Only trust the address written in this file, in this repo. The token is a way to say thanks.
> It is not an investment, it gives you no rights to anything, and nothing here is financial advice.

## Why open source is the right way to do this

**The information was never the scarce part.** A $29.99 PDF sells you the feeling of progress.
What actually builds an agency is running the loops, making the calls and delivering the work.
Charging for the plan puts the price on the wrong thing.

**You can check it before you trust it.** A paid info product makes you pay first and judge
later. Here you can read every prompt, every assumption and every open issue before you spend a
minute on it. If it's bad, you'll know, and you lost nothing.

**It gets better when people use it.** A PDF is frozen on the day it's sold. A repo can be
forked for dentists, law firms or landscapers. Someone who finds a broken step can fix it and
send the fix back. Every person who runs a loop is testing it for the next person.

**It keeps me honest.** I can't hide untested prices or made-up results behind a paywall. The
"Honest status" section below exists because anyone can open `00-EXECUTIVE/STATE.md` and see
exactly how far this has really got.

**AI changed the maths.** A model can write a plan like this in an afternoon. Selling access to
text that a machine can regenerate is a business with a short life. Giving the text away and
earning from the work, the reputation and the people who chose to back it will last longer.

**You pay after the value, not before.** That's what the token is for. Nobody is charged at the
door. If the script helped you, $AGENCY is how you say so. If it didn't, you owe nothing.

## How to use the script

### What you need

- [Claude Code](https://claude.com/claude-code) installed and signed in.
- Git.
- Nothing else to start. Later loops ask for accounts (n8n, a database, an SMS sandbox, Vercel),
  and each one stops and shows you the cost before it sets anything up.

### Set up

```
git clone https://github.com/NewSoulOnTheBlock/ai-agency.git ~/dev/ai-agency
cd ~/dev/ai-agency
claude
```

The prompts assume the folder is `~/dev/ai-agency`. If you put it somewhere else, find and
replace that path in `LOOP-PROMPTS.md`.

### Run a loop

Paste this runner prompt. It is the only prompt you need:

```
Read ~/dev/ai-agency/00-EXECUTIVE/STATE.md. Find the first loop whose status is not DONE,
open ~/dev/ai-agency/LOOP-PROMPTS.md, and run that loop's prompt exactly. At the end, run
its exit check, update STATE.md (status, files produced, decisions, open issues, next loop),
and append decisions to 00-EXECUTIVE/Decision-Log.md. Stop after one loop.
```

Each run does the same four things:

1. Reads `00-EXECUTIVE/STATE.md` to find out where the build is.
2. Does the work for the next unfinished loop and writes the files that loop names.
3. Runs that loop's exit check, a concrete test such as "the tenant isolation test passes
   against a real database".
4. Updates `STATE.md` and the decision log, then stops.

### The rules that make it work

- **One loop per session.** Type `/clear` before the next one. `STATE.md` carries the memory
  between sessions, so the conversation doesn't have to.
- **A loop is done only when its exit check passes.** If it fails, the runner prompt repeats
  the same loop next time. Don't mark it done by hand to move on.
- **Read the report.** Every loop ends with: objective, what it did, files produced, exit check
  results, open issues, next loop. The open issues are where the real decisions are.
- **You do the outward-facing parts.** Sending email, publishing, charging money and calling
  people are drafted, never sent. You review them and send them yourself.
- **Some loops wait for you.** Loop 5 (which CRM), Loop 6 (which hosting, and its cost) and
  Loop 12 (which cities to prospect in) stop and ask before they go further.
- **Loops 14 and 15 repeat.** Loop 14 runs for each active deal or client. Loop 15 runs monthly.

### Make it yours

- **Start from zero:** delete the four files in `00-EXECUTIVE/` (keep the README) and run the
  runner prompt. Loop 1 will write your own positioning and offer.
- **Change the industry:** edit the industry line and the Loop 1 context in `LOOP-PROMPTS.md`
  (customer type, company size, pain points), then start from zero. The later loops build on
  whatever Loop 1 produces.
- **Change the prices:** edit the offer ladder in Loop 1. Loop 4 checks the margins and flags
  any package under 60%.
- **Swap the tools:** Loop 5 assumes a CRM I already had (Alfred). Use your own, or HubSpot's
  free CRM. n8n, Supabase, Calendly and Vercel can all be replaced the same way.

## What's in here

| Path | What it is |
|---|---|
| `LOOP-PROMPTS.md` | The script. All 15 loop prompts, the runner prompt and the rules. |
| `agencyscript.md` | The same script under its original name. |
| `00-EXECUTIVE/` | Loop 1's real output: positioning, offer ladder, state tracker, decision log. |
| `01-SALES/` … `09-CLIENTS/` | The folder outline the script asks for. Each folder has a README saying what goes there and who owns it. |
| `LICENSE` | MIT. |

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

- This is a plan, not a proven business. Loop 1 is done and Loop 2 is partly done. Loops 3–15
  are prompts that have not been run yet.
- The prices, margins and pain points are untested assumptions. `00-EXECUTIVE/STATE.md` lists the open issues.
- There are no results, testimonials or revenue numbers here, because there aren't any yet.
- Contract and SMS-consent material the loops produce are drafts. Have a qualified attorney
  review them before you use them with a real client.

## License

MIT. See [LICENSE](LICENSE). Use it, change it, sell what you build with it. Just keep the
copyright notice in copies of this repo.

## Rules the script enforces

- Never fabricate data, testimonials or results. Label assumptions as assumptions.
- Client data lives only in `09-CLIENTS/CLIENT-00N/`, which git ignores.
- Secrets go in `.env`, never in a commit.
