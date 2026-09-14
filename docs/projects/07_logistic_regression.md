# Project 7: Logistic Regression

## Overview

**Level**: Classical ML (Level 1)  
**Prerequisites**: Projects 4-6  
**Estimated Time**: 15-18 hours  
**Notebook**: `07_logistic_regression.ipynb`

## Learning Objectives

- Understand classification as a probability estimation problem.
- Derive the sigmoid function and log loss.
- Implement binary logistic regression from scratch.
- Extend to multi-class classification with one-vs-rest and softmax.
- Tune the decision threshold for different business goals.
- Interpret coefficients as log-odds.

## Project Description

**Binary and Multi-Class Classification**

Build logistic regression models for problems such as spam detection, customer churn, or digit recognition. Start with a two-class problem, then generalize to multiple classes.

## Topics Covered

### Theory
- Sigmoid function and log-odds
- Maximum likelihood estimation
- Binary cross-entropy / log loss
- Decision boundary and threshold
- Gradient for logistic regression
- One-vs-rest and softmax multi-class strategies
- L2 regularization in logistic regression

### Implementation
1. Load a binary classification dataset.
2. Explore class balance and feature distributions.
3. Implement logistic regression with gradient descent.
4. Fit scikit-learn `LogisticRegression`.
5. Tune the classification threshold.
6. Solve a multi-class problem with one-vs-rest.
7. Interpret model coefficients.

### Evaluation Metrics
- Accuracy
- Precision, Recall, F1 score
- Confusion matrix
- ROC-AUC
- Log loss

## Key Exercises

1. Derive the log loss gradient with respect to weights.
2. Implement sigmoid and prediction functions from scratch.
3. Train binary logistic regression without using scikit-learn.
4. Compare your implementation with scikit-learn.
5. Tune the decision threshold and observe precision-recall tradeoffs.
6. Train a multi-class model and interpret the coefficient matrix.

## Final Challenge

Build an end-to-end classification pipeline that includes threshold tuning, calibration, and a written recommendation for which threshold to use in production.

---

**Logistic regression is a natural first classifier. Master the probability interpretation before moving to more complex models.**
