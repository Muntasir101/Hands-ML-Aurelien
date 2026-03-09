# Chapter 7 - Ensemble Learning and Random Forests

## Chapter Overview

If you aggregate the predictions of a group of predictors (such as classifiers or regressors), you will often get better predictions than with the best individual predictor. A group of predictors is called an **ensemble**; thus, this technique is called Ensemble Learning.

## Voting Classifiers

- **Hard Voting Classifier**: The class that receives the highest number of votes is the ensemble’s prediction.
- **Soft Voting Classifier**: If all classifiers are able to estimate class probabilities, you can tell Scikit-Learn to predict the class with the highest class probability, averaged over all the individual classifiers. This often achieves higher performance because it gives more weight to highly confident votes.

## Bagging and Pasting

One way to get a diverse set of classifiers is to use the same training algorithm for every predictor and train them on different random subsets of the training set.
- **Bagging (Bootstrap Aggregating)**: When sampling is performed *with* replacement.
- **Pasting**: When sampling is performed *without* replacement.

> [!TIP]
> **Out-of-Bag (oob) Evaluation**: With bagging, some instances may be sampled several times for any given predictor, while others may not be sampled at all. You can evaluate the ensemble by averaging the predictions on these oob instances.

## Random Forests

A Random Forest is an ensemble of Decision Trees, generally trained via the bagging method. Instead of searching for the very best feature when splitting a node, it searches for the best feature among a random subset of features. This results in greater tree diversity, which trades a higher bias for a lower variance.

```python
from sklearn.ensemble import RandomForestClassifier

rnd_clf = RandomForestClassifier(n_estimators=500, max_leaf_nodes=16, n_jobs=-1)
rnd_clf.fit(X_train, y_train)
```

## Boosting

Boosting refers to any Ensemble method that can combine several weak learners into a strong learner. The general idea is to train predictors sequentially, each trying to correct its predecessor.
- **AdaBoost (Adaptive Boosting)**: Each predictor pays more attention to the training instances that the predecessor underfitted.
- **Gradient Boosting**: Instead of tweaking instance weights at every iteration like AdaBoost, this method tries to fit the new predictor to the *residual errors* made by the previous predictor.

```python
from sklearn.ensemble import GradientBoostingRegressor

gbrt = GradientBoostingRegressor(max_depth=2, n_estimators=3, learning_rate=1.0)
gbrt.fit(X, y)
```

## Stacking (Stacked Generalization)

Instead of using trivial functions (such as hard voting) to aggregate the predictions of all predictors in an ensemble, why don’t we train a model to perform this aggregation? This model is called a **blender** or a **meta-learner**.

## Summary Checklist
- [x] Evaluated Hard vs Soft Voting performance.
- [x] Used oob evaluation to estimate generalization error without a validation set.
- [x] Analyzed feature importance using Random Forest properties.
- [x] Implemented Early Stopping with Gradient Boosting to prevent overfitting.

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*
