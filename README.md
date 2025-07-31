# Predicting CpG Methylation Sites in *Arabidopsis thaliana* Chromosome 1

This project applies machine learning techniques to predict CpG methylation sites in **Arabidopsis thaliana** using **GC content** and **nucleotide composition**. The goal is to demonstrate that simple sequence-based features can provide strong predictive power, reducing reliance on costly experimental methods like bisulfite sequencing.


##  Project Overview

- **Objective**: Predict CpG methylation status using only local sequence features.
- **Data**: Publicly available BEDGraph (methylation data) and FASTA (reference genome) files.
- **Models Used**: 
  - `SGDClassifier` from scikit-learn  
  - `XGBoost` for gradient-boosted decision trees
- **Outcome**: XGBoost achieved outstanding results with **97% precision/recall** and **AUC = 1.0**, proving the hypothesis.

## Files in this Repository

| File | Description |

| `CpG_Methylation_Prediction_Arabidopsis_ZarifaKabir.pdf` | Final report including the project summary, methods, results, discussion, and code |
| `cpg_predictor.ipynb` | Jupyter notebook with complete code for preprocessing, feature engineering, model training, and evaluation |
| `requirements.txt` | Python packages needed to run the code |
| `README.md` | You're here! Summary and instructions for the project |


## Key Methods

- Extract ±50bp sequence windows around CpG sites
- Calculate GC content and nucleotide composition (A, T, G, C frequency)
- Generate balanced negative samples (non-CpG regions)
- Train and evaluate two classifiers
- Analyze performance metrics and feature importance

## Results

| Model        | Accuracy | Precision | Recall | AUC  |
|--------------|----------|-----------|--------|------|
| SGDClassifier | ~75%     | 0.77      | 0.72   | 0.84 |
| XGBoost       | ~97%     | 0.97      | 0.97   | 1.00 |

- GC content was consistently the most important feature across both models.
- XGBoost outperformed SGDClassifier by a wide margin.


## How to Run

1. Clone this repo:
   ```bash
   git clone https://github.com/zarifamk01/cpg-methylation-prediction.git
   cd cpg-methylation-prediction
