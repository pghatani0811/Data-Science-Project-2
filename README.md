# Predicting Insurance claim cost

## Project Overview

This project uses machine learning to predict how much insurance claims may cost using the Kaggle Allstate Claims Severity dataset. The goal is to help claims managers find expensive claims early, review important claims first, and make better decisions about reserves.

The dataset has 188,318 insurance claims, with 116 categorical features and 14 numerical features. The target, called loss, is the dollar cost of each claim. Because the project predicts a dollar amount, I used regression models.

The data showed that most claims are low-cost. About 83.59% of claims are below $5,000, and only 23 claims are above $40,000. This means very expensive claims are rare, but they can create higher financial risk.

I tested three models:

Linear Regression: RMSE = $2,016.61
Random Forest: RMSE = $1,903.31
Gradient Boosting: RMSE = $1,945.67

At first, Random Forest performed best. After tuning, Gradient Boosting became the best final model, with an RMSE of $1,884.82, MAE of $1,218.61, and R² of 0.5646.

My recommendation is to use the tuned Gradient Boosting model to rank claims by predicted cost. As a starting point, the top 5% of claims can be sent to experienced adjusters for early review.

In the test data, the top 5% captured all 6 claims above $40,000. However, there were only six very expensive claims, so this result needs to be tested with more data before full use.

The model should help claims managers make decisions, not replace them or automatically set claim reserves.

The project follows a simple data science process:

-   Project topic finalized
-   Dataset downloaded and verified
-   Data cleaning
-   Exploratory Data Analysis (EDA)
-   Analysis plan
-   Linear Regression model
-   Model comparison (Random Forest and Gradient Boosting)
-   Model tuning
-   Final model evaluation
-   Visualization and dashboard
-   Final report and presentation

## Business Problem

Insurance companies handle many claims, and some claims can become very expensive. It can be difficult to know early which claims will have high costs.

The goal of this project is to use machine learning to predict claim costs so claims managers can identify potentially expensive claims early, review them sooner, and make better decisions about reserve planning.

The model is designed to support claims managers, not replace their professional judgment.

## Dataset Summary

The project uses the Allstate Claims Severity dataset from Kaggle.

 | **Metric**               |                **Value** |
| ------------------------ | -----------------------: |
| **Dataset**              | Allstate Claims Severity |
| **Total Claims**         |                  188,318 |
| **Total Columns**        |                      132 |
| **Categorical Features** |                      116 |
| **Numerical Features**   |                       14 |
| **Target Variable**      |      `loss` (Claim Cost) |
| **Duplicate Rows**       |                        0 |
| **Missing Values**       |                        0 |
| **Claims Below $5,000**  |         157,412 (83.59%) |
| **Claims Above $40,000** |               23 (0.01%) |


## Research Questions

Main Research Question:
How can machine learning be used to predict insurance claim costs using historical insurance claim data?

Supporting Questions:

- Which regression model gives the best prediction results?
- Can the model help identify potentially high-cost claims early?
- Can the model help claims managers prioritize claims for review and support reserve planning?

## The Primary Objectives of This Project Are:

- Predict insurance claim costs using machine learning.
- Compare regression models to find the best-performing model.
- Identify potentially high-cost claims early.
- Rank claims by predicted cost for early review.
- Help claims managers prioritize resources and support better reserve planning.
- Use the model as a decision-support tool, not to replace claims professionals or automatically set reserves.

## Repository Structure

``` text
Data-Science-Project-2/
├── data/
│   └── train.csv
├── notebooks/
│   └── Allstate_Claims_Complete_Project.ipynb
├── outputs/
│   └── generated charts and model results
├── reports/
│   ├── Project_Proposal.pdf
│   ├── Defensible_Analysis.docx
│   └── LLM_Log_Final_Reflection.docx
├── presentation/
│   └── Final_Presentation.pptx
├── README.md
├── requirements.txt
└── .gitignore
```

## Methodology
# Method I: Data Access and Understanding
- Used the Kaggle Allstate Claims Severity dataset.
- The dataset contains 188,318 insurance claims and 132 columns.
- It includes 116 categorical features and 14 numerical features.
- The target variable is loss, which represents the dollar cost of each insurance claim.
- The data was loaded and analyzed in Python using tools such as pandas and scikit-learn.
- Initial inspection found no duplicate rows and no missing values.
- Since loss is a continuous dollar amount, regression models were selected for prediction.

## Method II: Exploratory Data Analysis (EDA)

The EDA was used to understand claim-cost patterns and identify
high-cost claims. The results show that most claims are low-cost, while
very expensive claims are rare.

-   Activities Deliverables
-   Analyze Claim Cost Distribution Understand claim-cost patterns
-   Group Claims by Cost Range Compare low- and high-cost claims
-   Identify High-Cost Claims Find rare expensive claims
-   Analyze Claims Below \$5,000 157,412 claims (83.59%)
-   Analyze Claims Above \$40,000 Only 23 claims
-   Create EDA Visualization Claims-by-cost-range chart
-   Develop Business Insight Prioritize high-cost claims for early
    review
-   EDA Chart: Claims by Cost Range
-   Claims by cost range

<img width="1982" height="978" alt="image" src="https://github.com/user-attachments/assets/8575f30c-9bda-44c9-9209-738ce5b4b4b0" />


# Method III: Prepare Data


- Removed duplicate rows and separated the target variable loss from the input features.
- Removed the id column from the prediction features.
- Split the data into 80% training and 20% testing sets.
- Prepared numerical and categorical features separately.
- Used One-Hot Encoding for Linear Regression and Ordinal Encoding for the tree-based models.
- Prepared the data for Linear Regression, Random Forest, and Gradient Boosting.
  Data Preparation Chart

## 🔄 Machine Learning Workflow

                    Allstate Claims Severity Dataset
                         188,318 Claims
                               │
                               ▼
                       Basic Data Cleaning
                   Remove Duplicates and ID
                               │
                               ▼
                     Separate Features (X)
                      and Target (`loss`)
                               │
                               ▼
                       Train / Test Split
                           80% / 20%
                               │
                  ┌────────────┴────────────┐
                  ▼                         ▼
          Numerical Features       Categorical Features
                  │                         │
                  ▼                         ▼
          Median Imputation       Most-Frequent Imputation
                  │                         │
                  └────────────┬────────────┘
                               ▼
                       Feature Encoding
                               │
                               ▼
                      Regression Models
                               │
              ┌────────────────┼────────────────┐
              ▼                ▼                ▼
       Linear Regression   Random Forest   Gradient Boosting
                               │
                               ▼
                    Model Evaluation & Tuning
                               │
                               ▼
                  Final Gradient Boosting Model
## Models Evaluated:

Three regression models were tested to predict insurance claim costs:

- Linear Regression — Used as the baseline model.
- Random Forest — Performed best in the initial comparison with an RMSE of $1,903.31.
- Gradient Boosting — After tuning, it became the best final model with an RMSE of $1,884.82, MAE of $1,218.61, and R² of 0.5646.
  <img width="1792" height="966" alt="image" src="https://github.com/user-attachments/assets/b4fab611-5179-4b71-bd00-76055a8114a7" />

  <img width="364" height="178" alt="image" src="https://github.com/user-attachments/assets/6109e4ef-1e4d-44e9-8466-639b93de023b" />





# Method IV: Model Evaluation and Visualization
# Evaluated the models using RMSE, MAE, and R².
- Compared Linear Regression, Random Forest, and Gradient Boosting.
- Random Forest performed best before tuning with an RMSE of $1,903.31.
- After tuning, Gradient Boosting performed best overall with:
- RMSE: $1,884.82
- MAE: $1,218.61
- R²: 0.5646
Used Actual vs. Predicted and model comparison charts to understand model performance.
The final model is used to rank potentially high-cost claims for early review, not to automatically set reserves.

Model RMSE comparison

Lower RMSE indicates better prediction performance.
<img width="874" height="230" alt="image" src="https://github.com/user-attachments/assets/c2af018a-fcfd-4f9a-9fc0-89347629ea2d" />


  



# Method V: Business Recommendations

Method V: Business Recommendations
- Use the tuned Gradient Boosting model to rank claims by predicted cost.
- Send the top 5% of ranked claims to experienced adjusters for early review.
- Use the model before reserves are finalized to help prioritize potentially expensive claims.
- Treat the top 5% as a starting point for testing, not a final proven threshold.
- Continue testing the model with additional or future data.
- Use the model to support claims managers, not replace their professional judgment or automatically set reserves

# Final Recommendation:

Insurance executives should test the tuned Gradient Boosting model and
send the top 5% of scored claims to experienced adjusters for early
review before setting reserves. In the held-out test set, the top 5%
captured all 6 claims above \$40,000. Because only 6 such claims were
present, the threshold should be validated on additional data before
full deployment.

# Method VI: Visualization Dashboard

The dashboard shows that most claims are low-cost, but a small number
are very expensive. The tuned Gradient Boosting model performed best
overall and can be used to rank potentially high-cost claims for early
review.

Business Value: The dashboard helps insurance managers quickly
understand claim patterns, compare model performance, and support claim
prioritization and reserve planning.
`<img width="1350" height="978" alt="image" src="https://github.com/user-attachments/assets/65ea07d7-eb94-4d7f-abef-f740f6ce648a" />`{=html}

## How to Run

1.  Download or clone the project repository.
2.  Install the required Python packages:

``` bash
pip install -r requirements.txt
```

3.  Open the notebook:

``` bash
jupyter notebook Allstate_Claims_Complete_Project_TOP5_READY.ipynb
```

4.  Run all notebook cells in order.

The notebook performs data cleaning, EDA, preprocessing, model
development, model tuning, evaluation, and visualization. This project
uses Python libraries including pandas, NumPy, Matplotlib, and
scikit-learn.

## Tools Used

  Tool / Technology      Purpose
  ---------------------- -------------------------------------------
  **Python**             Data analysis and machine learning
  **Pandas**             Data loading, cleaning, and preparation
  **NumPy**              Numerical calculations
  **Matplotlib**         Charts and visualizations
  **Scikit-learn**       Regression models, tuning, and evaluation
  **Jupyter Notebook**   Develop and run the analysis
  **Kaggle**             Allstate Claims Severity dataset

## Author

Prakash Ghatani Master in Data Science, Regis University
pghatani@regis.edu
