# Engine-Failure-Prediction-Challenge

Overview

This project involves predicting the Remaining Useful Life (RUL) of turbofan engines using NASA's CMAPSS dataset. 
The goal is to build a system that enables proactive maintenance planning by identifying when engines are likely to fail. 
By predicting engine failures accurately, maintenance teams can optimize replacement schedules, reduce downtime, and prevent unexpected failures.

The solution includes data preprocessing, feature engineering, machine learning model training, and evaluation. 
Optional extensions include creating a dashboard for real-time engine health monitoring and maintenance planning.


Dataset

The dataset contains run-to-failure data for turbofan engines:
- train_FD001.txt: Training data with complete run-to-failure cycles.
- test_FD001.txt: Test data ending before failure.
- RUL_FD001.txt: Ground truth RUL values for the test set.

Data Format

Each row in the training and test datasets represents one operational cycle of an engine:
- Column 1: Engine ID
- Column 2: Time in cycles
- Columns 3-5: Operational settings
- Columns 6-26: Sensor measurements

Approach

Phase 1: Required Deliverables
1. Data Preprocessing
  - Loaded and organized the dataset using pandas.
  - Removed extraneous columns and handled missing or anomalous values.
  - Normalized sensor data to ensure consistent feature scaling.
2. Feature Engineering
- Created relevant time-based features:
  - time_to_failure: Difference between the maximum cycle and the current cycle for each engine.
  - Rolling averages and statistical summaries (mean, standard deviation) for sensor readings.
- Analyzed sensor degradation patterns to identify the most informative sensors.

3. Model Development
- Trained a Random Forest Regressor as the initial baseline model to predict RUL.
- Split the data into training and validation sets for model evaluation.
- Evaluated the model using metrics:
  - Mean Absolute Error (MAE): Measures average prediction error.
  - Root Mean Squared Error (RMSE): Penalizes large prediction errors more heavily
