## How to Swap Two Variables Without Using a Temporary Variable

Swapping two variables without using a temporary variable is possible in Python using different techniques.

### Solution 1: Using Tuple Unpacking
```python
a = 5
b = 10

a, b = b, a
print("a:", a, "b:", b)
```
**Output:**
```
a: 10 b: 5
```
**Explanation:** Python allows multiple assignments in one line using tuple unpacking.

---

### Solution 2: Using Arithmetic Operations
#### Using Addition and Subtraction
```python
a = 5
b = 10

a = a + b  # a becomes 15
b = a - b  # b becomes 5
a = a - b  # a becomes 10

print("a:", a, "b:", b)
```

#### Using Multiplication and Division (Avoid if `b` is 0)
```python
a = 5
b = 10

a = a * b  # a becomes 50
b = a // b  # b becomes 5
a = a // b  # a becomes 10

print("a:", a, "b:", b)
```

These methods swap values without requiring extra space.

