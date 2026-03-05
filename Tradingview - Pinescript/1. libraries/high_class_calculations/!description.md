# HighClassCalculations - Pine Script v6

Advanced Pine Script v6 calculation helpers for normalization, statistics, returns, trend quality, and risk metrics.

---

## Installation

```pinescript
import TheTradingSpiderMan/HighClassCalculations/1 as HCC
```

---

## Included Functions

| Function | Description |
| -------- | ----------- |
| `safeDiv()` | Division with a fallback value when denominator is zero |
| `clamp()` | Restricts a value to a fixed range |
| `rescale()` | Maps a value from one range into another |
| `normalize()` | Min-max normalization over a rolling window |
| `rangePercent()` | Rolling range position from `0` to `100` |
| `zScore()` | Standard z-score |
| `robustZScore()` | Median absolute deviation based z-score |
| `percentileRank()` | Percentile rank of the current value |
| `percentileValue()` | Value at a requested percentile |
| `simpleReturn()` | One-bar arithmetic return |
| `logReturn()` | One-bar logarithmic return |
| `compoundedReturn()` | Return over a fixed lookback |
| `realizedVolatility()` | Annualized volatility from log returns |
| `downsideDeviation()` | Annualized downside deviation from returns |
| `rollingSharpe()` | Rolling Sharpe ratio from returns |
| `rollingSortino()` | Rolling Sortino ratio from returns |
| `efficiencyRatio()` | Kaufman efficiency ratio |
| `regressionSlope()` | Rolling linear regression slope |
| `regressionAngle()` | Regression slope in degrees |
| `beta()` | Rolling beta versus a benchmark |
| `alpha()` | Rolling Jensen-style alpha |
| `ulcerIndex()` | Rolling Ulcer Index |
| `maxDrawdown()` | Rolling maximum drawdown |
| `atrPercent()` | ATR as a percentage of price |
| `relativeVolume()` | Volume divided by average volume |

---

## Example

```pinescript
//@version=6
indicator("High Class Calculation Demo", overlay = false)

import TheTradingSpiderMan/HighClassCalculations/1 as HCC

length = input.int(50, "Length", minval = 2)
benchmark = input.symbol("SPY", "Benchmark")
benchmarkClose = request.security(benchmark, timeframe.period, close)

returns = HCC.simpleReturn(close)
benchmarkReturns = HCC.simpleReturn(benchmarkClose)

plot(HCC.zScore(close, length), "Z-Score", color = color.aqua)
plot(HCC.efficiencyRatio(close, length), "Efficiency Ratio", color = color.orange)
plot(HCC.rollingSharpe(returns, length), "Rolling Sharpe", color = color.lime)
plot(HCC.beta(returns, benchmarkReturns, length), "Beta", color = color.fuchsia)
```

---

## Notes

- `rollingSharpe()`, `rollingSortino()`, `downsideDeviation()`, `beta()`, and `alpha()` expect return series, not raw prices.
- `realizedVolatility()` expects a price or equity series and computes log returns internally.
- `atrPercent()` and `relativeVolume()` use chart context data (`close`, `volume`, `ta.atr()`).

---

**Author:** TheTradingSpiderMan  
**Version:** 1.0  
**Pine Script Version:** 6
