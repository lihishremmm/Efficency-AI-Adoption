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
| **`index.html`** | **The main file.** The full survey report and its data — Velocity, Champions, Report, Conclusions tabs. Everything the audience needs to check a figure lives here, organised in tabs. |
| **`best-practices.html`** | **The Best Practices hub — a deliberate second product, not a duplicate.** Redesigned 2026-08-26 as its own browsable/searchable/filterable experience (Overview, Practice Library, Workflows, AI Champions, Examples, Resources). It is content built *from* the survey, not the survey's own numbers — a different audience (anyone wanting to work better with AI today) from a different job (checking a figure). `index.html`'s Best Practices tab is a short pointer to it, not a copy — see [below](#tabs-in-indexhtml). |
| **`AI Usage Assessment — NICE UX Team(1-37).xlsx`** | **The raw data.** The untouched survey export (37 responses) from Microsoft Forms. Every figure in the report traces back to this file. It is never edited — corrections and derived values live in `index.html`, not here. ⚠️ **Held outside git** — see [Handling the raw data](#handling-the-raw-data). |
| **`AI Usage Assessment — NICE UX Team(1-37) — anonymized.xlsx`** | **The versioned copy of the raw data.** The same 37 responses with the `Email`, `Name` and `Your full name` columns removed — 68 of the original 71 columns, every answer cell identical to the export. This is the file in git, so any figure can be recomputed from the repository alone. Generated from the export, never edited by hand. |
| `PURPOSE.md` | This file. Why the project exists. |

**`index.html` is the main file** for the survey report itself. Do not create parallel or duplicate HTML pages that show the *same* content — earlier copies of the Best Practices section caused it to drift out of sync in three places, which is exactly why that content now lives in exactly one file (`best-practices.html`) with a pointer from `index.html`, not two copies kept in sync by hand.

### Handling the raw data

The survey export is the source of truth for every number we publish, and the data is versioned — but in two files, not one.

| | Full export | Anonymized copy |
|---|---|---|
| File | `…NICE UX Team(1-37).xlsx` | `…NICE UX Team(1-37) — anonymized.xlsx` |
| Columns | 71 | 68 — no `Email`, `Name`, `Your full name` |
| In git | **No** (`*.xlsx` rule) | **Yes** (negated back in) |
| Lives in | The OneDrive project folder | This repository |

**Why the split:** this repository is public, and the export carries an `Email` column, a `Name` column and a `Your full name` column next to the free-text answers. Respondents were told those answers were anonymous. A commit cannot be taken back — once pushed, the file remains in history and can be cloned or indexed even after it is deleted. The anonymized copy carries the answers without the three columns that attach them to a person, so the numbers stay checkable from the repository alone while the identities never enter it.

**How the copy is produced:** re-exported from the full export — the three identity columns dropped, all 68 remaining columns copied cell-for-cell (verified identical, 2,451 answer cells, 37 rows). It is regenerated from the export, never edited by hand, and never edited to correct data: corrections live in `index.html`.

**What the copy still contains, knowingly:** the free-text answers verbatim (checked — no respondent names, emails, URLs or phone numbers appear inside them), the `Start time` / `Completion time` / `Last modified time` stamps, and the region field (IN 17 · IL 11 · US 9). The timestamps are the one residual re-identification route: someone who knows when a colleague filled the form in could match a row. Drop those three columns too if that ever matters.

**If the full export itself ever needs to be versioned:** make the repository private *first*, then remove the `*.xlsx` rule.

These rules exist to enforce the anonymity principle below — they are not housekeeping.

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

**The arithmetic layer was removed on 2026-08-24** by explicit decision: the collapsed `🧮` blocks (raw response counts and exact sums, one per figure) made the page heavier than the audience needed. Checkability is preserved differently: every figure traces back to the raw survey export — **versioned in this repository since 2026-08-25 as the anonymized copy**, so it can be recomputed without asking anyone — and most arithmetic blocks live in this repository's **git history** (last committed version). Blocks can be restored per-figure if a claim is ever challenged — the `details.calc` CSS is intentionally kept in `index.html` for that case.

**One block has been restored under that exception** (2026-08-25): the "a third more tasks" rung of the ladder, where the challenge was direct — the number appeared on the page with no visible source. It is the only `details.calc` in `index.html`, and it stays the exception, not a reopening of the arithmetic layer.

### How weekly time shares are computed

Several published figures — the 34% for meetings, the 60/40 split, and the seven-activity breakdown in Conclusions — rest on one shared method, stated here once because it is not obvious from the page.

Respondents never reported hours. For each of seven activities they chose a **frequency band**; we take the **midpoint** of the band, average it across the 37 answers, and **normalise** the seven results to 100%.

| Band as asked | Midpoint used |
|---|---|
| Rarely (0–10%) | 5% |
| Sometimes (10–25%) | 17.5% |
| Often (25–50%) | 37.5% |
| Most of my week (50%+) | 60% |

**Normalisation is required, not cosmetic:** the bands overlap, so the seven raw averages total ~200% of a week. The published shares are each raw average divided by that total.

Two consequences worth knowing:

- The figures are **Measured** — they come only from answers — but they inherit the coarseness of the bands. Treat them as reliable in *rank order and rough size*, not to the decimal.
- The open-ended top band (`50%+`) is the weakest point: 60% is our reading of "most of my week", and someone at 80% is recorded as 60%. This compresses **Design**, the activity where the top band was chosen most often (16 of 37) — so if anything, design hours are understated and the non-design share is a *conservative* estimate.

The method is stated in plain words on the page itself, in the first card of the Conclusions "Lever 1" section.

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
| **Conclusions** | What keeping pace would take: the required speed (~2.7–2.8×, +45–50%) vs. the structural ~2× ceiling (judgement doesn't compress) — so the levers are elsewhere: cut/automate the non-hands-on 40%, and headcount. Lever 1 is then broken down: where the 17 non-design hours sit, which activities still have room, the five automation targets in order, and the honest admission that automation reaches only half of what is needed. |
| **Best Practices** | *A pointer, not the content* (since 2026-08-26). Three sentences and a button to `best-practices.html`, the standalone hub. The Champion dossiers, the 0/7 interview tracker and the decisions ledger did **not** move — they stay here, and the hub's own Champions section links back to this tab for the full picture. |

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
| **Raw data** | `AI Usage Assessment — NICE UX Team(1-37).xlsx` — the survey export (37 responses). Kept in the OneDrive project folder, **not in git**. The repository carries `…(1-37) — anonymized.xlsx` instead: same answers, identity columns removed (see [Handling the raw data](#handling-the-raw-data)) |
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
| 2026-08-25 | **Lever 1 broken down in Conclusions** — "cut or automate the non-hands-on 40%" was a slogan with four example activities; it is now five ranked targets. Adds: ① the 17 non-design hours located by activity (meetings 6.8, reviews 5.7, task management 4.6 — 43% of the week, all with zero AI today); ② the survey's **automatable vs. actually-automated** comparison across 8 activities, which shows 5 of 7 design activities already used **past** the team's own automatability judgement (ideation −18, wireframing −14) while **meeting notes scores 84/100 with no use case at all** — 25 of 37 said fully automatable and *nobody* said impossible, the only such item in the questionnaire; ③ the five targets in order (meeting notes · status reporting · pre-review checks · usability analysis · pre-handoff spec check) with what each frees; ④ the admission that automation reaches **3.7 of the 6.4 hrs needed** — the remaining 2.7 can only be *cut*, which is what hands over to the headcount lever; ⑤ the two preconditions the barriers data imposes (tokens 54%, quality 59% — hence starting where imperfect output is cheap). The gap comparison was also added to the "~2× max" step as an **independent confirmation of the ceiling from a different question** |
| 2026-08-25 | **Weekly-time method documented** — the band-midpoint-and-normalise rule behind the 34%, the 60/40 split and the new seven-activity table was previously unstated anywhere. Now specified in [How weekly time shares are computed](#how-weekly-time-shares-are-computed), with the `50%+` open band named as its weakest assumption (understates Design, so the non-design share is conservative), and restated in plain words on the page itself |
| 2026-08-25 | **Raw data is now versioned, as an anonymized copy.** `AI Usage Assessment — NICE UX Team(1-37) — anonymized.xlsx` enters the repository: the same 37 responses with `Email`, `Name` and `Your full name` dropped (68 of 71 columns, all 2,451 answer cells verified identical to the export). The full export stays out of git — the `*.xlsx` rule holds and the copy is negated back in. Chosen over making the repository private so the figures stay recomputable from the repository alone. Free text was checked for names, emails, URLs and phone numbers before committing; the submission timestamps are kept and noted as the one residual re-identification route |
| 2026-08-25 | **The self-perception matrix is published for the first time** (📊 card, Velocity tab). Four survey items that had never appeared anywhere on the page — *Number of tasks I take on* (91% increased, **0 decreased**), *Volume of work I produce* (84%), *Overall efficiency* (89%), *Quality of my output* (87%) — were until now used only implicitly, as the unattributed "a third more tasks" rung of the ladder. The rung is now sourced on its face, and the card separates what the survey says (*how many* people took on more — Measured) from what we add (*how much* more: "a little" priced at +25%, "significantly" at +50% — Our reading), which is the step's only assumption. **One `details.calc` block was restored** for it under the challenged-claim exception in the [two-layer rule](#show-the-working--in-two-layers) — the question "where does a third come from?" was asked and could not be answered from the page — carrying the per-answer counts, the +31% sum, its agreement with the ladder's 53 → 71, and a sensitivity check showing the conclusion holds at +22% too |
| 2026-08-26 | **Best Practices rebuilt from a direct analysis of the raw survey data**, not just the champion workflow cards. Added, in both `best-practices.html` and `index.html`'s mirrored tab (superseded same day — see next entry): a "Where We Stand" stats section (Pro-vs-Mid skill crosstabs on hours saved / review discipline / learning time — labeled correlational, not causal); a 4-level AI Maturity Model (Exploring → Using → Integrating → Optimizing) built from those same crosstabs; an 11-practice **Practice Library**, tiered Top/Scale/Quick-win/Advanced/Experiment, each practice carrying why-it-matters, workflow, before/after, benefit, level, tools, tip, anti-pattern and a cited evidence line using the site's existing Measured/Estimated/Our-reading badges; 2 new prompts operationalizing the top two practices (meeting-notes automation, design-system context brief); one sharpened Do (design-system context) grounded in the single most-repeated "wasted time" cause (8+ respondents); and a closing Knowledge-Sharing section (workshops, templates, champions, experiments-to-run) featuring the survey's own call for quality evals alongside speed metrics. Every claim traces to a specific column/crosstab in the anonymized xlsx or a counted free-text pattern — see the practice cards' evidence lines |
| 2026-08-26 | **`best-practices.html` rebuilt again, same day, as its own product** — a full visual and IA redesign, not a copy-editing pass. New design system ("Bone & Signal, elevated": same paper/ink/pine-teal identity, now with real depth, generous spacing and an editorial hero) and a new information architecture — Overview (hero + 5 survey insights each with a "what this means" implication + compact Maturity Model + 3 featured "Start Here" practices) → Best Practices (the 11-practice library, now searchable and filterable by tier/level, each card a native `<details>` accordion with an impact rating and a localStorage bookmark) → Workflows (the five named case studies, each with a Before→After→Result strip) → AI Champions (profile cards: what they're good at, what the team can learn — the 7th, Assaf Zinger, named and flagged as not yet documented here) → Examples (the prompt library) → Resources (tool stack, Do's/Don'ts, knowledge-sharing plan, a "Share a practice" CTA). Content carried over unchanged; evidence lines untouched. **`index.html`'s Best Practices tab was replaced with a pointer** to the new hub (see the [project-structure](#project-structure) entry) — the ~1,180 lines of duplicated markup are gone, closing the exact drift risk this file warns about above. The Champion dossiers, tracker and decisions ledger stay on that tab; only the Best Practices *content* moved |
