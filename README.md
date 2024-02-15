# Introduction

This repository is responsible for containing all results, data, and code related to reproducing the results shown in the technical report: [Machine Learning for Performance Prediction of Data Distribution Service](https://openaccess.city.ac.uk/id/eprint/31554/).

Here is a run down of the contents of this repository:
- `2024-02-07_16-48-03_results.csv`
- `a00_lr_and_rf_modelling.py`
- `a01_results_analysis.py`
- `constants.py`
- `test_a01_results_analysis.py`

# `2024-02-07_16-48-03_results.csv`
A spreadsheet containing the training and testing error metric for every single model. It has the following columns:
- `model_type`: Either Linear Regression or Random Forests. 
- `created_at`
- `int_or_ext`: Interpolation or Extrapolation.
- `train_dataset`: Name of the train dataset.
- `train_dataset_filename`: Filename of the training dataset.
- `test_dataset`: Name of the test dataset.
- `test_dataset_filename`: Filename of the testing dataset.
- `train_example_count`: How many rows are in the training dataset.
- `test_example_count`: How many rows are in the testing dataset.
- `input_variables`: Input variables for the model.
- `output_variable`: Target/output variable for model.
- `metric_of_interest`: DDS metric that we are focusing on for this model e.g. latency_us.
- `standardisation_function`: Self-explanatory.
- `transform_function`: Self-explanatory.
- `error_type`: Error metric used to evaluate model performance e.g. RMSE.
- `train_error`: Value of the error metric at the end of training.
- `test_error`: Value of the error metric at the end of testing.

# `a00_lr_and_rf_modelling.py`
Python script responsible for running the linear regression and random forest models. Puts results into csv file with naming format of `<created_at>_results.csv`.

## Example Usage:
`python3 a00_lr_and_rf_modelling.py`

# `a01_results_analysis.py`
Processes the results and extracts the error metrics for each model per distribution statistic. It then processes the data into latex tables stored in `output.tex` which is generated at the end of the script. 

## Example Usage:
`python3 a01_results_analysis.py`

# `constants.py`
All constants used in the scripts e.g. `DDS_METRICS`, `STATS`, `STANDARDISATION_FUNCTIONS`, etc.

# `test_a01_results_analysis.py`
Unit test for `a01_results_analysis.py`. It's automatically run when you run `a01_results_analysis.py`.
