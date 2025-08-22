# ml-llm-365

A disciplined, 365-day machine-learning + LLM practice track. The goal is simple:
ship a tiny improvement **every day** (≈75 minutes) and log it.

## Repo layout
```text
ml-llm-365/
├─ notebooks/     # Daily notebooks; one per day (or topic)
├─ src/           # Reusable Python modules/utilities
├─ data/          # Local datasets (ignored by Git); keep tiny samples only
├─ experiments/   # Experiment notes/configs and outputs
├─ checks/        # Quick sanity scripts (eg. env check, data checks)
└─ notes/         # Learn logs, ideas, reading notes
```

## Quickstart

### 1) Create a Python environment
**Conda (recommended)**
```bash
conda create -n ml365 python=3.11 -y
conda activate ml365
pip install -r requirements.txt
python -m ipykernel install --user --name=ml365 --display-name "Python (ml365)"
```

**venv (built-in)**
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
python -m ipykernel install --user --name=ml365 --display-name "Python (ml365)"
```

### 2) VS Code / Jupyter
- In VS Code, select interpreter: **Python (ml365)**.
- Launch a notebook in `notebooks/` and pick the `Python (ml365)` kernel if prompted.

### 3) (Optional) pre-commit
Automatically format + lint on each commit.
```bash
pip install "pre-commit==3.*"
pre-commit install
# keep it fresh when needed
pre-commit autoupdate
```

## Daily flow (≈75 min template)
- **5 min** — Plan: pick one tiny target (readme/ticket in `notes/learnlog.md`).
- **45 min** — Build: a small notebook in `notebooks/` or a util in `src/`.
- **15 min** — Experiment: log results under `experiments/DATE-topic/`.
- **5 min** — Checks: run quick sanity scripts from `checks/`.
- **5 min** — Wrap: summarize learnings in `notes/learnlog.md`, commit & push.

### Naming suggestions
- Notebook: `notebooks/Day001-intro.ipynb` (or `YYYY-MM-DD-topic.ipynb`).
- Experiments: `experiments/Day001-intro/` with a short `README.md` and small artifacts.
- Data lives locally under `data/` (Git-ignored). Add tiny samples if needed.

### Quality gates
- Format: `black src notebooks`
- Lint: `ruff check .` (or `ruff check --fix .` to apply safe fixes)
- Keep notebooks lean (clear long outputs / plots when committing).

## First push to GitHub
```bash
git init
git add .
git commit -m "init: scaffold ml-llm-365"
# Option A: using GitHub CLI (recommended)
gh repo create ml-llm-365 --public --source=. --remote=origin --push
# Option B: manual
git remote add origin git@github.com:<your-username>/ml-llm-365.git
git branch -M main
git push -u origin main
```

---

**Tip:** If Jupyter doesn't show the `ml365` kernel, re-run:
```bash
python -m ipykernel install --user --name=ml365 --display-name "Python (ml365)"
```
