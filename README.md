# Flow-Based Detection of VPN Traffic (ENGE817)

An interpretable XGBoost model that detects VPN traffic from flow-level metadata
in the ISCXVPN2016 dataset. Scoped STEM Research pilot; foundation for the dissertation.

- **Student:** Sokhour Lay (25314544)
- **Supervisor:** Dr Mee Loong (Bobby) Yang
- **Course:** ENGE817 STEM Research

## Setup

```bash
conda env create -f environment.yml   # or: conda env update -f environment.yml
conda activate enge817
python -m ipykernel install --user --name enge817 --display-name "ENGE817"
jupyter lab
```

Verify XGBoost: `python -c "import xgboost; print(xgboost.__version__)"`

## Structure

- `data/`      raw and processed dataset (not tracked in Git)
- `notebooks/` exploratory analysis and experiments
- `src/`       reusable scripts (preprocessing, training, evaluation)
- `results/`   figures, metrics, model artifacts (not tracked in Git)

## Reproducibility

Environment is pinned in `environment.yml`. Fixed random seeds are used in all
experiments. Regenerate the environment with `conda env create -f environment.yml`.
