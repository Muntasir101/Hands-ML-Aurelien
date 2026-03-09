# Chapter 4 - Training Models

## Chapter Overview

This chapter helped me understand how models are actually trained, not just used.  
I learned the core idea of minimizing a cost function so the model predictions get closer to real values.

> **Important idea:** Training is basically an optimization problem where we try to reduce error step by step.

## Concepts I Learned

- Linear regression basics
- Normal Equation approach
- Gradient Descent (Batch, Stochastic, Mini-batch)
- Learning rate and convergence
- Polynomial regression (for non-linear patterns)

## Important Terms (Simple Explanation)

- **Cost function:** a score that shows how wrong the model is
- **Gradient Descent:** method to reduce error by moving parameters in better directions
- **Learning rate:** step size of each update
- **Convergence:** when training reaches a stable low-error area
- **Underfitting / Overfitting:** model too simple vs too complex

## My Personal Reflection

I enjoyed this chapter because it made model training feel mathematical but still practical.  
At first I felt confused about why learning rate matters so much, but now I see that too small is slow and too large can overshoot.

<details>
  <summary>What I found difficult</summary>
  I struggled with the difference between Batch GD and Stochastic GD.  
  My current understanding: Batch uses all data each step (stable but slow), while SGD updates faster with one sample (noisy but efficient).
</details>

## Real-World Examples

- Predicting house prices with linear regression
- Estimating sales trends over time
- Modeling simple risk score relationships

## Key Takeaways

1. Model training means minimizing a cost function.
2. Gradient Descent is powerful but sensitive to learning rate.
3. Adding model complexity can help, but may cause overfitting.

## Mini Quiz

1. Why is learning rate important in Gradient Descent?

<details>
  <summary>Show answer</summary>
  It controls update size. Too large can miss the minimum, too small makes training very slow.
</details>

2. What is one key difference between Batch GD and SGD?

<details>
  <summary>Show answer</summary>
  Batch GD uses the full dataset per update; SGD uses one sample at a time.
</details>

## Summary

This chapter made me understand the "how" behind training models.  
Now I can connect formulas, optimization, and practical model behavior better.
