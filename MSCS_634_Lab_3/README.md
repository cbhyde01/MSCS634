# MSCS 634 — Lab 3: K-Means and K-Medoids Clustering

**Student:** Corey Hyde  
**Course:** MSCS-634-A01 — Advanced Big Data and Data Mining

## Purpose

Compare **K-Means** and **K-Medoids (PAM)** clustering on scikit-learn's Wine dataset (178 records, 13 chemical features, three known classes). Features are standardized with z-scores before clustering. Both models use **k = 3**. I compare their Silhouette Scores and Adjusted Rand Indices (ARI) and visualize both clustering results with PCA.

## Project files

- `MSCS_634_Lab_3.ipynb` — Complete, executed Jupyter Notebook with analysis, metrics, plots, and discussion.
- `plots/clustering_comparison.png` — Side-by-side K-Means and K-Medoids scatter plots with marked centroids and medoids.
- `plots/actual_wine_classes.png` — PCA scatter plot of the real wine classes for reference.
- `requirements.txt` — Python package requirements.

## Results

| Algorithm | Silhouette Score | Adjusted Rand Index (ARI) |
|---|---:|---:|
| K-Means | 0.2849 | 0.8975 |
| K-Medoids (PAM) | 0.2676 | 0.7411 |

**Key observations:** K-Means produced more clearly separated clusters according to the Silhouette Score, while K-Means had better agreement with the dataset's actual wine classes according to ARI. These scores answer different questions: Silhouette measures separation without using labels, while ARI measures agreement with known categories. Clustering labels are arbitrary identifiers and do not need to equal the original class numbers.

The cluster plots may show slightly different boundaries and representative locations. K-Means places its centroids at feature averages, whereas K-Medoids selects actual wine samples. The plots use only two PCA dimensions for display, but **all clustering and metrics were calculated with all 13 standardized features**.

## Challenges and decisions

- **Different feature scales:** Some original chemical attributes have much larger values than others. I used `StandardScaler` so distances were not dominated by those features.
- **K-Medoids implementation:** `KMedoids` is not included in core scikit-learn. I used a documented PAM swap procedure implemented with NumPy and scikit-learn pairwise distances, making the notebook run without `scikit-learn-extra`.
- **Repeatability:** I set a fixed random seed and used multiple starts for both algorithms to reduce variation from random initialization.
- **Visualization:** PCA makes it possible to plot high-dimensional data in 2D, but projection can obscure separation in the original feature space.

## When each algorithm is useful

**K-Means** is usually computationally efficient and works well for compact groups without large outliers. **K-Medoids** can be preferable when real observations are needed as representatives or when resistance to outliers matters. Neither algorithm is automatically best in every dataset.

## Run locally

```bash
python -m pip install -r requirements.txt
jupyter notebook MSCS_634_Lab_3.ipynb
```

Alternatively, open the `.ipynb` file in **VS Code** with the Python and Jupyter extensions, select a Python kernel, and choose **Run All**.

## Dataset

The Wine recognition dataset is included in `sklearn.datasets.load_wine()`. Original dataset: UCI Machine Learning Repository, Wine dataset.
