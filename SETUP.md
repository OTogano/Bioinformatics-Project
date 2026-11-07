# Setup Guide

## 1. Get access to the shared data
The data lives in a shared Google Drive folder called **Bioinformatics Project Dataset**, with two subfolders:

- `raw/`: the original files downloaded from UCSC Xena (TCGA-BRCA, GDC hub).
- `processed/`: the cleaned data produced by Stages 2 and 3.

To use it:
1. Open the shared folder link (ask in the group if you don't have it).
2. Right-click the folder, choose **Organize**, then **Add shortcut**, and place it in **My Drive**. The notebook looks for the folder at `My Drive/Bioinformatics Project Dataset/`, so the name must match exactly.

## 2. Open the notebook in Colab
Open `notebooks/BRCA_Tumor_vs_Normal_Expression_Analysis.ipynb` from this repo and click **Open in Colab**. Run the first code cell and allow Drive access when prompted.

## 3. Load the cleaned data
```python
import pandas as pd
PROCESSED = "/content/drive/MyDrive/Bioinformatics Project Dataset/processed/"

X = pd.read_csv(PROCESSED + "X_clean.csv.gz", index_col=0)
y = pd.read_csv(PROCESSED + "y_labels.csv", index_col=0)["label"]
meta = pd.read_csv(PROCESSED + "sample_metadata.csv", index_col=0)
genes = pd.read_csv(PROCESSED + "gene_map_clean.csv")
```
Expect `X` to be 1,208 × 28,342.

## 4. Rules for working on the data
- Do not overwrite files in `raw/` or `processed/`. Save your own outputs in a new subfolder.
- Do not scale the data before splitting. Fit scalers on training data only.
- Split by the `patient` column in `sample_metadata.csv`.
- Use Ensembl IDs as gene keys. Gene names are not unique.

## 5. Working together in the notebook
Add your stage as a new section under the matching heading. To avoid clashes, work in your own copy of the notebook and merge your section into the main one, and commit with a clear message such as `Add Stage 4: exploratory data analysis`.
