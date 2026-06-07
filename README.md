# Calibrated Uncertainty Quantification for Patient-Level AML Drug Sensitivity Prediction Using Split Conformal Prediction

![Python](https://img.shields.io/badge/Python-3.9+-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Preprint-orange)

## Overview

This repository contains the full analysis pipeline for our study applying **split conformal prediction** to patient-level ex vivo AML drug response prediction using the BeatAML 2.0 cohort.

We demonstrate that statistically calibrated prediction intervals are achievable for 122 drugs across 318 AML patients, and that predictive uncertainty varies substantially by drug mechanism of action.

**Key results:**
- Empirical coverage: 81.4% / 90.7% / 95.5% at nominal 80% / 90% / 95% levels
- Prediction interval widths range 3.4-fold across drug classes
- Uncertainty is drug-driven rather than patient-subtype-driven

## Repository Structure
aml-conformal-prediction/
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_preprocessing.ipynb
│   ├── 03_baseline_models.ipynb
│   ├── 04_conformal_prediction.ipynb
│   ├── 05_uncertainty_analysis.ipynb
│   └── 06_figures_paper.ipynb
├── results/
│   ├── figures/
│   │   ├── fig1_baseline_performance.png
│   │   ├── fig2_calibration_curves.png
│   │   ├── fig3_uncertainty_by_drug_class.png
│   │   ├── fig4_top_bottom_drugs.png
│   │   └── fig5_uncertainty_heatmap.png
│   ├── baseline_results.csv
│   ├── conformal_results.csv
│   └── uncertainty_per_patient.csv
├── environment.yml
└── README.md

## Data

Data are publicly available and must be downloaded separately:

| Source | Files needed |
|---|---|
| [cBioPortal BeatAML 2.0](https://www.cbioportal.org/study/summary?id=aml_ohsu_2022) | `data_mrna_seq_rpkm_zscores_ref_all_samples.txt`, `data_clinical_sample.txt`, `data_clinical_patient.txt`, `data_mutations.txt` |
| [Bottomly et al. 2022 Supplementary](https://doi.org/10.1016/j.ccell.2022.07.002) | `41586_2018_623_MOESM3_ESM.xlsx` (Table S10) |
| [BeatAML GitHub](https://github.com/biodev/beataml2.0_data) | `beataml_waves1to4_sample_mapping.xlsx` |

Place all files in `data/raw/` before running notebooks.

## Installation

```bash
conda create -n drug_ai python=3.9
conda activate drug_ai
conda install -c conda-forge scikit-learn xgboost pandas numpy matplotlib mapie
```

## Usage

Run notebooks in order (01 → 06). Each notebook saves outputs to `data/processed/` or `results/` for use by subsequent notebooks.

## Citation

> Shokrzadeh A, Shokrzadeh P. Calibrated Uncertainty Quantification for Patient-Level AML Drug Sensitivity Prediction Using Split Conformal Prediction. 2025. GitHub: https://github.com/Amir-Shokrzadeh/aml-conformal-prediction

Preprint coming soon on bioRxiv.

## Authors

**Amir J. Shokrzadeh**
MSc AI Engineering student
GitHub: [@Amir-Shokrzadeh](https://github.com/Amir-Shokrzadeh)
**Pegah Shokrzadeh**
MSc Pediatric Nursing 

## License

MIT
