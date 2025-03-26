# How to Use Lambda Functions in Python?

A **lambda function** in Python is an anonymous, single-expression function defined using the `lambda` keyword. It is often used for short, simple operations.

---

## **1. Basic Syntax**
The syntax of a lambda function:
```python
lambda arguments: expression
```
It can take any number of arguments but must have a single expression.

Example:
```python
add = lambda x, y: x + y
print(add(3, 5))  # Output: 8
```

---

## **2. Using Lambda with `map()`**
The `map()` function applies a function to all elements in an iterable.
```python
numbers = [1, 2, 3, 4]
squared = list(map(lambda x: x**2, numbers))
print(squared)  # Output: [1, 4, 9, 16]
```

---

## **3. Using Lambda with `filter()`**
The `filter()` function filters elements based on a condition.
```python
numbers = [1, 2, 3, 4, 5, 6]
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # Output: [2, 4, 6]
```

---

## **4. Using Lambda with `sorted()`**
The `sorted()` function can use a lambda function as a key.
```python
students = [("Alice", 25), ("Bob", 20), ("Charlie", 23)]
sorted_students = sorted(students, key=lambda x: x[1])
print(sorted_students)  # Output: [('Bob', 20), ('Charlie', 23), ('Alice', 25)]
```

---

## **5. Using Lambda with `reduce()`**
The `reduce()` function from `functools` applies a function cumulatively to elements.
```python
from functools import reduce

numbers = [1, 2, 3, 4]
product = reduce(lambda x, y: x * y, numbers)
print(product)  # Output: 24
```

---

## **Conclusion**
- **Lambda functions** are useful for short, throwaway functions.
- They work well with **map()**, **filter()**, **sorted()**, and **reduce()**.
- Use lambdas for concise code, but prefer regular functions for readability in complex cases.

🚀 **Practice using lambda functions to improve your Python skills!**
