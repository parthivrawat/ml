# Notebooks Folder

> This is where your learning happens!

---

## Purpose

This folder contains all your Jupyter notebooks—one for each of the 50 projects.

---

## Naming Convention

Use this format for your notebooks:

```
01_python_ml_foundations.ipynb
02_numpy_from_scratch.ipynb
03_pandas_data_analysis.ipynb
04_visualization.ipynb
05_statistics_probability.ipynb
...
50_capstone_project.ipynb
```

**Format**: `{number}_{project_name}.ipynb`

---

## Notebook Structure

Each notebook should follow this structure:

```markdown
# Project X: [Project Name]

## 1. Problem Definition
[What problem are we solving?]

## 2. Dataset
[Load and inspect the data]

## 3. Mathematical Background
[Theory and equations]

## 4. Exploratory Data Analysis
[Visualizations and insights]

## 5. Data Preprocessing
[Cleaning and preparation]

## 6. Train/Test Split
[Split the data]

## 7. Baseline Model
[Simple solution first]

## 8. Model From Scratch
[NumPy implementation]

## 9. Model with Library
[Scikit-learn implementation]

## 10. Evaluation
[Metrics and performance]

## 11. Error Analysis
[Where did it fail and why?]

## 12. Experiments
[Improvements and variations]

## 13. Model Interpretation
[What did the model learn?]

## 14. Final Pipeline
[Clean, production-ready code]

## 15. Conclusions
[Summary and key learnings]
```

---

## Tips for Good Notebooks

### 1. Use Markdown Cells Liberally

Explain what you're doing and why. Your notebook should be readable by someone else (or future you).

### 2. One Concept Per Cell

Don't cram everything into one cell. Break it down.

### 3. Run Cells in Order

Notebooks can get confusing if run out of order. Use "Restart & Run All" periodically.

### 4. Comment Your Code

```python
# Good
def normalize(X):
    """Normalize features to [0, 1] range."""
    return (X - X.min()) / (X.max() - X.min())

# Bad
def normalize(X):
    return (X - X.min()) / (X.max() - X.min())
```

### 5. Visualize Often

A good visualization is worth a thousand numbers.

### 6. Save Frequently

Ctrl+S (or Cmd+S) is your friend.

---

## Notebook Checklist

Before considering a project complete, make sure your notebook has:

- [ ] Clear section headers
- [ ] Explanations in markdown cells
- [ ] Well-commented code
- [ ] Visualizations with titles and labels
- [ ] Error analysis section
- [ ] Experiments table
- [ ] Conclusions section
- [ ] All cells run successfully (Restart & Run All)

---

## Example First Cell

Every notebook should start with:

```python
# Project X: [Project Name]
# Date: [Today's date]
# Goal: [Brief description]

# Imports
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Settings
%matplotlib inline
plt.style.use('seaborn-v0_8')
sns.set_palette("husl")
np.random.seed(42)

# Display settings
pd.set_option('display.max_columns', None)
pd.set_option('display.max_rows', 100)

print("Setup complete!")
```

---

## Organizing Your Work

### During the Project

Keep your notebook messy if needed. Focus on learning.

### After Completing the Project

Clean it up:
1. Remove failed experiments (or move to a separate section)
2. Organize code into logical sections
3. Add clear explanations
4. Make visualizations publication-quality
5. Run "Restart & Run All" to ensure it works

### Create Two Versions (Optional)

- `01_python_ml_foundations_working.ipynb` - Your messy working version
- `01_python_ml_foundations.ipynb` - Clean final version

---

## Jupyter Shortcuts Reminder

| Shortcut | Action |
|----------|--------|
| Shift + Enter | Run cell and move to next |
| Ctrl + Enter | Run cell and stay |
| A | Insert cell above |
| B | Insert cell below |
| M | Convert to Markdown |
| Y | Convert to Code |
| DD | Delete cell |
| Z | Undo delete |
| Ctrl + S | Save |

---

## Common Issues

### "Kernel keeps dying"
- You might be running out of memory
- Try working with smaller datasets
- Restart your computer

### "Variables not defined"
- Make sure you ran all previous cells
- Try "Restart & Run All"

### "Import errors"
- Make sure your virtual environment is activated
- Reinstall the package: `pip install package_name`

---

## Getting Started

1. Launch Jupyter: `jupyter notebook`
2. Click "New" → "Python 3"
3. Rename to `01_python_ml_foundations.ipynb`
4. Start coding!

---

**Happy Learning! 🚀**
