# Chapter 7 - Dimensionality Reduction

## Chapter Overview

In this chapter, I learned how to reduce the number of input features while keeping as much useful information as possible.  
This helps models run faster and can even improve performance by removing noise and redundant features.

> **Important idea:** Dimensionality reduction is about finding a smaller, more meaningful representation of high-dimensional data.

## Concepts I Learned

- The curse of dimensionality (why high dimensions are hard)
- Projection vs manifold learning
- Principal Component Analysis (PCA)
- Explained variance ratio and choosing the number of components
- Incremental PCA for very large datasets
- Randomized PCA for fast approximations
- Kernel PCA for non-linear dimensionality reduction
- Manifold learning methods (briefly), like LLE and t-SNE for visualization

## Important Terms (Simple Explanation)

- **Dimensionality reduction:** turning many features into fewer, more informative ones
- **Curse of dimensionality:** in high dimensions, data becomes sparse and distances lose meaning
- **Projection:** mapping data onto a lower-dimensional subspace
- **Principal components:** directions of maximum variance in the data
- **Explained variance ratio:** how much of the original variation each component captures
- **Kernel PCA:** PCA performed in a high-dimensional feature space using kernels
- **Manifold learning:** techniques that assume data lies on a lower-dimensional curved surface inside a high-dimensional space

## My Personal Reflection

Before this chapter, I assumed “more features = more power”.  
Now I see that blindly adding features can hurt models, especially when the data becomes too sparse and noisy.

<details>
  <summary>What I found difficult</summary>
  The math behind PCA, SVD, and eigenvectors was intense.  
  For now, I focus on the idea that PCA finds directions where the data varies the most and uses those as new axes.
</details>

## Real-World Examples

- Compressing image data (e.g. faces) before training classifiers
- Reducing word embedding dimensions for visualization or faster models
- Speeding up training for algorithms that don’t like very high-dimensional inputs (like some kernel methods)

## Key Takeaways

1. More dimensions are not always better; high-dimensional spaces can confuse models and humans.
2. PCA is a strong default technique for building a compact representation of data.
3. Non-linear methods (Kernel PCA, LLE, t-SNE) are especially useful for understanding complex structures and visualizing clusters.

## Mini Quiz

1. What is the main goal of PCA?

<details>
  <summary>Show answer</summary>
  To find a lower-dimensional representation that captures as much variance of the original data as possible.
</details>

2. Why can very high-dimensional data cause problems?

<details>
  <summary>Show answer</summary>
  Because of the curse of dimensionality: data becomes sparse, distances lose meaning, and models may overfit or become unstable.
</details>

## Summary

This chapter taught me that simplifying the feature space can make models faster, easier to train, and sometimes more robust.  
I now see dimensionality reduction as an important preprocessing step, especially before visualization or training complex models.

## Key Insights I'm Taking Forward

- Before engineering more and more features, I should ask whether I can **summarize** existing features with PCA or related methods.
- Visualizing high-dimensional data (for example, with t-SNE after a PCA step) can reveal patterns and clusters that raw data hides.
- Dimensionality reduction is not just a “nice-to-have” step; it is part of designing a good representation for the problem I’m solving.
