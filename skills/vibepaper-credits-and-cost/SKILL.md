---
name: vibepaper-credits-and-cost
description: >-
  Check the VibePaper credits (points) balance and membership tier, and
  estimate what an image, video, audio or edit job will cost before running
  it. Use when the user asks about credits, pricing, balance, or cost, or
  before any batch or video generation.
---
# Credits and cost

1. Balance: `account_status` → points balance and membership tier.
2. Estimate a job: `estimate_generation_cost` (or `estimate_edit_cost` for edits) with the exact request you would submit. Changing duration, resolution, output count or model changes the price.
3. For several options, estimate each and show a small table: model, settings, credits.
4. If the balance is lower than the estimate, do not submit. Say how many credits are needed and point them to https://vibepaper.io to top up.
5. After a job, report credits spent and, if the user cares, the new balance from `account_status`.

Do not quote prices from memory; always use the estimate tools, because pricing changes.
