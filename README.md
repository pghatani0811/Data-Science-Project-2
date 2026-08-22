# Predicting Insurance claim cost
## Project Overview
This project uses machine learning to predict insurance claim costs using the Allstate Claims Severity dataset from Kaggle. The dataset contains 188,318 claims.

The goal is to help insurance managers identify high-cost claims early and improve reserve planning.

To predict claim costs, I tested three models: Linear Regression, Random Forest, and Gradient Boosting. After tuning, Gradient Boosting performed the best, with an RMSE of $1,884.82.

The final recommendation is to use the model to rank claims by predicted cost and send the top 5% to experienced adjusters for early review. The 5% should be tested before the model is fully used.


The project follows a simple data science process:

- Project topic finalized
- Dataset downloaded and verified
- Data cleaning
- Exploratory Data Analysis (EDA)
- Analysis plan
- Linear Regression model
- Model comparison (Random Forest and Gradient Boosting)
- Model tuning
- Final model evaluation 
- Visualization and dashboard 
- Final report and presentation

## Business Problem

Insurance companies need to estimate claim costs accurately to set proper reserves and manage their money. However, claim costs can vary greatly, and a small number of claims can become very expensive.

In this dataset, 83.59% of claims are below $5,000, while only 23 out of 188,318 claims are above $40,000. These rare high-cost claims can create greater financial risk.

The main business problem is to identify high-cost claims as early as possible. Machine learning can help predict and rank claim costs so claims managers can review expensive claims earlier, prioritize their work, and improve reserve planning.

## Dataset Summary

The project uses the Allstate Claims Severity dataset from Kaggle.

| Metric                   |                    Value |
| ------------------------ | -----------------------: |
| **Dataset**              | Allstate Claims Severity |
| **Total Claims**         |                  188,318 |
| **Total Columns**        |                      132 |
| **Categorical Features** |                      116 |
| **Numerical Features**   |                       14 |
| **Target Variable**      |      `loss` (claim cost) |
| **Duplicate Rows**       |                        0 |
| **Missing Values**       |                        0 |
| **Claims Below $5,000**  |                   83.59% |
| **Claims Above $40,000** |                       23 |


## Research Questions

- How can machine learning predict and identify high-cost insurance claims early to support better claim review and reserve planning?
- Which model is best—Linear Regression, Random Forest, or Gradient Boosting—best predicts insurance claim costs?
- Can the model effectively rank potentially high-cost claims for early review?
- How can claim-cost predictions help insurance managers prioritize claims and improve reserve planning?

These questions align well with your project’s goal of predicting claim costs, comparing regression models, and using the results as a decision-support tool.

## The Primary Objectives of This Project Are:
- Predict insurance claim costs using machine learning.
- Compare Linear Regression, Random Forest, and Gradient Boosting to find the best model for this project.
- Identify and rank potentially high-cost claims for early review.
- Enable claims managers to handle claims and distribute resources in the best possible way.
- Support better reserve planning using predicted claim costs.
- This project aims to develop a decision-support tool.

## Repository Structure
```text
Allstate_Claims_Severity_Portfolio/
├── data/
│   └── train.csv
├── notebooks/
│   └── Allstate_Claims_Complete_Project.ipynb
├── analysis/
│   ├── Data_Cleaning
│   ├── Exploratory_Data_Analysis
│   └── Analysis_Plan
├── models/
│   ├── Linear_Regression
│   ├── Random_Forest
│   ├── Gradient_Boosting
│   └── Model_Tuning
├── outputs/
│   ├── Final_Model_Evaluation
│   └── Visualization_Dashboard
├── reports/
│   └── Final_Project_Report.pdf
├── presentation/
│   └── Final_Presentation.pptx
├── README.md
├── requirements.txt
└── .gitignore
```

## Methodology

# Method I: Data Access and Understanding
The project follows a machine learning regression approach to predict insurance claim costs.

| Activities                                  | Deliverables                                       |
| ------------------------------------------- | -------------------------------------------------- |
| **Access Allstate Claims Severity Dataset** | Kaggle training dataset                            |
| **Load Data into Python**                   | Dataset successfully loaded                        |
| **Understand Dataset Structure**            | 188,318 claims and 132 columns                     |
| **Identify Features**                       | 116 categorical and 14 numerical features          |
| **Identify Target Variable**                | `loss` — insurance claim cost                      |
| **Check Data Quality**                      | No missing values or duplicate rows found          |
| **Assess Data Suitability**                 | Dataset confirmed suitable for regression analysis |


These items match the dataset-access and initial-inspection steps documented in your project.


## Method II: Exploratory Data Analysis (EDA)

The EDA was used to understand claim-cost patterns and identify high-cost claims. The results show that most claims are low-cost, while very expensive claims are rare.

- Activities	Deliverables
- Analyze Claim Cost Distribution	Understand claim-cost patterns
- Group Claims by Cost Range	Compare low- and high-cost claims
- Identify High-Cost Claims	Find rare expensive claims
- Analyze Claims Below $5,000	157,412 claims (83.59%)
- Analyze Claims Above $40,000	Only 23 claims
- Create EDA Visualization	Claims-by-cost-range chart
- Develop Business Insight	Prioritize high-cost claims for early review
- EDA Chart: Claims by Cost Range
- Claims by cost range


<img width="1980" height="978" alt="image" src="https://github.com/user-attachments/assets/83d11b73-dfca-4c02-b291-fa673bc329b8" />


# Method III: Prepare Data

The data was prepared for machine learning by separating the target variable (loss) from the input features and preparing the categorical and numerical variables for modeling. The project contains 116 categorical and 14 numerical features.

- Activities	Deliverables
- Select Target Variable	loss — claim cost
- Separate Input Features	Predictor variables prepared
- Prepare Categorical Features	Categorical data prepared for modeling
- Prepare Numerical Features	Numerical data prepared for modeling
- Split the Dataset	Training and testing data
- Prepare Modeling Data	Final dataset ready for regression models

# Models Evaluated:

Three regression models were evaluated to predict insurance claim costs.

| Model                       |          RMSE |         R² | Result               |
| --------------------------- | ------------: | ---------: | -------------------- |
| **Linear Regression**       |     $2,016.61 |     0.5016 | Baseline Model       |
| **Random Forest**           |     $1,903.31 |     0.5560 | Best Before Tuning   |
| **Gradient Boosting**       |     $1,945.67 |     0.5361 | Selected for Tuning  |
| **Tuned Gradient Boosting** | **$1,884.82** | **0.5646** | **Best Final Model** |


Final Model: After tuning, Gradient Boosting performed best, with an RMSE of $1,884.82, MAE of $1,218.61, and R² of 0.5646.

# Method IV: Model Evaluation and Visualization

Three regression models were tested to determine which model could best predict insurance claim costs: Linear Regression, Random Forest, and Gradient Boosting.

- Activities	Deliverables
- Build Linear Regression	Baseline regression model
- Build Random Forest	Random Forest regression model
- Build Gradient Boosting	Gradient Boosting regression model
- Evaluate Models	RMSE and R² results
- Compare Models	Compare prediction performance
- Select Model for Tuning	Gradient Boosting selected for tuning

Model Comparison Chart

Model comparison — lower RMSE is better

  <img width="1780" height="980" alt="image" src="https://github.com/user-attachments/assets/a9b191ea-a594-4fa7-a268-8fd0a00a99f2" />

 
| Model                 |          RMSE |         R² |
| --------------------- | ------------: | ---------: |
| **Linear Regression** |     $2,016.61 |     0.5016 |
| **Random Forest**     | **$1,903.31** | **0.5560** |
| **Gradient Boosting** |     $1,945.67 |     0.5361 |


Key Finding: Random Forest performed best initially with the lowest RMSE of $1,903.31. Gradient Boosting was then tuned to improve its performance.

After Tuning the Gradient Boosting Model

After hyperparameter tuning, Gradient Boosting became the best-performing model.

| Metric   |  Final Result |
| -------- | ------------: |
| **RMSE** | **$1,884.82** |
| **MAE**  | **$1,218.61** |
| **R²**   |    **0.5646** |
Key Finding: The tuned Gradient Boosting model achieved the lowest RMSE ($1,884.82) among the models tested, making it the final selected model


# Method V: Business Recommendations

The final recommendation is to use the tuned Gradient Boosting model as a decision-support tool to identify and prioritize potentially high-cost claims.
| Activities                        | Deliverables                                                    |
| --------------------------------- | --------------------------------------------------------------- |
| **Rank Claims by Predicted Cost** | Identify potentially high-cost claims                           |
| **Select Top 5% of Claims**       | Initial pilot group for review                                  |
| **Early Claim Review**            | Send top 5% to experienced adjusters                            |
| **Support Reserve Planning**      | Help managers make better reserve decisions                     |
| **Validate the 5% Threshold**     | Test how many $40,000+ claims are captured                      |
| **Support Professional Judgment** | Use the model for prioritization, not automatic reserve setting |


Final Recommendation: Insurance executives should test the Gradient Boosting model and send the top 5% of scored claims to experienced adjusters for early review before setting reserves. The 5% is a starting point and should be validated before full use


## How to Run
1. Download or clone the project repository.
2. Install the required Python packages:
```bash
pip install -r requirements.txt
```

3. Open the notebook:
```bash
jupyter notebook notebooks/Allstate_Claims_Complete_Project.ipynb
```
4. Run all notebook cells in order.

The notebook performs data cleaning, EDA, preprocessing, model development, model tuning, evaluation, and visualization. This project uses Python libraries including pandas, NumPy, Matplotlib, and scikit-learn.
