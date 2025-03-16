# Convert Python Script to EXE (Without Console)

This guide explains how to convert a Python GUI script into a standalone `.exe` file without displaying the console window.

## **Steps to Convert Python to EXE**
### **1. Install PyInstaller**
If you haven't installed PyInstaller yet, run:
```bash
pip install pyinstaller
```

### **2. Navigate to Your Script's Location**
Open **Command Prompt (CMD)** in the directory where your Python script (`your_script.py`) is located.

### **3. Run PyInstaller with Required Options**
Use the following command:
```bash
pyinstaller --onefile --noconsole your_script.py
```
- `--onefile` : Generates a single `.exe` file.  
- `--noconsole` : Hides the console window (for GUI applications).  

### **4. Locate the EXE File**
Once the process completes, the generated `.exe` file will be found in the **`dist/`** folder.

## **Additional Notes**
- If your script uses additional files (like images, config files), you may need to bundle them manually.
- For a custom icon, add `--icon=your_icon.ico` to the command.

---
✅ **Now you can run your Python GUI application as an executable without a console window!** 🚀
