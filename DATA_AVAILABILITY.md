# Data Availability

This document describes the provenance, download instructions, and redistribution guidance for the datasets required by the notebooks in this repository.

## Datasets

### Goldman Osteometric Data Set

- **Description:** Postcranial metric measurements (upper limb, lower limb, pelvis), sex estimates, and age categories compiled by Dr. Benjamin Auerbach (2001–2003). Global sample of ~1,500 individuals from 59 locations.
- **Download:** https://web.utk.edu/~auerbach/DATA.htm (Goldman dataset page)

### William W. Howells Craniometric Data Set

- **Description:** Cranial linear measurements collected by Dr. William Howells (1965–1980). Global comparative sample of >2,500 individuals from 28 populations.
- **Download:** https://web.utk.edu/~auerbach/DATA.htm (Howells dataset page)

## Expected filenames

Place the downloaded CSV files in the `datasets/` directory:

| Filename | Dataset |
|----------|---------|
| `Howell.csv` | Howells craniometric |
| `HowellTest.csv` | Howells craniometric (test partition) |
| `Goldman.csv` | Goldman osteometric |

## Example load commands

```python
raw_data_howell = pd.read_csv("datasets/Howell.csv", header=0, encoding='unicode_escape')
raw_data_howell_test = pd.read_csv("datasets/HowellTest.csv", header=0, encoding='unicode_escape')
raw_data_goldman = pd.read_csv("datasets/Goldman.csv", header=0, encoding='unicode_escape')
```

## Redistribution policy

These datasets are provided by Dr. Auerbach through his website. **Do NOT redistribute the files from this repository.** Direct users to download from the official source.

If you require an archival copy for reproducibility (e.g., journal supplementary materials), obtain explicit permission from the dataset owner(s) and provide proper attribution.

## Citation

When using these notebooks or models, please cite:

1. **SexEst paper:** https://doi.org/10.1002/oa.3109
2. **Datasets:** Follow the citation guidance on the Auerbach dataset pages linked above.

## Contact

For questions about dataset hosting or reuse, contact Dr. B. Auerbach (see contact info on the dataset pages).

---
*Last updated: December 2025. Check the original dataset pages for the latest terms.*
