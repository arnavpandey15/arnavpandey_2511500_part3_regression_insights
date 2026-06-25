# Model Comparison

## Objective

The purpose of this comparison is to evaluate the performance of the simple regression models against the multiple regression model in explaining variations in monthly sales. The comparison considers explanatory power, statistical significance, business usefulness, and model limitations.

---

# Model Comparison Table

| Item | Model 1 | Model 2 | Model 3 |
|------|---------|---------|---------|
| **Model Name** | Simple Regression (Marketing Spend) | Simple Regression (Footfall) | Multiple Regression |
| **Dependent Variable** | monthly_sales | monthly_sales | monthly_sales |
| **Independent Variables** | marketing_spend | footfall | marketing_spend, footfall, inventory_availability_pct, region (dummy variables) |
| **R-squared** | 0.167 | 0.736 | 0.811 |
| **Significant Variables** | Marketing Spend | Footfall | Marketing Spend, Footfall, Inventory Availability, Region_South, Region_West |
| **Business Usefulness** | Moderate | High | Very High |
| **Limitations** | Uses only one predictor and explains limited variation in sales. | Ignores other important factors affecting sales. | Does not include external factors such as competition, economic conditions, or customer demographics. |

---

# Comparison of Explanatory Power

### Model 1: Marketing Spend

- R² = **0.167**
- Explains approximately **16.7%** of the variation in monthly sales.
- Provides limited predictive ability because it considers only marketing expenditure.

### Model 2: Footfall

- R² = **0.736**
- Explains approximately **73.6%** of the variation in monthly sales.
- Demonstrates that customer traffic is a strong predictor of sales.

### Model 3: Multiple Regression

- R² = **0.811**
- Explains approximately **81.1%** of the variation in monthly sales.
- Provides the strongest predictive performance by considering multiple business factors simultaneously.

---

# Significant Variables

| Variable | Statistical Significance | Interpretation |
|-----------|-------------------------|---------------|
| Marketing Spend | Significant | Positive relationship with monthly sales. |
| Footfall | Highly Significant | Strong positive impact on monthly sales. |
| Inventory Availability | Significant | Better inventory availability leads to higher sales. |
| Region_South | Significant | Stores in the South outperform the reference region. |
| Region_West | Significant | Stores in the West outperform the reference region. |
| Region_North | Not Significant | No meaningful difference compared with the reference region. |

---

# Business Usefulness

## Model 1

Useful for estimating the effect of marketing expenditure alone but insufficient for making comprehensive business decisions.

## Model 2

Useful for understanding the importance of customer traffic and predicting sales based on store visits.

## Model 3

Most useful for business decision-making because it considers several operational factors simultaneously. Management can use this model to optimize marketing budgets, improve inventory availability, and prioritize high-performing regions.

---

# Model Limitations

Although the multiple regression model performs well, it does not capture every factor influencing sales.

Some important variables not included in the model may include:

- Seasonal demand
- Economic conditions
- Competitor promotions
- Product mix
- Customer demographics
- Online sales
- Store size
- Local events

These omitted variables may explain the remaining variation in monthly sales.

---

# Overall Conclusion

Among the three models, the **Multiple Regression Model** provides the best performance with an R² of **0.811**, indicating that it explains approximately **81.1%** of the variation in monthly sales.

While the simple regression models help understand the individual effects of marketing spend and footfall, the multiple regression model provides a more realistic representation of business performance by incorporating several predictors simultaneously. Therefore, the multiple regression model is recommended for forecasting monthly sales and supporting strategic business decisions.