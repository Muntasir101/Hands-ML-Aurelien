# Chapter 2 - End-to-End Machine Learning Project

## Chapter Overview

This chapter showed me a complete ML workflow using a housing dataset.  
I liked this chapter because it felt practical and close to real-world project work.

> **Important idea:** A strong workflow prevents common mistakes like data leakage.

## Concepts I Learned

- Framing the business problem
- Creating train/test sets early
- Data exploration with statistics and visualizations
- Feature engineering and preprocessing pipelines
- Model evaluation and tuning

## Important Terms (Simple Explanation)

- **Data leakage:** when training accidentally uses information from test data
- **Pipeline:** ordered steps for preprocessing + model training
- **Cross-validation:** repeated splits of training data to estimate performance
- **RMSE:** common regression error metric; lower is better

## My Personal Reflection

This chapter made ML feel structured and realistic.  
I also realized how easy it is to get overconfident if evaluation is not done carefully.

<details>
  <summary>What was most challenging for me?</summary>
  At first, I did not understand why we should not touch the test set early.  
  Now I see it gives an honest final estimate of model performance.
</details>

## Real-World Examples

- House price prediction
- Demand forecasting
- Delivery time prediction

## Key Takeaways

1. Keep the test set separate from the beginning.
2. Use pipelines for consistency and reproducibility.
3. Compare multiple models before selecting one.

## Mini Quiz

1. Why do we split train and test data early?

<details>
  <summary>Show answer</summary>
  To prevent accidental overfitting to the test set and keep final evaluation honest.
</details>

2. What is one benefit of using a pipeline?

<details>
  <summary>Show answer</summary>
  It keeps preprocessing steps consistent and reduces manual mistakes.
</details>

## Summary

I now have a clear ML project checklist: define, split, explore, prepare, train, validate, tune, test.
