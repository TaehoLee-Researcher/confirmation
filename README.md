# DNABERT-2 Functional Separation: Reproducibility Confirmation

This repository provides a **reproducibility confirmation framework**
for the analyses reported in the accompanying manuscript.

The goal of this repository is to ensure that all reported results can be
**independently and deterministically verified**.

---

## Overview

We evaluate whether DNABERT-2 embeddings can distinguish two known positive enzymes
from ten hard negative glycosyl hydrolases within a single genome.

All analyses reported in **Figure 2 (A–C)** are designed to be reproducible using
fixed embedding representations.

---

## Reproducibility Design

- **Input**: Fixed DNABERT-2 embeddings (`X_dnbert2.npy`)
- **Sample size**: 12 sequences (2 positive, 10 hard negatives)
- **Embedding dimension**: 768
- **Execution**: CPU-only, deterministic, no training

Due to potential stochasticity and hardware-dependent variation in large
pretrained language models, embedding generation is decoupled from downstream
evaluation. This ensures exact computational reproducibility of the reported
results.

---

## Repository Status

This repository is currently being populated with the following components:

- Fixed input embeddings
- A single reproducibility notebook for Figure 2 (A–C)
- Deterministic output figures and tables

Once finalized, the repository will allow any third party to reproduce all
reported analyses by running a single notebook.

---

## Notes

- No GPU is required.
- All analyses are deterministic given identical inputs.
- This repository is intended for result verification and transparency.

---

## Citation

If you use this repository for verification or reference, please cite the
corresponding manuscript.
