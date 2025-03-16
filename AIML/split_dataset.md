# Splitting a Dataset into Training and Testing Sets

## Problem Statement
When working with machine learning models, it is essential to split the dataset into training and testing sets. This ensures that the model can be trained on one portion of the data and evaluated on another to check its performance.

## Solution
To split a dataset into training and testing sets in Python, you can use the `train_test_split` function from the `sklearn.model_selection` module.

### Steps to Split the Dataset
1. Import the necessary libraries.
2. Load or create the dataset.
3. Use `train_test_split` to divide the dataset.
4. Verify the split.

### Implementation in Python
```python
# Import necessary libraries
from sklearn.model_selection import train_test_split
import numpy as np

# Sample dataset
X = np.array([[1, 2], [3, 4], [5, 6], [7, 8], [9, 10], [11, 12]])  # Features
y = np.array([0, 1, 0, 1, 0, 1])  # Labels

# Split the dataset (80% training, 20% testing)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Display the results
print("Training Features:", X_train)
print("Testing Features:", X_test)
print("Training Labels:", y_train)
print("Testing Labels:", y_test)
```

### Explanation
- `test_size=0.2`: Allocates 20% of the data to testing and 80% to training.
- `random_state=42`: Ensures reproducibility.
- `X_train, X_test, y_train, y_test`: The resulting split data.

## Conclusion
Splitting the dataset is a crucial step in machine learning to evaluate model performance effectively. Using `train_test_split` simplifies this process in Python.
