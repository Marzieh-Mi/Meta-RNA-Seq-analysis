## Project Overview 
This repository outlines a standardized computational framework for conducting meta-analysis on transcriptomic data. The pipeline is engineered to integrate various RNA-Seq datasets.

## 1. Analytical Architecture 
The workflow follows to a strict statistical approach to maintain data integrity across diverse sources:

# Data Harmonization: 
Applying CPM/TPM normalization to ensure consistent variance across varying sequencing depths. 

# Visualization and Batch effects detection: 
Employing Principal Component Analysis (PCA) and Multi-Dimensional Scaling (MDS), and Boxplots to evaluate batch effects.


# Differential Expression: 
Utilizing DESeq2 and RankProd.


## Steps included:
1. CPM/TPM normalization
2. PCA plot
3. MDS plot
4. Box plot 
5. Exploratory analysis of gene expression

## 2. Tools:
- R (DESeq2, RankProd)


## 3. Related Repositorie:
Downstream functional analysis (GO, promoter, miRNA)


```mermaid
graph TD
    A[Multi-study Count Matrices] --> B(CPM/TPM Normalization)
    B --> C{Batch Effect Detection}
    C --> D[PCA Plot]
    C --> E[MDS Plot]
    C --> F[Boxplots]
    D & E & F --> G{Correction Needed?}
    G -- Yes --> H[ComBat / limma removeBatchEffect]
    G -- No --> I[Proceed to Meta-Analysis]
    H --> I
