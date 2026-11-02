# MSCS 634 — Lab 1: Data Visualization, Data Preprocessing, and Statistical Analysis

**Student:** Corey Hyde  
**Student ID:** 003044072  
**Course:** MSCS-634-A01 — Advanced Big Data and Data Mining

## Purpose
Demonstrate Python-based exploratory analysis, data visualization, missing-value imputation, IQR outlier removal, sampling, feature elimination, scaling, age discretization, descriptive statistics, and Pearson correlation.

## Dataset
The notebook builds a reproducible **synthetic**, 500-row retail transaction dataset covering 2025, five product categories, and four geographical regions. Missing values and unusually large quantities are added for instruction. It is not a dataset of real customers or businesses. The raw CSV is written to `data/retail_sales_raw.csv`; the imputed and IQR-filtered CSV is written to `data/retail_sales_cleaned.csv`.

## Run in VS Code
1. Install the Python and Jupyter extensions.
2. Open the repository folder in VS Code.
3. Create and activate a Python virtual environment (optional but recommended).
4. Run `python -m pip install -r requirements.txt` in the VS Code terminal.
5. Open `Lab_1_Data_Analysis.ipynb`, select the installed Python kernel, then choose **Restart & Run All**.
6. Save the executed notebook. The CSVs and 15 PNG files will be regenerated locally.

## What the notebook covers
- **Visualizations:** scatter, line, bar, histogram, box, and pie charts; notebook displays dataset-specific computed insights.
- **Preprocessing:** median imputation for numeric fields, mode imputation for categories, recalculated sales totals, IQR outlier filtering, 50% random sampling, and two-column feature elimination.
- **Scaling and binning:** Min-Max scaling and `pd.cut()` age bands.
- **Statistics:** `.info()`, `.describe()`, central tendency, dispersion, unique Pearson correlation pairs and heatmap.

## Interpretation and decisions
All insights are computed from the actual generated data when the notebook runs, rather than typed-in or assumed. Correlation is not proof of causality. Artificial calendar variation is not evidence of seasonality. The IQR method can flag valid expensive transactions because categories differ in price, so outlier filtering is demonstration rather than a universal recommendation. Synthetic data and mode/median imputation limit real-world interpretation.

## Screenshots
The `screenshots/` folder stores 15 rendered PNGs. For submission requirements asking for screenshots of *calculation output*, capture the executed notebook cells in VS Code, especially the missing-value before/after output, IQR values and identified records, reductions, scaling and age groups, `.info()`/`.describe()`, and the numerical correlation matrix. The notebook's final checklist maps these to filenames.

## Repository structure
```text
MSCS_634_Lab_1/
├── Lab_1_Data_Analysis.ipynb
├── data/
│   ├── retail_sales_raw.csv
│   └── retail_sales_cleaned.csv
├── screenshots/
│   ├── 01_dataset_preview.png
│   └── ... (15 images total)
├── requirements.txt
├── .gitignore
└── README.md
```
