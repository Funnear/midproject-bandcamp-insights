# Developer Setup: Python + Jupyter + XGBoost + Git Submodules

This guide helps you set up a virtual environment with all dependencies—including **XGBoost**—and configure editable submodules (e.g., `data_ravers_utils`) in Jupyter notebooks.

---

## 1. Create and Activate Virtual Environment

### For Mac/Linux

```
python3 -m venv venv
source venv/bin/activate
```

To deactivate:

```
deactivate
```

### For Windows

Replace the `pythonPath` with the full path to your 64-bit Python executable:

```
$pythonPath = "C:\Users\YourUsername\AppData\Local\Programs\Python\Python310\python.exe"
& $pythonPath -m venv C:\path\to\your\env64
```

To activate:

```
venv\Scripts\activate
```

To deactivate:

```
deactivate
```

---

## 2. Mac-only: Fix for XGBoost (libomp)

XGBoost requires `libomp` for parallel computation. Install it globally:

```
brew install libomp
```

Reference: https://openmp.llvm.org/design/Runtimes.html

---

## 3. Install Dependencies

Update pip and install required libraries:

```
pip install --upgrade pip
pip install -r requirements.txt
```

Install internal packages (like local modules or submodules):

```
pip install -e .
```

---

## 4. Enable Jupyter Kernel from This Virtual Environment

Precondition: install `ipykernel` in your requirements first.

```
python -m ipykernel install --user --name=venv --display-name "Python 64 (venv)"
```

Restart VS Code, open a notebook, and:

```
!which python
```

Then select the correct kernel:
- Click “Select Another Kernel”
- Choose “Jupyter Kernel”
- Refresh and select the environment that matches your current `venv`

---

## 5. Use Git Submodules for Internal Libraries

### Add Submodule

```
git submodule add https://github.com/YourUsername/data_ravers_utils.git libs/data_ravers_utils
git submodule update --init --recursive
```

### Install Submodule as Editable Package

```
pip install -e ./libs/data_ravers_utils
```

### Import Inside Jupyter Notebook

```
import sys, os

# Append submodule path
module_path = os.path.abspath("./libs")
if module_path not in sys.path:
    sys.path.append(module_path)

# Example import
from data_ravers_utils.module_name import some_function
```

---

## 6. Updating or Removing Submodules

### Update

```
git submodule update --remote --merge
```

### Remove

```
git rm --cached libs/data_ravers_utils
rm -rf .git/modules/libs/data_ravers_utils
git commit -m "Removed submodule"
```

---

## 7. Recommended `requirements.txt` Example

```
# Jupyter & Notebooks
jupyterlab>=4.3.5
ipykernel>=6.29.5

# Data Analysis & Machine Learning
numpy>=2.1
pandas>=2.2.2
scikit-learn>=1.6.1
statsmodels>=0.14.4

# Visualization
matplotlib>=3.9.2
seaborn>=0.13.2

# APIs
kagglehub>=0.3.10
```