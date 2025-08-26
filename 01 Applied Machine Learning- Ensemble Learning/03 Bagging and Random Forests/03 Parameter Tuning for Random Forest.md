# Parameter Tuning for Random Forest

In this section, we explore the **hyperparameters** of a Random Forest and how tuning them can improve (or harm) performance.

---

## 🔧 What Are Hyperparameters?

* **Parameters** in programming control the behavior of a function.
* **Hyperparameters** are parameters that control how an algorithm itself works.
* In Random Forests, hyperparameters decide *how trees are built* and *how the forest combines them*.

---

## 🌲 Key Hyperparameters in Random Forest

### 1. `n_estimators`

* Number of trees in the forest.
* More trees → smoother, more stable predictions.
* Too many trees = longer training time, but usually not harmful for accuracy.

### 2. `max_depth`

* Controls the maximum depth of each decision tree.
* `max_depth = 1` → a **decision stump** (very simple, underfits).
* Large `max_depth` → very complex tree (may overfit).
* The sweet spot is usually *in the middle*.

### 3. `max_features`

* Number of features to consider when splitting a node.
* Controls the randomness of the forest.
* Smaller `max_features` → more diverse trees.

👉 There are more hyperparameters (`min_samples_split`, `min_samples_leaf`, etc.), but these three are the most impactful.

---

## 📊 Example: Sweeping `n_estimators`

The instructor loops over different values of `n_estimators` (number of trees) and measures:

* **Training accuracy** (on data the model *has seen*)
* **Testing accuracy** (on data the model *has not seen*)

Why track both?

* Large gap → indicates **overfitting**.
* Training accuracy is always slightly better than test accuracy (expected).

---

## 🖼 Accuracy vs Number of Trees

* **Training accuracy (orange line):** increases and then plateaus.
* **Testing accuracy (blue line):** starts lower but also rises and then levels off.
* If accuracy plateaus → adding more trees won’t improve performance much.
* Choose a simpler model if multiple perform similarly (Occam’s razor!).

📌 Example outcome:

* Accuracy plateaus around `n_estimators ≈ 100`.
* Trying between 50–100 may give a good balance between **accuracy** and **efficiency**.

---

## ✅ Key Takeaways

* **Hyperparameters** let you control model complexity.
* **n\_estimators** controls forest size → more trees = smoother results.
* **max\_depth** balances underfitting vs overfitting.
* Always compare **training vs testing accuracy** to detect overfitting.
* Prefer the *simplest model* when performance is similar.

---

## 🔍 Suggested Next Steps

* Explore more hyperparameters with `GridSearchCV` or `RandomizedSearchCV` in scikit-learn.
* Visualize accuracy curves for other parameters (`max_depth`, `max_features`).
* Use cross-validation for more robust results.
