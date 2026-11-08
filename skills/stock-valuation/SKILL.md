---
name: stock-valuation
description: Use for stock valuation questions: intrinsic value, fair value, DCF, multiples, overvalued or undervalued stock, and margin of safety.
---

# Intrinsic value and DCF

Use when the user asks about stock valuation, fair value, intrinsic value, discounted cash flow (DCF), valuation multiples, or margin of safety for a company. Call `get_stock_valuation` for the canonical result and preserve its assumptions and dated evidence. Do not recompute ValuEdge's margin-of-safety formula with an alternative denominator. When explaining MoS, use the exact returned result and report the source's formula only if the server provides it.

State that intrinsic value is an estimate, not a guaranteed future price. Make no real-time-price assumptions. If comparing two or more names, consider `compare_stocks` instead of repeated valuation calls when the request fits its supported 2–6 symbol range. Do not claim a single analysis call includes free fundamentals and technicals; these have their own usage policy. Missing valuation evidence should be presented as unavailable, not guessed.
