# Alpaca Trading Project

A comprehensive stock trading and data analysis project built with Python, utilizing the Alpaca API for paper trading and Yahoo Finance for historical data collection.

## Project Overview

This project provides tools for:
- **Stock Data Collection**: Automated downloading of historical stock data for 500+ major US stocks
- **Paper Trading**: Safe trading simulation using Alpaca's paper trading environment
- **Data Analysis**: Jupyter notebooks for exploring and analyzing stock market data
- **Trading Strategies**: Framework for implementing and testing trading algorithms

## Features

- **Multi-stock Data Collection**: Downloads 30-minute interval data for 500+ stocks
- **Paper Trading Integration**: Safe trading simulation with Alpaca API
- **Data Visualization**: Interactive analysis with Jupyter notebooks
- **Automated Data Management**: Organized CSV storage with timestamped files
- **Real-time Market Data**: Live streaming capabilities for market monitoring

## Project Structure

```
alpaca/
├── data/                          # Historical stock data (CSV files)
│   ├── AAPL_2025-04-27_2025-07-26_30_Min.csv
│   ├── MSFT_2025-04-27_2025-07-26_30_Min.csv
│   └── ... (500+ stock files)
├── main.ipynb                     # Main trading notebook with Alpaca integration
├── data.ipynb                     # Data analysis and visualization notebook
├── stock_data_downloader.py       # Automated stock data collection script
├── test_downloader.py             # Testing script for data downloader
├── stocks.txt                     # List of 500+ stock symbols
├── requirements.txt               # Python dependencies
└── README.md                      # This file
```

## Installation

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Alpaca Markets account (for paper trading)

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd alpaca
   ```

2. **Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up Alpaca API credentials**
   
   Create a `.env` file in the project root:
   ```bash
   ALPACA_API_KEY=your_paper_api_key_here
   ALPACA_SECRET_KEY=your_paper_secret_key_here
   ```
   
   Get your API keys from [Alpaca Markets](https://alpaca.markets/)

## Usage

### 1. Data Collection

Download historical stock data for all stocks in `stocks.txt`:

```bash
python stock_data_downloader.py
```

This will create CSV files in the `data/` directory with 30-minute interval data.

### 2. Trading with Alpaca

Open `main.ipynb` in Jupyter to:
- Connect to Alpaca paper trading
- Place buy/sell orders
- Monitor positions
- Access real-time market data

### 3. Data Analysis

Open `data.ipynb` to:
- Analyze historical price patterns
- Create visualizations
- Perform technical analysis
- Backtest trading strategies

## Data Format

Each stock CSV file contains:
- **Date/Time**: Timestamp for each data point
- **Open**: Opening price for the period
- **High**: Highest price during the period
- **Low**: Lowest price during the period
- **Close**: Closing price for the period
- **Volume**: Trading volume for the period

## Configuration

### Stock List
Edit `stocks.txt` to modify which stocks to track. Each line should contain one stock symbol.

### Data Parameters
Modify `stock_data_downloader.py` to change:
- Date range for data collection
- Time intervals (currently 30 minutes)
- Data source (currently Yahoo Finance)

## Safety Features

- **Paper Trading Only**: All trading examples use Alpaca's paper trading environment
- **Environment Variables**: API keys stored securely in `.env` file
- **Error Handling**: Robust error handling in data collection scripts

## Dependencies

- **yfinance**: Yahoo Finance data collection
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computing
- **requests**: HTTP requests
- **python-dotenv**: Environment variable management
- **tqdm**: Progress bars for data collection
- **alpaca-py**: Alpaca trading API client