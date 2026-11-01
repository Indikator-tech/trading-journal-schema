# trading-journal-schema

An open, broker-agnostic **schema for logging trades** — so your journal is structured, queryable, and portable instead of a messy spreadsheet. JSON Schema + a ready CSV template.

> Educational tool. Not advice. MIT, no warranty.

## Why
A good journal is the cheapest edge in trading. But freeform notes don't let you ask "what's my average R on breakout trades before 10am?" This gives every trade a consistent shape.

## Files
- `schema.json` — JSON Schema (draft-07) for a single trade record
- `trade-template.csv` — the same fields as a spreadsheet header you can start filling today

## A trade record (example)
```json
{
  "id": "2026-11-01-001",
  "symbol": "NIFTY",
  "asset_class": "options",
  "direction": "long",
  "strategy": "ORB",
  "entry_time": "2026-11-01T09:30:00+05:30",
  "exit_time": "2026-11-01T10:05:00+05:30",
  "entry_price": 100.0,
  "exit_price": 140.0,
  "stop_price": 80.0,
  "quantity": 50,
  "risk_amount": 1000.0,
  "r_multiple": 2.0,
  "fees": 35.5,
  "result": "win",
  "mode": "live",
  "tags": ["breakout", "morning"],
  "notes": "Clean break, followed the plan."
}
```

`mode` is required and must be one of `backtest | demo | live` — label everything. Pair with [`trading-risk-calculator`](https://github.com/Indikator-tech/trading-risk-calculator) to compute `r_multiple`.
