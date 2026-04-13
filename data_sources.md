# Data Sources — Cement & Concrete Monte Carlo Simulation

Channel parameters in `mc_simulation.py` trace to the sources listed here.
The paper (Cement & Concrete: Calcination Floor) is available on SSRN and contains the full
reference list and §4 calibration narrative.

---

## Channel Sources

### `C1_climate_damages`

Climate damages (process + combustion emissions). 2.3 Gt CO2/yr × $120/tonne SCC (central). Net of carbonation offset with 3% temporal-mismatch discount. Range $120-400B. Source: GCCA, IEA, EPA SCC $51-190/tonne.

*Full citations: paper §4 (available SSRN).*

### `C2_aggregate_extraction`

Aggregate extraction externalities. 50 Gt/yr sand and gravel — most extracted solid material on Earth. Fisheries losses, coastal erosion, ecosystem service losses, social costs. Range $45-105B. Source: UNEP Global Sand Observatory, Costanza et al.

*Full citations: paper §4 (available SSRN).*

### `C3_regulatory_capture`

Regulatory capture costs. €5B EU ETS windfall profits, blocked material substitution (NRMCA anti-timber), Buy Clean co-optation. Range $40-75B. Source: ifo Institute, PCA/NRMCA disclosure, GSA procurement data.

*Full citations: paper §4 (available SSRN).*

### `C4_health_externalities`

Health externalities from PM2.5, NOx, SO2, heavy metals. EPA NESHAP: 2,500 premature deaths/yr in US alone (2% of global production). Income-adjusted VSL global scaling. Range $30-60B. Source: EPA RIA 2010, WHO air quality data.

*Full citations: paper §4 (available SSRN).*

### `C5_structural_overdesign`

Structural overdesign waste. 48% excess material in developing-world construction (60% of global consumption). 660 Mt unnecessary cement/yr. Range $45-80B. Source: Oman engineering surveys, GCCA clinker ratio data, RMI analysis.

*Full citations: paper §4 (available SSRN).*

### `C6_governance_lockin`

Governance lock-in and institutional failure. Prescriptive code lock-in, Dangote-style grade manipulation (183% price premium), developing-world code adoption failure. LC3 at <5% despite 40% emission reduction at negative cost. Range $65-120B. Source: World Bank, Dangote/CABCO case, ICC code analysis.

*Full citations: paper §4 (available SSRN).*

---

## Industry Revenue (Π)

The private payoff Π = $170.0B/yr is global annual industry revenue.
Source: paper §2 and §4. See paper §DA-1 (Decision Audit Field 7) for full
revenue source documentation.

---

## SAPM Framework

- Postnieks, E. (2026). *The Private Pareto Theorem*. SAPM Foundation Paper. SSRN.
- Postnieks, E. (2026). *Cement & Concrete (Calcination Floor)*. SAPM Working Paper. SSRN.

---

## Distribution Methodology

- Iman, R. L., & Conover, W. J. (1982). A distribution-free approach to
  inducing rank correlation among input variables. *Communications in
  Statistics — Simulation and Computation*, 11(3), 311–334.
- Cooke, R. M. (1991). *Experts in Uncertainty*. Oxford University Press.
