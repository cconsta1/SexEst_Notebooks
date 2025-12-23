# SexEst_Notebooks — Model Training Notebooks

This repository contains the Jupyter notebooks used to train and evaluate the machine learning models deployed in the [SexEst web application](http://sexest.cyi.ac.cy/). The notebooks reproduce the data processing, feature selection, and model-training pipelines described in the associated paper.

## Notebooks

| Notebook | Dataset | Description |
|----------|---------|-------------|
| `howell_dataset_analysis.ipynb` | Howells craniometric | Cranial measurements; trains classifiers for sex estimation from skull dimensions |
| `goldman_dataset_analysis.ipynb` | Goldman osteometric | Postcranial measurements; trains classifiers for sex estimation from long bones and pelvis |

## What the notebooks do

1. Load raw CSV data (Howells / Goldman datasets)
2. Clean and harmonize column names and missing values
3. Select measurement subsets for modelling
4. Run cross-validation experiments and hyperparameter tuning (XGBoost, LightGBM, LDA, and others)
5. Export trained model artifacts used by the SexEst Streamlit app

## Data required

The notebooks require the original CSV datasets. **These files are NOT included** due to redistribution restrictions. Download them from the official source and place in `datasets/`:

| Filename | Source |
|----------|--------|
| `Howell.csv` | [Auerbach DATA page](https://web.utk.edu/~auerbach/DATA.htm) — Howells dataset |
| `HowellTest.csv` | Same as above |
| `Goldman.csv` | [Auerbach DATA page](https://web.utk.edu/~auerbach/DATA.htm) — Goldman dataset |

See [`DATA_AVAILABILITY.md`](DATA_AVAILABILITY.md) for full provenance, citation guidance, and redistribution policy.

### Example load commands

```python
raw_data_howell = pd.read_csv("datasets/Howell.csv", header=0, encoding='unicode_escape')
raw_data_howell_test = pd.read_csv("datasets/HowellTest.csv", header=0, encoding='unicode_escape')
raw_data_goldman = pd.read_csv("datasets/Goldman.csv", header=0, encoding='unicode_escape')
```

## Citation & Links

| Resource | Link |
|----------|------|
| Paper / DOI | https://doi.org/10.1002/oa.3109 |
| Live demo | http://sexest.cyi.ac.cy/ |
| Main app repo | https://github.com/cconsta1/SexEst.git |
| Training notebooks (this repo) | https://github.com/cconsta1/SexEst_Notebooks.git |

**Please cite the paper** if you use these notebooks or models in published work.

## Environment

Using Anaconda or a Python virtual environment is recommended. Install dependencies with `pip` or `conda`. The main SexEst repository contains a `requirements.txt` with the packages needed to run the models.

## License

This repository is licensed under the Apache License 2.0. See [`LICENSE`](LICENSE) for details.