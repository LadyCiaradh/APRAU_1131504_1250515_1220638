# APRAU_1131504_1250515_1220638 - Group 26

Project 1 - Machine Learning - ISEP - 2026/2027.

## Project structure

```text
APRAU_1131504_1250515_1220638/
├── data/
│   └── dataset_grupo_26.csv
├── notebooks/
│   └── APRAU_Group26.ipynb
├── reports/
│   └── Report_APRAU_1250515_1220638_1131504.pdf
├── .gitignore
├── README.md
└── requirements.txt
```

### `data/` - Dataset

Contains [dataset_grupo_26.csv](data/dataset_grupo_26.csv), used for analysis and model training.

- **Size:** 2,000 records and 35 columns.
- **Predictors:** clinical and lifestyle variables, including age, gender, BMI, cholesterol and blood pressure.
- **`target_regression`:** numerical target for regression models.
- **`target_class`:** classification target with three imbalanced categories: `DI_HY` (64.35%), `DI` (32.20%) and `HT_HY` (3.45%).

The two targets are studied separately. Neither is used to predict the other.

### `notebooks/` - Analysis and models

Contains [APRAU_Group26.ipynb](notebooks/APRAU_Group26.ipynb), with Python code, methodological explanations, results and plots.

The notebook covers:

1. Environment setup and reproducibility (fixed seed 26).
2. Data loading, descriptive statistics and exploratory data analysis (EDA), including categorical predictors versus the regression target (η²).
3. Data quality checks: constant and redundant variables, derived categories, the consistency of the low-HDL indicator and differences in within-class variability across diagnostic classes.
4. Experimental protocol (stratified 80/20 split) and prevention of data leakage between training and testing.
5. Simple and multiple linear regression.
6. Classification using class-balanced Logistic Regression and Linear Discriminant Analysis (LDA) with uniform class priors, plus a sensitivity check with empirical priors.
7. Evaluation using repeated holdout, 5-fold and 10-fold cross-validation, full leave-one-out on the 1,600 training records and 200 bootstrap replicates with out-of-bag evaluation.
8. L1/L2 regularization and feature selection for classification, with the regularization strength `C` tuned by cross-validation.
9. Conclusions, limitations and references.

### `reports/` - Report

Contains [Report_APRAU_1250515_1220638_1131504.pdf](reports/Report_APRAU_1250515_1220638_1131504.pdf), the PDF document for the project report. All numerical results in the report were taken from the executed notebook.

### Root files

| File | Purpose |
| --- | --- |
| `README.md` | Project structure and execution instructions. |
| `requirements.txt` | Python dependencies: NumPy, pandas, SciPy, Matplotlib, seaborn, scikit-learn, notebook, JupyterLab and ipykernel. |
| `.gitignore` | Excludes `.venv/`, Python caches, Jupyter checkpoints and `.env` from version control. |

The hidden `.git/` directory stores the repository history and local Git configuration.

## Running the project

With Python and `pip` installed, run these commands in PowerShell from the project root:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m jupyterlab
```

In JupyterLab, open `notebooks/APRAU_Group26.ipynb`, select the kernel for the created environment and choose **Restart Kernel and Run All Cells** to run the analysis in order.

The notebook can locate the CSV when launched from either the project root or the `notebooks/` directory.

Leave-one-out evaluation fits each classifier 1,600 times, and the bootstrap fits it 200 times, so these cells take longer than the rest of the notebook.

The saved results were produced with Python 3.13.9 and scikit-learn 1.9.1. Dependencies in `requirements.txt` are not pinned to specific versions, so other versions may change compatibility and the exact numbers obtained.
