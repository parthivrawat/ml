# Project 1: Python for Machine Learning

## Overview

**Level**: Foundation (Level 0)  
**Prerequisites**: None  
**Estimated Time**: 8-12 hours  
**Notebook**: `01_python_ml_foundations.ipynb`

## Learning Objectives

By the end of this project, you will:

- Master Python data structures (lists, dictionaries, tuples, sets)
- Write functions and use lambda expressions
- Understand list comprehensions and generators
- Handle files and exceptions
- Perform basic data analysis with pure Python
- Understand why NumPy and Pandas are necessary
- Build a foundation for all future ML projects

## Why This Project Matters

Before diving into ML algorithms, you need to be comfortable manipulating data in Python. This project teaches you to think computationally about data problems.

**Key Insight**: You'll start with pure Python to appreciate why specialized libraries exist. Understanding the limitations of basic Python data structures motivates learning NumPy and Pandas.

---

## Project Description

**Build a data-analysis notebook for a fictional e-commerce dataset**

You will analyze customer behavior data using only Python's built-in data structures (no NumPy, no Pandas initially).

### Dataset

Create a small dataset containing:

- `customer_id` (int)
- `age` (int)
- `gender` (str)
- `income` (float)
- `products_viewed` (int)
- `products_purchased` (int)
- `average_order_value` (float)
- `number_of_orders` (int)
- `customer_rating` (float, 1-5)

Start with ~50-100 customers.

---

## Learning Sequence

### Part 1: Python Fundamentals

#### 1.1 Data Structures

Learn by doing:

**Lists**
- Store customer data as lists
- Access elements by index
- Slice data
- Append new customers
- Remove customers

**Dictionaries**
- Represent a single customer as a dictionary
- Access values by key
- Update customer information
- Check if keys exist

**List of Dictionaries**
- Store all customers as a list of dictionaries
- This is your "database"

**Challenge**: Which structure is better for representing tabular data? Why?

#### 1.2 Functions

Write reusable functions:

```python
def calculate_average_age(customers):
    """Calculate the average age of all customers."""
    pass

def filter_by_age(customers, min_age, max_age):
    """Return customers within age range."""
    pass

def sort_by_income(customers, descending=True):
    """Sort customers by income."""
    pass
```

Learn:
- Function parameters
- Return values
- Default arguments
- Docstrings

#### 1.3 Loops and Comprehensions

Compare approaches:

**For Loop**:
```python
high_value_customers = []
for customer in customers:
    if customer['average_order_value'] > 100:
        high_value_customers.append(customer)
```

**List Comprehension**:
```python
high_value_customers = [c for c in customers if c['average_order_value'] > 100]
```

**Lambda + Filter**:
```python
high_value_customers = list(filter(lambda c: c['average_order_value'] > 100, customers))
```

Learn when each approach is appropriate.

#### 1.4 Exception Handling

Handle real-world data issues:

```python
def safe_divide(numerator, denominator):
    """Safely divide, handling division by zero."""
    try:
        return numerator / denominator
    except ZeroDivisionError:
        return None
```

Handle:
- Missing values (None)
- Invalid data types
- Out-of-range values

---

### Part 2: Data Analysis Tasks

#### Task 1: Basic Statistics

Calculate manually (without libraries):

1. **Mean** (average)
2. **Median** (middle value)
3. **Mode** (most common value)
4. **Min/Max**
5. **Range**
6. **Variance**
7. **Standard Deviation**

Implement each from scratch:

```python
def calculate_mean(values):
    """Calculate mean of a list of numbers."""
    if not values:
        return None
    return sum(values) / len(values)

def calculate_median(values):
    """Calculate median of a list of numbers."""
    # Your implementation here
    pass
```

**Challenge**: Why is median sometimes better than mean?

#### Task 2: Data Filtering

Filter customers by various criteria:

1. Age range (e.g., 25-35)
2. Income threshold (e.g., > $50,000)
3. High-value customers (e.g., average_order_value > $100)
4. Active customers (e.g., number_of_orders > 5)
5. Satisfied customers (e.g., rating >= 4.0)

Combine filters:
```python
# Find young, high-income, satisfied customers
def find_target_segment(customers):
    pass
```

#### Task 3: Data Aggregation

Group and aggregate:

1. **Group by gender**: Calculate average income for each gender
2. **Group by age bracket**: Create age groups (18-25, 26-35, 36-45, 46+)
3. **Group by customer tier**: Segment by total spending

Implement:
```python
def group_by_field(customers, field):
    """Group customers by a specific field."""
    groups = {}
    for customer in customers:
        key = customer[field]
        if key not in groups:
            groups[key] = []
        groups[key].append(customer)
    return groups
```

#### Task 4: Data Transformation

Transform the data:

1. **Normalize** income (scale to 0-1)
2. **Calculate** conversion rate (purchased / viewed)
3. **Create** new derived fields
4. **Bin** continuous variables into categories

```python
def normalize(values):
    """Normalize values to 0-1 range."""
    min_val = min(values)
    max_val = max(values)
    return [(v - min_val) / (max_val - min_val) for v in values]
```

#### Task 5: Missing Data

Handle missing values:

1. **Detect** missing values (None, empty strings)
2. **Count** missing values per field
3. **Remove** rows with missing values
4. **Impute** missing values (mean, median, mode)

```python
def handle_missing_values(customers, strategy='remove'):
    """
    Handle missing values.
    
    strategy: 'remove', 'mean', 'median', 'mode'
    """
    pass
```

#### Task 6: Data Validation

Validate data quality:

1. Check for duplicate customer_ids
2. Validate age range (e.g., 18-100)
3. Validate income (positive values)
4. Validate ratings (1-5)
5. Check for logical inconsistencies (e.g., products_purchased > products_viewed)

```python
def validate_customer(customer):
    """Return list of validation errors for a customer."""
    errors = []
    # Your validation logic
    return errors
```

#### Task 7: Reporting

Generate a summary report:

```python
def generate_report(customers):
    """Generate a comprehensive customer analysis report."""
    report = {
        'total_customers': len(customers),
        'average_age': calculate_mean([c['age'] for c in customers]),
        'average_income': calculate_mean([c['income'] for c in customers]),
        'total_revenue': sum([c['average_order_value'] * c['number_of_orders'] for c in customers]),
        # Add more metrics
    }
    return report
```

---

### Part 3: Understanding Limitations

#### Why Pure Python is Insufficient

After completing the analysis, reflect on:

1. **Performance**: How slow is processing 100 customers? What about 1 million?
2. **Code Complexity**: How much code did you write for simple operations?
3. **Error-Prone**: How easy is it to make mistakes with nested loops?
4. **Missing Features**: What operations were difficult or impossible?

#### Introduction to NumPy and Pandas

Now explain conceptually (don't implement yet):

**NumPy**:
- Efficient arrays for numerical data
- Vectorized operations (no loops needed)
- Mathematical functions
- 100x faster than pure Python for numerical operations

**Pandas**:
- DataFrame structure (like Excel tables)
- Built-in functions for common operations
- Easy handling of missing data
- Powerful groupby and aggregation

**Challenge**: Rewrite one of your functions using NumPy/Pandas and compare the code length and readability.

---

## Exercises

### Beginner

1. Add a new field `customer_lifetime_value` calculated as `average_order_value * number_of_orders`
2. Find the top 10 customers by lifetime value
3. Calculate the percentage of customers in each age bracket

### Intermediate

1. Implement a function to detect outliers using the IQR method
2. Create a customer segmentation based on RFM (Recency, Frequency, Monetary)
3. Build a simple recommendation: "Customers who bought X also bought Y"

### Advanced

1. Implement a simple decision rule classifier to predict if a customer will churn
2. Create a cohort analysis showing customer behavior over time
3. Build a data quality dashboard that flags suspicious patterns

---

## Final Challenge

**Independent Analysis**

You receive a new dataset: `employee_data.csv`

Fields:
- employee_id
- department
- years_of_experience
- salary
- performance_rating
- projects_completed
- overtime_hours

**Your Task**:

1. Load and validate the data
2. Perform exploratory analysis
3. Answer business questions:
   - Which department has the highest average salary?
   - Is there a correlation between experience and salary?
   - Which employees are high performers but underpaid?
   - Are employees working overtime more productive?
4. Generate a comprehensive report
5. Make recommendations

**Deliverable**: A complete Python script or notebook with your analysis.

Do NOT look for solutions. Use only what you've learned.

---

## Interview Questions

### Conceptual

1. What is the difference between a list and a tuple?
2. When would you use a dictionary vs. a list?
3. What is the difference between `==` and `is`?
4. What is a list comprehension and when should you use it?
5. What is the difference between `append()` and `extend()`?
6. What is the purpose of `try-except` blocks?
7. What is the difference between a function and a method?
8. What is the difference between `*args` and `**kwargs`?
9. What is a lambda function?
10. What is the difference between shallow copy and deep copy?

### Practical

1. Write a function to find duplicates in a list
2. Write a function to flatten a nested list
3. Write a function to merge two dictionaries
4. Write a function to count word frequency in a text
5. Write a function to remove outliers from a list
6. Write a function to transpose a matrix (list of lists)
7. Write a function to find the most common element
8. Write a function to group items by a key
9. Write a function to calculate moving average
10. Write a function to validate email addresses

### Debugging

1. Why does this fail? `my_list[10]` when `len(my_list) == 5`
2. Why does this fail? `sum([1, 2, '3'])`
3. Why does this give unexpected results? `[1, 2, 3] * 3`
4. Why is this slow? Nested loops over large lists
5. Why does this fail? Modifying a list while iterating over it

---

## Key Takeaways

After completing this project, you should understand:

✅ Python data structures and when to use each  
✅ How to write clean, reusable functions  
✅ How to handle errors and missing data  
✅ How to perform basic data analysis with pure Python  
✅ The limitations of pure Python for data analysis  
✅ Why NumPy and Pandas exist  
✅ How to think computationally about data problems  

---

## Next Project

**Project 2: NumPy from Scratch**

Now that you understand Python fundamentals and the limitations of pure Python for numerical computing, you're ready to learn NumPy—the foundation of all numerical computing in Python.

You'll learn:
- Arrays and vectorization
- Broadcasting
- Matrix operations
- Why NumPy is 100x faster than pure Python
