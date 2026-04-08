# quant-portfolio-study

document April 8 2026 as a regime change - Iran 2 week ceasefire into rolling beta analysis


Module 3 signals as of Apr 8 2026 show no RSI extremes across the portfolio, consistent with a macro volatility event compressing momentum signals. AVGO and MRVL flagged as bearish outliers.

Module 3 done. A few things to note before you run it:
This one always re-pulls — no CSV dependency on Modules 1 or 2. Every run gives you fresh signals as of today. That's intentional — signals go stale, prices don't.
What to look for in the output:

The heatmap is your dashboard — one glance tells you which tickers have consensus signals vs mixed readings
Charts only render for tickers with a non-zero composite score — if a ticker is neutral across all five signals it gets skipped, keeping the output clean
The composite score is deliberately simple — it's a starting point, not a trading system

Honest limitation to log: The composite score weights all five signals equally, which is naive. RSI and MA crossovers on an 8-month-old portfolio aren't the same quality signal as on a 5-year dataset.

Data & methodology issues

165 days is thin — need to caveat every ratio with confidence intervals or at minimum note the sample size limitation
PORTFOLIO_VALUE is hardcoded — should be dynamic
Beta assumed static — needs rolling beta calculation
Benchmark is SPY only — need QQQ and a sector ETF for honest comparison
Equal-weight fallback in the try/except doesn't match actual position weights — if Module 1 CSVs ever fail, Module 2 silently produces wrong numbers with no warning

Portfolio construction issues

LITE and COHR are effectively one concentrated photonics bet
Position sizes are tiny fractional shares from a small account — percentage returns look great but dollar returns are modest, which matters for how we frame the memo
No rebalancing logic — the backtest assumes you held everything static, which you didn't (you trimmed LITE, COHR, VRT, ANET in January)

Presentation issues

Chart titles still say "Entry Aug 2024" in some places
The per-ticker return chart doesn't account for the partial sells — LITE's 601% is calculated as if you still hold the full original position, but you sold some in January at $408
No transaction cost modeling — even fractional share platforms have spreads


