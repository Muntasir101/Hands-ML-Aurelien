# Chapter 8 - Dimensionality Reduction

## Chapter Overview

In this chapter, I learned how to reduce the number of features while keeping as much information as possible.  
This helps models run faster and sometimes even perform better by removing noise and redundancy.

> **Important idea:** Dimensionality reduction is about finding a smaller, more meaningful representation of the data.

## Concepts I Learned

- The curse of dimensionality (why high dimensions are hard)
- Projection vs manifold learning
- Principal Component Analysis (PCA)
- Explained variance ratio
- Choosing the number of components
- Incremental PCA for large datasets
- Non-linear methods (e.g. t-SNE) for visualization

## Important Terms (Simple Explanation)

- **Dimensionality reduction:** turning many features into fewer, more informative ones
- **Curse of dimensionality:** in very high dimensions, data becomes sparse and distances become less meaningful
- **Projection:** mapping data onto a lower-dimensional subspace
- **Principal Components:** directions of maximum variance in the data
- **Explained variance:** how much of the original data variation is captured by a set of components

## My Personal Reflection

I used to think more features are always better, but this chapter changed my mind.  
Now I see that too many weak or noisy features can confuse the model and make everything harder to visualize.

<details>
  <summary>What I found difficult</summary>
  The mathematical derivation of PCA was challenging.  
  For now, I focus on the intuition: PCA finds directions where the data varies the most and keeps those as new axes.
</details>

## Real-World Examples

- Compressing image data before training models
- Reducing dimensionality of word embeddings for visualization
- Speeding up training for models on large tabular datasets

## Key Takeaways

1. More features are not always better; high-dimensional spaces can hurt performance.
2. PCA is a powerful tool for finding a compact representation of the data.
3. Dimensionality reduction is especially helpful before visualization and some algorithms.

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

This chapter taught me that simplifying my feature space can make models faster, easier to train, and sometimes more accurate.  
I now see dimensionality reduction as a useful tool in my ML toolbox, especially before visualization or complex modeling.

## Key Insights I'm Taking Forward

- Before adding more and more features, I should think about whether I can **summarize** existing ones with PCA or similar methods.
- Visualizing high-dimensional data (e.g. with t-SNE) is a great way to build intuition about clusters and structure.
- Dimensionality reduction is not just a pre-processing step—it's part of designing a good representation of the problem.
