# Next Pitch Predictor

Predicting the type of the next pitch an MLB pitcher will throw, using only information available before the pitch: game context, player tendencies, and recent pitch history.

## Research Question

How accurately can we predict a pitcher's next pitch type, and how much does each group of features contribute to predictive performance?

## Status
⏳In progress - Phase 0: project setup

## Data

MLB Statcast pitch-level data (2025 regular season) via [pybaseball](https://github.com/jldbc/pybaseball).

Raw data is not committed; see *Reproducing* below.

## Project Structure
| Folder | Purpose |
|---|---|
| `configs/` | Settings (season dates, split cutoffs, model parameters) |
| `data/` | Raw and processed data (git-ignored, created by the pipeline) |
| `notebooks/` | Exploration |
| `src/` | Pipeline code: `data/`, `features/`, `models/`, `evaluation/` |
| `tests/` | Tests, including data-leakage checks |
| `app/` | Streamlit demo |
| `reports/` | Figures and results |

## Reproducing

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Results
*Coming soon*

## Limitations
*Coming soon*
