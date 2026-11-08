---
name: stock-technicals
description: Use for stock technical analysis, RSI, 20/50/200-day moving averages, trends, volatility, momentum and volume; this connector serves dated daily data.
---

# Daily technical stock research

Use for explicit requests for technical analysis of a stock including RSI, SMA moving averages, volume, volatility, ATR, momentum and daily trend interpretation. Call `get_stock_technicals` and use ONLY actually supplied daily snapshot fields. Report the source date, price basis and data-as-of values when present.

Do not describe the data as live, intraday, streamed quotes, or trade signals. Never invent MACD, support/resistance, chart-pattern recognition or price targets. If missing/stale data is returned, clearly state the gap. If the user wants a price chart, this read-only MCP tool does not supply live OHLC charting; do not misrepresent its capabilities. Technical analysis uses existing account quotas and OAuth; display real quota errors accurately.
