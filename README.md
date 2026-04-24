# Exercise-Induced Transcriptomic Remodeling in MPTP Mouse Striatum

## Overview
This repository contains RNA-seq analysis of how voluntary exercise alters the striatal transcriptome in an MPTP mouse model of Parkinson’s disease.
The pipeline identifies context-dependent transcriptional changes driven by exercise specifically in the diseased brain.

```
Repository Structure
├── notebooks/
│   ├── 1_data_cleaning.Rmd
│   ├── 2_analysis.Rmd
│   └── 3_cell_type_deconvolution.Rmd
├── raw_data/
│   ├── metadata.csv
│   └── GSE82187.csv.gz   # GEO-derived reference data
└── README.md
```
## Data Setup (Required)

This repo does not include raw count matrices.

```
You must manually add the RNA-seq count matrix (CSV) files to raw_data/, in a folder called counts
raw_data/
├── metadata.csv
├── GSE82187.csv.gz        # GEO-derived reference data for cell-type deconvolution
└── counts/
    ├── MC1-1.csv
    ├── MC1-2.csv
    ├── MC1-3.csv
    ├── ...
```

## Pipeline
#### 1. Data Preprocessing

Run the first R Notebook, 1_data_cleaning.Rmd

Outputs:
```
results/
├── *.rds   # processed expression data, DESeq objects, etc.
```

#### 2. Main Analysis

Run 2_analysis.Rmd

Outputs:
```
results/
└── figures/
    ├── PCA plots
    ├── volcano plots
    ├── heatmaps
    └── pathway analyses
  ```
  
#### 3. Cell-Type Deconvolution

Run 3_cell_type_deconvolution.Rmd

Outputs:
```
results/
└── figures/
    ├── cell_type_plots/
```

