# Project 9: Naive Bayes

## Overview

**Level**: Classical ML (Level 1)  
**Prerequisites**: Projects 4-8  
**Estimated Time**: 10-12 hours  
**Notebook**: `09_naive_bayes.ipynb`

## Learning Objectives

- Understand Bayes' theorem and the role of priors and likelihoods.
- Apply the conditional independence assumption and understand its consequences.
- Implement Gaussian, Multinomial, and Bernoulli Naive Bayes from scratch.
- Handle zero probabilities with Laplace smoothing.
- Compare Naive Bayes to logistic regression and k-NN.

## Project Description

**Probabilistic Classification**

Build Naive Bayes classifiers for both continuous and text data. Use a dataset such as the Iris flowers for Gaussian Naive Bayes and a simple spam or sentiment dataset for Multinomial/Bernoulli Naive Bayes.

## Topics Covered

### Theory
- Bayes' theorem: P(y | x) = P(x | y) * P(y) / P(x)
- Prior, likelihood, and posterior
- Conditional independence assumption
- Gaussian, Multinomial, and Bernoulli likelihoods
- Laplace smoothing for zero counts
- Log-probabilities for numerical stability

### Implementation
1. Load a continuous dataset for Gaussian Naive Bayes.
2. Implement Gaussian Naive Bayes from scratch.
3. Compare with scikit-learn `GaussianNB`.
4. Load a text or count dataset.
5. Implement Multinomial Naive Bayes from scratch.
6. Use Laplace smoothing and compare smoothing values.
7. Compare Naive Bayes with logistic regression and k-NN.

### Evaluation Metrics
- Accuracy
- Precision, recall, F1
- Confusion matrix
- Log loss

## Key Exercises

1. Derive the Gaussian likelihood for a single feature.
2. Implement the full Naive Bayes prediction pipeline.
3. Show the effect of Laplace smoothing on zero probabilities.
4. Compare all three variants (Gaussian, Multinomial, Bernoulli).
5. Explain when the conditional independence assumption breaks.
6. Compare performance and training time with logistic regression.

## Final Challenge

Build a text classification pipeline using Multinomial Naive Bayes with your own preprocessing and vectorization, and report the most informative features per class.

---

**Naive Bayes is fast and surprisingly effective when the independence assumption is reasonable. Always examine whether that assumption fits your data.**
