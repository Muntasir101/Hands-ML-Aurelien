# Chapter 3 - Classification

## Chapter Overview

Classification is one of the most common Machine Learning tasks. This chapter focuses on the MNIST dataset (70,000 small images of digits handwritten by high school students and employees of the US Census Bureau) to explore various classification challenges and metrics.

## Performance Measures

Unlike regression, evaluating a classifier is often significantly trickier, especially with imbalanced datasets.

### 1. Confusion Matrix
A much better way to evaluate the performance of a classifier is to look at the **Confusion Matrix**. It counts the number of times instances of class A are classified as class B.
- **True Positives (TP)**: Correctly predicted positive.
- **True Negatives (TN)**: Correctly predicted negative.
- **False Positives (FP)**: Predicted positive, but actually negative (Type I error).
- **False Negatives (FN)**: Predicted negative, but actually positive (Type II error).

### 2. Precision and Recall
- **Precision**: Accuracy of the positive predictions.
  $$\text{Precision} = \frac{TP}{TP + FP}$$
- **Recall (Sensitivity/True Positive Rate)**: Ratio of positive instances correctly detected by the classifier.
  $$\text{Recall} = \frac{TP}{TP + FN}$$

### 3. F1 Score
The harmonic mean of precision and recall. It gives much more weight to low values.
$$\text{F1} = \frac{2}{\frac{1}{\text{Precision}} + \frac{1}{\text{Recall}}}$$

## Precision/Recall Trade-off

Increasing precision reduces recall, and vice-versa. Classifiers compute a score based on a **Decision Function**. If that score is greater than a **threshold**, it assigns the instance to the positive class.

> [!IMPORTANT]
> To decide which threshold to use, you can use the `precision_recall_curve()` function to compute precision and recall for all possible thresholds.

## The ROC Curve

The **Receiver Operating Characteristic (ROC)** curve plots the **True Positive Rate (Recall)** against the **False Positive Rate (1 - Specificity)**.
- **AUC (Area Under the Curve)**: A perfect classifier will have a ROC AUC equal to 1, whereas a purely random classifier will have a ROC AUC equal to 0.5.

## Multiclass Classification

While some algorithms (like Random Forest or Naive Bayes) can handle multiple classes directly, others (like SVM or Linear Classifiers) are strictly binary.
- **One-versus-the-Rest (OvR)**: Train 10 binary classifiers (one for each digit) and select the one with the highest score.
- **One-versus-One (OvO)**: Train a binary classifier for every pair of digits (N * (N-1) / 2 classifiers). Preferred for algorithms that scale poorly with the size of the training set (like SVM).

## Professional Evaluation (Code Snippet)

```python
from sklearn.metrics import confusion_matrix, precision_score, recall_score, f1_score
from sklearn.model_selection import cross_val_predict

# Get predictions using K-fold cross-validation
y_train_pred = cross_val_predict(sgd_clf, X_train, y_train_5, cv=3)

# Evaluate
print("Confusion Matrix:\n", confusion_matrix(y_train_5, y_train_pred))
print("Precision:", precision_score(y_train_5, y_train_pred))
print("Recall:", recall_score(y_train_5, y_train_pred))
print("F1 Score:", f1_score(y_train_5, y_train_pred))
```

## Summary Checklist
- [x] Analyzed the Confusion Matrix to identify specific errors.
- [x] Evaluated the Precision/Recall trade-off.
- [x] Plotted the ROC Curve and calculated AUC.
- [x] Selected the appropriate Multiclass strategy (OvR vs OvO).
- [x] Addressed imbalanced classes using appropriate metrics (PR Curve over ROC).

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*
