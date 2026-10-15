# 08 — Oscar's operating-model inputs

**Source:** Oscar, 2026-10-14 ~8:40 PM ET. Full doc: [Drive](https://drive.google.com/drive/folders/1YaSw0YiF4iPdbocCz2j0HKm7SK88QoZJ). Standalone files below in `docs/oscar/`. Sections marked "Muse to confirm" need my sign-off; "Steve decides" need his.

## Files

| File | What |
|---|---|
| [oscar/forensics-16-sends.md](oscar/forensics-16-sends.md) | Full forensics on the Oct 14 sends — verdict, evidence, damage assessment, fix |
| [oscar/team-roster.md](oscar/team-roster.md) | Oscar's hunt roster — active seats, merges, kills (85 → ~15 runs/week) |
| [oscar/hunt-runbooks.md](oscar/hunt-runbooks.md) | Hunt runbooks: sourcing → enrichment → outreach → follow-up → forecast |
| [oscar/hubspot-stage-map.md](oscar/hubspot-stage-map.md) | HubSpot pipeline stage map + stage rules |
| [oscar/send-guardrail.md](oscar/send-guardrail.md) | Send guardrail — one lane, draft-first, lint, shared pause, reconciliation |
| [oscar/diagrams-source.md](oscar/diagrams-source.md) | Diagram sources (mermaid) |

## Key contributions folded in

- **Forensics:** Gmail client fingerprinting proved the 16 sends came through Muse's Gmail integration. (Resolution: Steve said "send em" at 19:00 — authorized, but Muse owns the scope/quality failures. PLX-470.)
- **Revenue diagnosis:** 0 positive replies from ~130 emails to ~110 firms (3.5% chance by luck) — deliverability (redirect-wrapped links), 11 PM–3 AM bursts, generic inboxes, spec-work framing, no tracking.
- **2-week plan:** Fix deliverability + tracking, 20-firm touch-2 with $149 Snapshot offer, Tue–Thu mornings, Steve's "send" each batch. Targets: 5 conversations, 2 Snapshots, 1 Fix.
- **16 overlaps resolved:** offers (merge under LGF), previews/hosting, Vercel cap, repo, HubSpot writers, inbox routing, sending (one lane: Oscar), pause (shared Linear gate), LinkedIn budget, Growth Ladders, Binsly, Substack, duplicate routines, morning briefs, Linear workspaces, booking link.
- **9 contradictions flagged** (C1–C9) between the two rule sets — see his doc §5.
- **Lean roster:** Oscar's side 85 → ~15 runs/week; 10 Muse-side cuts proposed (deploy watch, Lovable watch, Linear watch, X watchers, briefs merge, job scans, Fare Deal reminder → Todoist).

## 15 decisions for Steve (from Oscar's §9)

D1 restart order · D2 one prospect send lane (Oscar) · D3 offer merge (LGF) · D4 Muse trace (done) · D5 Lifepoint draft · D6 the 18 recipients (hold) · D7 one 30-day target · D8 Oscar → Linear plxio access · D9 shared pause scope · D10 Growth Ladders pricing · D11 Stripe "binsly" naming · D12 Supabase · D13 Grok usage top-up · D14 LinkedIn budget + CTA · D15 Meredith seat.

Each becomes a Linear `decision:steve` issue. D4 is closed (trace complete).
