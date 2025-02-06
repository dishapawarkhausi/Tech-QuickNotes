# 🚀 Tech-QuickNotes

**How to read large CSV files efficiently in Pandas**

##### Solution:
Reading large CSV files in Pandas can be memory-intensive. Here are some efficient ways to handle large files:

1. **Read in chunks:**
   ```python
   import pandas as pd

   chunk_size = 10000  # Adjust based on your memory limits
   for chunk in pd.read_csv('large_file.csv', chunksize=chunk_size):
       process(chunk)  # Replace with your processing function
   ```

2. **Use `usecols` to read only necessary columns:**
   ```python
   df = pd.read_csv('large_file.csv', usecols=['col1', 'col2'])
   ```

3. **Specify data types to reduce memory usage:**
   ```python
   df = pd.read_csv('large_file.csv', dtype={'col1': 'int32', 'col2': 'float32'})
   ```

4. **Use `low_memory=False` to optimize memory handling:**
   ```python
   df = pd.read_csv('large_file.csv', low_memory=False)
   ```

5. **Use Dask for parallel processing:**
   ```python
   import dask.dataframe as dd
   df = dd.read_csv('large_file.csv')
   ```

These methods help optimize memory usage and improve performance while handling large datasets.

---
