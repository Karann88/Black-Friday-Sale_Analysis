# Black Friday Sale — EDA & Analysis

This repository contains a Jupyter-based exploratory analysis of a Black Friday retail dataset (`BlackFriday.csv`). The notebook performs data cleaning, exploratory data analysis (EDA), and visualizations to understand purchase behavior across customer demographics and product categories.

Repository contents
- `Analysis.ipynb` — Main Jupyter notebook with EDA steps, cleaning, and visualizations.
- `BlackFriday.csv` — Dataset used in the notebook (transaction-level records).
- `Untitled-1.py` — Miscellaneous script (inspect before running).
- `Twitter/` — A folder with `package.json` (Node project or helper scripts).

Dataset (columns)
- `User_ID` : Identifier for each user (numeric in file; notebook converts to string).
- `Product_ID` : Identifier for each product.
- `Gender` : 'F' or 'M' (notebook maps `F->0`, `M->1`).
- `Age` : Age bracket (e.g., `0-17`, `18-25`, `26-35`, `36-45`, `46-50`, `51-55`, `55+`).
- `Occupation` : Coded occupation id (integer label).
- `City_Category` : City category label (A/B/C).
- `Stay_In_Current_City_Years` : Years staying in current city (string values like `0`, `1`, `2`, `3`, `4+`).
- `Marital_Status` : Binary indicator (0/1).
- `Product_Category_1` : Product category id (int).
- `Product_Category_2` : Product category id (int; contains missing values).
- `Product_Category_3` : Product category id (int; contains missing values).
- `Purchase` : Purchase amount (target / continuous value).

Notes about the data
- The CSV header is: `User_ID,Product_ID,Gender,Age,Occupation,City_Category,Stay_In_Current_City_Years,Marital_Status,Product_Category_1,Product_Category_2,Product_Category_3,Purchase`.
- `Product_Category_2` and `Product_Category_3` contain missing values in many rows. In the notebook they are filled with the mean of their respective columns.

What the notebook does (summary)
- Installs and imports common plotting libraries (Seaborn, Matplotlib) and loads `BlackFriday.csv` into a DataFrame.
- Creates a working copy of the data (`df1`) and performs basic checks (`.head()`, `.info()`, `.describe()`, missing-value counts).
- Converts `User_ID` to string, maps `Gender` to numeric (F->0, M->1), and fills missing product category values with column means.
- Generates visualizations: heatmap of correlations, pie/bar charts for gender/age/city distributions, countplots, and grouped purchase summaries by demographics.
- Computes aggregates like number of unique users/products, purchase totals and means grouped by demographic features.

How to run
1. Open the workspace in VS Code or a Jupyter environment.
2. Create/activate a Python environment (recommended: venv or conda).
3. Install the Python dependencies used in the notebook:

```powershell
python -m pip install --upgrade pip;
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

4. Launch Jupyter and open the notebook:

```powershell
jupyter notebook Analysis.ipynb
```
