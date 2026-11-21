# ApexPlanet Data Analytics Internship — Task 4
## Data Storytelling & Statistical Validation

### Dataset overview
- Dataset: ApexPlanet Task 1 cleaned dataset
- Rows: 1,000 orders; columns: 19
- Date coverage: 2025-01-01 to 2026-01-01
- Total sales: ₹139,399,439.65
- Mean order value: ₹139,399.44; median: ₹108,594.02
- Sales calculation checks passed: 1000/1000
- IQR-flagged sales outliers: 19 (1.9%)

### Business story / key findings
1. **Electronics is the largest category:** ₹50,778,581.70 in sales (36.4% of total).
2. **Laptop is the top product by sales:** ₹25,443,008.51; Mobile is close behind at ₹25,335,573.19.
3. **Patna leads known cities:** ₹19,285,966.89; Unknown city values total ₹1,540,617.54 and should be improved in source data.
4. **2025 monthly sales:** Highest month is 3 (13,059,899.94); lowest is 9 (₹9,179,896.29). This is monthly variation, not evidence of a causal driver.
5. The dataset includes 995 orders in 2025 and 5 orders in 2026; 2026 is too sparse for a year-over-year comparison.

### Hypothesis testing
**Question:** Is average order sales significantly different between male and female customers?

- H₀: Mean Total_Sales for male customers equals mean Total_Sales for female customers.
- H₁: The two mean order sales are different.
- Method: Welch independent two-sample t-test (two-sided; α = 0.05).
- Male mean: ₹141,807.34 (n=511)
- Female mean: ₹136,883.21 (n=489)
- Mean difference (male − female): ₹4,924.13
- t statistic: 0.6826
- p-value: 0.4950
- Decision: **Fail to reject H₀** because p > 0.05.
- Interpretation: The observed difference is not statistically significant in this dataset. Do not claim gender causes higher spending.

### Recommendations
- Prioritize inventory and campaign planning for Electronics, especially Laptop and Mobile.
- Investigate monthly peaks using promotions, seasonality, and stock availability data before attributing causes.
- Improve missing/Unknown city capture (13 records).
- Collect a larger and more balanced 2026 sample before comparing annual performance.
- Use customer segments and product/category margins (not sales alone) to optimize profitability.

### Limitations
This is an observational cleaned dataset. The analysis uses sales revenue, not profit or margin. A small amount of city information is Unknown, and 2026 contains only five orders. Statistical results describe this dataset and do not establish causality.
