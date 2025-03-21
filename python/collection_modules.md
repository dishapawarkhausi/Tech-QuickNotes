# Working with Python's `collections` Module

The `collections` module in Python provides specialized data structures like named tuples, deques, defaultdicts, and more, which enhance efficiency and readability.

## 1. Importing the `collections` Module
```python
import collections
```

## 2. `namedtuple` (Immutable Lightweight Objects)
```python
from collections import namedtuple

# Define a namedtuple
Point = namedtuple('Point', ['x', 'y'])
p = Point(2, 3)

print(p.x, p.y)  # Output: 2 3
```

## 3. `deque` (Double-Ended Queue for Fast Append/Pop)
```python
from collections import deque

d = deque([1, 2, 3])
d.append(4)       # Append at right
d.appendleft(0)   # Append at left

print(d)  # Output: deque([0, 1, 2, 3, 4])
```

## 4. `defaultdict` (Dictionary with Default Values)
```python
from collections import defaultdict

dd = defaultdict(int)
dd['a'] += 1

print(dd['a'])  # Output: 1
print(dd['b'])  # Output: 0 (default int value)
```

## 5. `Counter` (Counts Elements in an Iterable)
```python
from collections import Counter

c = Counter('mississippi')

print(c)  # Output: Counter({'i': 4, 's': 4, 'p': 2, 'm': 1})
```

## 6. `OrderedDict` (Maintains Order of Keys)
```python
from collections import OrderedDict

od = OrderedDict()
od['a'] = 1
od['b'] = 2
od['c'] = 3

print(od)  # Output: OrderedDict([('a', 1), ('b', 2), ('c', 3)])
```

## 7. `ChainMap` (Combine Multiple Dictionaries)
```python
from collections import ChainMap

d1 = {'a': 1, 'b': 2}
d2 = {'b': 3, 'c': 4}

cm = ChainMap(d1, d2)
print(cm['b'])  # Output: 2 (Takes value from the first dictionary)
```

## Summary
The `collections` module provides efficient alternatives to built-in Python data structures, making code more readable and performant.

