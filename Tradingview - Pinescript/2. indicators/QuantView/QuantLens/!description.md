# QuantLens

## Overview
QuantLens is a visual chart enhancement toolkit that overlays moving averages, trading sessions, liquidity levels, and volume profile onto price charts for comprehensive technical analysis.

## Core Methodology

### Moving Average System
Implements 5 configurable moving averages with 20 MA type options:
- **Signal MAs**: Fast (default: 12) and Slow (default: 21) for trend detection
- **Additional MAs**: 50, 100, and 200 periods for major trend identification
- **Trend Coloring**: MAs colored based on price position (above/below) or crossover state

### Trading Sessions
Visualizes major market sessions with configurable timezone offsets:
- **New York** (13:00-22:00 UTC)
- **London** (07:00-16:00 UTC)
- **Tokyo** (00:00-09:00 UTC)
- **Sydney** (21:00-06:00 UTC)
- **Custom Session**: User-defined time ranges

### Liquidity Levels
Automatically identifies and plots support/resistance levels based on pivot highs and lows:
- Configurable pivot sensitivity (1-50 bars)
- Lines extend until price touches or closes beyond level
- Maximum line limit to manage chart clutter

### Volume Profile
Full-width horizontal volume distribution visualization:
- Configurable lookback days (1-30)
- Number of price rows (10-200)
- Point of Control (POC) line at highest volume level
- Gradient opacity based on volume intensity

## Key Features
- **20 MA Types**: SMA, EMA, WMA, VWMA, RMA, HMA, DEMA, TEMA, KAMA, T3, ALMA, FRAMA, VIDYA, JMA, McGinley, ZLEMA, LSMA, TMA, Supersmoother, Laguerre
- **Color Themes**: 10 themes matching QuantView suite
- **Background Trend Color**: Optional chart background based on MA trend
- **Daily Dividers**: Vertical lines and day labels at session boundaries
- **Watermark**: Customizable title, subtitle, and symbol info display
- **Alert System**: Crossover/crossunder alerts for signal MAs

## Visual Output
- **MA Lines**: Color-coded by trend state with configurable widths
- **Session Boxes**: Semi-transparent ranges with labels for each session
- **Liquidity Lines**: Dotted/dashed support and resistance levels
- **Volume Bands**: Full-width horizontal boxes with POC marker
- **Daily Dividers**: Gray dashed lines with day labels

## Interpretation
| MA Position | Signal |
|-------------|--------|
| Price above MA | Bullish bias for that timeframe |
| Price below MA | Bearish bias for that timeframe |
| Fast MA > Slow MA | Short-term bullish trend |
| Fast MA < Slow MA | Short-term bearish trend |

## Best Used For
- Visual trend identification
- Session-based trading (volatility timing)
- Support/resistance mapping
- Volume distribution analysis
- Multi-timeframe trend alignment
