# Node-RED Crypto Price Monitor

## Overview

This Node-RED project monitors cryptocurrency prices and sends alerts via Telegram when certain conditions are met.

### Workflow

1. Trigger at regular intervals.
2. Fetch cryptocurrency data from Google Sheets.
3. Process and calculate various metrics for each coin.
4. Query real-time price information from Binance.
5. Calculate percentage changes based on historical and current data.
6. Make a decision to send a Telegram message if certain conditions are met.
7. Move on to the next cryptocurrency listed in the Google Sheet.

## Node Descriptions

- **Inject Node**: Triggered every 3600 seconds, this node starts the flow.
  
- **GSheet Node**: Retrieves the cryptocurrency data from a specific Google Sheet.

- **Get Coins Function Node**: Parses the Google Sheet's data and forwards it to the next node.

- **HTTP Request Node**: Queries the Binance API to get the real-time price data for a given cryptocurrency.

- **Calculate Price Function Node**: Processes real-time and historical data to calculate percentage change metrics.

- **Control Switch Node**: Checks if the calculated metrics meet certain criteria, which would trigger a Telegram message.

- **Calculate Price Function Node**: Constructs the payload for the Telegram message.

- **Telegram Sender Node**: Sends the constructed message to a Telegram bot.

- **Go Next Coin Function Node**: Increments the row number in the Google Sheet for the next cycle.

- **Debug Node**: For debugging purposes, outputs the final message payload.

## Prerequisites

- Node-RED installed and running.
- Google Sheets API setup with appropriate permissions.
- Binance API access.
- Telegram Bot API token.

## Setup

1. Import the JSON into your Node-RED editor.
2. Fill in the necessary API credentials and adjust the Google Sheets ID.
3. Deploy the project.

## Note

Please make sure that you understand the code and the API calls it makes. This is a project for educational purposes and should not be used as financial advice.
