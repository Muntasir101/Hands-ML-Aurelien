# Chapter 6 - Decision Trees

## Chapter Overview

In this chapter, I learned how Decision Trees make predictions by splitting data step by step.  
I liked this chapter because the model is easy to visualize and explain.

> **Important idea:** Decision Trees are very interpretable, but they can overfit if not controlled.

## Concepts I Learned

- Tree structure: root, internal nodes, leaves
- Splitting criteria (Gini impurity / entropy)
- Maximum depth and regularization
- Overfitting in deep trees
- Regression trees

## Important Terms (Simple Explanation)

- **Node:** a decision point in the tree
- **Leaf:** final output node (prediction)
- **Gini impurity:** measure of class mixing in a node
- **Entropy:** another impurity measure used for splitting
- **Pruning / regularization:** methods to keep tree from becoming too complex

## My Personal Reflection

This chapter felt intuitive because I could follow each decision path.  
At the same time, I learned that a tree can memorize training data too easily if we let it grow without limits.

<details>
  <summary>What I found difficult</summary>
  I was confused about when to use Gini vs entropy.  
  My understanding now is that both are valid and often produce similar trees, so tuning and validation matter more.
</details>

## Real-World Examples

- Loan approval decision systems
- Customer churn prediction
- Basic medical decision support

## Key Takeaways

1. Decision Trees are easy to explain and visualize.
2. Without constraints, trees can overfit quickly.
3. Hyperparameters like max depth are important for generalization.

## Mini Quiz

1. Why can very deep trees perform poorly on test data?

<details>
  <summary>Show answer</summary>
  Because they may overfit training data and fail to generalize to unseen examples.
</details>

2. What does a leaf node represent?

<details>
  <summary>Show answer</summary>
  The final prediction output after following decision splits.
</details>

## Summary

This chapter gave me a practical and interpretable model type.  
I now understand how trees split data and why controlling complexity is necessary.
