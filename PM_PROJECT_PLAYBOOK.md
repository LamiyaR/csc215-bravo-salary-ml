# Project Management Playbook — CSC-215 Bravo (5 people, ~1 month)

> **Operational hub (week-by-week deliverables, diagrams, Notion/Trello tracking):** **[PROJECT_MASTER_PLAN.md](./PROJECT_MASTER_PLAN.md)**  
> This file focuses on **SRS-style requirements**, **risks**, and **PM habits**.

**Audience:** Team lead / project manager  
**Scope:** ML salary-estimation project + SCITEPRESS paper + Canvas submission  
**Assumption:** ~4 intensive weeks + a short buffer before the course deadline  

This document is how I would run the project **end-to-end**: platforms, requirements (SRS-style), work split, alignment rituals, deliverables, and timeline.

---

## 1. How I would run it (executive summary)

1. **Freeze decisions early** — dataset, target variable, novelty sentence, train/test rules, and tool stack by end of **Week 1**. No “mystery scope” in Week 3.  
2. **Run two tracks in parallel** — **Engineering** (notebooks → model → demo) and **Paper** (Overleaf sections filling as facts appear).  
3. **Make ownership binary** — every task has **one** owner; reviewers are named, not “the group.”  
4. **Ship thin vertical slices weekly** — each week ends with something **runnable** and something **written**, not half of five things.  
5. **Protect integration time** — the lead (or a rotating integrator) runs a **dry-run from clean clone** before submission; that’s where student projects usually break.  

---

## 2. Platforms & tooling (what I would standardize)

| Need | Choice | Why |
|------|--------|-----|
| **Source control** | **GitHub** (private) | Branches, history, accountability; required for any serious team. |
| **Work tracking** | **GitHub Issues** + **Milestones** (one per week) | Lightweight; links to PRs; no extra SaaS unless the team loves Notion. |
| **Python** | **3.10+**, **`venv`**, pinned **`requirements.txt`** | Reproducible; easy to defend in Methods. |
| **Notebooks** | **Jupyter** locally or **Colab** (agree on one default) | Matches syllabus; export `.ipynb` into repo. |
| **Paper** | **Overleaf** + **SCITEPRESS** template | Single PDF truth; version history. |
| **References** | **BibTeX** in Overleaf (one `.bib` curator) | Avoid citation chaos. |
| **Chat** | One channel only (Discord / Slack / WhatsApp) | Reduce “I didn’t see that.” |
| **Video** | One standing meeting / week + optional 15 min mid-week | Enough sync without burnout. |
| **Large data** | **Not** in git without **Git LFS**; prefer **download script** + `.gitignore` | Keeps repo cloneable. |

**Rule I would enforce:** Anything the grader must run is described in **`README.txt`** and verified on **Windows** at least once before submit.

---

## 3. Keeping everyone on the same page (rituals & artifacts)

### 3.1 Standing meeting (45–60 min, same slot every week)

**Agenda (fixed order):**

1. **Decisions** (5 min) — only reopen if *everyone* agrees (see §8).  
2. **Demo** (10 min) — what ran since last week (one person shares screen).  
3. **Blockers** (10 min) — owner + helper assigned per blocker.  
4. **Rubric / SRS check** (10 min) — “Which requirement did we prove this week?” (traceability).  
5. **Paper** (10 min) — which sections moved; no new claims without a number or figure.  
6. **Actions** (5 min) — each action: **one owner**, **due date**.  

### 3.2 Async discipline

- **# of open PRs ≤ 3** — merge or close; avoid long-lived branches.  
- **Decision log** — one file in repo: `docs/DECISIONS.md` (date, decision, rationale). No arguments from memory.  
- **Definition of Ready** — a task is ready when inputs exist (e.g., “preprocess notebook merged to `main`”).  

### 3.3 “Same page” test (I would use every Friday)

Each person states **without notes**:

- What the **target** is we predict.  
- What **dataset** we use.  
- What **one sentence** is our novelty/contribution.  
- What **due next week** for them personally.  

If anyone hesitates, the PM stops and fixes clarity before anyone codes further.

---

## 4. SRS-style requirements (what “done” means technically)

Below is a **lightweight SRS**: enough for a course project, mapped to grading expectations. Formal IEEE-style numbering helps traceability.

### 4.1 Problem & scope

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-01** | System estimates **salary** (or agreed proxy) from **job-related features**. | Hold-out evaluation produces numeric predictions for all test rows with valid inputs. |
| **REQ-02** | Pipeline is **reproducible**. | Fixed random seeds; documented split; second person can rerun and match metrics within small tolerance. |
| **REQ-03** | **No leakage** from test into training. | Documented rules; QC notebook checks for forbidden columns and fit/transform scope. |

### 4.2 Data

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-10** | Primary dataset **locked** with **license** noted. | Citation + license in paper; path or download steps in README. |
| **REQ-11** | **EDA** documents missingness and basic distributions. | Notebook + short subsection in Materials. |

### 4.3 Preprocessing & transformation

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-20** | Missing data handled with **stated strategy**. | Methods text matches code. |
| **REQ-21** | Categorical/numeric handling + **scaling/encoding** justified. | Named techniques (e.g., one-hot, standard scaler) tied to model needs. |

### 4.4 Feature engineering / representation

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-30** | **Feature engineering** or representation steps documented. | List of features or representation; optional ablation or importance discussion. |

### 4.5 Modeling & training

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-40** | At least **one baseline** + **one strong** model (e.g., tree ensemble). | Both trained with same split protocol. |
| **REQ-41** | **Validation strategy** documented (CV or hold-out). | Stated k or split; hyperparameter search bounded and described. |

### 4.6 Evaluation

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-50** | Report **MAE**, **RMSE**, and **R²** (or justify substitutes). | Tables with **real numbers** on test set. |
| **REQ-51** | Discuss **over/underfitting** with evidence. | Train vs val/test gap or learning curves / residuals referenced in Discussion. |

### 4.7 Application / usability (course asks for user-friendly solution)

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-60** | **Inference path** exists (notebook or script). | Loads saved model; runs on sample rows; output readable table. |
| **REQ-61** | **README.txt** enables run on **Windows** (preferred). | Non-author follows README on a clean machine; issues logged and fixed. |

### 4.8 Paper (research article)

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-70** | **6–8 pages**, SCITEPRESS format. | PDF page count verified. |
| **REQ-71** | Sections: Intro, Lit review, Methods, Results, Discussion, Conclusion, Refs. | Completeness checklist signed. |
| **REQ-72** | Claims match code/results. | PM + QC pass: no metric in paper without notebook/CSV backing. |

### 4.9 Submission

| ID | Requirement | Acceptance criteria |
|----|-------------|----------------------|
| **REQ-80** | Single **.zip** to Canvas; folder naming per syllabus. | Dry-run zip contents list reviewed. |
| **REQ-81** | **No disallowed commercial URLs** in submitted materials. | README + PDF scan for policy violations. |

---

## 5. Work distribution (5 members — balanced PM model)

I would use **one primary notebook per person** + **one major paper chunk** + **shared** final proofread.

| Role | Engineering ownership | Paper ownership | Integrates with |
|------|----------------------|-----------------|-----------------|
| **Lead (PM)** | Inference demo notebook/script; end-to-end dry run before zip | Abstract, Intro, Conclusion, Ack; final LaTeX compile | Member 4 (model artifact), Member 5 (README OK) |
| **Member 2** | EDA notebook; data dictionary | Related Work; References; Materials (dataset) | Member 5 (leakage), Member 3 (schema) |
| **Member 3** | Preprocess + transforms; `requirements.txt`; README draft | Materials (preprocessing & transformations) | Member 5 (split rules, README sign-off) |
| **Member 4** | Feature engineering + train/eval; save model; figures | Materials (models/training); Experiments & Results | Member 1 (handoff), Member 5 (metrics) |
| **Member 5** | QC notebook; Windows README validation | Discussion | Everyone (factual gate) |

**Admin load:** PM runs meetings; **Member 2 co-scribes** minutes so PM isn’t the only person doing invisible work.

---

## 6. Deliverables matrix (who / what / when)

| Deliverable | Primary owner | Backup / reviewer | Due (suggested) |
|-------------|---------------|-------------------|-----------------|
| Dataset locked + license | Member 2 | Member 5 | End Week 1 |
| EDA notebook | Member 2 | Member 3 | End Week 1 |
| Split & leakage protocol doc | Member 5 | Member 4 | End Week 1 |
| Preprocess notebook merged | Member 3 | Member 5 | Mid Week 2 |
| Feature + train notebook + model file | Member 4 | Member 5 | End Week 3 |
| Inference demo notebook | Member 1 | Member 4 | Early Week 4 |
| README.txt validated Windows | Member 5 | Member 3 | Mid Week 4 |
| Paper first full draft | All section leads | PM | End Week 3 |
| Paper final PDF | PM | All | 3 days before deadline |
| Mock Canvas zip | PM | Member 5 | 5 days before deadline |
| Final Canvas zip | PM | — | Before deadline |

---

## 7. Timeline — 1 month (4 + 1 buffer weeks)

Assume **Week 5** is polish only (presentation prep, typo pass, sleep).

| Week | Engineering goals | Paper goals | Milestone (“done”) |
|------|-------------------|-------------|---------------------|
| **1** | Repo hygiene; data ingest; baseline sanity model | Intro draft; Related Work outline; problem frozen | **Decision log** filled; EDA + baseline run |
| **2** | Preprocess + transforms stable; feature v1 | Materials (data + prep) drafted | Member 4 can train without rework |
| **3** | Main models + CV; figures + `results.csv` | Experiments & Results populated | Numbers frozen except bugfixes |
| **4** | Inference demo; QC; README Windows pass | Discussion + Conclusion; full proofread | **Mock zip** passes dry run |
| **5 (buffer)** | Only bugfixes | Format SCITEPRESS; cut to page limit | **Final submit** |

**Hard stops I would enforce:**

- **End Week 3:** model/feature freeze (no new ideas).  
- **End Week 4:** code freeze except README/integration.  
- **2–3 days before due:** paper freeze except typos.  

---

## 8. Governance — how decisions get made

**Categories:**

- **Type A (irreversible):** dataset choice, target definition, novelty sentence → **unanimous** or majority with dissent logged in `DECISIONS.md`.  
- **Type B (reversible):** hyperparameters within a band, plot style → **owner decides**, informed by Member 5 metrics rules.  
- **Type C (paper wording):** PM has tie-breaker **only** if a claim is **unsupported**; QC (Member 5) wins on **factual** accuracy.  

---

## 9. Risk register (what usually kills team projects)

| Risk | Early signal | Mitigation |
|------|--------------|------------|
| Dataset access / license fights | Week 1 drama | Pick backup dataset in Week 1 decision meeting |
| One person becomes “the only coder” | PRs only from one account | Enforce notebook-per-person; PM escalates in Week 2 |
| Paper written last weekend | Empty Experiments in Week 3 | Weekly paper stub + “no TBD metrics after Week 3” |
| Leakage / inflated metrics | “Too good” R² | Member 5 protocol + independent rerun |
| Integration failure | README never tested | Windows walkthrough mid Week 4 |
| Scope creep (deep learning rabbit hole) | Week 3 still “trying models” | Cut to baseline + one strong model per §4.5 |

---

## 10. PM weekly checklist (personal — for you)

- [ ] Milestone in GitHub Issues is **closed** or **re-scoped** with team agreement.  
- [ ] `docs/DECISIONS.md` updated if anything changed.  
- [ ] One **merged PR** that improves **vertical slice** (not just docs).  
- [ ] Paper: **no new claims** without figure/table reference.  
- [ ] **Friday same-page test** completed.  
- [ ] Next week’s **three top risks** named aloud.  

---

## 11. Final submission rehearsal (non-negotiable)

**48–72 hours before due**, I would run:

1. Fresh clone into a new folder.  
2. Follow **only** `README.txt`.  
3. Run preprocess → train → inference demo.  
4. Open paper PDF side-by-side with **results.csv** — every number cross-checked.  
5. Build zip exactly as Canvas expects; open zip and spot-check paths.  

If anything fails, **stop features**; fix integration until green.

---

## 12. Relationship to your other team docs

- **`PROJECT_MASTER_PLAN.md`** — **primary** schedule, weekly IDs, diagrams, external tracker how-to.  
- `LEADER_KICKOFF_EASY_PLAN.md` — short Meeting 1 sheet.  
- `TEAM_PROJECT_PLAN.md` — syllabus snapshot.  
- `DETAILED_WORK_DISTRIBUTION.md` — dependency deep dive.  

Use this playbook for **requirements & risks**; use the master plan for **dates and tasks**.

---

*End of playbook.*
