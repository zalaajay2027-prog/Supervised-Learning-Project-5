📘 Smart Outcome Predictor — Ensemble Machine Learning
1. Project Overview

Smart Outcome Predictor is a Machine Learning project that predicts student outcomes using Ensemble Machine Learning techniques.

The project performs two tasks:

🎯 Classification: Predicts completion_status
📊 Regression: Predicts final_score

The main goal is to identify students who may need academic support and help improve learning outcomes.

2. Objectives
Predict student completion status.
Predict final student score.
Compare different Machine Learning models.
Use Ensemble Learning for better predictions.
Support early identification of students who may need intervention.
3. Dataset

Dataset: Smart_Outcome_Predictor_Dataset_5200.csv.csv

Rows: 5,200
Original Columns: 19
Train Data: 4,160
Test Data: 1,040
Target Variables
Task	Target
Classification	completion_status
Regression	final_score
4. Machine Learning Workflow
Dataset
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
Preprocessing
   ↓
Train-Test Split
   ↓
Machine Learning Models
   ↓
Ensemble Models
   ↓
Model Evaluation
   ↓
Final Prediction
5. Data Preprocessing

The following preprocessing steps were used:

Removed student_id.
Converted course_start_date into useful date features.
Handled missing numerical values using Median Imputation.
Handled missing categorical values using Most Frequent Imputation.
Applied One-Hot Encoding to categorical features.
Applied StandardScaler to numerical features.
Used 80% training and 20% testing data.
6. Machine Learning Models
Decision Tree

A tree-based model used for making predictions through decision rules.

Bagging

Uses multiple models and combines their predictions to improve stability.

AdaBoost

Combines weak learners and focuses more on incorrectly predicted samples.

Gradient Boosting

Builds models sequentially where each new model improves the previous model.

LightGBM

A fast and efficient gradient boosting algorithm.

XGBoost

A powerful gradient boosting algorithm widely used for structured/tabular data.

Voting

Combines predictions from multiple models.

Hard Voting: Uses majority prediction.
Soft Voting: Uses prediction probabilities.
Stacking

Combines multiple models and uses another model to make the final prediction.

7. Classification Results
Model	Accuracy	F1 Score	ROC-AUC
AdaBoost	72.88%	72.31%	78.43%
Gradient Boosting	73.65%	73.22%	78.77%
LightGBM	71.44%	70.96%	76.54%
XGBoost	72.31%	71.93%	77.04%
🏆 Best Classification Model

Gradient Boosting — 73.65% Accuracy

8. Regression Results
Model	MAE	RMSE	R²
AdaBoost	8.8351	10.8691	0.3677
Gradient Boosting	7.8476	9.8049	0.4855
LightGBM	8.0329	10.0052	0.4642
XGBoost	8.0076	9.9706	0.4679
🏆 Best Regression Model

Gradient Boosting gives the lowest RMSE among the listed individual models.

9. Ensemble Results
Ensemble Method	Accuracy
Hard Voting	73.46%
Soft Voting	71.54%
Stacking	73.56%

Best Ensemble: Stacking — 73.56%

10. Model Charts
Chart 1 — Boosting Models Comparison
<img width="1440" height="880" alt="01_boosting_models_comparison" src="https://github.com/user-attachments/assets/55fab111-4f5b-4422-a763-74100ebef753" />

Chart 2 — Hard vs Soft Voting
<img width="1280" height="800" alt="02_hard_vs_soft_voting" src="https://github.com/user-attachments/assets/d71a4e6c-6df8-4e49-b36e-0b18a1975386" />

Chart 3 — Classification Models
<img width="1600" height="960" alt="03_classification_models_comparison" src="https://github.com/user-attachments/assets/de0c8b34-91f0-4add-a21a-4fd8daa90ddc" />

Chart 4 — Regression Models
<img width="1600" height="960" alt="04_regression_models_comparison" src="https://github.com/user-attachments/assets/ae2e5eec-243f-46aa-8063-ec500dd6ae51" />

Chart 5 — Bagging vs Boosting
<img width="1600" height="880" alt="05_bagging_vs_boosting" src="https://github.com/user-attachments/assets/39b709db-3e8e-430b-a6d1-f8725e58a484" />

Chart 6 — Tree Based Boosting
<img width="1440" height="880" alt="06_tree_based_boosting_comparison" src="https://github.com/user-attachments/assets/f9af1e17-9076-4027-9794-6bd7ae7b0872" />

Chart 7 — Voting vs Stacking
<img width="1280" height="800" alt="07_voting_vs_stacking" src="https://github.com/user-attachments/assets/2bbaa4c5-91a1-4666-81b6-6369fe6df2bf" />

Chart 8 — Final Ensemble Comparison
<img width="1760" height="960" alt="08_final_ensemble_model_comparison" src="https://github.com/user-attachments/assets/4c877794-0170-4933-9c8d-8ec9bd72886a" />

11. Ensemble Models GIF
<img width="1000" height="600" alt="ensemble_models_charts" src="https://github.com/user-attachments/assets/998a8a72-ad68-4cd7-8224-9b025eb43bd2" />

12. Business / Academic Use

This project can help educational institutions to:

Identify students who may be at risk.
Predict student performance.
Provide early academic support.
Monitor student outcomes.
Support data-driven academic decisions.

The model should be used as a decision-support tool, not as a replacement for human judgment.

13. Technologies Used
Python
Pandas
NumPy
Scikit-learn
Matplotlib
LightGBM
XGBoost
Jupyter Notebook
14. How to Run
Step 1 — Install Libraries
pip install pandas numpy matplotlib scikit-learn lightgbm xgboost
Step 2 — Open Notebook

Open:

Smart_Outcome_Predictor_Complete_Code.ipynb
Step 3 — Keep Dataset in the Same Folder
Smart_Outcome_Predictor_Dataset_5200.csv.csv
Step 4 — Run All Cells

Run the notebook from beginning to end to generate the predictions, results and charts.

15. Project Structure
Smart-Outcome-Predictor/
│
├── README.md
├── Smart_Outcome_Predictor_Complete_Code.ipynb
├── Smart_Outcome_Predictor_Dataset_5200.csv.csv
│
└── assets/
    ├── charts/
    │   ├── 01_boosting_models_comparison.png
    │   ├── 02_hard_vs_soft_voting.png
    │   ├── 03_classification_models_comparison.png
    │   ├── 04_regression_models_comparison.png
    │   ├── 05_bagging_vs_boosting.png
    │   ├── 06_tree_based_boosting_comparison.png
    │   ├── 07_voting_vs_stacking.png
    │   └── 08_final_ensemble_model_comparison.png
    │
    └── gifs/
        └── ensemble_models_charts.gif
16. Conclusion

The Smart Outcome Predictor successfully applies Ensemble Machine Learning for both classification and regression tasks.

The results show that Gradient Boosting performs strongly for the individual models, while Stacking provides the best result among the tested ensemble methods.

This project demonstrates how Machine Learning can be used to support student performance prediction and early academic intervention.

⭐ Final Result

Classification: Gradient Boosting — 73.65% Accuracy

Best Ensemble: Stacking — 73.56% Accuracy

Regression: Gradient Boosting — RMSE 9.8049
