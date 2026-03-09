# Chapter 8 - Unsupervised Learning Techniques

## Chapter Overview

In this chapter, I moved from supervised learning (with labels) to unsupervised learning, where the data has **no labels**.  
The goal is to discover structure in the data: groups, densities, and unusual points.

> **Important idea:** Unsupervised learning does not tell me “who is right or wrong”, but it helps me see patterns I didn’t notice before.

## Concepts I Learned

- What makes unsupervised learning different from supervised learning
- Clustering as grouping similar instances
- K-Means algorithm and its limitations
- DBSCAN for density-based clustering
- Gaussian Mixture Models (GMMs)
- Anomaly and novelty detection
- How these methods can support supervised learning (preprocessing, feature engineering, semi-supervised)

## Important Terms (Simple Explanation)

- **Unsupervised learning:** learning from data without labels
- **Clustering:** automatically grouping similar instances together
- **K-Means:** algorithm that finds K cluster centers and assigns points to the nearest center
- **DBSCAN:** clustering based on dense regions; can find arbitrary shapes and mark noise points
- **Gaussian Mixture Model (GMM):** assumes data comes from a mix of several Gaussian distributions
- **Expectation-Maximization (EM):** iterative algorithm to fit mixture models like GMMs
- **Anomaly / novelty detection:** finding rare or unusual instances that do not fit the learned pattern

## My Personal Reflection

I liked this chapter because it felt like “exploratory data analysis with algorithms”.  
Instead of the model telling me a label, the algorithms helped me understand the structure of my dataset.

<details>
  <summary>What I found difficult</summary>
  I found it tricky to choose the right number of clusters for K-Means and to interpret Gaussian Mixture results.  
  For now, I rely on tools like the elbow method, silhouette scores, and visualizing clusters after dimensionality reduction.
</details>

## Real-World Examples

- Grouping customers into segments based on behavior (clustering)
- Detecting fraudulent or suspicious transactions (anomaly detection)
- Compressing colors in an image to a smaller palette (K-Means for color quantization)
- Separating background vs. foreground regions in images using clustering

## Key Takeaways

1. Unsupervised methods are powerful for **exploring** data when labels are missing or incomplete.
2. K-Means is simple and fast but assumes roughly spherical clusters and is sensitive to scaling and initialization.
3. Density-based methods like DBSCAN can find irregular shapes and mark outliers without needing to choose K in advance.
4. Gaussian Mixture Models are more flexible than K-Means because they model soft cluster membership and elliptical shapes.

## Mini Quiz

1. How is clustering different from classification?

<details>
  <summary>Show answer</summary>
  Classification predicts predefined labels, while clustering discovers groups in unlabeled data without knowing the labels in advance.
</details>

2. What is one advantage of DBSCAN over K-Means?

<details>
  <summary>Show answer</summary>
  DBSCAN can find clusters of arbitrary shape and automatically treat low-density points as noise, without requiring a fixed number of clusters K.
</details>

## Summary

This chapter showed me that I can learn a lot from data even without labels.  
Clustering, mixture models, and anomaly detection help me understand hidden structure and prepare better features for future supervised models.

## Key Insights I'm Taking Forward

- Before building a supervised model, I can use clustering and dimensionality reduction together to understand the data landscape.
- There is no single “correct” clustering result; the usefulness depends on my goal (e.g., marketing segments vs anomaly detection).
- Unsupervised learning is a key tool for **exploration and feature engineering**, not just a side topic.
