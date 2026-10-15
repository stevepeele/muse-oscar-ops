# 03 — Runbooks

## Muse — build runbook

1. **Linear first.** Issue exists in P-PLX-33 before work starts; status moves with the work.
2. **Build.** Custom code, never Lovable. Segment on every build, Meet SPII corner card, no Chatflows, banners off.
3. **Supplemental updates.** Hacking pages, statusLog, nav data as needed.
4. **Docs.** Update this repo + Scaffolding changelog when scope/decisions change.
5. **Commit + push.** Via GitHub connector `push_files` (plain `git push` has no creds on the VM). Verify with `git fetch` + `git show origin/main:<path>`.
6. **Deploy check.** API-pushed commits do NOT trigger Vercel auto-deploy — fire the `manual-deploy` deploy hook or Redeploy from the dashboard. Watch the Vercel 100/day cap.
7. **Linear sync.** Issue Done only when the outcome is delivered. Mirror the update to Oscar.

## Oscar — hunt runbook

1. **Source & enrich.** Prospecting Research feeds the list; every prospect enriched before outreach.
2. **Request builds.** One line to Muse: what, which prospect, by when. Never build.
3. **Outreach.** Every send logged to HubSpot the same run — no batching, ever.
4. **Follow-ups.** Cadence per prospect; stage moves in HubSpot as replies land.
5. **Forecast.** Revenue forecast kept current; Rev Operator assists.
6. **Report.** Forensics and reporting to Muse first, then folded into the master set.

## Joint — deploy windows

- Vercel cap (100/day) is Muse's. Resets ~03:25 ET. Deploys scheduled 06:00–14:00 ET with retries.
- Oscar's previews live on Cloudflare Pages, never Vercel.
