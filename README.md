# Marketplace Reliability: Reducing No-Call-No-Shows in a Healthcare Staffing Platform

## Overview

A data-driven operations case study analysing cancellation patterns in a two-sided healthcare staffing marketplace. The goal: identify the root causes of shift cancellations, quantify their impact on marketplace health, and propose a targeted intervention to reduce the most damaging cancellation type — No-Call-No-Shows (NCNS).

## The Problem

The marketplace connects healthcare facilities (demand) with healthcare professionals (supply) for shift-based work. The platform faces a reliability crisis:

- **40% fill rate** — only 4 in 10 posted shifts get worked
- **46.5% of cancellations** happen with less than 24 hours notice
- **81.6% of NCNS-affected shifts** remain permanently unfilled
- The marketplace recovers only **15.7%** of NCNS'd shifts

## Key Findings

### The problem is concentrated, not distributed
13.6% of workers (1,505 individuals) are responsible for 64.3% of all NCNS events. This Pareto pattern means a targeted intervention can achieve outsized results without disrupting the broader workforce.

### Lower-paid roles are least reliable
Entry-level workers (CNAs) make up 60% of shifts but have a 4.2% NCNS rate — 10x higher than the most specialised role (RNs at 0.4%). However, CNAs also have the highest fill rate (50.7%), creating a tension: they are simultaneously the biggest problem and the most essential supply.

### Booking lead time predicts cancellation risk
Shifts booked 2–7 days out have the lowest cancellation rate (26.4%). Both extremes — under 12 hours (30.3%) and over 2 weeks (34.2%) — carry higher risk.

### Recovery is nearly impossible after NCNS
The marketplace recovers 38.3% of standard cancellations but only 15.7% of NCNS events. The difference is time — standard cancellations give the platform hours to find a replacement; NCNS gives zero.

## Proposed Solution

A two-layer system targeting prevention and consequence:

**Layer 1 — Shift Confirmation Checkpoints**
Every shift is assigned a risk score based on worker history, role type, and booking lead time. High-risk shifts require mandatory confirmation at 48h, 24h, and 12h before start. Non-confirmation at 12h triggers automatic shift reposting, converting a potential NCNS (0h recovery time) into an early release (12h recovery time).

**Layer 2 — Tiered Access Restrictions**
Workers who NCNS face immediate, graduated restrictions — reduced shift visibility, booking window limits, single-shift booking — rather than delayed binary deactivation. All restrictions are reversible through consecutive completed shifts, keeping supply in the system while limiting damage.

## Tech Stack

- **Python** (pandas, numpy, matplotlib)
- **Jupyter Notebooks** for exploratory analysis
- **Dataset**: 127k booking events, 78k cancellation events, 41k shifts across 4 months

## Repository Structure

```
├── README.md
├── notebooks/
│   └── exploration.ipynb          # Full step-by-step data exploration
├── figures/
│   ├── ncns_damage.png            # NCNS vs non-NCNS unfilled rates
│   ├── concentration.png          # Worker concentration curve
│   ├── agent_comparison.png       # CNA vs LVN vs RN breakdown
│   └── lead_time_cancel_rate.png  # Booking lead time vs cancel rate
└── proposal/
    └── proposal.md                # Full proposal document
```

> **Note:** The source data is proprietary and not included in this repository. The analysis and findings are presented with anonymised references.

## Results

| Metric | Baseline | Target | Rationale |
|--------|----------|--------|-----------|
| NCNS rate | 3.1% | 2.0% | Preventing half of repeat-offender NCNS (64% of total) yields ~32% reduction |
| Late cancel rate | 8.9% | 6.5% | Confirmation checkpoints convert late cancels to early cancels |
| Confirmation response rate | N/A | 80%+ | Leading indicator for system adoption |
| Reposted shift fill rate | 15.7% | 35%+ | 12h recovery window approaches the 38.3% general recovery rate |

## What I Learned

- **Work backwards from the outcome.** Start with what you want to achieve, trace back through the data to find the root cause, then design the solution to target exactly that chain.
- **Concentration changes everything.** When a small group drives most of the problem, the solution should be targeted, not broad.
- **Intellectual honesty strengthens proposals.** Acknowledging that 72% of unfilled shifts are a supply problem (outside scope) made the cancellation-focused proposal more credible, not weaker.
- **Every number must be traceable.** Every target in the proposal maps to a specific calculation in the dataset.

## Author

Beniah — Data Science | www.linkedin.com/in/benaiah-okara |
