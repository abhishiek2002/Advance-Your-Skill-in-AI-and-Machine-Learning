## Epoch and Batch Size Experiment

### Overview

In this experiment, we explore the effects of varying batch sizes on model training performance. The primary goal is to observe how batch sizes influence accuracy progression across epochs.

### Experiment Setup

* **Notebook:** `code-02-XX`, Tuning the Deep Learning Network
* **Imports:** Common experiment functions from the shared library
* **Data:** Iris dataset (loaded via `get_data` method)
* **Base Model Configuration:** Default hyperparameters from `base_model_config`

### Parameters Tested

* **Batch Sizes:** 16, 32, 48, ..., 128 (incrementing by 16)
* **Epochs:** 20 (fixed)
* **Model Name:** Generated for labeling outputs and graphs

### Procedure

1. Initialize an empty collection to store accuracy results.
2. Iterate over the selected batch sizes.
3. For each batch size:

   * Load the base model configuration.
   * Load and preprocess the training data.
   * Set the epochs to 20 and batch size to the current iteration value.
   * Run the model and capture accuracy after each epoch.
4. Aggregate results to visualize trends across batch sizes.

### Observations

* **Model Consistency:** The model architecture remains constant irrespective of batch size.
* **Epoch Trends:**

  * Accuracy starts low for early epochs and stabilizes after several epochs.
  * Stabilization point varies depending on the model parameters and use case.
* **Batch Size Impact:**

  * Smaller batch sizes start with higher accuracy due to more iterations per epoch.
  * Accuracy tends to stabilize as epochs progress.
  * For this specific use case, smaller batch sizes provided a slightly higher stabilized accuracy.

### Notes and Recommendations

* This experiment used a small model with limited training data; results may vary with larger datasets.
* For real-world applications, using substantial training data is recommended to ensure reproducible results.
* After determining optimal batch size and epoch values, these parameters can be fixed for downstream tuning of other hyperparameters.

### Next Steps

* Use the identified optimal batch size and epoch combination as a baseline for tuning other hyperparameters such as learning rate, activation functions, and network architecture.
