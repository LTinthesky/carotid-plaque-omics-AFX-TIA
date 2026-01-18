# carotid-plaque-omics-AFX-TIA
# Carotid plaque transcriptomic analysis (AFX, TIA, stroke)

This repository contains the R code used to perform the main bulk RNA-seq
analyses reported in the manuscript:
"Plaque molecular profiling reveals differences between amaurosis fugax,
cerebral TIA, and stroke."

The code reproduces:
- Differential gene expression analysis using DESeq2
- Principal component analysis (PCA)
- PCA figures shown in the manuscript

---

## Data availability

Human bulk RNA-seq data and associated clinical metadata are available via
Dataverse and are not stored in this repository due to data governance and
privacy considerations.

Data access DOIs:
- https://doi.org/10.34894/D1MDKL
        
        
        
        
- https://doi.org/10.34894/4IKE3T
        
        
        
        

After obtaining access, place the following files in the `data/` directory:

- `normalized_genecounts.csv`
  (genes × samples integer count matrix; column names = sample IDs)

- `data20260106_complete.sav`
  (clinical metadata; must contain a column `STUDY_NUMBER` matching sample IDs)

Required metadata column:
- `sym_4g` (clinical group: asymptomatic, AFX, TIA, stroke)

Optional metadata column:
- `batch` (technical sequencing batch)

---

## Software requirements

- R version ≥ 4.2
- Required R packages:
  - DESeq2
  - dplyr
  - factoextra
  - ggplot2
  - matrixStats
  - haven

---

## How to run the analysis

From the project root directory in R:

```r
source("code/01_deseq2_pca.R")
