# 📊 Sales Regression Project

## 🎯 Objective
Predict **sales** using **Price**, **Urban**, and **US** as predictors with multiple linear regression.  
We evaluate model fit, significance of predictors, and conduct diagnostic checks.

---

## 🗂 Dataset
The dataset contains:

| Variable | Description |
|----------|-------------|
| `Sales` | Target variable (in thousands of units) |
| `Price` | Continuous variable for product price |
| `Urban` | Qualitative (Yes/No) indicating if store is urban |
| `US`    | Qualitative (Yes/No) indicating if store is in the US |

---

## 🛠 Analysis Steps

### (a) Fit a Multiple Regression Model
We fit the model:  

\[
Sales \sim Price + Urban + US
\]

using Python.

---

### (b) Interpretation of Coefficients
| Coefficient       | Estimate | Interpretation |
|------------------|----------|----------------|
| Intercept         | 13.0435 | Baseline predicted sales for a non-US, non-urban store with price = 0 |
| Urban\_Yes        | -0.0219 | Slight decrease in sales for urban stores; not statistically significant |
| US\_Yes           | 1.2006  | US stores sell ~1,200 more units on average; statistically significant |
| Price             | -0.0545 | Increasing price by 1 unit decreases sales by ~54.5 units; statistically significant |

---

### (c) Fitted Model Equation

\[
$\hat{Sales} = 13.0435 - 0.0219 \cdot Urban_{Yes} + 1.2006 \cdot US_{Yes} - 0.0545 \cdot Price$
\]

**Notes:**
- `Urban_Yes = 1` if store is urban, 0 otherwise  
- `US_Yes = 1` if store is in the US, 0 otherwise  
- `Price` is continuous  

---

### (d) Significance Testing
Null hypothesis for each predictor:  

\[
$H_0: \beta_j = 0$
\]

- Reject \($H_0$\) if p-value < 0.05  
- In this model:
  - **Price** and **US** are significant  
  - **Urban** is not significant

---

### (e) Fit Reduced Model
Since `Urban` was not significant, the reduced model is:  

\[
Sales \sim Price + US
\]

---

### (f) Model Fit Comparison

| Model   | R²    | Adjusted R² |
|---------|-------|-------------|
| Full    | 0.239 | 0.234       |
| Reduced | 0.239 | 0.235       |

✅ Reduced model is simpler and almost equally performant.

---

### (g) 95% Confidence Intervals (Reduced Model)

| Coefficient | Lower Bound | Upper Bound |
|------------|-------------|-------------|
| Intercept  | 11.7903     | 14.2713     |
| US\_Yes    | 0.6915      | 1.7078      |
| Price      | -0.0648     | -0.0442     |

---

### (h) Diagnostics: Outliers, Leverage, and Influence
- **Outliers:** Standardized residuals \(|r_i| > 2\) (moderate), >3 (extreme)  
- **High Leverage Points:** Leverage > 2 × average leverage (\(2 \bar{h}\))  
- **Influential Points:** Cook’s distance \(D_i > 0.5\) (moderate), >1 (high); visualized as large bubbles in influence plots

---

## ✅ Conclusion
- **Price** and **US location** significantly affect sales.  
- **Urban status** is not significant and can be removed for simplicity.  
- The **reduced model** explains the data nearly as well as the full model.  
- Diagnostic checks show no extreme outliers or influential points that compromise model validity.

---


