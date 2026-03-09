# Chapter 3 - Classification

## Chapter Overview

In this chapter, I learned how classification works (especially with MNIST).  
Unlike regression, classification predicts category labels instead of continuous values.

> **Important idea:** Accuracy alone is not enough for many classification problems.

## Concepts I Learned

- Binary classification
- Multiclass classification
- Multilabel classification
- Decision scores and thresholds
- Evaluating with multiple metrics
- The idea of precision–recall trade-off
- How ROC and PR curves tell different stories

## Important Terms (Simple Explanation)

- **Confusion matrix:** table of correct and wrong predictions
- **Precision:** among predicted positives, how many were correct
- **Recall:** among actual positives, how many were found
- **F1-score:** balance between precision and recall
- **ROC curve:** trade-off between true positive and false positive rates
- **Precision–Recall curve:** focuses on performance on the positive class, useful for imbalanced data

## My Personal Reflection

This chapter helped me think more deeply about model quality.  
I learned that metric choice depends on what kind of mistake matters more.

<details>
  <summary>What confused me at first?</summary>
  I mixed up precision and recall.  
  Confusion matrix examples helped me separate them clearly.
</details>

## Real-World Examples

- Medical diagnosis (disease / no disease)
- Spam detection
- Document/news category classification

## Key Takeaways

1. Accuracy can be misleading for imbalanced data.
2. Precision and recall tell different stories.
3. Threshold tuning can change model behavior a lot.

## Mini Quiz

1. Why can high accuracy still be bad in imbalanced datasets?

<details>
  <summary>Show answer</summary>
  A model can predict the majority class most of the time and still miss important minority cases.
</details>

2. What does a confusion matrix help us see?

<details>
  <summary>Show answer</summary>
  It shows where the model is correct and what kinds of mistakes it makes.
</details>

## Summary

This chapter taught me to evaluate classifiers more carefully and choose metrics based on problem goals.

## Key Insights I'm Taking Forward

- I should always ask: **what type of error hurts more here**—false positives or false negatives?
- For tasks like fraud detection or medical screening, I must look at **precision and recall**, not just a single accuracy number.
- Confusion matrices and PR curves help me see exactly which groups or classes the model is failing on, so I can design fixes (more data, new features, class weighting, etc.).

### Extra Notes from the Book

- For highly imbalanced datasets, Precision–Recall curves are often more informative than ROC curves.
- Choosing the right threshold is part of the model design, not just a small detail.
