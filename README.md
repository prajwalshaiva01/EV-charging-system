# EV Charging Station Demand Prediction System

An end-to-end Machine Learning project to analyze historical EV charging sessions and predict total energy demand (kWh) per session.

## Problem Statement
Predicting energy demand and session patterns is crucial for managing charging station infrastructure, reducing peak waiting times, and optimizing power distribution.

## Dataset Overview
- **Data:** Historical EV charging session records (3,395 sessions, 24 features).
- **Target Variable:** `kwhTotal` (Total energy consumed in kWh).
- **Key Features:** Charging duration (`chargeTimeHrs`), commute distance (`distance`), session time windows (`startTime`, `endTime`), facility type, and temporal day flags.

## Data Preprocessing & Engineering
1. **Handling Missing Values:** Imputed missing values in `distance` using median imputation.
2. **Feature Selection:** Removed non-predictive identifiers (`sessionId`, `userId`, timestamps).
3. **Encoding:** Converted categorical platform entries using one-hot encoding.

## Model Performance Comparison
| Model | MAE (kWh) | RMSE | R² Score |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | 1.631 | 3.287 | -0.409 |
| **Decision Tree Regressor** | 1.349 | 2.306 | 0.306 |
| **Random Forest Regressor** | **1.168** | **2.024** | **0.466** |

**Key Finding:** Linear Regression underperformed due to complex non-linear charging patterns. The ensemble Random Forest model significantly improved accuracy, lowering MAE to 1.168 kWh.
