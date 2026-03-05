# SURF AI: Time-Series Forecasting for Smart Water Systems

This repo contains an initial time-series forecasting baseline (LSTM) that predicts future consumption from historical hourly data.
In the SURF project, this forecast becomes an input to a higher-level AI agent / digital-twin workflow for smart water systems.

## What's inside
- `notebooks/water_demand_lstm.ipynb`: end-to-end notebook (load data → explore → scale → sequence building → LSTM → evaluation)

## Data
The notebook currently expects a CSV named `AEP_hourly.csv` with columns:
- `Datetime`
- `AEP_MW` (the target series)

If you're switching to a water-demand dataset, keep the same structure or rename columns inside the notebook.

**Recommended:** place data in a local folder named `data/` and do not commit it (it's gitignored).

## Run locally
```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Then open the notebook:
```bash
jupyter notebook
```

## Notes for publishing
- No API keys or tokens were found in the notebook.
- The first cell uses `google.colab.files.upload()`; if you run locally, replace it with a `pd.read_csv("data/<file>.csv")` path.
