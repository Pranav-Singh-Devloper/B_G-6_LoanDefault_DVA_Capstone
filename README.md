📊 Loan Default Risk Analytics
Predicting Loan Default Risk: A Data-Driven Credit Risk Analysis Framework

Sector: Banking / Financial Risk Analytics
Institute: Newton School of Technology, Rishihood University
Dataset Size: 10,000 Loans
Tool Used: Google Sheets

📌 Project Overview

Financial institutions face significant losses due to loan defaults. Traditional evaluation methods rely heavily on static indicators such as credit score and income, often missing deeper risk interactions between leverage (LTV), affordability stress (DTI), and loan categories.

This project builds a structured KPI-driven dashboard to:

Identify high-risk borrower segments

Quantify financial exposure due to defaults

Segment risk using LTV & DTI thresholds

Provide a centralized “Risk Control Tower” dashboard

🎯 Core Objective

Which borrower financial characteristics most significantly influence loan default risk, and how can lenders reduce exposure using data-driven segmentation?

📂 Dataset Analysis Source

Dataset sourced from Kaggle:

Loan Default Dataset
https://www.kaggle.com/datasets/yasserh/loan-default-dataset

Full project report reference: 

135bbde0-6343-40c9-964e-03dc88b…

📖 SECTION A: DATA DICTIONARY
Original Column	New Column Name	Data Type	Description	Used in Analysis?	Notes
ID	id	Numeric (ID)	Unique loan identifier	No	Primary key; no analytical value
year	year	Numeric	Year of issuance	No	Only 2019; no variation
loan_limit	loan_limit	Categorical	Regulatory loan classification	No	No meaningful separation
Gender	gender	Categorical	Applicant gender	No	Excluded to avoid bias
approve_in_adv	approved_in_advance	Categorical	Pre-approved flag	No	No significant structural effect
loan_type	loan_type	Categorical	Loan product type	Yes	Variation tested
loan_purpose	loan_purpose	Categorical	Loan purpose	No	Not structurally significant
Credit_Worthiness	credit_worthiness	Categorical	Internal classification	No	Weak separation
open_credit	open_credit	Categorical	Existing credit accounts	No	No strong pattern
business_or_commercial	loan_category	Categorical	Business vs Personal	Yes	Business risk higher
loan_amount	loan_amount	Numeric	Sanctioned amount	Yes (Secondary)	Weaker than LTV
rate_of_interest	rate_of_interest	Numeric	Interest rate (%)	Yes (Primary)	Activation band 3.5–4.0%
Interest_rate_spread	interest_rate_spread	Numeric	Spread over benchmark	No	Not analyzed separately
Upfront_charges	upfront_charges	Numeric	Initial fees	No	No direct test
term	loan_term	Numeric	Loan tenure	Tested	82% = 360 months
Neg_ammortization	negative_amortization	Categorical	Negative amortization flag	No	Low variation
interest_only	interest_only	Categorical	Interest-only flag	No	Not analyzed
lump_sum_payment	lump_sum_payment	Categorical	Lump sum clause	No	Not analyzed
property_value	property_value	Numeric	Property valuation	Indirect	Used in LTV
construction_type	construction_type	Categorical	Construction category	No	Not significant
occupancy_type	occupancy_type	Categorical	Occupancy class	No	Not analyzed
Secured_by	secured_by	Categorical	Collateral type	No	Not primary driver
total_units	total_units	Numeric	Number of units	No	Minimal variation
income	annual_income	Numeric	Annual income	Yes	Weak structural effect
credit_type	credit_type	Categorical	Credit agency type	No	Not significant
Credit_Score	credit_score	Numeric	Borrower credit score	Tested	Weak predictor
co-applicant_credit_type	co_applicant_credit_type	Categorical	Co-applicant source	No	Not significant
age	age	Categorical	Age group	No	Not analyzed
submission_of_application	submission_type	Categorical	Submission mode	No	No impact
LTV	loan_to_value_ratio	Numeric	Loan/Property ratio	Yes (Primary)	Strong severity amplifier
Region	region	Categorical	Geographic region	No	Not analyzed
Security_Type	security_type	Categorical	Security instrument	No	Not significant
Status	is_loan_default	Binary	Target variable	Yes	Overall default 24.88%
dtir1	debt_to_income_ratio	Numeric	Debt-to-income %	Yes (Secondary)	DTI ≥50 high risk
🧹 SECTION B: CLEANING & TRANSFORMATION LOG
Step	Column	Issue	Action Taken
1	loan_limit	Encoded values	Replaced with readable labels; blanks → Mode
2	approved_in_adv	Encoded values	Standardized; blanks → Mode
3	open_credit	Encoded values	Converted to Yes/No
4	loan_category	Encoded	Standardized Business/Personal
5	negative_amortization	Encoded	Converted to Yes/No
6	interest_only	Encoded	Converted to Yes/No
7	lump_sum_payment	Encoded	Converted to Yes/No
8	construction_type	Encoded	Replaced with readable categories
9	occupancy_type	Encoded	Standardized labels
10	submission_type	Encoded	Converted to Direct/Institution
11	total_units	Text values	Converted to numeric 1–4
12	loan_purpose_type	Missing	Mode imputation
13	loan_term	Missing	Mode (360 months)
14	amortization_type	Missing	Mode
15	age_group	Missing	Mode
16	upfront_fee	Skewed	Median imputation
17	property_value	Skewed	Median
18	interest_rate	Missing	Grouped Median
19	interest_rate_spread	Missing	Grouped Median
20	annual_income	Missing	Grouped Median
21	debt_to_income_ratio	Missing	Income-group based Median
📊 Key Insights & Statistics
📌 Portfolio Metrics

Total Loans: 10,000

Overall Default Rate: 24.88%

Median Interest Rate: 3.99%

Total Money Lost: 79,598,200

Avg Credit Score (Defaulted): 699.51

Avg Credit Score (Non-Defaulted): 702.03

🔎 Major Risk Findings
1️⃣ DTI is the Strongest Predictor

DTI 50–59% → 42.40% default rate

Represents borrower affordability breaking point

2️⃣ LTV Amplifies Severity

Default stable below 0.75

Sharp spike near 1.0 LTV

3️⃣ Business Loans Underperform

Business: 33.03%

Personal: 23.55%

4️⃣ Credit Score Weak Predictor

Only 2.52 point gap between defaulted vs non-defaulted

5️⃣ Portfolio Concentration Risk

Conventional Loans: 76.5%

Government: 14.1%

Special: 9.4%

📈 Dashboard Summary
🔝 KPI Cards

Total Loans

Default Rate

Median Interest Rate

Total Financial Loss

📊 Risk Drivers

Default by LTV Band (Line Chart)

Default by DTI Band (Bar Chart)

Loan Category Comparison

Loan Type Distribution (Donut)

📉 Drilldowns

LTV × Loan Type

DTI × Loan Type

Business vs Personal split

📷 Dataset Analysis Screenshots
Dashboard Overview

(Add exported dashboard image in repository as dashboard.png)

💡 Risk Segmentation Framework
Segment A — Critical Risk

DTI > 50%

LTV > 0.75

Segment B — Moderate Risk

DTI 30–49%

Medium LTV

Segment C — Low Risk

DTI < 30%

LTV < 0.5

💰 Financial Impact Estimation

Reducing high-DTI exposure by 30% could:

Reduce default exposure by 10–15%

Save approximately 8–12 million

⚠️ Limitations

Single-year dataset (2019)

No macroeconomic variables

No employment/industry variables

Correlation ≠ Causation

🚀 Future Scope

Logistic Regression Modeling

Probability of Default (PD) Framework

Machine Learning Credit Scoring

Early Warning Delinquency System

🏁 Conclusion

This project demonstrates:

Debt burden (DTI) is the strongest predictor

Leverage (LTV) amplifies risk

Portfolio concentration increases systemic exposure

Static credit score-based evaluation is insufficient

Moving toward dynamic segmentation-based underwriting can significantly reduce default losses and improve portfolio health.