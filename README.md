 <div align="center">

# Rohini AQI Predictor

### Next-Day Air Quality Index Prediction using Machine Learning

<p>
  A machine learning project that analyses historical air pollution patterns to predict the next day's AQI for Rohini, Delhi.
</p>

<img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/Machine%20Learning-Regression-orange?style=for-the-badge" />
<img src="https://img.shields.io/badge/Status-Development-success?style=for-the-badge" />

</div>

---

## About The Project

Air pollution is one of the major environmental challenges faced by Delhi. Monitoring air quality helps us understand current pollution levels, but predicting future AQI can provide additional insights into upcoming air quality conditions.

**Rohini AQI Predictor** is a machine learning-based project designed to forecast the next day's Air Quality Index (AQI) for Rohini, Delhi, using historical air quality observations.

The model learns patterns from previous AQI and pollutant measurements to estimate the following day's AQI.

### Project Objectives

- Analyse historical air quality data for Rohini, Delhi.
- Identify patterns and trends in AQI and pollutant concentrations.
- Build and compare multiple machine learning regression models.
- Predict the next day's AQI using previously available observations.
- Evaluate model performance using standard regression metrics.

---

## Tech Stack

<div align="center">

| Technology | Purpose |
|:---:|:---|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Core programming language |
| ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) | Data preprocessing and manipulation |
| ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white) | Numerical computations |
| ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white) | Machine learning models |
| ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat) | Data visualization |
| ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white) | Interactive development |

</div>

---

## Dataset

The project uses historical air quality observations, including AQI and pollutant measurements.

**Data sources and coverage:**

- Historical hourly AQI observations for Rohini (2017–2023).
- Additional Rohini-specific historical AQI observations, where available and verified.
- Pollutant measurements such as PM2.5, PM10, NO2, SO2, CO and Ozone, where available.

The collected data is cleaned, processed and organised into daily records before being used for model development.

> **Note:** Only verified Rohini monitoring station data is used for Rohini-specific predictions. Data from other monitoring locations is not treated as Rohini data.

---

## Methodology

The project follows an end-to-end machine learning workflow:

<div align="center">

<table>
<tr>
<td align="center"><b>01</b><br/>Data Collection</td>
<td align="center"><b>02</b><br/>Data Preprocessing</td>
<td align="center"><b>03</b><br/>Feature Engineering</td>
</tr>
<tr>
<td align="center"><b>04</b><br/>Train-Test Split</td>
<td align="center"><b>05</b><br/>Model Training</td>
<td align="center"><b>06</b><br/>Model Evaluation</td>
</tr>
<tr>
<td colspan="3" align="center"><b>07 — Next-Day AQI Prediction</b></td>
</tr>
</table>

</div>

### 1. Data Preprocessing
- Handle missing values and duplicate records.
- Convert timestamps into a consistent date format.
- Organise hourly observations into daily records.
- Sort observations chronologically.

### 2. Feature Engineering

The model uses historical information such as:

- Previous days' AQI values.
- Historical pollutant concentrations.
- Rolling averages over different time windows.
- Calendar features such as month and day of the week.

### 3. Target Variable

The target variable is the **AQI of the following day**.

For example, when predicting AQI for 10 January 2023, the model uses historical information available up to 9 January 2023.

This ensures that future information is not used during prediction.

### 4. Train-Test Split

The dataset is divided chronologically into training and testing sets.

This helps evaluate how well the model predicts AQI for dates it has not previously encountered.

---

## Machine Learning Models

Three regression algorithms are implemented and compared:

| Model | Description |
|:---|:---|
| Linear Regression | Establishes a baseline using linear relationships. |
| Random Forest Regressor | Captures complex and non-linear patterns using multiple decision trees. |
| Gradient Boosting Regressor | Builds an ensemble of sequentially improved decision trees. |

### Model Evaluation Metrics

| Metric | Meaning |
|:---|:---|
| **MAE** | Average absolute difference between predicted and actual AQI. |
| **RMSE** | Measures prediction error while penalising larger errors. |
| **R² Score** | Measures how well the model explains variations in AQI. |

The model with the lowest MAE is preferred, while RMSE and R² are also considered during comparison.

---

## How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/Rohini-AQI-Predictor.git
```

### 2. Navigate to the project directory

```bash
cd Rohini-AQI-Predictor
```

### 3. Install dependencies

```bash
pip install pandas numpy matplotlib scikit-learn openpyxl joblib jupyter
```

### 4. Open the Jupyter Notebook

Open the `.ipynb` file in VS Code or Jupyter Notebook.

### 5. Execute the notebook

Run all cells sequentially to:

- Load the historical datasets.
- Preprocess and analyse the data.
- Generate features for forecasting.
- Train and evaluate machine learning models.
- Generate the next-day AQI prediction.

---

## Prediction Workflow

<div align="center">

<table>
<tr>
<td align="center">
<h3>Historical Data</h3>
Previous AQI and pollutant readings
</td>
</tr>
<tr><td align="center">⬇</td></tr>
<tr>
<td align="center">
<h3>Feature Engineering</h3>
Lag values, rolling averages and date features
</td>
</tr>
<tr><td align="center">⬇</td></tr>
<tr>
<td align="center">
<h3>Trained ML Model</h3>
Selected regression algorithm
</td>
</tr>
<tr><td align="center">⬇</td></tr>
<tr>
<td align="center">
<h3>Next-Day AQI Prediction</h3>
Estimated AQI for the following day
</td>
</tr>
</table>

</div>

The prediction script uses the latest available historical observations. To generate predictions for current dates, the dataset must first be updated with recent Rohini readings.

---

## Future Scope

- Integration of live AQI data from reliable monitoring sources.
- Expansion of historical Rohini air quality records.
- Experimentation with advanced time-series forecasting techniques.
- Integration of meteorological parameters when reliable local data becomes available.
- Development of an interactive dashboard for AQI monitoring and prediction.

---

## Limitations

- Prediction quality depends on the availability and reliability of historical data.
- Sudden changes in weather, traffic and industrial activity may affect actual AQI.
- The model generates estimates and cannot guarantee exact future AQI values.
- Predictions are not a substitute for official air quality measurements.

---

## Disclaimer

This project is developed for educational and academic purposes as a machine learning mini-project. The predictions are estimates and should not be considered official air quality measurements.

---

<div align="center">

### Developed by

**Shivanshika**

[![GitHub](https://img.shields.io/badge/GitHub-ShivanshikaCode-181717?style=for-the-badge&logo=github)](https://github.com/ShivanshikaCode)

*Predicting tomorrow's air quality through historical data and machine learning.*

</div>
