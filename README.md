HOMES Performance Dashboard
Live sales scoreboard for the HOMES team — Team / Role / Rep views with targets, pace bars, appointments, and opportunities created.

Live URL: https://YOURUSERNAME.github.io/YOUR-REPO-NAME/ (update after deploy)
How it works
Single-file app: everything lives in index.html — no build step, no dependencies, no server.
Data source: a Coefficient-fed Google Sheet (Salesforce exports). The Sheet ID is hardwired in the file. The sheet must stay shared "Anyone with the link · Viewer" or all live fetches fail.
Snapshot fallback: the file ships with a baked data snapshot (as of 2026-07-10), so it renders instantly and degrades gracefully if any tab fetch fails. On load it fetches the sheet tabs and flips metrics to green "Live" badges.
Deploying an update
Replace index.html at the repo root and commit.
Wait 1–2 minutes for GitHub Pages to rebuild.
Hard-refresh the live URL (Ctrl+Shift+R / Cmd+Shift+R) — a normal refresh often shows the stale cached version.
Confirm the status dot turns green ("Live · core tabs loaded", then "Live · all tabs loaded").
Live vs. static metrics
Live (recomputed every refresh): Net Revenue & Avg Fee, Deals to ARIP, ARIP Fallout, Leads Claimed, Talk Time, Appointments Set/Attended, Show Rate, Opps Created & Lead Source, pipeline charts.
Static (baked Rainmakers export): targets, Deal Reviews, Contracts Sent, Calls, QCs, Live Transfers — these need Salesforce reports added as sheet tabs to go live.
Counting rules
Appointments credit only the rep who set them (Created By). Opps credit VPs by Opportunity Owner and AMs/Follow-Up by Created By. ARIPs count distinct opportunities. "Tech" excluded. Talk time in minutes.
Troubleshooting
Red dot / "All tab fetches failed": you're viewing inside an app preview that blocks Google requests (open the real Pages URL in a browser), or the sheet sharing isn't "Anyone with link · Viewer".
Status line names specific failed tabs: everything else stays live; the named tabs fall back to snapshot. Paste that message into a new chat along with HANDOFF_v3_addendum.md to debug.
Stale numbers: hard-refresh; also note the dashboard is only as fresh as Coefficient's last sync into the sheet.
Continuing development
Full architecture notes, verified tab headers, counting-rule anchors, and rebuild instructions live in HANDOFF_v3_addendum.md (plus the original HANDOFF v2). To continue work: paste the handoff + the current index.html into a fresh chat.

