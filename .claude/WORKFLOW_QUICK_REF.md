# Workflow Quick Reference

**Model:** Contractor (you direct, Claude orchestrates)

---

## The Loop

```
Your instruction
    ↓
[PLAN] (if multi-file or unclear) → Show plan → Your approval
    ↓
[EXECUTE] Implement, verify, done
    ↓
[REPORT] Summary + what's ready
    ↓
Repeat
```

---

## I Ask You When

- **Design forks:** "Option A (fast) vs. Option B (robust). Which?"
- **Code ambiguity:** "Spec unclear on X. Assume Y?"
- **Replication edge case:** "Just missed tolerance. Investigate?"
- **Scope question:** "Also refactor Y while here, or focus on X?"

---

## I Just Execute When

- Code fix is obvious (bug, pattern application)
- Verification (tolerance checks, tests, compilation)
- Documentation (logs, commits)
- Plotting (per established standards)
- Deployment (after you approve, I ship automatically)

---

## Quality Gates (No Exceptions)

| Score | Action |
|-------|--------|
| >= 80 | Ready to commit |
| < 80  | Fix blocking issues |

---

## Non-Negotiables (Locked-In Standards)

<!-- These are immutable for the IP Financing & TFP project -->

- **Path convention:** `here::here()` for R scripts, project-relative paths for LaTeX
- **Seed convention:** `set.seed()` at top of all stochastic simulations, seed documented
- **Figure standards:** White background, 300 DPI, RUC institutional theme
- **Color palette:** Primary #AE0B2A (RUC red), secondary #8B6F4E (gold accent)
- **Tolerance thresholds:** 1e-6 for point estimates, 1e-4 for aggregate statistics

---

## Preferences

<!-- Working style preferences for IP Financing project -->

**Visual:** Publication-ready figures, consistent styling across all plots, institutional colors
**Reporting:** Concise summary with key metrics by default; detailed prose on request
**Session logs:** Always (post-plan, incremental, end-of-session)
**Replication:** Strict — flag any deviations >1e-6; document all near-misses

---

## Exploration Mode

For experimental work, use the **Fast-Track** workflow:
- Work in `explorations/` folder
- 60/100 quality threshold (vs. 80/100 for production)
- No plan needed — just a research value check (2 min)
- See `.claude/rules/exploration-fast-track.md`

---

## Next Step

You provide task → I plan (if needed) → Your approval → Execute → Done.
