# Supervised-Learning-Project-5

🎓 Smart Outcome Predictor
Ensemble Machine Learning Project for Student Completion & Final Score Prediction

PythonJupyter NotebookScikit--learnLightGBMXGBoost

📌 Project Overview
Smart Outcome Predictor is an ensemble machine learning project for predicting student learning outcomes.

The project contains two machine learning tasks:

Classification → Predict completion_status
Regression → Predict final_score
The notebook covers:

Data loading and inspection
Data cleaning
Date/time feature extraction
Missing-value handling
Categorical encoding
Feature preprocessing
Train/test splitting
Decision Tree models
Bagging
AdaBoost
Gradient Boosting
LightGBM
XGBoost
Hard Voting
Soft Voting
Stacking
Classification evaluation
Regression evaluation
Model comparison
Final model recommendation
🎯 Objectives
Prepare and preprocess student learning data.
Predict whether a student will complete a course.
Predict the student's final score.
Understand and compare ensemble learning techniques.
Evaluate classification models using multiple metrics.
Evaluate regression models using error and goodness-of-fit metrics.
Compare different ensemble strategies.
Select the best-performing model for the given dataset.
📊 Dataset
Dataset: Smart_Outcome_Predictor_Dataset_5200.csv.csv

Property Value

Rows 5,200 Original columns 19 Train/Test split 80% / 20% Training samples 4,160 Testing samples 1,040 Classification target completion_status Regression target final_score Processed features 30

Main Features
Age
Country/Region
Device Type
Education Background
Course Level
Course Category
Week of Year
Sessions
Time Spent Hours
Videos Watched
Quiz Attempts
Assignments Submitted
Forum Posts
Average Quiz Score
Attendance Rate
Course Start Date
Year
Month
Day
🧠 Machine Learning Concepts Used
1. Machine Learning
Machine Learning allows a computer to learn patterns from data and make predictions on new data.

In this project:

Input = student learning/activity information
Output 1 = completion status
Output 2 = final score
2. Supervised Learning
This project uses supervised learning because the target/output is already available in the dataset.

Classification
The model predicts a category:

Student Features → Model → completion_status
Regression
The model predicts a numerical value:

Student Features → Model → final_score
🏷️ Classification
Classification predicts a class/category.

The target used in this project is:

completion_status
The classification models compare whether a student is likely to complete the course.

Classification Metrics
Accuracy
Accuracy tells us how many predictions were correct overall.

Accuracy = Correct Predictions / Total Predictions
Example:

If 100 predictions are made and 74 are correct:

Accuracy = 74 / 100 = 74%
Precision
Precision answers:

Of the students predicted as a particular class, how many were actually that class?

Recall
Recall answers:

Of all actual students belonging to a class, how many did the model correctly identify?

F1 Score
F1 Score combines Precision and Recall.

F1 = 2 × (Precision × Recall) / (Precision + Recall)
ROC-AUC
ROC-AUC measures how well a classification model separates classes across different decision thresholds.

Higher AUC generally indicates better class separation.

📉 Regression
Regression predicts a numerical value.

The target used in this project is:

final_score
The model estimates a student's final score.

Regression Metrics
MAE --- Mean Absolute Error
MAE measures the average absolute difference between actual and predicted values.

Lower MAE is better.

RMSE --- Root Mean Squared Error
RMSE gives more weight to larger errors.

Lower RMSE is better.

R² Score
R² indicates how much variation in the target is explained by the model.

Higher R² is better.

For this project, the best reported regression R² is:

0.4855
🧹 Data Preprocessing
Data preprocessing prepares raw data before machine learning.

Step 1 --- Date Conversion
course_start_date is converted to datetime.

Step 2 --- Date Feature Extraction
The project extracts:

start_year
start_month
start_day
This makes date information easier for machine learning models to use.

Step 3 --- Remove ID
student_id is removed because it is an identifier rather than a useful predictive feature.

Step 4 --- Missing Values
Missing numerical values are handled using median imputation.

Categorical missing values are also handled.

Step 5 --- Categorical Encoding
Categorical variables are converted into numerical representation using:

<img width="849" height="575" alt="Screenshot 2026-09-10 024545" src="https://github.com/user-attachments/assets/2e796e54-f14d-424a-b629-3b1511cccf23" />


OneHotEncoder
pandas dummy encoding
Step 6 --- Feature Scaling
StandardScaler is used in preprocessing pipelines where required.

After preprocessing, the classification and regression data contain:

4,160 rows × 30 processed features
🌳 Decision Tree
A Decision Tree makes predictions by asking a sequence of questions about the features.

Simple example:

Attendance > 75?
       |
   Yes | No
       |
   Continue
Advantages
Easy to understand
Handles nonlinear relationships
Useful as a base learner for ensemble methods
Disadvantage
A single deep tree can overfit the training data.

🧩 Ensemble Learning
Ensemble Learning combines multiple models instead of depending on only one model.

The basic idea is:

Multiple Models
      ↓
Combine Predictions
      ↓
Better / More Robust Prediction
This project compares several ensemble techniques.

<img width="1194" height="595" alt="Screenshot 2026-09-10 024908" src="https://github.com/user-attachments/assets/9aa112bd-123a-4a06-a8a1-8b7dd01041cf" />


👜 Bagging
Bagging = Bootstrap Aggregating

Bagging trains multiple models on different bootstrap samples of the training data and combines their predictions.

Basic workflow:

Original Data
     ↓
Bootstrap Samples
 ↓    ↓    ↓
Model Model Model
 ↓    ↓    ↓
Combine Predictions
     ↓
Final Prediction
Bagging mainly helps reduce variance and can make unstable learners more robust.

Reported final Bagging accuracy:

70.19%

🚀 Boosting
Boosting builds models sequentially.

Each new model focuses more on errors or difficult observations from previous models.

General idea:

Model 1
   ↓
Find Errors
   ↓
Model 2 focuses on errors
   ↓
Model 3 improves further
   ↓
Final Combined Model
The project uses:

<img width="1196" height="597" alt="Screenshot 2026-09-10 024627" src="https://github.com/user-attachments/assets/115b2f93-061c-4151-8330-f2a0b1b972ac" />


AdaBoost
Gradient Boosting
LightGBM
XGBoost
⚡ AdaBoost
AdaBoost means Adaptive Boosting.

It combines several weak learners into a stronger model.

Concept:

Weak Learner 1
      ↓
Give more attention to mistakes
      ↓
Weak Learner 2
      ↓
Continue improving
      ↓
Final Ensemble
Reported classification accuracy:

72.88%

<img width="1073" height="594" alt="Screenshot 2026-09-10 024703" src="https://github.com/user-attachments/assets/02c8cad7-ae62-4b12-9d62-c7baae7d91c1" />


📈 Gradient Boosting
Gradient Boosting builds decision trees sequentially.

Each new tree tries to improve the errors made by the previous ensemble.

Concept:

Initial Prediction
       ↓
Calculate Error
       ↓
Build Tree to Reduce Error
       ↓
Add Tree
       ↓
Repeat
       ↓
Final Prediction
Project result
Gradient Boosting is the best-performing model in the reported classification and regression comparisons.

Classification:

Accuracy: 73.65%
Precision: 73.17%
Recall: 73.65%
F1 Score: 73.22%
ROC-AUC: 78.77%
Regression:

MAE: 7.8476
RMSE: 9.8049
R²: 0.4855

<img width="1026" height="571" alt="Screenshot 2026-09-10 024505" src="https://github.com/user-attachments/assets/0350e88f-673c-49a2-906c-3d036587470d" />

💡 LightGBM
LightGBM is a gradient boosting framework designed for efficient tree-based learning.

It is included in this project as a boosting model for both classification and regression.

Reported classification accuracy:

71.44%

❌ XGBoost
XGBoost is another optimized gradient boosting implementation.

It builds trees sequentially and combines them into a strong predictive model.

Reported classification accuracy:

72.31%

Reported regression:

MAE: 8.0076
RMSE: 9.9706
R²: 0.4679
🤝 Voting Ensemble
Voting combines predictions from multiple different models.

Hard Voting
Hard Voting uses the predicted class from each model and selects the class receiving the most votes.

Example:

Model A → Complete
Model B → Complete
Model C → Not Complete

Final → Complete
Reported Hard Voting accuracy:

73.46%

Soft Voting
Soft Voting combines predicted probabilities and selects the class with the highest combined probability.

Reported Soft Voting accuracy:

71.54%

Result
For this experiment:

Hard Voting performed better than Soft Voting.

<img width="697" height="556" alt="Screenshot 2026-09-10 024414" src="https://github.com/user-attachments/assets/095d0dff-1362-4751-94f8-cfd61628090f" />


🧠 Stacking
Stacking combines multiple base models and uses another model, called a meta-model, to learn how to combine their predictions.

Concept:

             ┌─ Model 1 ─┐
Input Data ──┼─ Model 2 ─┼──→ Meta Model → Final Prediction
             └─ Model 3 ─┘
Reported Stacking accuracy:

73.56%

Stacking was slightly better than Voting:

Voting   = 73.46%
Stacking = 73.56%
Difference:

0.10 percentage points

<img width="838" height="476" alt="Screenshot 2026-09-10 024740 - Copy" src="https://github.com/user-attachments/assets/245b9e54-4137-40ee-bba1-44f1f0d86594" />
<img width="838" height="476" alt="Screenshot 2026-09-10 024740" src="https://github.com/user-attachments/assets/2668b359-cc11-4b10-a93f-570621cb0af5" />



📊 Classification Results
Model Accuracy Precision Recall F1 Score ROC-AUC

AdaBoost 72.88% 72.32% 72.88% 72.31% 78.43%

Gradient 73.65% 73.17% 73.65% 73.22% 78.77% Boosting

LightGBM 71.44% 70.87% 71.44% 70.96% 76.54%

XGBoost 72.31% 71.83% 72.31% 71.93% 77.04%
🏆 Best Classification Model
Gradient Boosting

Accuracy = 73.65%
F1 Score = 73.22%
ROC-AUC = 78.77%
📉 Regression Results
Model MAE RMSE R² Score

AdaBoost 8.8351 10.8691 0.3677 Gradient Boosting 7.8476 9.8049 0.4855 LightGBM 8.0329 10.0052 0.4642 XGBoost 8.0076 9.9706 0.4679

🏆 Best Regression Model
Gradient Boosting

R² = 0.4855
MAE = 7.8476
RMSE = 9.8049
⚖️ Bagging vs Boosting
Model Accuracy

Bagging 70.19% AdaBoost 72.88% Gradient Boosting 73.65% LightGBM 71.44% XGBoost 72.31%

Observation
Gradient Boosting achieved the highest accuracy among the models in this final comparison.

🌲 Tree-Based Boosting Comparison
Model Accuracy

AdaBoost 72.88% Gradient Boosting 73.65% LightGBM 71.44% XGBoost 72.31%

🗳️ Hard Voting vs Soft Voting
Voting Method Accuracy

Hard Voting 73.46% Soft Voting 71.54%

Hard Voting performed better in this experiment.

🧠 Voting vs Stacking
Ensemble Technique Accuracy

Voting 73.46% Stacking 73.56%

Stacking produced a slightly higher accuracy than Voting.

🎞️ Project Results --- Animated Charts
The project charts are combined into one GIF for a clean GitHub README presentation.

Ensemble Model Charts

📊 Individual Charts
1. Boosting Models Comparison
Boosting Models Comparison

2. Hard Voting vs Soft Voting
Hard Voting vs Soft Voting

3. Classification Models Comparison
Classification Models Comparison

4. Regression Models Comparison
Regression Models Comparison

5. Bagging vs Boosting Models
Bagging vs Boosting

6. Tree-Based Boosting Comparison
Tree-Based Boosting

7. Voting vs Stacking
Voting vs Stacking

8. Final Ensemble Model Comparison
Final Ensemble Model Comparison

🔄 Complete Project Workflow
Dataset
   ↓
Data Inspection
   ↓
Data Cleaning
   ↓
Date Feature Extraction
   ↓
Missing Value Handling
   ↓
Categorical Encoding
   ↓
Feature Scaling
   ↓
Train/Test Split
   ↓
Decision Tree
   ↓
Bagging
   ↓
AdaBoost
   ↓
Gradient Boosting
   ↓
LightGBM
   ↓
XGBoost
   ↓
Voting
   ↓
Stacking
   ↓
Classification / Regression Evaluation
   ↓
Model Comparison
   ↓
Best Model Selection
🧪 Model Evaluation Strategy
Classification
The classification models are compared using:

Accuracy
Precision
Recall
F1 Score
ROC-AUC
Regression
The regression models are compared using:

MAE
RMSE
R² Score
The best model is selected according to the reported evaluation results.

<img width="1000" height="620" alt="image" src="https://github.com/user-attachments/assets/91994512-fd60-4574-8bd1-49d5f10bd090" />


💼 Business Interpretation
The Smart Outcome Predictor can help identify students who may need additional academic support.

Possible applications:

Early identification of students at risk of non-completion
Monitoring student engagement
Supporting academic intervention decisions
Estimating expected final scores
Comparing learning behaviour and outcomes
Important Note
Model predictions should support human decision-making rather than replace academic judgment.

🛠️ Technologies Used
Python
Jupyter Notebook
Pandas
NumPy
Matplotlib
Scikit-learn
LightGBM
XGBoost
📦 Important Python Libraries
Typical libraries used by this project include:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler, OneHotEncoder
from sklearn.impute import SimpleImputer

from sklearn.tree import DecisionTreeClassifier, DecisionTreeRegressor
from sklearn.ensemble import (
    BaggingClassifier,
    BaggingRegressor,
    AdaBoostClassifier,
    AdaBoostRegressor,
    GradientBoostingClassifier,
    GradientBoostingRegressor,
    VotingClassifier,
    StackingClassifier,
    StackingRegressor
)

from sklearn.metrics import (
    accuracy_score,
    precision_score,
    recall_score,
    f1_score,
    roc_auc_score,
    mean_absolute_error,
    mean_squared_error,
    r2_score
)
LightGBM and XGBoost are also used in the notebook.

📁 Recommended Repository Structure
Smart-Outcome-Predictor/
│
├── README.md
├── Smart_Outcome_Predictor.ipynb
├── Smart_Outcome_Predictor_Dataset_5200.csv.csv
│
└── assets/
    ├── charts/
    │   ├── boosting_models_comparison.png
    │   ├── hard_vs_soft_voting.png
    │   ├── classification_models_comparison.png
    │   ├── regression_models_comparison.png
    │   ├── bagging_vs_boosting.png
    │   ├── tree_based_boosting_comparison.png
    │   ├── voting_vs_stacking.png
    │   └── final_ensemble_model_comparison.png
    │
    └── gifs/
        └── ensemble_models_charts.gif
▶️ How to Run
1. Clone the Repository
git clone <your-repository-url>
cd Smart-Outcome-Predictor
2. Install Libraries
pip install pandas numpy matplotlib scikit-learn lightgbm xgboost jupyter
3. Open Jupyter Notebook
jupyter notebook Smart_Outcome_Predictor.ipynb
4. Run the Notebook
Run the notebook cells from top to bottom.

🎓 Simple Concept Summary
Concept Simple Meaning

Machine Learning Computer learns patterns from data Supervised Learning Model learns using known target values Classification Predicts a category Regression Predicts a number Decision Tree Makes predictions using question-like splits Ensemble Combines multiple models Bagging Trains models on different samples and combines them Boosting Builds models sequentially to improve errors AdaBoost Gives more attention to previous mistakes Gradient Boosting Sequentially reduces prediction errors LightGBM Efficient gradient boosting framework XGBoost Optimized gradient boosting implementation Voting Combines predictions by voting Hard Voting Uses predicted classes Soft Voting Uses predicted probabilities Stacking Uses a meta-model to combine model predictions Accuracy Overall percentage of correct predictions Precision Correctness of positive/class predictions Recall Ability to find actual class members F1 Balance between precision and recall ROC-AUC Measures class-separation ability MAE Average absolute prediction error RMSE Error metric that penalizes larger errors more R² Proportion of target variation explained by model OneHotEncoder Converts categories into numerical columns Median Imputation Replaces missing numerical values with median StandardScaler Standardizes numerical features Train/Test Split Separates training data from testing data

🏆 Final Results
For the current dataset and notebook configuration:

Classification
Gradient Boosting is the best reported classification model.

Accuracy  = 73.65%
F1 Score  = 73.22%
ROC-AUC   = 78.77%
Regression
Gradient Boosting is also the best reported regression model.

MAE  = 7.8476
RMSE = 9.8049
R²   = 0.4855
Ensemble Comparison
Bagging    = 70.19%
AdaBoost   = 72.88%
Gradient   = 73.65%
LightGBM   = 71.44%
XGBoost    = 72.31%
Voting Comparison
Hard Voting = 73.46%
Soft Voting = 71.54%
Voting vs Stacking
Voting   = 73.46%
Stacking = 73.56%
⭐ Final Recommendation
Based on the reported evaluation results, Gradient Boosting is the recommended model for this project.

It achieved the highest reported classification accuracy and the strongest reported regression performance among the compared models.
