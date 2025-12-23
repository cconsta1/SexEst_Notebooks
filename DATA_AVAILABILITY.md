# Data Availability

This document describes the datasets required to run the notebooks in this repository, including provenance, download instructions, file specifications, and redistribution policy.

## Quick Start

1. Visit https://web.utk.edu/~auerbach/DATA.htm
2. Download the CSV versions of the Goldman and Howells datasets
3. Place the files in the `datasets/` directory with these exact names:
   - `Howell.csv`
   - `HowellTest.csv`
   - `Goldman.csv`

## Datasets

### Goldman Osteometric Data Set

| Property | Value |
|----------|-------|
| **Collector** | Dr. Benjamin Auerbach (2001–2003) |
| **Type** | Postcranial skeletal measurements |
| **Sample** | ~1,500 individuals from 59 worldwide locations |
| **Time period** | Throughout the Holocene (mostly preindustrial) |
| **Measurements** | Upper limb (humerus, radius), lower limb (femur, tibia), pelvis |
| **Download** | https://web.utk.edu/~auerbach/DATA.htm → Goldman dataset page |

#### Features used in the notebooks

| Abbreviation | Measurement |
|--------------|-------------|
| BIB | Bi-iliac breadth |
| HML | Humerus maximum length |
| HHD | Humerus head diameter |
| HEB | Humerus epicondylar breadth |
| RML | Radius maximum length |
| FML | Femur maximum length |
| FBL | Femur bicondylar length |
| FHD | Femur head diameter |
| FEB | Femur epicondylar breadth |
| TML | Tibia maximum length |
| TPB | Tibia plateau breadth |

### William W. Howells Craniometric Data Set

| Property | Value |
|----------|-------|
| **Collector** | Dr. William W. Howells (1965–1980) |
| **Type** | Cranial linear measurements |
| **Sample** | >2,500 individuals from 28 populations |
| **Time period** | Later Holocene |
| **Measurements** | Lengths, chords, subtenses, angles, radii |
| **Download** | https://web.utk.edu/~auerbach/DATA.htm → Howells dataset page |

#### Features used in the notebooks

| Abbreviation | Measurement |
|--------------|-------------|
| GOL | Glabello-occipital length |
| NOL | Nasio-occipital length |
| BNL | Basion-nasion length |
| BBH | Basion-bregma height |
| XCB | Maximum cranial breadth |
| XFB | Maximum frontal breadth |
| ZYB | Bizygomatic breadth |
| AUB | Biauricular breadth |
| WCB | Minimum cranial breadth |
| ASB | Biasterionic breadth |
| BPL | Basion-prosthion length |
| NPH | Nasion-prosthion height |
| NLH | Nasal height |
| JUB | Bijugal breadth |
| NLB | Nasal breadth |
| MAB | Palate breadth |
| MDH | Mastoid height |
| MDB | Mastoid breadth |
| OBH | Orbit height |
| OBB | Orbit breadth |
| DKB | Interorbital breadth |
| ZMB | Zygomaxillary breadth |
| FMB | Bifrontal breadth |
| EKB | Biorbital breadth |
| IML | Malar length, inferior |
| XML | Malar length, maximum |
| WMH | Cheek height |
| STB | Bistephanic breadth |
| FRC | Frontal chord |
| PAC | Parietal chord |
| OCC | Occipital chord |
| FOL | Foramen magnum length |

## File specifications

| Filename | Dataset | Rows | Columns | Size |
|----------|---------|------|---------|------|
| `Howell.csv` | Howells craniometric (training) | ~2,500 | 82 | ~700 KB |
| `HowellTest.csv` | Howells craniometric (test) | ~500 | 82 | ~170 KB |
| `Goldman.csv` | Goldman osteometric | ~1,500 | 40+ | ~540 KB |

## Loading the data

```python
import pandas as pd

# Howells craniometric
raw_data_howell = pd.read_csv("datasets/Howell.csv", header=0, encoding='unicode_escape')
raw_data_howell_test = pd.read_csv("datasets/HowellTest.csv", header=0, encoding='unicode_escape')

# Goldman osteometric
raw_data_goldman = pd.read_csv("datasets/Goldman.csv", header=0, encoding='unicode_escape')
```

## Redistribution policy

These datasets are hosted by Dr. B. Auerbach at the University of Tennessee. The dataset pages request:

> **Do NOT redistribute the files yourself** — instead, direct users to download them from the official source.

If you need archival copies for reproducibility (e.g., journal supplementary materials):
1. Obtain explicit permission from the dataset owner
2. Provide proper attribution and citation
3. Follow any terms specified on the dataset pages

## Citation

When using these datasets, cite:

1. **SexEst paper** (for models/methods):
   > Constantinou, C., et al. (2023). SexEst: A machine learning web application for skeletal sex estimation. *International Journal of Osteoarchaeology*. https://doi.org/10.1002/oa.3109

2. **Datasets** (follow citation guidance on the Auerbach pages):
   - Goldman Osteometric Data Set — cite Dr. Benjamin Auerbach
   - Howells Craniometric Data Set — cite Dr. William W. Howells

## Contact

For questions about dataset hosting, licensing, or reuse:
- Dr. B. Auerbach — see contact info on the [DATA pages](https://web.utk.edu/~auerbach/DATA.htm)

---
*Last updated: December 2025*
