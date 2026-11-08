---
name: get-started
description: Connect or troubleshoot Stock Analysis by ValuEdge MCP and OAuth. Use when the user wants to install, sign in, authorize or learn account access and research limits.
---

# Connect ValuEdge Stock Analysis

Use this setup workflow only when a user asks to connect, install, authorize, or understand ValuEdge Stock Analysis. Explain that the MCP endpoint is https://valuedge.app/mcp/stock-analysis and instruct them to use their client’s official MCP/OAuth flow. Do not request or store passwords, client secrets or bearer tokens in chat.

Tell the user that `search_securities` is public discovery; `get_stock_valuation`, `get_stock_fundamentals`, `get_stock_technicals`, and `compare_stocks` require ValuEdge OAuth with available account allowance. No brokerage linkage is needed. Never promise all research is free, or that a full stock review consumes one unit. For actual auth or quota errors, explain the server's returned reason. Refer to https://valuedge.app/connect and https://valuedge.app/privacy.

After connection, offer a small read-only query such as “Find Apple’s stock ticker.” Never represent a configuration file as an OAuth grant.
