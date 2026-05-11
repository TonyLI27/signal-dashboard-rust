# signal-dashboard-rust

Daily tie-out dashboard for the Rust BTC 5-min bot
([poly_temp_bot](https://github.com/TonyLI27/poly_temp_bot)) — verifies the
bot's live `smart_ratio` series against a frozen-tag offline backtest using
the snapshot the bot loaded at startup.

**Site:** https://tonyli27.github.io/signal-dashboard-rust/

This repo is **publish target only** — auto-populated by
`signal_dashboard_for_rust/_publish.py` from the local pipeline.
Don't edit `docs/latest/` by hand; it's wiped on each push. The pipeline
source code lives elsewhere on the publisher's machine, not in this repo.

## What this dashboard shows

- **Rust funder PnL** — every BTC 5-min market the bot's funder wallet
  (`0x4a19…a961`) has touched since the comparison start (2026-05-11
  18:00:59 UTC). Per-market BUY + REDEEM aggregated, 5-min resampled
  cumulative line, plus an entry-price regime histogram.
- **Tie-Out** — per signal (`pnlcumsum`, `tte1min`) and across both:
  - Online (bot live) smart_ratio vs Offline (frozen-tag) smart_ratio
    — time series + Pearson r scatter.
  - Net PnL cumsum: offline frozen-tag backtest vs online SR-replay vs
    offline rolling-tag (windowed from the main dashboard).
  - Venn diagram of entered markets (online vs offline).
- **Overview** — combined offline PnL vs real-account PnL, plus a
  price-compare table (price1 = offline mid, price2 = bot's
  AGGREGATE-time mid, price3 = on-chain weighted entry price).

## Companion site (main dashboard)

Python bot's full daily backtest + alpha-decay tracking lives at:
https://tonyli27.github.io/signal-dashboard/
