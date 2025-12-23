# Data analysis notebooks

This repository contains the Jupyter notebooks used to train and evaluate the models packaged in the SexEst web application (models in the SexEst repository). The notebooks reproduce the data processing, feature selection and model-training pipelines used in the paper: "SexEst — Skeletal sex estimation using machine learning" (see citation below).

Key contents
- **Notebooks:** `howell_dataset_analysis.ipynb`, `goldman_dataset_analysis.ipynb` — these notebooks load the public datasets (Howells craniometric; Goldman osteometric), perform cleaning and preprocessing, run model experiments (XGBoost, LightGBM, LDA and related comparisons), and export model metadata/artifacts used in the SexEst app.
- **datasets/** — placeholder directory where the CSV dataset files should be placed (see `datasets/README.md` and `DATA_AVAILABILITY.md` for provenance and download instructions).

What the notebooks do (short)
- Load raw CSVs for the Howells and Goldman datasets.
- Clean and harmonize column names and missing values.
- Select measurement sets used for modelling (cranial vs osteometric feature sets).
- Run cross-validation experiments and hyperparameter tuning for candidate classifiers (XGBoost, LightGBM, LDA and others as described in the paper).
- Generate model artifacts (model metadata and export files) and evaluation reports used by the Streamlit app in the main `SexEst` project.

Data required
- The notebooks require the original CSV versions of the Goldman and Howells datasets. These files must be downloaded from the official source (see `DATA_AVAILABILITY.md`) and placed inside the `datasets/` directory with the expected names:

- `datasets/Howell.csv`
- `datasets/HowellTest.csv`
- `datasets/Goldman.csv`

Example load commands used in the notebooks:

- `raw_data_howell = pd.read_csv("datasets/Howell.csv", header = 0, encoding= 'unicode_escape')`
- `raw_data_howell_test = pd.read_csv("datasets/HowellTest.csv", header = 0, encoding= 'unicode_escape')`
- `raw_data_goldman = pd.read_csv("datasets/Goldman.csv", header = 0, encoding= 'unicode_escape')`

Important: Do not commit or redistribute these dataset files unless you have explicit permission from the dataset owners. See `DATA_AVAILABILITY.md` for provenance and citation guidance.

Citation & links
- Paper / DOI: https://doi.org/10.1002/oa.3109 — please cite this paper if you use the models or notebooks in published work.
- Live demo (SexEst web app): http://sexest.cyi.ac.cy/
- Model training notebooks (this repository): https://github.com/cconsta1/SexEst_Notebooks.git
- Main application (pre-trained models & Streamlit UI): https://github.com/cconsta1/SexEst.git

Reproducing the app models
If you plan to re-run experiments and retrain models, follow the steps in each notebook. Keep in mind: training may require additional packages (see the SexEst repository `requirements.txt`), and model exports in `models_*` directories can be large.

Environment
- Using Anaconda or a virtual environment is recommended. Install required packages with `pip` or `conda` as needed.

Recommended housekeeping
- Add a `.gitignore` to avoid committing virtual environments, caches, notebook checkpoints, and large model binaries. A suggested `.gitignore` has been added to this repository.

If you want me to also run or validate the notebooks locally (execute them, produce HTML/HTML reports, or export model artifacts), tell me which notebook to run and I will prepare an execution plan.