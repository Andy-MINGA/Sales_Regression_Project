# Sales Regression Project

## Objective
The goal of this project is to predict **sales** based on the predictors **Price**, **Urban**, and **US** using multiple linear regression. We also evaluate model fit, significance of predictors, and diagnostic measures.

---

## Dataset
The dataset includes:
- `Sales` – Target variable (in thousands of units)
- `Price` – Continuous variable for product price
- `Urban` – Qualitative variable (Yes/No) indicating if the store is in an urban area
- `US` – Qualitative variable (Yes/No) indicating if the store is located in the US

---

## Analysis Steps

### (a) Fit a multiple regression model
We fit the model:

\[
Sales \sim Price + Urban + US
\]

using Python.  

---

### (b) Interpretation of Coefficients
- **Intercept (13.0435):** Baseline predicted sales for a non-US, non-urban store with price = 0.  
- **Urban\_Yes (-0.0219):** Being in an urban area decreases sales slightly, but not statistically significant.  
- **US\_Yes (1.2006):** Stores in the US sell on average 1,200 more units; statistically significant.  
- **Price (-0.0545):** Increasing price by 1 unit decreases sales by ~54.5 units; statistically significant.

---

### (c) Fitted Model Equation

\[
\hat{Sales} = 13.0435 - 0.0219 \cdot Urban_{Yes} + 1.2006 \cdot US_{Yes} - 0.0545 \cdot Price
\]

Where:
- `Urban_Yes = 1` if store is urban, 0 otherwise  
- `US_Yes = 1` if store is in the US, 0 otherwise  
- `Price` is a continuous numeric variable

---

### (d) Test for Significance
We test for each predictor:

\[
H_0: \beta_j = 0
\]

- Reject \(H_0\) if the p-value < 0.05  
- In our model: **Urban** is not significant, while **Price** and **US** are significant.

---

### (e) Fit Reduced Model
Since Urban was not significant, we refit the model using only:

\[
Sales \sim Price + US
\]

---

### (f) Model Fit Comparison

| Model        | R²    | Adjusted R² |
|--------------|-------|-------------|
| Full         | 0.239 | 0.234       |
| Reduced      | 0.239 | 0.235       |

The reduced model performs similarly to the full model but is simpler and more interpretable.

---

### (g) 95% Confidence Intervals for Reduced Model

| Coefficient   | Lower Bound | Upper Bound |
|---------------|------------|-------------|
| Intercept     | 11.7903    | 14.2713     |
| US\_Yes       | 0.6915     | 1.7078      |
| Price         | -0.0648    | -0.0442     |

---

### (h) Diagnostics: Outliers, Leverage, and Influence
- **Outliers:** Large standardized residuals (\(|r_i| > 2\) or \(> 3\))  
- **High Leverage Points:** Leverage > 2 × average leverage (\(2 \bar{h}\))  
- **Influential Points:** Cook’s distance \(D_i > 0.5\) or \(> 1\); appear as large bubbles in influence plots

---

## Figures

![Fitted Full Model](images/Summ4.png)  
*Figure 1: Full model fitting*

![Fitted Reduced Model](images/Summ5.png)  
*Figure 2: Reduced model fitting (without Urban variable)*

---

## Conclusion
- Price and US location significantly affect sales.  
- Urban status is not significant and can be removed for a simpler model.  
- The reduced model explains the data nearly as well as the full model.  
- Diagnostics show no extreme outliers or highly influential points that would invalidate the model.

---
