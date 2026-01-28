# MovingAverages Library - PineScript v6

A comprehensive PineScript v6 library containing **50+ Moving Average calculations** for TradingView.

---

## 📦 Installation

```pinescript
import TheTradingSpiderMan/MovingAverages/1 as MA
```

---

## 📊 All Available Moving Averages (50+)

### Basic Moving Averages

| Function | Selector Key | Description                                |
| -------- | ------------ | ------------------------------------------ |
| `sma()`  | `SMA`        | Simple Moving Average - arithmetic mean    |
| `ema()`  | `EMA`        | Exponential Moving Average                 |
| `wma()`  | `WMA`        | Weighted Moving Average                    |
| `vwma()` | `VWMA`       | Volume Weighted Moving Average             |
| `rma()`  | `RMA`        | Relative/Smoothed Moving Average           |
| `smma()` | `SMMA`       | Smoothed Moving Average (alias for RMA)    |
| `swma()` | -            | Symmetrically Weighted MA (4-period fixed) |

### Hull Family

| Function | Selector Key | Description                     |
| -------- | ------------ | ------------------------------- |
| `hma()`  | `HMA`        | Hull Moving Average             |
| `ehma()` | `EHMA`       | Exponential Hull Moving Average |

### Double/Triple Smoothed

| Function       | Selector Key | Description                       |
| -------------- | ------------ | --------------------------------- |
| `dema()`       | `DEMA`       | Double Exponential Moving Average |
| `tema()`       | `TEMA`       | Triple Exponential Moving Average |
| `tma()`        | `TMA`        | Triangular Moving Average         |
| `t3()`         | `T3`         | Tillson T3 Moving Average         |
| `twma()`       | `TWMA`       | Triple Weighted Moving Average    |
| `swwma()`      | `SWWMA`      | Smoothed Weighted Moving Average  |
| `trixSmooth()` | `TRIXSMOOTH` | Triple EMA Smoothed               |

### Zero/Low Lag

| Function  | Selector Key | Description                         |
| --------- | ------------ | ----------------------------------- |
| `zlema()` | `ZLEMA`      | Zero Lag Exponential MA             |
| `lsma()`  | `LSMA`       | Least Squares Moving Average        |
| `epma()`  | `EPMA`       | Endpoint Moving Average             |
| `ilrs()`  | `ILRS`       | Integral of Linear Regression Slope |

### Adaptive Moving Averages

| Function   | Selector Key | Description                     |
| ---------- | ------------ | ------------------------------- |
| `kama()`   | `KAMA`       | Kaufman Adaptive Moving Average |
| `frama()`  | `FRAMA`      | Fractal Adaptive Moving Average |
| `vidya()`  | `VIDYA`      | Variable Index Dynamic Average  |
| `vma()`    | `VMA`        | Variable Moving Average         |
| `vama()`   | `VAMA`       | Volume Adjusted Moving Average  |
| `rvma()`   | `RVMA`       | Rolling VMA                     |
| `apexMA()` | `APEXMA`     | Apex Moving Average             |

### Ehlers Filters

| Function          | Selector Key    | Description                       |
| ----------------- | --------------- | --------------------------------- |
| `superSmoother()` | `SUPERSMOOTHER` | Ehlers Super Smoother             |
| `butterworth2()`  | `BUTTERWORTH2`  | 2-Pole Butterworth Filter         |
| `butterworth3()`  | `BUTTERWORTH3`  | 3-Pole Butterworth Filter         |
| `instantTrend()`  | `INSTANTTREND`  | Ehlers Instantaneous Trendline    |
| `edsma()`         | `EDSMA`         | Deviation Scaled Moving Average   |
| `mama()`          | `MAMA`          | Mesa Adaptive Moving Average      |
| `fama()`          | `FAMAVAL`       | Following Adaptive Moving Average |

### Laguerre Family

| Function             | Selector Key       | Description              |
| -------------------- | ------------------ | ------------------------ |
| `laguerreFilter()`   | `LAGUERRE`         | Laguerre Filter          |
| `adaptiveLaguerre()` | `ADAPTIVELAGUERRE` | Adaptive Laguerre Filter |

### Special Weighted

| Function   | Selector Key | Description                      |
| ---------- | ------------ | -------------------------------- |
| `alma()`   | `ALMA`       | Arnaud Legoux Moving Average     |
| `sinwma()` | `SINWMA`     | Sine Weighted Moving Average     |
| `gwma()`   | `GWMA`       | Gaussian Weighted Moving Average |
| `nma()`    | `NMA`        | Natural Moving Average           |

### Jurik/McGinley/Coral

| Function     | Selector Key | Description           |
| ------------ | ------------ | --------------------- |
| `jma()`      | `JMA`        | Jurik Moving Average  |
| `mcginley()` | `MCGINLEY`   | McGinley Dynamic      |
| `coral()`    | `CORAL`      | Coral Trend Indicator |

### Mean Types

| Function       | Selector Key | Description               |
| -------------- | ------------ | ------------------------- |
| `medianMA()`   | `MEDIANMA`   | Median Moving Average     |
| `gma()`        | `GMA`        | Geometric Moving Average  |
| `harmonicMA()` | `HARMONICMA` | Harmonic Moving Average   |
| `trimmedMA()`  | `TRIMMEDMA`  | Trimmed Moving Average    |
| `cma()`        | `CMA`        | Cumulative Moving Average |

### Volume-Based

| Function  | Selector Key | Description                |
| --------- | ------------ | -------------------------- |
| `evwma()` | `EVWMA`      | Elastic Volume Weighted MA |

### Other Specialized

| Function          | Selector Key    | Description                 |
| ----------------- | --------------- | --------------------------- |
| `hwma()`          | `HWMA`          | Holt-Winters Moving Average |
| `gdema()`         | `GDEMA`         | Generalized DEMA            |
| `rema()`          | `REMA`          | Regularized EMA             |
| `modularFilter()` | `MODULARFILTER` | Modular Filter              |
| `rmt()`           | `RMT`           | Recursive Moving Trendline  |
| `qrma()`          | `QRMA`          | Quadratic Regression MA     |
| `wilderSmooth()`  | `WILDERSMOOTH`  | Welles Wilder Smoothing     |
| `leoMA()`         | `LEOMA`         | Leo Moving Average          |
| `ahrensMA()`      | `AHRENSMA`      | Ahrens Moving Average       |
| `runningMA()`     | `RUNNINGMA`     | Running Moving Average      |
| `ppoMA()`         | `PPOMA`         | PPO-based Moving Average    |
| `fisherMA()`      | `FISHERMA`      | Fisher Transform MA         |

---

## 🎯 Helper Functions

| Function         | Description                                                   |
| ---------------- | ------------------------------------------------------------- |
| `wcp()`          | Weighted Close Price: (H+L+2\*C)/4                            |
| `typicalPrice()` | Typical Price: (H+L+C)/3                                      |
| `medianPrice()`  | Median Price: (H+L)/2                                         |
| `selector()`     | **Master selector** - choose any MA by string name            |
| `getAllTypes()`  | Returns all supported MA type names as comma-separated string |

---

## 🔧 Usage Examples

### Basic Usage

```pinescript
//@version=6
indicator("MA Example")
import quantablex/moving_averages/1 as MA

// Simple calls
plot(MA.sma(close, 20), "SMA 20", color.blue)
plot(MA.ema(close, 20), "EMA 20", color.red)
plot(MA.hma(close, 20), "HMA 20", color.green)
```

### Using the Selector Function (50+ MA Types)

```pinescript
//@version=6
indicator("MA Selector")
import quantablex/moving_averages/1 as MA

// Full list of all supported types:
// SMA,EMA,WMA,VWMA,RMA,SMMA,HMA,EHMA,DEMA,TEMA,TMA,T3,TWMA,SWWMA,TRIXSMOOTH,
// ZLEMA,LSMA,EPMA,ILRS,KAMA,FRAMA,VIDYA,VMA,VAMA,RVMA,APEXMA,SUPERSMOOTHER,
// BUTTERWORTH2,BUTTERWORTH3,INSTANTTREND,EDSMA,LAGUERRE,ADAPTIVELAGUERRE,
// ALMA,SINWMA,GWMA,NMA,JMA,MCGINLEY,CORAL,MEDIANMA,GMA,HARMONICMA,TRIMMEDMA,
// EVWMA,HWMA,GDEMA,REMA,MODULARFILTER,RMT,QRMA,WILDERSMOOTH,LEOMA,AHRENSMA,
// RUNNINGMA,PPOMA,MAMA,FAMAVAL,FISHERMA,CMA

maType = input.string("EMA", "MA Type", options=["SMA","EMA","WMA","VWMA","HMA","DEMA","TEMA","KAMA","T3","ALMA","FRAMA","VIDYA","JMA","MCGINLEY","SUPERSMOOTHER","LAGUERRE","BUTTERWORTH2","MAMA"])
length = input.int(20, "Length")

plot(MA.selector(close, length, maType), "Selected MA", color.orange)
```

### Advanced Moving Averages

```pinescript
//@version=6
indicator("Advanced MAs")
import quantablex/moving_averages/1 as MA

// ALMA with custom offset and sigma
plot(MA.alma(close, 20, 0.85, 6), "ALMA", color.purple)

// KAMA with custom fast/slow periods
plot(MA.kama(close, 10, 2, 30), "KAMA", color.teal)

// T3 with custom volume factor
plot(MA.t3(close, 20, 0.7), "T3", color.yellow)

// Laguerre Filter with custom gamma
plot(MA.laguerreFilter(close, 0.8), "Laguerre", color.lime)
```

---

## 📈 MA Selection Guide

| Use Case               | Recommended MAs                             |
| ---------------------- | ------------------------------------------- |
| **Trend Following**    | EMA, DEMA, TEMA, HMA, CORAL                 |
| **Low Lag Required**   | ZLEMA, HMA, EHMA, JMA, LSMA                 |
| **Volatile Markets**   | KAMA, VIDYA, FRAMA, VMA, ADAPTIVELAGUERRE   |
| **Smooth Signals**     | T3, LAGUERRE, SUPERSMOOTHER, BUTTERWORTH2/3 |
| **Support/Resistance** | SMA, WMA, TMA, MEDIANMA                     |
| **Scalping**           | MCGINLEY, ZLEMA, HMA, INSTANTTREND          |
| **Noise Reduction**    | MAMA, EDSMA, GWMA, TRIMMEDMA                |
| **Volume-Based**       | VWMA, EVWMA, VAMA                           |

---

## ⚙️ Parameters Reference

### Common Parameters

- `src` - Source series (close, open, hl2, hlc3, etc.)
- `len` - Period length (integer)

### Special Parameters

- `alma()`: `offset` (0-1), `sigma` (curve shape)
- `kama()`: `fastLen`, `slowLen`
- `t3()`: `vFactor` (volume factor)
- `jma()`: `phase` (-100 to 100)
- `laguerreFilter()`: `gamma` (0-1 damping)
- `rema()`: `lambda` (regularization)
- `modularFilter()`: `beta` (sensitivity)
- `gdema()`: `mult` (multiplier, 2 = standard DEMA)
- `trimmedMA()`: `trimPct` (0-0.5, percentage to trim)
- `mama()/fama()`: `fastLimit`, `slowLimit`
- `adaptiveLaguerre()`: Uses `len` for adaptation period

---

## 📝 Notes

- All 50+ functions are exported for use in any PineScript v6 indicator/strategy
- The `selector()` function supports **all MA types** via string key
- Use `getAllTypes()` to get a comma-separated list of all supported MA names
- Some MAs (CMA, INSTANTTREND, LAGUERRE, MAMA) don't use `len` parameter
- Use `nz()` wrapper if handling potential NA values in your calculations

---

**Author:** thetradingspiderman
**Version:** 1.0
**PineScript Version:** 6
**Total MA Types:** 50+
