# Gloop Box

A single-file HTML sandbox toy. Gloop is a squishy jelly creature with soft-body physics, a mood and a health meter. Tickle, pet, feed, fling and pester it, earn coins, and unlock new tools.

**Play it online:** https://kefirman9000.github.io/gloop-box/

Or open `index.html` in any modern browser. No install or server needed.

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
| Mallet | 40 | Bonks Gloop away from your tap. |
| Bowling ball | 50 | Very heavy ball. |
| Cactus | 55 | Stings on contact. |
| Zapper | 70 | A one-second jolt. |
| Rocket | 100 | Homes in on Gloop and explodes. |
| Black hole | 150 | Pulls everything in for 4 seconds. |
| Storm cloud | 130 | Drifts over Gloop and strikes with lightning. |
| Trampoline | 45 | Bounces anything that lands on it. |
| Fan | 55 | Blows toward Gloop. |
| Goo puddle | 35 | Sticky floor that slows things down. |
| Potion | 90 | Shrink, grow, bouncy or liquid for 12 seconds. |
| Weather | 100 | Cycles snow, heat wave, wind and clear skies. |
| Pip | 150 | A little jelly pal. Tap Pip to switch between friend and rival. |
| Shelf | 30 | A platform things can land on. |
| Ramp | 40 | Slopes down toward Gloop. |
| Seesaw | 70 | Drop something heavy on one end to launch the other. |
| Critter | 80 | A butterfly or ladybug for Gloop to chase. |
| Pillow | 20 | Soft landing spot. Slams on it do no damage. |
| Banana peel | 25 | Gloop slips and spins if it steps on it. |
| Bubble wand | 75 | Gloop floats in a bubble until it pops. |
| Magnet | 85 | Hold to pull metal items, and Gloop in a chrome or gold skin. |

## Shop, games and trophies

- **Wardrobe:** 10 skins, 14 colors, 5 eye styles, hats, eyewear, patterns and a sparkle trail. Some unlock through trophies and stats.
- **Shop:** 8 rooms and every tool. Locked tools can be tried free for 15 seconds once a day.
- **Growing up:** Gloop goes from Baby to Grown-up over hours of play.
- **Day and night:** follows your clock (can be turned off in Settings).
- **Collection:** 12 collectibles drop from games; two unlock a skin and an eye style.
- **Tricks:** reward Gloop with a snack right after it shows off a trick. Three rewards and it learns it for good.
- **Building:** shelves, ramps and a seesaw catapult. Your layout is saved. Undo removes the last thing you placed.
- **Tool bar:** right-click or press and hold a tool to pin it to the front.
- **Games:** Keep-up, Snack Rain, Hide and Seek, Copy Me, Bounce Tower, Target Toss, Gloop Goal, a weekly boss and Fetch. Every game pays at least 5 coins plus a score bonus.
- **Trophies:** 22 goals that each pay coins, plus a stats page.
- **Personality:** Gloop has trust, hunger, boredom and naps. Treat it well and it comes to greet you; treat it badly and it spits jelly at your cursor.
- **Daily gift and challenge:** coins every day you visit, more for a streak, plus one daily challenge worth 60 coins.
- **Photo mode:** pause the room, add stickers and save a picture.
- **Music and settings:** room music, volume, calm mode and a reset button.
- **Phones:** pinch to zoom, and press and hold on an empty spot for a menu of your recent tools.
- **Item reactions:** snow freezes goo, lightning or the zapper electrifies it, firecrackers set off crates, and black holes eat items.
- **Reactions:** hits chain into combos that pay coins, hard slams kick up dust and can knock Gloop out, and after being hurt Gloop backs away from weapons.

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
