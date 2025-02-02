# 🚀 Tech-QuickNotes

**How to install and manage virtual environments in Python**

##### Solution:
A virtual environment allows you to manage dependencies for different Python projects separately. Follow these steps to install and use virtual environments:

1. **Install `venv` (built-in for Python 3.3+):**
   ```sh
   python -m venv myenv
   ```
2. **Activate the virtual environment:**
   - On macOS/Linux:
     ```sh
     source myenv/bin/activate
     ```
   - On Windows:
     ```sh
     myenv\Scripts\activate
     ```
3. **Install packages inside the virtual environment:**
   ```sh
   pip install package_name
   ```
4. **Deactivate the virtual environment:**
   ```sh
   deactivate
   ```
5. **Delete a virtual environment (if needed):**
   ```sh
   rm -rf myenv  # macOS/Linux
   rmdir /s /q myenv  # Windows
   ```

Using virtual environments ensures that dependencies do not conflict across different projects.

---
