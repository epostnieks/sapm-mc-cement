# SAPM Monte Carlo — Cement & Concrete / Calcination Floor

**Public replication repository for quantitative results in:**

> Postnieks, E. (2026). *Cement & Concrete (Calcination Floor).* SAPM Working Paper. SSRN.

This repository provides everything needed to independently reproduce, audit,
and extend the Monte Carlo simulation underlying the paper's core results.
The paper is available on SSRN.

---

## Results (N = 100,000 draws, seed = 42)

| Statistic | Value |
|-----------|-------|
| **β_W median** | **3.21** |
| β_W mean | 3.3 |
| β_W std | 0.67 |
| **90% CI** | **[2.4, 4.5]** |
| 99% CI | [2.1, 5.3] |
| P(β_W < 1) | 0.0000% |
| **ΔW median** | **$546.2B/yr** |
| Π (revenue) | $170.0B/yr |

**β_W = 3.21** means the cement & concrete industry destroys **$3.21 in system
welfare for every $1.00 in revenue** — across 6 channels and 100,000 Monte Carlo draws.

**Classification**: Class 1 — Impossibility

---

## What Is β_W?

```
β_W = ΔW / Π
```

- **ΔW** = total annualized welfare destruction ($B/yr) across all channels
- **Π** = annual industry **revenue** ($B/yr) — not profit

β_W > 1: industry destroys more welfare than it captures in revenue.
β_W > 3: Strong Intractability threshold — reform requires structural replacement.

---

## Quick Start

```bash
git clone https://github.com/epostnieks/sapm-mc-cement.git
cd sapm-mc-cement
pip install numpy scipy
python mc_simulation.py
```

Expected output: `β_W median : 3.21` and `ΔW median : $546.2B/yr`

---

## Welfare Channels

| Channel | Median ($B/yr) | 90% CI | Distribution |
|---------|---------------|--------|--------------|
| C1_climate_damages | $219.6B | [$120.5B, $399.1B] | Lognormal |
| C2_aggregate_extraction | $70.0B | [$46.6B, $105.3B] | Lognormal |
| C3_regulatory_capture | $55.0B | [$40.3B, $75.0B] | Lognormal |
| C4_health_externalities | $45.0B | [$33.7B, $59.9B] | Lognormal |
| C5_structural_overdesign | $59.9B | [$45.0B, $79.8B] | Lognormal |
| C6_governance_lockin | $89.9B | [$67.5B, $120.0B] | Lognormal |
| **Total ΔW** | **$546.2B** | **[$403.7B, $768.2B]** | Correlated (ρ=0.3) |

---

## Impossibility Floor

The floor β_W ≥ 3.6 cannot be breached by any policy while the
industry continues to operate. In 100,000 draws, only **71.6570%**
fall below this floor — confirming the structural constraint.

## Repository Contents

| File | Description |
|------|-------------|
| `mc_simulation.py` | Self-contained simulation — no private pipeline imports |
| `mc_results.json` | Pre-run results (100K draws, seed=42) — matches paper |
| `mc_histogram.json` | Binned β_W distribution (80 bins) for companion chart |
| `assumptions.md` | Every parameter: value, derivation, source |
| `data_sources.md` | Full citation list for all empirical inputs |

---

## Replication Notes

Results are seeded and deterministic. Tested with:
```
numpy==1.26.4  scipy==1.12.0  Python 3.11.9
```

The `median` and `ci_90` (to 1 decimal) match exactly across compatible versions.

---

## License

CC BY 4.0. Cite as:

> Postnieks, E. (2026). *SAPM Monte Carlo — Cement & Concrete (Calcination Floor)*.
> GitHub: epostnieks/sapm-mc-cement.
> https://github.com/epostnieks/sapm-mc-cement
