# Hostile Pinch · Economy Lab SEARCH

Phone-first 2D thrash of the **Hostile Pinch** economy thesis. Public lab sketch — **not** the live Spacefleet graph, and **not** shipped on [spacefleet-labs.pages.dev](https://spacefleet-labs.pages.dev).

**Play:** https://sidriff.github.io/economy-hostile-pinch/

**Repo:** https://github.com/sidriff/economy-hostile-pinch

## Latest retune (risk/reward)

Single clean `index.html` (no chunk loader). Quiet markets sell≈buy (flat spreads). ★ rich hubs pay: Slag 18 / Parts 25 / Spice 33 / Lux 44. Combat hulls: Frigate ¤62, Gunboat ¤54.

## Thesis

Markets are flatter — goods are not a distance puzzle. Profit is **running hot routes through contested space**. War fleets and pirates cluster on the approaches to the rich hubs **Crown / Ore / Gilt**. Trade fleets are prey.

Ships **gate shared capacity** (weapons, consumables, crew, goods). Over-arm and the hold shrinks. Under-arm and you get **pinched** (cargo, coin, sometimes a hull). Leave burns cells or time. Fight risks ships. Trading with War or pirates is usually **tribute**.

Poor is feelable. Gains are measured by costs — the end-run ledger puts coin earned against tribute, cargo lost, and ships lost.

## Play

Single file, no build, no deps. Phone portrait, max-width ~460px.

1. Start at **Ash Dock** with a Scout, thin purse, light guns/cells/crew. Read the always-on **Arm vs haul** strip (power vs Pirate 5–10 / War 7–12, plus free goods slots).
2. **Fleet** — Hauler for hold, Frigate/Gunboat for teeth. Shared cap.
3. **Market** — buy flat. Sell better at ★ Crown / Ore / Gilt.
4. **Travel** — tap a linked neighbor, read **quiet / hot / contested** and your power vs the lane, then Launch.
5. Map markers **W / P / L / T** (War / Pirate / Patrol / Trade) park near systems, denser at rich hubs, and bias encounters. Fight / Leave / Tribute.
6. ~14 turns. Ledger. A **POOR** banner shows when the purse is thin.

Open locally:

```bash
python3 -m http.server 8766
# → http://localhost:8766/
```
