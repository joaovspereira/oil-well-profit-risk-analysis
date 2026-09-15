# Validation — 2026-09-15

The original calculation selected targets by pandas labels after bootstrap sampling with replacement. Repeated labels could expand rows again during selection. A synthetic repeated-label example produced a selected sum of 300 instead of 220. The corrected function ranks sample positions and selects the corresponding target positions.

The prior code was reproduced against the downloaded course-distribution data and matched all three saved profit summaries. With the corrected function, the same split, seed, 500 sampled wells, top 200 selections and 1,000 repetitions produced the recalculated table in the README. The region decision remains unchanged. Model validation RMSE also matches the saved notebook values.

## Environment

- pandas 2.2.3
- numpy 2.3.5
- scikit-learn 1.8.0

## Data provenance

Datasets were read from the course distribution endpoint solely for local validation. CSV files are excluded from this repository.

| File | SHA-256 |
|---|---|
| [geo_data_0.csv](https://practicum-content.s3.us-west-1.amazonaws.com/datasets/geo_data_0.csv) | `03d9b17d4a503c35f938a9904357ceb1ac0a12dc9202f925f04975446a9f287d` |
| [geo_data_1.csv](https://practicum-content.s3.us-west-1.amazonaws.com/datasets/geo_data_1.csv) | `709841f59d976ab38d8360916c8f5606c5000e2211f474b862d548b2968cefab` |
| [geo_data_2.csv](https://practicum-content.s3.us-west-1.amazonaws.com/datasets/geo_data_2.csv) | `e0feeb086d7760e11c2f9058029a14af4974753da6771faba2000457b4cb8848` |

## Scope

Notebook execution, the repeated-index regression case, schema, syntax and repository paths were checked. The bootstrap does not refit the model in each repetition, so it does not capture training uncertainty. The 95% range refers to quantiles of simulated profits, conditional on the supplied educational data and assumptions.
