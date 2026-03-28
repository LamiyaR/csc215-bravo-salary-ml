# CSC-215 Project Bravo — Salary range estimation from job postings

Private course project (Spring 2026). Team workspace for code, notebooks, and planning docs.

## Docs (start here)

| File | Purpose |
|------|---------|
| [TEAM_PROJECT_PLAN.md](./TEAM_PROJECT_PLAN.md) | Deliverables, rubric, timeline |
| [DETAILED_WORK_DISTRIBUTION.md](./DETAILED_WORK_DISTRIBUTION.md) | Member 1–5 roles, dependencies, platforms |

## Repo layout (add as you build)

- `notebooks/` — EDA, preprocess, training
- `src/` — optional Python modules
- `figures/` — exports for the paper
- `requirements.txt` — pinned dependencies (Member 3)

Final Canvas submission will be a separate **`project {Group Name}`** zip per the syllabus; this repository is for collaboration and version control.

## Setup (when `requirements.txt` exists)

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
```

## Connect this folder to GitHub

This directory is already a **Git** repo (`main` branch). One teammate should:

1. On [github.com](https://github.com): **New repository** → name e.g. `csc215-bravo-salary-ml` → **Private** → create **without** README (this folder already has one).
2. In this folder, run (replace `YOUR_USER` and repo name):

```bash
cd "/Users/lamiyarampurawala/Downloads/CSC215-Bravo-SalaryML"
git remote add origin https://github.com/YOUR_USER/csc215-bravo-salary-ml.git
git push -u origin main
```

3. **Invite collaborators:** Repo → **Settings** → **Collaborators** → add teammates by GitHub username.

**SSH instead of HTTPS:** use `git@github.com:YOUR_USER/csc215-bravo-salary-ml.git` as `origin` if you use SSH keys.
