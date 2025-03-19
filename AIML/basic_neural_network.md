# Implementing a Basic Neural Network Using TensorFlow/Keras

Neural networks are the backbone of deep learning. TensorFlow and Keras provide a simple way to build and train them.

## 1. Install Required Libraries
Ensure you have TensorFlow installed:
```bash
pip install tensorflow
```

## 2. Import Required Libraries
```python
import tensorflow as tf
from tensorflow import keras
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense
import numpy as np
```

## 3. Prepare Dataset (Example: XOR Problem)
```python
# Sample input data (XOR problem)
X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]])
y = np.array([[0], [1], [1], [0]])
```

## 4. Build the Neural Network Model
```python
# Define the model
model = Sequential([
    Dense(4, activation='relu', input_shape=(2,)),  # Hidden layer with 4 neurons
    Dense(1, activation='sigmoid')  # Output layer with 1 neuron
])

# Compile the model
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])

# Print model summary
model.summary()
```

## 5. Train the Model
```python
# Train the model
model.fit(X, y, epochs=100, verbose=1)
```

## 6. Make Predictions
```python
# Make predictions
predictions = model.predict(X)
print("Predictions:")
print(predictions)
```

## 7. Explanation
- **Dense Layers**: Each layer consists of neurons that apply weights and activation functions.
- **ReLU Activation**: Used in the hidden layer for better learning.
- **Sigmoid Activation**: Used in the output layer for binary classification.
- **Adam Optimizer**: An adaptive learning rate optimization algorithm.
- **Binary Crossentropy**: Suitable for binary classification problems.

This basic neural network can be expanded for more complex tasks like image classification and natural language processing.

