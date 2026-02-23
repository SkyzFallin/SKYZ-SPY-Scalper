<p align="center">
  <img src="skyz_spy_scalper_logo.svg" alt="SKYZ SPY Scalper Logo" width="100%" />
</p>

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

Change the `PROFILE` variable at the top of the script to switch between modes.

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

## Not Financial Advice

This project is provided for **educational and informational purposes only**. Nothing in this repository constitutes financial advice, investment advice, trading advice, or any other form of professional advice. The creator of this indicator is not a licensed financial advisor, broker, or dealer.

Trading options and equities involves substantial risk of loss and is not suitable for all investors. Past performance of any trading system, methodology, or indicator is not necessarily indicative of future results. You should not trade with money you cannot afford to lose.

**You are solely responsible for your own trading decisions.** Always do your own research and consult with a qualified financial professional before making any investment decisions.

---

## Disclaimer

This indicator:

- Does **not** auto-trade or place orders
- Does **not** guarantee reversals or directional outcomes
- Is a **visual decision-support tool** only

Trade management and risk control are the edge. This tool provides structure — execution is yours.
