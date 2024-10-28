# Stock Brokers Script Master Mapping Assignment
## Project Overview
This project aims to unify data from various stock brokers by creating a consolidated mapping of all instruments traded across different brokers. The goal is to have a singular dataset where, upon selecting a script from any broker, you can view equivalent details across the other brokers. This enables an easy comparison of trading symbols, lot sizes, tokens, exchanges, and tick sizes for a particular instrument across brokers.

## Data Sources
The project uses publicly available script master lists from multiple brokers. These lists contain information such as:

- exchange: The exchange where the instrument is traded.
- lot_size: The lot size for trading the instrument.
- name: The name of the instrument.
- trading_symbol: The symbol used for trading.
- tick_size: The smallest price movement for the instrument.
- token: A unique identifier for the trade.

The data sources include the following brokers:
Angel One
Finvasia
Alice Blue
Flattrade
Zerodha

## Objectives/Flow
- Data Standardization: Ensure consistency across the brokers' data for merging, including cleaning and reordering columns.
- Column Arrangement: Reorder columns in each dataset to a standard order:
  token, name, trading_symbol, lot_size, exchange, tick_size.
- Data Cleaning: Remove rows with missing values across all columns except tick_size, ensuring each instrument's details are complete where available.
- Remove Duplicates: Eliminate any duplicate rows within each individual dataset to maintain a clean, accurate dataset.
- Merge Datasets: Create a unified DataFrame where each instrument (trading_symbol) has a single row. Each broker's data for the same trading_symbol is displayed in separate columns, filling NaN values where details are not available from a particular broker.
- Standardization of trading_symbol: To facilitate successful merging, ensure that trading_symbol values are consistent across all brokers’ datasets (e.g., by stripping whitespace and standardizing case).

## Final Output: 
The resulting dataset includes unique trading_symbol entries with corresponding broker details for each instrument, such as:
Columns for each broker’s lot_size, token, exchange, tick_size, and name.

## Future Work
- Database Integration: Store the final dataset in a SQL database with proper mappings for more querying capabilities.
- API Development: Develop an API to dynamically retrieve broker comparisons based on user-selected trading_symbol.
