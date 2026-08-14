# Sports-Card-Inventory-Checker
Sports Card Inventory Checker from top Retailers


An n8n workflow that checks Best Buy product availability and price on a
schedule and posts a Discord alert when a tracked product is in stock at or
below your target price.

## How it works
Schedule Trigger (every 15 min) -> Target Products -> Best Buy Lookup ->
Parse Product Info -> IF (in stock AND price <= target) -> Discord Alert

## Requirements
- n8n instance
- Best Buy API key (free: https://developer.bestbuy.com)
- Discord bot added to your server with Send Messages permission

## Setup
1. Import the workflow JSON.
2. Best Buy credential (HTTP Query Auth): Name = apiKey, Value = your key.
3. Discord Bot credential: attach, then set server + channel.
4. Edit the "Target Products" Code node with your SKUs + target prices.
5. Activate.

## Security
Never commit real credential values. n8n exports strip secrets — keep it so.
Rotate any exposed key/token and scrub git history.

## Limitations
Monitors + alerts only — no auto-checkout. Best Buy only (others lack a
public price/stock API).
