# Stock Analysis for Claude — Intrinsic Value, Fundamentals & Daily Technical Analysis (ValuEdge MCP)

**Analyze public stocks in Claude using ValuEdge's focused, read-only Stock Analysis MCP plugin.** Retrieve available **stock valuation and fair value estimates**, fundamental financial evidence, daily technical indicators, and stock comparisons—with dates and limitations instead of invented numbers.

[ValuEdge connection guide](https://valuedge.app/connect?utm_source=github&utm_medium=readme&utm_campaign=mcp_discovery&utm_content=stock-analysis) · [Full ValuEdge connector for Claude](https://claude.ai/directory/valuedge) · [Privacy policy](https://valuedge.app/privacy)

- **Focused remote MCP endpoint:** `https://valuedge.app/mcp/stock-analysis`
- **Host:** Claude, through the supported plugin/connection flow
- **Authentication:** Public company/ticker discovery may be available without sign-in; metered analysis requires the official ValuEdge OAuth flow and applicable plan allowances
- **Scope:** Read-only stock research. No portfolios, watchlist edits, manual record changes, or brokerage trades

## What can I ask a Claude stock analysis plugin?

| User intent | Example Claude prompt | Tool |
| --- | --- | --- |
| Stock intrinsic value | "Analyze AAPL's current ValuEdge fair value, model assumptions and margin of safety. Include data dates." | `get_stock_valuation` |
| Company fundamental analysis | "Explain MSFT's revenue, profitability, balance-sheet and cash-flow evidence by reporting period." | `get_stock_fundamentals` |
| Daily stock technical analysis | "Check NVDA's available end-of-day RSI (14), SMA 20/50/200, volume and trend indicators." | `get_stock_technicals` |
| Compare stock valuations | "Compare GOOGL, MSFT and AAPL on fair value and margin of safety, noting missing fields." | `compare_stocks` |
| Resolve a ticker | "Find the correct public stock listing for Alphabet before comparing the shares." | `search_securities` |

**What this is not:** An automated trading system, stock price prediction guarantee, live intraday quote service, portfolio tracker, or full-market stock screener. For screening, dividends and personal portfolios, see the [broader ValuEdge MCP connector](https://github.com/kkfir13/valuedge-mcp).

## Tools and access

| MCP tool | Description | Access |
| --- | --- | --- |
| `search_securities` | Resolve supported company names and stock tickers | Public discovery |
| `get_stock_valuation` | Read the available model-based fair value, method, evidence and margin of safety | OAuth; plan-metered |
| `get_stock_fundamentals` | Review sourced financial statement metrics, history and reporting periods | OAuth; plan-metered |
| `get_stock_technicals` | Read available daily RSI, SMA 20/50/200, momentum, relative volume, volatility and trend evidence | OAuth; plan-metered |
| `compare_stocks` | Compare valuation results for 2–6 confirmed stock tickers | OAuth; plan-metered |

The bundled workflow skills select relevant tools, preserve source/as-of dates, distinguish observed financial statements from valuation-model outputs, and explicitly flag unavailable or stale evidence. A request that invokes several tools may consume more than one unit of the user's research allowance.

## How to install Stock Analysis in Claude

1. Install the **Stock Analysis by ValuEdge** plugin from its Claude listing **if published**, or use a supported developer-plugin installation method for this repository. A public GitHub repo alone does not mean a directory listing is approved.
2. Follow Claude's connector prompt and authorize the ValuEdge account through its official OAuth browser flow when metered stock research is requested. Do not paste API keys, passwords, or tokens into the conversation.
3. Begin with one of the example prompts above. No brokerage account connection is required for stock research.

The plugin includes `.claude-plugin/plugin.json`, `.mcp.json` and five focused workflow skills. It bundles no local install-time scripts, npx/uvx launchers, private service keys, or brokerage trading functionality.

## FAQ: Stock valuation and analysis with Claude

### Can Claude calculate a stock's intrinsic value with ValuEdge?
The plugin can retrieve **ValuEdge's available model-derived intrinsic/fair-value estimate**, supporting model information and margin of safety for a supported ticker. It should not invent a missing value or imply that an estimate is an observed market price.

### Does it do discounted cash flow (DCF) valuation?
It can report the valuation methods and model evidence returned by `get_stock_valuation`, which may include DCF-derived components where available. Not every company has the same model or data coverage.

### Does it support RSI and moving averages?
It can retrieve available **daily/end-of-day** RSI and SMA 20, 50 and 200 readings, as well as other validated daily technical evidence. This is not live intraday technical analysis.

### Can it screen stocks or manage my portfolio?
No. This **focused Stock Analysis MCP endpoint** contains neither stock screening nor private portfolio/watchlist operations. Use the [full ValuEdge connection](https://valuedge.app/connect?utm_source=github&utm_medium=readme&utm_campaign=mcp_discovery&utm_content=stock-analysis-full) for supported broader tools.

### Do I need an API key or brokerage account?
No copied API key or connected brokerage account is required. ValuEdge OAuth and an eligible plan may be required to use the metered analysis tools.

## Financial data accuracy and limits

- Financial and daily technical coverage varies by ticker and data date.
- Daily indicators are not intraday trade signals or live candlestick data.
- Fair value and margin of safety are model-based estimates, not guaranteed price targets.
- The plugin respects the signed-in user's ValuEdge research quotas; it does not create an additional allowance.
- Never infer a buy, sell, or hold instruction or a guaranteed investment result from the tool output.

## Privacy: What data is transmitted?

This plugin invokes the remotely hosted HTTPS ValuEdge Stock Analysis MCP server. Claude may transmit stock names/tickers, comparison selections, requested tool parameters, an OAuth bearer token for authorized requests, and account/entitlement information as required for access control, rate limiting, and metering.

ValuEdge returns available source-dated financial, valuation, and technical evidence, plus relevant availability/usage status. The GitHub repository does **not** store account credentials or OAuth tokens. ValuEdge processes remote requests as described in its [privacy policy](https://valuedge.app/privacy); the AI client also has its own privacy practices.

The focused server does not provide private portfolios, watchlist or portfolio editing, or brokerage trading tools.

## Development and review

Review the published manifest, tools, and five workflow skills in this repository. The backend and financial datasets are not distributed here. See [LICENSE](LICENSE) and [REVIEW-TESTS.md](REVIEW-TESTS.md).

A valid manifest or test archive does **not** establish successful live OAuth or production analysis. End-to-end verification is required before claiming that a specific client flow has been tested.

[Help and contact](https://valuedge.app/contact) · [Terms](https://valuedge.app/terms) · [Full MCP documentation](https://github.com/kkfir13/valuedge-mcp)
