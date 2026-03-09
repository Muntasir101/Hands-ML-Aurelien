# Chapter 9 - Unsupervised Learning Techniques

## Chapter Overview

Most of the applications of Machine Learning today are based on supervised learning. However, the vast majority of the available data is unlabeled: we have the input features $X$, but we do not have the labels $y$. Unsupervised learning is about discovering hidden patterns in this unlabeled data.

## Clustering

Clustering is the task of grouping similar instances together into clusters. It is used for customer segmentation, data analysis, dimensionality reduction, anomaly detection, and more.

### 1. K-Means
An algorithm that searches for a semi-optimal solution by iteratively assigning instances to the nearest centroid and then updating the centroids.
- **Centroids**: The center points of the clusters.
- **Inertia**: The mean squared distance between each instance and its closest centroid.
- **Elbow Method**: A technique to choose the optimal number of clusters $K$ by looking for the "elbow" in the inertia curve.

### 2. DBSCAN
Density-Based Spatial Clustering of Applications with Noise. It defines clusters as continuous regions of high density.
- **Advantages**: It can find clusters of any shape and is robust to outliers (noise).
- **Hyperparameters**: `eps` (distance) and `min_samples` (minimum instances in a neighborhood).

## Gaussian Mixture Models (GMM)

A probabilistic model that assumes that the instances were generated from a mixture of several Gaussian distributions whose parameters are unknown.
- **Expectation-Maximization (EM)**: An algorithm used to estimate the GMM parameters.
- **Bayesian Information Criterion (BIC)**: Used to select the optimal number of clusters by penalizing models with more parameters.

## Anomaly and Novelty Detection

- **Anomaly Detection**: Identifying instances that look very different from the training data. Useful for fraud detection, manufacturing defect detection, etc.
- **Novelty Detection**: Identifying instances that are different from any instance in the training set, assuming the training set is "clean".

```python
from sklearn.mixture import GaussianMixture

gm = GaussianMixture(n_components=3, n_init=10)
gm.fit(X)

print(gm.weights_)
print(gm.means_)
print(gm.covariances_)
```

## Summary Checklist
- [x] Used K-Means for spherical clustering and selected $K$ using Silhouette scores.
- [x] Applied DBSCAN for irregular cluster shapes and noise filtering.
- [x] Modeled data distribution using Gaussian Mixtures for "soft" clustering assignments.
- [x] Implemented Anomaly Detection for identifying outliers in the dataset.

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*
