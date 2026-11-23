 
# 🎯 HTF Order Block + Golden Pocket Reversal & Zone Fill Engine
**Pine Script™ v6 Multi-Timeframe (`1H` / `4H` / `1D`) Reversal Zone Tracker for `15m` / `5m` LTF Execution — Separating Buy (Demand) & Sell (Supply) OB/GP Zones with Fill % & Break Risk Table**

---

### 1. Live Chart Overview & HTF Reversal Strategy Workflow

<img width="2976" height="1438" alt="Gemini_Generated_Image_uquwsuquwsuquwsu"
src="https://github.com/user-attachments/assets/9cdb244a-de30-4567-b2a6-b29fd1affd03" />

Built in **Pine Script™ v6** (`overlay=true`), this engine identifies high-impact **Higher Timeframe (HTF) reversal zones** — primarily **Order Blocks (`OB`)** and **Golden Pockets (`GP`)** — so traders can spot strong turning points and execute entries on Lower Timeframes (`15m` / `5m`).

#### How to Read & Trade With This Engine
- **High-Power `4H` & `1D` Reversal Zones:** `4H` and `1D` OB / GP zones carry strong institutional weight capable of reversing market direction. When price taps a `4H` or `1D` zone, traders watch for a clean reversal reaction.
- **`1H` Confirmation for `15m` / `5m` Entries:** `1H` zones help confirm trades taken on `15m` and `5m` LTF charts alongside lower-timeframe execution signals.
- **Clear Separation of Buy & Sell Zones:** **Buy (Demand) OB/GP** zones and **Sell (Supply) OB/GP** zones are separated and clearly labeled so bullish and bearish levels never get mixed up on the chart or in the table.
- **Fill % & Break Risk (`~70%` Watch):** The built-in table shows how much order fill each OB/GP has experienced and whether it is nearing a break — around **`70%` fill**, zones become vulnerable to breaking rather than holding as fresh reversal levels.

---

### 2. Core Technical & Filtering Mechanics

- **Real Breakout Filtering:** Evaluates swing highs/lows and requires a **confirmed candle close beyond the swing** plus body expansion (`body > avgBody * htfBodyMult`) to filter weak/fake moves before locating the opposing OB candle.
- **Golden Pocket & Star (`★`) Overlap Confluence:** Plots Golden Pocket boxes (`0.618`–`0.65` Fibonacci retracement by default) and flags overlapping OB + GP zones with a **`★`** star marker.
- **Configurable Fill % & Health Lifecycle:** Measures zone fill using either **Wick** or **Close** mode (`fillMode`), dynamically updates status (**`FRESH`**, **`TESTED`**, **`WEAK`**, **`NEAR BREAK !!`**), fades box opacity as zones weaken, and **automatically removes zones at `100%` fill**.

---

### 3. Live `OB / GP ZONES` Distance-Sorted Table

The built-in **OB / GP ZONES** table sorts active Supply (Sell) zones above price and Demand (Buy) zones below price around live price (`► PRICE`):

| Table Column | What It Displays |
| :--- | :--- |
| **Zone & Confluence** | Timeframe (`1H`, `4H`, `1D`), separated **Demand (Buy)** or **Supply (Sell)**, **OB** or **GP**, and **`★`** when OB and GP overlap. |
| **Range** | Exact price band (`bottom – top`) formatted to the instrument's tick precision. |
| **Fill %** | Visual 10-block progress bar (`█` / `░`) + exact fill percentage (`0%` to `<100%`) to monitor fill buildup toward break levels (~`70%`+). |
| **Status** | Real-time state (`FRESH`, `TESTED`, `WEAK`, `NEAR BREAK !!`) plus a `◄ price` tag when price is inside the zone. |

---

### 4. Built-In TradingView Alert Conditions

- **Price entered a Demand zone** / **Price entered a Supply zone** (confirmed bar touch)
- **A zone is NEAR BREAK** (when a zone crosses the `nearBreakAt` fill threshold)
- **A zone is fully filled (removed)** (when a zone hits `100%` fill and is cleared)
