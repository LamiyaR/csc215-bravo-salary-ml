# CSC-215 Bravo — Easy team plan (for the lead)

Use this in **Meeting 1**: read the **problem** and **decisions** out loud. Everyone signs the decision table at the bottom (or replies “agree” in chat). After that, **no silent changes**—if something must change, the **whole team** agrees in writing.

**GitHub:** [github.com/LamiyaR/csc215-bravo-salary-ml](https://github.com/LamiyaR/csc215-bravo-salary-ml)

---

## 1. What we are doing (one clear problem)

**Problem (plain English):**  
Job ads usually show the role, place, and skills, but **salary is often missing or vague**. We build a **machine learning model** that learns from **past job records that do include salary** and then **estimates a salary (or range)** for similar jobs.

**Who cares:** job seekers, HR benchmarking, course requirement.

**What “success” means for us:**  
A **working Python pipeline** (load data → clean → features → train → evaluate) plus a **short research-style paper** that explains every step honestly, with **real numbers** (errors, overfitting discussion).

---

## 2. What we must deliver (official + simple checklist)

| # | Deliverable | What it is |
|---|-------------|------------|
| 1 | **Code folder** | Named like the syllabus: **`project {Group Name}`** in the final **.zip** (for Canvas). Inside: notebooks or scripts, **commented code**, how to get/run data. |
| 2 | **README.txt** | Step-by-step: install Python, install packages, run training, run prediction. **Windows** instructions are preferred. |
| 3 | **Research paper** | **6–8 pages**, **SCITEPRESS LaTeX** template: intro, related work, methods, results, discussion, conclusion, references. |
| 4 | **Canvas upload** | One **.zip** before **May 4, 2026, 11:59 PM**. No late days if you want full credit. |

**Grading buckets (so we don’t skip anything):**  
clean data → good features → scaling/encoding → smart model choice → strong evaluation + discussion → clear paper → team looks organized in presentation.

---

## 3. Everything decided by the team (fill this in Meeting 1)

**Rule:** The lead proposes the **defaults** below. The team votes **yes / change**. Write the final answer in the **Final team choice** column.

### 3.1 Dataset

| Topic | Default proposal (if team agrees) | Final team choice (write here) |
|-------|-------------------------------------|--------------------------------|
| **Primary dataset** | **[Kaggle — “Data Science Job Salaries”](https://www.kaggle.com/datasets)** (search that title; use the version the team downloads together). It has role, experience, employment type, company size, **salary_in_usd**, region—**good for a clean first pipeline**. | |
| **Backup if blocked** | Any Kaggle CSV with **job title + location + numeric salary**; team picks **one** and sticks to it. | |
| **License** | Only use data **allowed for class / academic** use; screenshot or note the license in the paper. | |
| **Where stored** | Raw data **not** in GitHub if huge; use **download script** or README steps + `.gitignore` (already in repo). | |

*If the team wants more “job posting text,” you can add a **second** column or dataset later only if **Member 3 + Member 5** agree there is **no data leakage** and there is **time**.*

### 3.2 Target variable (what the model predicts)

| Topic | Default proposal | Final team choice |
|-------|------------------|-------------------|
| **Target** | **Single number:** `salary_in_usd` (or the dataset’s main salary column). | |
| **If only ranges exist** | Predict **midpoint** of range and state that in the paper. | |

### 3.3 Novelty (our “original angle” — keep it simple and true)

Pick **one** sentence the whole team repeats in presentation and paper.

| Option | One-sentence novelty (example) |
|--------|--------------------------------|
| **A (recommended)** | “We build a **leakage-safe** pipeline and show how **region + experience + role features** affect salary prediction errors, with **clear baselines** vs **gradient-boosted trees**.” |
| **B** | “We add **simple text features** from job title (e.g. TF-IDF) **on top of** tabular features and report whether they **actually help**.” |
| **C** | Team writes a **custom** sentence (must be **honest** and **supported by your experiments**). | |

**Final novelty sentence (copy into paper intro):**  
_______________________________________________________________________________

### 3.4 Models (minimum set — enough for a good grade)

| Step | Model / action |
|------|----------------|
| Baseline | Linear regression (or similar) on encoded features |
| Main model | **XGBoost** or **LightGBM** (course names these) |
| Optional | Small neural net **only if** someone has time and can explain it |

### 3.5 Metrics (how we say “good” or “bad”)

| Metric | Use for |
|--------|---------|
| **MAE** | Dollars wrong on average (easy to explain) |
| **RMSE** | Punishes big errors |
| **R²** | How much variance we explain (report carefully) |

### 3.6 Split strategy (avoid cheating the grade)

| Rule | Default |
|------|---------|
| **Train / validation / test** | e.g. **70 / 15 / 15** or **80 / 10 / 10** — **one** fixed split + **cross-validation** on train for tuning |
| **Leakage** | No column that **contains the answer** or is built using **test rows** (Member 5 checks this) |

### 3.7 Tools (everyone uses the same)

| Tool | Choice |
|------|--------|
| Language | **Python 3.10+** |
| Notebooks | **Jupyter** or **Colab** |
| Repo | **GitHub** (this project) |
| Paper | **Overleaf** + **SCITEPRESS** template |

---

## 4. Work split — 5 members (simple)

Each person has **one main hat**. Help others **only after** your main tasks move.

| Member | Main hat | Main jobs (plain English) |
|--------|----------|---------------------------|
| **Member 1 — Lead (you)** | Coordinator + paper glue | Meetings, deadlines, **Overleaf** admin, **Introduction & Conclusion**, final PDF check, Canvas zip checklist. |
| **Member 2** | Data + reading | Pick/lock dataset with team, **EDA** (plots, missing data), **Related Work** + references in paper, **dataset section** of Methods. |
| **Member 3** | Code pipeline | **Preprocessing**, encoding, scaling, **README.txt**, `requirements.txt`, **Methods** (what the code does—must match the repo). |
| **Member 4** | Models + results | Train baselines + XGBoost/LightGBM, **cross-validation**, tables and figures, **Experiments & Results** in paper. |
| **Member 5** | Quality | Define **train/test rules**, check **leakage**, test **README on Windows**, **Discussion** (limits, overfitting) in paper. |

### Order of work (who waits for whom)

1. **Member 2** shares data description → **Member 5** approves split/leakage rules.  
2. **Member 3** builds cleaning + features using those rules → **Member 4** trains models.  
3. **Member 4** shares numbers → **Member 5** checks + **Member 1** updates paper story.  
4. **Member 1** pulls everything into one paper and one zip.

---

## 5. Four-week rhythm (easy)

| Week | Team goal |
|------|-----------|
| **1** | Fill **Section 3** of this doc; EDA done; baseline model runs; Overleaf project created. |
| **2** | Full preprocessing + features; Methods draft matches code. |
| **3** | Main model + CV + all metrics; Results section has real tables/figures. |
| **4** | Discussion, polish, README test, **mock zip**; Week 5 buffer before May 4. |

---

## 6. “Same page” check — ask before you leave Meeting 1

- [ ] We all say the **problem** in one sentence without reading.  
- [ ] We all know the **dataset name** and who downloads it (**Member 2**).  
- [ ] We all know the **novelty sentence**.  
- [ ] We all know **due date** and **what goes in the zip**.  
- [ ] Everyone has **GitHub access** to the repo.

---

## 7. Team sign-off (decisions locked)

We agree the **Final team choice** rows in §3 are correct as written below. Changes require **everyone** to agree in chat/email.

| Name | Role (Member 1–5) | Signature or “Agree + date” |
|------|-------------------|-----------------------------|
| | | |
| | | |
| | | |
| | | |
| | | |

---

*This is the “easy” plan. More detail lives in `TEAM_PROJECT_PLAN.md` and `DETAILED_WORK_DISTRIBUTION.md`.*
