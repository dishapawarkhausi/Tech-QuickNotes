## How to Print Output Without Newline in Python

By default, the `print()` function in Python adds a newline character (`\n`) at the end of the output. However, you can override this behavior using the `end` parameter.

### Solution
To print output without a newline, use:

```python
print("Hello", end=" ")
print("World")
```

### Explanation
- The `end` parameter specifies what should be printed at the end instead of the default newline.
- Setting `end=" "` prints a space instead of a newline, so the next print statement continues on the same line.

### Example Output
```
Hello World
```

### Alternative Solution
You can also use `sys.stdout.write()` for more control:

```python
import sys
sys.stdout.write("Hello ")
sys.stdout.write("World")
```

This method does not add a newline unless explicitly specified.

