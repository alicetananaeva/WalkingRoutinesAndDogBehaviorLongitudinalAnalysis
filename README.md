# Walking routines and dog behavior — longitudinal mixed-effects

Portfolio project: a reproducible, research-style analysis of how **walking and everyday activity routines** relate to **fear- and anxiety-related behavior scores** over time, using a **longitudinal mixed-effects** framework.

**Notebook:** `dog_behavior_longitudinal_mixed_effects.ipynb`  
**PDF export:** `dog_behavior_longitudinal_mixed_effects.pdf`

## Summary

- **Study context**: Morris Animal Foundation *Golden Retriever Lifetime Study* (GRLS).
- **Design**: repeated annual observations per dog (longitudinal).
- **Core question**: do routine variables measured at year \(t\) predict behavior outcomes at year \(t+1\), after accounting for baseline outcome level and covariates?
- **Modeling approach**: lagged linear mixed-effects models with a dog-level random intercept.

## Key findings

- Behavioral outcomes showed moderate year-to-year stability, with Pearson correlations ranging approximately from 0.53 to 0.74 across adjacent annual transitions.
- The strongest predictor of next-year behavior was the current level of the same outcome.
- Higher overall activity level showed a small but consistent association with lower subsequent nonsocial fear, touch sensitivity, and stress-related composite scores.
- Out-of-sample validation showed moderate held-out predictive performance, with R² values ranging from approximately 0.32 to 0.49 across outcomes.
- Overall activity appeared more informative than any single walk-specific variable considered in isolation.

## What’s inside

- Data loading and basic validation
- Construction of longitudinal (within-dog) year pairs
- Stability analysis (year-to-year correlations and change summaries)
- Lagged mixed-effects modeling
- Out-of-sample evaluation (train/test split at the dog level)
- Sensitivity/scenario analysis to interpret model response to routine variables

## Data availability

The original GRLS source files are not included in this repository. The notebook is written so that data files can be placed locally (see the **Data input** section inside the notebook).

## Data input

The original source files are not distributed with this repository.

Expected local input files:
- `activity_details_through_SY2.csv`
- `beh_problem_scores.csv`
- `dog_profile.csv`

These files should be placed in the repository root unless paths are changed manually inside the notebook.

Expected key fields include:
- `subject_id`
- `year_in_study`
- annual activity variables
- annual behavior score variables
- dog profile date fields needed to derive age

## How to run

```bash
python -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

Open `dog_behavior_longitudinal_mixed_effects.ipynb`.

## Reproducibility notes

- The analysis avoids absolute paths and is intended to run from the repository root.
- Any random splitting is controlled within the notebook.

## License

This repository is shared for portfolio purposes. If you reuse code, please cite the repository and verify that your use complies with the data source’s terms.
