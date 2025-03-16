# Evaluating Model Performance: Accuracy, Precision, and Recall

## Problem Statement
Evaluating a machine learning model is essential to ensure its effectiveness. Three key metrics used for classification models are:
- **Accuracy**: Measures overall correctness.
- **Precision**: Measures how many predicted positives are actually positive.
- **Recall**: Measures how many actual positives were correctly predicted.

## Solution
We can use the `accuracy_score`, `precision_score`, and `recall_score` functions from `sklearn.metrics` to evaluate the model.

### Steps to Evaluate Model Performance
1. Import the necessary libraries.
2. Generate or load a dataset.
3. Train a classification model.
4. Make predictions.
5. Calculate accuracy, precision, and recall.

### Implementation in Python
```python
# Import necessary libraries
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, precision_score, recall_score
from sklearn.ensemble import RandomForestClassifier
import numpy as np

# Sample dataset
X = np.array([[1, 2], [3, 4], [5, 6], [7, 8], [9, 10], [11, 12]])  # Features
y = np.array([0, 1, 0, 1, 0, 1])  # Labels

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train a model
model = RandomForestClassifier()
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Evaluate performance
accuracy = accuracy_score(y_test, y_pred)
precision = precision_score(y_test, y_pred)
recall = recall_score(y_test, y_pred)

# Display the results
print(f"Accuracy: {accuracy:.2f}")
print(f"Precision: {precision:.2f}")
print(f"Recall: {recall:.2f}")
```

### Explanation
- **Accuracy** = (True Positives + True Negatives) / Total Samples
- **Precision** = True Positives / (True Positives + False Positives)
- **Recall** = True Positives / (True Positives + False Negatives)

## Conclusion
Evaluating a model using accuracy, precision, and recall helps in understanding its performance. Depending on the problem, different metrics may be prioritized. For example, in medical diagnosis, recall is more critical to minimize false negatives.

