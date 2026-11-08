# Stock Analysis by ValuEdge

**Stock analysis, valuation, fundamentals and daily technical research in Claude.**

This plugin provides a focused, read-only workflow for researching publicly
listed stocks using the ValuEdge remote MCP server. It helps Claude retrieve
source-dated financial evidence and valuation model estimates, rather than
substituting invented values or promising investment returns.

- MCP endpoint: **https://valuedge.app/mcp/stock-analysis**
- Documentation: https://valuedge.app/connect
- Privacy policy: https://valuedge.app/privacy
- Support: https://valuedge.app/contact
- Terms: https://valuedge.app/terms

## What you can do

| MCP tool | Purpose | Access |
| --- | --- | --- |
| `search_securities` | Resolve company names and stock tickers | Public discovery |
| `get_stock_valuation` | Read ValuEdge fair value, model evidence and margin of safety | ValuEdge OAuth, plan-metered |
| `get_stock_fundamentals` | Inspect financial statement metrics and reporting periods | ValuEdge OAuth, plan-metered |
| `get_stock_technicals` | Read validated daily RSI, SMA20/50/200, momentum, volume, volatility and trend coverage | ValuEdge OAuth, plan-metered |
| `compare_stocks` | Compare available valuation results across 2–6 stock tickers | ValuEdge OAuth, plan-metered |

The bundled skills help Claude select only the tools needed, explain periods
and data-as-of dates, distinguish model valuations from observed facts, and
report unavailable or stale evidence instead of guessing. An analysis involving
several tools can consume more than one unit of the account's research allowance.

## Example requests

1. **Stock analysis:** “Analyze AAPL's fundamentals and intrinsic value. Give me the dates of the evidence.”
2. **Technical analysis:** “Review NVDA's latest available daily RSI, SMA20/50/200, momentum and volume.”
3. **Stock comparison:** “Compare MSFT and GOOGL on fair value and margin of safety.”

## Installation

Install this plugin through Claude after its directory approval, or from this
GitHub repository using a supported plugin installation flow. When prompted,
connect a ValuEdge account using the official OAuth browser authorization.
No API key or password should be pasted into Claude or stored in this repo.
A brokerage account connection is **not** required.

The plugin contains `.claude-plugin/plugin.json`, `.mcp.json` and five workflow
skills. It contains no local scripts executed on installation, no npx/uvx
launchers, no private service keys and no trading functionality.

## Data sent to ValuEdge

This plugin talks to the remotely hosted ValuEdge MCP server over HTTPS.
When you use its tools, Claude may transmit the information needed to answer
your request, including:

- the stock names/ticker symbols, selected comparisons, tool arguments and
  research request parameters;
- an OAuth bearer access token in authenticated requests;
- account-identifying and entitlement information needed for authentication,
  rate limiting and metering, as handled by the remote ValuEdge service.

ValuEdge returns the available financial, valuation and daily technical
evidence, source dates, and relevant usage/availability states. Financial
research requests are processed by the remote service under
https://valuedge.app/privacy. Network requests to ValuEdge are necessary for
the plugin to function. This repository does **not** receive, contain or
store the user's OAuth token or private account credentials.

This focused Stock Analysis server does not expose private portfolios, watchlist
editing, portfolio editing, account mutation or brokerage trading tools.

## Limits and accuracy

- The technical endpoint returns daily/end-of-day coverage, **not** live
  intraday market prices, trade signals or live candlestick data.
- Financial coverage and technical data freshness may vary by stock.
- Model-derived fair values are estimates, not guaranteed price targets.
- The server uses each authenticated user's existing ValuEdge account allowances;
  the plugin does not grant additional access or bypass limits.
- No investment outcome is guaranteed.

## Development, licensing and review

Manifest metadata and skills are in this repository so reviewers can inspect
exactly which service the plugin contacts. See `LICENSE` for permission to
install and use the published plugin. The backend and datasets are not part of
this repository.

`REVIEW-TESTS.md` provides a non-exhaustive manual smoke-test plan. A valid
archive and manifest do not themselves prove production OAuth and data queries
work; live acceptance testing is required prior to marking the integration
self-tested.
