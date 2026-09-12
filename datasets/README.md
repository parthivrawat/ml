# Datasets

This folder contains the datasets used by the machine learning curriculum.

All files are plain CSV and can be loaded with Python's built-in `csv` module,
Pandas, NumPy, or any other tool you prefer.

## File Overview

| File | Rows | Purpose | Project |
|------|------|---------|---------|
| `ecommerce_customers.csv` | 101 | Fictional e-commerce customer data with missing values and one duplicate | 01: Python for ML |
| `employees.csv` | 200 | Employee records with missing and invalid values for the Project 1 final challenge | 01: Python for ML |
| `iris.csv` | 150 | Classic iris flower measurements by species | 02: NumPy from Scratch |
| `customer_behavior.csv` | 200 | Customer data with missing values and outliers for EDA | 03: Statistics & EDA |
| `house_prices.csv` | 150 | Synthetic house data for linear regression | 04: Linear Regression |

## Column Details

### `ecommerce_customers.csv`

- `customer_id` - unique customer identifier
- `age` - customer age in years
- `gender` - 'M' or 'F'
- `income` - annual income in US dollars
- `products_viewed` - number of products the customer viewed
- `products_purchased` - number of products purchased
- `average_order_value` - average value of each order
- `number_of_orders` - total number of orders placed
- `customer_rating` - satisfaction rating from 1 to 5

Notes:
- Some rows have missing `income` or `customer_rating` values for the missing-data exercises.
- Customer `50` appears twice so you can practice duplicate detection.
- One row has `products_purchased` greater than `products_viewed` for validation practice.

### `employees.csv`

- `employee_id` - unique employee identifier
- `department` - department name
- `years_of_experience` - years of professional experience
- `salary` - annual salary in US dollars
- `performance_rating` - performance score from 1 to 5
- `projects_completed` - number of completed projects
- `overtime_hours` - total overtime hours

Notes:
- Several `salary` values are missing for missing-data practice.
- A few rows contain invalid values (negative salary, rating above 5) for validation practice.

### `iris.csv`

- `sepal_length` - sepal length in cm
- `sepal_width` - sepal width in cm
- `petal_length` - petal length in cm
- `petal_width` - petal width in cm
- `species` - iris species (setosa, versicolor, virginica)

This is the classic iris dataset used as a simple classification benchmark.

### `customer_behavior.csv`

- `customer_id` - unique customer identifier
- `age` - customer age in years
- `income` - annual income in US dollars
- `spend_score` - spending score from 0 to 100
- `satisfaction` - satisfaction score from 1 to 5
- `purchase_freq` - number of purchases in a period
- `gender` - 'M' or 'F'

Notes:
- `income` has missing values and extreme outliers for EDA practice.
- The variables were generated with realistic correlations so you can explore relationships.

### `house_prices.csv`

- `size` - house size in square feet
- `bedrooms` - number of bedrooms
- `age` - house age in years
- `distance` - distance from city center in miles
- `price` - house price in US dollars

The price depends on the features with added noise, making it suitable for linear regression practice.

## Reproducibility

The synthetic datasets were generated with a fixed random seed (`seed=42`) so the same values are produced on every run. The `iris.csv` file is a copy of the well-known iris dataset.

## Usage

```python
import pandas as pd

customers = pd.read_csv('datasets/ecommerce_customers.csv')
iris = pd.read_csv('datasets/iris.csv')
```
