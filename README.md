# Binance Alerts Analyzer
This repository contains a Python script for processing alert signals and retrieving historical candlestick data from Binance. The script utilizes the Binance API to fetch the required data and performs calculations to determine various metrics related to the alert signals.

## Installation

To run the script, you need to have Python installed on your system. Additionally, you need to install the required dependencies by running the following command:

```
pip install pandas requests
```

## Usage

1. Save the alert signals in a CSV file named `alert_from_algo1_091123.csv`. The file should contain the following columns: `symbol`, `Time_(MSK)`, and `alert_price`.

2. Modify the script to specify the correct file path if necessary:

```python
alert_df = pd.read_csv("alert_from_algo1_091123.csv")
```

3. Run the script 

4. The processed data will be saved in a file named `Lebiadzevich_processed_data.csv`.

## Script Overview

The script performs the following steps:

1. Reads the alert signals from the CSV file.

2. Defines a function `get_historical_klines` to fetch historical candlestick data from Binance using the Binance API.

3. Defines a function `create_dataframe` to convert the fetched data into a pandas DataFrame.

4. Defines a function `convert_numeric_columns` to convert numeric columns in the DataFrame to the appropriate numeric format.

5. Defines a function `calculate_time_range` to calculate the start and end times for retrieving historical candlestick data based on the alert time.

6. Defines a function `calculate_resistance_length` to calculate the length of resistance based on the candlestick data and alert price.

7. Defines a function `calculate_metrics` to calculate various metrics based on the candlestick data and alert price, including the maximum price, price change percentage, resistance length, and effectiveness flag.

8. Defines a function `process_alerts` to process the alert signals. It iterates over each signal, retrieves the historical candlestick data, calculates the required metrics, and stores the results in a list.

9. Saves the processed data to a CSV file.
