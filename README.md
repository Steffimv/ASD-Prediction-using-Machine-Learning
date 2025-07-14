# ASD-Prediction-using-Machine-Learning
This project focuses on applying various machine learning algorithms to predict the likelihood of Autism Spectrum Disorder (ASD) based on a set of behavioral and demographic features. The code processes the dataset, trains multiple models, evaluates their performance on different data splits, and generates metrics for comparison.

### Dataset
File: train.csv
Target Column: Class/ASD (renamed to target)
Features: Behavioral scores (A1_Score to A10_Score), age, gender, jaundice, autism diagnosis history, etc.

### Preprocessing Steps:
1. Replaced '?' with NaN.
2. Converted age and A1_Score to A10_Score columns to numeric.
3. Filled missing numeric values with median/mode.
4. Encoded categorical columns using LabelEncoder.
5. Dropped irrelevant columns: ethnicity, contry_of_res, used_app_before, age_desc, relation.
6. Verified all input features are numeric.

### Models Used
Model	Abbreviation
Logistic Regression	LR
Support Vector Machine (SVC)	SVM
Decision Tree	DT
Random Forest	RF
XGBoost Classifier	XGB

Each model is evaluated using two validation splits: 70:30 and 80:20.

### Evaluation Metrics
The following metrics are calculated and stored:
Accuracy
Precision (for class 0 and 1)
Recall / Sensitivity
Specificity
F1-score (for class 0 and 1)
ROC AUC Score
Training and Testing Time

### Important Features (for interpretable models)
The ROC curve is plotted for models supporting probability estimates.

### Output
Excel File: model_results(800).xlsx
Contains evaluation results of each model across both validation splits.
ROC Curve Plots: Generated dynamically for each model (Logistic Regression, Random Forest, etc.) and split.

### Running the Script
Make sure the following packages are installed:
```
pip install numpy pandas scikit-learn xgboost matplotlib openpyxl
```
Then, simply run the script:
```
python asd_prediction_pipeline.py
```
Ensure that train.csv is in the same directory.
