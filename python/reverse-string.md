# Reverse a String in Python

## Problem Statement
Write a Python function to reverse a given string using a `for` loop with `range()`.

## Solution
Here is the Python code to reverse a string logically using a `for` loop:

```python
# Function to reverse a string using for loop with range
def reverse_string(s):
    reversed_str = ""
    for i in range(len(s) - 1, -1, -1):  # Loop from last index to 0
        reversed_str += s[i]  # Append characters in reverse order
    return reversed_str

# Example usage
string = "Hello, World!"
reversed_string = reverse_string(string)
print(reversed_string)
```

## Explanation
1. We define a function `reverse_string(s)` that takes a string `s` as input.
2. We initialize an empty string `reversed_str` to store the reversed result.
3. Using a `for` loop with `range(len(s) - 1, -1, -1)`, we iterate from the last index to the first.
4. We append each character in reverse order to `reversed_str`.
5. Finally, we return the reversed string.

## Output
```
!dlroW ,olleH
```

## Complexity Analysis
- **Time Complexity:** O(n), where `n` is the length of the string (since we iterate through all characters once).
- **Space Complexity:** O(n), as we store the reversed string separately.

## Alternative Methods
1. **Using Slicing:** `s[::-1]`
2. **Using `reversed()` and `join()`:** `''.join(reversed(s))`

This method provides a step-by-step logical approach to string reversal. 🚀
