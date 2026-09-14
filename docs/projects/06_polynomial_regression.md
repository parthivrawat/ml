# Project 6: Polynomial Regression

## Overview

**Level**: Classical ML (Level 1)  
**Prerequisites**: Projects 4-5  
**Estimated Time**: 10-12 hours  
**Notebook**: `06_polynomial_regression.ipynb`

## Learning Objectives

- Model non-linear relationships with polynomial features.
- Understand the bias-variance tradeoff through polynomial degree.
- Use validation and learning curves to select model complexity.
- Implement polynomial regression from scratch.
- Recognize overfitting and underfitting in practice.

## Project Description

**Model Non-Linear Trends**

Create synthetic data and real-world regression problems where the relationship between a feature and target is non-linear. Compare linear, polynomial, and regularized polynomial models.

## Topics Covered

### Theory
- Polynomial basis expansion
- Feature interaction terms
- Bias-variance tradeoff
- Underfitting vs overfitting
- Model capacity and generalization
- Learning curves and validation curves
- Regularization for high-degree polynomials

### Implementation
1. Generate or load non-linear data.
2. Create polynomial features manually and with `PolynomialFeatures`.
3. Fit polynomial regression with ordinary least squares.
4. Plot fitted curves for different degrees.
5. Use a validation set to select the best degree.
6. Apply Ridge regression to control high-degree overfitting.

### Evaluation Metrics
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R2 Score
- Validation error by degree

## Key Exercises

1. Derive the gradient for polynomial regression from scratch.
2. Generate a synthetic non-linear dataset.
3. Fit polynomial degrees 1, 2, 3, 5, 10, and 15.
4. Plot training and validation error as a function of degree.
5. Identify the degree that best generalizes.
6. Explain the difference between high bias and high variance.

## Final Challenge

Choose the right model complexity for a non-linear regression dataset and justify your choice using validation curves and residual analysis.

---

**Polynomial regression is a powerful tool, but it makes overfitting easy. Always validate complexity on held-out data.**
