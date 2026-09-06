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
| Copy | Markets are flat… | Quiet ≈0; ★ + surviving heat is the profit |

Pinch multipliers on hot/contested lanes **unchanged** (risk stays real).

## Before → After ranking (mean net)

### Before (N=40)

| Rank | Strategy | Mean net | Bankrupt % |
|-----:|----------|---------:|-----------:|
| 1 | SafeCoaster | +10.9 | 0% |
| 2 | HaulerRat | +5.9 | 90% |
| 3 | ConvoyRaider | +2.8 | 70% |
| 4 | HotRunner | −3.2 | 8% |
| 5 | TributePayer | −10.0 | 0% |
| 6 | Gunboat | −11.4 | 100% |

### After (N=60)

| Rank | Strategy | Mean net | 95% CI | Bankrupt % | Net p75 / max |
|-----:|----------|---------:|--------|-----------:|---------------|
| 1 | **HaulerRat** | **+28.8** | [19.9, 37.7] | 100%* | 24 / **266** |
| 2 | **Gunboat** | **+21.1** | [5.8, 36.4] | 82% | 10.5 / **221** |
| 3 | **SafeCoaster** | **+6.5** | [2.9, 10.1] | **0%** | 13 / 61 |
| 4 | HotRunner | +3.8 | [1.6, 6.0] | 2% | 7.5 / 39 |
| 5 | ConvoyRaider | −0.3 | [−1.6, 0.9] | 63% | 0 / 11 |
| 6 | TributePayer | −8.7 | [−10.3, −7.1] | 0% | −4 / 0 |

*HaulerRat purse-broke from reinvestment; mean tribute ~65→~20.

## Outcome

- SafeCoaster: mean +6.5, bankrupt 0%, rank **#3** (reliable floor, not #1).
- Risk pays on mean: HaulerRat #1, Gunboat #2.
- Risk pays on ceiling: max net 266/221 vs SafeCoaster 61.

## Live

https://sidriff.github.io/economy-hostile-pinch/

Workspace canonical: `hostile-pinch-live.html` (full readable source).
