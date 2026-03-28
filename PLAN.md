# Bravo — simple plan

**Due:** May 4, 2026 (Canvas) · **Repo:** [github.com/LamiyaR/csc215-bravo-salary-ml](https://github.com/LamiyaR/csc215-bravo-salary-ml)

---

## What you are building

Train a model on job data that **has salaries** so you can **predict salary** from things like title, location, experience. Turn in **code**, **README.txt**, and a **6–8 page** paper (SCITEPRESS on Overleaf).

---

## What you turn in

| Item | Notes |
|------|--------|
| Zip | Folder name **`project {Group Name}`** per syllabus |
| Code | Commented; train + run predictions |
| README.txt | Steps that work on **Windows** if possible |
| Paper | Intro, related work, methods, results, discussion, conclusion, references |

Write dataset name, target column, split %, and seed in [`docs/DECISIONS.md`](./docs/DECISIONS.md) after meeting 1.

---

## Tools

| Use | For |
|-----|-----|
| This GitHub repo | Code and notebooks |
| Overleaf | Paper |
| Python + `venv` + `requirements.txt` | Running the project |
| Group chat + one video call / week | Coordination |

Optional: a **shared Google Sheet** with columns `Task | Owner | Done?` if you want a task list outside GitHub.

---

## Who owns what

| Member | Main notebook | Main paper parts |
|--------|---------------|------------------|
| **1** | `04_inference_demo.ipynb` (load model, predict) | Abstract, intro, conclusion, ack; **final PDF** and **Canvas zip** |
| **2** | `01_eda.ipynb` + short data notes in `docs/` | Related work, references, dataset part of methods |
| **3** | `02_preprocess.ipynb`; `requirements.txt`; README draft | Preprocess + transforms in methods |
| **4** | `03_train_eval.ipynb`; save **model file**; `figures/`, `results.csv` | Models + training + experiments / results |
| **5** | `05_qc_checks.ipynb`; test README on Windows | Discussion |

Member **2** helps write **meeting notes** in `docs/meetings/` (short bullet list each week is enough).

---

## Order of work

1. Member **2** — data + EDA.  
2. Member **5** — train/test split rules and leakage checks (write `docs/EVAL_PROTOCOL.md`).  
3. Member **3** — clean and encode data (fit on train only).  
4. Member **4** — features, train models, save model, metrics.  
5. Member **5** — double-check metrics; finish discussion.  
6. Member **1** — inference notebook, then zip + upload.

---

## Week by week

### Week 1
| Who | Focus |
|-----|--------|
| All | Fill `docs/DECISIONS.md` (dataset, target, novelty one line, seed) |
| 1 | Overleaf project; intro draft; meeting time |
| 2 | `01_eda` merged; start references |
| 3 | `requirements.txt`; repo folders |
| 4 | One baseline + one number on hold-out data |
| 5 | `docs/EVAL_PROTOCOL.md` |

### Week 2
| Who | Focus |
|-----|--------|
| 3 | `02_preprocess` merged; README draft |
| 2 | Dataset section of paper |
| 5 | Review preprocess for leakage |
| 4 | Plan features (team agrees) |

### Week 3
| Who | Focus |
|-----|--------|
| 4 | Full training, CV, XGBoost or LightGBM, `results.csv`, figures, **saved model** |
| 5 | QC notebook; paper numbers match repo |
| 1 | Check paper vs `results.csv` |

### Week 4
| Who | Focus |
|-----|--------|
| 1 | `04_inference_demo`; **practice zip**; run from fresh clone using README only |
| 5 | Windows README check; discussion draft |
| 3 + 5 | Final README |
| 1 | Conclusion |

### Week 5 (before due date)
| Who | Focus |
|-----|--------|
| All | Proofread paper |
| 1 | Final PDF, final zip, Canvas upload |

---

## Before you upload

- [ ] README works on a **clean** folder (or Windows machine)  
- [ ] Paper metrics = what is in `results.csv` / notebooks  
- [ ] 6–8 pages, SCITEPRESS  
- [ ] No syllabus-banned links in README or PDF  

---

## Notebook list

```
notebooks/01_eda.ipynb
notebooks/02_preprocess.ipynb
notebooks/03_train_eval.ipynb
notebooks/04_inference_demo.ipynb
notebooks/05_qc_checks.ipynb
```
