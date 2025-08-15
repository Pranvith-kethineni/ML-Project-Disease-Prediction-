# ML-Project-Disease-Prediction-
Overview
This project demonstrates the development, training, evaluation, and deployment of a machine learning model for disease diagnosis using anonymized patient data. The pipeline utilizes the Random Forest Classifier and addresses imbalanced datasets with SMOTE. Comprehensive model evaluation and cross-validation are included for robust performance.

Project Files
report.pdf: Detailed project report, methodology, and evaluation results.

code.ipynb: Main Jupyter notebook with reproducible code for the full ML pipeline.

SE22UCSE133_predictions.csv: Final model predictions on the test dataset.

Dataset Description
Train Dataset (Disease_train.csv):

patient_id: Unique patient identifier

feature_1 to feature_n: Numeric anonymized features

diagnosis: Target (0 = no disease, 1 = disease)

Test Dataset (Disease_test.csv):

Same features as training, without the target.

ML Pipeline
1. Preprocessing
Missing Values: Checked and handled (none found in sample).

Feature Extraction: Dropped patient_id and diagnosis for features.

Standardization: Applied to all features for uniform contribution.

2. Imbalanced Data Handling
SMOTE: Synthetic Minority Over-sampling Technique applied to the scaled feature set to balance class distribution.

3. Model Development
Random Forest Classifier:

Initialized with random_state=42 for reproducibility.

Hyperparameter Tuning:

Performed using GridSearchCV, optimizing parameters like n_estimators, max_depth, min_samples_split, min_samples_leaf, and bootstrap.

4. Evaluation
Validation Split: 80:20 for training/validation.

Metric: ROC-AUC Score (0.96 on validation set).

Cross Validation: 5-fold performed with mean accuracy of 0.951 and low standard deviation (0.0006), indicating stability.

5. Prediction & Output
Test data standardized.

Predictions generated and saved in SE22UCSE133_predictions.csv.

Script ensures output file is correctly saved.

Reproducibility
All key steps, including preprocessing, model training, evaluation, hyperparameter tuning, and predictions, are fully documented and reproducible in code.ipynb.

How to Run
Clone Repo

text
git clone <repo_url>
cd <repo_name>
Install Requirements

text
pip install -r requirements.txt
Run Notebook
Launch code.ipynb in Jupyter or Google Colab to execute the full ML pipeline.

Results Summary
Model	ROC-AUC (Validation)	Cross-Validation Mean	Std. Dev.
Random Forest (best)	0.96	0.951	0.0006
Author
Name: K. Pranvith Chowdary

ID: SE22UCSE133

License
This project is open for educational and academic use.

For further details, refer to report.pdf and comments within code.ipynb.
