🏦 Investment Banking Customer Churn Analysis Dashboard (Power BI)
🎯 Objective

The goal of this project is to analyze customer data from an investment bank to identify factors that influence customer churn.
Using Power BI, the dashboard visualizes customer behavior, demographics, and financial indicators to uncover patterns and help design better retention strategies.

🧮 Dataset Information

Dataset name: train_preprocessed.csv
Source: Kaggle (Bank Customer Churn Prediction Dataset)

Attribute	Description
CreditScore	Customer’s credit score
Age	Age of the customer
Tenure	Number of years with the bank
Balance	Account balance
NumOfProducts	Number of bank products held
HasCrCard	Credit card ownership (1 = Yes, 0 = No)
IsActiveMember	Whether the customer is active
EstimatedSalary	Annual estimated salary
Geography, Gender	Demographic information
Exited	Target variable (1 = churned, 0 = retained)
🧩 Steps Followed
Step 1 – Data Understanding and Collection

Dataset downloaded from Kaggle’s Bank Churn Prediction challenge.

Focused only on train_preprocessed.csv for analysis (contains both features and target).

Step 2 – Data Preparation in SPSS Statistics

Before loading into Power BI, the dataset was further transformed in IBM SPSS Statistics for analytical grouping.

✅ Variables Re-coded in SPSS:

AgeGroup – Created by recoding “Age” into categories (e.g.,

18–30 = Young,

31–50 = Middle-aged,

51+ = Senior)

BalanceBucket – Grouped “Balance” into ranges (e.g.,

Low Balance, Medium Balance, High Balance)

TenureGroup – Re-coded “Tenure” into segments (e.g.,

0–3 years = New,

4–7 years = Moderate,

8+ years = Loyal customers)

🧠 This grouping helped in identifying behavioral patterns more effectively in Power BI visuals.

Step 3 – Import and Clean Data in Power BI

Imported the train_preprocessed.csv file using Get Data → Text/CSV.

Verified data types (Age, Tenure, Balance, etc.) and renamed columns for clarity.

Ensured all recoded variables from SPSS (AgeGroup, BalanceBucket, TenureGroup) were recognized properly.

Step 4 – Create DAX Measures
Measure	Formula	Purpose
Total Customers	COUNTROWS('train_preprocessed')	Count of all customers
Churned Customers	CALCULATE(COUNTROWS('train_preprocessed'), 'train_preprocessed'[Exited] = 1)	Count of churned customers
Churn Rate	DIVIDE([Churned Customers], [Total Customers], 0)	Percentage of customers lost
Average Balance	AVERAGE('train_preprocessed'[Balance])	Avg customer balance
Average Credit Score	AVERAGE('train_preprocessed'[CreditScore])	Avg credit score
Average Tenure	AVERAGE('train_preprocessed'[Tenure])	Avg tenure duration
Step 5 – Build Power BI Dashboard Pages
📘 Page 1 – Overview

KPI Cards: Total Customers, Churned Customers, Churn Rate, Avg Balance

Pie Chart: Churned vs Retained

Column Chart: AgeGroup vs Churn

Line Chart: Tenure vs Churn Rate

📗 Page 2 – Demographic Insights

Bar Chart: Gender vs Churn

Bar Chart: Geography vs Churn

TreeMap: AgeGroup & Gender vs Churn

📙 Page 3 – Financial Behavior

Scatter Plot: Credit Score vs Estimated Salary (colored by churn)

Column Chart: NumOfProducts vs Churn

Histogram: BalanceBucket vs Churn

📒 Page 4 – Retention Analysis

Matrix: AgeGroup × TenureGroup × Churn Rate

Slicers: Gender, Geography, IsActiveMember

KPI Cards: High-risk segment churns

Step 6 – Dashboard Design

Adopted a dark theme to represent an investment-banking look.

Used Segoe UI Semibold fonts for readability.

Added interactive slicers and tooltips for better user exploration.

Step 7 – Key Insights

Highest churn observed among mid-age customers (30–40) with low tenure.

Inactive members and those with only one product churned more frequently.

High-balance customers also showed churn — indicating service dissatisfaction rather than financial issues.

France region had slightly higher churn rates compared to other geographies.

💡 Business Impact

This dashboard empowers the investment bank to:

Detect and monitor high-risk customer segments early.

Design targeted retention strategies for specific age, tenure, or balance groups.

Improve relationship management through data-driven decision-making.

🛠️ Tools Used

IBM SPSS Statistics – Data preprocessing and recoding

Power BI Desktop – Dashboard creation and data modeling

Kaggle – Dataset source

📁 Deliverables

Investment_Banking_Customer_Churn.pbix (Power BI file)

train_preprocessed.csv (dataset)

README.md documentation
