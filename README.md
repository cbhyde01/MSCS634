# MSCS 634 — Lab 1: Data Visualization, Data Preprocessing, and Statistical Analysis

**Student:** Corey Hyde  
**Student ID:** 003044072  
**Course:** MSCS-634— Advanced Big Data and Data Mining

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

---

# MSCS 634 — Lab 2: KNN and Radius Neighbors Classification

## Purpose
This lab uses scikit-learn's Wine dataset (178 samples, 13 numeric features, 3 classes) to compare K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) classifiers. It explores the requested parameter settings, measures accuracy on an 80/20 stratified split, and visualizes trends.

## Results
The notebook was executed using `random_state=42` and **unscaled** Wine features.

| KNN k | Test accuracy |
|---:|---:|
| 1 | 77.78% |
| 5 | 80.56% |
| 11 | 80.56% |
| 15 | 80.56% |
| 21 | 80.56% |

| RNN radius | Test accuracy |
|---:|---:|
| 350 | 72.22% |
| 400 | 69.44% |
| 450 | 69.44% |
| 500 | 69.44% |
| 550 | 66.67% |
| 600 | 66.67% |

**Key observation:** KNN with k=5, 11, 15, or 21 scored 80.56%, outperforming the best RNN radius (350) at 72.22% by 8.33 percentage points on this test split. The tested RNN accuracy declined as the radius grew, consistent with wider neighborhoods mixing different classes.

## Challenges and decisions
- Wine features have different numeric scales. The original feature values were retained so the assigned RNN radii (350–600) would remain meaningful; this also means large-range features can dominate distance calculations.
- RNN uses `outlier_label="most_frequent"` to handle any test points with no neighbors, and the notebook reports how many such points occur.
- The split is stratified and reproducible. Parameter selection based on the test set is only an exploratory comparison; a more rigorous study would use training-set cross-validation to select settings and reserve the test set for final evaluation.

## Files
- `MSCS_634_Lab_2.ipynb` — executed notebook with dataset exploration, models, plots, and discussion
- `knn_accuracy.png` and `rnn_accuracy.png` — saved accuracy plots
- `requirements.txt` — Python dependencies

## Run locally in VS Code
1. Open this folder in VS Code and select a Python interpreter with Jupyter support.
2. In a terminal, run `python -m pip install -r requirements.txt`.
3. Open `MSCS_634_Lab_2.ipynb` and choose **Run All**.

## References
- [scikit-learn Wine dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_wine.html)
- [scikit-learn Nearest Neighbors documentation](https://scikit-learn.org/stable/modules/neighbors.html)
