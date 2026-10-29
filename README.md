# APRAU_1131504_1250515_1220638 — Group 26

Project 1 — Machine Learning — ISEP — 2026/2027.

## Project structure

```text
APRAU_1131504_1250515_1220638/
├── data/
│   └── dataset_grupo_26.csv
├── notebooks/
│   └── APRAU_Group26.ipynb
├── reports/
│   └── reportmodelo_1250515_1220638_1131504.docx
├── .gitignore
├── README.md
└── requirements.txt
```

### `data/` — Dataset

Contains [dataset_grupo_26.csv](data/dataset_grupo_26.csv), used for analysis and model training.

- **Size:** 2,000 records and 35 columns.
- **Predictors:** clinical and lifestyle variables, including age, gender, BMI, cholesterol and blood pressure.
- **`target_regression`:** numerical target for regression models.
- **`target_class`:** classification target with three categories: `DI`, `DI_HY` and `HT_HY`.

The two targets are studied separately. Neither is used to predict the other.

### `notebooks/` — Analysis and models

Contains [APRAU_Group26.ipynb](notebooks/APRAU_Group26.ipynb), with Python code, methodological explanations, results and plots.

The notebook covers:

1. Environment setup and reproducibility.
2. Data loading, descriptive statistics and exploratory data analysis (EDA).
3. Data quality checks and identification of constant or redundant variables.
4. Experimental protocol and prevention of data leakage between training and testing.
5. Simple and multiple linear regression.
6. Classification using Logistic Regression and Linear Discriminant Analysis (LDA).
7. Evaluation using holdout, 5-fold and 10-fold cross-validation, leave-one-out and bootstrap.
8. L1/L2 regularization and feature selection for classification.
9. Conclusions, limitations, references and submission procedures.

### `reports/` — Report

Contains [reportmodelo_1250515_1220638_1131504.docx](reports/reportmodelo_1250515_1220638_1131504.docx), the Word document for the project report.

### Root files

| File | Purpose |
| --- | --- |
| `README.md` | Project structure and execution instructions. |
| `requirements.txt` | Python dependencies: NumPy, pandas, Matplotlib, seaborn, scikit-learn, notebook, JupyterLab and ipykernel. |
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

The notebook can locate the CSV when launched from either the project root or the `notebooks/` directory. Leave-one-out evaluation may take longer because it fits the models repeatedly.

Dependencies in `requirements.txt` are not pinned to specific versions, so installed versions may affect compatibility and results.
