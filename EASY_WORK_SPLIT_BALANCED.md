# Easy work split — 5 members, balanced load

Goal: **no one person** carries coding *and* the whole paper *and* PM. Each person has **one main code or analysis track** plus **one main paper section** (except the lead, who trades heavy coding for coordination).

Approximate balance: everyone targets **similar weekly hours**; heavy weeks rotate.

---

## Member 1 — Lead (coordination + paper front/back)

| Owns | Does *not* own (delegate) |
|------|---------------------------|
| Meeting agenda, deadlines, GitHub Issues/milestones | Writing all code alone |
| Overleaf setup & who edits which section when | Running every experiment alone |
| **Introduction** + **Conclusion** + **Acknowledgments** | EDA and model training as primary owner |
| Final PDF page check, submission zip checklist | — |
| Presentation outline / who speaks on what | — |

**Load tip:** Start Intro early (2 short paragraphs). Conclusion is short if results are stable by Week 3.

---

## Member 2 — Data & reading

| Owns | Does *not* own |
|------|----------------|
| Download/lock dataset, license note | Full training pipeline (that’s Member 4) |
| **EDA notebook** (missing data, simple plots, summary stats) | Preprocessing code (that’s Member 3) |
| **Related Work** + **References** (`.bib`) | Being the only person on Methods |
| **Materials — dataset description** subsection | — |

**Load tip:** EDA is bounded—stop when the team understands the target and obvious junk rows.

---

## Member 3 — Cleaning & numbers-for-the-model (preprocess + transforms)

| Owns | Does *not* own |
|------|----------------|
| **Preprocessing** code (missing values, outliers, text cleanup if any) | Choosing final models / hyperparameter search (Member 4) |
| **Transforms** (encoding, scaling) wired for training | Writing the whole paper |
| **`requirements.txt`** + **`README.txt` draft** (Member 5 verifies on Windows) | Literature review lead (Member 2) |
| **Methods** text that matches *this* code only | — |

**Load tip:** Keep one clean notebook or `preprocess.py` that Member 4 calls—avoid “mystery steps.”

---

## Member 4 — Features + models + results

| Owns | Does *not* own |
|------|----------------|
| **Feature engineering** (new columns, feature selection, optional title TF-IDF) | Project management (Member 1) |
| **Train** baselines + **XGBoost/LightGBM** (+ optional NN if team agrees) | Dataset hunting as sole owner (Member 2 helps define target) |
| **Cross-validation**, metrics, plots → `figures/` | Leakage protocol definition (Member 5 leads; Member 4 follows) |
| **Experiments & Results** in the paper | README Windows test (Member 5) |

**Load tip:** Use Member 3’s outputs as input; don’t fork a second preprocessing path.

---

## Member 5 — Rules, testing, honest limits

| Owns | Does *not* own |
|------|----------------|
| **Train/val/test** rules written down (ratios, random seed) | Building the full preprocess pipeline |
| **Leakage checks** (no cheating columns; fit encoders on train only) | Related Work lead |
| **Acceptance checklist** (e.g. “run from clean clone + README”) | Training all models alone |
| **README tested on Windows** (or designated Windows machine) | — |
| **Discussion** (overfitting, failure cases, limitations) | — |

**Load tip:** Start Week 1 with a **one-page** `docs/EVAL_PROTOCOL.md`; update when models exist.

---

## Who does what each week (simple)

| Week | Focus by member |
|------|-----------------|
| **1** | M2 EDA · M5 protocol doc · M1 agenda + Overleaf · M3 stub preprocess · M4 explore one baseline |
| **2** | M3 finish preprocess/transforms · M4 features + baseline metrics · M2 Related Work draft · M5 review for leakage · M1 Methods intro text coordination |
| **3** | M4 main models + CV + figures · M5 full QC pass · M2 polish dataset section · M3 README draft · M1 Experiments placeholders filled |
| **4** | M5 Discussion + Windows README · M4 error analysis · M1 Conclusion · everyone proofread |

---

## Balance check (use in a meeting)

Ask: **Who feels above ~8–10 hrs/week for two weeks in a row?** → Redistribute a *small* slice (e.g. one figure, one proofread pass) from that person.

---

*Pairs with `LEADER_KICKOFF_EASY_PLAN.md` and `DETAILED_WORK_DISTRIBUTION.md`.*
