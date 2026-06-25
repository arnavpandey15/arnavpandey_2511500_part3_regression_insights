# Model Equations

## Objective

The objective of this analysis is to develop regression models that explain the factors influencing **monthly sales** across retail stores. Both simple and multiple regression models were developed to understand how individual variables and a combination of variables affect sales performance.

---

# 1. Simple Regression Equations

## Model 1: Marketing Spend

### Regression Equation

**Monthly Sales = 560,777.35 + (2.13 × Marketing Spend)**

### Business Interpretation

- The intercept (**560,777.35**) represents the estimated monthly sales when marketing spend is zero.
- The coefficient (**2.13**) indicates that for every additional unit spent on marketing, monthly sales are expected to increase by approximately **2.13 units**, assuming no other factors change.
- This suggests that increasing marketing investment has a positive impact on store sales.

---

## Model 2: Footfall

### Regression Equation

**Monthly Sales = 446,410.58 + (35.68 × Footfall)**

### Business Interpretation

- The intercept (**446,410.58**) represents the estimated monthly sales when customer footfall is zero.
- The coefficient (**35.68**) indicates that each additional customer visiting the store is associated with an increase of approximately **35.68 units** in monthly sales.
- This highlights customer traffic as one of the strongest drivers of sales performance.

---

# 2. Multiple Regression Equation

The final multiple regression model combines several operational factors to predict monthly sales.

### Regression Equation

**Monthly Sales =**

131,500

+ (1.1859 × Marketing Spend)

+ (33.8704 × Footfall)

+ (2818.2068 × Inventory Availability %)

+ (10,550 × Region_North)

+ (21,940 × Region_South)

+ (17,490 × Region_West)

+ ε

Where:

- ε = Random error (unexplained variation)

---

# 3. Explanation of Each Coefficient

## Intercept

The intercept (**131,500**) represents the estimated monthly sales when all predictor variables are zero and the store belongs to the reference region.

Although this scenario is unlikely in practice, it provides the starting point for calculating predicted sales.

---

## Marketing Spend

**Coefficient = 1.1859**

Business Meaning:

Increasing marketing expenditure is associated with higher monthly sales. For every additional unit invested in marketing, sales are expected to increase by approximately **1.19 units**, assuming other business conditions remain unchanged.

---

## Footfall

**Coefficient = 33.8704**

Business Meaning:

Each additional customer visiting a store contributes approximately **33.87 units** to monthly sales.

This variable has one of the strongest positive effects in the model, indicating that attracting more customers is critical for increasing revenue.

---

## Inventory Availability

**Coefficient = 2818.2068**

Business Meaning:

Improving inventory availability by one percentage point is associated with an increase of approximately **2,818 units** in monthly sales.

Stores with better stock availability are less likely to lose sales due to stock-outs.

---

## Region Dummy Variables

The coefficients compare each region with the reference region.

- **Region_North:** Sales are estimated to be about **10,550 units** higher than the reference region, although this effect is not statistically significant.
- **Region_South:** Sales are estimated to be about **21,940 units** higher than the reference region.
- **Region_West:** Sales are estimated to be about **17,490 units** higher than the reference region.

These coefficients measure the average difference in sales after accounting for all other variables.

---

# 4. Explanation of Dummy Variables

The variable **Region** is categorical and cannot be directly used in regression analysis.

Dummy variables were created to convert the categories into binary variables.

Example:

| Region | Region_North | Region_South | Region_West |
|---------|-------------:|-------------:|------------:|
| East | 0 | 0 | 0 |
| North | 1 | 0 | 0 |
| South | 0 | 1 | 0 |
| West | 0 | 0 | 1 |

Each dummy variable takes a value of:

- **1** if the store belongs to that region.
- **0** otherwise.

This allows the regression model to measure the effect of each region on monthly sales.

---

# 5. Reference Category Used

The **East** region was selected as the **reference category**.

No dummy variable was created for the East region because including all categories would create **perfect multicollinearity (the Dummy Variable Trap)**.

All regional coefficients are interpreted relative to the East region.

---

# 6. Final Model Selected

The **Multiple Linear Regression Model** was selected as the final predictive model.

### Variables Included

- Marketing Spend
- Footfall
- Inventory Availability (%)
- Region Dummy Variables

Dependent Variable:

- Monthly Sales

---

# 7. Reason for Selecting the Final Model

The multiple regression model was selected because it provides the most comprehensive explanation of monthly sales performance.

Reasons include:

- It achieved the highest **R² value (0.811)**, explaining approximately **81.1%** of the variation in monthly sales.
- It considers multiple business drivers simultaneously rather than evaluating one factor at a time.
- It identifies the relative importance of marketing, customer traffic, inventory availability, and regional differences.
- Most predictor variables are statistically significant, making the model suitable for business decision-making.
- The model provides management with practical insights for improving sales through targeted marketing, maintaining adequate inventory, increasing customer footfall, and evaluating regional performance.

Compared with the simple regression models, the multiple regression model offers greater predictive accuracy and better supports strategic planning.

---

# Conclusion

The regression analysis demonstrates that **customer footfall**, **marketing spend**, and **inventory availability** are the primary drivers of monthly sales. Regional differences also contribute to store performance.

The selected multiple regression model provides the best balance between predictive accuracy and business usefulness, making it the preferred model for forecasting sales and supporting operational decision-making.

# Model Equations and Dummy Variable Approach

## Objective

To use categorical variables in a regression model, they must first be converted into numerical values. This is achieved through **dummy variable encoding**, where each category is represented by a binary (0 or 1) variable.

---

# Dummy Variables Created

The following categorical variables were converted into dummy variables:

- region
- store_type

---

## 1. Region Dummy Variables

Suppose the dataset contains the following regions:

- North
- South
- East
- West

Using one-hot encoding, the following dummy variables were created:

| Region | region_East | region_North | region_South |
|---------|-------------|--------------|--------------|
| East | 1 | 0 | 0 |
| North | 0 | 1 | 0 |
| South | 0 | 0 | 1 |
| West | 0 | 0 | 0 |

### Reference Category

**West** was selected as the reference category.

No dummy variable is created for West because including all four dummy variables would cause **perfect multicollinearity (the Dummy Variable Trap)**.

---

## 2. Store Type Dummy Variables

Suppose the dataset contains three store types:

- Supermarket
- Hypermarket
- Convenience Store

The following dummy variables were created:

| Store Type | store_Hypermarket | store_Supermarket |
|------------|-------------------|-------------------|
| Hypermarket | 1 | 0 |
| Supermarket | 0 | 1 |
| Convenience Store | 0 | 0 |

### Reference Category

**Convenience Store** is used as the reference category.

Again, one category is omitted to avoid multicollinearity.

---

# Why One Category Is Removed

If dummy variables are created for every category, one variable becomes a perfect linear combination of the others.

For example,

```
region_West = 1 − (region_East + region_North + region_South)
```

This creates perfect multicollinearity, making regression coefficients impossible to estimate correctly.

Therefore, one category is always omitted and becomes the **reference category**.

---

# Multiple Regression Model

The regression model can be expressed as:

```
Monthly Sales =
β0
+ β1(Marketing Spend)
+ β2(Footfall)
+ β3(Discount %)
+ β4(Inventory Availability)
+ β5(Customer Rating)
+ β6(region_East)
+ β7(region_North)
+ β8(region_South)
+ β9(store_Hypermarket)
+ β10(store_Supermarket)
+ ε
```

where:

- **β0** = Intercept
- **β1 ... β10** = Regression coefficients
- **ε** = Random error term

---

# Interpretation

- The coefficient of each dummy variable represents the expected difference in monthly sales compared to its reference category.
- A positive coefficient indicates higher expected sales than the reference category.
- A negative coefficient indicates lower expected sales than the reference category.
- Numerical variables measure the change in monthly sales for a one-unit increase while keeping all other variables constant.

---

# Summary

| Variable | Reference Category |
|----------|--------------------|
| region | West |
| store_type | Convenience Store |

Using a reference category prevents the dummy variable trap, reduces redundancy, and allows regression coefficients to be interpreted correctly.