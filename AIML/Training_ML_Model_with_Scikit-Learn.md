# Training a Simple Machine Learning Model using Scikit-Learn

## 1. **Install Scikit-Learn**
```bash
pip install scikit-learn
```

## 2. **Import Necessary Libraries**
```python
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
```

## 3. **Load or Create a Dataset**
```python
data = {
    'Experience': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Salary': [30000, 35000, 40000, 45000, 50000, 55000, 60000, 65000, 70000, 75000]
}
df = pd.DataFrame(data)
```

## 4. **Prepare Data**
```python
X = df[['Experience']]
y = df['Salary']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

## 5. **Train a Machine Learning Model**
```python
model = LinearRegression()
model.fit(X_train, y_train)
```

## 6. **Make Predictions**
```python
y_pred = model.predict(X_test)
```

## 7. **Evaluate the Model**
```python
mse = mean_squared_error(y_test, y_pred)
print("Mean Squared Error:", mse)
```

## 8. **Use the Model for Prediction**
```python
new_experience = np.array([[12]])  # Predict salary for 12 years of experience
predicted_salary = model.predict(new_experience)
print("Predicted Salary:", predicted_salary[0])
```

---
This guide covers the essential steps to train a simple machine learning model using Scikit-Learn. 🚀
