## Challenge: Create a Stacked Model

### Challenge Overview

* The goal is to experiment with stacking different models together.
* You can include not just simple models like decision trees but also ensemble models inside the stacking ensemble.
* Aim: Improve performance compared to individual models.

### Solution Steps

1. **Boilerplate Code**: Start by copying your existing stacking setup.

   * Original model score: 0.822

2. **Add Different Models**:

   * Introduce `RandomForestClassifier` with `random_state=42` for consistency.
   * Introduce `AdaBoostClassifier`.

3. **Implementation**:

   ```python
   from sklearn.ensemble import RandomForestClassifier, AdaBoostClassifier, StackingClassifier
   from sklearn.tree import DecisionTreeClassifier
   from sklearn.neighbors import KNeighborsClassifier

   estimators = [
       ('decision_tree', DecisionTreeClassifier(max_depth=3)),
       ('knn', KNeighborsClassifier()),
       ('random_forest', RandomForestClassifier(random_state=42)),
       ('adaboost', AdaBoostClassifier())
   ]

   stacked_model = StackingClassifier(estimators=estimators, final_estimator=LogisticRegression())

   stacked_model.fit(X_train_transformed, y_train)
   score = stacked_model.score(X_test_transformed, y_test)
   print(score)
   ```

4. **Result**:

   * New stacked model score: 0.828
   * Slight improvement over original stacking (0.822)

5. **Individual Scores in Ensemble**:

   * Loop over each estimator to check individual performance.
   * Observe that combining them gives a slight boost, but still less than XGBoost out-of-the-box.

6. **Insights**:

   * XGBoost often outperforms a stacked ensemble of simple models.
   * Recommended approach: start with simple models, then compare with XGBoost.
   * Optionally, include XGBoost in the stacking ensemble for potential further improvements.
