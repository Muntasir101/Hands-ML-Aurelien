# Chapter 4 - Training Models

## Chapter Overview

This chapter explores what happens "under the hood" of Machine Learning algorithms. Understanding how models are trained helps in selecting the right model, the right training algorithm, and a good set of hyperparameters.

## Linear Regression

Linear Regression models the relationship between a dependent variable and one or more independent variables.
- **The Normal Equation**: A mathematical equation that gives the result directly.
  $$\hat{\theta} = (\mathbf{X}^T \mathbf{X})^{-1} \mathbf{X}^T \mathbf{y}$$
- **Computational Complexity**: The Normal Equation gets very slow when the number of features grows large (e.g., 100,000).

## Gradient Descent (GD)

Gradient Descent is a generic optimization algorithm capable of finding optimal solutions to a wide range of problems. The goal is to tweak parameters iteratively to minimize a cost function.

### Variants of Gradient Descent

| Algorithm | Data per Step | Accuracy | Speed |
| :--- | :--- | :--- | :--- |
| **Batch GD** | Full training set | High (Stable) | Slow |
| **Stochastic GD** | 1 instance | Random (Noisy) | Fast |
| **Mini-batch GD** | Small random sets | Moderate | Fast (Hardware optimized) |

> [!IMPORTANT]
> **Learning Rate**: If too small, the algorithm will take many iterations to converge. If too large, it might jump across the valley and fail to find a solution.

## Polynomial Regression and Learning Curves

When data is more complex than a straight line, we can use **Polynomial Regression** by adding powers of each feature as new features.
- **Learning Curves**: Plots of the model's performance on the training set and the validation set as a function of the training set size.
  - **High Bias**: Both curves reach a plateau; they are close and fairly high (Underfitting).
  - **High Variance**: There is a gap between the curves, meaning the model performs much better on training data than validation data (Overfitting).

## Regularized Linear Models

To reduce overfitting, we constrain the model (Regularization).
1. **Ridge Regression**: Adds a regularization term equal to $\alpha \sum \theta_i^2$ to the cost function.
2. **Lasso Regression**: Adds $\alpha \sum |\theta_i|$. It tends to eliminate the weights of the least important features (Automatic Feature Selection).
3. **Elastic Net**: A middle ground between Ridge and Lasso.

```python
from sklearn.linear_model import Ridge, Lasso, ElasticNet

# Ridge Regression
ridge_reg = Ridge(alpha=1, solver="cholesky")
ridge_reg.fit(X, y)

# Lasso Regression (useful for feature selection)
lasso_reg = Lasso(alpha=0.1)
lasso_reg.fit(X, y)

# Elastic Net
elastic_net = ElasticNet(alpha=0.1, l1_ratio=0.5)
elastic_net.fit(X, y)
```

## Early Stopping

A very different way to regularize iterative learning algorithms such as Gradient Descent is to stop training as soon as the validation error reaches a minimum. This is called **Early Stopping**.

## Logistic Regression

Commonly used to estimate the probability that an instance belongs to a particular class.
- **Softmax Regression**: A generalization of Logistic Regression to support multiple classes directly, without having to train and combine multiple binary classifiers.

## Summary Checklist
- [x] Compared Normal Equation and Gradient Descent for the given feature size.
- [x] Analyzed Learning Curves to detect Bias/Variance issues.
- [x] Applied Regularization (Ridge/Lasso) to handle overfitting.
- [x] Implemented Early Stopping for iterative models.

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*
