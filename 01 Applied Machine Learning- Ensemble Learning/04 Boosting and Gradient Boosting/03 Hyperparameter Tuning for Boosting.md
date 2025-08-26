# Hyperparameter Tuning for Boosting

## Overview

This section focuses on hyperparameter tuning for boosting algorithms, specifically AdaBoost and Gradient Boosting. Tuning hyperparameters helps control the model's behavior, improve performance, and prevent overfitting.

---

## AdaBoost Hyperparameters

1. **n\_estimators**:

   * Represents the number of boosting stages or weak learners.
   * Setting `n_estimators = 1` essentially uses the base estimator without boosting.
   * Increasing the number progressively improves predictions by correcting errors of previous models.

2. **learning\_rate**:

   * Controls the contribution of each weak learner to the final prediction.
   * Default is 1. Reducing this value slows down learning (like taking smaller steps), potentially leading to better results.

3. **estimator**:

   * The base learner to be used in boosting, typically a decision tree.
   * Other models can also be used, but the base estimator's hyperparameters themselves need tuning.

> Note: AdaBoost has fewer hyperparameters; most additional adjustments come from the base estimator.

---

## Gradient Boosting Hyperparameters

1. **n\_estimators**:

   * Number of boosting stages.
   * Each stage corrects the errors of previous trees.
   * Example range: 1, 5, 10, 20, 50, 70, 100, 150, 200.

2. **learning\_rate**:

   * Weight of each tree's contribution to the final model.
   * Value between 0 and 1.
   * Lower values reduce overfitting by taking smaller steps toward correction.

3. **max\_depth**:

   * Maximum depth of each tree.
   * Controls model complexity; higher values can lead to overfitting.

4. **subsample**:

   * Fraction of samples used for training each tree.
   * Reduces overfitting by introducing randomness and preventing each tree from capturing all noise.

---

## Example Interpretation: Gradient Boosting

* With 1 estimator, performance is equivalent to a single decision tree (\~76% accuracy).
* As more estimators are added, the model corrects residual errors, increasing accuracy.
* Accuracy plateaus after a certain number of estimators (e.g., \~150), indicating additional trees do not improve performance.
* Divergence between training (orange line) and testing accuracy (blue line) signals potential overfitting.
* To avoid overfitting, limit the number of trees and tune learning rate appropriately.

---

## Key Takeaways

1. Hyperparameter tuning is essential to maximize model performance.
2. Hyperparameters that work for one dataset may not generalize to another.
3. n\_estimators, learning\_rate, max\_depth, and subsample are major levers in boosting algorithms.
4. Monitoring training vs. testing accuracy helps detect overfitting.
5. The goal is to balance correcting errors and avoiding noise memorization.

---

By understanding and adjusting these hyperparameters, we can build more robust and accurate boosting models tailored to specific datasets.
