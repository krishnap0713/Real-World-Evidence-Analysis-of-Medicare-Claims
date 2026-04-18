# Real-World-Evidence-Analysis-of-Medicare-Claims
SQL &amp; Python-based analysis of Medicare claims data to identify cost drivers, utilization patterns, and patient financial burden.

This project analyzes Medicare inpatient and outpatient claims data to identify the major drivers of healthcare cost, utilization, and patient financial burden. The analysis combines advanced SQL for data extraction and transformation with Python, Pandas, and Matplotlib for further analysis and visualization.
The project focuses on how chronic disease burden, repeated outpatient care, high-cost inpatient episodes, and patient subgroups influence Medicare spending and out-of-pocket responsibility. The overall findings show that while some conditions drive very high utilization, a smaller set of severe chronic conditions drives a large share of total spending.
<img width="777" height="454" alt="image" src="https://github.com/user-attachments/assets/0de66897-0936-4c15-8378-51ce87d9e0b1" />


Dataset
Source: CMS Synthetic Medicare Claims Data (DE-SynPUF)

Tables used:
beneficiary_summary
inpatient_claims
outpatient_claims

These tables were used to study:
inpatient DRGs
outpatient HCPCS utilization
diagnosis-level spending
patient responsibility
chronic condition burden
demographic and geographic variation

Tools and Technologies
SQL (MySQL)
Python
Pandas
Matplotlib
SQLAlchemy

SQL Skills Demonstrated
This project uses a strong range of SQL functions and analytical logic to transform raw claims data into structured insight.
Core SQL:
GROUP BY,ORDER BY, HAVING, LIMIT
Aggregation Functions:
SUM()
AVG()
COUNT()
Conditional Logic:
CASE WHEN
Used to create:
length-of-stay buckets
chronic condition counts
grouped patient categories
cost/utilization segments
Joins
Used to combine:
beneficiary-level chronic condition flags
inpatient claims
outpatient claims
This made it possible to compare disease burden against cost, utilization, and patient responsibility across care settings.
CTEs (Common Table Expressions)
Used to break complex analysis into reusable and readable steps, especially for:
DRG-level summaries
provider ranking
chronic disease comparisons
payer cost breakdowns
Window Functions
Used for ranking and segmentation:
RANK()
DENSE_RANK()
ROW_NUMBER()
SUM() OVER()
AVG() OVER(PARTITION BY)
These helped identify:
highest-cost providers
top DRGs by payment
high-burden beneficiaries
top procedures by utilization or patient coinsurance
Data Cleaning / Handling Missing Values
COALESCE()
IS NOT NULL
conditional filters in WHERE
These were used to clean missing fields, exclude invalid values, and improve analytical reliability.
Python Skills Demonstrated
Python was used to connect SQL outputs to a reproducible analytics workflow.
Pandas
pd.read_sql() for pulling SQL results directly into Python
dataframe transformations and sorting
category creation and grouping
summary table creation for plotting and interpretation
Matplotlib
Built clear visualizations to communicate findings, including:
bar charts
scatter plots
dual-axis charts
stacked bar charts
pie charts
These visuals were used to show relationships between:
utilization and cost
inpatient stay and payment
chronic disease burden and spending
patient burden and payer contribution

Key Analyses Performed

1. Inpatient DRG Analysis
Identified DRGs with the highest patient out-of-pocket cost
Identified DRGs with the highest average Medicare payment per claim
Identified DRGs associated with longer average hospital stays
Insight: A small group of DRGs accounts for a disproportionate share of inpatient spending and patient burden, suggesting that certain hospital episodes are far more resource-intensive and financially burdensome than others.

2. Length of Stay vs Cost
Compared inpatient length of stay to:
average Medicare payment
claim frequency
average patient coinsurance
Insight: Longer hospital stays are less common but significantly more expensive. Patient coinsurance also rises sharply with longer stays, showing that prolonged admissions create a much greater out-of-pocket burden.

3. Outpatient HCPCS Utilization and Spending
Identified the most frequently used outpatient HCPCS services
Identified HCPCS procedures driving the highest total Medicare spending
Identified procedures with the highest patient coinsurance
Insight: Outpatient utilization is heavily concentrated in routine services such as lab work and office visits, while spending is driven by both very high-volume services and more expensive chronic-care procedures.

4. Outpatient Diagnosis-Level Analysis
Ranked the most common outpatient diagnoses
Ranked the most expensive outpatient diagnoses
Evaluated average outpatient cost breakdown across:
Medicare
primary payer
deductible
coinsurance
Insight: Chronic conditions such as hypertension and lipid disorders drive very high outpatient utilization, while kidney disease and dialysis-related diagnoses emerge as major cost drivers. Patient burden is driven mainly by coinsurance rather than deductible.

5. Chronic Disease Impact Analysis
The project specifically examined the spending and financial burden associated with major chronic conditions.
Heart Failure
Beneficiaries with heart failure showed substantially higher inpatient Medicare reimbursement and patient responsibility than those without heart failure.
Diabetes
Beneficiaries with diabetes had much higher inpatient and outpatient spending, and a higher outpatient-to-inpatient ratio than non-diabetic patients, suggesting heavier reliance on ongoing outpatient disease management.
Ischemic Heart Disease
Patients with ischemic heart disease incurred higher inpatient spending and greater patient responsibility, indicating more intensive and costly care needs.
Cancer
Cancer patients showed high spending across both inpatient and outpatient care, with inpatient spending remaining the larger cost driver. Their outpatient procedure patterns also reflected repeated office visits, lab work, and specialized oncology-related services.
Stroke / TIA
Stroke/TIA should be highlighted as an important high-burden chronic condition because it is closely associated with complex inpatient care, elevated reimbursement, and substantial patient burden. In a claims-based healthcare analysis, Stroke/TIA is valuable for understanding how serious cardiovascular and neurologic events affect hospitalization intensity, follow-up care, and spending concentration.
Chronic Kidney Disease
Chronic Kidney Disease is one of the most important conditions in this project because kidney disease and dialysis-related diagnoses emerged as major outpatient cost drivers. CKD reflects the strong financial impact of chronic disease management, repeated treatment utilization, and sustained payer burden over time.

Population-Level Insights
Gender
Average inpatient spending was similar across genders, but females showed somewhat higher outpatient and carrier reimbursement, suggesting slightly greater non-inpatient utilization.

State Variation
Average Medicare spending varied meaningfully across states, indicating regional differences in utilization, reimbursement patterns, or underlying population health burden.

Race and Chronic Burden
Both chronic disease burden and Medicare spending varied across racial groups, with a positive relationship between burden and spending. Differences between burden and spending may suggest disparities in access, care intensity, or utilization.

High-Cost Beneficiary Analysis
The project also identified the highest-cost beneficiaries and compared:
chronic condition count
Medicare reimbursement
patient responsibility
Insight: The highest-cost beneficiaries often had multiple chronic conditions and also carried substantial out-of-pocket burden, reinforcing that multimorbidity is a major driver of both payer spending and patient burden.

Provider-Level Analysis
Ranked providers with the highest outpatient Medicare payments
Compared providers by claim volume and payment impact
Insight: Some providers drive financial impact through very high claim volume, while others are high-cost because of more specialized and expensive care.

Real Project Takeaway
This project shows that Medicare spending is not driven by one single factor. It is driven by the combination of:
chronic disease burden
repeated outpatient utilization
expensive inpatient episodes
high-impact diagnoses and procedures
a smaller group of high-cost patients and providers
A major finding is that high-frequency conditions drive utilization, but severe chronic diseases such as Chronic Kidney Disease, cancer, diabetes, ischemic heart disease, heart failure, and Stroke/TIA drive a large share of cost and patient burden.
