# Hands-on coding with StackingClassifier

In this example, we'll implement a stacking ensemble using scikit-learn's `StackingClassifier`. Stacking allows us to combine multiple models to leverage their strengths and improve overall prediction accuracy.

## Step 1: Import Base Models and StackingClassifier

```python
from sklearn.tree import DecisionTreeClassifier
from sklearn.neighbors import KNeighborsClassifier
from sklearn.ensemble import StackingClassifier
```

## Step 2: Define Base Models

We create a list of tuples, each containing the name of the model and the model itself:

```python
estimators = [
    ('decision_tree', DecisionTreeClassifier()),
    ('knn', KNeighborsClassifier())
]
```

## Step 3: Create the StackingClassifier

```python
stacking_model = StackingClassifier(estimators=estimators)
```

## Step 4: Preprocess Data with a Pipeline

If you have a preprocessing pipeline, you can transform your data before feeding it into the stacking model:

```python
X_train_transformed = pipeline.fit_transform(X_train)
X_test_transformed = pipeline.transform(X_test)
```

## Step 5: Fit the Model

```python
stacking_model.fit(X_train_transformed, y_train)
```

## Step 6: Evaluate Model Accuracy

```python
accuracy = stacking_model.score(X_test_transformed, y_test)
print(f"Stacking model accuracy: {accuracy}")
```

### Notes:

* In this example, the stacking ensemble used a `DecisionTreeClassifier` and `KNeighborsClassifier` as base models.
* The final stacking model achieved an accuracy of **0.822**, which is comparable to other models but slightly lower than XGBoost.
* Stacking is particularly useful for combining models that capture different patterns in the data.
* Consider using more diverse base models or tuning hyperparameters for potential improvements.
