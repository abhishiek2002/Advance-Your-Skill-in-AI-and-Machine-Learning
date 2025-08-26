## AdaBoost and Gradient Boosting

### Overview

In this section, we explore AdaBoost and Gradient Boosting using both intuitive examples and real-world datasets. These ensemble methods build on the idea of sequentially improving predictions by learning from previous errors.

---

### AdaBoost (Adaptive Boosting)

* **Concept**: Starts with a weak learner (e.g., a shallow decision tree) and sequentially adds models that focus on correcting the errors of the previous models.
* **Code Example**:

  * We create an `AdaBoostRegressor` and specify the number of trees.
  * We provide a backing estimator, in this case a decision tree with `max_depth=3`.
  * Predictions are visualized: each subsequent tree (gray line) attempts to correct the errors of the previous model, while the final prediction is shown in red.
* **Observation**:

  * With a small number of trees (e.g., 2), we can already see corrections happening.
  * Increasing the number of trees beyond 20 shows minimal improvement for this dataset, indicating that after a certain point, additional trees do not significantly enhance the model.
  * Applying AdaBoost to the real-world housing dataset gives **82% accuracy**, comparable to Random Forest.

### Gradient Boosting

* **Concept**: Similar to AdaBoost but adds gradient descent optimization to sequentially reduce residual errors.
* **Code Example**:

  * We plot predictions from `GradientBoostingRegressor`.
  * Initially, a dummy regressor predicts the mean value.
  * Subsequent trees correct the errors of previous predictions.
* **Hyperparameters**:

  * `n_estimators`: Number of boosting stages/trees.
  * `max_depth`: Maximum depth of each tree.
  * `learning_rate`: Damps each tree's contribution to prevent overfitting. In the example, `learning_rate=0.1` ensures incremental improvements instead of large overcorrections.
* **Observation**:

  * Early trees correct major errors, later trees refine smaller deviations.
  * Smoothness of predictions can vary depending on data distribution.
  * Applied to the housing dataset, Gradient Boosting also yields **82% accuracy**, matching Random Forest and AdaBoost.

### Key Takeaways

1. **Sequential Correction**: Both AdaBoost and Gradient Boosting improve predictions iteratively by addressing previous errors.
2. **Hyperparameter Tuning**: Number of estimators, max depth, and learning rate are crucial to control overfitting and performance.
3. **Practical Performance**: For the given dataset, all three models—Random Forest, AdaBoost, and Gradient Boosting—achieved similar accuracy (\~82%), highlighting that model choice and tuning depend on the dataset.

---

This concludes the demonstration of AdaBoost and Gradient Boosting on intuitive and real-world datasets.
