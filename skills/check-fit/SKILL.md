---
name: check-fit
description: Use when the user asks which tenders fit their company, whether to bid on one ("is this worth bidding?", "can we do this job?"), or wants LoonBids to remember what their company does.
---

1. Call `get_company_info` for what the company does, where, its typical contract size, certifications, bonding and work it avoids. If it's empty, ask for those in one question and offer to save them with `update_company_info` (it replaces the whole text, so keep what should stay; in ChatGPT the user approves it on a card).
2. Get the tenders to check: `get_alert_matches` for an alert's recent matches, `search_tenders` for a new search, or the notice the user named. Open each one worth a closer look with `get_tender`.
3. For each, say fit or no fit in one line and why: type of work, location, contract size, and closing time (is there time to price it?). Then list what the notice says about site meetings (mandatory or not, date), bonding, insurance, prequalification and required certifications.
4. Only report requirements the notice states. When the notice doesn't mention them, say the full documents on the buyer's page need checking and give the link. The decision to bid is the user's.
