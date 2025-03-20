# Checking if a String is a Palindrome

A palindrome is a word, phrase, or sequence that reads the same forward and backward (ignoring spaces, punctuation, and case differences).

## 1. Method 1: Using String Slicing
```python
def is_palindrome(s):
    return s == s[::-1]

# Example usage
string = "madam"
print(is_palindrome(string))  # Output: True
```

## 2. Method 2: Using a Loop
```python
def is_palindrome(s):
    s = s.lower()  # Convert to lowercase for case insensitivity
    length = len(s)
    for i in range(length // 2):
        if s[i] != s[length - i - 1]:
            return False
    return True

# Example usage
string = "Racecar"
print(is_palindrome(string))  # Output: True
```

## 3. Method 3: Using the `reversed()` Function
```python
def is_palindrome(s):
    return list(s) == list(reversed(s))

# Example usage
string = "level"
print(is_palindrome(string))  # Output: True
```

## 4. Method 4: Ignoring Non-Alphanumeric Characters
```python
import re

def is_palindrome(s):
    s = re.sub(r'[^a-zA-Z0-9]', '', s.lower())  # Remove non-alphanumeric characters and convert to lowercase
    return s == s[::-1]

# Example usage
string = "A man, a plan, a canal, Panama!"
print(is_palindrome(string))  # Output: True
```

## Explanation
- **Method 1**: Uses Python slicing to reverse the string and compare it.
- **Method 2**: Iterates over the first half of the string and compares characters.
- **Method 3**: Uses `reversed()` to reverse the string and checks equality.
- **Method 4**: Handles special characters, spaces, and cases.

You can use any of these methods based on your requirements!

