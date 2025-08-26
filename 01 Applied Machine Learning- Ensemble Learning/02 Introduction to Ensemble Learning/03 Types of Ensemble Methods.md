# 🔄 Types of Ensemble Methods

---

## 🎯 Introduction

We’ve already seen how ensembles can tackle real-world problems. Now, let’s explore **how ensembles actually work** and the different strategies used to build them.

---

## ⛳ Bagging (Bootstrap Aggregating)

### Concept

* Imagine **clones of yourself playing golf** on different courses.
* Each clone sees a different subset of holes (different **subsets of data**).
* Their results are averaged to get a **better final outcome**.

### How It Works

* Uses the technique of **bootstrapping**:

  * Randomly sample subsets of the training data.
  * Train separate models on each subset.
* Combine (usually by averaging or majority vote) their outputs.

### Example

* **Random Forest**:

  * Trains many decision trees on random subsets of data.
  * Averages their results.
  * Benefits: Easy to use, robust, and works well with noisy data.

---

## ⚡ Boosting

### Concept

* Golf analogy: After your **first shot**, you get another chance to adjust.
* Each subsequent swing corrects the **errors from the previous shot**.

### How It Works

* Starts with a **weak model** (usually a shallow decision tree).
* Identifies mistakes made by the first model.
* Builds another model to **correct those errors**.
* Repeats the process, sequentially improving performance.

### Example

* **XGBoost**:

  * Extremely popular boosting library.
  * Strong performance **out of the box**.
  * Frequently tops **Kaggle competitions**.
  * Widely used in real-world applications.

📘 Fun fact: The instructor even wrote a book called *Effective XGBoost*.

---

## 🏗️ Stacking

### Concept

* Unlike bagging (similar models), stacking combines **different types of models**.
* Uses a **meta learner** to figure out how best to combine outputs.

### How It Works

1. Train multiple base models (e.g., k-nearest neighbors, linear regression, SVM).
2. Collect their predictions.
3. Feed predictions into a **meta model** (meta learner).
4. The meta learner learns **which models to trust more** in different cases.

### Benefits

* Leverages strengths of **diverse algorithms**.
* Often outperforms any single model by balancing different perspectives.

---

## 📊 Summary of Strategies

| Ensemble Method | Main Idea                                                         | Example                         | Strengths                                             |
| --------------- | ----------------------------------------------------------------- | ------------------------------- | ----------------------------------------------------- |
| **Bagging**     | Train models on different random subsets of data; average results | Random Forest                   | Reduces variance, robust, handles noisy data          |
| **Boosting**    | Sequentially correct errors of weak models                        | XGBoost                         | Reduces bias, strong performance, competition-winning |
| **Stacking**    | Combine different model types using a meta learner                | Mixed models (SVM, KNN, Linear) | Leverages diverse strengths, flexible                 |

---

## 🚀 What’s Next

In the next section, we’ll dive into **Bagging** and see why **Random Forest** is such a powerful and reliable ensemble method.
