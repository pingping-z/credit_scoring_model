# Credit Scoring Model for New Borrowers
A logistic regression–based scorecard using binning, WOE encoding, and class-imbalance correction.

## Overview
This project implements a full credit scoring pipeline for **first-time borrowers** using classical scorecard methodology.  
The end-to-end workflow includes preprocessing, binning, WOE transformation, logistic regression modelling, and final scorecard generation.  
All steps are implemented inside the provided Jupyter notebook.

---

## 1. Data Preprocessing
- Missing-value imputation  
- Outlier removal based on domain rules  
- Class-imbalance correction using **SMOTE**  
- Dataset re-indexing and column alignment  

---

## 2. Feature Binning & WOE Encoding
- Automatic optimal binning via **Chi-square merging**  
- Manual binning for irregular or non-monotonic variables  
- Weight of Evidence (**WOE**) calculation per bin  
- Construction of the final WOE-transformed dataset  

---

## 3. Logistic Regression Model
- Logistic regression trained on WOE features  
- Model evaluation: **AUC**, accuracy  
- Extraction of coefficients for scorecard scaling  

---

## 4. Scorecard Generation
- Base score computation  
- Bin-level scores computed by:  
  **Score = WOE × (−B × coefficient)**  
- Export of complete score table to `Score_data.csv`  

---

## Repository Structure<br>
model.ipynb # Model <br>
cs-training.csv # Raw training dataset <br>
model_data.csv # Cleaned training data after preprocessing <br>
vali_data.csv # Validation dataset <br>
Score_data.csv #Exported scorecard (base score + per-bin feature scores) <br>
README.md

