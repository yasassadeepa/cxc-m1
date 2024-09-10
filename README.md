# MetaTrader 5 Trading Bot

This is an automated trading bot for MetaTrader 5 that implements a strategy based on previous day's high/low and Asia session high/low levels. The bot places buy and sell limit orders, as well as stop orders, and manages positions with dynamic stop-loss adjustments.

## Features

- Automatically retrieves previous day's high and low prices for specified currency pairs
- Retrieves Asia session high and low prices
- Places buy and sell limit orders at key levels
- Places buy and sell stop orders
- Implements a trailing stop-loss strategy
- Automatically closes positions at predefined profit levels
- Deletes pending orders at a specified time
- Configurable via a separate configuration file

## Requirements

- Python 3.10
- MetaTrader 5
- Required Python packages:
  - MetaTrader5
  - pandas
  - schedule

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yasassadeepa/cxc-m1.git
   ```

2. Install the required packages:
   ```
   pip install MetaTrader5 pandas schedule
   ```

3. Set up your MetaTrader 5 terminal and ensure it's running.

## Configuration

1. Create a `config.txt` file in the same directory as the script with the following content:
   ```
   currency_pairs=EURUSD,GBPUSD,USDJPY
   day_high_low_time=03:00
   asia_high_low_time=13:00
   delete_orders_time=01:00
   lot_size=0.01
   ```

   Adjust the values according to your preferences.

## Usage

Run the script:

```
python trading_bot.py
```

The bot will prompt you to confirm or modify the configuration settings, then start running automatically.

## How it Works

1. The bot retrieves the previous day's high and low prices for specified currency pairs at a set time each day.
2. It also retrieves the Asia session's high and low prices at another set time.
3. Based on these levels and the current price, the bot places buy and sell limit orders, as well as stop orders.
4. The bot implements a trailing stop-loss strategy, adjusting the stop-loss as the position moves into profit.
5. Positions are automatically closed when they reach a 60 pip profit.
6. All pending orders are deleted at a specified time each day.
