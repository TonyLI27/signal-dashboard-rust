# Archived Live PnL (0xb5410aE1…FBd169d)

This is the **frozen** snapshot of the Rust bot's live PnL page from the
**pre-2026-05-21** strategy era.

- Wallet: `0xb5410aE1C135A3a97C997600B27243d62FBd169d`
- Window: **2026-05-11 15:57:07 UTC → 2026-05-21 03:57:03 UTC**
- Bot config at archive time: `pnlcumsum (entry=14%) + tte1min (entry=7%)`,
  shares scheduled `5.0` → `100.0` (per
  `poly_temp_bot_stable/state/bitcoin_5min/startup_*.json`)

On 2026-05-21 the bot was restarted with a new strategy
(`continuous_every_minute` + `>7% all-in`, on three exec strategies running
in parallel — `exp_bbo` / `exp_single` / `exp_taker`). Each runs on its
own funder wallet, so live PnL is now tracked by three separate pages in
the dashboard. **This page is no longer updated.**

For the current live PnL → see the main dashboard sidebar entry
"Live PnL · 3 strategies".

## File map

| file | what it is |
|---|---|
| `index.html`         | the original static dashboard (loads `data.json` via fetch) |
| `data.json`          | the dataset rendered on the page (frozen) |
| `activity_cache.json`| raw Polymarket /activity records (forensics) |

Archived on 2026-05-21 04:33:42 UTC by `_archive_old_pnl.py`.
