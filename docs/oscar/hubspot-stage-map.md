# HubSpot stage map (portal 22009185, "Sales Pipeline" / default)

Owner of every stage change: **Oscar** (via Rev Operator). Muse writes only chat-flow contacts/conversations and Arbolus consulting deals, never pipeline stages (agreed Oct 14). **Rules for stages after Outreach Initiated are proposals — Steve to confirm; process fit Muse to confirm.**

![HubSpot stages](hubspot-stages.png)

| Stage (internal id) | Enter when | Required on record | Exit / timer | Rule source |
|---|---|---|---|---|
| Identified | Rev Operator creates company + contact + deal | Named contact, source batch, amount | No addressable (named) email after 7 days → Closed lost | Steve rule 10 |
| Outreach Initiated (`appointmentscheduled`) | First-touch is in Gmail Sent | Send date, preview URL (HTTP 200 when sent), subject | Touch 2 day 3–4, touch 3 day 8–10; no reply 14 days after touch 3 → Closed lost (proposed) | Steve rule 9; follow-up timing proposed |
| Qualified | Positive human reply | Reply summary, next step | Call booked → Presentation Scheduled | proposed |
| Presentation Scheduled | Call on calendar (meet.stevepeeleii.com) | Date/time | After call → Contract Sent or Closed lost | proposed |
| Verbal Acceptance | Prospect says yes on call | Tier (Snapshot $149 / Fix $750 / System $1,250 / Care $250/mo, if merge approved) | Docs sent → Contract Sent | proposed |
| Contract Sent | Engagement letter + Stripe link sent with Steve's approval | Doc links | Paid → Closed won; declined → Closed lost | proposed |
| Closed won | Payment received | Amount, Linear `handoff:delivery` issue | — | — |
| Closed lost | Unsubscribe, hard bounce with no alternate, retiring, no authority, no email in 7 days, silence after touch 3 | Reason | Suppress domain | Steve rules 10 + Gartner precedent |

Snapshot Oct 14 7:55 PM ET (Oscar's pull): 105 deals — 73 Outreach Initiated ($57,000), 26 Closed lost, 6 Closed won (all legacy). Creation sources: 62 sprint-era deals Sep 30–Oct 9 created via INTEGRATION (Grok side, user id 100158557); 29 deals Oct 12 (23) and Oct 14 (6) created in the HubSpot web UI (CRM_UI) under Steve's own user 47552854.

Hygiene rules
- Amount: $750 per sprint deal; $1,200 for the 5 logistics retainer deals (CTI, JOB, M.C., Whitewater, RMA) until Steve changes it.
- One deal per firm; check company domain before creating (Oct 14 created a duplicate note on Warner).
- Every note prefixed with author `[Oscar]`/`[Rev Operator]`/`[Muse]`.
