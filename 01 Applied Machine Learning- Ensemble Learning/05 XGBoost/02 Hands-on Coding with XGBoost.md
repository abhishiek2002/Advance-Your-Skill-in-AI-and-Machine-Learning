# Hands-on Coding with XGBoost

## Overview

In this section, we perform a practical demonstration of using XGBoost, following a methodology similar to our previous models. We'll explore how the number of trees impacts model performance and how XGBoost handles categorical data and labels.

## Key Concepts

* **XGBoost** works by incrementally improving predictions, similar to golfing. Each subsequent tree corrects the errors of the previous one.
* **Weak learners:** Each individual tree is shallow, contributing incrementally to the overall model.
* **Learning rate:** Controls the contribution of each tree to the final prediction. Red bars in the plots are scaled according to the learning rate, showing gradual adjustments.
* **Transparency in plots:** More recent trees are darker, indicating their incremental influence on the prediction.

## Implementation Steps

1. **Looping over different tree counts:**

   * Trees considered: 1, 2, 5, 10, 20, 50.
   * Visualizing individual and cumulative predictions helps see how errors are corrected over iterations.

2. **Observation of trends:**

   * One tree: Weak performance, large prediction errors.
   * Two trees: Correction begins, some errors reduced.
   * Five trees: More noticeable corrections, adjustments on both ends.
   * Twenty trees: Predictions closely track trends in the data.
   * Fifty trees: Signs of overfitting appear; the model may start capturing noise.

3. **Applying XGBoost on larger dataset:**

   * No pipeline needed.
   * Fit using `X_train`.
   * Enable categorical feature handling with `enable_categorical=True`.
   * Convert string labels to Boolean (e.g., `y_train == '>5K'`) because XGBoost prefers Boolean labels.

4. **Model evaluation:**

   * Achieved accuracy: 87%.
   * Comparison: Previous models (Random Forest, AdaBoost, Gradient Boosting) achieved around 82-83%.
   * Out-of-the-box XGBoost can overfit but still provides strong performance.

## Key Takeaways

* XGBoost efficiently improves predictions incrementally using weak learners.
* Learning rate and tree count control the pace of error correction and model complexity.
* Visual inspection of predictions across trees helps identify overfitting.
* Handling categorical data and Boolean labels is straightforward in XGBoost.
* Even out-of-the-box, XGBoost can outperform other ensemble methods.

This demo highlights why XGBoost is a popular choice for tabular datasets due to its simplicity, performance, and incremental improvement approach.
