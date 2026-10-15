# Send guardrail — nothing leaves outside the approved path

Status: proposed by Oscar after the Oct 12–14 incident (see main doc §6). **Process fit: Muse to confirm. Final: Steve.**

![Send guardrail](send-guardrail.png)

## The rule
1. **One lane per send type.** Prospect email (first touch, follow-up, reply) is Oscar's lane only. Muse's Gmail integration sends only to Steve himself and to categories Steve pre-authorized in writing (recruiter scheduling logistics, specific one-off emails he approved by name). Job applications and Arbolus submits are forms, not email, and stay Muse's under the existing grants.
2. **Draft-first.** Every prospect message is a draft (Gmail draft or approval card), never a direct Gmail API send.
3. **Explicit approval.** A send needs Steve's explicit "send" naming the draft or batch, within 24h. A bare "yes" to an either/or, "do everything", "bias to action" or "if you can handle it just do it" is **not** send approval (Muse's own hard-gate wording, adopted for both sides).
4. **Lint before send** (machine-checkable):
   - no `(`…`pending`…`)`, `verify`, `TODO`, `[`, `{`, `##`, `|` table rows, or internal IDs like `P-00`;
   - every preview link returns HTTP 200 at send time and links are plain (no `google.com/url?q=` wrappers);
   - recipient is a named person, not on the suppression list, not contacted in the last 72h, no prior bounce;
   - firm name and possessive correct ("SmartFinancials'", not "SmartFinancials's");
   - batch ≤ 20/day, sent Tue–Thu 8–10 AM ET.
5. **Shared pause.** A pause from Steve on either app applies to both. The pause lives in one place both bots read before any external action: a pinned Linear issue labeled `gate:send` titled `PAUSE — all external actions` (proposed; Muse to confirm). While it is open, no sends, posts, deploys, CRM stage changes, or scheduled public actions (including queued cron posts).
6. **Same-run logging with author.** Every send is logged in HubSpot the same run with an `[Oscar]` or `[Muse]` prefix.
7. **Daily reconciliation.** Rev Operator compares Gmail Sent (prospect domains) with HubSpot. Any prospect send with no approval record opens a Linear `incident` issue and pauses the lane that sent it.

## Standing-authorized sends (no per-message approval) — to be confirmed by Steve
- Muse: morning brief and digests to steve@stevepeeleii.com; recruiter scheduling logistics (his order); Arbolus auto-submits; job applications (standing grant).
- Oscar: none.
Everything else follows steps 2–6.
