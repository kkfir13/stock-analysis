# Reviewer smoke tests (to run; NOT verified in this archive)

| Tool | Prompt | Acceptance criterion |
|---|---|---|
| `search_securities` | Find Apple Inc.'s ticker | Correct listing, without OAuth research consumption |
| `get_stock_valuation` | Analyze AAPL fair value and margin of safety | Canonical source value, as-of date, OAuth and allowance respected |
| `get_stock_fundamentals` | Review MSFT revenue, earnings and cash flow | Period-dated numbers or marked missing coverage |
| `get_stock_technicals` | Review NVDA daily RSI and SMA20/50/200 | Dated daily readings when covered, never live claims |
| `compare_stocks` | Compare MSFT and GOOGL valuations | Source-dated valuation evidence; no fabricated metric |

Negative tests: anonymous requests to metered tools should receive a valid OAuth challenge; missing or stale technical data must fail safely; out-of-allowance requests should preserve the true quota reason; requests to buy a security or edit holdings must not trigger any write tool.

**Do not mark Self-tested until run against the actual endpoint in Claude/MCP Inspector.**
