# 04 — Data and Preparation

## Data, examples, features, labels
A dataset is a collection of examples. One example is a sample. A **feature** is input information; a **label/target** is the answer in supervised learning. For house price prediction, size and bedrooms are features, price is target.

## Formats
CSV is tabular text:
```csv
size,bedrooms,price
80,2,100000
120,3,150000
```
JSON stores structured objects:
```json
{"features": [80, 2], "label": 100000}
```

## Data cleaning
Check missing values, duplicates, incorrect labels, inconsistent units, types, and unusual values. An outlier may be a real rare case, not an error; investigate before deleting.

## Numerical and categorical data
Numerical features are quantities. Categorical features are groups such as color. One-hot encoding represents categories as vectors: red=[1,0,0], green=[0,1,0], blue=[0,0,1]. Avoid arbitrary numeric labels that imply a false ordering.

## Scaling
Min-max scaling: `x_scaled = (x − min)/(max − min)`. Standardization: `z=(x−μ)/σ`. Scaling helps some optimization algorithms when feature ranges differ greatly. Fit scaling parameters on training data only; apply those same parameters to validation/test sets.

## Dataset splits
- Training: learn parameters.
- Validation: tune decisions and compare models.
- Test: final evaluation after decisions are finished.
A common split is 70/15/15, but context matters. Time series often require chronological splits.

## Leakage
Data leakage happens when information unavailable at prediction time improperly influences training or evaluation. Examples: future data used to predict past, scaling before splitting, or a feature that directly reveals the target. Leakage creates misleadingly high scores.

## NumPy and pandas
```python
import numpy as np
X = np.array([[80,2],[120,3],[100,2]], dtype=float)
print(X.shape)  # (3, 2): three rows, two features
```
```python
import pandas as pd
df = pd.read_csv("data.csv")
print(df.head())
print(df.isna().sum())
```

## Exercises
Identify features/target for exam prediction; explain why test data should not tune a model; give a leakage example; explain scaling; describe why a missing value needs careful handling.

## Mini-project
Load CSV, inspect columns, find missing data, separate X and y, create train/validation/test splits, and document preprocessing.