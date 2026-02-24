# Constitutional Governance: IP Financing & TFP Project

**Immutable principles for research on Intellectual Property Financing, R&D Investment, and Aggregate TFP.**

---

## Why Constitutional Governance?

As this research project grows, some decisions become non-negotiable (to maintain quality, reproducibility, and theoretical consistency). Others remain flexible based on context.

Making this distinction explicit prevents:
- Repeated debates on settled issues
- Inconsistent application of standards
- Uncertainty about when to ask vs. decide

---

## Article I: Replication-First

All empirical claims must have accompanying R scripts with documented data provenance.

**Why this matters:** Research credibility depends on verifiable results. Every number in the paper must trace back to executable code.

**Requirements:**
- R scripts for every table and figure
- Data provenance documented in `Empirical/data/README.md`
- Seeds documented for all stochastic simulations
- Replication package tested on clean environment

**Exceptions:** Theoretical/model-based claims without empirical component; literature review summaries.

---

## Article II: Theoretical Consistency

Model assumptions must be explicitly stated; all equations must trace to their theoretical justification.

**Why this matters:** Macroeconomic models require precise foundations. Hidden assumptions invalidate conclusions.

**Requirements:**
- Every assumption stated before the result that uses it
- First-order conditions derived explicitly
- Steady-state properties proven
- Aggregation conditions verified

**Exceptions:** Standard results (e.g., basic Solow model) with proper citations; pedagogical simplifications noted as such.

---

## Article III: Quality Gate

Nothing commits below 80/100; simulations must replicate within tolerance.

**Why this matters:** Technical debt accumulates exponentially below quality thresholds. Flawed analysis propagates.

**Requirements:**
- Quality score >= 80 for commits
- Quality score >= 90 for PRs
- Numerical replication within 1e-6 for point estimates
- Numerical replication within 1e-4 for aggregate statistics

**Exceptions:** Explicit WIP branches tagged `[WIP]`; exploration folder (60/100 threshold).

---

## Article IV: Data Provenance

All datasets documented with source, date, and processing steps in `Empirical/data/README.md`.

**Why this matters:** Data errors are common and hard to detect. Provenance enables debugging and updating.

**Requirements:**
- Source URL or citation for each dataset
- Download date
- Processing steps documented
- Variable definitions included
- Sample restrictions noted

**Exceptions:** Synthetic/simulated data with DGP documented; proprietary data with access instructions.

---

## Article V: Plan-First Threshold

Enter plan mode for tasks requiring >3 files, >30 minutes, or multi-step analysis.

**Why this matters:** Research workflows are complex. Planning prevents mid-implementation pivots and wasted effort.

**Requirements:**
- Requirements spec for ambiguous tasks
- Saved plan in `quality_reports/plans/`
- User approval before implementation
- Session log updated at key milestones

**Exceptions:** Exploration folder (fast-track workflow); typo fixes; single-file edits with clear scope.

---

## User Preferences (Override Anytime)

These patterns ARE flexible and can vary by context:

- File naming conventions: `snake_case` for R, `kebab-case` for documentation
- Tolerance thresholds: 1e-6 for point estimates, 1e-4 for aggregates (can tighten for final version)
- Figure aesthetics: Publication-ready, consistent with institutional theme
- Code verbosity: Comments for non-obvious steps, self-documenting variable names
- Citation style: Author-Year (economics standard)

---

## Requesting Amendment

When requesting deviation from an article, specify:

> "Amending Article X (permanent change) or overriding for this task (one-time exception)?"

**Amendment process:**
1. Propose amendment with rationale
2. Discuss implications (what breaks? what improves?)
3. Update this file if approved
4. Document change in session log with `[CONSTITUTIONAL AMENDMENT]` tag

---

## Maintenance

**Review cadence:** Quarterly (or after every 5 research milestones)

**Review questions:**
- Are all articles still relevant?
- Are any being violated repeatedly? (If yes, amend or delete)
- Are any new patterns emerging? (If yes, consider promoting to article)
- Are articles enabling or obstructing work?

---

## Amendment History

| Date | Article | Change | Rationale |
|------|---------|--------|-----------|
| 2026-02-24 | All | Initial adoption | Project initialization |
