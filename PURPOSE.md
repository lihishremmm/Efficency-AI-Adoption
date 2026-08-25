# Project Purpose — AI Efficiency & Adoption, NICE UX Team

> **This file is the single source of truth for *why* this project exists.**
> It is a living document: extend and refine it whenever the scope becomes clearer.
> It deliberately contains **no findings and no data** — see [Where findings go](#where-findings-go).

---

## What this project is

We surveyed the NICE UX team about how it works with AI. This project turns that survey into something the team can act on.

The goal is not to produce a report. The goal is to **understand how the team can work better with AI**, and to make what already works available to everyone.

---

## What we want to answer

### 1. How efficient are we today, compared to before AI?
Establish a real, measured baseline of our efficiency with AI versus without it — not an impression, something we can re-measure later and compare against.

### 2. How has the work itself changed?
Understand what the job actually looks like now: what we no longer do, what takes the same time as always, and what we can produce today that simply wasn't possible before.

### 3. How have the demands on us increased?
Understand how expectations and volume of requests have grown, and what that means for the team.

### 4. How does our velocity compare to Development's?
Understand whether design is keeping pace with the developers now that both sides use AI, and where the friction between us actually sits.

### 5. Which practices work best for us — and how do we spread them?
Identify the working practices that deliver the most for this team, and find a way to take them from the individuals who invented them and distribute them across the whole team.

### 6. Who are our AI Champions?
Identify the people already using AI intensively and at depth, and **interview them**. Understand how their way of working has changed because of AI — both:
- **inside the UX team**, and
- **in collaboration with other teams**, particularly **Product** and **Development**.

---

## What success looks like

This project has done its job when:

- We have a **measured efficiency baseline** we can re-run in six months and compare against.
- We know **which practices are worth spreading**, and why.
- The champions have been **interviewed**, and what they know exists somewhere other than their heads.
- The team has a **shared place** for prompts, workflows and practices — instead of everyone solving the same problem alone.
- We can describe our position relative to Development with **evidence**, not impressions.

---

## Scope boundaries

To keep the project clear, it is worth stating what this is **not**:

- ❌ Not a performance evaluation of individuals.
- ❌ Not a tool procurement exercise — though it may produce a purchasing recommendation.
- ❌ Not a one-off report. The baseline exists to be re-measured.
- ❌ Not a rollout of AI to a team that doesn't use it. The team already uses AI daily; this is about depth, not adoption.

---

## Working principles

- **Measured over felt.** Where we can compute a number from actual responses, we use it — even when it is less impressive than the estimate.
- **Only claims we can defend.** Every figure we publish should survive someone checking it.
- **Confidence is stated.** When a number is derived or estimated rather than measured, we say so where it appears.
- **Anonymity is respected.** Respondents were told their open answers were anonymous. Anything naming individuals is kept separate and is not published without their explicit consent.

---

## Project structure

| File | Role |
|---|---|
| **`index.html`** | **The main file.** The single page we build and present. Everything the audience sees lives here, organised in tabs. |
| **`AI Usage Assessment — NICE UX Team(1-37).xlsx`** | **The raw data.** The untouched survey export (37 responses) from Microsoft Forms. Every figure in the report traces back to this file. It is never edited — corrections and derived values live in `index.html`, not here. ⚠️ **Held outside git** — see [Handling the raw data](#handling-the-raw-data). |
| `PURPOSE.md` | This file. Why the project exists. |

**`index.html` is the main file.** When something needs to be shown, it goes in `index.html`. Do not create parallel or duplicate HTML pages — earlier copies caused the same content to drift out of sync in three places.

### Handling the raw data

The survey export is the source of truth for every number we publish, but it is **deliberately not committed**. A `.gitignore` rule (`*.xlsx`) keeps it out.

**Why:** this repository is public, and the export carries an `Email` column, a `Name` column and a `Your full name` column next to the free-text answers. Respondents were told those answers were anonymous. A commit cannot be taken back — once pushed, the file remains in history and can be cloned or indexed even after it is deleted.

**Where it lives:** in the project folder on OneDrive, next to the repository, shared with the team the same way the rest of the team's material is.

**If it ever needs to be versioned:** make the repository private *first*, then remove the `*.xlsx` rule. Alternatively commit a copy with the `Email`, `Name` and `Your full name` columns stripped, and keep the full export out.

This rule exists to enforce the anonymity principle below — it is not housekeeping.

### Show the working — in two layers

The audience is **not data-literate, and should not need to be.** Every figure is therefore presented twice, in this fixed order:

| Layer | What it is | Visibility |
|---|---|---|
| **1. The number** | The figure itself, with a plain one-line meaning. | Always visible |
| **2. The logic** | *How we got there*, in short steps, **in words — no arithmetic.** What we counted, what we couldn't know, what we assumed. | Always visible |

**Every figure also carries a confidence badge**, and the page explains the three of them once, at the top:

- **Measured** — counted from the 37 answers. Nothing assumed.
- **Estimated** — the survey gave direction but not size, so we chose a number. Directional only.
- **Our reading** — not a survey answer at all; our interpretation.

**The arithmetic layer was removed on 2026-08-24** by explicit decision: the collapsed `🧮` blocks (raw response counts and exact sums, one per figure) made the page heavier than the audience needed. Checkability is preserved differently: every figure traces back to the raw survey export (available on request), most arithmetic blocks live in this repository's **git history** (last committed version), and any figure can be recomputed from the export directly. Blocks can be restored per-figure if a claim is ever challenged — the `details.calc` CSS is intentionally kept in `index.html` for that case.

### Say it plainly

Two further rules follow from the audience:

- **No unexplained jargon.** Where a term is unavoidable (*story points*), it is defined in one sentence at the point of use, and the chart is re-described in plain words underneath.
- **Never show the same figure twice in two formats.** One visual per idea. A second chart of the same numbers is not extra rigour, it is extra reading.

### Tabs in `index.html`

| Tab | Contains |
|---|---|
| **Velocity vs. Actual Efficiency** | The core argument: velocity went up, but so did the scope of the job and the pace of the developers — so the real efficiency gain is smaller than the raw speed-up. |
| **Critical Issues** | *Coming soon.* |
| **AI Champions** | The seven intensive users, one dossier each, on **three layers**: ① what the survey shows (Measured) · ② interview notes (empty until the interviews happen, shown as empty on purpose) · ③ the decision on how to adapt their suggestion for the whole team. Plus the interview tracker (0/7), a decisions ledger of every suggestion, and the fixed interview guide. |
| **Report** | The full assessment — adoption, efficiency, use cases, workflow, champions, barriers, programme, actions, metrics. |
| **Conclusions** | What keeping pace would take: the required speed (~2.7–2.8×, +45–50%) vs. the structural ~2× ceiling (judgement doesn't compress) — so the levers are elsewhere: cut/automate the non-hands-on 40%, and headcount. |

---

## Where findings go

**Nothing is recorded yet.** This file stays purpose-only.

When we confirm something worth keeping, it goes into a **separate folder**, as its own categorised `.md` file — one topic per file, so each finding can be updated, cited or withdrawn on its own.

We create that folder when there is a first real finding to put in it, and not before.

---

## Background

| | |
|---|---|
| **Source** | *AI Usage Assessment — NICE UX Team* survey (Microsoft Forms) |
| **Raw data** | `AI Usage Assessment — NICE UX Team(1-37).xlsx` — the survey export (37 responses). Kept in the OneDrive project folder, **not in git** (see [Handling the raw data](#handling-the-raw-data)) |
| **Team** | NICE UX — India, Israel, United States |
| **Owner** | Design Operations |
| **Repository** | `lihishremmm/Efficency-AI-Adoption` |

---

## Changelog

| Date | Change |
|---|---|
| 2026-08-23 | Initial purpose defined |
| 2026-08-23 | Raw data file recorded: `AI Usage Assessment — NICE UX Team(1-37).xlsx`, held outside git (public repo, export contains names and emails) |
| 2026-08-24 | Audience fixed as **non data-literate**. Velocity tab rebuilt on the three-layer rule (number → logic in words → arithmetic), confidence badges added to every figure, and the duplicate effort chart replaced by a single plain-language ladder |
| 2026-08-24 | Method stated on the face of the speed figure: the 1.88× is an **effort estimation by the designers themselves** (each of the 37 sized four fixed tasks before-AI and today), not a stopwatch — with the resulting optimism bias named at the point of use |
| 2026-08-24 | "Start here" reframed around the week, not the task: 2× on tasks → diluted by the **60/40 hands-on vs. meetings split** (≈34% of the week in meetings & calls measured, 40% our rounding) → ~1.4× week-level → freed time consumed by **new deliverables** (59% HTML prototypes, 11% production code). The +34%/−29% pair stays in its own section; a NOT-THE-SAME-NUMBER warning separates the two dilutions |
| 2026-08-24 | Final occupancy figure added (⏱ card, Velocity tab): the reconstructed week costs **≈83 of the pre-AI 100 → ~6.9 hrs/week freed**, which converges to 0.2 hrs with the independently measured **7.1 hrs/week** (Q11) — the report's strongest cross-validation. Occupancy read as *effectively full again* once new deliverables are counted (Our reading) |
| 2026-08-24 | Dev speed reframed as a **demand engine**, not just a pace to match: developers ~2× faster (84% perceive it, Q27) consume design content at roughly double the old rate, so the volume design must supply rose with them — added as the second consumer of the freed ~7 hrs (leak 3, ⏱ card, Start-here sentence), flagged *Our reading* |
| 2026-08-24 | "Start here" compressed into a **five-line schematic chain** (2× → 60/40 → ≈7 hrs confirmed twice → consumed by 59%·11%·dev-2× → occupancy full): only the fundamental figures, one line each, badges inline. Keybar cards and the long summary paragraph removed — same figures were shown twice |
| 2026-08-24 | **All 30 collapsed 🧮 arithmetic blocks removed** from `index.html` on request. The show-the-working rule drops from three layers to two (number + logic in words); checkability now rests on the raw export and git history. See the updated [two-layer rule](#show-the-working--in-two-layers) |
| 2026-08-24 | Velocity tab slimmed to three sections: the section **"The speed-up is real"** (per-scenario chart + table, took-over/still-takes cards) removed with its chart JS; remaining sections renumbered (01 where the time went · 02 the whole story). The per-scenario detail (1.79–2.03×) survives as one line in the opening chain |
| 2026-08-24 | **AI Champions tab added**, built on a three-layer rule per champion: ① survey (Measured) → ② interview notes (*Not yet collected* — kept visibly empty, with the questions each interview must answer) → ③ how we adapt the suggestion, with one of four verdicts (**Adopt · Adapt · Pilot · Park**), an owner and a `Proposed` status until the interview confirms it. Adds an interview tracker (**0/7**, the project's P0 gate), a **decisions ledger** of all 11 champion suggestions with the reason each one is reshaped rather than taken as-is, and a fixed 12-question interview guide split *method / inside UX / Product & Dev*. The seven compact cards were **moved out of Report §05** (now a pointer, id `champions-ref`) so champion content has one home and cannot drift; the unused `.champion-*` CSS was removed |
| 2026-08-24 | **Conclusions tab added**: to keep pace we would need ~2.7–2.8× (+45–50% over 1.88×), but speed has a structural ceiling of ~2× because judgement (~half of every task) doesn't compress — so the levers are cutting/automating the non-hands-on 40% and headcount, not working faster |
