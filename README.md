# Intellectual Property Financing, R&D Investment, and Aggregate TFP

**Research project at Renmin University of China**

**Last Updated:** 2026-02-24

This repository contains research on how intellectual property financing affects aggregate TFP through R&D investment and misallocation-reduction channels. The project uses the Claude Code academic workflow for structured research development with **LaTeX + R + Quarto**.

This is a working research project using the [claude-code-my-workflow](https://github.com/pedrohcgs/claude-code-my-workflow) template.

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
- **Project:** Intellectual Property Financing, R&D Investment, and Aggregate TFP
- **Institution:** Renmin University of China
- **Domain:** Macroeconomics, Innovation Economics
- **Quality Gates:** 80/90/95 thresholds

## Research Overview

### Core Research Questions

1. How does IP financing affect R&D investment at the firm level?
2. What are the aggregate TFP implications of improved IP financing?
3. How much of TFP growth can be explained by reduced misallocation through IP collateralization?

### Theoretical Framework

The project builds on:
- **Endogenous growth theory** (Romer 1990, Grossman-Helpman 1991)
- **Misallocation literature** (Hsieh-Klenow 2009)
- **Financial frictions and innovation** (Mann 2018, Brown et al. 2009)

### Empirical Strategy

- **Data:** Compustat, USPTO patent data, China firm census
- **Methods:** TFP decomposition, panel regression, quantitative model
- **Identification:** Difference-in-differences around collateral reforms

### Repository Structure

```
.
├── Paper/              # Paper drafts (LaTeX)
├── Models/             # Model documentation
├── Empirical/          # Analysis scripts
│   ├── data/          # Datasets (documented)
│   └── R/             # R scripts
├── Figures/           # Generated figures
├── Quarto/            # Presentation slides
├── .claude/           # Workflow configuration
└── quality_reports/   # Research logs
```

---

## Workflow Features

### Contractor Mode

You describe a research task. For complex or ambiguous requests, Claude creates a requirements specification with MUST/SHOULD/MAY priorities. You approve the spec, then Claude plans, implements, runs specialized review agents, fixes issues, re-verifies, and scores against quality gates — all autonomously.

**Example:** "Analyze how patent collateral affects R&D investment using the Mann (2018) approach." → Claude creates spec → You approve → Claude implements analysis with replication package.

### Specialized Agents for Research

- **domain-reviewer** — Model assumptions, derivation correctness, identification (macro/innovation econ specialized)
- **r-reviewer** — R code quality, reproducibility, econometric correctness
- **proofreader** — Academic writing quality
- **slide-auditor** — Presentation layout (for talks)

### Quality Gates

Every deliverable gets a score (0–100):
- **80** — commit threshold (save progress)
- **90** — PR threshold (share with coauthors)
- **95** — excellence (submission-ready)

### Research-Specific Features

- **Replication protocol** — Replicate before extending; strict tolerance thresholds (1e-6)
- **Exploration folder** — `explorations/` for experimental analysis (60/100 threshold)
- **Data provenance tracking** — All datasets documented in `Empirical/data/README.md`
- **Session logging** — Research decisions preserved across sessions

## Key Configuration Files

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Project overview, notation, folder structure |
| `.claude/rules/knowledge-base-ip-financing.md` | Domain knowledge: notation, models, pitfalls |
| `.claude/rules/constitutional-governance.md` | Immutable principles (replication-first, quality gates) |
| `.claude/WORKFLOW_QUICK_REF.md` | Non-negotiables and preferences |
| `.claude/agents/domain-reviewer.md` | Customized 5-lens review for macro/innovation econ |
| `Quarto/ruc-clean.scss` | RUC institutional theme (#AE0B2A red)

---

## Prerequisites

| Tool | Required For | Install |
|------|-------------|---------|
| [Claude Code](https://code.claude.com/docs/en/overview) | Everything | `npm install -g @anthropic-ai/claude-code` |
| XeLaTeX | LaTeX compilation | [TeX Live](https://tug.org/texlive/) or [MacTeX](https://tug.org/mactex/) |
| [Quarto](https://quarto.org) | Presentation slides | [quarto.org/docs/get-started](https://quarto.org/docs/get-started/) |
| R | Empirical analysis | [r-project.org](https://www.r-project.org/) |
| [gh CLI](https://cli.github.com/) | PR workflow | `brew install gh` (macOS) |

Claude Code is the only hard requirement; install others as needed.

## Available Skills

| Command | What It Does |
|---------|-------------|
| `/review-r [file]` | R code quality and reproducibility review |
| `/data-analysis [dataset]` | End-to-end analysis with publication-ready output |
| `/proofread [file]` | Academic writing review |
| `/review-paper [file]` | Manuscript structure and referee objection check |
| `/lit-review [topic]` | Literature synthesis |
| `/slide-excellence [file]` | Multi-agent review for presentations |
| `/validate-bib` | Cross-reference citations |
| `/commit [msg]` | Stage, commit, PR, merge |

## Research Workflow Commands

```bash
# Compile LaTeX paper
cd Paper && xelatex paper.tex && bibtex paper && xelatex paper.tex && xelatex paper.tex

# Run R analysis with renv
Rscript -e "renv::restore(); source('Empirical/R/01_clean_data.R')"

# Quality score
python scripts/quality_score.py Paper/paper.tex
```

## Project Status

| Component | Status | Notes |
|-----------|--------|-------|
| Model Framework | In Progress | IP financing wedge in quality-ladder model |
| Calibration | Planned | Match to US/China manufacturing moments |
| Empirical Analysis | Planned | Patent collateral and R&D investment |
| Draft Paper | Planned | Target: Q3 2026 |

## Documentation

See `.claude/rules/` for detailed workflow documentation:
- `knowledge-base-ip-financing.md` — Domain knowledge and notation
- `constitutional-governance.md` — Immutable research principles
- `replication-protocol.md` — Replication standards
- `plan-first-workflow.md` — When and how to use plan mode

## Contact

[Your contact information]

---

**Powered by:** [claude-code-my-workflow](https://github.com/pedrohcgs/claude-code-my-workflow) — Multi-agent academic workflow template.
