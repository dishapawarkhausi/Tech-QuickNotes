# Saving and Loading a Trained Machine Learning Model

After training a machine learning model, it is essential to save it for future use and load it whenever needed without retraining.

## 1. Why Save a Model?
- Avoid retraining the model every time.
- Deploy the trained model in applications.
- Share the model with others.

## 2. Methods to Save and Load Models

### Method 1: Using Joblib (Recommended for Large Models)
**Saving the model:**
```python
import joblib

# Save the trained model
joblib.dump(model, 'model.joblib')
```

**Loading the model:**
```python
# Load the saved model
loaded_model = joblib.load('model.joblib')

# Use the loaded model for prediction
predictions = loaded_model.predict(X_test)
```

### Method 2: Using Pickle (General Purpose)
**Saving the model:**
```python
import pickle

# Save the trained model
with open('model.pkl', 'wb') as file:
    pickle.dump(model, file)
```

**Loading the model:**
```python
# Load the saved model
with open('model.pkl', 'rb') as file:
    loaded_model = pickle.load(file)

# Use the loaded model for prediction
predictions = loaded_model.predict(X_test)
```

### Method 3: Using TensorFlow/Keras (For Deep Learning Models)
**Saving the model:**
```python
# Save the Keras model
model.save('model.h5')
```

**Loading the model:**
```python
from tensorflow.keras.models import load_model

# Load the saved model
loaded_model = load_model('model.h5')

# Use the loaded model for prediction
predictions = loaded_model.predict(X_test)
```

## 3. Choosing the Right Saving Method
- Use **Joblib** for large models (faster than Pickle for NumPy arrays).
- Use **Pickle** for general-purpose model saving.
- Use **TensorFlow/Keras** for deep learning models.

Saving and loading models helps in efficient ML model deployment and reuse without retraining.
