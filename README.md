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

```text
Sales = Price + Urban + US
