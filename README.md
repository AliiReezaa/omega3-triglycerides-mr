<p align="center"><img src="assets/header.svg" width="100%" alt="Omega-3 fatty acids and triglycerides"></p>

<p align="center">![First author](https://img.shields.io/badge/First%20author-c2552b?style=flat-square) ![MR-Clust](https://img.shields.io/badge/MR--Clust-5b4bb7?style=flat-square) ![Two-step MR](https://img.shields.io/badge/Two--step%20MR-0f6e6a?style=flat-square) ![MVMR](https://img.shields.io/badge/MVMR-0f6e6a?style=flat-square) ![R](https://img.shields.io/badge/R-276DC3?style=flat-square)</p>

> **Status:** manuscript complete; preparing submission to a Q1 journal
>
> This repository is a public overview of an unpublished study. It shows the research question, design and methods. **Results, data and analysis code are withheld until peer-reviewed publication**, and will be released here at that point.

## Research question
Genetic instruments for circulating omega-3 fatty acids act through **several distinct biological pathways**. Do these pathways affect triglycerides differently, and are the effects mediated by glycaemic traits, adiposity or inflammation?

## Study design
```mermaid
flowchart TB
  subgraph D[Discovery arm]
   D1[Omega-3: UK Biobank NMR<br/>N≈115k] --> D2[Triglycerides: GLGC<br/>excluding UK Biobank]
  end
  subgraph R[Replication arm]
   R1[Omega-3: 33 cohorts<br/>N≈136k, no UKB] --> R2[Triglycerides:<br/>UK Biobank]
  end
  D --> P1[Phase 1 · Univariable MR<br/>Steiger · reverse MR · MVMR vs omega-6]
  R --> P1
  P1 --> P2[Phase 2 · MR-Clust<br/>pathway-specific clusters]
  P2 --> P3[Phase 3 · Cluster-specific two-step MR<br/>glycaemic traits · BMI · CRP]
  style P2 fill:#ede9fb,stroke:#5b4bb7
```

## Data sources
| Role | Dataset | Notes |
|---|---|---|
| Exposure | UK Biobank NMR omega-3 (GWAS Catalog) | discovery |
| Exposure | Karjalainen et al. 2024 (33 cohorts) | replication, no UKB |
| Outcome | GLGC 2021 triglycerides (excl. UKB) / UK Biobank TG | no participant overlap within each arm |
| Mediators | MAGIC glycaemic traits, GIANT BMI, CRP | two-step MR |

## Methods
| Component | Approach |
|---|---|
| Instruments | P < 5×10⁻⁸, MAF ≥ 0.01, r² < 0.001 within 10 Mb, F ≥ 10 |
| Univariable MR | IVW (multiplicative random effects), MR-Egger, weighted median, simple/weighted mode |
| Robustness | Cochran Q, Rücker Q′, MR-PRESSO, leave-one-out, Steiger filtering, reverse MR |
| Pathways | MR-Clust (≥4 variants, conditional probability > 0.8) |
| Mediation | cluster-specific two-step MR and MVMR; product-of-coefficients with delta-method SE |

## Why it matters
Omega-3 supplementation trials show mixed cardiovascular results. Separating the genetic pathways that link omega-3 to triglycerides helps explain why, and shows which biology is worth targeting.

## Team & role
**A. R. Soleymani Taloubaghi** (first author: design, analysis, writing) with D. Habibi, M. Akbarzadeh and F. Haghighatdoost.

## Reproducibility
- Analysis pipeline written in R 4.6 (TwoSampleMR, MRPRESSO, mrclust, RadialMR, MVMR), with pinned package versions and a single entry-point script
- Public summary statistics only; no individual-level data is used or shared
- Reported according to STROBE-MR

---
<sub>Contact: <a href="mailto:alirezasoleymani24@gmail.com">alirezasoleymani24@gmail.com</a> · <a href="https://aliireezaa.github.io">aliireezaa.github.io</a></sub>
