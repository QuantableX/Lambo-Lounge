# Oscillator Suite

## Overview
The Oscillator Suite is a comprehensive all-in-one oscillator indicator that provides access to 46 oscillator variants across 5 categories, paired with a 12-method normalization/transform layer for standardizing any oscillator output — including z-score, detrending, percentile ranking, Fisher transforms, and more.

## Core Methodology

### Oscillator Engine
A single dropdown selector dispatches to one of 46 oscillator calculations. Each oscillator computes a `float` value per bar. The MACD family and several volume/volatility oscillators leverage the `MovingAverages` library (50+ MA types) for full configurability beyond hardcoded EMA/SMA.

### Normalization Layer
After the raw oscillator is computed, an optional normalization transform is applied. This converts any oscillator — regardless of its native range — into a standardized scale suitable for cross-comparison, signal generation, or statistical analysis. All normalization functions leverage the `HighClassCalculations` library where available.

---

## Oscillator Catalog (46 Oscillators)

### A. Momentum Oscillators (22)

| # | Oscillator | Description | Native Range | Key Parameters |
|---|-----------|-------------|-------------|----------------|
| 1 | RSI | Relative Strength Index — ratio of average gains to average losses | 0–100 | length, source |
| 2 | Stochastic %K | Raw stochastic position within high-low range, smoothed | 0–100 | length, smoothK |
| 3 | Stochastic %D | Smoothed %K (signal line of stochastic) | 0–100 | length, smoothK, smoothD |
| 4 | Stochastic RSI | Stochastic formula applied to RSI output | 0–100 | rsiLen, length, smoothK, smoothD |
| 5 | Williams %R | Inverse stochastic — distance from highest high | -100 to 0 | length |
| 6 | CCI | Commodity Channel Index — deviation from statistical mean | unbounded (~-200 to +200) | length, source |
| 7 | MFI | Money Flow Index — volume-weighted RSI | 0–100 | length |
| 8 | ROC | Rate of Change — percentage change over N bars | unbounded | length, source |
| 9 | Momentum | Simple price difference: `close - close[n]` | unbounded | length, source |
| 10 | CMO | Chande Momentum Oscillator — normalized difference of ups/downs | -100 to +100 | length, source |
| 11 | TSI | True Strength Index — double-smoothed momentum ratio | -100 to +100 | longLen, shortLen, source |
| 12 | Ultimate Oscillator | Weighted average of 3 timeframe buying pressure ratios | 0–100 | len1, len2, len3 |
| 13 | Awesome Oscillator | Difference of 5-period and 34-period SMA of midpoint | unbounded | (fixed periods) |
| 14 | Accelerator Oscillator | AO minus 5-period SMA of AO — rate of change of AO | unbounded | (fixed periods) |
| 15 | TRIX | 1-bar ROC of triple-smoothed EMA — momentum filter | unbounded | length, source |
| 16 | Coppock Curve | WMA of summed long-term ROC values — trend reversal | unbounded | wmaLen, roc1Len, roc2Len |
| 17 | KST | Know Sure Thing — weighted sum of 4 smoothed ROC values | unbounded | 4 ROC lengths, 4 SMA lengths |
| 18 | DPO | Detrended Price Oscillator — price minus shifted MA | unbounded | length, source |
| 19 | Aroon Oscillator | Aroon Up minus Aroon Down — trend direction strength | -100 to +100 | length |
| 20 | Balance of Power | `(close - open) / (high - low)` — intrabar buying/selling pressure | -1 to +1 | smoothLen |
| 21 | SMI | Stochastic Momentum Index — distance from midpoint of range | ~-100 to +100 | length, smoothLen1, smoothLen2 |
| 22 | Ergodic Oscillator | TSI minus its signal line — momentum divergence | unbounded | longLen, shortLen, signalLen |

### B. MACD Family (4)

All MACD variants use `MA.selector()` for the fast and slow moving averages, enabling any of 50+ MA types (not just EMA).

| # | Oscillator | Description | Native Range | Key Parameters |
|---|-----------|-------------|-------------|----------------|
| 23 | MACD | Fast MA minus Slow MA — trend-following momentum | unbounded | fastLen, slowLen, maType |
| 24 | MACD Histogram | MACD minus its signal line — momentum acceleration | unbounded | fastLen, slowLen, signalLen, maType |
| 25 | PPO | Percentage Price Oscillator — MACD as % of slow MA | unbounded | fastLen, slowLen, maType |
| 26 | APO | Absolute Price Oscillator — same as MACD in price units | unbounded | fastLen, slowLen, maType |

### C. Volume-Based Oscillators (10)

Volume-dependent oscillators guard against `na(volume)` for instruments without volume data.

| # | Oscillator | Description | Native Range | Key Parameters |
|---|-----------|-------------|-------------|----------------|
| 27 | Chaikin Oscillator | Fast EMA minus Slow EMA of Accumulation/Distribution line | unbounded | fastLen, slowLen |
| 28 | Volume Oscillator | `(fastVolMA - slowVolMA) / slowVolMA * 100` | unbounded | fastLen, slowLen |
| 29 | OBV Oscillator | On-Balance Volume minus its moving average | unbounded | length, maType |
| 30 | Klinger Oscillator | Klinger Volume Oscillator — volume-weighted trend | unbounded | fastLen, slowLen |
| 31 | CMF | Chaikin Money Flow — A/D normalized by volume over N bars | -1 to +1 | length |
| 32 | EMV | Ease of Movement — price movement relative to volume | unbounded | length |
| 33 | VWAP Deviation | `(close - VWAP) / stdev` — session-based deviation from VWAP | unbounded | (session VWAP) |
| 34 | PVT Oscillator | Price Volume Trend minus its moving average | unbounded | length, maType |
| 35 | A/D Oscillator | Accumulation/Distribution line minus its moving average | unbounded | length, maType |
| 36 | Force Index | `close change * volume`, smoothed — Elder Force Index | unbounded | length |

### D. Volatility-Based Oscillators (7)

| # | Oscillator | Description | Native Range | Key Parameters |
|---|-----------|-------------|-------------|----------------|
| 37 | Bollinger %B | Position within Bollinger Bands: `(close - lower) / (upper - lower)` | ~0–1 (can exceed) | length, mult |
| 38 | Bollinger Bandwidth | Band width as % of middle: `(upper - lower) / middle * 100` | 0+ | length, mult |
| 39 | Keltner Oscillator | Position within Keltner Channel: `(close - mid) / (upper - mid)` | ~-1 to +1 | length, mult, atrLen |
| 40 | Donchian Oscillator | Position within Donchian Channel: `(close - lower) / (upper - lower)` | 0–1 | length |
| 41 | ATR Ratio | `ATR / close * 100` — volatility as percentage of price | 0+ | length |
| 42 | Historical Volatility | Annualized standard deviation of log returns | 0+ | length |
| 43 | Chaikin Volatility | ROC of EMA of `(high - low)` — volatility acceleration | unbounded | emaLen, rocLen |

### E. Statistical Oscillators (3)

| # | Oscillator | Description | Native Range | Key Parameters |
|---|-----------|-------------|-------------|----------------|
| 44 | Z-Score | `(price - mean) / stdev` — standard deviations from mean | unbounded | length, source |
| 45 | Robust Z-Score | MAD-based z-score — outlier-resistant standardization | unbounded | length, source |
| 46 | Percentile Rank | Rolling percentile position within lookback window | 0–100 | length, source |

---

## Normalization / Transform Layer (12 Methods)

Applied after the raw oscillator value is computed. Select "None" to use the raw output.

| # | Method | Description | Output Range | Implementation |
|---|--------|-------------|-------------|----------------|
| 1 | None | Raw oscillator output (passthrough) | varies | — |
| 2 | Z-Score | Standardize to zero-mean, unit-variance | unbounded (~-3 to +3) | `HCC.zScore(raw, normLen)` |
| 3 | Robust Z-Score | MAD-based z-score, outlier-resistant | unbounded | `HCC.robustZScore(raw, normLen)` |
| 4 | Min-Max (0–100) | Rescale to 0–100 within rolling window | 0–100 | `HCC.rangePercent(raw, normLen)` |
| 5 | Min-Max (0–1) | Rescale to 0–1 within rolling window | 0–1 | `HCC.normalize(raw, normLen)` |
| 6 | Percentile Rank | Rank position within rolling distribution | 0–100 | `HCC.percentileRank(raw, normLen)` |
| 7 | Detrend (MA) | Subtract MA from oscillator — removes trend bias | unbounded | `raw - MA.selector(raw, normLen, maType)` |
| 8 | Detrend (LinReg) | Subtract linear regression — removes linear trend | unbounded | `raw - ta.linreg(raw, normLen, 0)` |
| 9 | Stochastic | Apply stochastic formula to oscillator values | 0–100 | `(raw - lowest) / (highest - lowest) * 100` |
| 10 | Inverse Fisher | Compress to bounded range via inverse Fisher transform | -1 to +1 | `(e^(2x) - 1) / (e^(2x) + 1)` on z-scored input |
| 11 | Fisher Transform | Expand via Fisher transform — amplifies extremes | unbounded | `0.5 * ln((1+x)/(1-x))` on clamped normalized input |
| 12 | Sigmoid | Logistic sigmoid — smooth compression to probability | 0–1 | `1 / (1 + e^(-z))` on z-scored input |

---

## Key Features

- **46 Oscillators** in a single dropdown — every major momentum, MACD, volume, volatility, and statistical oscillator
- **12 Normalization Methods** — z-score, robust z-score, min-max, percentile rank, detrending (MA and LinReg), stochastic, inverse Fisher, Fisher transform, sigmoid
- **50+ MA Types** — MACD family, signal lines, and MA-based detrending all use the full MovingAverages library (SMA, EMA, WMA, HMA, DEMA, TEMA, KAMA, T3, ALMA, FRAMA, VIDYA, JMA, McGinley, ZLEMA, LSMA, Supersmoother, Laguerre, and 30+ more)
- **Signal Line** — configurable MA type and length applied to the final (optionally normalized) oscillator
- **Auto-Detect Levels** — automatically sets OB/OS/Midline defaults appropriate to the selected oscillator and normalization method
- **5 Plot Styles** — Line, Histogram, Line + Histogram, Columns, Area
- **Divergence Detection** — regular and hidden divergence (bullish and bearish) via pivot analysis
- **Multi-Timeframe** — compute oscillator on any timeframe via `request.security()`
- **Data Mode** — Live (real-time) or Confirmed (closed bars only, no repainting)
- **10 Color Themes** — DEFAULT, MONO, VAPOR, NEON, OCEAN, SUNSET, FOREST, CANDY, FIRE, ICE
- **Dashboard Table** — current value, signal, status, normalization method, OB/OS levels, divergence, timeframe
- **8 Alert Conditions** — OB/OS entry/exit, midline cross up/down, signal line cross up/down

---

## Input Groups

| Group | Inputs |
|-------|--------|
| General | Data Mode (Live/Confirmed), Source |
| Oscillator | Master dropdown (46 options) |
| Parameters | Length, Fast/Slow Length, Smooth K/D, RSI Length, Long/Short Length, BB Multiplier, Period 1/2/3, MA Type |
| Normalization | Method dropdown (12 options), Norm Lookback, Detrend MA Type |
| Signal Line | Show Signal, Signal Length, Signal MA Type |
| Levels | OB Level, OS Level, Midline, Show Levels, Auto-Detect Levels |
| Visual | Plot Style, Show OB/OS Background, Line Width |
| Divergence | Show Divergence, Pivot Lookback, Div Lookback, Bullish/Bearish/Hidden toggles |
| Multi-Timeframe | Enable MTF, Timeframe |
| Dashboard | Show Dashboard, Position |
| Colors | Color Theme |

---

## Auto-Level Defaults

When "Auto-Detect Levels" is enabled, OB/OS/Midline are set based on the oscillator's native range:

| Oscillator Group | OB | OS | Mid |
|-----------------|----|----|-----|
| RSI, MFI, StochRSI, Stoch %K/%D | 80 | 20 | 50 |
| Williams %R | -20 | -80 | -50 |
| CCI | +100 | -100 | 0 |
| CMO, Aroon, SMI | +50 | -50 | 0 |
| TSI | +25 | -25 | 0 |
| Bollinger %B | 1.0 | 0.0 | 0.5 |
| Balance of Power | 0.5 | -0.5 | 0 |
| Unbounded (MACD, ROC, etc.) | — | — | 0 |

After normalization, levels adjust to the output range:

| Normalization | OB | OS | Mid |
|--------------|----|----|-----|
| Z-Score / Robust Z-Score | +2 | -2 | 0 |
| Min-Max (0–100) / Stochastic | 80 | 20 | 50 |
| Min-Max (0–1) | 0.8 | 0.2 | 0.5 |
| Percentile Rank | 80 | 20 | 50 |
| Inverse Fisher | 0.5 | -0.5 | 0 |
| Sigmoid | 0.7 | 0.3 | 0.5 |
| Detrend (MA/LinReg) | — | — | 0 |
| Fisher Transform | +2 | -2 | 0 |

---

## Visual Output

- **Oscillator Plot** — main oscillator value in selected style (Line, Histogram, Line + Histogram, Columns, or Area), colored via gradient from OS (bull color) to OB (bear color)
- **Signal Line** — thin line tracking the smoothed oscillator value
- **OB/OS Levels** — horizontal dashed lines at overbought and oversold thresholds
- **Midline** — horizontal dotted line at the center reference level
- **Background Fill** — optional shading when value enters OB zone (bear tint) or OS zone (bull tint)
- **Divergence Labels** — plotted at pivot points with lines connecting divergent price/oscillator pivots
- **Dashboard Table** — positioned at configurable corner, showing current state summary

### Dashboard Layout

```
+----------------------------------+
| Oscillator Suite                 |
+----------------------------------+
| Oscillator  | RSI                |
| Value       | 62.34              |
| Signal      | 58.21              |
| Status      | Neutral            |
| Norm        | None               |
| OB / OS     | 80.00 / 20.00      |
| Divergence  | None               |
| Timeframe   | Chart              |
+----------------------------------+
```

---

## Interpretation

### Raw Oscillator Signals
| Condition | Signal |
|-----------|--------|
| Value crosses above OB level | Overbought — potential reversal or strong momentum |
| Value crosses below OS level | Oversold — potential reversal or strong selling |
| Value crosses above midline | Bullish momentum shift |
| Value crosses below midline | Bearish momentum shift |
| Oscillator crosses above signal line | Bullish signal |
| Oscillator crosses below signal line | Bearish signal |
| Regular bullish divergence | Price makes lower low but oscillator makes higher low — potential reversal up |
| Regular bearish divergence | Price makes higher high but oscillator makes lower high — potential reversal down |
| Hidden bullish divergence | Price makes higher low but oscillator makes lower low — trend continuation up |
| Hidden bearish divergence | Price makes lower high but oscillator makes higher high — trend continuation down |

### Normalization Use Cases
| Method | Best For |
|--------|----------|
| Z-Score | Comparing current reading to statistical norm — identifying extremes |
| Robust Z-Score | Same as Z-Score but resilient to outlier spikes |
| Min-Max (0–100) | Standardizing unbounded oscillators into a fixed range for comparison |
| Percentile Rank | Understanding where current value sits relative to history |
| Detrend (MA) | Removing trending bias from oscillator — isolating cyclical component |
| Detrend (LinReg) | Removing linear drift — cleaner detrending than MA |
| Stochastic | Converting any oscillator into a bounded 0–100 stochastic reading |
| Inverse Fisher | Compressing to -1/+1 with sharp transitions at extremes |
| Fisher Transform | Amplifying small moves near extremes — sharper signals |
| Sigmoid | Smooth probability-like output (0–1) — good for scoring |

---

## Alert Conditions

| Alert | Trigger |
|-------|---------|
| Overbought Entry | Oscillator crosses above OB level |
| Overbought Exit | Oscillator crosses below OB level |
| Oversold Entry | Oscillator crosses below OS level |
| Oversold Exit | Oscillator crosses above OS level |
| Cross Above Mid | Oscillator crosses above midline |
| Cross Below Mid | Oscillator crosses below midline |
| Signal Cross Up | Oscillator crosses above signal line |
| Signal Cross Down | Oscillator crosses below signal line |

---

## Library Dependencies

| Library | Import | Used For |
|---------|--------|----------|
| `TheTradingSpiderMan/MovingAverages/1` | `MA` | MACD MA types, signal line, MA-based detrending, OBV/PVT/A/D smoothing |
| `TheTradingSpiderMan/HighClassCalculations/1` | `HCC` | Z-Score, Robust Z-Score, Min-Max, Percentile Rank, Rescale, Clamp, SafeDiv |
| `TheTradingSpiderMan/ColorsLibrary/2` | `CLR` | Bull/bear colors, gradient coloring, 10 color themes |

---

## Best Used For

- Universal oscillator analysis — one indicator replaces dozens of separate oscillator scripts
- Cross-oscillator comparison via normalization — apply the same scale to RSI, MACD, CCI, or any other oscillator
- Statistical regime detection — z-score and percentile rank reveal when readings are historically extreme
- Trend-debiased momentum — detrending methods isolate cyclical oscillations from directional trend
- Signal refinement — Fisher/inverse Fisher transforms sharpen entry/exit signals
- Multi-timeframe confirmation — validate oscillator readings across timeframes
- Divergence-based reversal detection — systematic pivot-based divergence scanning
