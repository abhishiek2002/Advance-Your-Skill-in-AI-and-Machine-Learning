# 🌳 Random Forest Example

In the previous section, we worked with a toy dataset to understand how **Random Forests** work. Now, let’s dive into a more **real-world dataset** and see the practical workflow in action.

---

## 🔑 Key Idea

A **Random Forest** is built from many decision trees, each learning from different parts of the data. By combining them, the model makes stronger predictions than a single tree.

---

## 📦 Imports

We start with the following imports:

```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score
from sklearn import set_config
```

* **train\_test\_split** → splits data into training and testing sets (important to avoid overfitting).
* **RandomForestClassifier** → our main model.
* **accuracy\_score** → to measure how well the model performs.
* **set\_config** → ensures scikit-learn outputs **pandas DataFrames** instead of numpy arrays for easier handling.

---

## 📊 Dataset

We’ll use a dataset predicting whether someone earns **more than \$50,000/year**.

Features include:

* Work class
* Occupation
* Native country
* Age, education, and more…

The **target column**: `>50K` or `<=50K`

⚠️ Note: The dataset contains **missing values** in columns like `workclass`, `occupation`, and `native-country`. We’ll handle those with preprocessing.

---

## 🔍 Exploring the Data

Using pandas:

```python
x.describe().T
```

* **Mean, median, std** → quick statistical summary.
* **Count** → beware! It shows **non-missing values per column**, not total rows. Many beginners mistake this.

---

## 🛠 Handling Missing & Categorical Data

We’ll build a **preprocessing pipeline**:

```python
from sklearn.pipeline import Pipeline
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import OneHotEncoder
```

### Steps:

1. **Imputer** → fills missing categorical values with `missing` or `unknown`.
2. **OneHotEncoder** → converts categories into numeric 0/1 columns.

⚠️ Important: Don’t one-hot encode numeric columns. Only categorical features should be transformed.

---

## ⚙️ Building a Pipeline

```python
from sklearn.compose import ColumnTransformer

categorical_features = x.select_dtypes(include=['object']).columns

categorical_transformer = Pipeline(steps=[
    ('imputer', SimpleImputer(strategy='most_frequent')),
    ('onehot', OneHotEncoder(handle_unknown='ignore', sparse_output=False))
])

preprocessor = ColumnTransformer(
    transformers=[('cat', categorical_transformer, categorical_features)]
)
```

This ensures only categorical features get imputed and encoded.

---

## 🌲 Training Models

### Decision Tree

```python
from sklearn.tree import DecisionTreeClassifier

X_train, X_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=42)

dt_pipeline = Pipeline(steps=[
    ('preprocessor', preprocessor),
    ('classifier', DecisionTreeClassifier())
])

dt_pipeline.fit(X_train, y_train)
y_pred_dt = dt_pipeline.predict(X_test)

accuracy_dt = accuracy_score(y_test, y_pred_dt)
print(f"Decision Tree Accuracy: {accuracy_dt:.2%}")
```

✅ Result: **81% accuracy**

---

### Random Forest

```python
rf_pipeline = Pipeline(steps=[
    ('preprocessor', preprocessor),
    ('classifier', RandomForestClassifier(n_estimators=100, random_state=42))
])

rf_pipeline.fit(X_train, y_train)
y_pred_rf = rf_pipeline.predict(X_test)

accuracy_rf = accuracy_score(y_test, y_pred_rf)
print(f"Random Forest Accuracy: {accuracy_rf:.2%}")
```

✅ Result: **82.6% accuracy**

---

## 📈 Key Takeaways

* Always split data into **train/test** to avoid overfitting.
* **Pipelines** make preprocessing + modeling seamless.
* **Decision Tree** gave us 81%.
* **Random Forest** boosted performance to 82.6% by combining 100 trees.
* Small gains matter — in real-world ML, even a **1% boost** can be huge.

---

## 📌 Summary

* Random Forests are a **powerful extension of Decision Trees**.
* They reduce variance by aggregating multiple trees.
* Scikit-learn makes it **easy to switch between models** by reusing the same pipeline.

👉 Next, we’ll explore **why Random Forests often outperform single trees** in more detail.
