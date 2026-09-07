# Why nobody dies (and the T30 lethality nudge)

## Survive metric

**Survive** = still have ≥1 ship when the clock ends (`turn > TURNS`).
Bankrupt (purse < 10) ≠ dead. You can be broke and still "alive."

## Live `doFight` loss path (pre-nudge)

Ship loss happens **only on a lost fight** — wins never strip hulls.

On a loss (old):

```js
const shipRisk = power()+1 < enc.str ? 0.28 : 0.1;
if (Math.random() < shipRisk && S.ships.length) loseShip();
```

So even a bad loss is usually cargo/coin pinch, not a hull:

| Matchup | shipRisk (old) |
|---------|----------------|
| Under-armed (`power()+1 < enc.str`) | 28% |
| Covered / even | 10% |

`loseShip()` can wipe the **last** hull (sets `S.ships = []` → run ends). But with a 10–28% gate **and** only ~14 turns of fights, a full fleet wipe was vanishingly rare — stance bots routinely showed ~98–100% survive %.

## T30 + lethality nudge (current)

1. **`TURNS = 30`** — roughly 2× fight exposure vs the old 14-turn clock.
2. **Higher base shipRisk** on loss:

```js
let shipRisk = power()+1 < enc.str ? 0.42 : 0.16;
if (S.ships.length === 1) shipRisk *= 1.35;
```

| Matchup | shipRisk (new) | last-hull ×1.35 |
|---------|----------------|-----------------|
| Under-armed | 42% | ~56.7% |
| Covered / even | 16% | ~21.6% |

Still not guaranteed death: many losses only pinch cargo/coin; multi-ship fleets need repeated hull hits; Leave / Tribute avoid the fight-loss path entirely.

Mirrored in `bot-sims/sim.py` so stance batches match Pages.

## Reading batch numbers

- **Bankrupt %** — purse < 10 (or no ships) at end; economic failure.
- **Fleet wiped %** — `survived=false` / ships empty at end (`fleet_gone`); true death.
- **Survive %** — still have ≥1 ship at clock end.

See `bot-sims/T30_BATCH.md` for ranking + wipe rates after the T30 re-run.
