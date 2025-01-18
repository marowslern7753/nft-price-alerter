# NFT Price Tracker Alert Bot

## Overview

The **NFT Price Tracker Alert Bot** is a Python-based tool that tracks the price of specific NFTs from a collection on OpenSea. It monitors prices against a defined threshold and sends an alert email if a token’s price falls below the threshold. This is ideal for users looking to receive notifications about potential deals.

### Features

- **Real-Time Price Monitoring**: Regularly checks NFT prices on OpenSea.
- **Threshold-Based Alerts**: Only sends an alert if the price falls below a specified ETH threshold.
- **Email Notifications**: Sends alerts to a specified email address.

### Prerequisites

To use this script, you’ll need:

1. Python 3.x
2. Required libraries: `requests`, `smtplib` (built-in), and `email` (built-in)

Install the necessary libraries with:

```bash
pip install requests
```

### Usage

#### Step 1: Update the Contract Address, Token IDs, and Threshold

Replace the `contract_address` and `token_ids` with the specific NFT collection’s contract address and token IDs you wish to track. Set the `price_threshold` to the ETH value you’d like to use as the alert threshold.

#### Step 2: Configure Email Alerts

In `email_config`, add:

- **from_email**: Email address from which alerts are sent.
- **to_email**: Recipient’s email address.
- **smtp_server** and **smtp_port**: Email provider’s SMTP server and port (e.g., `smtp.gmail.com` for Gmail).
- **password**: Password for the `from_email` account.

Ensure that **two-factor authentication** is disabled or set up an **app-specific password** if using Gmail or another secure email provider.

#### Step 3: Run the Script

Run the script using:

```bash
py nft_price_tracker_alert_bot.py
```

The script will check each token’s price periodically (default: every 10 minutes) and send an alert email if a price is below the threshold.

### Example

If your contract address is `0x12345...` and you wish to track tokens `[1, 2, 3]` with an alert threshold of `0.5` ETH:

```python
contract_address = "0x12345..."
token_ids = [1, 2, 3]
price_threshold = 0.5
```

Then run:

```bash
py nft_price_tracker_alert_bot.py
```

### Important Notes

- **API Rate Limiting**: OpenSea enforces rate limits on their API. Ensure you don’t check too frequently to avoid being blocked.
- **Email Security**: Use a secure email account and follow email provider recommendations for app-specific passwords or two-factor authentication.

### Limitations

- **Platform-Specific**: This script is tailored for OpenSea. Adjustments may be needed to track prices on other platforms.
- **Dynamic Pricing**: This script fetches data periodically; it may miss price changes that occur between intervals.

### Future Enhancements

- **Multi-Channel Notifications**: Add SMS or Telegram notifications as alternative alert channels.
- **Enhanced Scheduling**: Use a scheduler (e.g., cron) to manage start/stop intervals.
- **Database Logging**: Log price data in a database for historical tracking and analysis.

--- 

This script provides a robust way to track NFT prices on OpenSea, with customizable alerting options. Let me know if you need additional configuration for other alert types or have questions on further expanding the bot's features!
semzdhb