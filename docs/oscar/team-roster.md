# Oscar's team roster (the hunt)

Status: draft by Oscar, 2026-10-14 ~8:30 PM ET. **Process fit: Muse to confirm.**

![Oscar team](oscar-team.png)
Source of record: `/home/box/agent-data/agents/<id>/profile.json`, the Grok message index, `/workspace/oscar/bot-inventory.md` (Oct 9 audit), `/workspace/oscar/usage-cut-list.md` (Oct 8). Routine schedules are what each bot said in chat; no routine definitions are stored on disk. Everything below is **paused** since Steve's 7:40 PM ET order on Oct 14.

Rule for every seat: bots draft; nothing leaves Steve's accounts without his explicit "send" (see `send-guardrail.md`). Every handoff to Muse is a Linear issue (see `hunt-runbooks.md`).

## Active seats

| Bot (id) | Role | Inputs | Outputs | Trigger / routine | Status (Oct 14) | Call |
|---|---|---|---|---|---|---|
| **Oscar** (`a4c6730d`) | Co-exec, the hunt. Owns pipeline, stage rules, outreach drafts, forecasting, team orchestration | HubSpot, Gmail (read), Linear, team outputs | Weekly hunt plan, approval packages for Steve, Linear handoffs to Muse | Routines claimed: daily LinkedIn connects, prospecting Drive sync, Friday revenue cycle, Growth Ladders Substack weekly | Paused (all 4 routines) | **KEEP**. Cut to 1 weekly routine (Friday revenue cycle); LinkedIn connects run as a step inside it; drop Drive sync (Compiler does it) |
| **Prospecting Research** (`29568a8a`) | Sources firms: Greater Cincinnati/NKY professional services, logistics. Scores 0–10 | ICP brief from Oscar, public web | `batch-00N-*.md` package: firm, site, location, vertical, contacts, why, score | On request, batch then wait for Steve | Paused; silent since Oct 1 | **KEEP** (on request only) |
| **Profiler** (`ed339881`) | Public enrichment: named emails, decision-makers, reach methods. Never outreach | Sourced firm | `profiler-*.md`, contact CSV rows | On request | Paused | **KEEP** (on request only) |
| **Rev Operator** (`2eb156b6`) | Only HubSpot writer on Oscar's side: company, contact, deal, stage, notes | Approved prospects, Gmail Sent proof | HubSpot records with IDs reported | Weekday 08:06 email-block check + 08:49 pipeline report (both failing since Oct 9 on usage) | Paused after 7:28 PM Lifepoint fix | **KEEP**. Merge 08:06 into 08:49; add daily Gmail-Sent vs HubSpot reconciliation (the check that would have caught the Oct 12–14 sends) |
| **Ponderer / Dreamer** (`e5000ab7`) | Opportunity package: evidence, 3–5 quick wins, firm thesis for the preview | Firm/URL | `ponderer-*.md` (20 on disk) | On request | Paused; quiet since Oct 3 | **KEEP**. Its thesis becomes the body of the Linear `handoff:build` issue to Muse. Drop the "Lovable prompt" output (Lovable is out) |
| **Prompter** (`7b2169c6`) | De facto outreach drafter (email cards) and duplicate pipeline reporter | Thesis, preview link | Drafts | Claimed: Deal engagement alert (weekdays 8:17am–7:17pm, hourly assumed) + Weekday pipeline report 08:48 | Paused | **MERGE**: becomes the single outreach drafter. Kill its pipeline report (duplicate of Rev Operator 08:49) and the hourly alert (duplicate of Muse's HubSpot chat watch + lead alerts) |
| **Offer Ops** (`c453e8a1`) | Scope, compliance flags, deliverable checklist once a prospect says yes | Yes from prospect, package | `offer-ops-handoff-*.md` (18) | On a yes | Paused; thread cold since Sep 30 | **MERGE into Compiler** (same firms, same pack). Keep the compliance checklist as a template |
| **Compiler** (`eb16c0bd`) | Assembles the per-firm Drive pack, writes folder link to HubSpot | HubSpot stages | Drive folders (`/workspace/compiler/run-2026-10-08/`) | Weekdays 07:56 | Paused | **KEEP**, cut to Mon/Thu. Absorbs Offer Ops |
| **Binsly Bot** (`c89e8e5a`) | Binsly growth: IG @bins.ly, X @yourbinsly posts and drafts | Binsly product (Muse builds it) | Growth pack, scheduled posts | Weekday drafts, Friday recap, scheduled posts (#2, #3 failed on usage) | Paused, drafts only | **KEEP but gate**: drafts only until Steve approves a posting cadence; Muse's queued "Bins.ly X autopost (5 posts)" is the same lane, so one of them must go (see main doc §3) |
| **Pulse** (`08033b34`) | X mentions/replies roundups | X | Hourly roundups to Steve | Hourly | Paused (no X replies) | **MERGE** with Muse's Spencer (X lane, 10-min cycles) and "vault X engagement 10m". One X watcher, max 2 roundups/day |

## Paused or dormant seats

| Bot (id) | Role as written | Evidence of output | Call |
|---|---|---|---|
| Builder (`b59f7429`) | One HTML concept per firm; does not publish | 189 msgs through Oct 3 | **KILL as a builder** (Muse owns all builds as of Oct 14). Optional: keep as a mockup sketcher whose output only goes into a Linear `handoff:build` issue |
| Grok Bot (`a581849a`) | Generic teammate; ran "Periodic proactive work" (routine id `5138c468…`, no longer exists) | Oct 14 Lifepoint draft card + HubSpot fix request | **KILL routines**; keep seat paused. It must never run an unregistered proactive routine again |
| Research (`2e2fe747`) | One sourced brief | Greeting only | **KILL** (Muse owns research) |
| CMO (`69ccae31`) | Marketing slate | Greeting only | **KILL** |
| VP Sales (`f58fa23b`) | Pipeline table | Greeting only | **KILL** (Oscar + Rev Operator do it) |
| VP Product (`8299034e`) | Scope | Greeting only | **KILL** (Muse owns delivery) |
| Copywright (`e2f27839`) | Draft copy | Greeting only | **KILL** (Prompter drafts) |
| Controller (`17870955`) | Money picture vs $2,500 | No figure ever | **KILL**; revenue forecast moves to Oscar's Friday cycle |
| Community (`5f4c2c3b`) | Relationship move | Greeting only | **KILL** |
| People (`e9a515b4`) | Role map | One stale map | **KILL** (this roster replaces it) |
| COO (`3ace39a0`) | Operating call | Nothing since Oct 3 | **KILL** (merged into Oscar) |
| Steve OS (`9229418b`) | Morning brief, Todoist, calendar, inbox | Brief Oct 8 07:35 | **KILL / merge into Muse** (Muse runs the 08:30 brief, Todoist, inbox) |
| Meredith (`a9311d19`) | Not defined on disk (empty description) | Acknowledged hold Oct 14 | **Steve to say what it is**; default KILL |
| Retired seats `8aeec7e6`, `8f600ce4`, `b19f141a` | Already retired | none | **Delete** (and repoint `active-agent.json` off `b19f141a`) |
| 13 idle/echo rooms (Exec, Sales, Marketing, Product, Finance, Staff, Money, Mary Maker, 3 "updates", CMO line, People line, Builder room) | Echoes | none | **Archive** (Steve, in the app) |

Net: 10 working seats → **7 keep** (Oscar, Prospecting Research, Profiler, Rev Operator, Ponderer, Prompter, Compiler) + Binsly Bot gated + Pulse merged. Scheduled runs on Oscar's side drop from ~85/week (Oct 8 estimate) to ~15/week: Rev Operator 5, Compiler 2, Oscar Friday cycle 1, Binsly 5–7 drafts.
