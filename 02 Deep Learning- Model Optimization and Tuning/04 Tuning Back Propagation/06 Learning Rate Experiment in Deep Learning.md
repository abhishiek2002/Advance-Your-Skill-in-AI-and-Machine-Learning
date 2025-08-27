# Learning Rate Experiment in Deep Learning

## Overview

This section covers the practical experiment for learning rate tuning in deep learning models, particularly focusing on the iris dataset example. The goal of this experiment is to determine how the learning rate affects model training and convergence.

## Experiment Setup

* **Notebook Section:** 3.6 (Back Propagation)
* **Learning Rates Tested:** 0.001, 0.005, 0.01, 0.1, 0.5
* **Model:** Neural network for iris classification
* **Experiment Process:**

  1. Use the common experiment functions notebook.
  2. Pass the learning rate as a parameter while initializing the optimizer for the model.
  3. Build and run the model for each learning rate.
  4. Capture accuracy across epochs.
  5. Plot results to analyze performance trends.

## Observations

* **0.001:**

  * Model converges to a low accuracy.
  * Learning is too slow; progress is steady but minimal.

* **0.005 and 0.01:**

  * Model achieves higher accuracies.
  * Smooth and stable training.
  * These are likely the optimal learning rate values for this use case.

* **0.1:**

  * Model accuracy reaches near previous optimal values.
  * Training becomes choppy, showing oscillations in accuracy.

* **0.5:**

  * Model exhibits significant oscillations.
  * Average accuracy is lower than the moderate learning rates.

## Key Takeaways

* The **learning rate** controls the speed of weight updates during training.
* Too low: Slow learning and potentially low final accuracy.
* Moderate: Balanced learning speed and stable convergence.
* Too high: Oscillations and potential instability (risk of exploding gradients).
* **Practical Recommendation:** Choose a learning rate that provides high accuracy while maintaining steady improvement across epochs.

## Next Steps

* Use the identified optimal learning rate for further hyperparameter tuning.
* Combine learning rate tuning with optimizer selection for better model performance.
* Validate results across multiple datasets to ensure stability and avoid overfitting.
