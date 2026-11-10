---
name: set-up-alerts
description: Use when the user wants to be told about new tenders ("email me when…", "watch for…"), or wants to see, change, pause or delete their LoonBids alerts.
---

1. Build the filters as for `search_tenders` (use `buyer` for one buyer, such as "Toronto" for the City of Toronto) and run `search_tenders` once so the user sees what the alert would catch today.
2. Confirm the alert's name, filters and frequency (`instant`, `daily` or `weekly`) with the user before calling `create_alert`. If LoonBids isn't connected yet, the first call asks the user to connect their account; that's expected.
3. To change one, call `list_alerts` to find its id, then `update_alert` with only the fields that change (`paused: true` stops emails without deleting).
4. Only call `delete_alert` after the user confirms; suggest pausing instead if they might want it back.
5. `get_alert_matches` shows what an alert has already found and whether each was emailed.
6. In ChatGPT, `create_alert`, `update_alert` and `delete_alert` show an approval card instead of acting: nothing changes until the user clicks Approve. Don't call the tool again while the card is waiting.
