![Oil Well Profit & Risk Analysis](assets/banner.svg)

[English](README.md) · [Português](README.pt-BR.md) · [Notebook](notebooks/oil_well_profit_risk_analysis.ipynb) · [Portfolio](https://github.com/joaovspereira)

# Oil Well Profit & Risk Analysis

> **US$4.61M simulated profit · 0.7% loss risk**

**Decision question:** Which region satisfies the simulated loss-risk limit of 2.5%?

**Key result:** Region 1 is the only region below the risk limit after the corrected bootstrap calculation.

Business-oriented machine-learning project combining regression, simulation and risk analysis.

## Business problem
OilyGiant needs to choose one of three regions for developing new oil wells.

## Objective
Predict reserves, select the 200 most promising wells among 500 studied locations, estimate profit and choose a region with **loss risk below 2.5%**.

## Model RMSE
- Region 0: 37.5794
- Region 1: 0.8931
- Region 2: 40.0297

## Recalculated bootstrap results

| Region | Average simulated profit | Central 95% bootstrap range | Loss risk |
|---|---:|---:|---:|
| 0 | USD 3.96M | USD -1.11M to USD 9.10M | 6.9% |
| 1 | USD 4.61M | USD 0.78M to USD 8.63M | 0.7% |
| 2 | USD 3.93M | USD -1.12M to USD 9.35M | 6.5% |

## Recommendation
**Region 1** is the only region satisfying the required risk threshold and also has the highest simulated average profit among eligible regions.

## Technologies
Python · pandas · NumPy · scikit-learn · bootstrap simulation · Jupyter

## Repository structure
- [notebooks/oil_well_profit_risk_analysis.ipynb](notebooks/oil_well_profit_risk_analysis.ipynb)
- [data/README.md](data/README.md)
- [requirements.txt](requirements.txt)

## Next steps
Sensitivity analysis for oil price and drilling cost, stability checks and probabilistic optimization.

## Run locally

Clone the repository, enter its directory and create an environment:

```bash
git clone https://github.com/joaovspereira/oil-well-profit-risk-analysis.git
cd oil-well-profit-risk-analysis
python -m venv .venv
```

Activate it with `source .venv/bin/activate` on macOS/Linux or `.\.venv\Scripts\Activate.ps1` in Windows PowerShell. Then run:

```bash
python -m pip install -r requirements.txt
python -m notebook notebooks/oil_well_profit_risk_analysis.ipynb
```

Place the original datasets listed in [data/README.md](data/README.md) inside `data/` before executing cells. Dataset files are excluded from version control.

## Learning

This project was developed during the TripleTen Data Science bootcamp. It demonstrates a documented analytical workflow, explicit evaluation criteria and interpretation of model limitations.

## Reproduction and limitations

The complete notebook was rerun on 2026-09-15 after fixing duplicated-index alignment in the bootstrap profit calculation. The historical $5.18M / 0.3% result for Region 1 is superseded by **$4.61M / 0.7%**. [Validation details](VALIDATION.md) record dataset hashes, the correction and the runtime.

The bootstrap range describes simulated outcomes conditional on the fitted model, validation sample, fixed budget and unit revenue. It is not a confidence interval for mean profit or a guarantee of investment returns. Repeated well identifiers need investigation and group-aware validation if they refer to the same wells. No real financial gain was measured.

## Key learning

Ranking by prediction error alone is insufficient: selection must account for the decision budget, profit distribution and downside risk.

[Explore the complete portfolio](https://github.com/joaovspereira) · [Contact](mailto:joaovitorsouza20pereira@gmail.com)
