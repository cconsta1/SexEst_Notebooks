# Datasets directory

This directory is the expected location for the original datasets used by the notebooks in this repository. The notebooks expect CSV files exported from the original data sources; they are NOT included here by default for licensing and redistribution reasons.

Where to obtain the data
- The datasets are publicly available from Dr. B. Auerbach's site (Auerbach hosts both datasets and related documentation): https://web.utk.edu/~auerbach/DATA.htm

Typical filenames used by the notebooks
- `Howell.csv`
- `HowellTest.csv`
- `Goldman.csv`

Example load commands used in the notebooks

- `raw_data_howell = pd.read_csv("datasets/Howell.csv", header = 0, encoding= 'unicode_escape')`
- `raw_data_howell_test = pd.read_csv("datasets/HowellTest.csv", header = 0, encoding= 'unicode_escape')`
- `raw_data_goldman = pd.read_csv("datasets/Goldman.csv", header = 0, encoding= 'unicode_escape')`

Provenance, redistribution, and hosting guidance
- Goldman Osteometric Data Set: postcranial measurements collected by Dr. Benjamin Auerbach. See the dataset page on Auerbach's site for full details and citation instructions.
- William W. Howells Craniometric Data Set: cranial measurements collected by Dr. William Howells. See Auerbach's site for the Howells dataset page and citation guidance.

Please do NOT redistribute these datasets from this repository. Instead, ask collaborators to download them directly from the official source (Auerbach's site). If you must supply data for reproducibility in a controlled environment (for example, a journal supplementary archive), follow the dataset owners' terms and cite them appropriately.

If you have questions about dataset licensing or long-term hosting, contact Dr. Auerbach as noted on the data pages; he is working to move the datasets to a more stable repository.