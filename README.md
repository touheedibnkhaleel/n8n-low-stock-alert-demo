# n8n-low-stock-alert-demo
A small n8n workflow that warns a store owner when a product is
running low, so they can restock before it sells out. Built as a
demo for online stores.

## How it works
1. Schedule Trigger runs every day at 9am
2. Google Sheets reads the Stock tab
3. IF node keeps products where stock_left is at or below
   reorder_level and no alert has been sent yet
4. Gmail emails the store owner: "<product> is down to <n> bags"
5. Google Sheets writes "alert sent on <date>" to alert_status,
   so the owner is not emailed again every day

## Sheet format (Stock tab)
product | stock_left | reorder_level | alert_status

## Setup
1. Import `low-stock-alert-workflow.json` into n8n
2. Connect your own Google Sheets and Gmail credentials
3. Point the sheet nodes at your own Google Sheet and Stock tab
4. Change the "To" address to the store owner's email

## Note
This is a demo with test data, not a client project.
