# MSCS 634 — Project Deliverable 1

**Student:** Corey Hyde  
**Course:** MSCS-634-A01 — Advanced Big Data and Data Mining

## Dataset
[UCI Online Retail](https://archive.ics.uci.edu/dataset/352/online+retail) includes 541,909 transaction rows and 8 original attributes. Additional date and revenue features are engineered. The data supports future regression, classification, customer clustering, and market-basket association rules.

## Setup
1. Download **Online Retail.xlsx** from UCI and place it in `data/`.
2. Install dependencies: `pip install -r requirements.txt`
3. Open `Project_Deliverable_1.ipynb` in VS Code with the Jupyter extension and run all cells.

## Cleaning and exploration
- Audit missing fields, duplicates, cancellations, and invalid quantities/prices.
- Remove exact duplicates and standardize text/date types.
- Separate cancellations/returns from positive-sales analysis.
- Retain missing CustomerID in transaction analysis; exclude from customer aggregation.
- Engineer line-item revenue and calendar features.
- Plot sales distributions, outliers, monthly revenue, country revenue, and numeric correlations.
- Export cleaned transaction, returns, and customer feature tables into `outputs/`.

## Challenges and decisions
- Customer identifiers are missing for some transactions: do not invent identifiers.
- Returns and zero-price entries distort gross sales: keep returns separate.
- High-value bulk orders can be valid: visualize using percentile limits instead of deleting them.
- December 2011 is incomplete: interpret monthly comparisons cautiously.

## Key insights
Run the notebook and fill in verified values before submission: the most prominent distribution shape, top month, UK revenue share, and largest outliers. The dataset may be dominated by UK purchases and skewed line-item values; verify with outputs.

## References
UCI Machine Learning Repository. (2015). *Online Retail* [Dataset]. https://doi.org/10.24432/C5BW33

Han, J., Pei, J., & Tong, H. (2022). *Data mining* (4th ed.). Elsevier.

Wu, D. (2024). *Data mining with Python*. Taylor & Francis.
