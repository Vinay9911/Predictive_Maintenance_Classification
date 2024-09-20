# 🔧 Predictive Maintenance System Using XGBoost and Random Forest 🚀

## 📝 Overview
This project implements a **Predictive Maintenance System** for industrial motors using two machine learning models: **XGBoost** and **Random Forest**. The models predict the type of failure that may occur in the motors, such as:
- ⚡ **Power Failure**
- 🛠️ **Tool Wear Failure**
- 💥 **Overstrain Failure**

The predictions are made based on sensor data like:
- 🌡️ **Air temperature**
- 🌡️ **Process temperature**
- 🔄 **Rotational speed**
- ⚙️ **Torque**
- ⏳ **Tool wear**

## 🛠️ Installation

To set up the project, you need to install the required libraries. Run the following commands:

```bash
!pip install pandas numpy matplotlib seaborn plotly
!pip install xgboost scikit-learn
```

## 📊 Dataset Overview
The dataset contains sensor readings from motors with the following key features:
- 🌡️ **Air temperature** [K]
- 🌡️ **Process temperature** [K]
- 🔄 **Rotational speed** [rpm]
- ⚙️ **Torque** [Nm]
- ⏳ **Tool wear** [min]
- 🎯 **Failure Type** (Target variable with 6 classes)

## 🛠️ Project Workflow

### 1. ⚙️ **Data Preprocessing:**
- Load and clean the dataset.
- Drop unnecessary columns like `Product ID`, `UDI`, and any column with more than 5% missing values.
- Rename columns for clarity (e.g., `Air temperature [K]` → `air_temperature`).

### 2. 📊 **Exploratory Data Analysis (EDA):**
- 📈 Generate histograms and pairplots for visualizing relationships between sensor readings and failure types.
- 🔍 Compute and visualize correlations between numerical features.

### 3. 🤖 **Modeling:**
- Two models are trained:
  - 🌲 **XGBoost:** A tree-based algorithm optimized with the `gpu_hist` method.
  - 🌳 **Random Forest:** A classic ensemble method using 100 trees.
  
- Cross-validation is performed for the XGBoost model, and performance metrics such as accuracy, confusion matrices, and classification reports are generated.

### 4. 🛠️ **Manual Predictions:**
- A function allows users to input sensor values manually for real-time predictions of motor failures.

### 5. ⚖️ **Model Comparison:**
- The accuracies of **XGBoost** and **Random Forest** are compared, and the model with the highest accuracy is identified.

### 6. 💾 **Saving & Loading Models:**
- Models are saved as `.pkl` files for future use.

### 7. 📊 **Predictions:**
- Make predictions on new data and output the predicted failure types to a CSV file.

## 🏆 Results

- **XGBoost Accuracy:** 90.12% ✔️
- **Random Forest Accuracy:** 89.75% ✔️
  
The **XGBoost** model slightly outperforms the **Random Forest** model on the test dataset.

## 📂 File Structure

```plaintext
.
├── predictive_maintenance.csv          # Dataset for training
├── Sensor_Data.csv                     # Dataset on which predictions are made
├── xgb_model.pkl                       # Saved XGBoost model
├── rf_model.pkl                        # Saved Random Forest model
├── Sensor_Data_predictions.csv         # Dataset with predicted failure types
```
