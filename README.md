# Stock Price Forecasting using ARIMA & SARIMAX

## Project Overview

This project focuses on time series analysis and stock price forecasting using historical market data for **Indian Renewable Energy Development Agency (IREDA)** (`IREDA.NS`).

The project uses Python to collect approximately one year of daily stock data, analyze the closing-price series, check stationarity, and build ARIMA/SARIMAX forecasting models.

## Objectives

- Collect historical IREDA stock-price data.
- Explore daily Open, High, Low, Close, and Volume data.
- Analyze the closing-price time series.
- Check stationarity using the Augmented Dickey-Fuller (ADF) test.
- Apply differencing when required.
- Build an ARIMA model.
- Build a seasonal SARIMAX model.
- Generate a 30-step future forecast.
- Visualize actual and predicted closing prices.

## Dataset

The dataset is downloaded directly using the `yfinance` library.

- **Ticker:** `IREDA.NS`
- **Period:** Approximately one year of available daily data
- **Observations:** 249
- **Main variables:** Date, Open, High, Low, Close, Volume

The notebook shows the data ranging from **August 7, 2025 to August 6, 2026**.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- yFinance
- Statsmodels
- ARIMA
- SARIMAX

## Project Workflow

### 1. Data Collection

Historical IREDA stock data is downloaded using `yfinance`.

### 2. Data Preparation

The downloaded data is reset and organized into the following columns:

- Date
- Open
- High
- Low
- Close
- Volume

For forecasting, the **Close** price is used as the primary target variable.

### 3. Exploratory Data Analysis

The project examines the stock-price series and visualizes Open, High, Low, and Close prices to understand price movement over time.

### 4. Stationarity Testing

The Augmented Dickey-Fuller (ADF) test is used to check whether the time series is stationary.

The notebook defines a stationarity-checking function that reports the ADF statistic and p-value.

### 5. ARIMA Model

An ARIMA model is developed using:

```text
ARIMA(0, 1, 0)
```

The model uses first-order differencing (`d = 1`) and generates a future forecast.

### 6. SARIMAX Model

A seasonal SARIMAX model is also tested using:

```text
SARIMAX(1, 1, 1) × (1, 1, 1, 12)
```

The notebook reports an AIC of approximately **1137.50** for this model configuration.

### 7. Forecasting

The project generates predictions for approximately the next **30 steps** and visualizes the predicted values against the historical closing-price series.

## Model Results

The notebook contains the following model configurations:

| Model | Configuration | AIC |
|---|---|---:|
| ARIMA | (0, 1, 0) | 1153.57 |
| SARIMAX | (1, 1, 1) × (1, 1, 1, 12) | 1137.50 |

Based on the reported AIC values in the notebook, the tested seasonal SARIMAX configuration has the lower AIC.

## Key Takeaways

- The project demonstrates an end-to-end time series forecasting workflow.
- The closing price is used as the primary forecasting variable.
- Stationarity is evaluated using the ADF test.
- Differencing is used with `d = 1`.
- Both ARIMA and seasonal SARIMAX models are explored.
- A 30-step forecast is generated and visualized.

## Project Structure

```text
Stock-Price-Forecasting/
│
├── Time_series_forecasting.ipynb
└── README.md
```

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/Priyanshuprajapati-038/Stock-Price-Forecasting.git
```

2. Open `Time_series_forecasting.ipynb` in Google Colab or Jupyter Notebook.

3. Install the required libraries if necessary:

```bash
pip install pandas numpy matplotlib seaborn plotly yfinance statsmodels
```

4. Run the notebook cells sequentially.

## Disclaimer

This project is created for educational and analytical purposes. Stock-market forecasts are uncertain and should not be treated as financial advice or guaranteed future prices.

## Author

**Priyanshu Prajapati**

B.Tech Student | Data Analytics Enthusiast
