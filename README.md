# DNABERT-2 Functional Separation: Reproducibility Confirmation

This repository provides a deterministic, repository-level reproducibility package
for Figure 2 (A–C) reported in the accompanying manuscript.

The purpose of this repository is to allow independent verification that
DNABERT-2 embeddings exhibit functional separation between two positive enzymes
and closely related hard-negative glycosyl hydrolases, using fixed inputs and
fully reproducible analysis steps.

No model training or stochastic inference is performed in this repository.

---

## Repository Structure

confirmation/
├── data/
│   ├── posneg_sequences.csv
│   └── X_dnbert2.npy
│
├── notebook/
│   └── reproduce_fig2.ipynb
│
├── outputs/
│   ├── Fig2A_PCA.png
│   ├── Fig2A_UMAP.png
│   ├── Fig2B_heatmap.png
│   └── Fig2C_holdout_ranking.csv
│
├── requirements.txt
└── README.md

---

## Contents

- posneg_sequences.csv  
  Sequence metadata including enzyme names and binary labels
  (POS = functional enzyme, NEG = hard negative)

- X_dnbert2.npy  
  Fixed 768-dimensional DNABERT-2 embeddings corresponding to the sequences
  in posneg_sequences.csv

- reproduce_fig2.ipynb  
  Single-notebook pipeline that reproduces Figure 2A–C

---

## Reproducibility Design

This repository enforces strict reproducibility through:

- Fixed, precomputed DNABERT-2 embeddings
- CPU-only execution
- Fixed random seed (SEED = 42)
- No external downloads during analysis
- No dependence on GPU, CUDA, or backend-specific kernels

All figures are generated deterministically from the provided inputs.

---

## Environment Setup

Python version: 3.9 or later

Install required packages:

pip install -r requirements.txt

---

## How to Reproduce Figure 2

1. Open the notebook:

notebook/reproduce_fig2.ipynb

2. Run all cells from top to bottom without modification.

3. Output files will be saved automatically to:

outputs/

---

## Reproduced Outputs

- Fig2A_PCA.png  
  PCA projection of DNABERT-2 embeddings

- Fig2A_UMAP.png  
  UMAP projection using fixed random seed

- Fig2B_heatmap.png  
  Cosine similarity heatmap across all enzymes

- Fig2C_holdout_ranking.csv  
  Leave-one-out functional retrieval results

---

## Notes on Embeddings

The embeddings in X_dnbert2.npy were generated using the model:

zhihan1996/DNABERT-2-117M

They are included directly to ensure exact reproducibility and to avoid
hardware- or version-dependent variation in transformer inference.

---

## Intended Use

This repository is intended for:

- Peer reviewers
- Editors
- Readers verifying reproducibility claims

It is not intended as a training or benchmarking framework.

---

## Contact

For questions regarding this reproducibility package, please contact
the corresponding author.
