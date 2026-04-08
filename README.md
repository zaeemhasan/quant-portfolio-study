# quant-portfolio-study
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
