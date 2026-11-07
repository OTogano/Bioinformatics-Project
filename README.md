# Breast Tumor vs Normal Tissue: Gene Expression Analysis and Classification

**Research question:** Which genes and pathways differ in expression between breast tumor and normal tissue, and can those expression differences accurately classify samples?

## Team
- Clyde Mugambi - 166330
- Mohamed Chaudhry - 166335
- Mark Mutinda - 150066
- Matthew Wachira - 151733
- Lee Gitonga - 150465

## Data
TCGA-BRCA from the UCSC Xena browser (GDC hub): STAR gene counts (log2(count + 1)), the phenotype table, and the Ensembl gene ID map. The data is not stored in this repo because of its size. See [SETUP.md](SETUP.md) for how to get it.

## Repository structure
```
.
├── README.md
├── SETUP.md
└── notebook/
    └── BRCA_Tumor_vs_Normal_Expression_Analysis.ipynb
```

## Project stages
| Stage | Status |
|---|---|
| 1. Question and objectives | In the notebook introduction |
| 2. Data acquisition | Done |
| 3. Pre-processing and quality control | Done |
| 4. Exploratory data analysis | To do |
| 5. Core analysis (differential expression) | To do |
| 6. Biological interpretation | To do |
| 7. Machine learning | To do |
| 8. Conclusions | To do |

## Cleaned data (output of Stages 2 and 3)
1,208 samples (1,095 primary tumor, 113 normal) and 28,342 genes, split into `X_clean.csv.gz`, `y_labels.csv`, `sample_metadata.csv` and `gene_map_clean.csv`. Notes for later stages: the data is not scaled (fit scaling on training data only), classes are imbalanced, and normal samples are paired with tumors from the same patient, so split by patient.

## Getting started
See [SETUP.md](SETUP.md).
