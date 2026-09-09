# Flow-Based Detection of VPN Traffic (ENGE817)

An interpretable XGBoost model that detects VPN traffic from flow-level metadata
in the ISCXVPN2016 dataset. Scoped STEM Research pilot; foundation for the dissertation.

- **Student:** Sokhour Lay (25314544)
- **Supervisor:** Dr Mee Loong (Bobby) Yang
- **Course:** ENGE817 STEM Research

## Data

This project uses the ISCXVPN2016 dataset from the Canadian Institute for
Cybersecurity at the University of New Brunswick. **The dataset is not included in
this repository** and must be obtained directly from the source:

<https://www.unb.ca/cic/datasets/vpn.html>

Download the Scenario A1 ARFF files and place them in:

```
data/Scenario A1-ARFF/
```

The analysis uses `TimeBasedFeatures-Dataset-15s-VPN.arff` (15-second flow timeout,
VPN versus non-VPN binary labels).

Please cite the dataset authors:

> Draper-Gil, G., Lashkari, A. H., Mamun, M. S. I., & Ghorbani, A. A. (2016).
> Characterization of encrypted and VPN traffic using time-related features.
> *Proceedings of the 2nd International Conference on Information Systems Security
> and Privacy*, 407–414.

## Setup

```bash
conda env create -f environment.yml   # or: conda env update -f environment.yml
conda activate enge817
python -m ipykernel install --user --name enge817 --display-name "ENGE817"
jupyter lab
```

Verify XGBoost: `python -c "import xgboost; print(xgboost.__version__)"`

## Structure

- `data/`      dataset location (contents not tracked in Git; see Data above)
- `notebooks/` exploratory analysis and experiments
- `src/`       reusable scripts (preprocessing, training, evaluation)
- `results/`   generated figures (tracked); model artifacts (not tracked)

## Reproducibility

Environment is pinned in `environment.yml`. Fixed random seeds are used in all
experiments. Regenerate the environment with `conda env create -f environment.yml`.
