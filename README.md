# Regression-Based Business Insights

## Business Problem Summary

A retail chain aims to understand the key factors influencing **monthly sales** across its stores. The leadership team is considering several business initiatives, including increasing marketing expenditure, improving inventory availability, adjusting discount strategies, reallocating staff, and prioritizing specific store types or regions.

The objective of this project is to use **regression analysis** to identify the variables most strongly associated with monthly sales and provide evidence-based recommendations to support business decision-making.

---

# Dataset Description

The dataset contains operational and performance information for multiple retail stores over different months.

The dataset includes variables related to:

- Monthly sales
- Marketing expenditure
- Customer footfall
- Average discount percentage
- Staff count
- Inventory availability
- Competitor distance
- Customer ratings
- Holiday indicator
- Region
- Store type
- Monthly profit

Before analysis, the dataset was cleaned by handling missing values, preserving the original dataset, and preparing categorical variables for regression.

---

# Dependent and Independent Variables

## Dependent Variable

- **monthly_sales**

This is the target variable that the regression models aim to predict.

---

## Independent Variables

### Numerical Variables

- marketing_spend
- footfall
- avg_discount_pct
- staff_count
- inventory_availability_pct
- competitor_distance_km
- customer_rating

### Categorical Variables

- region
- store_type
- holiday_flag

### Variables Excluded

- store_id (identifier only)
- monthly_profit (to avoid target leakage)

---

# Regression Approach

Three regression models were developed.

## Simple Regression Model 1

Dependent Variable:

- monthly_sales

Independent Variable:

- marketing_spend

Results:

- R² = **0.167**

This model showed that marketing spend has a statistically significant positive relationship with monthly sales but explains only a limited proportion of sales variation.

---

## Simple Regression Model 2

Dependent Variable:

- monthly_sales

Independent Variable:

- footfall

Results:

- R² = **0.736**

Customer footfall was found to be a strong predictor of monthly sales.

---

## Multiple Regression Model

Dependent Variable:

- monthly_sales

Independent Variables:

- marketing_spend
- footfall
- inventory_availability_pct
- region (dummy variables)

Results:

- R² = **0.811**

The multiple regression model provided the strongest explanatory power by considering several business factors simultaneously.

---

# Dummy Variable Approach

The categorical variable **region** was converted into dummy variables before running the multiple regression model.

The following dummy variables were created:

- Region_North
- Region_South
- Region_West

The **East** region was selected as the **reference category**.

One category was intentionally omitted to prevent **perfect multicollinearity (Dummy Variable Trap)**.

Each dummy coefficient measures the difference in expected monthly sales compared with stores located in the East region.

---

# Model Comparison Summary

| Model | Variables Used | R² | Business Usefulness |
|------|----------------|----:|--------------------|
| Simple Regression (Marketing Spend) | marketing_spend | 0.167 | Moderate |
| Simple Regression (Footfall) | footfall | 0.736 | High |
| Multiple Regression | marketing_spend, footfall, inventory availability, region | 0.811 | Very High |

The multiple regression model outperformed both simple regression models by explaining approximately **81.1%** of the variation in monthly sales.

---

# Final Model Selected

The **Multiple Linear Regression Model** was selected as the final predictive model because it achieved the highest explanatory power while incorporating several important operational factors.

The final model includes:

- Marketing Spend
- Customer Footfall
- Inventory Availability
- Region Dummy Variables

The model provides the most comprehensive explanation of monthly sales and is suitable for supporting strategic business decisions.

---

# Business Recommendation

Based on the regression analysis, the following recommendations are proposed:

### Increase Customer Footfall

Customer footfall is the strongest predictor of monthly sales. Leadership should invest in marketing campaigns, customer engagement programs, and promotional activities that attract more customers to stores.

### Improve Inventory Availability

Maintaining high inventory availability reduces lost sales due to stock shortages and contributes significantly to higher monthly sales.

### Optimize Marketing Investment

Marketing spend has a positive and statistically significant relationship with sales. Marketing budgets should be allocated toward campaigns with measurable returns on investment.

### Monitor Regional Performance

Stores located in the South and West regions consistently performed better than the reference region. Leadership should investigate successful operational practices in these regions and consider applying them across other locations.

### Review Underperforming Stores

Residual analysis identified stores whose sales differed substantially from model predictions. These stores should be reviewed for operational inefficiencies, staffing issues, inventory problems, or local competitive pressures.

---

# Assumptions and Limitations

The regression analysis is based on several assumptions:

- Linear relationships exist between predictors and monthly sales.
- Residuals are independent.
- Residual variance is approximately constant (homoscedasticity).
- Predictor variables are not excessively correlated.
- Regression coefficients remain stable across observations.

Limitations of the analysis include:

- The model explains approximately **81.1%** of the variation in monthly sales, leaving **18.9%** unexplained.
- Important variables such as economic conditions, customer demographics, product mix, online sales, seasonal effects, and competitor promotions were not included.
- Regression identifies statistical associations but does not establish causal relationships.

Therefore, regression results should support business decision-making rather than replace managerial judgment.

---

# Screenshots Included

The following screenshots have been included as supporting evidence for the analysis:

- **simple_regression_output.png**
- **multiple_regression_output.png**
- **model_comparison_preview.png**
- **residuals_preview.png**

These screenshots document the regression outputs, model comparison, and residual analysis performed during the project.

---

# Project Deliverables

The completed project includes the following files:

```
README.md

analysis/
├── regression_workbook.xlsx
├── model_comparison.md
├── residual_analysis.md

outputs/
├── model_equations.md
├── final_recommendation.md
├── regression_summary.xlsx

screenshots/
├── simple_regression_output.png
├── multiple_regression_output.png
├── model_comparison_preview.png
└── residuals_preview.png
```

---

# Conclusion

The regression analysis demonstrates that **customer footfall**, **inventory availability**, and **marketing spend** are the most influential factors associated with monthly sales. Among the evaluated models, the **multiple regression model** provides the highest predictive accuracy (**R² = 0.811**) and offers the strongest support for strategic decision-making.

The findings enable leadership to prioritize operational improvements, optimize marketing investments, enhance inventory management, and make informed decisions that can improve overall sales performance while recognizing the limitations of statistical modeling.