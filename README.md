# credit scoring model
Predicting individual's credit worthiness

# Project overview 
Built a multi-class classification model

# Dataset
Source: Kaggle
Size: 100,000
Features: 
Target: 3 credit risk classes(Standard, good and poor) in 52:29:19 proportion

# Methodology
### Initial dataset
- Original dataset: 100,000
- After deduplication : 12,500
- Reason: Dataset contained multiple entries per user, kept only most recent record.

### Feature selection
Started with 25 features and remived several during exploratory analysis
-Removed features with no predictive power 

Final feature set: contained 21 features after encoding 

### Data Preprocessing
-Missing values imputation
-One hot encoding for categorical data
-Feature scaling for numerical data with Standard scaler
-SMOTE oversampling to handle class imbalance

### Models Tested
-Logistic regression
-Random forest classifier (best performer)
-Gradient boosting
-XGBoost
-Support Vector Machine

### Final Model Performance 
- **Accuracy:** 76%
- **Class 0:**   73% precision, 65% recall  
- **Class 1:**  79% precision, 76% recall
- **Class 2:**  76% precision,  88% recall    

## Key findings
-Age is the most important feature
-Feature importance scores are relatively low suggesting difficulty in modelling based on the available attributes.
-Acheiving 76% accuracy is reasonable given the dataset's limitation and probabilistic nature of credit scoring.

## Challenges
- **Challenge:** Initial accuracy was only 31% due to preprocessing errors
- **Solution:** Discovered I was using unscaled validation data after training on scaled data
- **Lesson:** Consistent preprocessing across train/validation/test sets is critical

**Challenge:** Class imbalance affecting model predictions
- **Solution:** Applied SMOTE oversampling and class weights
- **Result:** Improved from ignoring minority class to balanced predictions

**Challenge:** Stuck at 75% accuracy after trying 4 algorithms
- **Analysis:** Feature importance analysis revealed weak predictive power across all features
- **Conclusion:** Reached practical ceiling with available data; further improvement requires additional features (payment history details, employment stability, etc.)
