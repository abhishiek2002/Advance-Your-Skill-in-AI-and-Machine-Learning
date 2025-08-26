# Evaluation of Stacking vs Individual Models

## Overview

This section explains how stacking ensembles improve model performance by combining multiple models, comparing the performance of individual models with the final stacked model.

## Concept

Stacking combines multiple base models into one ensemble, where the predictions of base models are used by a meta-model to generate a final prediction.

## Evaluation Steps

1. **Train individual models independently:**

   * Decision Tree (max depth = 3)
   * K-Nearest Neighbors (KNN)

2. **Evaluate each model:**

   * Decision Tree score: **0.81**
   * KNN score: **0.80**

3. **Combine models using StackingClassifier:**

   * Stack Decision Tree and KNN.
   * Train a meta-model on the predictions of base models.

4. **Evaluate stacked model:**

   * Final stacked model score: **0.82**

## Insights

* Individual models may perform moderately, but combining them through stacking improves overall performance.
* Stacking leverages the strengths of each model and reduces individual weaknesses.
* Even if base models perform worse independently, the stacked ensemble often outperforms them.

## Conclusion

Stacking provides a simple yet powerful way to boost predictive performance by combining models, especially when different models capture different aspects of the data.
