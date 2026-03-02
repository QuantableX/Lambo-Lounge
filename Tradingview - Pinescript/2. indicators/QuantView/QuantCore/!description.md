# QuantCore

## Overview
QuantCore is a comprehensive multi-timeframe trend and valuation analysis dashboard that aggregates 40 technical indicators into unified scores for actionable market insights.

## Core Methodology

### QuantDEX (Trend Analysis)
Calculates price position relative to 20 configurable moving averages (Y-001 to Y-020) across short-term and long-term timeframes. Each MA returns +1 (above), -1 (below), or 0 (neutral), aggregated into a normalized trend score ranging from -1 to +1.

### QuantVAL (Valuation Analysis)
Computes Z-Scores across 20 configurable lengths (X-001 to X-020) to identify statistical overbought/oversold conditions. Values beyond ±2 indicate extreme deviations from historical mean.

## Key Features
- **Multi-Timeframe Analysis**: Short-term (default: 1D) and long-term (default: 1W) perspectives
- **Configurable MA Types**: SMA, EMA, WMA, VWMA, RMA, HMA, DEMA, TEMA, KAMA, T3, ALMA, FRAMA, VIDYA, JMA, McGinley, ZLEMA, LSMA, TMA, Supersmoother, Laguerre
- **OSSR Metrics**: Displays Sharpe, Sortino, and Omega ratios for risk-adjusted performance
- **EMA Band System**: Visual trend bands with 12/21/50/100/200 MAs
- **Score History Tracking**: Historical score comparison with configurable day offsets
- **Data Mode**: Live (real-time) or Confirmed (closed bars only, no repainting)

## Visual Output
- **Bottom Table**: Score overview with historical comparisons and ROC indicators
- **Top Table**: QuantMetrics displaying OSSR ratios
- **Side Tables**: Detailed indicator breakdowns (QuantDEX and QuantVAL)
- **Chart Overlay**: EMA trend bands with optional background coloring

## Interpretation
| Score Range | Trend Signal |
|-------------|--------------|
| +0.5 to +1.0 | Strong bullish trend |
| 0 to +0.5 | Moderate bullish trend |
| -0.5 to 0 | Moderate bearish trend |
| -1.0 to -0.5 | Strong bearish trend |

## Best Used For
- Trend identification and confirmation
- Valuation assessment (overbought/oversold detection)
- Multi-timeframe alignment verification
- Risk-adjusted performance monitoring
