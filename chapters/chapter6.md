# Chapter 6 - Decision Trees

## Chapter Overview

Decision Trees are versatile Machine Learning algorithms that can perform both classification and regression tasks, and even multioutput tasks. They are powerful algorithms, capable of fitting complex datasets.

## Training and Visualizing a Decision Tree

Unlike many other models, Decision Trees are "white box" models: their decisions are easy to interpret and visualize.
- **Root Node**: The top node that represents the entire population or sample.
- **Leaf Node**: Nodes that do not split further and represent a class (or a value in regression).

## The CART Training Algorithm

Scikit-Learn uses the **Classification and Regression Tree (CART)** algorithm to train Decision Trees. The algorithm splits the training set into two subsets using a single feature $k$ and a threshold $t_k$. It searches for the pair $(k, t_k)$ that produces the purest subsets (weighted by their size).

### Gini Impurity vs. Entropy
- **Gini Impurity**: Measures how often a randomly chosen element from the set would be incorrectly labeled.
  $$G_i = 1 - \sum_{k=1}^{n} p_{i,k}^2$$
- **Entropy**: Measures the average information content you reap from each message. A node's entropy is zero when it contains instances of only one class.

> [!NOTE]
> Most of the time it does not make a big difference which one you use; they lead to similar trees. Gini impurity is slightly faster to compute.

## Regularization Hyperparameters

Decision Trees make very few assumptions about the training data (unlike linear models). If left unconstrained, the tree structure will adapt itself to the training data, fitting it very closely—and most likely overfitting it.
- **`max_depth`**: Limits the maximum depth of the tree.
- **`min_samples_split`**: The minimum number of samples a node must have before it can be split.
- **`min_samples_leaf`**: The minimum number of samples a leaf node must have.
- **`max_leaf_nodes`**: The maximum number of leaf nodes.

## Decision Tree Regression

Decision Trees are also capable of performing regression. Instead of predicting a class in each node, it predicts a value (usually the average target value of the training instances associated with that leaf node).

```python
from sklearn.tree import DecisionTreeRegressor

tree_reg = DecisionTreeRegressor(max_depth=2)
tree_reg.fit(X, y)
```

## Instability

Decision Trees have a few limitations. They love orthogonal decision boundaries (all splits are perpendicular to an axis), which makes them sensitive to training set rotation. More importantly, they are very sensitive to small variations in the training data.

> [!TIP]
> **Random Forests** can limit this instability by averaging predictions over many trees.

## Summary Checklist
- [x] Visualized the tree structure to ensure interpretability.
- [x] Compared Gini vs Entropy for the specific dataset.
- [x] Applied regularization (`max_depth`, `min_samples_leaf`) to prevent overfitting.
- [x] Evaluated the impact of data rotation/scaling on the tree structure.

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*

