# Evaluating Model Performance: Accuracy, Precision, and Recall

When evaluating a machine learning model, we use various metrics to measure its performance. Three key metrics are:

- **Accuracy**: The overall correctness of the model.
- **Precision**: The ability to correctly predict positive instances.
- **Recall**: The ability to find all actual positive instances.

## 1. Accuracy
Accuracy is the ratio of correctly predicted instances to the total instances.

\[ Accuracy = \frac{TP + TN}{TP + TN + FP + FN} \]

Where:
- **TP** (True Positives): Correctly predicted positive cases.
- **TN** (True Negatives): Correctly predicted negative cases.
- **FP** (False Positives): Incorrectly predicted positive cases.
- **FN** (False Negatives): Incorrectly predicted negative cases.

## 2. Precision
Precision (also called Positive Predictive Value) is the ratio of correctly predicted positive cases to all predicted positive cases.

\[ Precision = \frac{TP}{TP + FP} \]

Higher precision means fewer false positives.

## 3. Recall
Recall (also called Sensitivity) is the ratio of correctly predicted positive cases to all actual positive cases.

\[ Recall = \frac{TP}{TP + FN} \]

Higher recall means fewer false negatives.

## 4. Example Calculation in Python
Below is a Python example to compute accuracy, precision, and recall using `sklearn.metrics`:

```python
from sklearn.metrics import accuracy_score, precision_score, recall_score

# Example true labels and predicted labels
y_true = [1, 0, 1, 1, 0, 1, 0, 0, 1, 0]  # Actual values
y_pred = [1, 0, 1, 0, 0, 1, 1, 0, 1, 0]  # Predicted values

# Compute metrics
accuracy = accuracy_score(y_true, y_pred)
precision = precision_score(y_true, y_pred)
recall = recall_score(y_true, y_pred)

# Print results
print(f'Accuracy: {accuracy:.2f}')
print(f'Precision: {precision:.2f}')
print(f'Recall: {recall:.2f}')
```

## 5. Choosing the Right Metric
- Use **accuracy** when classes are balanced.
- Use **precision** when false positives are costly (e.g., spam detection).
- Use **recall** when missing a positive case is critical (e.g., medical diagnosis).

By evaluating these metrics, you can better assess your model’s performance and make improvements accordingly.
