---
name: stock-analysis
description: Perform evidence-based stock analysis with ValuEdge. Trigger for research on a stock’s fair value, fundamentals and daily technicals; use only the dimensions needed.
---

# Full stock analysis

Use this workflow for user requests to analyze a publicly listed stock with both business and market evidence, for example “analyze AAPL stock”, “give me stock analysis for Microsoft”, or “is NVDA stock worth researching?” Only use ValuEdge tools when the user has asked for a security analysis that those tools can support, and the connection is available.

1. Resolve an ambiguous listing with `search_securities`. If the ticker is supplied unambiguously, do not call discovery unnecessarily.
2. Call `get_stock_valuation` to obtain the canonical fair value and margin-of-safety evidence **when valuation is requested**. Call `get_stock_fundamentals` for supported financial results, and `get_stock_technicals` for source-dated daily indicators if the user requests technical analysis. These are separate metered calls; use the smallest tool set that answers the request.
3. Organize the result into **Valuation**, **Fundamentals**, **Technicals (daily)** and **Risks / missing coverage**; omit sections for data not requested. Use only returned values. Include reporting-period and valuation/source dates; explain where dates differ.
4. ValuEdge valuations are model estimates, not guaranteed targets. Never invent ratios, MACD, support/resistance, buy/sell signals, real-time quotes or forward performance. Indicate if the server returns data unavailable due to coverage or freshness.
5. If the server is unconnected, request official OAuth setup. If a research quota was actually exceeded, report the server-provided limit and upgrade path if returned; do not disguise errors as marketing messages. No trade execution or portfolio modifications.

Answer the actual question first; be concise but complete. A good response is evidence-based, date-aware and separates estimates from observed data.
