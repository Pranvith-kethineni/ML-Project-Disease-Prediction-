# ML-Project-Disease-Prediction-
# Machine Learning with Python: Disease Classification Project

## Overview

This project demonstrates the development, training, evaluation, and deployment of a **machine learning model for disease diagnosis** using anonymized patient data. The pipeline utilizes the Random Forest Classifier and addresses **imbalanced datasets** with SMOTE. Comprehensive model evaluation and cross-validation are included for robust performance.

***

## Project Files

- `report.pdf`: Detailed project report, methodology, and evaluation results.
- `code.ipynb`: Main Jupyter notebook with reproducible code for the full ML pipeline.
- `SE22UCSE133_predictions.csv`: Final model predictions on the test dataset.

***

## Dataset Description

- **Train Dataset** (`Disease_train.csv`):  
  - `patient_id`: Unique patient identifier  
  - `feature_1` to `feature_n`: Numeric anonymized features  
  - `diagnosis`: Target (0 = no disease, 1 = disease)  
- **Test Dataset** (`Disease_test.csv`):  
  - Same features as training, without the target.

***

## ML Pipeline

### 1. Preprocessing

- Checked and handled missing values (none found).
- Extracted features by dropping `patient_id` and `diagnosis`.
- Standardized features to ensure equal contribution.

### 2. Handling Imbalanced Data

- Applied SMOTE (Synthetic Minority Over-sampling Technique) to balance the dataset.

### 3. Model Development

- Used a Random Forest Classifier with `random_state=42`.
- Performed hyperparameter tuning using GridSearchCV on parameters:
  - `n_estimators`: [100,max_depth`: [10,`min_samples_split`: [2,  - `min_samples_leaf`:[1][2]
  - `bootstrap`: [True, False]

### 4. Evaluation

- Split training data into training and validation sets (80:20).
- Evaluated on validation set using ROC-AUC metric: **0.9613**.
- Performed 5-fold cross-validation resulting in:
  - Mean accuracy: **0.95075**
  - Standard deviation: **0.00061**

### 5. Prediction and Output

- Standardized test dataset.
- Generated predictions with the best model.
- Saved predictions to `SE22UCSE133_predictions.csv`.

***

## Results Summary

| Model              | ROC-AUC (Validation) | Cross-Validation Mean | Std. Deviation |
|--------------------|----------------------|----------------------|----------------|
| Random Forest      | 0.9613               | 0.95075              | 0.00061        |

***

## How to Run

1. **Clone the repository**  
   ```bash
   git clone 
   cd 
   ```
2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the notebook**  
   Open `code.ipynb` in Jupyter or Google Colab to execute the full ML pipeline.

***

## Author

- **Name:** K. Pranvith Chowdary  
- **ID:** SE22UCSE133

***

## License

This project is open for educational and academic use.

***

*For more details, please refer to the `report.pdf` and the code comments in `code.ipynb`.*
