# Cancer-Drug-Response-ML
This project explores how different biological and experimental features relate to cancer drug sensitivity. Using the Genomics of Drug Sensitivity in Cancer (GDSC) dataset from Kaggle, I trained a LightGBM model to predict LN_IC50 values for various drugs across cancer cell lines. The goal was to build a simple, interpretable model and understand which features contribute most to drug response.
# Dataset
Kaggle source: 

    - https://www.kaggle.com/datasets/samiraalipour/genomics-of-drug-sensitivity-in-cancer-gdsc/data?select=GDSC_DATASET.csv

The dataset includes a mix of identifiers, drug‑response metrics, biological annotations, and experimental metadata. Some of the main columns are:
- COSMIC_ID, CELL_LINE_NAME – cell‑line identifiers
- TCGA_DESC, Cancer Type – tissue and cancer‑type labels
- DRUG_ID, DRUG_NAME – drug information
- LN_IC50, AUC, Z_SCORE – drug‑response measurements
- Growth Properties – adherent vs. suspension
- Screen Medium – assay conditions
- TARGET, TARGET_PATHWAY – drug target annotations
- CNA, Gene Expression, Methylation – high‑level genomic feature categories
The model uses LN_IC50 as the prediction target.
# What I Did
- Loaded and cleaned the dataset
- One‑hot encoded categorical features
- Split the data into train/test sets
- Trained a LightGBM regression model
- Tuned hyperparameters with RandomizedSearchCV
- Evaluated performance (R², RMSE)
- Analyzed feature importance and biological patterns
All steps are implemented in a single notebook.
# Model Performance
The final LightGBM model achieved:
- RMSE: 1.1717
- R²: 0.8201
- Correlation: 0.9066
These results show that the model captures a large portion of the variation in LN_IC50 and produces predictions that correlate strongly with the true drug‑response values.
# Main Insights
Some of the strongest predictors were:
- Suspension growth (common in hematopoietic cancers)
- Leukemia and lymphoma tissues
- ERK/MAPK and PI3K–mTOR pathway features
- DNA replication and mitosis pathways
- Drug identity (e.g., bortezomib, gemcitabine, rapamycin)
These patterns match known drug‑response behavior in cancer biology, suggesting the model is capturing meaningful biological signals.
# How to Run
- Clone the repository
- Install the required Python packages:
pandas, numpy, scikit-learn, lightgbm, matplotlib
- Open the notebook in Jupyter
- Run all cells
The notebook is self‑contained and reproducible.
# Why I Did This Project
I wanted hands‑on experience with:
- pharmacogenomic datasets
- gradient‑boosting models
- interpreting ML results in a biological context
- organizing a small ML project clearly

