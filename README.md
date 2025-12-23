# SexEst_Notebooks

Jupyter notebooks for training machine learning models that predict biological sex from skeletal measurements. These notebooks produce the models deployed in the [SexEst web application](http://sexest.cyi.ac.cy/).

[![DOI](https://img.shields.io/badge/DOI-10.1002%2Foa.3109-blue)](https://doi.org/10.1002/oa.3109)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](LICENSE)
[![Demo](https://img.shields.io/badge/Demo-sexest.cyi.ac.cy-orange)](http://sexest.cyi.ac.cy/)

## Overview

Skeletal sex estimation is essential in osteoarchaeology and forensic anthropology. This project evaluates multiple machine learning classifiers on worldwide cranial and postcranial measurements and deploys the best-performing models (XGBoost, LightGBM, Linear Discriminant Analysis) in a free, open-source web application.

## Notebooks

| Notebook | Dataset | Measurements | Sample Size |
|----------|---------|--------------|-------------|
| `howell_dataset_analysis.ipynb` | Howells craniometric | 32 cranial dimensions (GOL, NOL, BNL, BBH, XCB, etc.) | >2,500 individuals |
| `goldman_dataset_analysis.ipynb` | Goldman osteometric | 11 postcranial dimensions (BIB, HML, HHD, FML, TML, etc.) | ~1,500 individuals |

## What the notebooks do

1. **Load data** — Import CSV files from the `datasets/` directory
2. **Preprocess** — Handle missing values (KNN imputation, iterative imputation), average left/right measurements, encode sex labels
3. **Feature selection** — Select measurement subsets for modelling
4. **Model training** — Train and compare 14 classifiers:
   - Logistic Regression, Decision Tree, SVM, Gaussian Process
   - Random Forest, AdaBoost, Gradient Boosting, Extra Trees
   - Gaussian Naive Bayes, k-Nearest Neighbors
   - Linear/Quadratic Discriminant Analysis
   - **XGBoost**, **LightGBM**
5. **Hyperparameter tuning** — Grid search, randomized search, Bayesian optimization (scikit-optimize)
6. **Export models** — Save trained models as `.dat` files (pickle) for use in the SexEst app

## Requirements

### Python packages

```
pandas
numpy
scipy
matplotlib
seaborn
scikit-learn
xgboost
lightgbm
scikit-optimize
joblib
```

### Environment setup

```bash
# Create virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate  # macOS/Linux
# .venv\Scripts\activate   # Windows

# Install dependencies
pip install pandas numpy scipy matplotlib seaborn scikit-learn xgboost lightgbm scikit-optimize joblib

# Or with conda
conda create -n sexest python=3.10
conda activate sexest
conda install pandas numpy scipy matplotlib seaborn scikit-learn xgboost lightgbm
pip install scikit-optimize
```

### Data files

The notebooks require CSV datasets that are **NOT included** in this repository. See [`DATA_AVAILABILITY.md`](DATA_AVAILABILITY.md) for download instructions.

| File | Description | Download |
|------|-------------|----------|
| `datasets/Howell.csv` | Howells craniometric training data | [Auerbach DATA page](https://web.utk.edu/~auerbach/DATA.htm) |
| `datasets/HowellTest.csv` | Howells craniometric test partition | Same as above |
| `datasets/Goldman.csv` | Goldman osteometric data | Same as above |

## Running the notebooks

1. Download datasets and place in `datasets/` directory
2. Open notebooks in Jupyter or VS Code
3. Run cells sequentially — the notebooks are designed to be executed top-to-bottom
4. Trained models will be saved as `.dat` files in the working directory

```bash
# Start Jupyter
jupyter notebook

# Or in VS Code, open .ipynb files directly
```

## Output

The notebooks export trained models as pickle files:
- `lda_model_*.dat` — Linear Discriminant Analysis
- `xgb_model_*.dat` — XGBoost
- `lgb_model_*.dat` — LightGBM

These models are used by the [SexEst Streamlit app](https://github.com/cconsta1/SexEst.git).

## Citation

If you use these notebooks or models, please cite:

> Constantinou, C., et al. (2023). SexEst: A machine learning web application for skeletal sex estimation. *International Journal of Osteoarchaeology*. https://doi.org/10.1002/oa.3109

```bibtex
@article{constantinou2022sexest,
  title={SexEst: An open access web application for metric skeletal sex estimation},
  author={Constantinou, Chrysovalantis and Nikita, Efthymia},
  journal={International Journal of Osteoarchaeology},
  volume={32},
  number={4},
  pages={832--844},
  year={2022},
  publisher={Wiley Online Library}
}
```

## Links

| Resource | URL |
|----------|-----|
| Paper | https://doi.org/10.1002/oa.3109 |
| Live demo | http://sexest.cyi.ac.cy/ |
| Web app repository | https://github.com/cconsta1/SexEst.git |
| Training notebooks | https://github.com/cconsta1/SexEst_Notebooks.git |
| Original datasets | https://web.utk.edu/~auerbach/DATA.htm |

## License

Apache License 2.0. See [`LICENSE`](LICENSE).