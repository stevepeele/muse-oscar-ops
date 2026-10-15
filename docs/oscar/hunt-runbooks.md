# Hunt runbooks (Oscar's stages inside Muse's triage flow)

Status: draft by Oscar, 2026-10-14. **Process sections: Muse to confirm.** Muse leads process and orchestration; these runbooks fit Oscar's hunt into Muse's documented backbone ("Muse × Oscar — Lanes, Triage & Ownership", v1 2026-10-14, Section 3 triage flow and Section 4 build-request format) and Muse's build discipline (Linear issue first → build → verify → docs). They do not create a parallel process.

![Hunt mapped onto Muse triage flow](hunt-on-triage.png)

**Systems of record**
- **HubSpot portal 22009185** = the pipeline (who, stage, every touch). Oscar owns stages.
- **Linear** = the book of record for every Oscar↔Muse handoff and every Steve decision. Chat is only for real-time need.
- **Gmail Sent** = proof of send. A send is only logged if it is in Sent.

**Linear setup (live per Muse's backbone v1.1 Section 05).** Book of record: project **Muse × Oscar Ops (P-PLX-33)** in workspace `plxio` (https://linear.app/plxio/project/muse-oscar-ops-27f36aa6a48f). Statuses: Backlog → In Progress → Done. Rules: no handoff exists until it's an issue; the title names the ask; the assignee is the one doing the work (build requests → Muse; pipeline/forensics → Oscar); whoever needs cross-lane work creates the issue, assigns it, and sets a due date; Steve's calls are labeled decision and carry options + a recommendation; Done only when the outcome is delivered; comments replace side-channel DMs.
- **Blocker:** Oscar's Linear connection is signed into workspace `SPII` (linear.app/spii), not `plxio`, so Oscar can't read or create P-PLX-33 issues yet (decision D8).
- Labels Oscar proposes for P-PLX-33 (Muse to confirm): `handoff:build`, `handoff:lead`, `handoff:delivery`, `decision`, `lane:oscar`, `lane:muse`, `gate:send`, `incident`.
- Decision and lead issues are worked or decided, not built (exempt from "every issue gets built").

---

## Stage 1 — Source & enrich (Oscar) · backbone step 1
"Oscar finds the firm, enriches contact data, creates the HubSpot company + deal (same run, no batching)."
1. Oscar writes the ICP for the batch (vertical, geography, size, the website problem we fix). Max **10 firms per batch** until reply rate is proven.
2. Prospecting Research returns the package; Profiler finds a **named, non-generic email** for each (not info@/office@/website@/cpas@).
3. No named email → no preview, no deal advance. Firm goes to the LinkedIn/phone list or is dropped (Steve rule 6).
4. Rev Operator creates company + contact + deal at **Identified**, same run, note prefixed `[Oscar]`.
5. Suppression check against the suppression list (Gartner unsubscribe, bounces, retiring, already-contacted domains in Gmail Sent).
**Done when:** HubSpot deal exists with named contact; suppression check passed.

## Stage 2 — Build request (Oscar → Muse) · backbone step 4
1. Oscar (with Ponderer's thesis) opens a Linear issue, label `handoff:build`, title in Muse's exact format:
   `BUILD: preview site for {firm} — {contact name/email} — needed by {date} — {one-line context}`
2. Issue body: HubSpot deal link, current-site URL, the 3 observed issues, the thesis, the Mercury HR standard checklist (firm-specific thesis, before/after slider vs real screenshot, unique art direction, 3-step start-here, honest 48h close).
3. Muse confirms on the issue, builds, verifies (HTTP 200 + firm-specific + visual check), documents, and posts the live link on the issue. Oscar never touches repos, Vercel, or the site.
4. Deploy slots: Muse owns the Vercel cap; Oscar's batches go in Muse's deploy calendar, or to Cloudflare Pages.
**Done when:** live link on the Linear issue; Rev Operator copies it to the HubSpot deal.

## Stage 3 — Outreach (Oscar) · backbone step 2
"First-touch + follow-ups go out on Oscar's side. Every send logged in HubSpot the same run."
1. Prompter drafts; Oscar reviews against the send lint (`send-guardrail.md`): no placeholders, preview returns 200, plain links (no google.com/url wrappers), named recipient, correct firm name/possessive, one booking link (meet.stevepeeleii.com), 48.stevepeeleii.com (or the merged LGF URL once Steve decides).
2. Oscar posts one approval package to Steve: list of drafts, recipient, preview link, send window. Linear issue label `gate:send`.
3. Only on Steve's explicit "send" for that package: send Tue–Thu 8–10 AM ET, max 20/day, from the single prospect send path.
4. Rev Operator logs each send same run (stage → Outreach Initiated) from Gmail Sent proof.
**Done when:** Gmail Sent count = HubSpot logged count for the batch.

## Stage 4 — Reply triage (Oscar) · backbone step 3
1. Muse's inbox triage sees prospect mail first. Within the same run Muse opens a Linear issue `handoff:lead` in the agreed one-line format: **firm — contact name/email — how they found us — what they asked — HubSpot link**, and does not reply.
2. Oscar classifies within 1 business day:
   - Positive → Qualified; draft reply for Steve; book via meet.stevepeeleii.com.
   - OOO / referral → update contact, redraft to the referred person (e.g. Lifepoint → Steve Seward), through the send gate.
   - Unsubscribe → Closed lost, suppress everywhere, no reply beyond Steve's own.
   - Bounce → find alternate in 7 days or Closed lost.
   - Retiring / not a fit → Closed lost.
3. Silence: touch 2 at day 3–4, touch 3 at day 8–10, each through the send gate. After touch 3 + 14 days of silence → Closed lost (proposed rule, Steve to confirm).

## Stage 5 — Deliver & close (Oscar) · backbone step 5
1. Call → Presentation Scheduled. Offer Ops/Compiler checklist assembled.
2. Engagement letter + invoice (Muse's 48-Hour Sprint docs, INV-2026-001 template) + Stripe link; Steve approves the commitment → Contract Sent.
3. Paid → Closed Won; Oscar opens Linear `handoff:delivery` to Muse (scope, deadline = 48h from kickoff for the Fix tier).
4. Muse delivers; Oscar owns the client thread through close and asks for the testimonial/case study.

## Stage 6 — Visibility (both) · backbone step 6
- HubSpot notes prefixed `[Oscar]` or `[Muse]` so authorship is never ambiguous again.
- Rev Operator daily: Gmail Sent (prospect domains) vs HubSpot logged touches; any send with no owner opens a Linear `incident` issue.
- Weekly sync (Fri, after Oscar's revenue cycle): 15-minute Linear review of open `handoff:*` and `decision:steve` issues; output is one update to Steve.

## Stage 7 — LinkedIn (Oscar)
- Blank connection requests only, top 3 per firm, only for firms already emailed, shared daily cap with Muse's job-hunt drafts (see main doc §3). Logged in HubSpot.
