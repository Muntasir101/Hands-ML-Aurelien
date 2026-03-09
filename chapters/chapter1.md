# Chapter 1 - The Machine Learning Landscape

## Chapter Overview

Machine Learning (ML) is the science of programming computers so they can learn from data. It is particularly effective for problems where existing solutions require a long list of hand-tuned rules, or for complex problems for which there is no good solution using a traditional approach.

In this chapter, we explore the fundamental concepts:
- **Defining ML**: Automating the discovery of patterns.
- **Why use ML?**: Handling fluctuating environments and gaining insights from large data (Data Mining).
- **The Workflow**: From data collection to deployment.

## Taxonomy of Machine Learning Systems

### 1. Supervision Level
- **Supervised Learning**: The training data includes the desired solutions, called **labels** (e.g., Regression, Classification).
- **Unsupervised Learning**: The system tries to learn without a teacher. It finds hidden patterns (e.g., Clustering, Dimensionality Reduction).
- **Semi-supervised Learning**: Deals with partially labeled training data.
- **Reinforcement Learning**: An agent observes the environment, selects and performs actions, and gets rewards or penalties in return.

### 2. Learning Style
- **Batch Learning**: The system is incapable of learning incrementally; it must be trained using all available data (offline).
- **Online Learning**: The system is trained incrementally by feeding it data instances sequentially, either individually or in small groups (mini-batches).

### 3. Generalization Strategy
- **Instance-based Learning**: The system learns the examples by heart, then generalizes to new cases by comparing them to the learned examples using a similarity measure.
- **Model-based Learning**: Building a model from a set of examples and using that model to make predictions.

## Main Challenges in Machine Learning

Professional ML development requires addressing several pitfalls:
1. **Insufficient Quantity of Training Data**: Most ML algorithms need thousands of examples to work properly.
2. **Non-representative Training Data**: If the sample is too small, you have **sampling noise**; if the sampling method is flawed, you have **sampling bias**.
3. **Poor-Quality Data**: Data full of errors, outliers, and noise.
4. **Irrelevant Features**: The system will only be able to learn if the training data contains enough relevant features and not too many irrelevant ones (**Feature Engineering**).

## Overfitting and Underfitting

| Concept | Description | Solution |
| :--- | :--- | :--- |
| **Overfitting** | Model performs well on training data but fails to generalize. | Simplify model, gather more data, or reduce noise. |
| **Underfitting** | Model is too simple to learn the underlying structure. | Select more powerful model, better features, or reduce constraints. |

> [!TIP]
> **Regularization** is the process of constraining a model to make it simpler and reduce the risk of overfitting.

## Professional Implementation (Scikit-Learn Example)

A typical model-based learning workflow involves selecting a model, training it, and making predictions.

```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
from sklearn.linear_model import LinearRegression

# Download and prepare the data
data_root = "https://github.com/ageron/data/raw/main/"
lifesat = pd.read_csv(data_root + "lifesat/lifesat.csv")
X = lifesat[["GDP per capita (USD)"]].values
y = lifesat[["Life satisfaction"]].values

# Visualize the data
lifesat.plot(kind='scatter', grid=True, x="GDP per capita (USD)", y="Life satisfaction")
plt.axis([23500, 62500, 4, 9])
plt.show()

# Select a linear model
model = LinearRegression()

# Train the model
model.fit(X, y)

# Make a prediction for Cyprus
X_new = [[37_655.2]]  # Cyprus' GDP per capita in 2020
print(model.predict(X_new)) # outputs [[6.30165767]]
```

## Key Professional Terms

- **Utility Function (Fitness Function)**: Measures how *good* your model is.
- **Cost Function**: Measures how *bad* your model is.
- **Hyperparameter**: A parameter of a learning algorithm (not of the model itself) that remains constant during training.

## Summary Checklist

- [x] Defined the problem in terms of ML (Supervised/Unsupervised).
- [x] Identified the learning approach (Online vs Batch).
- [x] Evaluated the risk of overfitting/underfitting.
- [x] Performed feature selection/extraction.

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*
