---
name: find-tenders
description: Use when the user asks for Canadian public tenders, RFPs, RFQs or bids to respond to ("any snow removal tenders in Ontario?", "federal IT contracts closing this month"). Searches and summarises open notices with links.
---

1. Turn the request into `search_tenders` filters: keywords (English or French), `regions` (province codes; Canada-wide notices always match), `buyer_levels`, `categories`, closing dates. Ask only if the region or kind of work is unclear.
2. Call `search_tenders`. If nothing matches, broaden once (fewer keywords, drop a filter) and say what you changed.
3. Report a short table: title, buyer, region, closing date (converted from UTC to the user's time zone), link. Mention that Quebec data refreshes weekly when Quebec is in scope.
4. For a notice the user picks, call `get_tender` for the description, contact, attachments and trade agreements.
5. Offer to save the search as an alert (see the set-up-alerts skill).
