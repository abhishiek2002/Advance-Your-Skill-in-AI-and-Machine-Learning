# Concept of Bagging (Bootstrap Aggregating)

## 📌 What is Bagging?

Bagging stands for **Bootstrap Aggregating** — a technique used to improve the accuracy and robustness of machine learning models.

* **Process**:

  1. Create multiple subsets of the dataset (via bootstrapping = sampling with replacement).
  2. Train a separate model on each subset.
  3. Combine the predictions of these models (e.g., averaging for regression, majority vote for classification).

👉 The key idea: **Reduce variance** by combining multiple weak learners into a more stable predictor.

---

## 🌲 Random Forest: Popular Bagging Implementation

Random Forest is the most widely used bagging algorithm:

* Splits dataset into multiple random subsets.
* Trains **decision trees** on each subset.
* Combines tree outputs into a final prediction.

This ensures that:

* Each tree learns different aspects of the data.
* The final model generalizes better, avoiding overfitting.

---

## 🎯 Example Walkthrough with Code

### Step 1: Import Libraries

```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
from sklearn.ensemble import RandomForestRegressor
import warnings

warnings.filterwarnings("ignore")
```

### Step 2: Visualizing Bootstrapped Trees

```python
fig, ax = plt.subplots(2, 3, figsize=(12, 8))

for seed, axis in enumerate(ax.ravel(), start=1):
    # Example: sample subset of data
    model = RandomForestRegressor(n_estimators=1, max_samples=0.01, random_state=seed)
    model.fit(X, y)
    
    x_vals = np.linspace(X.min(), X.max(), 100).reshape(-1, 1)
    y_pred = model.predict(x_vals)
    
    axis.scatter(X, y, alpha=0.4)
    axis.plot(x_vals, y_pred, color='red')
    axis.set_title(f"Tree with seed {seed}")
```

Each subplot shows a single tree trained on a different subset of the data. Notice how each tree captures different parts of the trend.

---

### Step 3: Combining Trees into a Random Forest

```python
n_trees = [1, 2, 5, 10, 20, 50]

fig, ax = plt.subplots(2, 3, figsize=(12, 8))

for n, axis in zip(n_trees, ax.ravel()):
    model = RandomForestRegressor(n_estimators=n, max_samples=0.1, random_state=42)
    model.fit(X, y)

    x_vals = np.linspace(X.min(), X.max(), 100).reshape(-1, 1)
    y_pred = model.predict(x_vals)
    
    axis.scatter(X, y, alpha=0.4)
    axis.plot(x_vals, y_pred, color='red')
    axis.set_title(f"Random Forest with {n} trees")
```

* With **1 tree**, predictions are noisy.
* With **more trees**, predictions become smoother and follow the true trend.

---

## ⚙️ Interactive Exploration with ipywidgets

Using `ipywidgets`, you can:

* Adjust **tree depth** (shallow vs deep trees).
* Adjust **sample size** (how much data each tree sees).

This helps visualize:

* Shallow trees underfit.
* Deep trees may overfit.
* But when combined (via bagging), even deep trees generalize better.

---

## ✅ Key Takeaways

* Bagging works by training models on **different subsets** of data and combining results.
* It helps reduce **variance** and prevents **overfitting**.
* **Random Forest** is the most popular and effective implementation.
* More trees generally improve performance (until diminishing returns).

---

## 📜 Full Code (Combined)

```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
from sklearn.ensemble import RandomForestRegressor
import warnings

warnings.filterwarnings("ignore")

# Example dataset (replace with your own)
X = np.sort(5 * np.random.rand(80, 1), axis=0)
y = np.sin(X).ravel() + np.random.randn(80) * 0.1

# Visualize single-tree subsets
fig, ax = plt.subplots(2, 3, figsize=(12, 8))
for seed, axis in enumerate(ax.ravel(), start=1):
    model = RandomForestRegressor(n_estimators=1, max_samples=0.1, random_state=seed)
    model.fit(X, y)
    x_vals = np.linspace(X.min(), X.max(), 100).reshape(-1, 1)
    y_pred = model.predict(x_vals)
    axis.scatter(X, y, alpha=0.4)
    axis.plot(x_vals, y_pred, color='red')
    axis.set_title(f"Tree with seed {seed}")

# Visualize Random Forest with increasing number of trees
n_trees = [1, 2, 5, 10, 20, 50]
fig, ax = plt.subplots(2, 3, figsize=(12, 8))
for n, axis in zip(n_trees, ax.ravel()):
    model = RandomForestRegressor(n_estimators=n, max_samples=0.1, random_state=42)
    model.fit(X, y)
    x_vals = np.linspace(X.min(), X.max(), 100).reshape(-1, 1)
    y_pred = model.predict(x_vals)
    axis.scatter(X, y, alpha=0.4)
    axis.plot(x_vals, y_pred, color='red')
    axis.set_title(f"Random Forest with {n} trees")
plt.show()
```
