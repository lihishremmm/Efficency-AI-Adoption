# AI Usage Assessment — NICE UX Team

Two static pages summarizing the "AI Usage Assessment — NICE UX Team" survey (37 responses):

- **`index.html`** — the full written report (executive summary, findings, KPI baseline, program, action items), mirroring the Word report.
- **`dashboard.html`** — an interactive chart dashboard (Chart.js) with the same data.

Both link to each other via a top nav bar.

## Publish to GitHub Pages

Your repo: **https://github.com/lihishremmm/Efficency-AI-Adoption**

I tried pushing directly and, as expected, GitHub refused with no credentials available (`terminal prompts disabled` — I don't accept or enter tokens/passwords on your behalf). Pick whichever of these is easiest — both take under 2 minutes.

### Option A — no git needed (drag & drop)
1. Go to your repo: https://github.com/lihishremmm/Efficency-AI-Adoption
2. Click **Add file → Upload files**, drag in `index.html`, `dashboard.html`, and `README.md` from this folder, and commit.
3. Go to **Settings → Pages**. Under "Build and deployment", set Source = `Deploy from a branch`, Branch = `main` / `/(root)`, then Save.
4. Your report will be live at **https://lihishremmm.github.io/Efficency-AI-Adoption/** within a minute or two; the dashboard is at the same URL + `dashboard.html`.

### Option B — with git (this folder is already a git repo, commits ready, remote already set)
```bash
# from this folder
git push -u origin main
```
(The remote `origin` is already set to `https://github.com/lihishremmm/Efficency-AI-Adoption.git` — git will prompt for your GitHub credentials/token on push.)
Then enable Pages the same way as step 3 above (Settings → Pages → Deploy from branch `main`).

## Notes
- Both pages are static HTML — no build step, no server needed.
- `dashboard.html` uses Chart.js loaded from a CDN, so it needs an internet connection to render (true for any visitor, including on GitHub Pages).
- Data source: Microsoft Forms survey, 37 responses, Aug 2026. All figures are aggregate — no individual names appear on either public page (one illustrative champion example in `index.html` was anonymized for this public version).
