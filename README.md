# Gloop Box

A single-file HTML sandbox toy. Gloop is a squishy jelly creature with soft-body physics, a mood and a health meter. Tickle, pet, feed, fling and pester it, earn coins, and unlock new tools.

Open `index.html` in any modern browser. No install or server needed.

## Tools

| Tool | Cost | What it does |
|---|---|---|
| Hand | free | Drag and fling Gloop or items. Hover slowly to pet. |
| Feather | free | Wiggle over Gloop to tickle. Tickles can pay coins. |
| Snack | 2 coins each | Drops a snack. Eating heals and cheers Gloop up. |
| Pin | free | Pokes Gloop. Also pops balls. |
| Ball | 15 | Bouncy ball. |
| Paint | 20 | Cycles Gloop's color. |
| Crate | 30 | Heavy wooden crate. |
| Party hat | 35 | Toggles a hat. |
| Firecracker | 60 | Explodes after a short fuse. |
| Anvil | 90 | Drops from the ceiling. Very heavy. |
| Gravity | 120 | Flips gravity. |

Gloop earns coins on its own while its mood is above 60. If health hits zero it gets knocked out for a few seconds and then recovers.

Progress (coins, unlocks, color, hat, name) is saved in the browser's local storage.

## Updating

The **Update** button checks `version.json` on the `main` branch of this repo. If the version there is newer than the one in the file you're running, you can play the new version right away or save the new file over your old one.

To release an update:

1. Edit `index.html`.
2. Bump `const VERSION = '...'` near the `updates from GitHub` section of the script.
3. Set the same version (and optional `notes`) in `version.json`.
4. Commit and push to `main`.

## Code map

Everything lives in `index.html`:

- `TOOLS`, `LINES`, `COLORS` – content tables, the easiest place to add things
- `spawn()` – item definitions (radius, mass, bounce, friction)
- `step()` – verlet physics: blob springs, pressure, collisions
- `think()` – mood, health, damage, hops, eating, coins
- `drawBlob()`, `drawObj()`, `drawParts()` – rendering
