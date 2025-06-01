# Paris Temperature Prediction

This project aims to predict daily average temperatures in Paris using historical weather data. The goal is to explore patterns in temperature over time and build a forecasting model using Prophet.

## What's Inside

- `notebook.ipynb`: Main Jupyter Notebook with all the code – from data cleaning to prediction and evaluation.
- `paris_temperature.csv`: Historical weather data for Paris, including temperature, humidity, precipitation, and more.

## Data Preprocessing

We start by doing some basic checks:
- Make sure the temperature values make sense (`tempmax > temp > tempmin`, etc.)
- Check if `preciptype` matches up with actual precipitation values
- Convert the `datetime` column to a proper date format
- Remove columns that aren’t useful for prediction

## Exploratory Analysis

We look at:
- Temperature trends over time
- Correlations between different weather variables
- Seasonal patterns (like whether it’s hotter during certain months)

## Stationarity Check

We use the Augmented Dickey-Fuller (ADF) test to see if the temperature series is stationary. If not, we apply differencing to stabilize the data before modeling.

## Model

We use **Facebook Prophet** to forecast future temperatures because it handles seasonality and trends well. The model is trained on daily temperature data and gives us predictions for future days.

## Results

We evaluate the model using:
- RMSE (Root Mean Squared Error)
- R² Score
- MAPE (Mean Absolute Percentage Error)

You’ll also find plots showing:
- The model’s predictions vs. actual temperatures
- Forecasted future temperature trends

## Requirements

Install the following before running:

```bash
pip install pandas matplotlib seaborn prophet scikit-learn statsmodels
