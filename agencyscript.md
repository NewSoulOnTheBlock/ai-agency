# AI Business Operations Agency: 15-Loop Build Plan

Industry: **home services** (HVAC, plumbing, roofing, electrical, garage doors).
Agency root: `~/dev/ai-agency` (holds the AI-AGENCY folder tree from the blueprint).

## How to run the loops

1. Run one loop per session. `/clear` between loops.
2. Every loop starts by reading `00-EXECUTIVE/STATE.md` and ends by updating it.
3. A loop is **done** only when its exit check passes. If it doesn't, the next run repeats the same loop.
4. Anything outward-facing (sending email, publishing, charging money, calling) is **drafted, never sent**. You do those yourself.

### Runner prompt (paste this to run whatever is next)

```
Read ~/dev/ai-agency/00-EXECUTIVE/STATE.md. Find the first loop whose status is not DONE,
open ~/dev/ai-agency/LOOP-PROMPTS.md, and run that loop's prompt exactly. At the end, run
its exit check, update STATE.md (status, files produced, decisions, open issues, next loop),
and append decisions to 00-EXECUTIVE/Decision-Log.md. Stop after one loop.
```

### Standard footer (already included in every loop below)

> Report back in this order: objective, what you did, files produced, exit check results, open issues, next loop. Never fabricate data, testimonials or results. Label assumptions as assumptions.

---

## Loop 1: Positioning and offer

```
LOOP 1 of 15: POSITIONING AND OFFER. Agency root: ~/dev/ai-agency (create it if missing).

Context: We're an AI business operations agency for home-services companies (HVAC, plumbing,
roofing, electrical), 5–50 employees, $500K–$10M revenue. Promise: "We are the outsourced
operations department that makes sure no lead, call or job falls through the cracks."
We start with two divisions: Operations Engine and Sales Engine. The other four come later as upsells.

Do:
1. Write 00-EXECUTIVE/Positioning.md: ideal customer profile, the top 7 home-services pain points
   (missed calls, slow quote follow-up, no-show appointments, review neglect, dispatch chaos,
   paper job tickets, no reporting), a one-line promise, three proof-point claims we can
   demonstrate (not results we have achieved), and disqualifiers (who we won't sell to).
2. Write 00-EXECUTIVE/Offer-Ladder.md: $499 Audit → Essentials ($1,500 + $500/mo) →
   Growth ($3,500 + $1,250/mo) → Premium ($7,500+ + $2,500/mo), each mapped to concrete
   home-services deliverables (e.g. "missed-call text-back", "quote follow-up sequence").
3. Create 00-EXECUTIVE/STATE.md with a table of loops 1–15 (status, date, outputs) and
   00-EXECUTIVE/Decision-Log.md.

Exit check: every Offer-Ladder deliverable traces back to a pain point in Positioning.md,
and STATE.md shows Loop 1 DONE.
Report: objective, actions, files, exit check, open issues, next loop. No fabricated claims.
```

## Loop 2: Agency workspace scaffold

```
LOOP 2 of 15: WORKSPACE SCAFFOLD. Read ~/dev/ai-agency/00-EXECUTIVE/STATE.md first.

Do:
1. Create the full tree: 00-EXECUTIVE … 09-CLIENTS/CLIENT-TEMPLATE with the subfolders from the
   blueprint (Proposals/, SOP-Library/, Automation-Blueprints/, etc.). Put a README.md in each
   that says what goes there and who owns it.
2. Write 00-EXECUTIVE/Master-Department-Instruction.md (the shared operating instruction:
   deliver tangible work, document decisions, never claim unfinished work is done, escalate
   pricing/legal/sensitive calls, and prepare explicit handoff docs because Projects don't share memory).
3. Write 00-EXECUTIVE/Handoff-Template.md and 00-EXECUTIVE/Master-Task-Tracker.md (a markdown
   table, not .xlsx).
4. git init the agency root and add a .gitignore that excludes 09-CLIENTS/*/ (everything except
   CLIENT-TEMPLATE) so client data is never committed.

Exit check: the tree exists, every folder has a README, git status shows client folders ignored.
Update STATE.md. Report in the standard order.
```

## Loop 3: Department prompts (10 Claude Projects)

```
LOOP 3 of 15: DEPARTMENT PROMPTS. Read STATE.md, Positioning.md, Offer-Ladder.md and
Master-Department-Instruction.md first.

Do: For each of the 10 departments (00 Executive, 01 Sales, 02 Marketing, 03 Operations,
04 CX, 05 Knowledge, 06 Intelligence, 07 Development, 08 Finance, 09 Delivery & QA) write
<dept-folder>/PROJECT-INSTRUCTIONS.md containing:
- role and mission, specific to home services
- the inputs it expects and the outputs it must produce (file names + templates)
- what it may NOT do (e.g. Sales can't set prices below the floor in 08-FINANCE)
- the handoff targets (which department receives each output)
- a starter "first 3 tasks" list
Mark 02/04/05/06 as "PHASE 2 — dormant until Loop 15".
Also write 00-EXECUTIVE/Project-Setup-Guide.md: the click steps for creating each Claude
Project and which files to upload as its knowledge.

Exit check: 10 files exist, each names its handoff targets, and no two departments own the
same output. Update STATE.md. Report in the standard order.
```

## Loop 4: Pricing, scope and contracts

```
LOOP 4 of 15: PRICING AND CONTRACTS. Read STATE.md, Offer-Ladder.md, 08-FINANCE/PROJECT-INSTRUCTIONS.md.

Do:
1. 08-FINANCE/Pricing/Price-Book.md: each package with included workflows, connected
   platforms, usage allowance (SMS/voice/API), revision limits, support SLA, and the
   out-of-scope hourly rate. Include a floor price per package.
2. 08-FINANCE/Financial-Models/Unit-Economics.md: per package, estimated delivery hours at
   setup and per month, tool cost pass-through, gross margin. Flag any package under 60%.
3. 08-FINANCE/Contracts/: SOW template, change-order template, and a list of MSA clauses
   (data ownership, third-party costs, liability cap, termination, data processing).
   Put a banner at the top: "DRAFT — must be reviewed by a qualified attorney before use."
4. 08-FINANCE/Pricing/Scope-Rules.md: what counts as out of scope, with 10 home-services examples.

Exit check: every package shows margin ≥60%, or the shortfall is flagged with a fix.
Contract drafts carry the attorney banner. Update STATE.md. Report in the standard order.
```

## Loop 5: Internal CRM (reuse Alfred)

```
LOOP 5 of 15: INTERNAL CRM. Read STATE.md first. Existing asset: Alfred Client Studio,
source at ~/alfred-crm, deployed on Render (<your-render-service-id>). Its free
Postgres was due to expire around 2026-09-09.

Do:
1. Check the real status: does the Render service respond, and does the DB still exist? Report
   what you find. Do not guess.
2. Recommend one of: (a) revive Alfred on a paid/permanent DB, (b) move Alfred's DB to Neon
   free tier, (c) adopt HubSpot free CRM. Give the cost and effort of each. Wait for my choice
   before changing infrastructure.
3. After I choose: make sure the pipeline stages match the agency journey (Prospect → Audit
   Sent → Discovery → Demo → Proposal → Won/Lost → Onboarding → Live), and add fields for
   trade, service area, review count, website, and audit link.
4. Document in 01-SALES/CRM-Guide.md.

Exit check: I can create a prospect, move it through every stage, and export it. Old
credentials are rotated (including the old APP_PASSWORD). Update STATE.md. Report in the standard order.
```

## Loop 6: Automation and data infrastructure

```
LOOP 6 of 15: INFRASTRUCTURE. Read STATE.md and 07-DEVELOPMENT/PROJECT-INSTRUCTIONS.md.

Do:
1. Pick hosting for n8n (n8n Cloud vs self-host on Fly.io/Render). Show the cost, then wait for my OK.
2. Database: a Supabase (or Neon, if Loop 5 chose it) multi-tenant schema in
   07-DEVELOPMENT/Source-Code/schema.sql with tables clients, contacts, leads, jobs,
   appointments, messages, automation_runs, audit_log. Every table has client_id. Use Row
   Level Security policies so a client's users only ever see their own client_id.
3. Write tests (SQL or script) proving tenant A cannot read tenant B's rows.
4. 07-DEVELOPMENT/Integrations/Credential-Policy.md: one n8n credential set per client,
   least privilege, where secrets live, rotation.
5. Never commit secrets. Use .env with .env.example.

Exit check: the RLS isolation test passes against a real database (show the output), and n8n
is reachable. Update STATE.md. Report in the standard order.
```

## Loop 7: Demo 1, Operations Engine (missed-call → booked job)

```
LOOP 7 of 15: OPERATIONS DEMO. Read STATE.md, schema.sql, Credential-Policy.md.

Build for a fictional "Demo Heating & Air" (clearly labeled DEMO, fake data only):
1. Missed-call text-back: a missed call or web inquiry triggers an SMS within 60 seconds with
   a booking link (use a sandbox/test SMS number).
2. Booking: Calendly (or Cal.com) slot → appointment row → confirmation + 24h and 2h reminders.
3. Post-job: a job marked complete triggers a review-request message draft (queued for human
   approval, not auto-sent).
4. Every step writes to automation_runs and audit_log. Failures alert an admin channel.
5. Export the n8n workflows to 03-OPERATIONS/Automation-Blueprints/ and write a 1-page SOP plus
   a 3-minute demo script.

Exit check: run the flow end to end with test data and show the logs. Also test 3 failure
cases (bad phone number, double booking, SMS provider down). Update STATE.md. Report in the standard order.
```

## Loop 8: Demo 2, Sales Engine (lead → quote → follow-up)

```
LOOP 8 of 15: SALES DEMO. Read STATE.md and the Loop 7 blueprints (reuse that infra).

Build for the same DEMO company:
1. Lead capture form (Tally or a native form) → leads row → enrichment (trade, urgency, zip
   in service area?).
2. Claude qualification: score 1–5 with a written reason; hot leads notify the owner instantly.
3. Quote draft: Claude fills a quote template from the lead details. A human approves it
   before it's sent.
4. Follow-up sequence: day 1/3/7 drafts until booked or marked lost. It stops when the lead replies.
5. A weekly pipeline summary to the owner (leads, response time, quotes, won).
6. Save to 01-SALES/Automation-Blueprints/ with an SOP and a demo script that runs alongside Loop 7.

Exit check: 5 test leads (hot, cold, out-of-area, spam, duplicate) are each handled correctly,
with logs shown. Update STATE.md. Report in the standard order.
```

## Loop 9: Onboarding, delivery and QA system

```
LOOP 9 of 15: DELIVERY SYSTEM. Read STATE.md and 09-DELIVERY & QA PROJECT-INSTRUCTIONS.md.

Do:
1. 09-CLIENTS/CLIENT-TEMPLATE/: a welcome packet, intake questionnaire (home-services specific:
   FSM software like ServiceTitan/Jobber/Housecall Pro, phone system, service area, hours,
   emergency policy), access request checklist (least privilege), kickoff agenda.
2. SOPs in 03-OPERATIONS/SOP-Library/: Implementation (document current process → map →
   build → test incl. edge cases → client approval → deploy → monitor → document), Handover,
   and Monthly Management.
3. QA acceptance checklists per division (from blueprint Part 7) in 09-…/QA/.
4. A delivery-hours log template per client (the biggest hidden cost).
5. A script, new-client.sh (or .ps1), that copies CLIENT-TEMPLATE to CLIENT-00N.

Exit check: a dry run with a fake client creates the folder, and every SOP step has an owner
and a checklist. Update STATE.md. Report in the standard order.
```

## Loop 10: The $499 audit product

```
LOOP 10 of 15: AUDIT OFFER. Read STATE.md, Positioning.md, Offer-Ladder.md.

Do:
1. 01-SALES/Audit/Audit-Template.md: business overview, acquisition channels, website and
   Google Business Profile observations, response-time test results, review profile, three
   recommended automations, complexity, estimated impact WITH stated assumptions, next steps.
   It has two clearly separated sections: "Observed (public evidence)" and "Hypotheses (need discovery)".
2. 01-SALES/Audit/Audit-Research-Prompt.md: a reusable prompt that turns a business's public
   footprint (site, GBP, reviews, a test form submission, a timed web-form response) into a
   filled audit. It never invents internal facts.
3. Two variants: a free 1-page "mini audit" for outreach, and the paid $499 full audit with
   a 30-minute walkthrough.
4. Run it once on a real public home-services business near me (I'll name one, or you pick
   one from a public listing) as a sample. Keep it internal and don't send it.

Exit check: every claim in the sample is tagged Observed (with source) or Hypothesis.
Update STATE.md. Report in the standard order.
```

## Loop 11: Agency website

```
LOOP 11 of 15: WEBSITE. Read STATE.md, Positioning.md, Offer-Ladder.md, the Loop 7–8 demo scripts.

Build a fast static site (deploy target: Vercel), with pages: Home (promise + the
missed-call problem + CTA), Services (Operations, Sales; "coming soon" for the rest), Pricing
(Audit/Essentials/Growth, with Premium "by quote"), How It Works (the client journey),
Demo (short embedded walkthrough videos or GIFs from Loops 7–8), Book an Audit (form → CRM
from Loop 5), Privacy, Terms (marked draft).
Rules: no fake testimonials, logos or stats. Use "what we build" proof, not "results we got".
Mobile-first, Lighthouse ≥90.
Deploy a PREVIEW only. I'll promote to production and connect the domain myself.

Exit check: the audit form submission lands in the CRM, Lighthouse scores are reported, and
the preview URL is given. Update STATE.md. Report in the standard order.
```

## Loop 12: First 100 prospects

```
LOOP 12 of 15: PROSPECT RESEARCH. Read STATE.md, Positioning.md (ICP + disqualifiers), CRM-Guide.md.

Do:
1. Pick 1–2 metro areas (ask me if STATE.md doesn't name them).
2. Build 01-SALES/Prospect-Database.csv of 100 home-services businesses from public sources
   (Google Maps listings, business websites, state contractor license lookups). Respect site
   terms. No scraping behind logins. Business contact info only.
3. Fields: name, trade, city, website, phone, public email (if listed), review count/rating,
   has online booking? has chat? after-hours answering? (from public evidence), fit score 1–5
   with a reason, and a source URL for each fact.
4. Import the top 50 into the CRM at stage "Prospect".
5. Run the mini audit (Loop 10) on the top 10.

Exit check: 100 rows, every fact has a source, nothing invented, and the top 50 are in the CRM.
Update STATE.md. Report in the standard order.
```

## Loop 13: Outreach system

```
LOOP 13 of 15: OUTREACH. Read STATE.md, Prospect-Database.csv, the mini audits, Positioning.md.

Do:
1. 01-SALES/Outreach-Templates.md: a 4-touch cold email sequence (each leads with one
   observed, specific finding from their mini audit), a phone opener, a voicemail, and a
   LinkedIn note. No false urgency and no fake personalization.
2. 01-SALES/Sales-Scripts.md: the discovery-call script (reuse Alfred's 31 questions,
   adapted for home services), a demo-call script built on Loops 7–8, and objection handling
   ("we tried software", "too expensive", "my office manager does it").
3. 01-SALES/Compliance.md: CAN-SPAM requirements (physical address, opt-out, honest
   subject), TCPA rules for calls and texts (no automated texts or calls to prospects without
   consent), a suppression list process, and sending-domain setup (separate domain, SPF/DKIM/DMARC, warm-up).
4. Draft personalized first-touch emails for the top 10 prospects as files in
   01-SALES/Outreach/Drafts/. DO NOT SEND. I send them myself.
5. Set up the weekly activity tracker (50 researched / 50 touches / 50 follow-ups / 5 calls / 3 demos / 3 proposals).

Exit check: 10 drafts exist, each cites its audit finding, and each passes the Compliance.md
checklist. Update STATE.md. Report in the standard order.
```

## Loop 14: Close and deliver client #1

```
LOOP 14 of 15: FIRST CLIENT. Read STATE.md and the CRM. This loop repeats each time there's an
active deal or a client in implementation.

Depending on the deal stage in the CRM:
- Discovery done → write a proposal in 01-SALES/Proposals/ from the Price-Book plus a filled SOW
  (respect the floor price, flag anything out of scope). I approve the pricing.
- Won → run new-client script, then Onboarding SOP, intake, access checklist, and the
  implementation plan with milestones.
- Implementing → clone the Loop 7/8 blueprints into the client's n8n credentials and tenant,
  adapt them to their FSM/phone stack, test with their sample data plus edge cases, then
  QA checklist, client approval, deploy, and handover docs plus training.
- Log delivery hours every session.

Exit check: the current stage's checklist is 100% complete, with evidence (test logs, approval
notes). Real client data stays in 09-CLIENTS/CLIENT-00N only. Update STATE.md. Report in the standard order.
```

## Loop 15: Measure, report, expand

```
LOOP 15 of 15: MEASURE AND EXPAND. Read STATE.md, the CRM, delivery-hour logs, Unit-Economics.md.
Run this monthly.

Do:
1. Agency KPI scorecard in 06-INTELLIGENCE/Monthly-Reports/YYYY-MM.md: MRR (target $10K),
   active clients (10), prospects/week (50), demos/week (3), proposal conversion (30%+),
   churn (<3%), gross margin (60%+), delivery hours trend. Real numbers only. Mark a metric
   "not yet tracked" if there's no data.
2. A monthly client report per active client: hours saved, response time, missed-call recovery,
   bookings, follow-up completion, and recommendations for my approval.
3. Profitability per client: actual hours vs. estimate. Reprice or rescope anything under 60% margin.
4. Expansion decision: based on what clients actually asked for, choose the next division to
   activate (default order: Customer Experience, then Marketing, Knowledge, Intelligence). Wake
   that department's PROJECT-INSTRUCTIONS and write its demo plan. That plan feeds a new Loop 7-style build.
5. Next-quarter targets in 00-EXECUTIVE/Strategic-Roadmap.md.

Exit check: every number traces to a source (CRM export, logs, invoices), and one expansion
decision is logged in Decision-Log.md with its reason. Update STATE.md. Report in the standard order.
```
