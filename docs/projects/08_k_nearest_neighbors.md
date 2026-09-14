# Project 8: k-Nearest Neighbors

## Overview

**Level**: Classical ML (Level 1)  
**Prerequisites**: Projects 4-7  
**Estimated Time**: 12-15 hours  
**Notebook**: `08_k_nearest_neighbors.ipynb`

## Learning Objectives

- Understand instance-based learning and lazy learning.
- Implement k-NN for both classification and regression from scratch.
- Compare distance metrics and understand their assumptions.
- See why feature scaling matters for k-NN.
- Explore the curse of dimensionality.
- Choose k using validation error.

## Project Description

**Instance-Based Classification and Regression**

Use a tabular dataset (e.g., Iris for classification or a synthetic regression dataset) to build a k-NN model. First implement the algorithm manually, then compare with scikit-learn.

## Topics Covered

### Theory
- Instance-based learning
- Distance metrics: Euclidean, Manhattan, Minkowski, Cosine
- Majority voting and weighted voting
- k for classification vs regression
- Feature scaling necessity
- Curse of dimensionality
- Decision boundaries

### Implementation
1. Load a small classification dataset.
2. Implement a k-NN classifier from scratch.
3. Compare uniform and distance-weighted voting.
4. Test different values of k.
5. Measure the effect of feature scaling.
6. Implement k-NN regression on a continuous target.
7. Compare with scikit-learn `KNeighborsClassifier` and `KNeighborsRegressor`.

### Evaluation Metrics
- Classification: accuracy, precision, recall, F1, confusion matrix
- Regression: MAE, MSE, RMSE, R2

## Key Exercises

1. Implement k-NN classification without scikit-learn.
2. Compare Euclidean vs Manhattan distance on the same dataset.
3. Show how accuracy changes with different k values.
4. Demonstrate the impact of unscaled features.
5. Plot decision boundaries for a 2D feature set.
6. Discuss why k-NN can fail in high-dimensional spaces.

## Final Challenge

Select the best k and distance metric for a given dataset using a validation set, and justify your choice with an error analysis.

---

**k-NN is simple, but its performance depends heavily on distance, scaling, and dimensionality. Treat it as a careful baseline, not a default.**
