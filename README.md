Loan Default Risk Analytics
Predicting Loan Default Risk: A Data-Driven Credit Risk Analysis Framework

Sector: Banking / Financial Risk Analytics
Institute: Newton School of Technology, Rishihood University
Dataset Size: 10,000 Loans
Tool Used: Google Sheets

Project Overview

Financial institutions face significant losses due to loan defaults. Traditional evaluation methods rely heavily on static indicators such as credit score and income, often failing to capture risk interactions between leverage (LTV), affordability stress (DTI), and loan categories.

This project builds a KPI-driven analytical dashboard to:

Identify high-risk borrower segments

Quantify financial exposure

Define structural LTV and DTI thresholds

Support data-driven credit decisioning

Objective

Which borrower financial characteristics most significantly influence loan default risk, and how can lenders reduce exposure using structured segmentation?

Dataset Source

Loan Default Dataset (Kaggle)
https://www.kaggle.com/datasets/yasserh/loan-default-dataset

Full project report reference: 

135bbde0-6343-40c9-964e-03dc88b…

SECTION A: DATA DICTIONARY
Original Column	New Column Name	Data Type	Description	Used in Analysis?	Notes
ID	id	Numeric	Unique loan identifier	No	Primary key
year	year	Numeric	Year of issuance	No	Only 2019
loan_type	loan_type	Categorical	Loan product type	Yes	Segment comparison
business_or_commercial	loan_category	Categorical	Business vs Personal	Yes	Business risk higher
loan_amount	loan_amount	Numeric	Sanctioned principal	Yes (Secondary)	Moderate impact
rate_of_interest	rate_of_interest	Numeric	Interest rate (%)	Yes (Primary)	Activation band identified
loan_term	loan_term	Numeric	Loan tenure	Tested	Majority at 360 months
annual_income	annual_income	Numeric	Borrower income	Tested	Weak structural effect
Credit_Score	credit_score	Numeric	Credit score	Tested	Weak predictor
LTV	loan_to_value_ratio	Numeric	Loan / Property value	Yes (Primary)	Strong severity driver
dtir1	debt_to_income_ratio	Numeric	Debt-to-income ratio	Yes (Secondary)	DTI ≥ 50 high risk
Status	is_loan_default	Binary	Target variable	Yes	Default rate 24.88%

(Non-analytical columns removed for brevity.)

SECTION B: DATA CLEANING SUMMARY
Category	Action Taken
Encoded Categorical Values	Replaced codes with readable labels (e.g., cf → Conforming, b/c → Business)
Binary Indicators	Standardized to Yes/No format
Text-Based Numerics	Converted to numeric format (e.g., total units 1U–4U → 1–4)
Missing Categorical Values	Filled using Mode
Skewed Numeric Features	Median imputation
Interest Rate & Income	Grouped median imputation
DTI	Income-based grouped median

All transformations were performed in Google Sheets using IF(), MODE(), MEDIAN(), and FILTER() logic.

Key Insights & Statistics

Portfolio Metrics:

Total Loans: 10,000

Overall Default Rate: 24.88%

Median Interest Rate: 3.99%

Total Money Lost: 79,598,200

Avg Credit Score (Defaulted): 699.51

Avg Credit Score (Non-Defaulted): 702.03

Risk Drivers

Debt-to-Income Ratio

DTI 50–59% → 42.40% default rate

Strongest predictor of default

Loan-to-Value Ratio

Stable below 0.75

Sharp increase near 1.0 LTV

Loan Category

Business: 33.03% default

Personal: 23.55%

Credit Score

Only 2.52-point difference

Weak standalone predictor

Portfolio Concentration

Conventional loans: 76.5%

Creates systemic exposure risk

Dashboard Summary

Top Section – KPI Cards

Total Loans

Default Rate

Median Interest Rate

Total Financial Loss

Middle Section – Risk Drivers

Default by LTV Band

Default by DTI Band

Loan Category Comparison

Loan Type Distribution

Bottom Section – Drilldowns

LTV by Loan Type

DTI by Loan Type

Business vs Personal Comparison

Dataset Analysis Screenshot

Add exported dashboard image to repository:

Risk Segmentation Framework

Critical Risk

DTI > 50%

LTV > 0.75

Moderate Risk

DTI 30–49%

Medium LTV

Low Risk

DTI < 30%

LTV < 0.5

Impact Estimation

Reducing high-DTI exposure by 30% could:

Reduce default exposure by 10–15%

Save approximately 8–12 million

Limitations

Single-year dataset

No macroeconomic variables

No employment variables

Correlation does not imply causation

Future Scope

Logistic Regression

Probability of Default framework

Machine Learning scoring

Early warning system

Conclusion

Debt burden (DTI) is the strongest predictor of default.
Leverage (LTV) amplifies risk severity.
Business loans carry structural risk.
Credit score alone is insufficient for accurate risk assessment.

A segmentation-based underwriting approach can significantly improve portfolio health and reduce financial loss.