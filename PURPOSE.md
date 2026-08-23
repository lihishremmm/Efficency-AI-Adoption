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

### Show the working

**Every figure displayed must show how it was calculated.** Each chart, table and headline number carries a `🧮` disclosure with the raw response counts, the arithmetic, and an explicit flag when a number is an estimate, a judgement, or not a calculation at all. A **Show all calculations** control at the top of the page expands them all at once.

This is a hard rule, not a nicety. The report makes claims about the team's efficiency to an audience that will act on them, and a figure nobody can check is a figure nobody should trust. It also means the underlying per-question data lives inside `index.html` itself, so the page stands alone without a separate raw-results file.

### Tabs in `index.html`

| Tab | Contains |
|---|---|
| **Velocity vs. Actual Efficiency** | The core argument: velocity went up, but so did the scope of the job and the pace of the developers — so the real efficiency gain is smaller than the raw speed-up. |
| **Critical Issues** | *Coming soon.* |
| **Report** | The full assessment — adoption, efficiency, use cases, workflow, champions, barriers, programme, actions, metrics. |

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
