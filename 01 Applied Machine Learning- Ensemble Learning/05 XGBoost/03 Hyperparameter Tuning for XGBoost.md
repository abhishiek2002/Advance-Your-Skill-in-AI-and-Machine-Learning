# Hyperparameter Tuning for XGBoost

## Overview

In this section, we focus on hyperparameter tuning for XGBoost, one of the most powerful gradient boosting algorithms. XGBoost is highly performant out of the box, but can overfit if not carefully tuned. Hyperparameters allow us to control the behavior of the model and optimize performance.

## Key Hyperparameters

1. **max\_depth**:

   * Controls the depth of each tree.
   * Shallower trees are generally preferred because each subsequent tree corrects the errors of previous trees.

2. **eta (learning\_rate)**:

   * A value between 0 and 1.
   * Shrinks the contribution of each tree to avoid overshooting the target.
   * Lower eta often requires increasing the number of trees (`n_estimators`).

3. **subsample and colsample\_bytree**:

   * Control how much of the data is sampled for individual trees.
   * Helps prevent overfitting by training on different subsets of data.

4. **gamma**:

   * Regularization parameter.
   * Higher gamma can simplify the model and reduce overfitting.

## Observations from Max Depth Tuning

* A plot of training vs testing scores helps visualize the impact of `max_depth`.
* **Testing score (blue line)**: Main metric of interest, reflects performance on unseen data.
* **Training score (orange line)**: Helps detect overfitting.
* As `max_depth` increases:

  * Training accuracy can approach 100%.
  * Testing accuracy may plateau or decrease if the model overfits.
* For this dataset:

  * Optimal `max_depth` is around 3.
  * Default `max_depth` is 6.
  * Increasing beyond 3 leads to divergence between training and testing scores, indicating overfitting.
* Surprisingly, a very deep tree (depth 15) gives a testing score of 86%, better than some non-overfit models, highlighting XGBoost's robustness.

## Tuning Result

* By setting `max_depth` to 3:

  * Model accuracy improved from 0.875 to 0.878 (87.8%).
  * Demonstrates that careful tuning of hyperparameters can yield modest but meaningful gains.

## Takeaways

* XGBoost performs well out of the box but can overfit.
* Hyperparameters like `max_depth`, `eta`, `subsample`, `colsample_bytree`, and `gamma` are critical for controlling overfitting.
* Use plots of training vs testing scores to guide tuning decisions.
* Optimal hyperparameters are dataset-specific and require experimentation.

**Next Steps:**

* Explore tuning other XGBoost hyperparameters.
* Use grid search or Bayesian optimization tools for systematic hyperparameter optimization.
