# QuantTime

## Overview
QuantTime is a multi-timeframe support and resistance indicator that automatically plots high/low levels from 6 different timeframes (1D, 1W, 1M, 3M, 6M, 1Y) to identify key price boundaries.

## Core Methodology

### Timeframe Level Extraction
Fetches the highest high and lowest low from each timeframe using `request.security()`:
- **1 Day (1D)**: Previous day's range
- **1 Week (1W)**: Previous week's range
- **1 Month (1M)**: Previous month's range
- **3 Months (3M)**: Previous quarter's range
- **6 Months (6M)**: Previous half-year's range
- **1 Year (1Y)**: Previous year's range

### Level Tracking
Maintains persistent line objects that automatically extend to the right and update when new highs/lows are established. Each timeframe has independent tracking for both high and low levels.

### Visual Hierarchy
Uses gradient opacity to create visual importance hierarchy:
- Shorter timeframes (1D): Full opacity (most visible)
- Longer timeframes (1Y): Higher opacity (faded, background context)

## Key Features
- **6 Timeframes**: Comprehensive coverage from daily to yearly levels
- **Toggle Controls**: Enable/disable each timeframe independently
- **Line Styling**: Solid, Dashed, or Dotted options per timeframe
- **Line Width**: Configurable 1-4 pixels per timeframe
- **Label Display**: Optional labels (e.g., "1D H", "1W L") at level origin
- **Data Mode**: Choose between current candle data or previous completed candle
- **Color Themes**: 10 themes matching QuantView suite

## Visual Output
| Timeframe | High Label | Low Label | Default Opacity |
|-----------|------------|-----------|-----------------|
| 1D | 1D H | 1D L | 0% (full visibility) |
| 1W | 1W H | 1W L | 25% |
| 1M | 1M H | 1M L | 50% |
| 3M | 3M H | 3M L | 60% |
| 6M | 6M H | 6M L | 65% |
| 1Y | 1Y H | 1Y L | 75% |

## Interpretation
| Level Type | Trading Significance |
|------------|---------------------|
| 1D High/Low | Intraday support/resistance |
| 1W High/Low | Weekly swing points |
| 1M High/Low | Monthly trend boundaries |
| 3M High/Low | Quarterly institutional levels |
| 6M High/Low | Semi-annual macro levels |
| 1Y High/Low | Yearly major support/resistance |

### Confluence Zones
When multiple timeframe levels align at similar prices, they create high-probability support/resistance zones with increased significance.

## Best Used For
- Identifying key support and resistance levels
- Multi-timeframe analysis integration
- Breakout/breakdown target identification
- Stop-loss placement at significant levels
- Trend continuation/reversal confirmation
