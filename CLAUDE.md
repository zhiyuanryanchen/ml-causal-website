# CLAUDE.MD -- Academic Project Development with Claude Code

<!-- HOW TO USE: Replace [BRACKETED PLACEHOLDERS] with your project info.
     Customize Beamer environments and CSS classes for your theme.
     Keep this file under ~150 lines — Claude loads it every session.
     See the guide at docs/workflow-guide.html for full documentation. -->

**Project:** Intellectual Property Financing, R&D Investment, and Aggregate TFP
**Institution:** Renmin University of China
**Branch:** main

---

## Core Principles

- **Plan first** -- enter plan mode before non-trivial tasks; save plans to `quality_reports/plans/`
- **Verify after** -- compile/render and confirm output at the end of every task
- **Single source of truth** -- Beamer `.tex` is authoritative; Quarto `.qmd` derives from it
- **Quality gates** -- nothing ships below 80/100
- **[LEARN] tags** -- when corrected, save `[LEARN:category] wrong → right` to MEMORY.md

---

## Folder Structure

```
[YOUR-PROJECT]/
├── CLAUDE.MD                    # This file
├── .claude/                     # Rules, skills, agents, hooks
├── Bibliography_base.bib        # Centralized bibliography
├── Paper/                       # Paper drafts (LaTeX)
├── Figures/                     # Figures and tables
├── Models/                      # Model documentation
├── Empirical/                   # Empirical analysis scripts
│   ├── data/                    # Datasets (documented provenance)
│   └── R/                       # R scripts for analysis
├── Quarto/                      # RevealJS .qmd files + theme
├── docs/                        # GitHub Pages (auto-generated)
├── scripts/                     # Utility scripts
├── quality_reports/             # Plans, session logs, merge reports
├── explorations/                # Research sandbox (see rules)
├── templates/                   # Session log, quality report templates
└── master_supporting_docs/      # Papers and supporting materials
```

---

## Commands

```bash
# LaTeX Paper (3-pass, XeLaTeX only)
cd Paper && xelatex -interaction=nonstopmode paper.tex
BIBINPUTS=..:$BIBINPUTS bibtex paper
xelatex -interaction=nonstopmode paper.tex
xelatex -interaction=nonstopmode paper.tex

# Beamer Slides (if needed)
cd Slides && xelatex -interaction=nonstopmode slides.tex

# Deploy Quarto to GitHub Pages
./scripts/sync_to_docs.sh LectureN

# Quality score
python scripts/quality_score.py Quarto/file.qmd
```

---

## Quality Thresholds

| Score | Gate | Meaning |
|-------|------|---------|
| 80 | Commit | Good enough to save |
| 90 | PR | Ready for deployment |
| 95 | Excellence | Aspirational |

---

## Skills Quick Reference

| Command | What It Does |
|---------|-------------|
| `/compile-latex [file]` | 3-pass XeLaTeX + bibtex |
| `/deploy [LectureN]` | Render Quarto + sync to docs/ |
| `/extract-tikz [LectureN]` | TikZ → PDF → SVG |
| `/proofread [file]` | Grammar/typo/overflow review |
| `/visual-audit [file]` | Slide layout audit |
| `/pedagogy-review [file]` | Narrative, notation, pacing review |
| `/review-r [file]` | R code quality review |
| `/qa-quarto [LectureN]` | Adversarial Quarto vs Beamer QA |
| `/slide-excellence [file]` | Combined multi-agent review |
| `/translate-to-quarto [file]` | Beamer → Quarto translation |
| `/validate-bib` | Cross-reference citations |
| `/devils-advocate` | Challenge slide design |
| `/create-lecture` | Full lecture creation |
| `/commit [msg]` | Stage, commit, PR, merge |
| `/lit-review [topic]` | Literature search + synthesis |
| `/research-ideation [topic]` | Research questions + strategies |
| `/interview-me [topic]` | Interactive research interview |
| `/review-paper [file]` | Manuscript review |
| `/data-analysis [dataset]` | End-to-end R analysis |

---

<!-- CUSTOMIZE: Replace the example entries below with your own
     Beamer environments and Quarto CSS classes. These are examples
     from the original project — delete them and add yours. -->

## Beamer Custom Environments

| Environment | Effect | Use Case |
|-------------|--------|----------|
| `modelbox` | Blue-bordered box | Model specifications |
| `resultbox` | Gold-bordered box | Key empirical results |
| `assumptionbox` | Gold background box | Model assumptions |
| `calibbox` | Light blue box | Calibration targets |
| `keybox` | Gold left-accent box | Key takeaways |

## Quarto CSS Classes

| Class | Effect | Use Case |
|-------|--------|----------|
| `.modelbox` | Blue left border | Model specifications |
| `.resultbox` | Gold border, light bg | Key empirical results |
| `.assumptionbox` | Gold border | Model assumptions |
| `.calibbox` | Light blue background | Calibration targets |
| `.smaller` | 85% font | Dense content slides |
| `.positive` | Green bold | Good annotations |
| `.negative` | Red bold | Problematic results |

---

## Current Project State

| Component | Status | Files | Key Content |
|-----------|--------|-------|-------------|
| Paper Draft | In Progress | `Paper/paper.tex` | IP financing and TFP framework |
| Model Documentation | Planned | `Models/` | Theoretical model derivations |
| Empirical Analysis | Planned | `Empirical/R/` | R&D misallocation quantification |
| Supporting Slides | Optional | `Quarto/` | Presentation versions |
