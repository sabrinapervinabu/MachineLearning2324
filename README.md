# Machine Learning Homework 2024 – BCG

This repository contains the solution to the Machine Learning 2024 homework by Francesco Trovò, Vanja Miskovic, and Stefano Samele (Politecnico di Milano).  
The goal of this project is to **predict taxonomic identity and genetic composition based on codon usage bias**.

---

## Files
- `ABU_ML_homework2024_BCG.ipynb`: Main Jupyter Notebook with the full analysis.
- `train.csv`: Training dataset (10,422 samples × 67 features).
- `test.csv`: Test dataset (2,606 samples × 66 features, **missing the AGA codon frequency**).
- `ml_homework_2024.pdf`: Project instructions and background.

---
## Project Overview
The dataset originates from Khomtchouk, 2020 and includes codon usage frequencies for 13,028 organisms.  
Each sample is described by:
- 64 codon frequency features
- Codon count
- Species identifiers
- Two classification targets:
  - `Kingdom` (11 biological categories, e.g., virus, bacteria, mammal, etc.)
  - `DNAtype` (12 types, e.g., genomic, mitochondrial, chloroplast, etc.)
---
### 1. Exploratory Data Analysis & Clustering
- Analyze distributions and correlations of codon features
- Visualize class separability
- Apply clustering algorithms to detect inherent structures
- Compare clustering performances using metrics like Silhouette, Calinski-Harabasz, etc.

### 2. Classification (Kingdom Prediction)
- Feature selection and dimensionality reduction
- Compare classifiers (e.g. SVM, Random Forest, XGBoost)
- Evaluate models with cross-validation
- Final test evaluation with and without AGA feature

### 3. Regression (AGA Imputation)
- Train a regression model to predict AGA codon frequency using the other 65 codons
- Compare multiple regression models (e.g. Linear, Ridge, Gradient Boosting)
- Validate imputation robustness

### 4. Final Integration
- Apply regression model to impute AGA values in test set
- Re-evaluate best classifier performance using the recovered AGA values

---

## Run the Notebook
- Install required Python libraries:
```bash
pip install numpy pandas scikit-learn matplotlib seaborn xgboost jupyter
```
- Clone the repository:
```
git clone https://github.com/yourusername/ml-homework-2024.git
cd ml-homework-2024
```
- Launch Jupyter:
```
jupyter notebook ABU_ML_homework2024_BCG.ipynb
```
