## Challenge: Tune XGBoost Model (Gamma)

**Objective:** Find the value of gamma that maximizes accuracy for XGBoost.

### Solution: Step-by-Step

1. **Copy Previous Code:**

   * Start by duplicating your previous XGBoost tuning code.
   * Update variable names from generic (`values`) to `gamma`.

2. **Define Gamma Values:**

   * Gamma is a regularization term that simplifies the model to prevent overfitting.
   * Start with a set of candidate values: `0, 0.1, 1, 5, 10`.

3. **Update the Model Loop:**

   * Replace any references to previous hyperparameters (like `max_depth`) with `gamma` in the estimator setup.
   * Example in scikit-learn XGBoost API:

   ```python
   for g in gamma_values:
       model = XGBClassifier(gamma=g, max_depth=3, n_estimators=100, learning_rate=0.1)
       model.fit(X_train, y_train)
       score = model.score(X_test, y_test)
       print(f'Gamma: {g}, Test Accuracy: {score}')
   ```

4. **Plot Results:**

   * Plot testing accuracy vs gamma values to visualize performance.
   * Example:

   ```python
   plt.plot(gamma_values, test_scores, marker='o')
   plt.title('XGBoost Classifier Accuracy vs Gamma')
   plt.xlabel('Gamma')
   plt.ylabel('Test Accuracy')
   plt.show()
   ```

5. **Interpret Results:**

   * At gamma = 0, the model is overfitting.
   * As gamma increases, the model regularizes and the training score decreases, aligning more with the test score.
   * If gamma is too high, the model underfits, reducing accuracy.
   * In this example, gamma ≈ 5 gives the best performance (Goldilocks point).

### Key Insights

* Gamma controls the complexity of the model by applying a penalty.
* Low gamma → risk of overfitting.
* High gamma → risk of underfitting.
* Optimal gamma balances model complexity and generalization to maximize accuracy.

**Result:** Optimal gamma for this dataset is around `5`, providing the highest test accuracy.
