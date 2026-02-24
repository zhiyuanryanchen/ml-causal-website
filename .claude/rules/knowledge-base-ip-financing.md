---
paths:
  - "Paper/**/*.tex"
  - "Quarto/**/*.qmd"
  - "Empirical/**/*.R"
  - "Models/**/*.tex"
---

# Knowledge Base: IP Financing, R&D Investment, and Aggregate TFP

**Domain-specific knowledge for macro/innovation economics research.**

---

## Notation Registry

| Rule | Convention | Example | Anti-Pattern |
|------|-----------|---------|-------------|
| TFP notation | Uppercase A with subscripts | $A_t$, $A_{it}$ | Using T, Z for TFP |
| R&D intensity | rho ($\rho$) for R&D share | $\rho = R/Y$ | Using r (confusion with interest rate) |
| Innovation rate | g for growth rate | $g_A$ | Using $\gamma$ without definition |
| Misallocation | tau ($\tau$) for wedges | $\tau_{it}$ | Using generic w |
| Interest rate | Lowercase r | $r_t$ | Using R (confusion with R&D) |
| Patent value | V for value | $V_{it}$ | Using P (confusion with price) |
| Discount factor | Beta ($\beta$) | $\beta = 1/(1+r)$ | Using $\delta$ (confusion with depreciation) |
| Elasticity | Theta ($\theta$) | $\theta$ for substitution | Using $\sigma$ inconsistently |
| Innovation step | Lambda ($\lambda$) | $\lambda$ for step size | Using random Greek letters |

---

## Symbol Reference

| Symbol | Meaning | Introduced | Context |
|--------|---------|------------|---------|
| $A_t$ | Aggregate TFP | Baseline | Production function |
| $A_{it}$ | Firm-level TFP | Baseline | Firm heterogeneity |
| $\rho$ | R&D share of output | Baseline | $R/Y$ ratio |
| $s_R$ | R&D investment rate | Model extension | Alternative notation |
| $\lambda$ | Innovation step size | Quality ladder models | Productivity improvement |
| $\tau_{IP}$ | IP financing wedge | Core contribution | Financing friction |
| $\theta$ | Elasticity of substitution | Production | Within-sector substitution |
| $\alpha$ | Capital share | Production | Cobb-Douglas parameter |
| $\delta$ | Depreciation rate | Capital dynamics | Physical capital |
| $\beta$ | Household discount factor | Household problem | $1/(1+\rho_{time})$ |
| $V_{it}$ | Value of patent/firm | Firm dynamics | Bellman equation |
| $z_{it}$ | Innovation productivity | Firm heterogeneity | R&D efficiency |
| $m_{it}$ | Misallocation wedge | TFP decomposition | Hsieh-Klenow style |
| $MRPK_{it}$ | Marginal revenue product of capital | Misallocation measurement | Dispersion metric |

---

## Model Hierarchy

| Model | Key Features | Use Case |
|-------|--------------|----------|
| **Baseline: Romer (1990)** | R&D-driven growth, variety expansion | Theoretical foundation |
| **Quality ladders: Grossman-Helpman (1991)** | Schumpeterian growth, creative destruction | Innovation dynamics |
| **Misallocation: Hsieh-Klenow (2009)** | Distortion wedges, TFP losses | Empirical framework |
| **IP Financing (This paper)** | Collateral constraints on patents, R&D external financing | Core contribution |

---

## Empirical Applications

| Application | Paper | Dataset | Purpose | Status |
|------------|-------|---------|---------|--------|
| TFP measurement | Hsieh-Klenow (2009) | China/India manufacturing | Misallocation measurement | Planned |
| R&D financing frictions | Brown et al. (2009) | Compustat | R&D investment sensitivity | Planned |
| Patent collateral | Mann (2018) | SBA loans, patent data | IP as collateral evidence | Planned |
| Innovation-TFP link | Akcigit et al. (various) | USPTO, Census | Innovation dynamics | Reference |
| Aggregate TFP trends | Fernald (2014) | Aggregate series | TFP facts | Reference |

---

## Design Principles

| Principle | Evidence | Application |
|-----------|----------|-------------|
| Micro-to-macro aggregation | Hsieh-Klenow framework | Empirical TFP decomposition |
| Financial frictions matter | Lamont (1997), Kaplan-Zingales (1997) | R&D investment literature |
| Endogenous growth | Romer (1990), Aghion-Howitt | Theoretical foundation |
| General equilibrium | Firm dynamics + household problem | Full model |

---

## Anti-Patterns (Don't Do This)

| Anti-Pattern | What Happened | Correction |
|-------------|---------------|-----------|
| Using "TFP" for output | TFP is a residual, not output | Distinguish $Y_t$ (output) from $A_t$ (TFP) |
| Confusing $\tau$ types | Using same symbol for different wedges | Subscript: $\tau_{IP}$, $\tau_{capital}$ |
| Ignoring GE effects | Partial equilibrium intuition in GE model | Document spillovers, transition dynamics |
| Mixing notation across sections | Same concept, different symbols | Update symbol table, be consistent |
| Rounding intermediate results | Compounding numerical errors | Keep full precision, round only final output |

---

## R Code Pitfalls

| Bug | Impact | Fix |
|-----|--------|-----|
| Forgetting `set.seed()` | Non-reproducible stochastic simulations | Set seed at top of all simulation scripts |
| Using `df` as variable name | Conflicts with `stats::df()` density function | Use `data`, `dt`, or domain-specific names |
| `summarize()` without `ungroup()` | Silent grouping persists | Always `ungroup()` after grouped operations |
| `merge()` with duplicate keys | Cartesian explosion | Check for duplicates before merging |
| Integer overflow in large panels | Silent wrong results | Use `as.numeric()` for large integers |

---

## Tolerance Thresholds

| Context | Threshold | Rationale |
|---------|-----------|-----------|
| Point estimates (coefficients) | 1e-6 | High precision for parameters |
| Aggregate statistics (moments) | 1e-4 | Slightly relaxed for aggregates |
| Simulation convergence | 1e-8 | Tighter for numerical optimization |
| Graphics/display | 1e-3 | Visual tolerance |

---

## Key Equations Reference

### TFP Decomposition (Hsieh-Klenow)

$$Y = \prod_{s=1}^{S} \left( \sum_{i=1}^{M_s} Y_{sit}^{\frac{\sigma-1}{\sigma}} \right)^{\frac{\sigma}{\sigma-1}}$$

$$\text{TFP}_{actual} = \prod_{s} \left( \sum_{i} \left( \frac{A_{sit}K_{sit}^{\alpha}L_{sit}^{1-\alpha}}{\bar{A}_s\bar{K}_s^{\alpha}\bar{L}_s^{1-\alpha}} \right)^{\sigma-1} \right)^{\frac{1}{\sigma-1}}$$

### R&D Production Function

$$\dot{n} = \lambda R^{\phi} n^{\psi}$$

Where:
- $n$ = number of varieties/quality level
- $R$ = R&D investment
- $\lambda$ = innovation productivity
- $\phi, \psi$ = curvature parameters

### IP Financing Constraint

$$R_{it} \leq \eta \cdot V_{it} + (1-\eta) \cdot \text{Collateral}_{it}$$

Where:
- $\eta$ = fraction of innovation value pledgeable
- $V_{it}$ = patent value (collateral)
- Collateral = tangible assets (traditional collateral)

---

## Literature Quick Reference

### Foundation Papers
- **Romer (1990)**: Endogenous growth via variety expansion
- **Grossman-Helpman (1991)**: Quality ladders, creative destruction
- **Aghion-Howitt (1992)**: Schumpeterian paradigm

### Misallocation Literature
- **Restuccia-Rogerson (2008)**: Policy distortions and TFP
- **Hsieh-Klenow (2009)**: Misallocation measurement methodology
- **Banerjee-Duflo (2005)**: Financial constraints and growth

### IP and Financing
- **Mann (2018)**: Patents as collateral
- **Fischer-Saidi (2021)**: Patent-based financing
- **Aghion et al. (2005)**: Competition and innovation

### R&D Investment
- **Hall (2002)**: R&D tax treatment
- **Brown et al. (2009)**: Financing constraints and R&D
- **Nanda-Nicholas (2014)**: Bank credit and innovation
