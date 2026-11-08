# Claude submission copy — Stock Analysis by ValuEdge

## Listing name
Stock Analysis by ValuEdge

## One-liner
Stock Analysis in Claude: fair value, company fundamentals, daily technical indicators and stock comparisons powered by ValuEdge.

## Description
Stock Analysis by ValuEdge helps investors research public equities inside Claude. Look up the correct ticker, review intrinsic value and margin of safety, examine financial fundamentals, inspect source-dated daily technical indicators, and compare valuations across companies. Five read-only MCP tools use existing ValuEdge data and account entitlements. Valuation, fundamentals, technical analysis and comparison require ValuEdge OAuth; stock discovery is public. Daily technical data is not live intraday trading information. The connector cannot trade or edit portfolios.

## Use cases (reviewer-only)
1. **Stock valuation and fundamental analysis.** Prompt: “Analyze AAPL fundamentals, fair value and margin of safety, including source dates.”
2. **Daily technical analysis.** Prompt: “Show NVDA RSI, SMA20/50/200, momentum and volume, noting the data-as-of date.”
3. **Compare stocks.** Prompt: “Compare MSFT and GOOGL valuation estimates and margins of safety.”

## Prerequisites
A ValuEdge account and completed OAuth authorization are required for the four research tools. The account needs enough remaining plan allowance. The unmetered ticker-discovery tool is public. No brokerage connection is needed.

## Read/write capabilities
Read-only: public ticker search and authenticated valuation, fundamental, technical, and comparison lookups. No trades, account writes, or private portfolio access.

## Reviewer setup
1. Add `https://valuedge.app/mcp/stock-analysis` as a custom MCP connector in Claude.
2. Sign in to ValuEdge via its official OAuth page and grant requested permissions. **Provide a reviewer-specific test account with research allowance separately through the secure review channel.** Do not place credentials in the ZIP.
3. Test `search_securities`, `get_stock_valuation`, `get_stock_fundamentals`, `get_stock_technicals`, and `compare_stocks` using the prompts in `REVIEW-TESTS.md`.
4. Check date/source attribution, missing-data behavior, OAuth enforcement, limits, and that trading requests are not handled.
5. Confirm every test in Claude or MCP Inspector before selecting Self-tested. The checks are not certified solely by this ZIP.

Documentation: https://valuedge.app/connect
Repository: https://github.com/kkfir13/stock-analysis
Support: https://valuedge.app/contact
Privacy: https://valuedge.app/privacy
