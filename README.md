# Machine Learning and Causal Inference Course

**Undergraduate course at Renmin University of China (中国人民大学)**

**Last Updated:** 2026-03-02

This repository contains materials for an undergraduate course on machine learning and causal inference. The course aims to lay the foundation for economics, finance, and management students to understand the theory, application, and programming skills in causal inference, machine learning, and their combinations.

The project uses the Claude Code academic workflow for structured course development with **Python + R + Quarto**.

This is a working course project using the [claude-code-my-workflow](https://github.com/zhiyuanryanchen/claude-code-my-workflow) template.

---

## Quick Start

### 1. Clone and Setup

```bash
git clone https://github.com/[USERNAME]/[REPO].git
cd [REPO]
```

### 2. Start Claude Code

```bash
claude
```

Claude will automatically read the configuration files in `.claude/` and follow the established workflow.

### 3. Project Configuration

All project settings are in `CLAUDE.md`:
- **Project:** Machine Learning and Causal Inference Course
- **Institution:** Renmin University of China
- **Domain:** Econometrics, Causal Inference, Machine Learning
- **Quality Gates:** 80/90/95 thresholds

---

## Course Overview

### Learning Objectives

1. Understand the potential outcomes framework and core identification strategies
2. Master classical econometric methods: RCT, IV, RD, DID
3. Learn machine learning methods for causal inference: Double ML, Causal Forests
4. Develop programming skills in both Python and R
5. Apply methods to real-world economic problems
6. Demonstrate AI-assisted research workflow in the modern era

### Core Topics

| Module | Topics | Methods |
|--------|--------|---------|
| **1. Foundations** | Potential outcomes, DAGs, selection bias | Rubin model, Pearl framework |
| **2. Experiments** | Randomization, balance, compliance | RCT, A/B testing |
| **3. IV** | Exclusion restriction, relevance, LATE | 2SLS, weak instruments |
| **4. RD** | Continuity, fuzzy RD, bandwidth | Local polynomial |
| **5. DID** | Parallel trends, event studies, staggered | Two-way FE, Callaway-Sant'Anna |
| **6. ML Basics** | Prediction vs causation, cross-validation | Regularization, ensembles |
| **7. Double ML** | Neyman orthogonality, sample splitting | Partially linear model |
| **8. Heterogeneous Effects** | CATE estimation, policy targeting | Causal forests, meta-learners |

### Repository Structure

```
.
├── Lectures/           # Lecture slides (Beamer LaTeX)
├── Labs/               # Hands-on lab sessions (Python/R)
├── Assignments/        # Problem sets with solutions
├── Data/               # Example datasets (documented)
├── Code/               # Reproducible examples (Python + R)
├── Figures/            # Generated figures
├── Quarto/             # RevealJS slides
├── docs/               # GitHub Pages
├── .claude/            # Workflow configuration
└── quality_reports/    # Session logs and plans
```

---

## Workflow Features

### Contractor Mode

You describe a teaching task. For complex or ambiguous requests, Claude creates a requirements specification with MUST/SHOULD/MAY priorities. You approve the spec, then Claude plans, implements, runs specialized review agents, fixes issues, re-verifies, and scores against quality gates — all autonomously.

**Example:** "Create Lecture 3 on Directed Acyclic Graphs with worked examples from labor economics." → Claude creates spec → You approve → Claude implements lecture with TikZ diagrams, examples, and code.

### Specialized Agents for Teaching

- **ml-causal-reviewer** — Identification validity, DAG correctness, ML-causal alignment
- **r-reviewer** — R code quality, reproducibility, econometric correctness
- **python-reviewer** — Python code quality, ML best practices
- **proofreader** — Academic writing quality (supports Chinese)
- **slide-auditor** — Presentation layout (for lectures)
- **pedagogy-reviewer** — Teaching effectiveness, pacing, clarity

### Quality Gates

Every deliverable gets a score (0–100):
- **80** — commit threshold (save progress)
- **90** — PR threshold (share with students)
- **95** — excellence (publication-ready)

### Teaching-Specific Features

- **Plan-first workflow** — Plan mode for lecture/lab creation
- **Session logging** — Teaching decisions preserved across sessions
- **Quality reports** — Track progress and improvements
- **Both Python and R** — Equal support for both languages

---

## Key Configuration Files

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Course overview, notation, folder structure |
| `.claude/rules/knowledge-base-ml-causal.md` | Domain knowledge: potential outcomes, DAGs, ML methods |
| `.claude/agents/ml-causal-reviewer.md` | Customized 5-lens review for causal inference |
| `.claude/rules/r-code-conventions.md` | R and Python coding standards |
| `.claude/WORKFLOW_QUICK_REF.md` | Non-negotiables and preferences |
| `Quarto/ruc-clean.scss` | RUC institutional theme (#AE0B2A red)

---

## Prerequisites

| Tool | Required For | Install |
|------|-------------|---------|
| [Claude Code](https://code.claude.com/docs/en/overview) | Everything | `npm install -g @anthropic-ai/claude-code` |
| XeLaTeX | LaTeX compilation | [TeX Live](https://tug.org/texlive/) or [MacTeX](https://tug.org/mactex/) |
| [Quarto](https://quarto.org) | Presentation slides | [quarto.org/docs/get-started](https://quarto.org/docs/get-started/) |
| R | Econometric analysis | [r-project.org](https://www.r-project.org/) |
| Python | ML analysis | [python.org](https://www.python.org/) or Anaconda |
| [gh CLI](https://cli.github.com/) | PR workflow | `brew install gh` (macOS) |

Claude Code is the only hard requirement; install others as needed.

---

## Available Skills

| Command | What It Does |
|---------|-------------|
| `/review-r [file]` | R code quality and reproducibility review |
| `/review-python [file]` | Python code quality review |
| `/data-analysis [dataset]` | End-to-end analysis with publication-ready output |
| `/proofread [file]` | Academic writing review |
| `/create-lecture` | Create new lecture slides |
| `/create-lab` | Create hands-on lab session |
| `/pedagogy-review [file]` | Teaching effectiveness review |
| `/slide-excellence [file]` | Multi-agent review for presentations |
| `/validate-bib` | Cross-reference citations |
| `/commit [msg]` | Stage, commit, PR, merge |

---

## Teaching Workflow Commands

```bash
# Compile LaTeX lecture
cd Lectures && xelatex lecture.tex && bibtex lecture && xelatex lecture.tex && xelatex lecture.tex

# Run R analysis with renv
Rscript -e "renv::restore(); source('Code/example_analysis.R')"

# Run Python analysis
python Code/example_ml.py

# Quality score
python scripts/quality_score.py Quarto/file.qmd
```

---

## Course Status

| Component | Status | Notes |
|-----------|--------|-------|
| Lecture 1: Intro | Planned | Potential outcomes framework |
| Lecture 2: RCTs | Planned | Randomized experiments |
| Lecture 3: DAGs | Planned | Directed acyclic graphs |
| Lecture 4: IV | Planned | Instrumental variables |
| Lecture 5: RD | Planned | Regression discontinuity |
| Lecture 6: DID | Planned | Difference-in-differences |
| Lecture 7: ML Basics | Planned | Prediction vs causation |
| Lecture 8: Double ML | Planned | Debiased machine learning |
| Labs 1-3 | Planned | Python/R setup, simulations |

---

## Documentation

See `.claude/rules/` for detailed workflow documentation:
- `knowledge-base-ml-causal.md` — Domain knowledge and notation
- `constitutional-governance.md` — Immutable teaching principles
- `plan-first-workflow.md` — When and how to use plan mode
- `r-code-conventions.md` — R and Python coding standards

---

## Contact

[Your contact information]

---

**Powered by:** [claude-code-my-workflow](https://github.com/zhiyuanryanchen/claude-code-my-workflow) — Multi-agent academic workflow template.
