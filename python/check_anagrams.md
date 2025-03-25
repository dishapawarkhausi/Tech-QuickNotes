# How to Check if Two Strings are Anagrams in Python?

An anagram is a word or phrase formed by rearranging the letters of another. For example, "listen" and "silent" are anagrams.

---

## **1. Using Sorted Method**
This method sorts both strings and compares them.

```python
def are_anagrams(str1, str2):
    return sorted(str1) == sorted(str2)

# Example usage
print(are_anagrams("listen", "silent"))  # Output: True
print(are_anagrams("hello", "world"))    # Output: False
```

**Time Complexity:** O(n log n) due to sorting.

---

## **2. Using Counter from collections**
This method counts character occurrences and compares them.

```python
from collections import Counter

def are_anagrams(str1, str2):
    return Counter(str1) == Counter(str2)

# Example usage
print(are_anagrams("listen", "silent"))  # Output: True
print(are_anagrams("hello", "world"))    # Output: False
```

**Time Complexity:** O(n), more efficient than sorting.

---

## **3. Without Built-in Functions (Using Dictionary)**
This method manually counts character occurrences.

```python
def are_anagrams(str1, str2):
    if len(str1) != len(str2):
        return False

    char_count = {}

    for char in str1:
        char_count[char] = char_count.get(char, 0) + 1

    for char in str2:
        if char not in char_count or char_count[char] == 0:
            return False
        char_count[char] -= 1

    return True

# Example usage
print(are_anagrams("listen", "silent"))  # Output: True
print(are_anagrams("hello", "world"))    # Output: False
```

**Time Complexity:** O(n), efficient for large strings.

---

## **Conclusion**
- **Sorting method** is simple but slower.
- **Counter method** is efficient and concise.
- **Dictionary method** is efficient without extra imports.

Use the method that best suits your needs! 🚀
