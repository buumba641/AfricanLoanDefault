# Analysis Summary

## Key Findings and Summary

Based on the analysis:

### Data Analysis Insights
- The loan dataset is heavily skewed towards Kenya and repeat borrowers, primarily focusing on Type_1 loans.
- Significant class imbalance exists across loan types and between new and repeat borrowers.
- Numerical features (loan amounts, duration) are positively skewed, indicating a prevalence of smaller, short-term loans.
- Loan types show varying default rates; while dominant types like Type_1 have lower default rates, some less frequent types pose higher risks.
- Loan amounts and duration show positive correlations with default likelihood.
- Engineered features (`repayment_period`, `disbursement_month`, `disbursement_day_of_week`, `funding_ratio`, `interest_amount`) were created to capture temporal patterns and loan characteristics.
- The Random Forest model achieved high overall accuracy (approx. 99.38%) and excellent discriminatory power (ROC AUC approx. 0.9951).
- The model shows good precision (approx. 89.55%) in identifying defaults but could improve recall (approx. 73.77%) to capture more actual default cases.
- Economic analysis indicates Kenya faces increasing inflation and currency depreciation, and rising lending rates, while Ghana experiences higher and more volatile inflation and significant currency depreciation.
- Cote d'Ivoire, based on initial data, appears to have a more favorable economic environment (low inflation, strong growth).

---

## Categorical Feature Distributions

Insights into the distribution of categorical variables:

- **`loan_type`**: 'Type_1' is overwhelmingly the most frequent, followed by 'Type_7', 'Type_5', and 'Type_4'. Remaining types have significantly fewer observations, indicating class imbalance. This impacts modeling and may require stratified analysis.
- **`New_versus_Repeat`**: The vast majority are 'Repeat Loan', showing severe class imbalance and a focus on repeat borrowers.

---

## Numerical Feature Distributions

Summary of numerical data distributions:

- **`Total_Amount`, `Total_Amount_to_Repay`, `Amount_Funded_By_Lender`, `Lender_portion_Funded`, and `Lender_portion_to_be_repaid`**: All show highly skewed distributions, with most loans being small and a long tail towards larger amounts, typical for financial lending data.
- **`duration`**: Most loans are short-term, peaking at around 7 days, with fewer long-duration loans.
- **`Year`**: Most disbursements occurred in 2022, fewer in 2021 and 2024.
- **Engineered Features**: 'repayment_period' closely matches 'duration'. 'disbursement_month' and 'disbursement_day_of_week' show loans' temporal spread. 'funding_ratio' and 'interest_amount' provide insights into loan funding and charged interest.

---

## Categorical Feature Visualizations

Bar plots demonstrate the categorical distributions:

- **`country_id`**: Only Kenya is present.
- **`loan_type`**: Type_1 dominates, with a steep drop-off for other types.
- **`New_versus_Repeat`**: 'Repeat Loan' is the clear majority.

These visuals highlight imbalances and dominant categories for deeper analysis.

---

## Default Rate by Loan Type Analysis

Pie chart analysis of loan type default rates:

- Types like Type_15, Type_23, Type_14, and Type_2 have high default rates, though fewer instances.
- The dominant Type_1 has a low default rate.
- This informs risk assessment and strategic lending decisions.

---

## Correlations with Target Variable

Pearson correlation heatmap findings:

- Features like 'duration', 'Lender_portion_to_be_repaid', 'Amount_Funded_By_Lender', 'Total_Amount_to_Repay', and 'Total_Amount' are positively correlated with default risk.
- 'lender_id' shows a negative correlation, suggesting some lenders have lower default rates.
- Identifiers ('customer_id', 'tbl_loan_id') have very weak positive correlations, as expected.

These correlations highlight which features may influence default risk.

---

## Country-Specific Opportunities and Risks Visualization

Bar charts and context annotations summarize country-level lending environments:

- **Kenya**: Opportunities with repeat borrowers and Type_1 loans; risks include inflation and unemployment.
- **Ghana**: Risks from high inflation and currency depreciation.
- **Cote d'Ivoire**: Opportunities due to low inflation and robust GDP growth; focus recommended on short-term loans.

This integrates economic context into lending strategies.

---

## Summary of Exploratory Data Analysis Insights

- The dataset is highly skewed toward Kenya and repeat borrowers.
- Type_1 is the most common loan type, but other types show higher default rates.
- Loan amounts and durations are positively skewed and moderately correlated with default.
- Loans are temporally concentrated in 2022.
- Country analysis highlights Cote d'Ivoire as most favorable, Ghana as most risky, and Kenya as offering targeted opportunities.

---

## Overall

The EDA provides a foundational understanding of the data, highlighting loan characteristics, risk factors, and the economic context of lending. These insights are vital for building predictive models and guiding strategic decisions.
