# CSC-215 (Spring 2026) — Project Bravo  
## Multimodal Workforce Analytics: Job Postings → Salary-Range Estimation

**Course:** Artificial Intelligence (CSC-215-02)  
**Instructor:** Dr. Bonaventure Chidube Molokwu  
**Official deadline:** 11:59 PM, Monday, May 4, 2026 (Canvas)  
**Group name:** project(Bravo)  
**Team size:** 5  

This document aligns the team on **what** you are building, **who** owns **what**, **when** it ships, and **how** you maximize rubric points (target: **A**).

---

## 1. What this project is (one paragraph)

Your client wants a **machine learning system** that learns from job-market data to **predict or estimate an actual salary range** for a given job posting. The solution should reflect real patterns: industry, role, location, skills, company signals, etc. The course requires **strong data work** (preprocessing, feature engineering, transformations), **rigorous training/validation**, **honest evaluation** (metrics, over/underfitting discussion), and a **polished, original research-style write-up** (6–8 pages) using the **SCITEPRESS** LaTeX conference template. You also deliver **runnable code**, a **`README.txt`** with run instructions (Windows preferred), and eventually a **zip** named per syllabus conventions.

**Novelty angle (pick one team narrative and stick to it):** e.g., multimodal fusion (tabular + text from job description), or careful handling of salary as censored/range labels, or geographic/industry normalization—document it clearly in the paper.

---

## 2. Official deliverables (from the assignment)

| Deliverable | Notes |
|-------------|--------|
| **Code folder** | Directory titled `project {Group Name}` per instructions; include datasets or clear download scripts, trained artifacts if allowed/size permits, commented code. |
| **README.txt** | How to run on **Windows** (preferred) and/or web; environment, commands, expected outputs. |
| **Research article** | **6–8 pages**, **SCITEPRESS** LaTeX template: Introduction → Lit review → Methods → Experiments/Results → Discussion → Conclusion/Future work → Acknowledgments → References. |
| **Canvas submission** | Single **.zip** before deadline; **20%/day** late penalty; >5 days late → 0. |

**Submission rules that affect your repo/website choices:**  
The brief says **no commercial URLs, webpages, or websites** in the submission—plan for **local + README instructions**, not “visit our startup landing page.” A **private GitHub org/repo** for collaboration is fine; **do not** put ad-like or commercial links inside the PDF/README you submit if the instructor treats that as a violation—keep README academic and minimal.

---

## 3. Grading rubric (where the A comes from)

| Criterion | Weight | What “excellent” looks like |
|-----------|--------|-----------------------------|
| Data preprocessing | 15% | Documented pipeline; missing values; leakage avoided; reproducible splits. |
| Feature engineering / representation learning | 15% | Clear features or learned representations; ablation or justification. |
| Data transformation | 10% | Scaling/normalization choices tied to models; before/after rationale. |
| Code quality & algorithm choice | 10% | Clean structure, sensible baselines → strong model; not random stacking. |
| Performance / evaluation metrics | 15% | Right metrics for regression (e.g., MAE, RMSE, MAPE); CV strategy; train vs val vs test discussion; over/underfitting. |
| Research article | 20% | Publication-style clarity, figures/tables, honest limitations. |
| Presentation & team cohesion | 15% | Roles visible, steady meetings, integrated story. |

**A strategy:** Nail **paper + evaluation + preprocessing/features** first—they are half the grade together with cohesion.

---

## 4. Roles — Member 1 through Member 5 (pick one slot each)

The assignment defines **four** role types; **five** slots below split work so one person focuses on **ML experiments** while another owns **PM + paper integration**. Each person **claims one Member number** for the project (see **`DETAILED_WORK_DISTRIBUTION.md`** for dependencies).

| Member slot | Maps to course role | Core responsibilities |
|-------------|---------------------|------------------------|
| **Member 1** | Project Manager | Schedule, agenda, risk log, milestones; **Overleaf** admin; **Introduction**, **Conclusion**, **Acknowledgments**; final SCITEPRESS compile; submission checklist; cohesion. |
| **Member 2** | Analyst | Dataset sourcing & licensing, EDA, requirements traceability (“rubric § → artifact”), **Related Work**, **References** (`.bib`), **Materials** (dataset part). |
| **Member 3** | Programmer | Preprocessing, features, transforms, repo layout, **`requirements.txt`**, **`README.txt`**, **Materials** (implementation part). |
| **Member 4** | ML/DL + experiments | Model comparison (e.g., sklearn + **XGBoost/LightGBM** vs optional **neural**), CV, metrics, **Experiments & Results** figures. |
| **Member 5** | Quality Control | Train/val/test rules, leakage checks, acceptance tests, **README** on Windows; **Discussion** (limitations, over/underfitting). |

*Note:* **One** person must take **Member 1** so submission and paper merge have a single owner.

**Useful pairings:** Member 1 + Member 2 (paper skeleton & references); Member 3 + Member 5 (pipeline vs evaluation); Member 4 + Member 2 (result tables).

---

## 5. Research paper — section owners (SCITEPRESS)

Draft in **Overleaf** (LaTeX); final in **SCITEPRESS template**.

| Section | Lead | Support |
|---------|------|---------|
| Introduction & problem statement | Member 1 | Member 2 |
| Review of literature & related work | Member 2 | Member 4 |
| Materials & methodology (data, prep, models) | Member 3 | Member 2, Member 4 |
| Experiments & results (tables, figures) | Member 4 | Member 5 |
| Discussion (interpretation, limitations) | Member 5 | Member 1 |
| Conclusion & future work | Member 1 | All |
| Acknowledgments | Member 1 | — |
| References (template style) | Member 2 | Member 1 |

**Everyone** reviews the final PDF for grammar (rubric mentions errors).

---

## 6. One-month execution timeline (aligned to May 4 deadline)

**“One month” sprint:** treat **Weeks 1–4** below as your intensive build; **Week 5** is buffer, polish, and pre-deadline freeze.

Assume start **~March 31, 2026** (adjust dates if you start earlier/later).

| Week | Dates (approx.) | Goals |
|------|-----------------|--------|
| **1** | Mar 31 – Apr 6 | Charter + dataset locked; EDA; baseline sklearn model; repo + `requirements.txt`; weekly meeting rhythm; risk: data access. |
| **2** | Apr 7 – Apr 13 | Full preprocessing doc; feature set v1; transformations; XGBoost/LightGBM baseline; first full draft of **Methods** + **Lit review** outline. |
| **3** | Apr 14 – Apr 20 | Advanced model(s) + CV; hyperparameter protocol; all **metrics** on hold-out; figures; **Experiments** draft; QC test matrix. |
| **4** | Apr 21 – Apr 27 | Error analysis; limitations; **Discussion**; README freeze; code comments; internal “mock submission” zip. |
| **5** | Apr 28 – May 3 | Paper polish, SCITEPRESS formatting, proofread; presentation dry-run; **final zip** + Canvas upload **before** May 4 11:59 PM. |

**Hard stops:**  
- **Apr 20:** model/experiment freeze (only bugfixes after).  
- **Apr 27:** feature freeze on code and paper content.  
- **May 3:** submission-ready build.

---

## 7. Where to store the project (GitHub vs Hugging Face)

| Option | Best for | Notes |
|--------|----------|--------|
| **GitHub (private org or private repo)** | **Source code**, issues, PRs, `README`, releases | **Default recommendation:** use **GitHub** for collaboration and version control; add `.gitignore` for large data; use **Git LFS** or **release assets** only if needed. |
| **Google Drive / Colab** | Shared notebooks, large files | Good for assets; pair with GitHub for “real” versioning. |
| **Hugging Face Hub** | **Publishing models/datasets** publicly | Useful if you want a **Model** card and **Dataset** card for portfolio **after** the course—or for team convenience with large files. **Not required** for CSC-215; your graded artifact is **Canvas zip**. If you use HF, keep the **course submission** self-contained and **non-commercial**. |

**Practical stack:** **Private GitHub repo** + optional **Hugging Face** dataset/model for backup/sharing—not a substitute for the required Canvas zip and README.

---

## 8. Definition of done (team is “on the same page”)

- [ ] One **primary dataset** + documented license and split strategy (no leakage).  
- [ ] Notebooks or scripts run top-to-bottom with fixed **random seeds**.  
- [ ] **README.txt** works on Windows per instructions.  
- [ ] **Rubric sections** explicitly mapped in the paper (preprocessing, features, transforms, training, metrics).  
- [ ] **6–8 pages** SCITEPRESS PDF, figures readable, references complete.  
- [ ] **Zip** structure: `project(Bravo)` or `project Bravo` exactly as syllabus states (`project {Group Name}`).  
- [ ] No disallowed commercial URLs in submitted materials.  
- [ ] Presentation slots prepared per syllabus when announced.

---

## 9. Team roster

**Five students on the course roster** should each sign up for **Member 1–5** in `DETAILED_WORK_DISTRIBUTION.md` (fill in the names table there). Keep the same mapping until the project is submitted unless the whole team agrees to swap.

---

## 10. Quick weekly standing agenda (15–20 min)

1. Blockers (data, compute, bugs)  
2. This week’s milestones vs §6  
3. Rubric gap check  
4. Paper: who owes which subsection by next meeting  
5. Action items with one owner each  

---

*Derived from CSC-215-02-P01 Project 01 brief (Multimodal Workforce Analytics). **Member 1** can be reassigned if the whole team agrees.*

---

## 11. See also

**[`DETAILED_WORK_DISTRIBUTION.md`](./DETAILED_WORK_DISTRIBUTION.md)** — agreed **platforms** (GitHub, Overleaf, Colab/Jupyter), **where to get datasets**, **parallel paper + code tracks**, **per-person tasks**, Git workflow, and rubric-to-owner mapping.
