# Project 5: Multiple Linear Regression

## Overview

**Level**: Classical ML (Level 1)  
**Prerequisites**: Project 4  
**Estimated Time**: 12-15 hours  
**Notebook**: `05_multiple_linear_regression.ipynb`

## Learning Objectives

- Extend linear regression to multiple input features.
- Understand the normal equations and multivariate gradient descent.
- Detect and interpret multicollinearity.
- Create interaction and polynomial features for multiple variables.
- Compare Ridge, Lasso, and Elastic Net regularization.
- Interpret coefficients in the presence of scaling and correlation.

## Project Description

**Predict House Prices with Multiple Features**

Use a dataset with several predictors (e.g., square footage, number of rooms, location, age) to predict a continuous target. Build the model from scratch, then compare with scikit-learn and regularized variants.

## Topics Covered

### Theory
- Multivariate hypothesis: h(x) = w0 + w1x1 + ... + wnxn
- Vectorized cost function and gradient
- Normal equations: closed-form solution
- Multicollinearity and the Variance Inflation Factor (VIF)
- Feature interactions
- Regularization: Ridge (L2), Lasso (L1), Elastic Net
- Adjusted R2 for model comparison

### Implementation
1. Load and inspect a multivariate dataset.
2. Perform correlation and VIF analysis.
3. Engineer simple interaction features.
4. Implement multivariate linear regression with gradient descent.
5. Solve the normal equations.
6. Fit Ridge, Lasso, and Elastic Net with scikit-learn.
7. Evaluate and compare models.

### Evaluation Metrics
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R2 Score
- Adjusted R2

## Key Exercises

1. Derive the vectorized gradient descent update rule.
2. Implement multivariate linear regression from scratch.
3. Compute VIF for each feature and decide whether to remove any.
4. Add one interaction feature and measure its effect.
5. Fit Ridge and Lasso and compare coefficient shrinkage.
6. Plot residuals and check for heteroscedasticity.
7. Compare the closed-form solution to your iterative solution.

## Final Challenge

Build a complete house price prediction system with feature engineering, multicollinearity handling, and regularized model selection.

---

**Focus on understanding how multiple features work together, not just adding more variables.**
