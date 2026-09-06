# Economy Lab SEARCH · Variant B — Hostile Pinch · **KEPT**

**Status:** KEPT direction for SEARCH. Variants A (distance trade) and C (crew/reputation) remain playable thrash bets but are **not primary**.

**GitHub:** https://github.com/sidriff/economy-hostile-pinch

Also mirrored at `../v2-hostile-pinch/` (same build). This folder is the obvious KEPT snapshot.

**Thesis:** Markets are flatter (goods less about distance). Profit comes from **running hot routes through contested space**. Heavily armed War fleets and pirates cluster near rich systems (Crown / Ore / Gilt). Trade fleets are prey. Over-arm and you haul less (ships gate capacity); under-arm and you get pinched (lose cargo/coin). Leaving costs consumables or time; fighting risks ships; trading with War often means **tribute** (protection racket). Poor is feelable. Phone-first 2D one-layer.

Lab family: Spacefleet Economy Lab SEARCH · owns `purse`, capacity tradeoff, encounter decisions.  
Constitution: *Gains are measured by costs* — end-of-run ledger shows coin earned vs tribute, cargo lost, ships lost.

## How to open

```bash
cd /workspace/spacefleet-economy-lab/kept-hostile-pinch
# or: cd /workspace/spacefleet-economy-lab/v2-hostile-pinch
python3 -m http.server 8766
# → http://localhost:8766/
# or open index.html via file://
```

Single file: `index.html` (HTML + CSS + vanilla JS, no deps, no build). Phone-first portrait (~420–480px).

## Polish (kept deepenings)

1. **Arm vs haul meter** — always-visible HUD strip: combat power vs Pirate (5–10) / War (7–12) bands, plus goods hold used/free. Warns when hold is too thin for a real haul.
2. **NPC fleets on the map** — 3–6 typed markers (W/P/L/T) parked near systems; denser near rich hubs. Lane bumps bias encounter rolls so the map lies less.
3. **Sharper pinch** — under-armed on hot approaches: bigger goods/coin loss on failed fight or unpaid tribute. Over-armed: UI calls out thin hold at rich hubs.
4. **Pre-launch odds** — Travel tab shows quiet / hot / contested for the selected lane, your power vs expected threat, before Launch.
5. **End-of-run ledger** — coin earned, tribute paid, cargo lost to pinches, ships lost (gains − costs).

## Decision feel

| Choice | Feel |
|---|---|
| **Arm heavy** (Gunboat / Frigate + weapons/crew) | Survive War & Pirates on approaches to Crown / Ore / Gilt — but hold shrinks; fewer goods to sell. |
| **Haul heavy** (Hauler + goods) | Fat purse *if* you arrive — pinched hard when under-gunned. |
| **Fight** | Auto-resolve from weapons+crew vs NPC strength. Win = salvage; lose = coin/cargo/ship risk. |
| **Leave** | Burns consumables; if dry, burns a turn + leaks coin. |
| **Trade / Tribute** | War/Pirate = pay protection; Patrol waves armed fleets; Trade convoys = soft prey or mild swap. |

## 60-second how-to-play

1. Start at **Ash Dock** with a Scout, thin purse, light weapons/consumables/crew. Read the **Arm vs haul** strip — power vs Pirate/War bands, goods free slots.
2. **Fleet** — buy a Hauler (haul) or Frigate/Gunboat (teeth). Capacity is shared: weapons + consumables + crew + goods.
3. **Market** — buy goods (spreads are flat). Sell at ★ **rich hubs** (Crown, Ore, Gilt) for the bump.
4. **Travel** — tap a linked neighbor → read **pre-launch odds** (quiet / hot / contested + your power vs threat) → **Launch**.
5. Map markers (W/P/L/T) park near systems; bumping them biases encounters. **Fight / Leave / Trade** — tribute taxes profit; under-arm pinches the hold harder.
6. ~14 turns. End ledger scores gains against tribute, cargo lost, ships lost. Playable in 2–3 minutes.

## Map

~10 systems, one 2D layer (no inner systems). NPC markers denser near Crown / Ore / Gilt; Trade in quieter space.

## Aesthetic

`#10080a` bg · accent `#c47848` / `#e8a070` · purse + capacity + score HUD · arm/haul strip · Spacefleet-ish monospace.

## Repository

Repo: https://github.com/sidriff/economy-hostile-pinch
