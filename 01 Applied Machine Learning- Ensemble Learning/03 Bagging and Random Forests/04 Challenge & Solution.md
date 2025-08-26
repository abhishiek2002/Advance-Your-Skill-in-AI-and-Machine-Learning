# Challenge: Tune Random Forest Parameters

🎵 *Upbeat electronic music plays*

**Task:**
Your challenge is to tweak the `max_depth` parameter of a Random Forest model and determine which value yields the best accuracy.

---

# Solution: Tuning Random Forest Parameters

🎵 *Upbeat music plays*

Before diving in, a quick reminder: the best way to learn is by *doing*. If you haven’t already, try this exercise yourself before reviewing the solution. Experimentation and hands-on coding will deepen your intuition.

---

## Step 1: Adjust the Code to Tune `max_depth`

We start by modifying the previous parameter tuning code (which varied `n_estimators`) and instead focus on `max_depth`.

```python
from sklearn.ensemble import RandomForestClassifier
import pandas as pd
import matplotlib.pyplot as plt

# Example depths to test
depths = [1, 2, 4, 6, 10, 20]

results = []
for d in depths:
    model = RandomForestClassifier(max_depth=d, random_state=42)
    model.fit(X_train, y_train)
    train_acc = model.score(X_train, y_train)
    test_acc = model.score(X_test, y_test)
    results.append({"max_depth": d, "train_acc": train_acc, "test_acc": test_acc})

results_df = pd.DataFrame(results)
results_df.set_index("max_depth", inplace=True)

# Plot
results_df.plot(marker='o')
plt.ylabel("Accuracy")
plt.title("Random Forest Accuracy vs Max Depth")
plt.show()
```

---

## Step 2: Interpret the Results

* **Shallow depth (e.g., `max_depth=1`)** → Produces a *decision stump*. Both training and testing accuracy are low and similar → **underfitting**.
* **Increasing depth** → Training accuracy rises steadily. Testing accuracy improves slightly but eventually plateaus.
* **High depth (e.g., 20+)** → Training accuracy continues to climb, but testing accuracy declines → **overfitting**.

---

## Step 3: Key Takeaways

* A *decision stump* is too simple (underfit).
* Very deep trees can memorize noise (overfit).
* The *sweet spot* lies in the middle range (e.g., `max_depth=6–10` depending on the dataset).
* Always compare **training vs testing accuracy** to detect underfitting or overfitting.

---

✅ **Conclusion:** Tuning `max_depth` helps balance bias and variance. The best value usually maximizes testing accuracy before overfitting begins.
