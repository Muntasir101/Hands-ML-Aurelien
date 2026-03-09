# Chapter 8 - Dimensionality Reduction

## Chapter Overview

Many Machine Learning problems involve hundreds or even thousands of features for each training instance. This not only makes training extremely slow, but it can also make it much harder to find a good solution. This problem is often referred to as the **Curse of Dimensionality**.

## The Curse of Dimensionality

High-dimensional datasets are at risk of being very sparse: most training instances are likely to be far away from each other. This also means that a new instance will likely be far from any training instance, making predictions much less reliable than in lower dimensions (higher risk of overfitting).

## Main Approaches for Dimensionality Reduction

### 1. Projection
In most real-world problems, training instances are not spread out uniformly across all dimensions. Many features are almost constant, while others are highly correlated. As a result, all training instances lie within a much lower-dimensional **subspace**.

### 2. Manifold Learning
A $d$-dimensional manifold is a part of an $n$-dimensional space that locally resembles a $d$-dimensional hyperplane. Many dimensionality reduction algorithms work by modeling the manifold on which the training instances live.

## PCA (Principal Component Analysis)

PCA is by far the most popular dimensionality reduction algorithm. It identifies the hyperplane that lies closest to the data, and then it projects the data onto it.
- **Preserving the Variance**: PCA chooses the axis that preserves the maximum amount of variance, as it will most likely lose less information than other projections.
- **Principal Components**: The unit vector that defines the $i$-th axis is called the $i$-th Principal Component (PC).
- **Explained Variance Ratio**: Indicates the proportion of the dataset’s variance that lies along each principal component.

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=0.95) # Keep 95% of variance
X_reduced = pca.fit_transform(X_train)
```

## Randomized and Incremental PCA

- **Randomized PCA**: Uses a stochastic algorithm to quickly find an approximation of the first $d$ principal components ($O(m \times d^2) + O(d^3)$ instead of $O(m \times n^2) + O(n^3)$).
- **Incremental PCA (IPCA)**: Allows you to split the training set into mini-batches and feed an IPCA algorithm one mini-batch at a time. This is useful for large training sets that do not fit in memory.

## Manifold Learning Techniques (LLE, t-SNE)

- **LLE (Locally Linear Embedding)**: A powerful nonlinear dimensionality reduction technique. It works by first measuring how each training instance linearly relates to its closest neighbors, and then looking for a low-dimensional representation where these local relationships are best preserved.
- **t-SNE (t-distributed Stochastic Neighbor Embedding)**: Primarily used for visualization. It keeps similar instances close and dissimilar instances apart.

## Summary Checklist
- [x] Addressed the Curse of Dimensionality by reducing feature redundancy.
- [x] Analyzed the Explained Variance Ratio to select the optimal number of components.
- [x] Used Incremental PCA for memory-constrained environments.
- [x] Visualized complex high-dimensional structures using t-SNE or LLE.

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*
