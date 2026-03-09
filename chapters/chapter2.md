# Chapter 2 - End-to-End Machine Learning Project

## Chapter Overview

This chapter guides through a complete Machine Learning project, from data ingestion to model deployment, using the California Housing Prices dataset. The primary objective is to build a model that predicts median housing prices in various districts.

### The 8-Step Machine Learning Checklist
1. **Frame the problem** and look at the big picture.
2. **Get the data**.
3. **Explore the data** to gain insights.
4. **Prepare the data** to better expose the underlying patterns to ML algorithms.
5. **Explore many different models** and short-list the best ones.
6. **Fine-tune your models** and combine them into a great solution.
7. **Present your solution**.
8. **Launch, monitor, and maintain** your system.

## Performance Measures

Selecting the right metric is critical for evaluating regression models:
- **RMSE (Root Mean Square Error)**: The preferred performance measure for regression tasks. It gives a higher weight to large errors.
  $$\text{RMSE}(\mathbf{X}, h) = \sqrt{\frac{1}{m} \sum_{i=1}^{m} (h(\mathbf{x}^{(i)}) - y^{(i)})^2}$$
- **MAE (Mean Absolute Error)**: Preferred if there are many outlier districts.

## Data Splitting and Sampling

Professional ML requires careful data splitting to avoid **Snooping Bias**.
- **Random Sampling**: Generally fine if the dataset is large enough.
- **Stratified Sampling**: Essential if the dataset is small to ensure the sample is representative of the whole population (e.g., ensuring the distribution of income categories is the same in both train and test sets).

```python
from sklearn.model_selection import StratifiedShuffleSplit

split = StratifiedShuffleSplit(n_splits=1, test_size=0.2, random_state=42)
for train_index, test_index in split.split(housing, housing["income_cat"]):
    strat_train_set = housing.loc[train_index]
    strat_test_set = housing.loc[test_index]
```

## Preparing Data for ML Algorithms

Data preparation should be automated using functions and pipelines for reproducibility.

### 1. Data Cleaning
Handle missing values using `SimpleImputer`.
```python
from sklearn.impute import SimpleImputer
imputer = SimpleImputer(strategy="median")
```

### 2. Handling Text and Categorical Attributes
Convert categories to numbers using `OneHotEncoder` (to avoid assuming proximity between values).

### 3. Feature Scaling
- **Min-Max Scaling (Normalization)**: Scales values to a range (0 to 1).
- **Standardization**: Subtracts the mean and divides by the standard deviation. Less affected by outliers.

### 4. Transformation Pipelines
Using `ColumnTransformer` to apply different transformations to different columns.

```python
from sklearn.compose import ColumnTransformer
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler, OneHotEncoder

num_pipeline = Pipeline([
    ('imputer', SimpleImputer(strategy="median")),
    ('std_scaler', StandardScaler()),
])

full_pipeline = ColumnTransformer([
    ("num", num_pipeline, num_attribs),
    ("cat", OneHotEncoder(), cat_attribs),
])

housing_prepared = full_pipeline.fit_transform(housing)
```

## Fine-Tuning the Model

Instead of manual tuning, use automated search techniques:
- **Grid Search**: Exhaustive search over a specified subset of hyperparameters.
- **Randomized Search**: Evaluates a given number of random combinations (better for large search spaces).

```python
from sklearn.model_selection import GridSearchCV

param_grid = [{'n_estimators': [3, 10, 30], 'max_features': [2, 4, 6, 8]}]
grid_search = GridSearchCV(forest_reg, param_grid, cv=5, scoring='neg_mean_squared_error')
grid_search.fit(housing_prepared, housing_labels)
```

## Summary Checklist
- [x] Framed the problem (Supervised, Regression, Batch).
- [x] Selected RMSE as the performance measure.
- [x] Implemented Stratified Sampling.
- [x] Built a full Transformation Pipeline.
- [x] Fine-tuned hyperparameters using `GridSearchCV`.

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*
