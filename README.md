# SOGAR ablations
Ablation studies on depth, action sparsity, timeouts, and bin counts

# TIMEOUTS

## Time Degradation of Results - 10-fold cross validation per timeout (Maximum Depth = 3)

Degradation is computed as the relative increase in `inv.` compared to the no-timeout baseline:
**Degradation (%) = (inv_timeout − inv_no_timeout) / inv_no_timeout × 100**

| Dataset | Timeout | cost ↓ | loss ↓ | inv. ↓ | Degradation (%) |
|---------|---------|--------|--------|--------|-----------------|
| Attrition | 10s | 0.33±0.02 | 0.10±0.03 | 0.43±0.03 | +16.2% |
| | 60s | 0.31±0.02 | 0.08±0.02 | 0.39±0.02 | +5.4% |
| | No timeout | 0.30±0.02 | 0.07±0.02 | 0.37±0.02 | — |
| German | 10s | 0.12±0.00 | 0.04±0.01 | 0.16±0.01 | +14.3% |
| | 60s | 0.11±0.01 | 0.03±0.01 | 0.14±0.01 | 0.0% |
| | No timeout | 0.11±0.01 | 0.03±0.01 | 0.14±0.01 | — |
| Bank | 10s | 0.19±0.05 | 0.08±0.04 | 0.28±0.04 | +12.0% |
| | 60s | 0.19±0.04 | 0.08±0.03 | 0.27±0.04 | +8.0% |
| | No timeout | 0.19±0.03 | 0.06±0.02 | 0.25±0.03 | — |
| Adult | 10s | — | — | — | no solution |
| | 60s | — | — | — | no solution |
| | 200s | 0.35±0.01 | 0.20±0.04 | 0.55±0.04 | +5.8% |
| | No timeout | 0.35±0.03 | 0.17±0.02 | 0.52±0.03 | — |

---

# DEPTH ANALYSIS

## DEPTH 2 (10-fold cross validation )



## Attrition

| Model | cost ↓ | loss ↓ | inv. ↓ | time(s) ↓ |
|-------|--------|--------|--------|-----------|
| DNN | 0.06±0.00 | <0.01±0.00 | 0.06±0.00 | 9±1 |
| LightGBM | 0.31±0.03 | 0.12±0.02 | 0.43±0.03 | 12±1 |
| XGBoost | 0.25±0.01 | 0.06±0.01 | 0.31±0.01 | 10±0 |
---

## German

| Model | cost ↓ | loss ↓ | inv. ↓ | time(s) ↓ |
|-------|--------|--------|--------|-----------|
| DNN | 0.02±0.01 | <0.01±0.00 | 0.03±0.01 | 3±0 |
| LightGBM | 0.11±0.01 | 0.05±0.01 | 0.16±0.01 | 3±1 |
| XGBoost | 0.11±0.01 | 0.04±0.02 | 0.15±0.02 | 3±0 |

---

## Bank

| Model | cost ↓ | loss ↓ | inv. ↓ | time(s) ↓ |
|-------|--------|--------|--------|-----------|
| DNN | 0.17±0.01 | 0.33±0.03 | 0.49±0.04 | 8±0 |
| LightGBM | 0.19±0.03 | 0.08±0.03 | 0.27±0.03 | 6±1 |
| XGBoost | 0.22±0.04 | 0.29±0.07 | 0.51±0.04 | 8±1 |

## Adult

| Model | cost ↓ | loss ↓ | inv. ↓ | time(s) ↓ |
|-------|--------|--------|--------|-----------|
| DNN | 0.03±0.01 | 0.04±0.03 | 0.07±0.04 | 47±1 |
| LightGBM | 0.37±0.02 | 0.20±0.04 | 0.57±0.03 | 51±3 |
| XGBoost | 0.32±0.08 | 0.37±0.11 | 0.69±0.04 | 63±3 |



---


# ACTION SPARSITY 

## Maximum 2 feature actions - 10-fold Cross-Validation (LightGBM classifier)

| Dataset | cost ↓ | loss ↓ | inv. ↓ | time(s) ↓ |
|---------|--------|--------|--------|-----------|
| Attrition | 0.32±0.02 | 0.17±0.03 | 0.50±0.03 | 162.6±6.8s |
| German | 0.12±0.00 | 0.08±0.01 | 0.19±0.01 | 23.4±1.7s |
| Bank | 0.14±0.03 | 0.22±0.03 | 0.36±0.04 | 116.7±2.4s |
| Adult | 0.40±0.16 | 0.44±0.18 | 0.84±0.04 | 533.9±25.8s |


--- 


# BINS ABLATION

## MAX BINS DECREASE - SCORE DEGRADATION - 10-fold Cross-validation



| Bins | cost ↓ | loss ↓ | inv. ↓ | time(s) ↓ | Degradation (%) |
|------|--------|--------|--------|-----------|-----------------|
| Baseline | 0.30±0.02 | 0.07±0.02 | 0.37±0.02 | 356.4±9.4 | — |
| 10 bins | 0.31±0.01 | 0.08±0.02 | 0.38±0.01 | 163 | +3.2% |
| 5 bins | 0.32±0.01 | 0.07±0.01 | 0.39±0.01 | 127 | +4.7% |


---
