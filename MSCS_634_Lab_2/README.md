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

## Files
- `MSCS_634_Lab_2.ipynb`
- `knn_accuracy.png`
- `rnn_accuracy.png`
- `requirements.txt`

## Run locally in VS Code
1. Open this folder in VS Code and select a Python interpreter with Jupyter support.
2. In a terminal, run `python -m pip install -r requirements.txt`.
3. Open `MSCS_634_Lab_2.ipynb` and choose **Run All**.

## References
- [scikit-learn Wine dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_wine.html)
- [scikit-learn Nearest Neighbors documentation](https://scikit-learn.org/stable/modules/neighbors.html)
