# CSC-215 Project Bravo — Salary estimation from job postings

**Course:** CSC-215 (Spring 2026) · **Team:** 5 · **Canvas due:** May 4, 2026, 11:59 PM  

**GitHub:** [github.com/LamiyaR/csc215-bravo-salary-ml](https://github.com/LamiyaR/csc215-bravo-salary-ml)

---

## Start here

| Document | What it is |
|----------|------------|
| **[PROJECT_MASTER_PLAN.md](./PROJECT_MASTER_PLAN.md)** | **Main hub:** weekly deliverables, member×week matrix, Gantt + dependency diagrams, rubric map, **external progress tool (Notion/Trello)**, PM rituals, submission checklist |
| [PM_PROJECT_PLAYBOOK.md](./PM_PROJECT_PLAYBOOK.md) | SRS-style requirements, risks, PM weekly checklist |
| [LEADER_KICKOFF_EASY_PLAN.md](./LEADER_KICKOFF_EASY_PLAN.md) | Meeting 1 problem statement + decision table |
| [DETAILED_WORK_DISTRIBUTION.md](./DETAILED_WORK_DISTRIBUTION.md) | Member 1–5 deep dive: dependencies, notebooks, paper sections |
| [TEAM_PROJECT_PLAN.md](./TEAM_PROJECT_PLAN.md) | Short syllabus snapshot + paper section owners |
| [docs/EXTERNAL_PROGRESS_TRACKING.md](./docs/EXTERNAL_PROGRESS_TRACKING.md) | How to set up **Notion / Trello / Sheets** for tracking (besides GitHub) |
| [docs/DECISIONS.md](./docs/DECISIONS.md) | Living decision log — fill in Meeting 1 |
| [docs/WEEKLY_STATUS_TEMPLATE.md](./docs/WEEKLY_STATUS_TEMPLATE.md) | Copy-paste for meeting notes |

---

## Repo layout (as you build)

```
notebooks/
  01_eda.ipynb              # Member 2
  02_preprocess.ipynb       # Member 3
  03_train_eval.ipynb       # Member 4 (+ model artifact)
  04_inference_demo.ipynb   # Member 1
  05_qc_checks.ipynb        # Member 5
figures/
docs/
  meetings/                   # weekly notes
  DECISIONS.md
requirements.txt
README.txt                    # submission-style (Windows-friendly)
```

Final **Canvas** upload = zip of **`project {Group Name}`** per syllabus (can copy from this repo when ready).

---

## Setup (after `requirements.txt` exists)

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
```

## Clone

```bash
git clone https://github.com/LamiyaR/csc215-bravo-salary-ml.git
cd csc215-bravo-salary-ml
```

## License

[LICENSE](./LICENSE) (MIT).
