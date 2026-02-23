# SKYZ SPY Scalper (Webull Custom Indicator)

A 1-minute optimized SPY scalping indicator built for fast stop/limit execution and short hold times (5-15 minutes).

Designed for traders who:

- Trade SPY intraday on the 1-minute chart
- Use tight stop losses with defined risk
- Take quick limit targets and scale out
- Want structured entries instead of guessing tops and bottoms

---

## Core Strategy Logic

This indicator combines multiple filters to generate high-probability pullback continuation signals in the direction of the dominant micro-trend.

### Trend Alignment

- EMA Fast / Mid / Slow stack determines trend direction
- Only generates signals in the direction of the prevailing micro-trend

### Pullback Continuation Entries

- Waits for price to pull back to the mid EMA
- Triggers on reclaim of the fast EMA
- Avoids chasing extended candles away from structure

### Momentum Confirmation

- RSI filter prevents entries on weak or exhausted breakouts

### Volume Filter

- Confirms participation behind the move before signaling

### ATR-Based Risk Framework

- Stop-loss guide calculated from current volatility
- Two target bands for scaling out or taking quick exits

---

## Hold Profiles (5 / 10 / 15 Minutes)

The indicator includes three adjustable internal presets that control signal sensitivity and risk parameters.

| Profile | Use Case | Behavior |
|---------|----------|----------|
| 5 min | Quick pops | More signals, tighter stops |
| 10 min | Balanced | Default micro-swing behavior |
| 15 min | Cleaner swings | Fewer signals, wider targets |

Change the \`PROFILE\` variable at the top of the script to switch between modes.

---

## Optional Add-On: Exhaustion Signals

Includes potential top/bottom zone markers using:

- ATR stretch detection to identify overextended moves
- Simple RSI divergence for early reversal warnings
- Chop filter to avoid fading strong trending conditions

These mark probable reversal zones, not standalone entry signals. They are intended as context overlays to support discretionary decision-making.

---

## Intended Workflow (1-Minute Chart)

1. Wait for a signal dot in the direction of the trend
2. Place stop near the ATR-based guide level
3. Set limit at Target 1, or scale into Target 2
4. Exit immediately if price structure breaks down

Built for fast decision-making, not prediction.

---

## Disclaimer

This indicator:

- Does **not** auto-trade or place orders
- Does **not** guarantee reversals or directional outcomes
- Is a **visual decision-support tool** only

Trade management and risk control are the edge. This tool provides structure — execution is yours.
