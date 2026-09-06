# Hostile Pinch — Risk/Reward Retune

**Goal:** SafeCoaster stays consistently effective (positive mean net, low bankrupt) but is **not** consistently best. Risk (★ hubs, armed hulls, hot lanes) should sometimes/often beat quiet grinding on mean net and/or ceiling.

**Batch:** N=60 · engine mirrors live `hostile-pinch-live.js`.

## What changed

| Knob | Before | After |
|------|--------|-------|
| Quiet sell spread | sell = buy+1 | **sell = buy** (≈0 quiet profit) |
| ★ rich sell | Slag 12 / Parts 17 / Spice 23 / Lux 30 | **18 / 25 / 33 / 44** |
| Rich buy markup | +1 | **+2** (discourage sourcing at hubs) |
| Frigate | cost 72, pwr 3 | **cost 62**, pwr 3 |
| Gunboat | cost 64, pwr 4 | **cost 54**, pwr 4 |
| Fight salvage | 8+d10 (+6 if str>8); crate 40% | **10+d10** (+6 str>8) + heat bonus; crate **45%** |
| Tribute (War/Pirate) | base 12–20 / 8–16 × rich 1.2 × underpwr 1.15 | **base 7–12 / 5–10** × rich 1.15 × underpwr 1.12 × **cargoM** (`0.55 + 0.07×min(10,crates)`) |
| Copy | “Markets are flat…” | Quiet ≈0; ★ + surviving heat is the profit |

Pinch multipliers on hot/contested lanes **unchanged** (risk stays real).

## Before → After ranking (mean net)

### Before (N=40, prior batch)

| Rank | Strategy | Mean net | Bankrupt % |
|-----:|----------|---------:|-----------:|
| 1 | SafeCoaster | +10.9 | 0% |
| 2 | HaulerRat | +5.9 | 90% |
| 3 | ConvoyRaider | +2.8 | 70% |
| 4 | HotRunner | −3.2 | 8% |
| 5 | TributePayer | −10.0 | 0% |
| 6 | Gunboat | −11.4 | 100% |

### After (N=60, this retune)

| Rank | Strategy | Mean net | 95% CI | Std | Mean purse | Bankrupt % | Net p75 / max |
|-----:|----------|---------:|--------|-----:|-----------:|-----------:|---------------|
| 1 | **HaulerRat** | **+28.8** | [19.9, 37.7] | 37.6 | 0.2 | 100%* | 24 / **266** |
| 2 | **Gunboat** | **+21.1** | [5.8, 36.4] | 53.0 | 13.7 | 82% | 10.5 / **221** |
| 3 | **SafeCoaster** | **+6.5** | [2.9, 10.1] | 13.2 | 38.3 | **0%** | 13 / 61 |
| 4 | HotRunner | +3.8 | [1.6, 6.0] | 8.3 | 37.7 | 2% | 7.5 / 39 |
| 5 | ConvoyRaider | −0.3 | [−1.6, 0.9] | 5.1 | 9.4 | 63% | 0 / 11 |
| 6 | TributePayer | −8.7 | [−10.3, −7.1] | 4.8 | 41.3 | 0% | −4 / 0 |

\*HaulerRat ends purse-broke because it reinvests into hull + full holds; **mean tribute fell ~65 → ~20** vs prior (cargo-scaled fees). Ledger net is high from ★ sales.

## Outcome vs design goal

- **SafeCoaster:** mean net **+6.5 > 0**, bankrupt **0%** — reliable floor; rank **#3** (not #1).
- **Risk pays on mean:** HaulerRat (#1) and Gunboat (#2) beat SafeCoaster.
- **Risk pays on ceiling:** HaulerRat / Gunboat max net ≫ SafeCoaster (266 / 221 vs 61).
- Quiet grinding still works via **poor-dock sourcing** (+1 vs flat sell) and safe ★ touches — not useless.

## Files touched

- `hostile-pinch-live.html` / `hostile-pinch-live.js` (live game)
- `bot-sims/sim.py` (mirrored rules)
- `bot-sims/bots.py` (`est_tribute` cargo-aware)
- Plots refreshed under `bot-sims/plots/`

## Live / Pages

Push retuned single-file game to `sidriff/economy-hostile-pinch` → https://sidriff.github.io/economy-hostile-pinch/
