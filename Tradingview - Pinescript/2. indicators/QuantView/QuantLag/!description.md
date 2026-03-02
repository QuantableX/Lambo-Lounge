# QuantLag

## Overview
QuantLag is a lagged correlation indicator that projects secondary asset data forward in time to identify leading/lagging relationships between assets. It visualizes historical values and projected paths to reveal predictive correlations.

## Core Methodology

### Lagged Projection System
Fetches secondary asset data (default: Global M2 Money Supply composite) and plots:
- **Historical Lines**: Asset values lagged backward (e.g., 50 bars ago, shown at current position)
- **Projected Lines**: Asset values projected forward using offset, creating a "future preview"

### Deviation Bands
Configurable deviation bands (1-5 levels) around the main lag, calculated as:
- Upper deviations: `mainLag + (deviation × step)`
- Lower deviations: `mainLag - (deviation × step)`

### Correlation Analysis
Computes Pearson correlation coefficients between the primary asset (close) and the lagged secondary asset across 30 configurable lengths (default: 10 to 300 bars). Results displayed in a comprehensive correlation table.

## Key Features
- **Flexible Asset Input**: Any TradingView symbol or composite formula
- **Configurable Lag Settings**: Main lag (bars), deviation steps, and number of deviation bands (0-5)
- **Correlation Table**: 30 correlation lengths with average scores per lag level
- **Color Themes**: 10 themes (DEFAULT, MONO, VAPOR, NEON, OCEAN, SUNSET, FOREST, CANDY, FIRE, ICE)
- **Inverse Color Toggle**: Swap historical/projected color assignments
- **Opacity Controls**: Fine-tune line and fill transparency

## Visual Output
- **Historical Lines**: Solid lines showing past secondary asset values
- **Projected Lines**: Forward-offset projections with gradient opacity
- **Fill Zones**: Semi-transparent bands between deviation levels
- **Correlation Table**: Real-time correlation matrix with color-coded values

## Interpretation
| Correlation | Signal |
|-------------|--------|
| +0.7 to +1.0 | Strong positive leading indicator |
| +0.3 to +0.7 | Moderate positive relationship |
| -0.3 to +0.3 | Weak/no relationship |
| -0.7 to -0.3 | Moderate negative relationship |
| -1.0 to -0.7 | Strong inverse relationship |

## Best Used For
- Identifying leading indicators (M2, interest rates, sentiment indices)
- Detecting macro-driven market movements
- Correlation-based timing strategies
- Multi-asset divergence/convergence analysis
