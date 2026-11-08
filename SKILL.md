---
name: compare-stocks
description: Compare two to six stocks, stock-versus-stock valuation, fair value and margin of safety using ValuEdge evidence and visible data dates.
---

# Compare stock valuations

Use when asked to compare 2–6 securities by ValuEdge valuation evidence (e.g., “MSFT vs GOOGL”). First resolve ambiguous ticker names with `search_securities` if required, then call `compare_stocks` on the requested symbols. Report fair values and margins of safety as provided, with consistent metrics, as-of dates and explicit gaps. Explain when differences in period or methodology limit comparability.

The comparison tool does not automatically supply every financial statement or technical indicator. For those requested dimensions, call `get_stock_fundamentals` or `get_stock_technicals` per supported symbol where authorized, mindful of separate quota charges. Never fabricate a ranking, recommendation, or forecast. Do not treat unavailable or stale data as a zero.
