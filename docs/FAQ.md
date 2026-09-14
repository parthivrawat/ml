# Frequently Asked Questions

> Quick answers to common questions about the learning curriculum

---

## Do I need a math background to start?

No. Projects 1-7 build the necessary math and programming foundations. However, you should be comfortable with high-school algebra and be willing to learn statistics, linear algebra, and calculus as you go.

---

## How much time should I spend on each project?

- **Foundations (Projects 1-7)**: 8-15 hours each
- **Classical ML (Projects 8-18)**: 10-20 hours each
- **Engineering/End-to-End (Projects 19-40)**: 12-25 hours each
- **Deep Learning (Projects 41-50)**: 15-50 hours each

These are rough estimates. The goal is understanding, not speed.

---

## Can I skip projects?

Avoid skipping levels. Each level builds on concepts from the previous one. You may skip a project within a level only if you can already explain its core concepts and implement them from scratch.

---

## Why implement algorithms from scratch first?

Writing the algorithm yourself teaches you what is actually happening under the hood. It makes you better at debugging, choosing hyperparameters, and understanding the limitations of libraries.

---

## Should I use scikit-learn or write everything from scratch?

For each algorithm:

1. Implement a simplified version with NumPy first.
2. Compare it against the scikit-learn implementation.
3. Use the library version for experiments, evaluation, and final pipelines.

---

## How do I know if I have understood a project?

You should be able to:

- Explain the algorithm to someone without ML experience.
- Derive the key equations or update rules.
- Implement a working version from scratch.
- Know when the algorithm works well and when it fails.
- Debug common errors independently.

---

## What should I do when I get stuck?

1. Re-read the theory section carefully.
2. Check your code against the math one line at a time.
3. Print intermediate values to find where the logic diverges.
4. Reduce the problem to a smaller dataset or simpler case.
5. Search for the concept, not the final answer.
6. Take a break and return with fresh eyes.

---

## How should I track my progress?

Use `PROGRESS.md` after every project. Record:

- What you learned.
- What was confusing.
- Which exercises you completed.
- Questions you still have.
- Mistakes you made and how you fixed them.

---

## Can I use this with an AI tutor or assistant?

Yes, but use it actively. Ask for explanations, not solutions. Use `docs/MASTER_PROMPT.md` as a learning guide. Never copy code you do not understand.

---

## Is it okay to make mistakes?

Yes. Mistakes are part of learning. The exercises and error-analysis sections are designed to make you struggle with the right concepts so that understanding sticks.

---

## Do I need a GPU?

Not for most of the curriculum. A GPU becomes useful in Level 5 (Deep Learning) for larger image and transformer models, but many exercises can be completed on a CPU.

---

## What is the best environment to use?

Jupyter Notebook or JupyterLab is recommended for all projects because it supports the iterative, cell-based workflow used throughout the curriculum.

---

## Where can I find datasets?

- `datasets/` folder in this repository.
- Scikit-learn built-in datasets.
- UCI Machine Learning Repository.
- Kaggle.
- OpenML.

Always inspect the dataset license and description before using it.

---

## How do I avoid data leakage?

- Split data into train/validation/test sets before any preprocessing.
- Fit scalers, imputers, and transformers only on the training data.
- Treat the test set as unseen data that simulates the future.
- Be suspicious of features that are too strongly correlated with the target.

---

## What if a project takes much longer than estimated?

That is normal. The estimates assume a steady pace. It is better to finish one project with deep understanding than to rush through several projects.

---

## Where do I go after finishing all 50 projects?

After completing the curriculum, consider:

- Kaggle competitions for real-world practice.
- Building a portfolio project from end to end.
- Studying MLOps, specialized domains (computer vision, NLP, time series), or research papers.

---

*If your question is not listed here, ask it during your project work and add the answer to your learning notes.*
