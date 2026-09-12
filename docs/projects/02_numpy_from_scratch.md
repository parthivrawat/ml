# Project 2: NumPy from Scratch

## Overview

**Level**: Foundation (Level 0)  
**Prerequisites**: Project 1 (Python for ML)  
**Estimated Time**: 10-15 hours  
**Notebook**: `02_numpy_from_scratch.ipynb`

## Learning Objectives

By the end of this project, you will:

- Understand NumPy arrays and why they're faster than Python lists
- Master array indexing, slicing, and reshaping
- Understand broadcasting and vectorization
- Perform matrix operations essential for ML
- Implement ML-relevant operations (distance, normalization, etc.)
- Build intuition for how ML algorithms use linear algebra

## Why This Project Matters

**NumPy is the foundation of all ML in Python.** Every ML library (scikit-learn, TensorFlow, PyTorch) is built on NumPy concepts.

Understanding NumPy deeply means understanding:
- How ML algorithms actually compute
- Why certain operations are fast or slow
- How to write efficient ML code
- The mathematical operations behind ML

---

## Project Description

**Build a Numerical Data Processing Engine**

You will learn NumPy through a machine-learning-oriented project where you:

1. Compare Python lists vs. NumPy arrays
2. Implement ML operations from scratch
3. Build a linear algebra toolkit
4. Prepare feature matrices like in real ML

---

## Learning Sequence

### Part 1: Why NumPy?

#### 1.1 The Performance Problem

**Experiment 1**: Compare Python lists vs. NumPy arrays

```python
import time
import numpy as np

# Python lists
python_list = list(range(1000000))
start = time.time()
result = [x * 2 for x in python_list]
python_time = time.time() - start

# NumPy arrays
numpy_array = np.arange(1000000)
start = time.time()
result = numpy_array * 2
numpy_time = time.time() - start

print(f"Python: {python_time:.4f}s")
print(f"NumPy: {numpy_time:.4f}s")
print(f"Speedup: {python_time / numpy_time:.1f}x")
```

**Questions**:
- Why is NumPy faster?
- When would you still use Python lists?

#### 1.2 Memory Efficiency

Compare memory usage:

```python
import sys

python_list = list(range(1000))
numpy_array = np.arange(1000)

print(f"Python list: {sys.getsizeof(python_list)} bytes")
print(f"NumPy array: {numpy_array.nbytes} bytes")
```

**Key Insight**: NumPy arrays are:
- Stored contiguously in memory
- Homogeneous (same data type)
- Optimized for numerical operations
- Written in C (fast)

---

### Part 2: NumPy Fundamentals

#### 2.1 Creating Arrays

Learn different ways to create arrays:

```python
# From Python lists
arr1 = np.array([1, 2, 3, 4, 5])

# Using NumPy functions
arr2 = np.arange(0, 10, 2)        # [0, 2, 4, 6, 8]
arr3 = np.linspace(0, 1, 5)       # [0, 0.25, 0.5, 0.75, 1]
arr4 = np.zeros((3, 4))           # 3x4 matrix of zeros
arr5 = np.ones((2, 3))            # 2x3 matrix of ones
arr6 = np.eye(3)                  # 3x3 identity matrix
arr7 = np.random.rand(3, 3)       # 3x3 random values [0, 1)
arr8 = np.random.randn(3, 3)      # 3x3 random normal distribution
```

**Exercise**: Create arrays for:
- 100 evenly spaced points between 0 and 2π
- A 5x5 matrix with random integers between 1 and 100
- A 3x3 matrix with 1s on the diagonal and 0s elsewhere

#### 2.2 Array Attributes

Understand array properties:

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

print(arr.shape)      # (2, 3) - dimensions
print(arr.ndim)       # 2 - number of dimensions
print(arr.size)       # 6 - total number of elements
print(arr.dtype)      # int64 - data type
print(arr.itemsize)   # 8 - bytes per element
print(arr.nbytes)     # 48 - total bytes
```

**Key Concept**: Shape is crucial in ML. A shape mismatch is the most common error.

#### 2.3 Data Types

Learn about dtypes:

```python
# Different data types
int_arr = np.array([1, 2, 3], dtype=np.int32)
float_arr = np.array([1, 2, 3], dtype=np.float64)
bool_arr = np.array([True, False, True], dtype=np.bool_)

# Type conversion
float_arr = int_arr.astype(np.float64)
```

**ML Relevance**: 
- Features are usually `float64`
- Labels might be `int32` (classification) or `float64` (regression)
- Memory matters for large datasets

#### 2.4 Indexing and Slicing

Master array access:

```python
arr = np.array([[1, 2, 3, 4],
                [5, 6, 7, 8],
                [9, 10, 11, 12]])

# Basic indexing
arr[0, 0]           # 1 - element at row 0, col 0
arr[1, 2]           # 7 - element at row 1, col 2

# Slicing
arr[0, :]           # [1, 2, 3, 4] - first row
arr[:, 0]           # [1, 5, 9] - first column
arr[0:2, 1:3]       # [[2, 3], [6, 7]] - submatrix

# Boolean indexing
arr[arr > 5]        # [6, 7, 8, 9, 10, 11, 12]

# Fancy indexing
arr[[0, 2], [1, 3]] # [2, 12] - elements at (0,1) and (2,3)
```

**ML Application**: 
- Select specific samples: `X[indices]`
- Select specific features: `X[:, feature_indices]`
- Filter data: `X[y == 1]` (all samples where label is 1)

#### 2.5 Reshaping

Change array dimensions:

```python
arr = np.arange(12)                    # [0, 1, 2, ..., 11]

arr.reshape(3, 4)                      # 3x4 matrix
arr.reshape(4, 3)                      # 4x3 matrix
arr.reshape(2, 2, 3)                   # 2x2x3 tensor
arr.reshape(-1, 1)                     # Column vector (12, 1)
arr.reshape(1, -1)                     # Row vector (1, 12)

# Flatten
arr.flatten()                          # 1D array
arr.ravel()                            # 1D array (view, not copy)

# Transpose
arr.reshape(3, 4).T                    # Transpose
```

**ML Relevance**: 
- Reshape features: `X.reshape(-1, 1)` for single feature
- Flatten images: `image.reshape(-1)` for ML input
- Transpose: `X.T` for matrix operations

---

### Part 3: Vectorization

#### 3.1 Element-wise Operations

Compare loop vs. vectorized:

**With Loops (Slow)**:
```python
result = []
for x in arr:
    result.append(x ** 2)
```

**Vectorized (Fast)**:
```python
result = arr ** 2
```

Operations:
```python
arr + 5              # Add 5 to every element
arr * 2              # Multiply every element by 2
arr ** 2             # Square every element
np.sqrt(arr)         # Square root
np.exp(arr)          # Exponential
np.log(arr)          # Natural log
np.sin(arr)          # Sine
```

**Exercise**: Implement the sigmoid function:
```python
def sigmoid(x):
    """Sigmoid activation function."""
    return 1 / (1 + np.exp(-x))
```

#### 3.2 Broadcasting

Understand how NumPy handles different shapes:

```python
# Scalar broadcasting
arr = np.array([[1, 2, 3],
                [4, 5, 6]])
arr + 10  # Adds 10 to every element

# Vector broadcasting
arr + np.array([10, 20, 30])  # Adds [10, 20, 30] to each row

# Broadcasting rules
# Shape (3, 4) + Shape (4,)   → OK (broadcasts to (3, 4))
# Shape (3, 4) + Shape (3, 1) → OK (broadcasts to (3, 4))
# Shape (3, 4) + Shape (3,)   → ERROR (incompatible)
```

**ML Application**: Feature normalization
```python
# Normalize features (mean=0, std=1)
X_normalized = (X - X.mean(axis=0)) / X.std(axis=0)
```

---

### Part 4: Aggregations

#### 4.1 Basic Aggregations

```python
arr = np.array([[1, 2, 3],
                [4, 5, 6]])

# Aggregate over entire array
arr.sum()           # 21
arr.mean()          # 3.5
arr.std()           # 1.707...
arr.min()           # 1
arr.max()           # 6

# Aggregate over axis
arr.sum(axis=0)     # [5, 7, 9] - sum each column
arr.sum(axis=1)     # [6, 15] - sum each row
arr.mean(axis=0)    # [2.5, 3.5, 4.5] - mean of each column
```

**Key Concept**: 
- `axis=0`: operate down the rows (result has shape of columns)
- `axis=1`: operate across the columns (result has shape of rows)

**ML Application**:
```python
# Feature-wise statistics
feature_means = X.mean(axis=0)      # Mean of each feature
feature_stds = X.std(axis=0)        # Std of each feature

# Sample-wise statistics
sample_means = X.mean(axis=1)       # Mean of each sample
```

#### 4.2 Other Useful Aggregations

```python
np.median(arr)
np.percentile(arr, 75)    # 75th percentile
np.argmin(arr)            # Index of minimum
np.argmax(arr)            # Index of maximum
np.unique(arr)            # Unique values
np.bincount(arr)          # Count occurrences (for integers)
```

---

### Part 5: Linear Algebra for ML

#### 5.1 Dot Product

**Mathematical Definition**:
```
a · b = a₁b₁ + a₂b₂ + ... + aₙbₙ
```

**Implementation**:
```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# Three ways to compute dot product
result1 = np.dot(a, b)           # 32
result2 = a @ b                  # 32 (Python 3.5+)
result3 = (a * b).sum()          # 32 (element-wise then sum)
```

**ML Application**: Similarity between vectors
```python
def cosine_similarity(a, b):
    """Compute cosine similarity between two vectors."""
    return np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))
```

#### 5.2 Matrix Multiplication

**Mathematical Definition**:
```
C[i,j] = Σ A[i,k] * B[k,j]
```

**Implementation**:
```python
A = np.array([[1, 2],
              [3, 4]])
B = np.array([[5, 6],
              [7, 8]])

C = A @ B  # [[19, 22], [43, 50]]
```

**ML Application**: Linear regression prediction
```python
# X: (n_samples, n_features)
# w: (n_features, 1)
# y_pred: (n_samples, 1)
y_pred = X @ w
```

**Exercise**: Implement matrix multiplication from scratch using loops, then compare with `@`.

#### 5.3 Euclidean Distance

**Mathematical Definition**:
```
d(a, b) = √[(a₁-b₁)² + (a₂-b₂)² + ... + (aₙ-bₙ)²]
```

**Implementation**:
```python
def euclidean_distance(a, b):
    """Compute Euclidean distance between two vectors."""
    return np.sqrt(np.sum((a - b) ** 2))

# Or using NumPy
def euclidean_distance(a, b):
    return np.linalg.norm(a - b)
```

**ML Application**: k-Nearest Neighbors
```python
def find_nearest_neighbor(X, query_point):
    """Find the nearest neighbor to query_point in X."""
    distances = np.linalg.norm(X - query_point, axis=1)
    return np.argmin(distances)
```

#### 5.4 Matrix Operations

```python
A = np.array([[1, 2],
              [3, 4]])

# Transpose
A.T                      # [[1, 3], [2, 4]]

# Inverse
np.linalg.inv(A)         # Inverse matrix

# Determinant
np.linalg.det(A)         # -2.0

# Eigenvalues and eigenvectors
eigenvalues, eigenvectors = np.linalg.eig(A)

# Solve linear system Ax = b
b = np.array([5, 11])
x = np.linalg.solve(A, b)  # x = [1, 2]
```

**ML Application**: Linear regression closed-form solution
```python
def linear_regression_closed_form(X, y):
    """
    Solve linear regression using normal equation.
    w = (X^T X)^(-1) X^T y
    """
    return np.linalg.inv(X.T @ X) @ X.T @ y
```

---

### Part 6: ML-Relevant Operations

#### 6.1 Normalization

**Min-Max Normalization** (scale to [0, 1]):
```python
def min_max_normalize(X):
    """Normalize features to [0, 1] range."""
    X_min = X.min(axis=0)
    X_max = X.max(axis=0)
    return (X - X_min) / (X_max - X_min)
```

**Standardization** (mean=0, std=1):
```python
def standardize(X):
    """Standardize features to mean=0, std=1."""
    mean = X.mean(axis=0)
    std = X.std(axis=0)
    return (X - mean) / std
```

**Exercise**: Apply both to a sample dataset and visualize the distributions.

#### 6.2 Distance Metrics

Implement multiple distance metrics:

```python
def manhattan_distance(a, b):
    """L1 distance."""
    return np.sum(np.abs(a - b))

def euclidean_distance(a, b):
    """L2 distance."""
    return np.sqrt(np.sum((a - b) ** 2))

def chebyshev_distance(a, b):
    """L-infinity distance."""
    return np.max(np.abs(a - b))
```

**ML Application**: Different distance metrics for k-NN.

#### 6.3 Pairwise Distances

Compute distances between all pairs:

```python
def pairwise_distances(X):
    """
    Compute pairwise Euclidean distances.
    
    X: (n_samples, n_features)
    Returns: (n_samples, n_samples) distance matrix
    """
    n = X.shape[0]
    distances = np.zeros((n, n))
    for i in range(n):
        for j in range(n):
            distances[i, j] = np.linalg.norm(X[i] - X[j])
    return distances
```

**Vectorized Version** (much faster):
```python
def pairwise_distances_vectorized(X):
    """Vectorized pairwise distances using broadcasting."""
    # X: (n, d)
    # X[:, np.newaxis, :]: (n, 1, d)
    # X[np.newaxis, :, :]: (1, n, d)
    # Difference: (n, n, d)
    diff = X[:, np.newaxis, :] - X[np.newaxis, :, :]
    return np.sqrt(np.sum(diff ** 2, axis=2))
```

**Exercise**: Compare the speed of both implementations.

#### 6.4 One-Hot Encoding

Convert categorical labels to binary vectors:

```python
def one_hot_encode(y, num_classes):
    """
    One-hot encode labels.
    
    y: (n_samples,) with values 0 to num_classes-1
    Returns: (n_samples, num_classes)
    """
    n = len(y)
    one_hot = np.zeros((n, num_classes))
    one_hot[np.arange(n), y] = 1
    return one_hot

# Example
y = np.array([0, 1, 2, 1, 0])
one_hot = one_hot_encode(y, 3)
# [[1, 0, 0],
#  [0, 1, 0],
#  [0, 0, 1],
#  [0, 1, 0],
#  [1, 0, 0]]
```

---

### Part 7: Building a Linear Algebra Toolkit

Create a module with ML-relevant functions:

```python
class MLToolkit:
    """A collection of ML utility functions using NumPy."""
    
    @staticmethod
    def normalize(X, method='minmax'):
        """Normalize features."""
        pass
    
    @staticmethod
    def train_test_split(X, y, test_size=0.2, random_state=None):
        """Split data into train and test sets."""
        pass
    
    @staticmethod
    def add_intercept(X):
        """Add intercept term (column of 1s) to X."""
        pass
    
    @staticmethod
    def compute_accuracy(y_true, y_pred):
        """Compute classification accuracy."""
        pass
    
    @staticmethod
    def compute_mse(y_true, y_pred):
        """Compute mean squared error."""
        pass
```

**Exercise**: Implement all methods.

---

## Exercises

### Beginner

1. Create a 10x10 matrix with random values and find the min/max of each row
2. Normalize a random array to have mean=0 and std=1
3. Create a function to compute the correlation between two arrays
4. Implement a function to shuffle rows of a matrix

### Intermediate

1. Implement k-means clustering initialization (random centroids)
2. Compute the covariance matrix of a dataset
3. Implement PCA projection (project data onto first k principal components)
4. Create a function to generate polynomial features (x, x², x³, ...)

### Advanced

1. Implement batch matrix multiplication for neural networks
2. Implement gradient descent for linear regression using only NumPy
3. Create a function to compute confusion matrix from predictions
4. Implement cross-validation splits (k-fold)

---

## Final Challenge

**Build a k-Nearest Neighbors Classifier from Scratch**

Using only NumPy, implement:

```python
class KNNClassifier:
    def __init__(self, k=3):
        self.k = k
    
    def fit(self, X, y):
        """Store training data."""
        pass
    
    def predict(self, X):
        """Predict labels for X."""
        pass
    
    def score(self, X, y):
        """Compute accuracy."""
        pass
```

Test it on a simple dataset (e.g., Iris dataset loaded manually).

**Requirements**:
- Use vectorized operations (no Python loops for distance computation)
- Handle multiple test samples efficiently
- Achieve >90% accuracy on Iris dataset

---

## Interview Questions

### Conceptual

1. Why is NumPy faster than Python lists?
2. What is broadcasting and when is it useful?
3. What is the difference between `arr.flatten()` and `arr.ravel()`?
4. What does `axis=0` vs `axis=1` mean?
5. What is the difference between `np.dot()` and `*`?
6. What is vectorization and why does it matter?
7. What is the difference between a view and a copy?
8. When would you use `np.where()`?
9. What is the difference between `np.array()` and `np.asarray()`?
10. What are the broadcasting rules?

### Practical

1. Write a function to compute pairwise cosine similarity
2. Implement softmax function
3. Implement ReLU activation function
4. Write a function to compute confusion matrix
5. Implement batch normalization
6. Write a function to shuffle data while keeping X and y aligned
7. Implement stratified sampling
8. Write a function to compute ROC curve points
9. Implement moving average
10. Write a function to detect outliers using z-score

---

## Key Takeaways

After completing this project, you should understand:

✅ Why NumPy is essential for ML  
✅ How to manipulate arrays efficiently  
✅ Broadcasting and vectorization  
✅ Matrix operations for ML  
✅ How to implement ML operations from scratch  
✅ The mathematical foundations of ML algorithms  

---

## Next Project

**Project 3: Pandas for Data Analysis**

Now that you understand numerical computing with NumPy, you'll learn Pandas for working with structured, tabular data—the most common format in real-world ML projects.
