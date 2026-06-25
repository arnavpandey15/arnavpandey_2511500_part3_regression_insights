# Residual Analysis

## Objective

Residual analysis was performed to evaluate the prediction accuracy of the final multiple regression model.

The final model used the following predictors:

- Marketing Spend
- Footfall
- Inventory Availability (%)
- Region (dummy variables)

The dependent variable was **monthly_sales**.

Residuals were calculated using:

> **Residual = Actual Monthly Sales − Predicted Monthly Sales**

- A **positive residual** means the store achieved higher sales than the model predicted.
- A **negative residual** means the model predicted higher sales than the store actually achieved.

---

# Predicted Sales and Residual Calculation

For each observation in the dataset:

**Predicted Sales**

= Regression Equation Output

**Residual**

= Actual Sales − Predicted Sales

The final multiple regression model achieved an **R² of 0.811**, indicating that approximately **81.1%** of the variation in monthly sales is explained by the selected predictors.

---

# Five Largest Positive Residuals

These stores performed substantially better than predicted by the regression model.

| Rank | Store ID | Month | Region | Actual Sales | Predicted Sales | Residual |
|------|----------|---------|--------|-------------:|----------------:|----------:|
| 1 | STR-1028 | 2025-04 | East | 713,611.16 | 590,071.86 | **123,539.30** |
| 2 | STR-1026 | 2025-04 | East | 625,514.04 | 511,045.81 | **114,468.23** |
| 3 | STR-1051 | 2025-02 | East | 787,715.51 | 676,940.06 | **110,775.45** |
| 4 | STR-1073 | 2025-03 | East | 813,316.71 | 714,345.17 | **98,971.54** |
| 5 | STR-1021 | 2025-03 | West | 727,241.86 | 637,964.61 | **89,277.25** |

---

# Five Largest Negative Residuals

These stores performed substantially worse than predicted by the regression model.

| Rank | Store ID | Month | Region | Actual Sales | Predicted Sales | Residual |
|------|----------|---------|--------|-------------:|----------------:|----------:|
| 1 | STR-1017 | 2025-03 | West | 685,379.08 | 848,156.22 | **−162,777.14** |
| 2 | STR-1012 | 2025-01 | West | 595,467.60 | 736,451.54 | **−140,983.94** |
| 3 | STR-1023 | 2025-02 | South | 627,171.90 | 749,339.69 | **−122,167.79** |
| 4 | STR-1009 | 2025-01 | North | 641,865.03 | 760,876.85 | **−119,011.82** |
| 5 | STR-1077 | 2025-02 | South | 538,376.00 | 649,612.36 | **−111,236.36** |

---

# Business Interpretation of Positive Residuals

Stores with large positive residuals generated considerably higher sales than expected.

Possible explanations include:

- Strong local customer demand
- Successful store-level promotions
- Excellent store management
- Better customer service
- Popular product assortment
- Local events or seasonal factors not included in the regression model

These stores may represent best-performing locations whose strategies can be studied and replicated across the retail chain.

---

# Business Interpretation of Negative Residuals

Stores with large negative residuals generated lower sales than expected.

Possible business reasons include:

- Inventory shortages
- Poor operational efficiency
- Increased local competition
- Staffing challenges
- Lower customer demand
- External economic conditions
- Temporary operational disruptions

These stores should be investigated further to identify operational issues and opportunities for improvement.

---

# Under-Prediction and Over-Prediction

### Under-Predicted Stores

The model under-predicted sales for several stores, particularly those in the East and West regions with exceptionally strong performance.

This suggests that the model does not fully capture factors such as:

- Exceptional store management
- Customer loyalty
- Local marketing initiatives
- Product assortment
- Regional demand differences

---

### Over-Predicted Stores

The model over-predicted sales for several stores in the West, South, and North regions.

Possible explanations include:

- Lower-than-expected customer demand
- Operational inefficiencies
- Supply chain disruptions
- Increased competition
- Local economic conditions

These factors are not explicitly included in the regression model and therefore contribute to prediction errors.

---

# Conclusion

The residual analysis indicates that the multiple regression model provides strong overall predictive performance (R² = **0.811**), but prediction errors remain for some stores.

The largest positive residuals identify stores performing better than expected and may highlight successful business practices worth replicating. Conversely, the largest negative residuals identify stores that underperformed relative to expectations and may require operational review.

Overall, residual analysis provides valuable insights into where the model performs well, where it struggles, and which additional variables could improve future forecasting accuracy.