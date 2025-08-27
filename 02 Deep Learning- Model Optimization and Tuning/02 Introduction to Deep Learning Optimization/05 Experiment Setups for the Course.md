# Experiment Setups for the Course

This section explains the experiment setup used in the course for exploring deep learning tuning parameters using the Iris flower dataset.

## Overview

To systematically experiment with different hyperparameters in deep learning, we have created a structured experiment setup using Jupyter Notebooks. The setup ensures consistency and reproducibility of experiments.

## Key Components

### 1. **Common Experiment Functions Notebook**

This notebook contains utility functions used throughout the course:

* **`get_data` Method:**

  * Loads the Iris dataset (`iris.csv`).
  * Pre-processes the data.
  * Extracts feature and target datasets.
  * Returns the features (`X`) and targets (`y`).

* **`base_model_config` Method:**

  * Initializes default hyperparameters for the deep learning model.
  * Each hyperparameter has a default value.
  * During experiments, individual parameters can be modified to observe their effect on performance.

* **`create_and_run_model` Method:**

  * Uses the input model configuration and datasets to build and train the model.
  * Executes training for the specified number of epochs.
  * Returns results including metrics such as accuracy for each epoch.

* **`plot_graph` Method:**

  * Accepts an array of accuracy measures.
  * Plots the model accuracy across epochs.
  * Visualizes how different parameter choices affect training performance.

## How the Experiments Work

1. **Define Experiments:**

   * Each experiment has a unique key and a set of values representing accuracy measures for the hyperparameter settings.

2. **Run Experiments:**

   * For each experiment, update the relevant hyperparameter values in the model configuration.
   * Train the model using the `create_and_run_model` method.

3. **Analyze Results:**

   * Use the `plot_graph` function to visualize accuracy trends.
   * Compare the effect of different hyperparameter values.

## Notes

* Ensure all required packages are installed before running experiments.
* Explore the utility functions in detail to understand their internal workings.
* This setup allows a systematic approach to hyperparameter tuning and model evaluation.

By following this setup, you can consistently experiment with different deep learning hyperparameters and evaluate their impact on model performance.
