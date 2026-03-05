# QuantClass

## Overview
QuantClass is a Pine Script v6 indicator built as a full demonstration layer for the `HighClassCalculations` library. It computes and displays every exported calculation helper in one place.

## What It Uses
- `safeDiv()`
- `clamp()`
- `rescale()`
- `normalize()`
- `rangePercent()`
- `zScore()`
- `robustZScore()`
- `percentileRank()`
- `percentileValue()`
- `simpleReturn()`
- `logReturn()`
- `compoundedReturn()`
- `realizedVolatility()`
- `downsideDeviation()`
- `rollingSharpe()`
- `rollingSortino()`
- `efficiencyRatio()`
- `regressionSlope()`
- `regressionAngle()`
- `beta()`
- `alpha()`
- `ulcerIndex()`
- `maxDrawdown()`
- `atrPercent()`
- `relativeVolume()`
- `getAllFunctions()`

## Visual Output
- A normalized score pane with `Class Score`, `Z-Score Heat`, `Robust Z Heat`, `Efficiency Ratio`, and `Sharpe Heat`
- A dashboard table that surfaces the full calculation set
- An optional feature-catalog label that prints the library export list returned by `getAllFunctions()`

## Inputs
- Source, lookback, percentile, annualization
- Risk-free rate and minimum acceptable return
- ATR length and relative volume length
- Benchmark symbol for beta and alpha
- Color theme, dashboard toggle, feature-catalog toggle, and background toggle

## Interpretation
- `Class Score` compresses normalized range, percentile, and z-score data into a 0-100 composite.
- Negative `Z-Score` and `Robust Z` values indicate price is below its recent statistical center.
- `Efficiency Ratio` near `1` indicates directional movement; values near `0` indicate noise.
- `Sharpe`, `Sortino`, `Alpha`, and `Beta` are benchmark and risk-adjusted context metrics.
- `Ulcer Index`, `Max Drawdown`, and `ATR %` show downside and volatility pressure.

## Example Import Stack

```pinescript
//@version=6
indicator("QuantClass Example", overlay = false)

import TheTradingSpiderMan/HighClassCalculations/1 as HCC
import TheTradingSpiderMan/ColorsLibrary/2 as CLR
```
