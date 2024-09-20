# Predictive Maintenance System Using XGBoost and Random Forest

## Overview

This project implements a predictive maintenance system for industrial motors using two machine learning models: **XGBoost** and **Random Forest**. The models predict the type of failure that may occur in the motors, such as Power Failure, Tool Wear Failure, or Overstrain Failure, based on sensor data like air temperature, process temperature, rotational speed, torque, and tool wear.

## Installation

To use the project, you need to install the required libraries. Run the following commands to install them:

```bash
!pip install pandas numpy matplotlib seaborn plotly
!pip install xgboost scikit-learn
```

## Dataset Overview
- The dataset contains sensor readings from motors, with the following key features:
  - Air temperature [K].
  - Process temperature [K]
  - Rotational speed [rpm]
  - Torque [Nm]
  - Tool wear [min]
  - Failure Type (Target variable with 6 classes)

## Project Structure(WORKFLOW)

- **Data Preprocessing:**
  - Load and clean the data.
  - Drop unnecessary columns like `Product ID`, `UDI`, and columns with more than 5% missing values.
  - Rename columns for clarity (e.g., `Air temperature [K]` to `air_temperature`).

- **Exploratory Data Analysis:**
  - Generate histograms and pairplots for visualizing relationships between sensor readings and failure types.
  - Compute and visualize correlations between numerical features.
  
- **Modeling:**
  - Two models are trained:
    1. **XGBoost:** A tree-based algorithm optimized with the `gpu_hist` method.
    2. **Random Forest:** A classic ensemble method with 100 trees.
  
  - Cross-validation is performed for the XGBoost model, and performance metrics such as accuracy, confusion matrices, and classification reports are generated.

- **Manual Predictions:**
  - A function allows users to input sensor values manually for real-time predictions of motor failure.

- **Model Comparison:**
  - The accuracies of XGBoost and Random Forest are compared, and the model with the highest accuracy is identified.

- **Saving & Loading Models:**
  - Models are saved as `.pkl` files for easy loading and future use.

- **Prediction**
  -  Make predictions on new data and output the predicted failure types in a csv file.
    

## Results

- **XGBoost Accuracy:** 90.12%
- **Random Forest Accuracy:** 89.75%
- The XGBoost model slightly outperforms the Random Forest model on the test dataset.

## File Structure

```plaintext
.
├── predictive_maintenance.csv          # Dataset for training
├── Sensor_Data.csv                     # Dataset on which we have to make predictions
├── xgb_model.pkl                       # Saved XGBoost model
├── rf_model.pkl                        # Saved Random Forest model
├── Sensor_Data_predictions.csv         # Dataset with predicted failure types of Sensor_Data.csv
```

 

---
