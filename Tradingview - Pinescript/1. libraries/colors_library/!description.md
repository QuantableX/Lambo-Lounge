# ColorsLibrary - PineScript v6

A comprehensive PineScript v6 library containing **10 color themes** and utility functions for TradingView.

---

## 📦 Installation

```pinescript
import TheTradingSpiderMan/ColorsLibrary/2 as CLR
```

---

## 🎨 All Available Color Themes (10)

### Default Theme (Green/Red - Classic Trading)

| Function           | Description     |
| ------------------ | --------------- |
| `defaultBull()`    | Green (#26A69A) |
| `defaultBear()`    | Red (#EF5350)   |
| `defaultNeutral()` | Grey (#787B86)  |

### Monochrome Theme (White/Grey/Black)

| Function        | Description          |
| --------------- | -------------------- |
| `monoBull()`    | White (#FFFFFF)      |
| `monoBear()`    | Grey (#808080)       |
| `monoNeutral()` | Grey (#B8B8B8)       |
| `monoLight()`   | Light Grey (#C0C0C0) |
| `monoDark()`    | Dark Grey (#404040)  |

### Vaporwave Theme (Purple/Pink, Blue/Cyan)

| Function         | Description             |
| ---------------- | ----------------------- |
| `vaporBull()`    | Cyan (#00FFFF)          |
| `vaporBear()`    | Magenta (#FF00FF)       |
| `vaporNeutral()` | Grey (#787B86)          |
| `vaporPurple()`  | Purple (#9B59B6)        |
| `vaporPink()`    | Hot Pink (#FF6EC7)      |
| `vaporBlue()`    | Electric Blue (#0080FF) |

### Neon Theme (Bright Fluorescent Colors)

| Function        | Description           |
| --------------- | --------------------- |
| `neonBull()`    | Neon Green (#39FF14)  |
| `neonBear()`    | Neon Red (#FF073A)    |
| `neonNeutral()` | Grey (#787B86)        |
| `neonYellow()`  | Neon Yellow (#FFFF00) |
| `neonOrange()`  | Neon Orange (#FF6600) |
| `neonBlue()`    | Neon Blue (#00BFFF)   |

### Ocean Theme (Blues and Teals)

| Function         | Description         |
| ---------------- | ------------------- |
| `oceanBull()`    | Teal (#20B2AA)      |
| `oceanBear()`    | Deep Blue (#1E3A5F) |
| `oceanNeutral()` | Grey (#787B86)      |
| `oceanAqua()`    | Aqua (#00CED1)      |
| `oceanNavy()`    | Navy (#000080)      |
| `oceanSeafoam()` | Seafoam (#3EB489)   |

### Sunset Theme (Oranges, Yellows, Reds)

| Function          | Description             |
| ----------------- | ----------------------- |
| `sunsetBull()`    | Golden Yellow (#FFD700) |
| `sunsetBear()`    | Crimson (#DC143C)       |
| `sunsetNeutral()` | Grey (#787B86)          |
| `sunsetOrange()`  | Orange (#FF8C00)        |
| `sunsetCoral()`   | Coral (#FF7F50)         |
| `sunsetPurple()`  | Twilight (#8B008B)      |

### Forest Theme (Greens and Browns)

| Function          | Description            |
| ----------------- | ---------------------- |
| `forestBull()`    | Forest Green (#228B22) |
| `forestBear()`    | Brown (#8B4513)        |
| `forestNeutral()` | Grey (#787B86)         |
| `forestLime()`    | Lime Green (#32CD32)   |
| `forestOlive()`   | Olive (#6B8E23)        |
| `forestEarth()`   | Earth Brown (#704214)  |

### Candy Theme (Pastel/Soft Colors)

| Function          | Description          |
| ----------------- | -------------------- |
| `candyBull()`     | Mint Green (#98FB98) |
| `candyBear()`     | Soft Pink (#FFB6C1)  |
| `candyNeutral()`  | Grey (#787B86)       |
| `candyLavender()` | Lavender (#E6E6FA)   |
| `candyPeach()`    | Peach (#FFDAB9)      |
| `candySky()`      | Sky Blue (#87CEEB)   |

### Fire Theme (Reds, Oranges, Yellows)

| Function        | Description            |
| --------------- | ---------------------- |
| `fireBull()`    | Flame Orange (#FF5722) |
| `fireBear()`    | Dark Red (#B71C1C)     |
| `fireNeutral()` | Grey (#787B86)         |
| `fireYellow()`  | Flame Yellow (#FFC107) |
| `fireEmber()`   | Ember (#FF6F00)        |
| `fireAsh()`     | Ash Grey (#424242)     |

### Ice Theme (Cool Blues and Whites)

| Function       | Description            |
| -------------- | ---------------------- |
| `iceBull()`    | Ice Blue (#B3E5FC)     |
| `iceBear()`    | Frost Blue (#0277BD)   |
| `iceNeutral()` | Grey (#787B86)         |
| `iceWhite()`   | Snow White (#F5F5F5)   |
| `iceCrystal()` | Crystal Blue (#81D4FA) |
| `iceFrost()`   | Frost (#4FC3F7)        |

---

## 🔧 Selector & Utility Functions

| Function             | Description                                         |
| -------------------- | --------------------------------------------------- |
| `bullColor()`        | Get bullish color by theme name                     |
| `bearColor()`        | Get bearish color by theme name                     |
| `trendColor()`       | Returns bull/bear color based on boolean condition  |
| `gradientColor()`    | Creates gradient between bull/bear (0-100 value)    |
| `rsiGradient()`      | RSI-style coloring (oversold=bull, overbought=bear) |
| `candleColor()`      | Returns color based on candle direction             |
| `volumeColor()`      | Returns color based on close vs previous close      |
| `withTransparency()` | Applies transparency to any color                   |
| `getAllThemes()`     | Returns comma-separated list of all theme names     |
| `getThemeOptions()`  | Returns array of theme names for input options      |

---

## 🔧 Usage Examples

### Basic Usage

```pinescript
//@version=6
indicator("Color Example")
import quantablex/colors_library/1 as CLR

// Direct color usage
plot(close, "Close", CLR.defaultBull())
plot(open, "Open", CLR.defaultBear())

// With transparency
plot(high, "High", CLR.vaporPurple(50))
```

### Using Theme Selector

```pinescript
//@version=6
indicator("Theme Selector")
import quantablex/colors_library/1 as CLR

theme = input.string("DEFAULT", "Color Theme",
    options=["DEFAULT","MONO","VAPOR","NEON","OCEAN","SUNSET","FOREST","CANDY","FIRE","ICE"])

bullCol = CLR.bullColor(theme)
bearCol = CLR.bearColor(theme)

plot(close, "Close", close >= open ? bullCol : bearCol)
```

### Trend Coloring

```pinescript
//@version=6
indicator("Trend Colors")
import quantablex/colors_library/1 as CLR

theme = input.string("VAPOR", "Theme")
ma = ta.ema(close, 20)

// Auto trend color based on condition
trendCol = CLR.trendColor(close > ma, theme)
plot(ma, "EMA", trendCol, 2)
```

### Gradient & RSI Coloring

```pinescript
//@version=6
indicator("Gradient Example")
import quantablex/colors_library/1 as CLR

rsi = ta.rsi(close, 14)

// Gradient based on RSI value
gradCol = CLR.gradientColor(rsi, "NEON")
plot(rsi, "RSI", gradCol)

// Or use built-in RSI gradient
rsiCol = CLR.rsiGradient(rsi, "DEFAULT")
bgcolor(rsiCol, transp=90)
```

### Candle & Volume Coloring

```pinescript
//@version=6
indicator("Candle Colors", overlay=true)
import quantablex/colors_library/1 as CLR

theme = input.string("FIRE", "Theme")

// Auto candle coloring
barcolor(CLR.candleColor(theme))

// Volume bars colored by direction
plotshape(volume, style=shape.circle, color=CLR.volumeColor(theme, 30))
```

---

## 🎨 Theme Selection Guide

| Use Case              | Recommended Themes    |
| --------------------- | --------------------- |
| **Classic Trading**   | DEFAULT, MONO         |
| **Dark Mode Charts**  | NEON, VAPOR, ICE      |
| **Light Mode Charts** | CANDY, SUNSET, FOREST |
| **High Visibility**   | NEON, FIRE            |
| **Low Eye Strain**    | OCEAN, CANDY, ICE     |
| **Professional Look** | MONO, DEFAULT, OCEAN  |
| **Aesthetic/Stylish** | VAPOR, SUNSET, CANDY  |

---

## ⚙️ Parameters Reference

### Common Parameters

- `transparency` - Transparency level (0-100, where 0=opaque, 100=invisible)

### Selector Parameters

- `theme` - Theme name string: `DEFAULT`, `MONO`, `VAPOR`, `NEON`, `OCEAN`, `SUNSET`, `FOREST`, `CANDY`, `FIRE`, `ICE`

---

## 📝 Notes

- All functions accept optional `transparency` parameter (default 0)
- Theme selector functions default to `DEFAULT` theme if invalid name provided
- Use `getAllThemes()` to get comma-separated list of all theme names
- Use `getThemeOptions()` to get array for `input.string` options
- All 50+ color functions are exported for direct use

---

**Author:** thetradingspiderman
**Version:** 1.0
**PineScript Version:** 6
**Total Themes:** 10
**Total Color Functions:** 50+
