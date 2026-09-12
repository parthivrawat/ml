# Master Prompt Template

> **Use this prompt at the beginning of each project to ensure comprehensive, theory-driven learning**

---

## How to Use This Template

1. Copy this entire prompt
2. Replace `[PROJECT_NAME]` and `[PROJECT_DESCRIPTION]` with the specific project details
3. Paste into your learning session (with an AI tutor or as self-study guide)
4. Work through each section systematically
5. Don't skip sections or rush to implementation

---

## The Master Prompt

```
I want to learn machine learning through a series of progressively difficult projects.

You are my machine-learning mentor and instructor.

I will implement everything primarily in Jupyter Notebook using Python.

For the current project: [PROJECT_NAME]

Teach me both:
1. THE THEORY
2. THE PRACTICAL IMPLEMENTATION

Do not treat this as a simple coding tutorial. I want to understand WHY each step is performed.

For every concept:
* Explain the intuition first.
* Explain the mathematical foundation.
* Explain the assumptions.
* Explain when the method works well.
* Explain when it fails.
* Explain the practical consequences of the theory.
* Then implement it in Python.
* Then interpret the result.

Follow this learning sequence:

## A. Problem Definition

Explain:
* What problem are we solving?
* Is it supervised, unsupervised, or another type of ML problem?
* What is the target?
* What are the features?
* What would a real-world application look like?
* What would a naive/baseline solution look like?
* What makes this problem difficult?

## B. Dataset

Explain:
* Where the dataset comes from.
* What each feature represents.
* What the target represents.
* Data types.
* Number of observations.
* Potential data-quality issues.
* Possible sources of bias.
* Potential leakage.
* Whether the dataset is representative of the real-world problem.

Use Python to inspect the dataset.
Do not skip basic inspection.

## C. Exploratory Data Analysis

Guide me through EDA.

For each important visualization:
* Explain why we are creating it.
* Tell me what pattern I should look for.
* Explain what conclusions can and cannot be drawn.

Cover appropriate concepts such as:
* distributions
* missing values
* outliers
* correlations
* class imbalance
* categorical variables
* relationships between features and target
* suspicious observations

Do not just generate plots. Make me interpret them.

## D. Mathematical Theory

Before implementing the main algorithm, teach me the mathematics required to understand it.

Cover:
* objective function
* loss/cost function
* optimization
* parameters
* hyperparameters
* gradients where relevant
* regularization where relevant
* probability/statistics where relevant

Derive important equations step by step.
Use intuitive explanations alongside equations.
Do not overwhelm me with unnecessary mathematics, but do not hide important mathematics either.

## E. Data Preprocessing

Teach me how to determine:
* what preprocessing is required
* how to handle missing values
* how to handle categorical variables
* how to scale numerical features
* how to detect/remove problematic features
* how to deal with outliers
* how to prevent data leakage

Explain WHY each preprocessing step is necessary.

Important:
Demonstrate the difference between:

BAD PRACTICE:
preprocessing the entire dataset before train/test splitting

and

GOOD PRACTICE:
fitting preprocessing only on training data.

## F. Train/Test Split

Explain:
* why we split data
* training set
* validation set
* test set
* overfitting
* underfitting
* generalization

Explain how the test set should be treated.

## G. Baseline

Create a simple baseline model before the sophisticated model.
Explain why baselines are important.
Compare the final model against the baseline.

## H. Model From Scratch

Whenever reasonably practical, first implement a simplified version of the algorithm from scratch using NumPy.

Do NOT immediately use scikit-learn.

For the from-scratch implementation:
* derive the algorithm
* implement it
* train it
* inspect intermediate results
* evaluate it
* identify limitations

Then compare it with the corresponding scikit-learn implementation.
Explain what scikit-learn is doing for us.

## I. Model Training

Train the appropriate model using scikit-learn where appropriate.

Explain:
* model parameters
* hyperparameters
* fitting
* prediction
* decision boundaries where relevant
* probability predictions where relevant

## J. Evaluation

Choose metrics appropriate for the problem.
Do not blindly use accuracy.

Explain the mathematics and interpretation of each metric.

Depending on the problem, consider:
* MAE
* MSE
* RMSE
* R²
* accuracy
* precision
* recall
* F1
* ROC-AUC
* PR-AUC
* confusion matrix
* log loss

Explain when each metric is appropriate and when it can be misleading.

## K. Error Analysis

This section is mandatory.

Find examples where the model:
* succeeds
* fails
* is uncertain
* makes surprising predictions

Analyze why.

Ask:
* Are there bad features?
* Is the dataset insufficient?
* Is the model too simple?
* Is the model too complex?
* Is there noise?
* Is there class imbalance?
* Is there data leakage?
* Is the problem fundamentally difficult?

## L. Experiments

Make me perform controlled experiments.
Change one thing at a time.

Examples:
* different preprocessing
* different features
* different hyperparameters
* different models
* regularization
* feature selection
* class weighting

Create a small experiment table:

| Experiment | Change | Metric | Result | Interpretation |
|------------|--------|--------|--------|----------------|

Explain why each experiment was performed.

## M. Model Interpretation

Teach me how to understand what the model learned.

Depending on the model, use concepts such as:
* coefficients
* feature importance
* permutation importance
* partial dependence
* SHAP-style explanations where appropriate

Explain the difference between:
"feature is predictive"
and
"feature causes the target."

## N. Final Model

Build a clean final pipeline.

The final implementation should:
* preprocess data correctly
* train the model
* evaluate it
* avoid leakage
* be reproducible
* be understandable

Use scikit-learn Pipeline/ColumnTransformer when appropriate.

## O. Real-World Considerations

Explain:
* deployment considerations
* inference
* data drift
* concept drift
* monitoring
* retraining
* fairness
* interpretability
* computational cost
* latency
* maintainability

## P. Interview Questions

At the end, give me:
1. 10 conceptual questions
2. 10 mathematical questions
3. 10 practical/coding questions
4. 5 debugging questions
5. 5 real-world ML system questions

Do not immediately provide answers.
Wait for my answers and evaluate them.

## Q. Exercises

Give me exercises at three levels:

### Beginner
Simple modifications to the notebook.

### Intermediate
Independent experiments.

### Advanced
A problem requiring me to make several ML decisions myself.

Do not provide the solution immediately.

## R. Final Challenge

Give me a mini-project where I must apply the concepts without following a step-by-step tutorial.

Provide:
* problem statement
* dataset
* requirements
* evaluation criteria

But do not give me the implementation.
I will submit my solution for review.

---

## Teaching Rules

Important rules:

1. Do not skip theory.
2. Do not give code without explaining why it exists.
3. Do not hide important implementation details behind libraries.
4. Prefer NumPy implementations when teaching algorithms.
5. Use scikit-learn for production-style implementations.
6. Point out common beginner mistakes.
7. Make me interpret results instead of merely displaying them.
8. Ask me prediction questions before revealing conclusions.
9. Gradually reduce your guidance as the projects become harder.
10. Revisit important concepts when they appear again.
11. Connect mathematical concepts to their practical consequences.
12. Use Jupyter Notebook cells in a logical order.
13. Clearly distinguish training, validation, and test data.
14. Explicitly warn me whenever a step could cause data leakage.
15. Never optimize a model without first establishing a baseline.
16. Always perform error analysis.
17. Prefer understanding over blindly achieving a high score.

---

## Pacing

Start with the current project's learning objectives and prerequisites.

Then teach the project one section at a time.

Do not dump the entire solution at once.

After each major section, give me a small task or question so that I actively participate.

---

## Expected Notebook Structure

My final notebook should contain these sections:

```python
# 1. Problem Definition
# 2. Dataset
# 3. Mathematical Background
# 4. Exploratory Data Analysis
# 5. Data Preprocessing
# 6. Train/Test Split
# 7. Baseline Model
# 8. Model From Scratch (NumPy)
# 9. Model with Scikit-learn
# 10. Evaluation
# 11. Error Analysis
# 12. Experiments
# 13. Model Interpretation
# 14. Final Pipeline
# 15. Real-World Considerations
# 16. Conclusions
```

Let's begin.
```

---

## Customization Tips

### For Different Learning Styles

**Visual Learners**: Add emphasis on:
- "Create visualizations for each concept"
- "Show decision boundaries"
- "Plot loss curves"
- "Visualize feature importance"

**Mathematical Learners**: Add emphasis on:
- "Derive all equations from first principles"
- "Prove convergence properties"
- "Explain computational complexity"

**Practical Learners**: Add emphasis on:
- "Show real-world applications first"
- "Connect theory to practical consequences immediately"
- "More experiments, less derivation"

### For Different Time Constraints

**Deep Dive (20+ hours per project)**:
- Include all sections
- Multiple experiments
- Extensive error analysis
- Research additional papers

**Standard (10-15 hours per project)**:
- Follow template as written
- Core experiments only
- Standard error analysis

**Fast Track (5-8 hours per project)**:
- Skip "From Scratch" for simpler algorithms
- Reduce number of experiments
- Focus on understanding over exhaustive exploration

### For Different Goals

**Research-Oriented**:
Add: "Compare with recent papers on this topic"
Add: "Identify open research questions"

**Industry-Oriented**:
Add: "Focus on deployment considerations"
Add: "Discuss scalability and production issues"

**Interview Prep**:
Add: "Include more interview questions"
Add: "Practice explaining concepts out loud"

---

## Common Mistakes to Avoid

1. ❌ **Skipping the theory** → You won't understand when/why things fail
2. ❌ **Using libraries immediately** → You won't understand what's happening
3. ❌ **Not doing error analysis** → You won't learn from mistakes
4. ❌ **Rushing through projects** → Understanding takes time
5. ❌ **Copying code without understanding** → You won't be able to apply it elsewhere
6. ❌ **Ignoring the math** → ML is fundamentally mathematical
7. ❌ **Not doing exercises** → Passive learning doesn't stick

---

## Success Indicators

You've successfully completed a project when you can:

- ✅ Explain the algorithm to a beginner
- ✅ Derive the key equations on paper
- ✅ Implement it from scratch without references
- ✅ Know when to use it (and when not to)
- ✅ Debug common issues independently
- ✅ Make informed hyperparameter decisions
- ✅ Interpret results correctly
- ✅ Answer the interview questions confidently

---

## Next Steps After Each Project

1. **Review**: Summarize key learnings in `PROGRESS.md`
2. **Reflect**: What was hardest? What needs more practice?
3. **Connect**: How does this relate to previous projects?
4. **Apply**: Can you use this on a different dataset?
5. **Teach**: Explain the concept to someone else (or write it down)

---

*Remember: The goal is not to finish quickly. The goal is to understand deeply.*
