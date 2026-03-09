# Chapter 5 - Support Vector Machines (SVM)

## Chapter Overview

Support Vector Machines (SVM) are powerful and versatile Machine Learning models capable of performing linear or nonlinear classification, regression, and even outlier detection. SVMs are particularly well-suited for classification of complex small- or medium-sized datasets.

## Linear SVM Classification

The fundamental idea behind SVMs is to find the "widest possible street" between classes. This is called **Large Margin Classification**.
- **Support Vectors**: The instances located on the edge of the "street". The decision boundary is entirely determined by these vectors.
- **Hard Margin Classification**: Strictly imposes that all instances must be off the street and on the right side. Only works if the data is linearly separable and is very sensitive to outliers.
- **Soft Margin Classification**: Finds a good balance between keeping the street as large as possible and limiting the margin violations (i.e., instances that end up in the middle of the street or even on the wrong side).

> [!TIP]
> Use the **C hyperparameter** to control this balance: a smaller `C` leads to a wider street but more margin violations (high bias, low variance).

## Nonlinear SVM Classification

When datasets are not linearly separable, we can add nonlinear features (like polynomial features).
- **Polynomial Kernel**: Instead of adding features, we use a mathematical technique to get the same result without actually adding them (**Kernel Trick**).
- **Similarity Features (Gaussian RBF Kernel)**: Adds features computed using a similarity function, which measures how much each instance resembles a particular landmark.

```python
from sklearn.svm import SVC
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler

# Nonlinear SVM with RBF Kernel
rbf_kernel_svm_clf = Pipeline([
    ("scaler", StandardScaler()),
    ("svm_clf", SVC(kernel="rbf", gamma=5, C=0.001))
])
rbf_kernel_svm_clf.fit(X, y)
```

## SVM Regression

SVMs also support linear and nonlinear regression. Instead of trying to fit the largest possible street between two classes while limiting margin violations, SVM Regression tries to fit as many instances as possible *on* the street while limiting margin violations (i.e., instances *off* the street).

```python
from sklearn.svm import LinearSVR

svm_reg = LinearSVR(epsilon=1.5)
svm_reg.fit(X, y)
```

## Internal Mechanics (Brief)

- **Decision Function**: $h(\mathbf{x}) = \mathbf{w}^T \mathbf{x} + b$.
- **The Dual Problem**: Solving the dual problem is faster when the number of training instances is smaller than the number of features. It also makes the kernel trick possible.

## Summary Checklist
- [x] Scaled the features (SVMs are sensitive to feature scales).
- [x] Chose between LinearSVC and SVC(kernel="poly"/"rbf").
- [x] Tuned the `C` hyperparameter to balance bias vs variance.
- [x] Evaluated SVM Regression for continuous output tasks.

---
*Reference: "Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow" by Aurélien Géron.*
