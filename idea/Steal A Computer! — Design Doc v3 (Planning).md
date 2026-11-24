# Steal A Computer! — Design Doc v3 (Planning)

Nov 24, 2026 · @Zwei

## Overview

Steal A Computer! is a Roblox game about building PCs, mining crypto with GPUs, and raiding other players' offices. The core loop is settled, but several numbers and rules are still open. This doc records what is locked and what is still open.

## Confirmed decisions

- Stealing and mining are both core. Stealing needs players to feel exciting; mining hooks them early.
- Sessions start short, and systems unlock as players progress.
- Each player has an office with a personal PC and separate GPU racks.
- Mining runs automatically while the player is in the game.
- A GPU mines only while installed in a rack. Removing it stops its output immediately.
- Offline crypto is protected. Only online players can be raided.
- Installed GPUs can be stolen by entering another player's office and taking GPUs from their racks.
- Raids use a hybrid of stats and light player decisions.
- A successful breach opens the office for a fixed time window.
- Stolen GPUs must be carried home to be kept. If the thief dies or leaves first, they return to the victim.
- Carry capacity is measured in slots. Backpacks increase it. Larger, rarer GPUs take more slots.
- Raid success lets the attacker take as many GPUs as their carry capacity allows.
- Backpacks are bought in the store. Special backpacks may come from the merchant.
- Newbie protection lasts until the first PvE breach or first GPU install, whichever is later.
- NPC breach rewards are component boxes plus crypto.
- Some challenges and tasks do not involve NPCs.
- Robux purchases are deferred.

## Core loop and early pacing

1. Join, see the office, and mining is already running.
2. Take a board request; finish it to earn enough for a first GPU.
3. Buy the first GPU, carry it, and snap it into a rack slot. Output visibly jumps.
4. Complete a first PvE breach on a weak-tier NPC office. Reward: a component box plus crypto.
5. Open the box, install the part, and see the next goal.

Target: first GPU by about 10 minutes, first breach by about 15 minutes.

## Mining rules

- Output = GPU base rate × rarity multiplier, summed across installed GPUs. Values are unset.
- Rarer GPUs produce more crypto and take more slots.
- Each rack has a fixed number of slots. Capacity is undecided.
- Offline earnings are capped. Proposed cap: 1 to 2 hours (not yet decided).
- Crypto value may drift slowly. Exact behaviour is undecided.
- GPU designs must look good enough to keep players engaged. Visual tiers are undecided.

## Raiding and hacking rules

The proposed breach flow:

1. **Scan:** see the target's visible defense level and rack count. Costs time or crypto.
2. **Load:** choose attack features, limited by RAM. The main decision.
3. **Breach:** server decides from CPU speed and loaded features against the defender's active defense. One short timing input adds a bonus.
4. **Open window:** on success, the office opens for a fixed time. Victim gets an alert. Length is undecided.
5. **Extract:** take GPUs from racks, limited by carry capacity.
6. **Escape:** return home to keep the GPUs. Death or leaving first returns them to the victim.

Proposed: a raid cooldown on the same victim, and a short shield after a successful raid. Defense features shape breach odds and are chosen within RAM.

## PvE content, NPC requests, and challenges

- **NPC client offices:** fixed tiers (weak, medium, strong), breached with the same flow as a player raid. No victim response.
- **NPC request board:** short jobs in the central area, such as mining a target amount, breaching a weak office, or delivering a GPU. Pays crypto, boxes, or both.
- **Component boxes:** one component per box, weighted by rarity. Contents are previewed before opening. Box tier matches challenge tier.
- **Non-NPC challenges:** self-contained tasks, such as mining milestones, PC upgrades, and timed system-optimization jobs.

Open: reward values, box odds, and how many requests are active at once.

## Carrying, backpacks, and special GPUs

- Carry capacity is measured in slots. Base capacity is proposed at 3 slots; undecided.
- Backpacks add capacity. Store-bought; special backpacks possibly from the merchant. Tiers and prices are undecided.
- Rare GPUs can be merchant stock and take multiple slots.
- Special GPU behaviour beyond slot size is undecided.

## Proposed values not yet balanced

- Starting cash and first GPU price.
- Rack slot count per rack.
- Mining rates by rarity, hardware prices, and crypto exchange rate.
- Box odds and component values.
- Breach timing: open window length, cooldowns, and feature costs.
- Backpack prices and capacities.
- Offline cap (proposed 1 to 2 hours).
- Newbie protection: decided as outlined above; length is tied to milestones, not a timer.

## Undecided questions

- [ ] Newbie protection: confirm it ends at first PvE breach or first GPU install, whichever is later.
- [ ] Open-window length: depends on player count and map distance.
- [ ] Rack slot sizing: do slots match GPU size?
- [ ] Special GPU behaviour and visual tiers.
- [ ] Backpack tiers, costs, and merchant vs store split.
- [ ] Raid frequency and targeting limits.
- [ ] Victim recovery after a raid.
- [ ] Crypto exchange: simple claim at the bank, or a PC step first?
- [ ] Which PC parts matter in the prototype (proposed: CPU, RAM, SSD).

## Next planning steps

1. Settle the undecided list above.
2. Draft the economy numbers (prices, mining rates, box odds) as a table for tuning.
3. Define the breach formula and the full feature list.
4. Scope the prototype: one office, one rack, one NPC office, one request, one box.

## Sources

None. This doc records planning decisions only.
